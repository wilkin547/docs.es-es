---
title: Tutorial sobre cómo incluir una aplicación en un contenedor con Docker
description: En este tutorial obtendrá información sobre cómo incluir una aplicación de .NET Core en un contenedor con Docker.
ms.date: 01/09/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: e1904430a591b0e74a69d50a53869a130fc0a248
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "78157835"
---
# <a name="tutorial-containerize-a-net-core-app"></a>Tutorial: Incluir una aplicación de .NET Core en un contenedor

En este tutorial se ofrece información sobre cómo compilar una imagen de Docker que contiene una aplicación de .NET Core. La imagen puede usarse para crear contenedores para un entorno de desarrollo local, una nube privada o una nube pública.

Aprenderá a hacer lo siguiente:

> [!div class="checklist"]
>
> - Crear y publicar una aplicación .NET Core sencilla
> - Crear y configurar un archivo Dockerfile para .NET Core
> - Creación de una imagen de Docker
> - Crear y ejecutar un contenedor de Docker

Aprenderá sobre las tareas de compilación e implementación de un contenedor de Docker para una aplicación .NET Core. La *plataforma Docker* usa el *motor de Docker* para compilar y empaquetar rápidamente aplicaciones como *imágenes de Docker*. Estas imágenes se escriben en el formato *Dockerfile* para implementarse y ejecutarse en un contenedor superpuesto.

> [!TIP]
> Si está trabajando con una aplicación de ASP.NET Core, consulte el tutorial [Obtenga información sobre cómo incluir una aplicación ASP.NET Core en contenedores](/aspnet/core/host-and-deploy/docker/building-net-docker-images).

## <a name="prerequisites"></a>Requisitos previos

Instale estos requisitos previos:

- [SDK de .NET Core 3.1](https://dotnet.microsoft.com/download)\
Si tiene instalado .NET Core, use el comando `dotnet --info` para determinar el SDK que está usando.

- [Docker Community Edition](https://www.docker.com/products/docker-desktop)

- Una carpeta de trabajo temporal para *Dockerfile* y una aplicación .NET Core de ejemplo. En este tutorial, el nombre *docker-working* se usa como la carpeta de trabajo.

## <a name="create-net-core-app"></a>Creación de una aplicación .NET Core

Necesita una aplicación .NET Core que el contenedor de Docker ejecutará. Abra el terminal, cree una carpeta de trabajo si todavía no lo ha hecho y entre en ella. En la carpeta de trabajo, ejecute el comando siguiente para crear un proyecto en un subdirectorio llamado *app*:

```dotnetcli
dotnet new console -o app -n myapp
```

El árbol de carpetas tendrá un aspecto similar al siguiente:

```
docker-working
│
└───app
    │   myapp.csproj
    │   Program.cs
    │
    └───obj
            myapp.csproj.nuget.cache
            myapp.csproj.nuget.dgspec.json
            myapp.csproj.nuget.g.props
            myapp.csproj.nuget.g.targets
            project.assets.json
```

Con el comando `dotnet new` se crea una carpeta denominada *app* y se genera una aplicación "Hola mundo". Entre en la carpeta *app* y ejecute el comando `dotnet run`. Verá la salida siguiente:

```console
> dotnet run
Hello World!
```

La plantilla predeterminada crea una aplicación que imprime en el terminal y luego se cierra. En este tutorial, se usará una aplicación que se repite en bucle de manera indefinida. Abra el archivo *Program.cs* en un editor de texto. Actualmente debe ser similar al código siguiente:

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
            while (max == -1 || counter < max)
            {
                counter++;
                Console.WriteLine($"Counter: {counter}");
                System.Threading.Tasks.Task.Delay(1000).Wait();
            }
        }
    }
}
```

Guarde el archivo y vuelva a probar el programa con `dotnet run`. Recuerde que esta aplicación se ejecuta de manera indefinida. Use el comando de cancelación <kbd>CTRL</kbd>+<kbd>C</kbd> para detenerla. Verá la salida siguiente:

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

Desde la carpeta de trabajo, entre en la carpeta *app* con el código fuente de ejemplo y ejecute el comando siguiente:

```dotnetcli
dotnet publish -c Release
```

Con este comando se compila la aplicación en la carpeta *publish*. La ruta de acceso a la carpeta *publish* desde la carpeta de trabajo debería ser `.\app\bin\Release\netcoreapp3.1\publish\`.

En la carpeta *app*, obtenga un listado de los directorios de la carpeta publish para comprobar que se creó el archivo *myapp.dll*.

```console
> dir bin\Release\netcoreapp3.1\publish

    Directory:  C:\docker-working\app\bin\Release\netcoreapp3.1\publish

