---
title: Tutorial sobre cómo incluir una aplicación en un contenedor con Docker
description: En este tutorial obtendrá información sobre cómo incluir una aplicación de .NET Core en un contenedor con Docker.
ms.date: 04/27/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: c5e6648539af45f3ce615bfc183e6f95a62b085a
ms.sourcegitcommit: 5988e9a29cedb8757320817deda3c08c6f44a6aa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2020
ms.locfileid: "82200033"
---
# <a name="tutorial-containerize-a-net-core-app"></a>Tutorial: Incluir una aplicación de .NET Core en un contenedor

En este tutorial obtendrá información sobre cómo incluir una aplicación de .NET Core en un contenedor con Docker. Los contenedores tienen muchas características y ventajas, como ser una infraestructura inmutable, proporcionar una arquitectura portátil y permitir la escalabilidad. La imagen puede usarse para crear contenedores para un entorno de desarrollo local, una nube privada o una nube pública.

En este tutorial ha:

> [!div class="checklist"]
>
> - Crear y publicar una aplicación .NET Core sencilla
> - Crear y configurar un archivo Dockerfile para .NET Core
> - Creación de una imagen de Docker
> - Crear y ejecutar un contenedor de Docker

Aprenderá sobre las tareas de compilación e implementación de un contenedor de Docker para una aplicación .NET Core. La *plataforma Docker* usa el *motor de Docker* para compilar y empaquetar rápidamente aplicaciones como *imágenes de Docker*. Estas imágenes se escriben en el formato *Dockerfile* para implementarse y ejecutarse en un contenedor superpuesto.

> [!NOTE]
> Este tutorial **no es** para aplicaciones ASP.NET Core. Si usa ASP.NET Core, lea el tutorial sobre [cómo incluir una aplicación de ASP.NET Core en un contenedor](/aspnet/core/host-and-deploy/docker/building-net-docker-images).

## <a name="prerequisites"></a>Requisitos previos

Instale estos requisitos previos:

- [SDK de .NET Core 3.1](https://dotnet.microsoft.com/download)\
Si tiene instalado .NET Core, use el comando `dotnet --info` para determinar el SDK que está usando.
- [Docker Community Edition](https://www.docker.com/products/docker-desktop)
- Una carpeta de trabajo temporal para *Dockerfile* y una aplicación .NET Core de ejemplo. En este tutorial, el nombre *docker-working* se usa como la carpeta de trabajo.

## <a name="create-net-core-app"></a>Creación de una aplicación .NET Core

Necesita una aplicación .NET Core que el contenedor de Docker ejecutará. Abra el terminal, cree una carpeta de trabajo si todavía no lo ha hecho y entre en ella. En la carpeta de trabajo, ejecute el comando siguiente para crear un proyecto en un subdirectorio llamado *app*:

```dotnetcli
dotnet new console -o App -n NetCore.Docker
```

El árbol de carpetas tendrá un aspecto similar al siguiente:

```
docker-working
    └──App
        ├──NetCore.Docker.csproj
        ├──Program.cs
        └──obj
            ├──NetCore.Docker.csproj.nuget.dgspec.json
            ├──NetCore.Docker.csproj.nuget.g.props
            ├──NetCore.Docker.csproj.nuget.g.targets
            ├──project.assets.json
            └──project.nuget.cache
```

Con el comando `dotnet new` se crea una carpeta denominada *App* y se genera una aplicación de consola "Hola mundo". Cambie los directorios y vaya a la carpeta *App*, desde la sesión de Terminal. Use el comando `dotnet run` para iniciar la aplicación. La aplicación se ejecutará e imprimirá `Hello World!` debajo del comando:

```dotnetcli
dotnet run
Hello World!
```

La plantilla predeterminada crea una aplicación que imprime en el terminal y termina de inmediato. En este tutorial, se usará una aplicación que se repite en bucle de manera indefinida. Abra el archivo *Program.cs* en un editor de texto.

> [!TIP]
> Si está utilizando Visual Studio Code, en la sesión de Terminal anterior, escriba el siguiente comando:
>
> ```
> code .
> ```
>
> Se abrirá la carpeta *App* que contiene el proyecto en Visual Studio Code.

El archivo *Program.cs* debería ser similar al código de C# siguiente:

```csharp
using System;

namespace NetCore.Docker
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
using System.Threading.Tasks;

namespace NetCore.Docker
{
    class Program
    {
        static async Task Main(string[] args)
        {
            var counter = 0;
            var max = args.Length != 0 ? Convert.ToInt32(args[0]) : -1;
            while (max == -1 || counter < max)
            {
                Console.WriteLine($"Counter: {++counter}");
                await Task.Delay(1000);
            }
        }
    }
}
```

Guarde el archivo y vuelva a probar el programa con `dotnet run`. Recuerde que esta aplicación se ejecuta de manera indefinida. Use el comando Cancelar <kbd>Ctrl+C</kbd> para detenerla. A continuación se muestra un resultado de ejemplo:

```dotnetcli
dotnet run
Counter: 1
Counter: 2
Counter: 3
Counter: 4
^C
```

Si pasa un número en la línea de comandos a la aplicación, solo se contará hasta esa cantidad y se cerrará. Inténtelo con `dotnet run -- 5` para contar hasta cinco.

> [!IMPORTANT]
> Cualquier parámetro posterior a `--` no se pasa al comando `dotnet run` y, en su lugar, se pasa a su aplicación.

## <a name="publish-net-core-app"></a>Publicación de una aplicación .NET Core

Antes de agregar la aplicación .NET Core a la imagen de Docker, primero debe publicarse. Es mejor que el contenedor ejecute la versión publicada de la aplicación. Ejecute el comando siguiente para publicar la aplicación:

```dotnetcli
dotnet publish -c Release
```

Con este comando se compila la aplicación en la carpeta *publish*. La ruta de acceso a la carpeta *publish* desde la carpeta de trabajo debería ser `.\App\bin\Release\netcoreapp3.1\publish\`.

#### <a name="windows"></a>[Windows](#tab/windows)

En la carpeta *App*, obtenga un listado de los directorios de la carpeta publish para comprobar que se ha creado el archivo *NetCore.Docker.dll*.

```powershell
dir .\bin\Release\netcoreapp3.1\publish\

    Directory: C:\Users\dapine\App\bin\Release\netcoreapp3.1\publish

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        4/27/2020   8:27 AM            434 NetCore.Docker.deps.json
-a----        4/27/2020   8:27 AM           6144 NetCore.Docker.dll
-a----        4/27/2020   8:27 AM         171520 NetCore.Docker.exe
-a----        4/27/2020   8:27 AM            860 NetCore.Docker.pdb
-a----        4/27/2020   8:27 AM            154 NetCore.Docker.runtimeconfig.json
```

#### <a name="linux"></a>[Linux](#tab/linux)

Use el comando `ls` para obtener una lista de directorios y comprobar que se ha creado el archivo *NetCore.Docker.dll*.

```bash
me@DESKTOP:/docker-working/app$ ls bin/Release/netcoreapp3.1/publish
NetCore.Docker.deps.json  NetCore.Docker.dll  NetCore.Docker.pdb  NetCore.Docker.runtimeconfig.json
```

---

## <a name="create-the-dockerfile"></a>Creación del archivo Dockerfile

El archivo *Dockerfile* lo usa el comando `docker build` para crear una imagen de contenedor. Este archivo es un archivo de texto denominado *Dockerfile* que no tiene ninguna extensión.

Cree un archivo denominado *Dockerfile* en el directorio que contiene el archivo *.csproj* y ábralo en un editor de texto. Este tutorial usa la imagen de runtime de ASP.NET Core (que contiene la imagen de runtime de .NET Core) y corresponde a la aplicación de consola de .NET Core.

```dockerfile
FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
```

> [!NOTE]
> Aquí se usa intencionadamente la imagen de runtime de ASP.NET Core, aunque se podría haber usado la imagen de `mcr.microsoft.com/dotnet/core/runtime:3.1`.

La palabra clave `FROM` requiere un nombre completo de imagen de contenedor de Docker. Microsoft Container Registry (MCR, mcr.microsoft.com) es un sindicato de Docker Hub, que hospeda contenedores accesibles públicamente. El segmento `dotnet/core` es el repositorio de contenedores, donde el segmento de `aspnet` es el nombre de la imagen de contenedor. La imagen está etiquetada con `3.1`, que se usa para el control de versiones. Por lo tanto, `mcr.microsoft.com/dotnet/core/aspnet:3.1` es el runtime de .NET Core 3.1. Asegúrese de extraer el runtime que coincida con el que el SDK tiene como destino. Por ejemplo, la aplicación creada en la sección anterior usaba el SDK de .NET Core 3.1, y la imagen base a la que se hace referencia en el documento *Dockerfile* se etiqueta con **3.1**.

Guarde el archivo *Dockerfile*. La estructura de directorios de la carpeta de trabajo debería tener el siguiente aspecto. Algunos de los archivos y carpetas inferiores se han omitido para ahorrar espacio en este artículo:

```
docker-working
    └──App
        ├──Dockerfile
        ├──NetCore.Docker.csproj
        ├──Program.cs
        ├──bin
        │   └──Release
        │       └──netcoreapp3.1
        │           └──publish
        │               ├──NetCore.Docker.deps.json
        │               ├──NetCore.Docker.exe
        │               ├──NetCore.Docker.dll
        │               ├──NetCore.Docker.pdb
        │               └──NetCore.Docker.runtimeconfig.json
        └──obj
            └──...
```

Desde un terminal, ejecute el comando siguiente:

```Docker
docker build -t counter-image -f Dockerfile .
```

Docker procesará cada línea en el archivo *Dockerfile*. `.` del comando `docker build` indica a Docker que use la carpeta actual para encontrar un archivo *Dockerfile*. Este comando crea la imagen y un repositorio local denominado **counter-image** que apunta a esa imagen. Una vez que finalice este comando, ejecute `docker images` para ver una lista de las imágenes instaladas:

```Docker
docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
counter-image                           latest              e6780479db63        4 days ago          190MB
mcr.microsoft.com/dotnet/core/aspnet    3.1                 e6780479db63        4 days ago          190MB
```

Observe que ambas imágenes comparten el mismo valor **IMAGE ID**. El valor es el mismo entre ambas imágenes porque el único comando en *Dockerfile* era basar la imagen nueva en una imagen existente. Agreguemos tres comandos a *Dockerfile*. Cada comando crea una capa de imagen y el comando final que representa la imagen **counter-image** a la que apunta el repositorio.

```dockerfile
COPY bin/Release/netcoreapp3.1/publish/ App/
WORKDIR /App
ENTRYPOINT ["dotnet", "NetCore.Docker.dll"]
```

El comando `COPY` indica a Docker que copie la carpeta especificada en el equipo a una carpeta del contenedor. En este ejemplo, la carpeta *publish* se copia en una carpeta denominada *App* del contenedor.

El comando `WORKDIR` cambia el **directorio actual** dentro del contenedor a *App*.

El comando siguiente, `ENTRYPOINT`, indica a Docker que configure el contenedor para que se ejecute como ejecutable. Cuando el contenedor se inicia, se ejecuta el comando `ENTRYPOINT`. Cuando este comando finaliza, el contenedor se detiene automáticamente.

Desde el terminal, ejecute `docker build -t counter-image -f Dockerfile .` y, cuando el comando finalice, ejecute `docker images`.

```Docker
docker build -t counter-image -f Dockerfile .
Sending build context to Docker daemon  1.117MB
Step 1/4 : FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
 ---> e6780479db63
Step 2/4 : COPY bin/Release/netcoreapp3.1/publish/ App/
 ---> d1732740eed2
Step 3/4 : WORKDIR /App
 ---> Running in b1701a42f3ff
Removing intermediate container b1701a42f3ff
 ---> 919aab5b95e3
Step 4/4 : ENTRYPOINT ["dotnet", "NetCore.Docker.dll"]
 ---> Running in c12aebd26ced
Removing intermediate container c12aebd26ced
 ---> cd11c3df9b19
Successfully built cd11c3df9b19
Successfully tagged counter-image:latest

docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
counter-image                           latest              cd11c3df9b19        41 seconds ago      190MB
mcr.microsoft.com/dotnet/core/aspnet    3.1                 e6780479db63        4 days ago          190MB
```

Cada comando de *Dockerfile* generó una capa y creó un valor **IMAGE ID**. El valor **IMAGE ID** final (el suyo será distinto) es **cd11c3df9b19** y, después, usted creará un contenedor basado en esta imagen.

## <a name="create-a-container"></a>Crear un contenedor

Ahora que tiene una imagen que contiene la aplicación, puede crear un contenedor. Hay dos formas de crear un contenedor. En primer lugar, cree un contenedor que esté detenido.

```Docker
docker create --name core-counter counter-image
0f281cb3af994fba5d962cc7d482828484ea14ead6bfe386a35e5088c0058851
```

El comando `docker create` anterior creará un contenedor basado en la imagen **counter-image**. La salida de ese comando muestra el valor **CONTAINER ID** (el suyo será distinto) del contenedor creado. Para ver una lista de *todos* los contenedores, use el comando `docker ps -a`:

```Docker
docker ps -a
CONTAINER ID    IMAGE            COMMAND                   CREATED           STATUS     PORTS    NAMES
0f281cb3af99    counter-image    "dotnet NetCore.Dock…"    40 seconds ago    Created             core-counter
```

### <a name="manage-the-container"></a>Administración del contenedor

El contenedor se creó con un nombre específico, `core-counter`, usado para administrar el contenedor. En el ejemplo siguiente se usa el comando `docker start` para iniciar el contenedor y luego se usa el comando `docker ps` para mostrar solo los contenedores que están en ejecución:

```Docker
docker start core-counter
core-counter

docker ps
CONTAINER ID    IMAGE            COMMAND                   CREATED          STATUS          PORTS    NAMES
2f6424a7ddce    counter-image    "dotnet NetCore.Dock…"    2 minutes ago    Up 11 seconds            core-counter
```

De manera similar, el comando `docker stop` detendrá el contenedor. En el ejemplo siguiente se usa el comando `docker stop` para detener el contenedor y luego se usa el comando `docker ps` para mostrar que no hay ningún contenedor en ejecución:

```Docker
docker stop core-counter
core-counter

docker ps
CONTAINER ID    IMAGE    COMMAND    CREATED    STATUS    PORTS    NAMES
```

### <a name="connect-to-a-container"></a>Conectarse a un contenedor

Una vez que se ejecuta un contenedor, puede conectarse a él para ver la salida. Use los comandos `docker start` y `docker attach` para iniciar el contenedor y echar un vistazo al flujo de salida. En este ejemplo, la pulsación de teclas <kbd>Ctrl+C</kbd> se usa para desasociarse del contenedor en ejecución. A menos que se especifique lo contrario, esta pulsación de teclas finalizará el proceso en el contenedor, con lo que se detendrá el contenedor. El parámetro `--sig-proxy=false` garantiza que <kbd>Ctrl+C</kbd> no detendrá el proceso en el contenedor.

Después de desasociarse del contenedor, reasócielo para comprobar que sigue en ejecución.

```Docker
docker start core-counter
core-counter

docker attach --sig-proxy=false core-counter
Counter: 7
Counter: 8
Counter: 9
^C

docker attach --sig-proxy=false core-counter
Counter: 17
Counter: 18
Counter: 19
^C
```

### <a name="delete-a-container"></a>Eliminación de un contenedor

Para el propósito de este artículo, no queremos contenedores que solo existan y no hagan nada. Elimine el contenedor que creó anteriormente. Si el contenedor está en ejecución, deténgalo.

```Docker
docker stop core-counter
```

En el ejemplo siguiente se muestran todos los contenedores. Luego, usa el comando `docker rm` para eliminar el contenedor y después vuelve a comprobar si hay algún contenedor en ejecución.

```Docker
docker ps -a
CONTAINER ID    IMAGE            COMMAND                   CREATED          STATUS                        PORTS    NAMES
2f6424a7ddce    counter-image    "dotnet NetCore.Dock…"    7 minutes ago    Exited (143) 20 seconds ago            core-counter

docker rm core-counter
core-counter

docker ps -a
CONTAINER ID    IMAGE    COMMAND    CREATED    STATUS    PORTS    NAMES
```

### <a name="single-run"></a>Ejecución única

Docker proporciona el comando `docker run` para crear y ejecutar el contenedor como comando único. Este comando elimina la necesidad de ejecutar `docker create` y luego `docker start`. También puede establecer este comando en que elimine automáticamente el contenedor cuando este se detenga. Por ejemplo, use `docker run -it --rm` para hacer dos cosas: primero, use automáticamente el terminal actual para conectarse al contenedor y cuando el contenedor finalice, quítelo:

```Docker
docker run -it --rm counter-image
Counter: 1
Counter: 2
Counter: 3
Counter: 4
Counter: 5
^C
```

El contenedor también pasa parámetros a la ejecución de la aplicación .NET Core. Para indicar a la aplicación .NET Core que cuente solo hasta 3, pase 3.

```Docker
docker run -it --rm counter-image 3
Counter: 1
Counter: 2
Counter: 3
```

Con `docker run -it`, el comando <kbd>Ctrl+C</kbd> detendrá el proceso que está ejecutándose en el contenedor, lo que, a su vez, detendrá el contenedor. Como se proporcionó el parámetro `--rm`, el contenedor se elimina automáticamente cuando se detiene el proceso. Compruebe que no existe:

```Docker
docker ps -a
CONTAINER ID    IMAGE    COMMAND    CREATED    STATUS    PORTS    NAMES
```

### <a name="change-the-entrypoint"></a>Cambio de ENTRYPOINT

El comando `docker run` también permite modificar el comando `ENTRYPOINT` desde el archivo *Dockerfile* y ejecute algún otro elemento, pero solo para ese contenedor. Por ejemplo, use el comando siguiente para ejecutar `bash` o `cmd.exe`. Edite el comando según sea necesario.

#### <a name="windows"></a>[Windows](#tab/windows)

En este ejemplo, `ENTRYPOINT` cambia a `cmd.exe`. Se presiona <kbd>Ctrl+C</kbd> para finalizar el proceso y detener el contenedor.

```Docker
docker run -it --rm --entrypoint "cmd.exe" counter-image

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

#### <a name="linux"></a>[Linux](#tab/linux)

En este ejemplo, `ENTRYPOINT` cambia a `bash`. Se ejecuta el comando `exit`, lo que finaliza el proceso y detiene el contenedor.

```bash
docker run -it --rm --entrypoint "bash" counter-image
root@b735b9799abf:/App# ls
NetCore.Docker.deps.json  NetCore.Docker.dll  NetCore.Docker.exe  NetCore.Docker.pdb  NetCore.Docker.runtimeconfig.json
root@b735b9799abf:/App# dotnet NetCore.Docker.dll 3
Counter: 1
Counter: 2
Counter: 3
root@b735b9799abf:/App# exit
exit
```

---

## <a name="essential-commands"></a>Comandos esenciales

Docker tiene muchos comandos diferentes que crean, administran e interactúan con contenedores e imágenes. Estos comandos de Docker son esenciales para la administración de los contenedores:

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

    ```Docker
    docker ps -a
    ```

02. Detener los contenedores que están en ejecución por nombre

    ```Docker
    docker stop counter-image
    ```

03. Eliminar el contenedor

    ```Docker
    docker rm counter-image
    ```

A continuación, elimine las imágenes que ya no quiere tener en la máquina. Elimine la imagen que creó el archivo *Dockerfile* y luego elimine la imagen de .NET Core en que se basó el archivo *Dockerfile*. Puede usar el valor **IMAGE ID** o la cadena con formato **REPOSITORY:TAG**.

```Docker
docker rmi counter-image:latest
docker rmi mcr.microsoft.com/dotnet/core/aspnet:3.1
```

Use el comando `docker images` para ver una lista de las imágenes instaladas.

> [!TIP]
> Los archivos de imagen pueden ser grandes. Por lo general, quitaría los contenedores temporales que creó al probar y desarrollar la aplicación. Habitualmente, estas imágenes base se conservan con el runtime instalado si se planea crear otras imágenes basadas en ese runtime.

## <a name="next-steps"></a>Pasos siguientes

- [Obtenga información sobre cómo incluir una aplicación ASP.NET Core en contenedores.](/aspnet/core/host-and-deploy/docker/building-net-docker-images)
- [Consulte el tutorial de ASP.NET Core para los microservicios](https://dotnet.microsoft.com/learn/web/aspnet-microservice-tutorial/intro).
- [Revise los servicios de Azure que admiten contenedores](https://azure.microsoft.com/overview/containers/).
- [Lea sobre los comandos de Dockerfile](https://docs.docker.com/engine/reference/builder/).
- [Explorar las herramientas de contenedor para Visual Studio](/visualstudio/containers/overview)
