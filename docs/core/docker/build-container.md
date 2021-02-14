---
title: Tutorial sobre cómo incluir una aplicación en un contenedor con Docker
description: En este tutorial obtendrá información sobre cómo incluir una aplicación de .NET Core en un contenedor con Docker.
ms.date: 04/27/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: c92f5823f56f74941afdd28638d30e759b2c51c9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740761"
---
# <a name="tutorial-containerize-a-net-core-app"></a><span data-ttu-id="21e35-103">Tutorial: Incluir una aplicación de .NET Core en un contenedor</span><span class="sxs-lookup"><span data-stu-id="21e35-103">Tutorial: Containerize a .NET Core app</span></span>

<span data-ttu-id="21e35-104">En este tutorial obtendrá información sobre cómo incluir una aplicación de .NET Core en un contenedor con Docker.</span><span class="sxs-lookup"><span data-stu-id="21e35-104">In this tutorial, you'll learn how to containerize a .NET Core application with Docker.</span></span> <span data-ttu-id="21e35-105">Los contenedores tienen muchas características y ventajas, como ser una infraestructura inmutable, proporcionar una arquitectura portátil y permitir la escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="21e35-105">Containers have many features and benefits, such as being an immutable infrastructure, providing a portable architecture, and enabling scalability.</span></span> <span data-ttu-id="21e35-106">La imagen puede usarse para crear contenedores para un entorno de desarrollo local, una nube privada o una nube pública.</span><span class="sxs-lookup"><span data-stu-id="21e35-106">The image can be used to create containers for your local development environment, private cloud, or public cloud.</span></span>

<span data-ttu-id="21e35-107">En este tutorial ha:</span><span class="sxs-lookup"><span data-stu-id="21e35-107">In this tutorial, you:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="21e35-108">Crear y publicar una aplicación .NET Core sencilla</span><span class="sxs-lookup"><span data-stu-id="21e35-108">Create and publish a simple .NET Core app</span></span>
> - <span data-ttu-id="21e35-109">Crear y configurar un archivo Dockerfile para .NET Core</span><span class="sxs-lookup"><span data-stu-id="21e35-109">Create and configure a Dockerfile for .NET Core</span></span>
> - <span data-ttu-id="21e35-110">Creación de una imagen de Docker</span><span class="sxs-lookup"><span data-stu-id="21e35-110">Build a Docker image</span></span>
> - <span data-ttu-id="21e35-111">Crear y ejecutar un contenedor de Docker</span><span class="sxs-lookup"><span data-stu-id="21e35-111">Create and run a Docker container</span></span>

<span data-ttu-id="21e35-112">Aprenderá sobre las tareas de compilación e implementación de un contenedor de Docker para una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="21e35-112">You'll understand the Docker container build and deploy tasks for a .NET Core application.</span></span> <span data-ttu-id="21e35-113">La *plataforma Docker* usa el *motor de Docker* para compilar y empaquetar rápidamente aplicaciones como *imágenes de Docker*.</span><span class="sxs-lookup"><span data-stu-id="21e35-113">The *Docker platform* uses the *Docker engine* to quickly build and package apps as *Docker images*.</span></span> <span data-ttu-id="21e35-114">Estas imágenes se escriben en el formato *Dockerfile* para implementarse y ejecutarse en un contenedor superpuesto.</span><span class="sxs-lookup"><span data-stu-id="21e35-114">These images are written in the *Dockerfile* format to be deployed and run in a layered container.</span></span>

> [!NOTE]
> <span data-ttu-id="21e35-115">Este tutorial **no es** para aplicaciones ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="21e35-115">This tutorial **is not** for ASP.NET Core apps.</span></span> <span data-ttu-id="21e35-116">Si usa ASP.NET Core, lea el tutorial sobre [cómo incluir una aplicación de ASP.NET Core en un contenedor](/aspnet/core/host-and-deploy/docker/building-net-docker-images).</span><span class="sxs-lookup"><span data-stu-id="21e35-116">If you're using ASP.NET Core, see the [Learn how to containerize an ASP.NET Core application](/aspnet/core/host-and-deploy/docker/building-net-docker-images) tutorial.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="21e35-117">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="21e35-117">Prerequisites</span></span>

<span data-ttu-id="21e35-118">Instale estos requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="21e35-118">Install the following prerequisites:</span></span>