01/09/2020  11:41 AM    <DIR>          .
01/09/2020  11:41 AM    <DIR>          ..
01/09/2020  11:41 AM               407 myapp.deps.json
01/09/2020  12:15 PM             4,608 myapp.dll
01/09/2020  12:15 PM           169,984 myapp.exe
01/09/2020  12:15 PM               736 myapp.pdb
01/09/2020  11:41 AM               154 myapp.runtimeconfig.json
```

Si usa Linux o macOS, use el comando `ls` para obtener una lista de directorios y comprobar que se ha creado el archivo *dmyapp.dll*.

```bash
me@DESKTOP:/docker-working/app$ ls bin/Release/netcoreapp3.1/publish
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
```

## <a name="create-the-dockerfile"></a>Creación del archivo Dockerfile

El archivo *Dockerfile* lo usa el comando `docker build` para crear una imagen de contenedor. Este archivo es un archivo de texto denominado *Dockerfile* que no tiene ninguna extensión.

En el terminal, suba un directorio a la carpeta de trabajo creada al principio. Cree un archivo denominado *Dockerfile* en la carpeta de trabajo y ábralo en un editor de texto. En función del tipo de aplicación que vaya a incluir en un contenedor, elija el runtime de ASP.NET Core o el de .NET Core. En duda, elija el runtime de ASP.NET Core, que incluye el de .NET Core. En este tutorial se usará la imagen del runtime de ASP.NET Core, pero la aplicación creada en las secciones anteriores es una aplicación de .NET Core.

- Runtime de ASP.NET Core

  ```dockerfile
  FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
  ```

- Tiempo de ejecución de .NET Core

  ```dockerfile
  FROM mcr.microsoft.com/dotnet/core/runtime:3.1
  ```

El comando `FROM` indica a Docker que extraiga la imagen etiquetada **3.1** del repositorio especificado. Asegúrese de extraer el runtime que coincida con el que el SDK tiene como destino. Por ejemplo, la aplicación creada en la sección anterior usaba el SDK de .NET Core 3.1, y la imagen base a la que se hace referencia en el documento *Dockerfile* se etiqueta con **3.1**.

Guarde el archivo *Dockerfile*. La estructura de directorios de la carpeta de trabajo debería tener el siguiente aspecto. Algunos de los archivos de carpetas y archivos inferiores se han cortado para ahorrar espacio en este artículo:

```
docker-working
│   Dockerfile
│
└───app
    │   myapp.csproj
    │   Program.cs
    │
    ├───bin
    │   └───Release
    │       └───netcoreapp3.1
    │           └───publish
    │                   myapp.deps.json
    │                   myapp.exe
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
myimage                                 latest              38db0eb8f648        4 weeks ago         346MB
mcr.microsoft.com/dotnet/core/aspnet    3.1                 38db0eb8f648        4 weeks ago         346MB
```

Observe que ambas imágenes comparten el mismo valor **IMAGE ID**. El valor es el mismo entre ambas imágenes porque el único comando en *Dockerfile* era basar la imagen nueva en una imagen existente. Agreguemos dos comandos a *Dockerfile*. Cada comando crear una capa de imagen con el comando final que representa la imagen a la que apuntará el repositorio **myimage**.

```dockerfile
COPY app/bin/Release/netcoreapp3.1/publish/ app/

