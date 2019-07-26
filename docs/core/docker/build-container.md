---
title: Tutorial sobre cómo incluir una aplicación en un contenedor con Docker
description: En este tutorial obtendrá información sobre cómo incluir una aplicación de .NET Core en un contenedor con Docker.
ms.date: 06/26/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 81b3ce2d6ebb73648d9026c92f490dcc723014f6
ms.sourcegitcommit: 09d699aca28ae9723399bbd9d3d44aa0cbd3848d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/19/2019
ms.locfileid: "68331048"
---
# <a name="tutorial-containerize-a-net-core-app"></a>Tutorial: Incluir una aplicación de .NET Core en un contenedor

En este tutorial se ofrece información sobre cómo compilar una imagen de Docker que contiene una aplicación de .NET Core. La imagen puede usarse para crear contenedores para un entorno de desarrollo local, una nube privada o una nube pública.

Aprenderá a hacer lo siguiente:

> [!div class="checklist"]
> * Crear y publicar una aplicación .NET Core sencilla
> * Crear y configurar un archivo Dockerfile para .NET Core
> * Creación de una imagen de Docker
> * Crear y ejecutar un contenedor de Docker

Aprenderá sobre las tareas de compilación e implementación de un contenedor de Docker para una aplicación .NET Core. La *plataforma Docker* usa el *motor de Docker* para compilar y empaquetar rápidamente aplicaciones como *imágenes de Docker*. Estas imágenes se escriben en el formato *Dockerfile* para implementarse y ejecutarse en un contenedor superpuesto.

## <a name="prerequisites"></a>Requisitos previos

Instale estos requisitos previos:

* [SDK de .NET Core 2.2](https://dotnet.microsoft.com/download)\
Si tiene instalado .NET Core, use el comando `dotnet --info` para determinar el SDK que está usando.

* [Docker Community Edition](https://www.docker.com/products/docker-desktop)

* Una carpeta de trabajo temporal para *Dockerfile* y una aplicación .NET Core de ejemplo. En este tutorial, el nombre `docker-working` se usa como la carpeta de trabajo.

### <a name="use-sdk-version-22"></a>Uso de la versión 2.2 del SDK

Si usa un SDK más reciente, como 3.0, asegúrese de que la aplicación tenga que usar el SDK 2.2. Cree un archivo denominado `global.json` en la carpeta de trabajo y pegue el código JSON siguiente:

```json
{
  "sdk": {
    "version": "2.2.100"
  }
}
```

Guarde este archivo. La presencia del archivo obligará a .NET Core a usar la versión 2.2 para cualquier comando `dotnet` llamado desde esta carpeta y por debajo.

## <a name="create-net-core-app"></a>Creación de una aplicación .NET Core

Necesita una aplicación .NET Core que el contenedor de Docker ejecutará. Abra el terminal, cree una carpeta de trabajo si todavía no lo ha hecho y entre en ella. En la carpeta de trabajo, ejecute el comando siguiente para crear un proyecto en un subdirectorio denominado app:

```console
dotnet new console -o app -n myapp
```

El árbol de carpetas tendrá un aspecto similar al siguiente:

```console
docker-working
│   global.json
│
└───app
    │   myapp.csproj
    │   Program.cs
    │
    └───obj
            myapp.csproj.nuget.cache
            myapp.csproj.nuget.g.props
            myapp.csproj.nuget.g.targets
            project.assets.json
```

Con el comando `dotnet new` se crea una carpeta denominada *app* y se genera una aplicación "Hola mundo". Entre en la carpeta *app* y ejecute el comando `dotnet run`. Verá la salida siguiente:

```console
> dotnet run
Hello World!
```

La plantilla predeterminada crea una aplicación que imprime en el terminal y luego se cierra. En este tutorial, se usará una aplicación que se repite en bucle de manera indefinida. Abra el archivo **Program.cs** en un editor de texto. Actualmente debe ser similar al código siguiente:

```csharp
using System;

namespace myapp
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

Reemplace el archivo por el código siguiente que cuenta números cada segundo:

```csharp
using System;

namespace myapp
{
    class Program
    {
        static void Main(string[] args)
        {
            var counter = 0;
            var max = args.Length != 0 ? Convert.ToInt32(args[0]) : -1;
            while(max == -1 || counter < max)
            {
                counter++;
                Console.WriteLine($"Counter: {counter}");
                System.Threading.Tasks.Task.Delay(1000).Wait();
            }
        }
    }
}
```

Guarde el archivo y vuelva a probar el programa con `dotnet run`. Recuerde que esta aplicación se ejecuta de manera indefinida. Use el comando Cancelar <kbd>CTRL + C</kbd> para detenerla. Verá la salida siguiente:

```console
> dotnet run
Counter: 1
Counter: 2
Counter: 3
Counter: 4
^C
```

Si pasa un número en la línea de comandos a la aplicación, solo se contará hasta esa cantidad y se cerrará. Inténtelo con `dotnet run -- 5` para contar hasta cinco.

> [!NOTE]
> Cualquier parámetro posterior a `--` no se pasa al comando `dotnet run` y, en su lugar, se pasa a su aplicación.

## <a name="publish-net-core-app"></a>Publicación de una aplicación .NET Core

Antes de agregar la aplicación .NET Core a la imagen de Docker, publíquela. Quiere asegurarse de que el contenedor ejecuta la versión publicada de la aplicación al iniciarse.

Desde la carpeta de trabajo, entre en la carpeta **app** con el código fuente de ejemplo y ejecute el comando siguiente:

```console
dotnet publish -c Release
```

Con este comando se compila la aplicación en la carpeta **publish**. La ruta de acceso a la carpeta **publish** desde la carpeta de trabajo debería ser `.\app\bin\Release\netcoreapp2.2\publish\`.

Obtenga un listado de los directorios de la carpeta publish para comprobar que se creó el archivo **myapp.dll**. Desde la carpeta **app**, ejecute uno de los comandos siguientes:

```console
> dir bin\Release\netcoreapp2.2\publish
 Directory of C:\docker-working\app\bin\Release\netcoreapp2.2\publish

04/05/2019  11:00 AM    <DIR>          .
04/05/2019  11:00 AM    <DIR>          ..
04/05/2019  11:00 AM               447 myapp.deps.json
04/05/2019  11:00 AM             4,608 myapp.dll
04/05/2019  11:00 AM               448 myapp.pdb
04/05/2019  11:00 AM               154 myapp.runtimeconfig.json
```

```bash
me@DESKTOP:/docker-working/app$ ls bin/Release/netcoreapp2.2/publish
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
```

## <a name="create-the-dockerfile"></a>Creación del archivo Dockerfile

El archivo *Dockerfile* lo usa el comando `docker build` para crear una imagen de contenedor. Este archivo es un archivo de texto no cifrado denominado *Dockerfile* que no tiene ninguna extensión.

En el terminal, suba un directorio a la carpeta de trabajo creada al principio. Cree un archivo denominado *Dockerfile* en la carpeta de trabajo y ábralo en un editor de texto. Agregue el comando siguiente como la primera línea del archivo:

```dockerfile
FROM mcr.microsoft.com/dotnet/core/runtime:2.2
```

El comando `FROM` indica a Docker que extraiga la imagen con la etiqueta **2.2** desde el repositorio **mcr.microsoft.com/dotnet/core/runtime**. Asegúrese de extraer el runtime de .NET Core que coincida con el runtime que el SDK tiene como destino. Por ejemplo, en la aplicación que se creó en la sección anterior se usó el SDK de .NET Core 2.2 y se creó una aplicación destinada a .NET Core 2.2. Por lo tanto, la imagen base a la que se hace referencia en *Dockerfile* tiene la etiqueta **2.2**.

Guarde el archivo *Dockerfile*. La estructura de directorios de la carpeta de trabajo debería tener el siguiente aspecto. Algunos de los archivos de carpetas y archivos inferiores se han cortado para ahorrar espacio en este artículo:

```console
docker-working
│   Dockerfile
│   global.json
│
└───app
    │   myapp.csproj
    │   Program.cs
    │
    ├───bin
    │   └───Release
    │       └───netcoreapp2.2
    │           └───publish
    │                   myapp.deps.json
    │                   myapp.dll
    │                   myapp.pdb
    │                   myapp.runtimeconfig.json
    │
    └───obj
```

Desde un terminal, ejecute el comando siguiente:

```console
docker build -t myimage -f Dockerfile .
```

Docker procesará cada línea en el archivo *Dockerfile*. `.` del comando `docker build` indica a Docker que use la carpeta actual para encontrar un archivo *Dockerfile*. Este comando crea la imagen y un repositorio local denominado **myimage** que apunta a esa imagen. Una vez que finalice este comando, ejecute `docker images` para ver una lista de las imágenes instaladas:

```console
> docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
mcr.microsoft.com/dotnet/core/runtime   2.2                 d51bb4452469        2 days ago          314MB
myimage                                 latest              d51bb4452469        2 days ago          314MB
```

Observe que ambas imágenes comparten el mismo valor **IMAGE ID**. El valor es el mismo entre ambas imágenes porque el único comando en *Dockerfile* era basar la imagen nueva en una imagen existente. Agreguemos dos comandos a *Dockerfile*. Cada comando crear una capa de imagen nueva con el comando final que representa la imagen a la que apuntará el repositorio **myimage**.

```dockerfile
COPY app/bin/Release/netcoreapp2.2/publish/ app/

ENTRYPOINT ["dotnet", "app/myapp.dll"]
```

El comando `COPY` indica a Docker que copie la carpeta especificada en el equipo a una carpeta del contenedor. En este ejemplo, la carpeta **publish** se copia a una carpeta denominada **app** del contenedor.

El comando siguiente, `ENTRYPOINT`, indica a Docker que configure el contenedor para que se ejecute como ejecutable. Cuando el contenedor se inicia, se ejecuta el comando `ENTRYPOINT`. Cuando este comando finaliza, el contenedor se detiene automáticamente.

Desde el terminal, ejecute `docker build -t myimage -f Dockerfile .` y, cuando el comando finalice, ejecute `docker images`.

```console
> docker build -t myimage -f Dockerfile .
Sending build context to Docker daemon  819.7kB
Step 1/3 : FROM mcr.microsoft.com/dotnet/core/runtime:2.2
 ---> d51bb4452469
Step 2/3 : COPY app/bin/Release/netcoreapp2.2/publish/ app/
 ---> a1e98ac62017
Step 3/3 : ENTRYPOINT ["dotnet", "app/myapp.dll"]
 ---> Running in f34da5c18e7c
Removing intermediate container f34da5c18e7c
 ---> ddcc6646461b
Successfully built ddcc6646461b
Successfully tagged myimage:latest

> docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
myimage                                 latest              ddcc6646461b        10 seconds ago      314MB
mcr.microsoft.com/dotnet/core/runtime   2.2                 d51bb4452469        2 days ago          314MB
```

Cada comando de *Dockerfile* generó una capa y creó un valor **IMAGE ID**. El valor **IMAGE ID** final (el suyo será distinto) es **ddcc6646461b** y, a continuación, usted creará un contenedor basado en esta imagen.

## <a name="create-a-container"></a>Crear un contenedor

Ahora que tiene una imagen que contiene la aplicación, puede crear un contenedor. Hay dos formas de crear un contenedor. En primer lugar, cree un contenedor que esté detenido.

```console
> docker create myimage
0e8f3c2ca32ce773712a5cca38750f41259a4e54e04bdf0946087e230ad7066c
```

El comando `docker create` anterior creará un contenedor basado en la imagen **myimage**. La salida de ese comando muestra el valor **CONTAINER ID** (el suyo será distinto) del contenedor creado. Para ver una lista de *todos* los contenedores, use el comando `docker ps -a`:

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS        PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   4 seconds ago       Created               boring_matsumoto
```

### <a name="manage-the-container"></a>Administración del contenedor

Cada contenedor tiene asignado un nombre aleatorio que puede usar para hacer referencia a la instancia de contenedor. Por ejemplo, el contenedor que se creó automáticamente eligió el nombre **boring_matsumoto** (el suyo será distinto) y ese nombre se puede usar para iniciar el contenedor. Puede reemplazar el nombre automático por uno específico si usa el parámetro `docker create --name`.

En el ejemplo siguiente se usa el comando `docker start` para iniciar el contenedor y luego se usa el comando `docker ps` para mostrar solo los contenedores que están en ejecución:

```console
> docker start boring_matsumoto
boring_matsumoto

> docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS         PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   7 minutes ago       Up 8 seconds           boring_matsumoto
```

De manera similar, el comando `docker stop` detendrá el contenedor. En el ejemplo siguiente se usa el comando `docker stop` para detener el contenedor y luego se usa el comando `docker ps` para mostrar que no hay ningún contenedor en ejecución.

```console
> docker stop boring_matsumoto
boring_matsumoto

> docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS   NAMES
```

### <a name="connect-to-a-container"></a>Conectarse a un contenedor

Una vez que se ejecuta un contenedor, puede conectarse a él para ver la salida. Use los comandos `docker start` y `docker attach` para iniciar el contenedor y echar un vistazo al flujo de salida. En este ejemplo, el comando <kbd>CTRL + C</kbd> se usa para desasociarse del contenedor en ejecución. Esto podría realmente finalizar el proceso en el contenedor, lo que detendrá el contenedor. El parámetro `--sig-proxy=false` garantiza que <kbd>CTRL + C</kbd> no detendrá el proceso en el contenedor.

Después de desasociarse del contenedor, reasócielo para comprobar que sigue en ejecución.

```console
> docker start boring_matsumoto
boring_matsumoto

> docker attach --sig-proxy=false boring_matsumoto
Counter: 7
Counter: 8
Counter: 9
^C

> docker attach --sig-proxy=false boring_matsumoto
Counter: 17
Counter: 18
Counter: 19
^C
```

### <a name="delete-a-container"></a>Eliminación de un contenedor

Para el propósito de este artículo, no queremos contenedores que solo existan y no hagan nada. Elimine el contenedor que creó anteriormente. Si el contenedor está en ejecución, deténgalo.

```console
> docker stop boring_matsumoto
```

En el ejemplo siguiente se muestran todos los contenedores. Luego, usa el comando `docker rm` para eliminar el contenedor y después vuelve a comprobar si hay algún contenedor en ejecución.

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS     PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   19 minutes ago      Exited             boring_matsumoto

> docker rm boring_matsumoto
boring_matsumoto

> docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS    NAMES
```

### <a name="single-run"></a>Ejecución única

Docker proporciona el comando `docker run` para crear y ejecutar el contenedor como comando único. Este comando elimina la necesidad de ejecutar `docker create` y luego `docker start`. También puede establecer este comando en que elimine automáticamente el contenedor cuando este se detenga. Por ejemplo, use `docker run -it --rm` para hacer dos cosas: primero, use automáticamente el terminal actual para conectarse al contenedor y cuando el contenedor finalice, quítelo:

```
> docker run -it --rm myimage
Counter: 1
Counter: 2
Counter: 3
Counter: 4
Counter: 5
^C
```

Con `docker run -it`, el comando <kbd>CTRL + C</kbd> detendrá el proceso que está en ejecución en el contenedor, lo que, a su vez, detendrá el contenedor. Como se proporcionó el parámetro `--rm`, el contenedor se elimina automáticamente cuando se detiene el proceso. Compruebe que no existe:

```
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS    PORTS   NAMES
```

### <a name="change-the-entrypoint"></a>Cambio de ENTRYPOINT

El comando `docker run` también permite modificar el comando `ENTRYPOINT` desde el archivo *Dockerfile* y ejecute algún otro elemento, pero solo para ese contenedor. Por ejemplo, use el comando siguiente para ejecutar `bash` o `cmd.exe`. Edite el comando según sea necesario.

#### <a name="windows"></a>Windows
En este ejemplo, `ENTRYPOINT` cambia a `cmd.exe`. Se presiona <kbd>CTRL + C</kbd> para finalizar el proceso y detener el contenedor.

```console
> docker run -it --rm --entrypoint "cmd.exe" myimage

Microsoft Windows [Version 10.0.17763.379]
(c) 2018 Microsoft Corporation. All rights reserved.

C:\>dir
 Volume in drive C has no label.
 Volume Serial Number is 3005-1E84

 Directory of C:\

04/09/2019  08:46 AM    <DIR>          app
03/07/2019  10:25 AM             5,510 License.txt
04/02/2019  01:35 PM    <DIR>          Program Files
04/09/2019  01:06 PM    <DIR>          Users
04/02/2019  01:35 PM    <DIR>          Windows
               1 File(s)          5,510 bytes
               4 Dir(s)  21,246,517,248 bytes free

C:\>^C
```

#### <a name="linux"></a>Linux

En este ejemplo, `ENTRYPOINT` cambia a `bash`. Se ejecuta el comando `quit`, lo que finaliza el proceso y detiene el contenedor.

```bash
root@user:~# docker run -it --rm --entrypoint "bash" myimage
root@8515e897c893:/# ls app
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
root@8515e897c893:/# exit
exit
```

## <a name="essential-commands"></a>Comandos esenciales

Docker tiene muchos comandos distintos que abarcan las acciones que quiere hacer con el contenedor y las imágenes. Estos comandos de Docker son esenciales para la administración de los contenedores:

* [docker build](https://docs.docker.com/engine/reference/commandline/build/)
* [docker run](https://docs.docker.com/engine/reference/commandline/run/)
* [docker ps](https://docs.docker.com/engine/reference/commandline/ps/)
* [docker stop](https://docs.docker.com/engine/reference/commandline/stop/)
* [docker rm](https://docs.docker.com/engine/reference/commandline/rm/)
* [docker rmi](https://docs.docker.com/engine/reference/commandline/rmi/)
* [docker image](https://docs.docker.com/engine/reference/commandline/image/)

## <a name="clean-up-resources"></a>Limpiar los recursos

Durante este tutorial, creó contenedores e imágenes. Elimine estos recursos si quiere hacerlo. Use los comandos siguientes para

01. Mostrar todos los contenedores

    ```console
    > docker ps -a
    ```

02. Detener los contenedores que están en ejecución `CONTAINER_NAME` representa el nombre que se asignó automáticamente al contenedor.

    ```console
    > docker stop CONTAINER_NAME
    ```

03. Eliminar el contenedor

    ```console
    > docker rm CONTAINER_NAME
    ```

A continuación, elimine las imágenes que ya no quiere tener en la máquina. Elimine la imagen que creó el archivo *Dockerfile* y luego elimine la imagen de .NET Core en que se basó el archivo *Dockerfile*. Puede usar el valor **IMAGE ID** o la cadena con formato **REPOSITORY:TAG**.

```console
docker rmi myimage:latest
docker rmi mcr.microsoft.com/dotnet/core/runtime:2.2
```

Use el comando `docker images` para ver una lista de las imágenes instaladas.

> [!NOTE]
> Los archivos de imagen pueden ser grandes. Por lo general, quitaría los contenedores temporales que creó al probar y desarrollar la aplicación. Habitualmente, estas imágenes base se conservan con el runtime instalado si se planea crear otras imágenes basadas en ese runtime.

## <a name="next-steps"></a>Pasos siguientes

* [Consulte el tutorial de ASP.NET Core para los microservicios](https://dotnet.microsoft.com/learn/web/aspnet-microservice-tutorial/intro).
* [Revise los servicios de Azure que admiten contenedores](https://azure.microsoft.com/overview/containers/).
* [Lea sobre los comandos de Dockerfile](https://docs.docker.com/engine/reference/builder/).
* [Explorar las herramientas de contenedor para Visual Studio](/visualstudio/containers/overview)