- <span data-ttu-id="21e35-119">[SDK de .NET Core 5.0](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="21e35-119">[.NET Core 5.0 SDK](https://dotnet.microsoft.com/download)</span></span>\
<span data-ttu-id="21e35-120">Si tiene instalado .NET Core, use el comando `dotnet --info` para determinar el SDK que está usando.</span><span class="sxs-lookup"><span data-stu-id="21e35-120">If you have .NET Core installed, use the `dotnet --info` command to determine which SDK you're using.</span></span>
- [<span data-ttu-id="21e35-121">Docker Community Edition</span><span class="sxs-lookup"><span data-stu-id="21e35-121">Docker Community Edition</span></span>](https://www.docker.com/products/docker-desktop)
- <span data-ttu-id="21e35-122">Una carpeta de trabajo temporal para *Dockerfile* y una aplicación .NET Core de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="21e35-122">A temporary working folder for the *Dockerfile* and .NET Core example app.</span></span> <span data-ttu-id="21e35-123">En este tutorial, el nombre *docker-working* se usa como la carpeta de trabajo.</span><span class="sxs-lookup"><span data-stu-id="21e35-123">In this tutorial, the name *docker-working* is used as the working folder.</span></span>

## <a name="create-net-core-app"></a><span data-ttu-id="21e35-124">Creación de una aplicación .NET Core</span><span class="sxs-lookup"><span data-stu-id="21e35-124">Create .NET Core app</span></span>

<span data-ttu-id="21e35-125">Necesita una aplicación .NET Core que el contenedor de Docker ejecutará.</span><span class="sxs-lookup"><span data-stu-id="21e35-125">You need a .NET Core app that the Docker container will run.</span></span> <span data-ttu-id="21e35-126">Abra el terminal, cree una carpeta de trabajo si todavía no lo ha hecho y entre en ella.</span><span class="sxs-lookup"><span data-stu-id="21e35-126">Open your terminal, create a working folder if you haven't already, and enter it.</span></span> <span data-ttu-id="21e35-127">En la carpeta de trabajo, ejecute el comando siguiente para crear un proyecto en un subdirectorio llamado *app*:</span><span class="sxs-lookup"><span data-stu-id="21e35-127">In the working folder, run the following command to create a new project in a subdirectory named *app*:</span></span>

```dotnetcli
dotnet new console -o App -n NetCore.Docker
```

<span data-ttu-id="21e35-128">El árbol de carpetas tendrá un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="21e35-128">Your folder tree will look like the following:</span></span>

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

<span data-ttu-id="21e35-129">Con el comando `dotnet new` se crea una carpeta denominada *App* y se genera una aplicación de consola "Hola mundo".</span><span class="sxs-lookup"><span data-stu-id="21e35-129">The `dotnet new` command creates a new folder named *App* and generates a "Hello World" console application.</span></span> <span data-ttu-id="21e35-130">Cambie los directorios y vaya a la carpeta *App*, desde la sesión de Terminal.</span><span class="sxs-lookup"><span data-stu-id="21e35-130">Change directories and navigate into the *App* folder, from your terminal session.</span></span> <span data-ttu-id="21e35-131">Use el comando `dotnet run` para iniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="21e35-131">Use the `dotnet run` command to start the app.</span></span> <span data-ttu-id="21e35-132">La aplicación se ejecutará e imprimirá `Hello World!` debajo del comando:</span><span class="sxs-lookup"><span data-stu-id="21e35-132">The application will run, and print `Hello World!` below the command:</span></span>

```dotnetcli
dotnet run
Hello World!
```

<span data-ttu-id="21e35-133">La plantilla predeterminada crea una aplicación que imprime en el terminal y termina de inmediato.</span><span class="sxs-lookup"><span data-stu-id="21e35-133">The default template creates an app that prints to the terminal and then immediately terminates.</span></span> <span data-ttu-id="21e35-134">En este tutorial, se usará una aplicación que se repite en bucle de manera indefinida.</span><span class="sxs-lookup"><span data-stu-id="21e35-134">For this tutorial, you'll use an app that loops indefinitely.</span></span> <span data-ttu-id="21e35-135">Abra el archivo *Program.cs* en un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="21e35-135">Open the *Program.cs* file in a text editor.</span></span>

> [!TIP]
> <span data-ttu-id="21e35-136">Si está utilizando Visual Studio Code, en la sesión de Terminal anterior, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="21e35-136">If you're using Visual Studio Code, from the previous terminal session type the following command:</span></span>
>
> ```console
> code .
> ```
>
> <span data-ttu-id="21e35-137">Se abrirá la carpeta *App* que contiene el proyecto en Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="21e35-137">This will open the *App* folder that contains the project in Visual Studio Code.</span></span>

<span data-ttu-id="21e35-138">El archivo *Program.cs* debería ser similar al código de C# siguiente:</span><span class="sxs-lookup"><span data-stu-id="21e35-138">The *Program.cs* should look like the following C# code:</span></span>

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

<span data-ttu-id="21e35-139">Reemplace el archivo por el código siguiente que cuenta números cada segundo:</span><span class="sxs-lookup"><span data-stu-id="21e35-139">Replace the file with the following code that counts numbers every second:</span></span>

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

<span data-ttu-id="21e35-140">Guarde el archivo y vuelva a probar el programa con `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="21e35-140">Save the file and test the program again with `dotnet run`.</span></span> <span data-ttu-id="21e35-141">Recuerde que esta aplicación se ejecuta de manera indefinida.</span><span class="sxs-lookup"><span data-stu-id="21e35-141">Remember that this app runs indefinitely.</span></span> <span data-ttu-id="21e35-142">Use el comando Cancelar <kbd>Ctrl+C</kbd> para detenerla.</span><span class="sxs-lookup"><span data-stu-id="21e35-142">Use the cancel command <kbd>Ctrl+C</kbd> to stop it.</span></span> <span data-ttu-id="21e35-143">A continuación se muestra un resultado de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="21e35-143">The following is an example output:</span></span>

```dotnetcli
dotnet run
Counter: 1
Counter: 2
Counter: 3
Counter: 4
^C
```

<span data-ttu-id="21e35-144">Si pasa un número en la línea de comandos a la aplicación, solo se contará hasta esa cantidad y se cerrará.</span><span class="sxs-lookup"><span data-stu-id="21e35-144">If you pass a number on the command line to the app, it will only count up to that amount and then exit.</span></span> <span data-ttu-id="21e35-145">Inténtelo con `dotnet run -- 5` para contar hasta cinco.</span><span class="sxs-lookup"><span data-stu-id="21e35-145">Try it with `dotnet run -- 5` to count to five.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="21e35-146">Cualquier parámetro posterior a `--` no se pasa al comando `dotnet run` y, en su lugar, se pasa a su aplicación.</span><span class="sxs-lookup"><span data-stu-id="21e35-146">Any parameters after `--` are not passed to the `dotnet run` command and instead are passed to your application.</span></span>

## <a name="publish-net-core-app"></a><span data-ttu-id="21e35-147">Publicación de una aplicación .NET Core</span><span class="sxs-lookup"><span data-stu-id="21e35-147">Publish .NET Core app</span></span>

<span data-ttu-id="21e35-148">Antes de agregar la aplicación .NET Core a la imagen de Docker, primero debe publicarse.</span><span class="sxs-lookup"><span data-stu-id="21e35-148">Before adding the .NET Core app to the Docker image, first it must be published.</span></span> <span data-ttu-id="21e35-149">Es mejor que el contenedor ejecute la versión publicada de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="21e35-149">It is best to have the container run the published version of the app.</span></span> <span data-ttu-id="21e35-150">Ejecute el comando siguiente para publicar la aplicación:</span><span class="sxs-lookup"><span data-stu-id="21e35-150">To publish the app, run the following command:</span></span>

```dotnetcli
dotnet publish -c Release
```

<span data-ttu-id="21e35-151">Con este comando se compila la aplicación en la carpeta *publish*.</span><span class="sxs-lookup"><span data-stu-id="21e35-151">This command compiles your app to the *publish* folder.</span></span> <span data-ttu-id="21e35-152">La ruta de acceso a la carpeta *publish* desde la carpeta de trabajo debería ser `.\App\bin\Release\net5.0\publish\`.</span><span class="sxs-lookup"><span data-stu-id="21e35-152">The path to the *publish* folder from the working folder should be `.\App\bin\Release\net5.0\publish\`</span></span>

#### <a name="windows"></a>[<span data-ttu-id="21e35-153">Windows</span><span class="sxs-lookup"><span data-stu-id="21e35-153">Windows</span></span>](#tab/windows)

<span data-ttu-id="21e35-154">En la carpeta *App*, obtenga un listado de los directorios de la carpeta publish para comprobar que se ha creado el archivo *NetCore.Docker.dll*.</span><span class="sxs-lookup"><span data-stu-id="21e35-154">From the *App* folder, get a directory listing of the publish folder to verify that the *NetCore.Docker.dll* file was created.</span></span>

```powershell
dir .\bin\Release\net5.0\publish\

    Directory: C:\Users\dapine\App\bin\Release\net5.0\publish

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        4/27/2020   8:27 AM            434 NetCore.Docker.deps.json
-a----        4/27/2020   8:27 AM           6144 NetCore.Docker.dll
-a----        4/27/2020   8:27 AM         171520 NetCore.Docker.exe
-a----        4/27/2020   8:27 AM            860 NetCore.Docker.pdb
-a----        4/27/2020   8:27 AM            154 NetCore.Docker.runtimeconfig.json
```

#### <a name="linux"></a>[<span data-ttu-id="21e35-155">Linux</span><span class="sxs-lookup"><span data-stu-id="21e35-155">Linux</span></span>](#tab/linux)

<span data-ttu-id="21e35-156">Use el comando `ls` para obtener una lista de directorios y comprobar que se ha creado el archivo *NetCore.Docker.dll*.</span><span class="sxs-lookup"><span data-stu-id="21e35-156">Use the `ls` command to get a directory listing and verify that the *NetCore.Docker.dll* file was created.</span></span>

```bash
me@DESKTOP:/docker-working/app$ ls bin/Release/net5.0/publish
NetCore.Docker.deps.json  NetCore.Docker.dll  NetCore.Docker.pdb  NetCore.Docker.runtimeconfig.json
```

---

## <a name="create-the-dockerfile"></a><span data-ttu-id="21e35-157">Creación del archivo Dockerfile</span><span class="sxs-lookup"><span data-stu-id="21e35-157">Create the Dockerfile</span></span>

<span data-ttu-id="21e35-158">El archivo *Dockerfile* lo usa el comando `docker build` para crear una imagen de contenedor.</span><span class="sxs-lookup"><span data-stu-id="21e35-158">The *Dockerfile* file is used by the `docker build` command to create a container image.</span></span> <span data-ttu-id="21e35-159">Este archivo es un archivo de texto denominado *Dockerfile* que no tiene ninguna extensión.</span><span class="sxs-lookup"><span data-stu-id="21e35-159">This file is a text file named *Dockerfile* that doesn't have an extension.</span></span>

<span data-ttu-id="21e35-160">Cree un archivo denominado *Dockerfile* en el directorio que contiene el archivo *.csproj* y ábralo en un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="21e35-160">Create a file named *Dockerfile* in directory containing the *.csproj* and open it in a text editor.</span></span> <span data-ttu-id="21e35-161">Este tutorial usa la imagen de runtime de ASP.NET Core (que contiene la imagen de runtime de .NET Core) y corresponde a la aplicación de consola de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="21e35-161">This tutorial will use the ASP.NET Core runtime image (which contains the .NET Core runtime image) and corresponds with the .NET Core console application.</span></span>

```dockerfile
FROM mcr.microsoft.com/dotnet/aspnet:5.0
```

> [!NOTE]
> <span data-ttu-id="21e35-162">Aquí se usa intencionadamente la imagen de runtime de ASP.NET Core, aunque se podría haber usado la imagen de `mcr.microsoft.com/dotnet/runtime:5.0`.</span><span class="sxs-lookup"><span data-stu-id="21e35-162">The ASP.NET Core runtime image is used intentionally here, although the `mcr.microsoft.com/dotnet/runtime:5.0` image could have been used.</span></span>

<span data-ttu-id="21e35-163">La palabra clave `FROM` requiere un nombre completo de imagen de contenedor de Docker.</span><span class="sxs-lookup"><span data-stu-id="21e35-163">The `FROM` keyword requires a fully qualified Docker container image name.</span></span> <span data-ttu-id="21e35-164">Microsoft Container Registry (MCR, mcr.microsoft.com) es un sindicato de Docker Hub, que hospeda contenedores accesibles públicamente.</span><span class="sxs-lookup"><span data-stu-id="21e35-164">The Microsoft Container Registry (MCR, mcr.microsoft.com) is a syndicate of Docker Hub - which hosts publicly accessible containers.</span></span> <span data-ttu-id="21e35-165">El segmento `dotnet/core` es el repositorio de contenedores, donde el segmento de `aspnet` es el nombre de la imagen de contenedor.</span><span class="sxs-lookup"><span data-stu-id="21e35-165">The `dotnet/core` segment is the container repository, where as the `aspnet` segment is the container image name.</span></span> <span data-ttu-id="21e35-166">La imagen está etiquetada con `5.0`, que se usa para el control de versiones.</span><span class="sxs-lookup"><span data-stu-id="21e35-166">The image is tagged with `5.0`, which is used for versioning.</span></span> <span data-ttu-id="21e35-167">Por lo tanto, `mcr.microsoft.com/dotnet/aspnet:5.0` es el entorno de ejecución de .NET Core 5.0.</span><span class="sxs-lookup"><span data-stu-id="21e35-167">Thus, `mcr.microsoft.com/dotnet/aspnet:5.0` is the .NET Core 5.0 runtime.</span></span> <span data-ttu-id="21e35-168">Asegúrese de extraer el runtime que coincida con el que el SDK tiene como destino.</span><span class="sxs-lookup"><span data-stu-id="21e35-168">Make sure that you pull the runtime version that matches the runtime targeted by your SDK.</span></span> <span data-ttu-id="21e35-169">Por ejemplo, la aplicación creada en la sección anterior usaba el SDK de .NET Core 5.0, y la imagen base a la que se hace referencia en el documento *Dockerfile* se etiqueta con **5.0**.</span><span class="sxs-lookup"><span data-stu-id="21e35-169">For example, the app created in the previous section used the .NET Core 5.0 SDK and the base image referred to in the *Dockerfile* is tagged with **5.0**.</span></span>

<span data-ttu-id="21e35-170">Guarde el archivo *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="21e35-170">Save the *Dockerfile* file.</span></span> <span data-ttu-id="21e35-171">La estructura de directorios de la carpeta de trabajo debería tener el siguiente aspecto.</span><span class="sxs-lookup"><span data-stu-id="21e35-171">The directory structure of the working folder should look like the following.</span></span> <span data-ttu-id="21e35-172">Algunos de los archivos y carpetas inferiores se han omitido para ahorrar espacio en este artículo:</span><span class="sxs-lookup"><span data-stu-id="21e35-172">Some of the deeper-level files and folders have been omitted to save space in the article:</span></span>

```
docker-working
    └──App
        ├──Dockerfile
        ├──NetCore.Docker.csproj
        ├──Program.cs
        ├──bin
        │   └──Release
        │       └──net5.0
        │           └──publish
        │               ├──NetCore.Docker.deps.json
        │               ├──NetCore.Docker.exe
        │               ├──NetCore.Docker.dll
        │               ├──NetCore.Docker.pdb
        │               └──NetCore.Docker.runtimeconfig.json
        └──obj
            └──...
```

<span data-ttu-id="21e35-173">Desde un terminal, ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="21e35-173">From your terminal, run the following command:</span></span>

```console
docker build -t counter-image -f Dockerfile .
```

<span data-ttu-id="21e35-174">Docker procesará cada línea en el archivo *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="21e35-174">Docker will process each line in the *Dockerfile*.</span></span> <span data-ttu-id="21e35-175">`.` del comando `docker build` indica a Docker que use la carpeta actual para encontrar un archivo *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="21e35-175">The `.` in the `docker build` command tells Docker to use the current folder to find a *Dockerfile*.</span></span> <span data-ttu-id="21e35-176">Este comando crea la imagen y un repositorio local denominado **counter-image** que apunta a esa imagen.</span><span class="sxs-lookup"><span data-stu-id="21e35-176">This command builds the image and creates a local repository named **counter-image** that points to that image.</span></span> <span data-ttu-id="21e35-177">Una vez que finalice este comando, ejecute `docker images` para ver una lista de las imágenes instaladas:</span><span class="sxs-lookup"><span data-stu-id="21e35-177">After this command finishes, run `docker images` to see a list of images installed:</span></span>

```console
docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
counter-image                           latest              e6780479db63        4 days ago          190MB
mcr.microsoft.com/dotnet/aspnet         5.0                 e6780479db63        4 days ago          190MB
```

<span data-ttu-id="21e35-178">Observe que ambas imágenes comparten el mismo valor **IMAGE ID**.</span><span class="sxs-lookup"><span data-stu-id="21e35-178">Notice that the two images share the same **IMAGE ID** value.</span></span> <span data-ttu-id="21e35-179">El valor es el mismo entre ambas imágenes porque el único comando en *Dockerfile* era basar la imagen nueva en una imagen existente.</span><span class="sxs-lookup"><span data-stu-id="21e35-179">The value is the same between both images because the only command in the *Dockerfile* was to base the new image on an existing image.</span></span> <span data-ttu-id="21e35-180">Agreguemos tres comandos a *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="21e35-180">Let's add three commands to the *Dockerfile*.</span></span> <span data-ttu-id="21e35-181">Cada comando crea una capa de imagen y el comando final que representa la imagen **counter-image** a la que apunta el repositorio.</span><span class="sxs-lookup"><span data-stu-id="21e35-181">Each command creates a new image layer with the final command representing the **counter-image** repository entry points to.</span></span>

```dockerfile
COPY bin/Release/net5.0/publish/ App/
WORKDIR /App
ENTRYPOINT ["dotnet", "NetCore.Docker.dll"]
```

<span data-ttu-id="21e35-182">El comando `COPY` indica a Docker que copie la carpeta especificada en el equipo a una carpeta del contenedor.</span><span class="sxs-lookup"><span data-stu-id="21e35-182">The `COPY` command tells Docker to copy the specified folder on your computer to a folder in the container.</span></span> <span data-ttu-id="21e35-183">En este ejemplo, la carpeta *publish* se copia en una carpeta denominada *App* del contenedor.</span><span class="sxs-lookup"><span data-stu-id="21e35-183">In this example, the *publish* folder is copied to a folder named *App* in the container.</span></span>

<span data-ttu-id="21e35-184">El comando `WORKDIR` cambia el **directorio actual** dentro del contenedor a *App*.</span><span class="sxs-lookup"><span data-stu-id="21e35-184">The `WORKDIR` command changes the **current directory** inside of the container to *App*.</span></span>

<span data-ttu-id="21e35-185">El comando siguiente, `ENTRYPOINT`, indica a Docker que configure el contenedor para que se ejecute como ejecutable.</span><span class="sxs-lookup"><span data-stu-id="21e35-185">The next command, `ENTRYPOINT`, tells Docker to configure the container to run as an executable.</span></span> <span data-ttu-id="21e35-186">Cuando el contenedor se inicia, se ejecuta el comando `ENTRYPOINT`.</span><span class="sxs-lookup"><span data-stu-id="21e35-186">When the container starts, the `ENTRYPOINT` command runs.</span></span> <span data-ttu-id="21e35-187">Cuando este comando finaliza, el contenedor se detiene automáticamente.</span><span class="sxs-lookup"><span data-stu-id="21e35-187">When this command ends, the container will automatically stop.</span></span>

<span data-ttu-id="21e35-188">Desde el terminal, ejecute `docker build -t counter-image -f Dockerfile .` y, cuando el comando finalice, ejecute `docker images`.</span><span class="sxs-lookup"><span data-stu-id="21e35-188">From your terminal, run `docker build -t counter-image -f Dockerfile .` and when that command finishes, run `docker images`.</span></span>

```console
docker build -t counter-image -f Dockerfile .
Sending build context to Docker daemon  1.117MB
Step 1/4 : FROM mcr.microsoft.com/dotnet/aspnet:5.0
 ---> e6780479db63
Step 2/4 : COPY bin/Release/net5.0/publish/ App/
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
mcr.microsoft.com/dotnet/aspnet         5.0                 e6780479db63        4 days ago          190MB
```

<span data-ttu-id="21e35-189">Cada comando de *Dockerfile* generó una capa y creó un valor **IMAGE ID**.</span><span class="sxs-lookup"><span data-stu-id="21e35-189">Each command in the *Dockerfile* generated a layer and created an **IMAGE ID**.</span></span> <span data-ttu-id="21e35-190">El valor **IMAGE ID** final (el suyo será distinto) es **cd11c3df9b19** y, después, usted creará un contenedor basado en esta imagen.</span><span class="sxs-lookup"><span data-stu-id="21e35-190">The final **IMAGE ID** (yours will be different) is **cd11c3df9b19** and next you'll create a container based on this image.</span></span>

## <a name="create-a-container"></a><span data-ttu-id="21e35-191">Crear un contenedor</span><span class="sxs-lookup"><span data-stu-id="21e35-191">Create a container</span></span>

<span data-ttu-id="21e35-192">Ahora que tiene una imagen que contiene la aplicación, puede crear un contenedor.</span><span class="sxs-lookup"><span data-stu-id="21e35-192">Now that you have an image that contains your app, you can create a container.</span></span> <span data-ttu-id="21e35-193">Hay dos formas de crear un contenedor.</span><span class="sxs-lookup"><span data-stu-id="21e35-193">You can create a container in two ways.</span></span> <span data-ttu-id="21e35-194">En primer lugar, cree un contenedor que esté detenido.</span><span class="sxs-lookup"><span data-stu-id="21e35-194">First, create a new container that is stopped.</span></span>

```console
docker create --name core-counter counter-image
0f281cb3af994fba5d962cc7d482828484ea14ead6bfe386a35e5088c0058851
```

<span data-ttu-id="21e35-195">El comando `docker create` anterior creará un contenedor basado en la imagen **counter-image**.</span><span class="sxs-lookup"><span data-stu-id="21e35-195">The `docker create` command from above will create a container based on the **counter-image** image.</span></span> <span data-ttu-id="21e35-196">La salida de ese comando muestra el valor **CONTAINER ID** (el suyo será distinto) del contenedor creado.</span><span class="sxs-lookup"><span data-stu-id="21e35-196">The output of that command shows you the **CONTAINER ID** (yours will be different) of the created container.</span></span> <span data-ttu-id="21e35-197">Para ver una lista de *todos* los contenedores, use el comando `docker ps -a`:</span><span class="sxs-lookup"><span data-stu-id="21e35-197">To see a list of *all* containers, use the `docker ps -a` command:</span></span>

```console
docker ps -a
CONTAINER ID    IMAGE            COMMAND                   CREATED           STATUS     PORTS    NAMES
0f281cb3af99    counter-image    "dotnet NetCore.Dock…"    40 seconds ago    Created             core-counter
```

### <a name="manage-the-container"></a><span data-ttu-id="21e35-198">Administración del contenedor</span><span class="sxs-lookup"><span data-stu-id="21e35-198">Manage the container</span></span>

<span data-ttu-id="21e35-199">El contenedor se creó con un nombre específico, `core-counter`, usado para administrar el contenedor.</span><span class="sxs-lookup"><span data-stu-id="21e35-199">The container was created with a specific name `core-counter`, this name is used to manage the container.</span></span> <span data-ttu-id="21e35-200">En el ejemplo siguiente se usa el comando `docker start` para iniciar el contenedor y luego se usa el comando `docker ps` para mostrar solo los contenedores que están en ejecución:</span><span class="sxs-lookup"><span data-stu-id="21e35-200">The following example uses the `docker start` command to start the container, and then uses the `docker ps` command to only show containers that are running:</span></span>

```console
docker start core-counter
core-counter

docker ps
CONTAINER ID    IMAGE            COMMAND                   CREATED          STATUS          PORTS    NAMES
2f6424a7ddce    counter-image    "dotnet NetCore.Dock…"    2 minutes ago    Up 11 seconds            core-counter
```

<span data-ttu-id="21e35-201">De manera similar, el comando `docker stop` detendrá el contenedor.</span><span class="sxs-lookup"><span data-stu-id="21e35-201">Similarly, the `docker stop` command will stop the container.</span></span> <span data-ttu-id="21e35-202">En el ejemplo siguiente se usa el comando `docker stop` para detener el contenedor y luego se usa el comando `docker ps` para mostrar que no hay ningún contenedor en ejecución:</span><span class="sxs-lookup"><span data-stu-id="21e35-202">The following example uses the `docker stop` command to stop the container, and then uses the `docker ps` command to show that no containers are running:</span></span>

```console
docker stop core-counter
core-counter

docker ps
CONTAINER ID    IMAGE    COMMAND    CREATED    STATUS    PORTS    NAMES
```

### <a name="connect-to-a-container"></a><span data-ttu-id="21e35-203">Conectarse a un contenedor</span><span class="sxs-lookup"><span data-stu-id="21e35-203">Connect to a container</span></span>

<span data-ttu-id="21e35-204">Una vez que se ejecuta un contenedor, puede conectarse a él para ver la salida.</span><span class="sxs-lookup"><span data-stu-id="21e35-204">After a container is running, you can connect to it to see the output.</span></span> <span data-ttu-id="21e35-205">Use los comandos `docker start` y `docker attach` para iniciar el contenedor y echar un vistazo al flujo de salida.</span><span class="sxs-lookup"><span data-stu-id="21e35-205">Use the `docker start` and `docker attach` commands to start the container and peek at the output stream.</span></span> <span data-ttu-id="21e35-206">En este ejemplo, la pulsación de teclas <kbd>Ctrl+C</kbd> se usa para desasociarse del contenedor en ejecución.</span><span class="sxs-lookup"><span data-stu-id="21e35-206">In this example, the <kbd>Ctrl+C</kbd> keystroke is used to detach from the running container.</span></span> <span data-ttu-id="21e35-207">A menos que se especifique lo contrario, esta pulsación de teclas finalizará el proceso en el contenedor, con lo que se detendrá el contenedor.</span><span class="sxs-lookup"><span data-stu-id="21e35-207">This keystroke will end the process in the container unless otherwise specified, which would stop the container.</span></span> <span data-ttu-id="21e35-208">El parámetro `--sig-proxy=false` garantiza que <kbd>Ctrl+C</kbd> no detendrá el proceso en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="21e35-208">The `--sig-proxy=false` parameter ensures that <kbd>Ctrl+C</kbd> will not stop the process in the container.</span></span>

<span data-ttu-id="21e35-209">Después de desasociarse del contenedor, reasócielo para comprobar que sigue en ejecución.</span><span class="sxs-lookup"><span data-stu-id="21e35-209">After you detach from the container, reattach to verify that it's still running and counting.</span></span>

```console
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

### <a name="delete-a-container"></a><span data-ttu-id="21e35-210">Eliminación de un contenedor</span><span class="sxs-lookup"><span data-stu-id="21e35-210">Delete a container</span></span>

<span data-ttu-id="21e35-211">Para el propósito de este artículo, no queremos contenedores que solo existan y no hagan nada.</span><span class="sxs-lookup"><span data-stu-id="21e35-211">For the purposes of this article you don't want containers just hanging around doing nothing.</span></span> <span data-ttu-id="21e35-212">Elimine el contenedor que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="21e35-212">Delete the container you previously created.</span></span> <span data-ttu-id="21e35-213">Si el contenedor está en ejecución, deténgalo.</span><span class="sxs-lookup"><span data-stu-id="21e35-213">If the container is running, stop it.</span></span>

```console
docker stop core-counter
```

<span data-ttu-id="21e35-214">En el ejemplo siguiente se muestran todos los contenedores.</span><span class="sxs-lookup"><span data-stu-id="21e35-214">The following example lists all containers.</span></span> <span data-ttu-id="21e35-215">Luego, usa el comando `docker rm` para eliminar el contenedor y después vuelve a comprobar si hay algún contenedor en ejecución.</span><span class="sxs-lookup"><span data-stu-id="21e35-215">It then uses the `docker rm` command to delete the container, and then checks a second time for any running containers.</span></span>

```console
docker ps -a
CONTAINER ID    IMAGE            COMMAND                   CREATED          STATUS                        PORTS    NAMES
2f6424a7ddce    counter-image    "dotnet NetCore.Dock…"    7 minutes ago    Exited (143) 20 seconds ago            core-counter

docker rm core-counter
core-counter

docker ps -a
CONTAINER ID    IMAGE    COMMAND    CREATED    STATUS    PORTS    NAMES
```

### <a name="single-run"></a><span data-ttu-id="21e35-216">Ejecución única</span><span class="sxs-lookup"><span data-stu-id="21e35-216">Single run</span></span>

<span data-ttu-id="21e35-217">Docker proporciona el comando `docker run` para crear y ejecutar el contenedor como comando único.</span><span class="sxs-lookup"><span data-stu-id="21e35-217">Docker provides the `docker run` command to create and run the container as a single command.</span></span> <span data-ttu-id="21e35-218">Este comando elimina la necesidad de ejecutar `docker create` y luego `docker start`.</span><span class="sxs-lookup"><span data-stu-id="21e35-218">This command eliminates the need to run `docker create` and then `docker start`.</span></span> <span data-ttu-id="21e35-219">También puede establecer este comando en que elimine automáticamente el contenedor cuando este se detenga.</span><span class="sxs-lookup"><span data-stu-id="21e35-219">You can also set this command to automatically delete the container when the container stops.</span></span> <span data-ttu-id="21e35-220">Por ejemplo, use `docker run -it --rm` para hacer dos cosas: primero, use automáticamente el terminal actual para conectarse al contenedor y cuando el contenedor finalice, quítelo:</span><span class="sxs-lookup"><span data-stu-id="21e35-220">For example, use `docker run -it --rm` to do two things, first, automatically use the current terminal to connect to the container, and then when the container finishes, remove it:</span></span>

```console
docker run -it --rm counter-image
Counter: 1
Counter: 2
Counter: 3
Counter: 4
Counter: 5
^C
```

<span data-ttu-id="21e35-221">El contenedor también pasa parámetros a la ejecución de la aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="21e35-221">The container also passes parameters into the execution of the .NET Core app.</span></span> <span data-ttu-id="21e35-222">Para indicar a la aplicación .NET Core que cuente solo hasta 3, pase 3.</span><span class="sxs-lookup"><span data-stu-id="21e35-222">To instruct the .NET Core app to count only to 3 pass in 3.</span></span>

```console
docker run -it --rm counter-image 3
Counter: 1
Counter: 2
Counter: 3
```

<span data-ttu-id="21e35-223">Con `docker run -it`, el comando <kbd>Ctrl+C</kbd> detendrá el proceso que está ejecutándose en el contenedor, lo que, a su vez, detendrá el contenedor.</span><span class="sxs-lookup"><span data-stu-id="21e35-223">With `docker run -it`, the <kbd>Ctrl+C</kbd> command will stop process that is running in the container, which in turn, stops the container.</span></span> <span data-ttu-id="21e35-224">Como se proporcionó el parámetro `--rm`, el contenedor se elimina automáticamente cuando se detiene el proceso.</span><span class="sxs-lookup"><span data-stu-id="21e35-224">Since the `--rm` parameter was provided, the container is automatically deleted when the process is stopped.</span></span> <span data-ttu-id="21e35-225">Compruebe que no existe:</span><span class="sxs-lookup"><span data-stu-id="21e35-225">Verify that it doesn't exist:</span></span>

```console
docker ps -a
CONTAINER ID    IMAGE    COMMAND    CREATED    STATUS    PORTS    NAMES
```

### <a name="change-the-entrypoint"></a><span data-ttu-id="21e35-226">Cambio de ENTRYPOINT</span><span class="sxs-lookup"><span data-stu-id="21e35-226">Change the ENTRYPOINT</span></span>

<span data-ttu-id="21e35-227">El comando `docker run` también permite modificar el comando `ENTRYPOINT` desde el archivo *Dockerfile* y ejecute algún otro elemento, pero solo para ese contenedor.</span><span class="sxs-lookup"><span data-stu-id="21e35-227">The `docker run` command also lets you modify the `ENTRYPOINT` command from the *Dockerfile* and run something else, but only for that container.</span></span> <span data-ttu-id="21e35-228">Por ejemplo, use el comando siguiente para ejecutar `bash` o `cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="21e35-228">For example, use the following command to run `bash` or `cmd.exe`.</span></span> <span data-ttu-id="21e35-229">Edite el comando según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="21e35-229">Edit the command as necessary.</span></span>

#### <a name="windows"></a>[<span data-ttu-id="21e35-230">Windows</span><span class="sxs-lookup"><span data-stu-id="21e35-230">Windows</span></span>](#tab/windows)

<span data-ttu-id="21e35-231">En este ejemplo, `ENTRYPOINT` cambia a `cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="21e35-231">In this example, `ENTRYPOINT` is changed to `cmd.exe`.</span></span> <span data-ttu-id="21e35-232">Se presiona <kbd>Ctrl+C</kbd> para finalizar el proceso y detener el contenedor.</span><span class="sxs-lookup"><span data-stu-id="21e35-232"><kbd>Ctrl+C</kbd> is pressed to end the process and stop the container.</span></span>

```console
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

#### <a name="linux"></a>[<span data-ttu-id="21e35-233">Linux</span><span class="sxs-lookup"><span data-stu-id="21e35-233">Linux</span></span>](#tab/linux)

<span data-ttu-id="21e35-234">En este ejemplo, `ENTRYPOINT` cambia a `bash`.</span><span class="sxs-lookup"><span data-stu-id="21e35-234">In this example, `ENTRYPOINT` is changed to `bash`.</span></span> <span data-ttu-id="21e35-235">Se ejecuta el comando `exit`, lo que finaliza el proceso y detiene el contenedor.</span><span class="sxs-lookup"><span data-stu-id="21e35-235">The `exit` command is run which ends the process and stop the container.</span></span>

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

## <a name="essential-commands"></a><span data-ttu-id="21e35-236">Comandos esenciales</span><span class="sxs-lookup"><span data-stu-id="21e35-236">Essential commands</span></span>

<span data-ttu-id="21e35-237">Docker tiene muchos comandos diferentes que crean, administran e interactúan con contenedores e imágenes.</span><span class="sxs-lookup"><span data-stu-id="21e35-237">Docker has many different commands that create, manage, and interact with containers and images.</span></span> <span data-ttu-id="21e35-238">Estos comandos de Docker son esenciales para la administración de los contenedores:</span><span class="sxs-lookup"><span data-stu-id="21e35-238">These Docker commands are essential to managing your containers:</span></span>

- [<span data-ttu-id="21e35-239">docker build</span><span class="sxs-lookup"><span data-stu-id="21e35-239">docker build</span></span>](https://docs.docker.com/engine/reference/commandline/build/)
- [<span data-ttu-id="21e35-240">docker run</span><span class="sxs-lookup"><span data-stu-id="21e35-240">docker run</span></span>](https://docs.docker.com/engine/reference/commandline/run/)
- [<span data-ttu-id="21e35-241">docker ps</span><span class="sxs-lookup"><span data-stu-id="21e35-241">docker ps</span></span>](https://docs.docker.com/engine/reference/commandline/ps/)
- [<span data-ttu-id="21e35-242">docker stop</span><span class="sxs-lookup"><span data-stu-id="21e35-242">docker stop</span></span>](https://docs.docker.com/engine/reference/commandline/stop/)
- [<span data-ttu-id="21e35-243">docker rm</span><span class="sxs-lookup"><span data-stu-id="21e35-243">docker rm</span></span>](https://docs.docker.com/engine/reference/commandline/rm/)
- [<span data-ttu-id="21e35-244">docker rmi</span><span class="sxs-lookup"><span data-stu-id="21e35-244">docker rmi</span></span>](https://docs.docker.com/engine/reference/commandline/rmi/)
- [<span data-ttu-id="21e35-245">docker image</span><span class="sxs-lookup"><span data-stu-id="21e35-245">docker image</span></span>](https://docs.docker.com/engine/reference/commandline/image/)

## <a name="clean-up-resources"></a><span data-ttu-id="21e35-246">Limpiar los recursos</span><span class="sxs-lookup"><span data-stu-id="21e35-246">Clean up resources</span></span>

<span data-ttu-id="21e35-247">Durante este tutorial, creó contenedores e imágenes.</span><span class="sxs-lookup"><span data-stu-id="21e35-247">During this tutorial, you created containers and images.</span></span> <span data-ttu-id="21e35-248">Elimine estos recursos si quiere hacerlo.</span><span class="sxs-lookup"><span data-stu-id="21e35-248">If you want, delete these resources.</span></span> <span data-ttu-id="21e35-249">Use los comandos siguientes para</span><span class="sxs-lookup"><span data-stu-id="21e35-249">Use the following commands to</span></span>

01. <span data-ttu-id="21e35-250">Mostrar todos los contenedores</span><span class="sxs-lookup"><span data-stu-id="21e35-250">List all containers</span></span>

    ```console
    docker ps -a
    ```

02. <span data-ttu-id="21e35-251">Detener los contenedores que están en ejecución por nombre</span><span class="sxs-lookup"><span data-stu-id="21e35-251">Stop containers that are running by their name.</span></span>

    ```console
    docker stop counter-image
    ```

03. <span data-ttu-id="21e35-252">Eliminar el contenedor</span><span class="sxs-lookup"><span data-stu-id="21e35-252">Delete the container</span></span>

    ```console
    docker rm counter-image
    ```

<span data-ttu-id="21e35-253">A continuación, elimine las imágenes que ya no quiere tener en la máquina.</span><span class="sxs-lookup"><span data-stu-id="21e35-253">Next, delete any images that you no longer want on your machine.</span></span> <span data-ttu-id="21e35-254">Elimine la imagen que creó el archivo *Dockerfile* y luego elimine la imagen de .NET Core en que se basó el archivo *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="21e35-254">Delete the image created by your *Dockerfile* and then delete the .NET Core image the *Dockerfile* was based on.</span></span> <span data-ttu-id="21e35-255">Puede usar el valor **IMAGE ID** o la cadena con formato **REPOSITORY:TAG**.</span><span class="sxs-lookup"><span data-stu-id="21e35-255">You can use the **IMAGE ID** or the **REPOSITORY:TAG** formatted string.</span></span>

```console
docker rmi counter-image:latest
docker rmi mcr.microsoft.com/dotnet/aspnet:5.0
```

<span data-ttu-id="21e35-256">Use el comando `docker images` para ver una lista de las imágenes instaladas.</span><span class="sxs-lookup"><span data-stu-id="21e35-256">Use the `docker images` command to see a list of images installed.</span></span>

> [!TIP]
> <span data-ttu-id="21e35-257">Los archivos de imagen pueden ser grandes.</span><span class="sxs-lookup"><span data-stu-id="21e35-257">Image files can be large.</span></span> <span data-ttu-id="21e35-258">Por lo general, quitaría los contenedores temporales que creó al probar y desarrollar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="21e35-258">Typically, you would remove temporary containers you created while testing and developing your app.</span></span> <span data-ttu-id="21e35-259">Habitualmente, estas imágenes base se conservan con el runtime instalado si se planea crear otras imágenes basadas en ese runtime.</span><span class="sxs-lookup"><span data-stu-id="21e35-259">You usually keep the base images with the runtime installed if you plan on building other images based on that runtime.</span></span>

## <a name="next-steps"></a><span data-ttu-id="21e35-260">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="21e35-260">Next steps</span></span>

- [<span data-ttu-id="21e35-261">Obtenga información sobre cómo incluir una aplicación ASP.NET Core en contenedores.</span><span class="sxs-lookup"><span data-stu-id="21e35-261">Learn how to containerize an ASP.NET Core application.</span></span>](/aspnet/core/host-and-deploy/docker/building-net-docker-images)
- <span data-ttu-id="21e35-262">[Consulte el tutorial de ASP.NET Core para los microservicios](https://dotnet.microsoft.com/learn/web/aspnet-microservice-tutorial/intro).</span><span class="sxs-lookup"><span data-stu-id="21e35-262">[Try the ASP.NET Core Microservice Tutorial.](https://dotnet.microsoft.com/learn/web/aspnet-microservice-tutorial/intro)</span></span>
- <span data-ttu-id="21e35-263">[Revise los servicios de Azure que admiten contenedores](https://azure.microsoft.com/overview/containers/).</span><span class="sxs-lookup"><span data-stu-id="21e35-263">[Review the Azure services that support containers.](https://azure.microsoft.com/overview/containers/)</span></span>
- <span data-ttu-id="21e35-264">[Lea sobre los comandos de Dockerfile](https://docs.docker.com/engine/reference/builder/).</span><span class="sxs-lookup"><span data-stu-id="21e35-264">[Read about Dockerfile commands.](https://docs.docker.com/engine/reference/builder/)</span></span>
- [<span data-ttu-id="21e35-265">Explorar las herramientas de contenedor para Visual Studio</span><span class="sxs-lookup"><span data-stu-id="21e35-265">Explore the Container Tools for Visual Studio</span></span>](/visualstudio/containers/overview)