ENTRYPOINT ["dotnet", "app/myapp.dll"]
```

El comando `COPY` indica a Docker que copie la carpeta especificada en el equipo a una carpeta del contenedor. En este ejemplo, la carpeta *publish* se copia a una carpeta denominada *app* del contenedor.

El comando siguiente, `ENTRYPOINT`, indica a Docker que configure el contenedor para que se ejecute como ejecutable. Cuando el contenedor se inicia, se ejecuta el comando `ENTRYPOINT`. Cuando este comando finaliza, el contenedor se detiene automáticamente.

Desde el terminal, ejecute `docker build -t myimage -f Dockerfile .` y, cuando el comando finalice, ejecute `docker images`.

```console
> docker build -t myimage -f Dockerfile .
Sending build context to Docker daemon  1.624MB
Step 1/3 : FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
 ---> 38db0eb8f648
Step 2/3 : COPY app/bin/Release/netcoreapp3.1/publish/ app/
 ---> 37873673e468
Step 3/3 : ENTRYPOINT ["dotnet", "app/myapp.dll"]
 ---> Running in d8deb7b3aa9e
Removing intermediate container d8deb7b3aa9e
 ---> 0d602ca35c1d
Successfully built 0d602ca35c1d
Successfully tagged myimage:latest

> docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
myimage                                 latest              0d602ca35c1d        4 seconds ago       346MB
mcr.microsoft.com/dotnet/core/aspnet    3.1                 38db0eb8f648        4 weeks ago         346MB
```

Cada comando de *Dockerfile* generó una capa y creó un valor **IMAGE ID**. El valor **IMAGE ID** final (el suyo será distinto) es **ddcc6646461b** y, a continuación, usted creará un contenedor basado en esta imagen.

## <a name="create-a-container"></a>Crear un contenedor

Ahora que tiene una imagen que contiene la aplicación, puede crear un contenedor. Hay dos formas de crear un contenedor. En primer lugar, cree un contenedor que esté detenido.

```console
> docker create myimage
ceda87b219a4e55e9ad5d833ee1a7ea4da21b5ea7ce5a7d08f3051152e784944
```

El comando `docker create` anterior creará un contenedor basado en la imagen **myimage**. La salida de ese comando muestra el valor **CONTAINER ID** (el suyo será distinto) del contenedor creado. Para ver una lista de *todos* los contenedores, use el comando `docker ps -a`:

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS        PORTS   NAMES
ceda87b219a4        myimage             "dotnet app/myapp.dll"   4 seconds ago       Created               gallant_lehmann
```

### <a name="manage-the-container"></a>Administración del contenedor

Cada contenedor tiene asignado un nombre aleatorio que puede usar para hacer referencia a la instancia de contenedor. Por ejemplo, el contenedor que se creó automáticamente eligió el nombre **gallant_lehmann** (el suyo será distinto) y ese nombre se puede usar para iniciar el contenedor. Puede reemplazar el nombre automático por uno específico si usa el parámetro `docker create --name`.

En el ejemplo siguiente se usa el comando `docker start` para iniciar el contenedor y luego se usa el comando `docker ps` para mostrar solo los contenedores que están en ejecución:

```console
> docker start gallant_lehmann
gallant_lehmann

> docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS         PORTS   NAMES
ceda87b219a4        myimage             "dotnet app/myapp.dll"   7 minutes ago       Up 8 seconds           gallant_lehmann
```

De manera similar, el comando `docker stop` detendrá el contenedor. En el ejemplo siguiente se usa el comando `docker stop` para detener el contenedor y luego se usa el comando `docker ps` para mostrar que no hay ningún contenedor en ejecución:

```console
> docker stop gallant_lehmann
gallant_lehmann

> docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS   NAMES
```

### <a name="connect-to-a-container"></a>Conectarse a un contenedor

Una vez que se ejecuta un contenedor, puede conectarse a él para ver la salida. Use los comandos `docker start` y `docker attach` para iniciar el contenedor y echar un vistazo al flujo de salida. En este ejemplo, el comando <kbd>Ctrl+C</kbd> se usa para desasociarse del contenedor en ejecución. Esta pulsación de teclas podría realmente finalizar el proceso en el contenedor, lo que detendrá el contenedor. El parámetro `--sig-proxy=false` garantiza que <kbd>CTRL + C</kbd> no detendrá el proceso en el contenedor.

Después de desasociarse del contenedor, reasócielo para comprobar que sigue en ejecución.

```console
> docker start gallant_lehmann
gallant_lehmann

> docker attach --sig-proxy=false gallant_lehmann
Counter: 7
Counter: 8
Counter: 9
^C

> docker attach --sig-proxy=false gallant_lehmann
Counter: 17
Counter: 18
Counter: 19
^C
```

### <a name="delete-a-container"></a>Eliminación de un contenedor

Para el propósito de este artículo, no queremos contenedores que solo existan y no hagan nada. Elimine el contenedor que creó anteriormente. Si el contenedor está en ejecución, deténgalo.

```console
> docker stop gallant_lehmann
```

En el ejemplo siguiente se muestran todos los contenedores. Luego, usa el comando `docker rm` para eliminar el contenedor y después vuelve a comprobar si hay algún contenedor en ejecución.

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS     PORTS   NAMES
ceda87b219a4        myimage             "dotnet app/myapp.dll"   19 minutes ago      Exited             gallant_lehmann

> docker rm gallant_lehmann
gallant_lehmann

> docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS    NAMES
```

### <a name="single-run"></a>Ejecución única

Docker proporciona el comando `docker run` para crear y ejecutar el contenedor como comando único. Este comando elimina la necesidad de ejecutar `docker create` y luego `docker start`. También puede establecer este comando en que elimine automáticamente el contenedor cuando este se detenga. Por ejemplo, use `docker run -it --rm` para hacer dos cosas: primero, use automáticamente el terminal actual para conectarse al contenedor y cuando el contenedor finalice, quítelo:

```console
> docker run -it --rm myimage
Counter: 1
Counter: 2
Counter: 3
Counter: 4
Counter: 5
^C
```

Con `docker run -it`, el comando <kbd>CTRL + C</kbd> detendrá el proceso que está en ejecución en el contenedor, lo que, a su vez, detendrá el contenedor. Como se proporcionó el parámetro `--rm`, el contenedor se elimina automáticamente cuando se detiene el proceso. Compruebe que no existe:

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS    PORTS   NAMES
```

### <a name="change-the-entrypoint"></a>Cambio de ENTRYPOINT

El comando `docker run` también permite modificar el comando `ENTRYPOINT` desde el archivo *Dockerfile* y ejecute algún otro elemento, pero solo para ese contenedor. Por ejemplo, use el comando siguiente para ejecutar `bash` o `cmd.exe`. Edite el comando según sea necesario.

#### <a name="windows"></a>Windows

En este ejemplo, `ENTRYPOINT` cambia a `cmd.exe`. Se presiona <kbd>CTRL</kbd>+<kbd>C</kbd> para finalizar el proceso y detener el contenedor.

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

- [docker build](https://docs.docker.com/engine/reference/commandline/build/)
- [docker run](https://docs.docker.com/engine/reference/commandline/run/)
- [docker ps](https://docs.docker.com/engine/reference/commandline/ps/)
- [docker stop](https://docs.docker.com/engine/reference/commandline/stop/)
- [docker rm](https://docs.docker.com/engine/reference/commandline/rm/)
- [docker rmi](https://docs.docker.com/engine/reference/commandline/rmi/)
- [docker image](https://docs.docker.com/engine/reference/commandline/image/)

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
docker rmi mcr.microsoft.com/dotnet/core/aspnet:3.1
```

Use el comando `docker images` para ver una lista de las imágenes instaladas.

> [!NOTE]
> Los archivos de imagen pueden ser grandes. Por lo general, quitaría los contenedores temporales que creó al probar y desarrollar la aplicación. Habitualmente, estas imágenes base se conservan con el runtime instalado si se planea crear otras imágenes basadas en ese runtime.

## <a name="next-steps"></a>Pasos siguientes

- [Obtenga información sobre cómo incluir una aplicación ASP.NET Core en contenedores.](/aspnet/core/host-and-deploy/docker/building-net-docker-images)
- [Consulte el tutorial de ASP.NET Core para los microservicios](https://dotnet.microsoft.com/learn/web/aspnet-microservice-tutorial/intro).
- [Revise los servicios de Azure que admiten contenedores](https://azure.microsoft.com/overview/containers/).
- [Lea sobre los comandos de Dockerfile](https://docs.docker.com/engine/reference/builder/).
- [Explorar las herramientas de contenedor para Visual Studio](/visualstudio/containers/overview)
