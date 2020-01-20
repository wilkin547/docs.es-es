---
title: Tutorial sobre cómo incluir una aplicación en un contenedor con Docker
description: En este tutorial obtendrá información sobre cómo incluir una aplicación de .NET Core en un contenedor con Docker.
ms.date: 01/09/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 17d3dfbe58770b19a75be1dad3ae03406584992c
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900114"
---
# <a name="tutorial-containerize-a-net-core-app"></a><span data-ttu-id="6dcfb-103">Tutorial: Incluir una aplicación de .NET Core en un contenedor</span><span class="sxs-lookup"><span data-stu-id="6dcfb-103">Tutorial: Containerize a .NET Core app</span></span>

<span data-ttu-id="6dcfb-104">En este tutorial se ofrece información sobre cómo compilar una imagen de Docker que contiene una aplicación de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-104">This tutorial teaches you how to build a Docker image that contains your .NET Core application.</span></span> <span data-ttu-id="6dcfb-105">La imagen puede usarse para crear contenedores para un entorno de desarrollo local, una nube privada o una nube pública.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-105">The image can be used to create containers for your local development environment, private cloud, or public cloud.</span></span>

<span data-ttu-id="6dcfb-106">Aprenderá a hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6dcfb-106">You'll learn to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="6dcfb-107">Crear y publicar una aplicación .NET Core sencilla</span><span class="sxs-lookup"><span data-stu-id="6dcfb-107">Create and publish a simple .NET Core app</span></span>
> - <span data-ttu-id="6dcfb-108">Crear y configurar un archivo Dockerfile para .NET Core</span><span class="sxs-lookup"><span data-stu-id="6dcfb-108">Create and configure a Dockerfile for .NET Core</span></span>
> - <span data-ttu-id="6dcfb-109">Creación de una imagen de Docker</span><span class="sxs-lookup"><span data-stu-id="6dcfb-109">Build a Docker image</span></span>
> - <span data-ttu-id="6dcfb-110">Crear y ejecutar un contenedor de Docker</span><span class="sxs-lookup"><span data-stu-id="6dcfb-110">Create and run a Docker container</span></span>

<span data-ttu-id="6dcfb-111">Aprenderá sobre las tareas de compilación e implementación de un contenedor de Docker para una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-111">You'll understand the Docker container build and deploy tasks for a .NET Core application.</span></span> <span data-ttu-id="6dcfb-112">La *plataforma Docker* usa el *motor de Docker* para compilar y empaquetar rápidamente aplicaciones como *imágenes de Docker*.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-112">The *Docker platform* uses the *Docker engine* to quickly build and package apps as *Docker images*.</span></span> <span data-ttu-id="6dcfb-113">Estas imágenes se escriben en el formato *Dockerfile* para implementarse y ejecutarse en un contenedor superpuesto.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-113">These images are written in the *Dockerfile* format to be deployed and run in a layered container.</span></span>

> [!TIP]
> <span data-ttu-id="6dcfb-114">Si está trabajando con una aplicación de ASP.NET Core, consulte el tutorial [Obtenga información sobre cómo incluir una aplicación ASP.NET Core en contenedores](/aspnet/core/host-and-deploy/docker/building-net-docker-images).</span><span class="sxs-lookup"><span data-stu-id="6dcfb-114">If you're working with an existing ASP.NET Core application, see the [Learn how to containerize an ASP.NET Core application](/aspnet/core/host-and-deploy/docker/building-net-docker-images) tutorial.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6dcfb-115">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6dcfb-115">Prerequisites</span></span>

<span data-ttu-id="6dcfb-116">Instale estos requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="6dcfb-116">Install the following prerequisites:</span></span>

- <span data-ttu-id="6dcfb-117">[SDK de .NET Core 3.1](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="6dcfb-117">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download)</span></span>\
<span data-ttu-id="6dcfb-118">Si tiene instalado .NET Core, use el comando `dotnet --info` para determinar el SDK que está usando.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-118">If you have .NET Core installed, use the `dotnet --info` command to determine which SDK you're using.</span></span>

- [<span data-ttu-id="6dcfb-119">Docker Community Edition</span><span class="sxs-lookup"><span data-stu-id="6dcfb-119">Docker Community Edition</span></span>](https://www.docker.com/products/docker-desktop)

- <span data-ttu-id="6dcfb-120">Una carpeta de trabajo temporal para *Dockerfile* y una aplicación .NET Core de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-120">A temporary working folder for the *Dockerfile* and .NET Core example app.</span></span> <span data-ttu-id="6dcfb-121">En este tutorial, el nombre *docker-working* se usa como la carpeta de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-121">In this tutorial, the name *docker-working* is used as the working folder.</span></span>

## <a name="create-net-core-app"></a><span data-ttu-id="6dcfb-122">Creación de una aplicación .NET Core</span><span class="sxs-lookup"><span data-stu-id="6dcfb-122">Create .NET Core app</span></span>

<span data-ttu-id="6dcfb-123">Necesita una aplicación .NET Core que el contenedor de Docker ejecutará.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-123">You need a .NET Core app that the Docker container will run.</span></span> <span data-ttu-id="6dcfb-124">Abra el terminal, cree una carpeta de trabajo si todavía no lo ha hecho y entre en ella.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-124">Open your terminal, create a working folder if you haven't already, and enter it.</span></span> <span data-ttu-id="6dcfb-125">En la carpeta de trabajo, ejecute el comando siguiente para crear un proyecto en un subdirectorio llamado *app*:</span><span class="sxs-lookup"><span data-stu-id="6dcfb-125">In the working folder, run the following command to create a new project in a subdirectory named *app*:</span></span>

```dotnetcli
dotnet new console -o app -n myapp
```

<span data-ttu-id="6dcfb-126">El árbol de carpetas tendrá un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="6dcfb-126">Your folder tree will look like the following:</span></span>

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

<span data-ttu-id="6dcfb-127">Con el comando `dotnet new` se crea una carpeta denominada *app* y se genera una aplicación "Hola mundo".</span><span class="sxs-lookup"><span data-stu-id="6dcfb-127">The `dotnet new` command creates a new folder named *app* and generates a "Hello World" app.</span></span> <span data-ttu-id="6dcfb-128">Entre en la carpeta *app* y ejecute el comando `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-128">Enter the *app* folder and run the command `dotnet run`.</span></span> <span data-ttu-id="6dcfb-129">Verá la salida siguiente:</span><span class="sxs-lookup"><span data-stu-id="6dcfb-129">You'll see the following output:</span></span>

```console
> dotnet run
Hello World!
```

<span data-ttu-id="6dcfb-130">La plantilla predeterminada crea una aplicación que imprime en el terminal y luego se cierra.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-130">The default template creates an app that prints to the terminal and then exits.</span></span> <span data-ttu-id="6dcfb-131">En este tutorial, se usará una aplicación que se repite en bucle de manera indefinida.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-131">For this tutorial, you'll use an app that loops indefinitely.</span></span> <span data-ttu-id="6dcfb-132">Abra el archivo *Program.cs* en un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-132">Open the *Program.cs* file in a text editor.</span></span> <span data-ttu-id="6dcfb-133">Actualmente debe ser similar al código siguiente:</span><span class="sxs-lookup"><span data-stu-id="6dcfb-133">It should currently look like the following code:</span></span>

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

<span data-ttu-id="6dcfb-134">Reemplace el archivo por el código siguiente que cuenta números cada segundo:</span><span class="sxs-lookup"><span data-stu-id="6dcfb-134">Replace the file with the following code that counts numbers every second:</span></span>

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

<span data-ttu-id="6dcfb-135">Guarde el archivo y vuelva a probar el programa con `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-135">Save the file and test the program again with `dotnet run`.</span></span> <span data-ttu-id="6dcfb-136">Recuerde que esta aplicación se ejecuta de manera indefinida.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-136">Remember that this app runs indefinitely.</span></span> <span data-ttu-id="6dcfb-137">Use el comando de cancelación <kbd>CTRL</kbd>+<kbd>C</kbd> para detenerla.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-137">Use the cancel command <kbd>CTRL</kbd>+<kbd>C</kbd> to stop it.</span></span> <span data-ttu-id="6dcfb-138">Verá la salida siguiente:</span><span class="sxs-lookup"><span data-stu-id="6dcfb-138">You'll see the following output:</span></span>

```console
> dotnet run
Counter: 1
Counter: 2
Counter: 3
Counter: 4
^C
```

<span data-ttu-id="6dcfb-139">Si pasa un número en la línea de comandos a la aplicación, solo se contará hasta esa cantidad y se cerrará.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-139">If you pass a number on the command line to the app, it will only count up to that amount and then exit.</span></span> <span data-ttu-id="6dcfb-140">Inténtelo con `dotnet run -- 5` para contar hasta cinco.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-140">Try it with `dotnet run -- 5` to count to five.</span></span>

> [!NOTE]
> <span data-ttu-id="6dcfb-141">Cualquier parámetro posterior a `--` no se pasa al comando `dotnet run` y, en su lugar, se pasa a su aplicación.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-141">Any parameters after `--` are not passed to the `dotnet run` command and instead are passed to your application.</span></span>

## <a name="publish-net-core-app"></a><span data-ttu-id="6dcfb-142">Publicación de una aplicación .NET Core</span><span class="sxs-lookup"><span data-stu-id="6dcfb-142">Publish .NET Core app</span></span>

<span data-ttu-id="6dcfb-143">Antes de agregar la aplicación .NET Core a la imagen de Docker, publíquela.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-143">Before you add your .NET Core app to the Docker image, publish it.</span></span> <span data-ttu-id="6dcfb-144">Quiere asegurarse de que el contenedor ejecuta la versión publicada de la aplicación al iniciarse.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-144">You want to make sure that the container runs the published version of the app when it's started.</span></span>

<span data-ttu-id="6dcfb-145">Desde la carpeta de trabajo, entre en la carpeta *app* con el código fuente de ejemplo y ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="6dcfb-145">From the working folder, enter the *app* folder with the example source code and run the following command:</span></span>

```dotnetcli
dotnet publish -c Release
```

<span data-ttu-id="6dcfb-146">Con este comando se compila la aplicación en la carpeta *publish*.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-146">This command compiles your app to the *publish* folder.</span></span> <span data-ttu-id="6dcfb-147">La ruta de acceso a la carpeta *publish* desde la carpeta de trabajo debería ser `.\app\bin\Release\netcoreapp3.1\publish\`.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-147">The path to the *publish* folder from the working folder should be `.\app\bin\Release\netcoreapp3.1\publish\`</span></span>

<span data-ttu-id="6dcfb-148">En la carpeta *app*, obtenga un listado de los directorios de la carpeta publish para comprobar que se creó el archivo *myapp.dll*.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-148">From the *app* folder, get a directory listing of the publish folder to verify that the *myapp.dll* file was created.</span></span> 

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

<span data-ttu-id="6dcfb-149">Si usa Linux o macOS, use el comando `ls` para obtener una lista de directorios y comprobar que se ha creado el archivo *dmyapp.dll*.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-149">If you're using Linux or macOS, use the `ls` command to get a directory listing and verify that the *myapp.dll* file was created.</span></span>

```bash
me@DESKTOP:/docker-working/app$ ls bin/Release/netcoreapp3.1/publish
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
```

## <a name="create-the-dockerfile"></a><span data-ttu-id="6dcfb-150">Creación del archivo Dockerfile</span><span class="sxs-lookup"><span data-stu-id="6dcfb-150">Create the Dockerfile</span></span>

<span data-ttu-id="6dcfb-151">El archivo *Dockerfile* lo usa el comando `docker build` para crear una imagen de contenedor.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-151">The *Dockerfile* file is used by the `docker build` command to create a container image.</span></span> <span data-ttu-id="6dcfb-152">Este archivo es un archivo de texto denominado *Dockerfile* que no tiene ninguna extensión.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-152">This file is a text file named *Dockerfile* that doesn't have an extension.</span></span>

<span data-ttu-id="6dcfb-153">En el terminal, suba un directorio a la carpeta de trabajo creada al principio.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-153">In your terminal, navigate up a directory to the working folder you created at the start.</span></span> <span data-ttu-id="6dcfb-154">Cree un archivo denominado *Dockerfile* en la carpeta de trabajo y ábralo en un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-154">Create a file named *Dockerfile* in your working folder and open it in a text editor.</span></span> <span data-ttu-id="6dcfb-155">En función del tipo de aplicación que vaya a incluir en un contenedor, elija el runtime de ASP.NET Core o el de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-155">Depending on the type of application you're going to containerize, you'll choose either the ASP.NET Core runtime or the .NET Core runtime.</span></span> <span data-ttu-id="6dcfb-156">En duda, elija el runtime de ASP.NET Core, que incluye el de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-156">When in doubt, choose the ASP.NET Core runtime, which includes the .NET Core runtime.</span></span> <span data-ttu-id="6dcfb-157">En este tutorial se usará la imagen del runtime de ASP.NET Core, pero la aplicación creada en las secciones anteriores es una aplicación de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-157">This tutorial will use the ASP.NET Core runtime image, but the application created in the previous sections is an .NET Core application.</span></span>

- <span data-ttu-id="6dcfb-158">Runtime de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="6dcfb-158">ASP.NET Core runtime</span></span>

  ```dockerfile
  FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
  ```

- <span data-ttu-id="6dcfb-159">Tiempo de ejecución de .NET Core</span><span class="sxs-lookup"><span data-stu-id="6dcfb-159">.NET Core runtime</span></span>

  ```dockerfile
  FROM mcr.microsoft.com/dotnet/core/runtime:3.1
  ```

<span data-ttu-id="6dcfb-160">El comando `FROM` indica a Docker que extraiga la imagen etiquetada **3.1** del repositorio especificado.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-160">The `FROM` command tells Docker to pull down the image tagged **3.1** from the specified repository.</span></span> <span data-ttu-id="6dcfb-161">Asegúrese de extraer el runtime que coincida con el que el SDK tiene como destino.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-161">Make sure that you pull the runtime version that matches the runtime targeted by your SDK.</span></span> <span data-ttu-id="6dcfb-162">Por ejemplo, la aplicación creada en la sección anterior usaba el SDK de .NET Core 3.1, y la imagen base a la que se hace referencia en el documento *Dockerfile* se etiqueta con **3.1**.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-162">For example, the app created in the previous section used the .NET Core 3.1 SDK and the base image referred to in the *Dockerfile* is tagged with **3.1**.</span></span>

<span data-ttu-id="6dcfb-163">Guarde el archivo *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-163">Save the *Dockerfile* file.</span></span> <span data-ttu-id="6dcfb-164">La estructura de directorios de la carpeta de trabajo debería tener el siguiente aspecto.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-164">The directory structure of the working folder should look like the following.</span></span> <span data-ttu-id="6dcfb-165">Algunos de los archivos de carpetas y archivos inferiores se han cortado para ahorrar espacio en este artículo:</span><span class="sxs-lookup"><span data-stu-id="6dcfb-165">Some of the deeper-level files and folders have been cut to save space in the article:</span></span>

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

<span data-ttu-id="6dcfb-166">Desde un terminal, ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="6dcfb-166">From your terminal, run the following command:</span></span>

```console
docker build -t myimage -f Dockerfile .
```

<span data-ttu-id="6dcfb-167">Docker procesará cada línea en el archivo *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-167">Docker will process each line in the *Dockerfile*.</span></span> <span data-ttu-id="6dcfb-168">`.` del comando `docker build` indica a Docker que use la carpeta actual para encontrar un archivo *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-168">The `.` in the `docker build` command tells Docker to use the current folder to find a *Dockerfile*.</span></span> <span data-ttu-id="6dcfb-169">Este comando crea la imagen y un repositorio local denominado **myimage** que apunta a esa imagen.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-169">This command builds the image and creates a local repository named **myimage** that points to that image.</span></span> <span data-ttu-id="6dcfb-170">Una vez que finalice este comando, ejecute `docker images` para ver una lista de las imágenes instaladas:</span><span class="sxs-lookup"><span data-stu-id="6dcfb-170">After this command finishes, run `docker images` to see a list of images installed:</span></span>

```console
> docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
myimage                                 latest              38db0eb8f648        4 weeks ago         346MB
mcr.microsoft.com/dotnet/core/aspnet    3.1                 38db0eb8f648        4 weeks ago         346MB
```

<span data-ttu-id="6dcfb-171">Observe que ambas imágenes comparten el mismo valor **IMAGE ID**.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-171">Notice that the two images share the same **IMAGE ID** value.</span></span> <span data-ttu-id="6dcfb-172">El valor es el mismo entre ambas imágenes porque el único comando en *Dockerfile* era basar la imagen nueva en una imagen existente.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-172">The value is the same between both images because the only command in the *Dockerfile* was to base the new image on an existing image.</span></span> <span data-ttu-id="6dcfb-173">Agreguemos dos comandos a *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-173">Let's add two commands to the *Dockerfile*.</span></span> <span data-ttu-id="6dcfb-174">Cada comando crear una capa de imagen con el comando final que representa la imagen a la que apuntará el repositorio **myimage**.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-174">Each command creates a new image layer with the final command representing the image the **myimage** repository entry points to.</span></span>

```dockerfile
COPY app/bin/Release/netcoreapp3.1/publish/ app/

ENTRYPOINT ["dotnet", "app/myapp.dll"]
```

<span data-ttu-id="6dcfb-175">El comando `COPY` indica a Docker que copie la carpeta especificada en el equipo a una carpeta del contenedor.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-175">The `COPY` command tells Docker to copy the specified folder on your computer to a folder in the container.</span></span> <span data-ttu-id="6dcfb-176">En este ejemplo, la carpeta *publish* se copia a una carpeta denominada *app* del contenedor.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-176">In this example, the *publish* folder is copied to a folder named *app* in the container.</span></span>

<span data-ttu-id="6dcfb-177">El comando siguiente, `ENTRYPOINT`, indica a Docker que configure el contenedor para que se ejecute como ejecutable.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-177">The next command, `ENTRYPOINT`, tells Docker to configure the container to run as an executable.</span></span> <span data-ttu-id="6dcfb-178">Cuando el contenedor se inicia, se ejecuta el comando `ENTRYPOINT`.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-178">When the container starts, the `ENTRYPOINT` command runs.</span></span> <span data-ttu-id="6dcfb-179">Cuando este comando finaliza, el contenedor se detiene automáticamente.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-179">When this command ends, the container will automatically stop.</span></span>

<span data-ttu-id="6dcfb-180">Desde el terminal, ejecute `docker build -t myimage -f Dockerfile .` y, cuando el comando finalice, ejecute `docker images`.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-180">From your terminal, run `docker build -t myimage -f Dockerfile .` and when that command finishes, run `docker images`.</span></span>

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

<span data-ttu-id="6dcfb-181">Cada comando de *Dockerfile* generó una capa y creó un valor **IMAGE ID**.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-181">Each command in the *Dockerfile* generated a layer and created an **IMAGE ID**.</span></span> <span data-ttu-id="6dcfb-182">El valor **IMAGE ID** final (el suyo será distinto) es **ddcc6646461b** y, a continuación, usted creará un contenedor basado en esta imagen.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-182">The final **IMAGE ID** (yours will be different) is **ddcc6646461b** and next you'll create a container based on this image.</span></span>

## <a name="create-a-container"></a><span data-ttu-id="6dcfb-183">Crear un contenedor</span><span class="sxs-lookup"><span data-stu-id="6dcfb-183">Create a container</span></span>

<span data-ttu-id="6dcfb-184">Ahora que tiene una imagen que contiene la aplicación, puede crear un contenedor.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-184">Now that you have an image that contains your app, you can create a container.</span></span> <span data-ttu-id="6dcfb-185">Hay dos formas de crear un contenedor.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-185">You can create a container in two ways.</span></span> <span data-ttu-id="6dcfb-186">En primer lugar, cree un contenedor que esté detenido.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-186">First, create a new container that is stopped.</span></span>

```console
> docker create myimage
ceda87b219a4e55e9ad5d833ee1a7ea4da21b5ea7ce5a7d08f3051152e784944
```

<span data-ttu-id="6dcfb-187">El comando `docker create` anterior creará un contenedor basado en la imagen **myimage**.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-187">The `docker create` command from above will create a container based on the **myimage** image.</span></span> <span data-ttu-id="6dcfb-188">La salida de ese comando muestra el valor **CONTAINER ID** (el suyo será distinto) del contenedor creado.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-188">The output of that command shows you the **CONTAINER ID** (yours will be different) of the created container.</span></span> <span data-ttu-id="6dcfb-189">Para ver una lista de *todos* los contenedores, use el comando `docker ps -a`:</span><span class="sxs-lookup"><span data-stu-id="6dcfb-189">To see a list of *all* containers, use the `docker ps -a` command:</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS        PORTS   NAMES
ceda87b219a4        myimage             "dotnet app/myapp.dll"   4 seconds ago       Created               gallant_lehmann
```

### <a name="manage-the-container"></a><span data-ttu-id="6dcfb-190">Administración del contenedor</span><span class="sxs-lookup"><span data-stu-id="6dcfb-190">Manage the container</span></span>

<span data-ttu-id="6dcfb-191">Cada contenedor tiene asignado un nombre aleatorio que puede usar para hacer referencia a la instancia de contenedor.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-191">Each container is assigned a random name that you can use to refer to that container instance.</span></span> <span data-ttu-id="6dcfb-192">Por ejemplo, el contenedor que se creó automáticamente eligió el nombre **gallant_lehmann** (el suyo será distinto) y ese nombre se puede usar para iniciar el contenedor.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-192">For example, the container that was created automatically chose the name **gallant_lehmann** (yours will be different) and that name can be used to start the container.</span></span> <span data-ttu-id="6dcfb-193">Puede reemplazar el nombre automático por uno específico si usa el parámetro `docker create --name`.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-193">You override the automatic name with a specific one by using the `docker create --name` parameter.</span></span>

<span data-ttu-id="6dcfb-194">En el ejemplo siguiente se usa el comando `docker start` para iniciar el contenedor y luego se usa el comando `docker ps` para mostrar solo los contenedores que están en ejecución:</span><span class="sxs-lookup"><span data-stu-id="6dcfb-194">The following example uses the `docker start` command to start the container, and then uses the `docker ps` command to only show containers that are running:</span></span>

```console
> docker start gallant_lehmann
gallant_lehmann

> docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS         PORTS   NAMES
ceda87b219a4        myimage             "dotnet app/myapp.dll"   7 minutes ago       Up 8 seconds           gallant_lehmann
```

<span data-ttu-id="6dcfb-195">De manera similar, el comando `docker stop` detendrá el contenedor.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-195">Similarly, the `docker stop` command will stop the container.</span></span> <span data-ttu-id="6dcfb-196">En el ejemplo siguiente se usa el comando `docker stop` para detener el contenedor y luego se usa el comando `docker ps` para mostrar que no hay ningún contenedor en ejecución:</span><span class="sxs-lookup"><span data-stu-id="6dcfb-196">The following example uses the `docker stop` command to stop the container, and then uses the `docker ps` command to show that no containers are running:</span></span>

```console
> docker stop gallant_lehmann
gallant_lehmann

> docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS   NAMES
```

### <a name="connect-to-a-container"></a><span data-ttu-id="6dcfb-197">Conectarse a un contenedor</span><span class="sxs-lookup"><span data-stu-id="6dcfb-197">Connect to a container</span></span>

<span data-ttu-id="6dcfb-198">Una vez que se ejecuta un contenedor, puede conectarse a él para ver la salida.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-198">After a container is running, you can connect to it to see the output.</span></span> <span data-ttu-id="6dcfb-199">Use los comandos `docker start` y `docker attach` para iniciar el contenedor y echar un vistazo al flujo de salida.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-199">Use the `docker start` and `docker attach` commands to start the container and peek at the output stream.</span></span> <span data-ttu-id="6dcfb-200">En este ejemplo, el comando <kbd>Ctrl+C</kbd> se usa para desasociarse del contenedor en ejecución.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-200">In this example, the <kbd>CTRL + C</kbd> keystroke is used to detach from the running container.</span></span> <span data-ttu-id="6dcfb-201">Esta pulsación de teclas podría realmente finalizar el proceso en el contenedor, lo que detendrá el contenedor.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-201">This keystroke may actually end the process in the container, which will stop the container.</span></span> <span data-ttu-id="6dcfb-202">El parámetro `--sig-proxy=false` garantiza que <kbd>CTRL + C</kbd> no detendrá el proceso en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-202">The `--sig-proxy=false` parameter ensures that <kbd>CTRL + C</kbd> won't stop the process in the container.</span></span>

<span data-ttu-id="6dcfb-203">Después de desasociarse del contenedor, reasócielo para comprobar que sigue en ejecución.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-203">After you detach from the container, reattach to verify that it's still running and counting.</span></span>

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

### <a name="delete-a-container"></a><span data-ttu-id="6dcfb-204">Eliminación de un contenedor</span><span class="sxs-lookup"><span data-stu-id="6dcfb-204">Delete a container</span></span>

<span data-ttu-id="6dcfb-205">Para el propósito de este artículo, no queremos contenedores que solo existan y no hagan nada.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-205">For the purposes of this article you don't want containers just hanging around doing nothing.</span></span> <span data-ttu-id="6dcfb-206">Elimine el contenedor que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-206">Delete the container you previously created.</span></span> <span data-ttu-id="6dcfb-207">Si el contenedor está en ejecución, deténgalo.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-207">If the container is running, stop it.</span></span>

```console
> docker stop gallant_lehmann
```

<span data-ttu-id="6dcfb-208">En el ejemplo siguiente se muestran todos los contenedores.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-208">The following example lists all containers.</span></span> <span data-ttu-id="6dcfb-209">Luego, usa el comando `docker rm` para eliminar el contenedor y después vuelve a comprobar si hay algún contenedor en ejecución.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-209">It then uses the `docker rm` command to delete the container, and then checks a second time for any running containers.</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS     PORTS   NAMES
ceda87b219a4        myimage             "dotnet app/myapp.dll"   19 minutes ago      Exited             gallant_lehmann

> docker rm gallant_lehmann
gallant_lehmann

> docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS    NAMES
```

### <a name="single-run"></a><span data-ttu-id="6dcfb-210">Ejecución única</span><span class="sxs-lookup"><span data-stu-id="6dcfb-210">Single run</span></span>

<span data-ttu-id="6dcfb-211">Docker proporciona el comando `docker run` para crear y ejecutar el contenedor como comando único.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-211">Docker provides the `docker run` command to create and run the container as a single command.</span></span> <span data-ttu-id="6dcfb-212">Este comando elimina la necesidad de ejecutar `docker create` y luego `docker start`.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-212">This command eliminates the need to run `docker create` and then `docker start`.</span></span> <span data-ttu-id="6dcfb-213">También puede establecer este comando en que elimine automáticamente el contenedor cuando este se detenga.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-213">You can also set this command to automatically delete the container when the container stops.</span></span> <span data-ttu-id="6dcfb-214">Por ejemplo, use `docker run -it --rm` para hacer dos cosas: primero, use automáticamente el terminal actual para conectarse al contenedor y cuando el contenedor finalice, quítelo:</span><span class="sxs-lookup"><span data-stu-id="6dcfb-214">For example, use `docker run -it --rm` to do two things, first, automatically use the current terminal to connect to the container, and then when the container finishes, remove it:</span></span>

```console
> docker run -it --rm myimage
Counter: 1
Counter: 2
Counter: 3
Counter: 4
Counter: 5
^C
```

<span data-ttu-id="6dcfb-215">Con `docker run -it`, el comando <kbd>CTRL + C</kbd> detendrá el proceso que está en ejecución en el contenedor, lo que, a su vez, detendrá el contenedor.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-215">With `docker run -it`, the <kbd>CTRL + C</kbd> command will stop process that is running in the container, which in turn, stops the container.</span></span> <span data-ttu-id="6dcfb-216">Como se proporcionó el parámetro `--rm`, el contenedor se elimina automáticamente cuando se detiene el proceso.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-216">Since the `--rm` parameter was provided, the container is automatically deleted when the process is stopped.</span></span> <span data-ttu-id="6dcfb-217">Compruebe que no existe:</span><span class="sxs-lookup"><span data-stu-id="6dcfb-217">Verify that it doesn't exist:</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS    PORTS   NAMES
```

### <a name="change-the-entrypoint"></a><span data-ttu-id="6dcfb-218">Cambio de ENTRYPOINT</span><span class="sxs-lookup"><span data-stu-id="6dcfb-218">Change the ENTRYPOINT</span></span>

<span data-ttu-id="6dcfb-219">El comando `docker run` también permite modificar el comando `ENTRYPOINT` desde el archivo *Dockerfile* y ejecute algún otro elemento, pero solo para ese contenedor.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-219">The `docker run` command also lets you modify the `ENTRYPOINT` command from the *Dockerfile* and run something else, but only for that container.</span></span> <span data-ttu-id="6dcfb-220">Por ejemplo, use el comando siguiente para ejecutar `bash` o `cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-220">For example, use the following command to run `bash` or `cmd.exe`.</span></span> <span data-ttu-id="6dcfb-221">Edite el comando según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-221">Edit the command as necessary.</span></span>

#### <a name="windows"></a><span data-ttu-id="6dcfb-222">Windows</span><span class="sxs-lookup"><span data-stu-id="6dcfb-222">Windows</span></span>

<span data-ttu-id="6dcfb-223">En este ejemplo, `ENTRYPOINT` cambia a `cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-223">In this example, `ENTRYPOINT` is changed to `cmd.exe`.</span></span> <span data-ttu-id="6dcfb-224">Se presiona <kbd>CTRL</kbd>+<kbd>C</kbd> para finalizar el proceso y detener el contenedor.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-224"><kbd>CTRL</kbd>+<kbd>C</kbd> is pressed to end the process and stop the container.</span></span>

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

#### <a name="linux"></a><span data-ttu-id="6dcfb-225">Linux</span><span class="sxs-lookup"><span data-stu-id="6dcfb-225">Linux</span></span>

<span data-ttu-id="6dcfb-226">En este ejemplo, `ENTRYPOINT` cambia a `bash`.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-226">In this example, `ENTRYPOINT` is changed to `bash`.</span></span> <span data-ttu-id="6dcfb-227">Se ejecuta el comando `quit`, lo que finaliza el proceso y detiene el contenedor.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-227">The `quit` command is run which ends the process and stop the container.</span></span>

```bash
root@user:~# docker run -it --rm --entrypoint "bash" myimage
root@8515e897c893:/# ls app
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
root@8515e897c893:/# exit
exit
```

## <a name="essential-commands"></a><span data-ttu-id="6dcfb-228">Comandos esenciales</span><span class="sxs-lookup"><span data-stu-id="6dcfb-228">Essential commands</span></span>

<span data-ttu-id="6dcfb-229">Docker tiene muchos comandos distintos que abarcan las acciones que quiere hacer con el contenedor y las imágenes.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-229">Docker has many different commands that cover what you want to do with your container and images.</span></span> <span data-ttu-id="6dcfb-230">Estos comandos de Docker son esenciales para la administración de los contenedores:</span><span class="sxs-lookup"><span data-stu-id="6dcfb-230">These Docker commands are essential to managing your containers:</span></span>

- [<span data-ttu-id="6dcfb-231">docker build</span><span class="sxs-lookup"><span data-stu-id="6dcfb-231">docker build</span></span>](https://docs.docker.com/engine/reference/commandline/build/)
- [<span data-ttu-id="6dcfb-232">docker run</span><span class="sxs-lookup"><span data-stu-id="6dcfb-232">docker run</span></span>](https://docs.docker.com/engine/reference/commandline/run/)
- [<span data-ttu-id="6dcfb-233">docker ps</span><span class="sxs-lookup"><span data-stu-id="6dcfb-233">docker ps</span></span>](https://docs.docker.com/engine/reference/commandline/ps/)
- [<span data-ttu-id="6dcfb-234">docker stop</span><span class="sxs-lookup"><span data-stu-id="6dcfb-234">docker stop</span></span>](https://docs.docker.com/engine/reference/commandline/stop/)
- [<span data-ttu-id="6dcfb-235">docker rm</span><span class="sxs-lookup"><span data-stu-id="6dcfb-235">docker rm</span></span>](https://docs.docker.com/engine/reference/commandline/rm/)
- [<span data-ttu-id="6dcfb-236">docker rmi</span><span class="sxs-lookup"><span data-stu-id="6dcfb-236">docker rmi</span></span>](https://docs.docker.com/engine/reference/commandline/rmi/)
- [<span data-ttu-id="6dcfb-237">docker image</span><span class="sxs-lookup"><span data-stu-id="6dcfb-237">docker image</span></span>](https://docs.docker.com/engine/reference/commandline/image/)

## <a name="clean-up-resources"></a><span data-ttu-id="6dcfb-238">Limpiar los recursos</span><span class="sxs-lookup"><span data-stu-id="6dcfb-238">Clean up resources</span></span>

<span data-ttu-id="6dcfb-239">Durante este tutorial, creó contenedores e imágenes.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-239">During this tutorial, you created containers and images.</span></span> <span data-ttu-id="6dcfb-240">Elimine estos recursos si quiere hacerlo.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-240">If you want, delete these resources.</span></span> <span data-ttu-id="6dcfb-241">Use los comandos siguientes para</span><span class="sxs-lookup"><span data-stu-id="6dcfb-241">Use the following commands to</span></span>

01. <span data-ttu-id="6dcfb-242">Mostrar todos los contenedores</span><span class="sxs-lookup"><span data-stu-id="6dcfb-242">List all containers</span></span>

    ```console
    > docker ps -a
    ```

02. <span data-ttu-id="6dcfb-243">Detener los contenedores que están en ejecución</span><span class="sxs-lookup"><span data-stu-id="6dcfb-243">Stop containers that are running.</span></span> <span data-ttu-id="6dcfb-244">`CONTAINER_NAME` representa el nombre que se asignó automáticamente al contenedor.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-244">The `CONTAINER_NAME` represents the name automatically assigned to the container.</span></span>

    ```console
    > docker stop CONTAINER_NAME
    ```

03. <span data-ttu-id="6dcfb-245">Eliminar el contenedor</span><span class="sxs-lookup"><span data-stu-id="6dcfb-245">Delete the container</span></span>

    ```console
    > docker rm CONTAINER_NAME
    ```

<span data-ttu-id="6dcfb-246">A continuación, elimine las imágenes que ya no quiere tener en la máquina.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-246">Next, delete any images that you no longer want on your machine.</span></span> <span data-ttu-id="6dcfb-247">Elimine la imagen que creó el archivo *Dockerfile* y luego elimine la imagen de .NET Core en que se basó el archivo *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-247">Delete the image created by your *Dockerfile* and then delete the .NET Core image the *Dockerfile* was based on.</span></span> <span data-ttu-id="6dcfb-248">Puede usar el valor **IMAGE ID** o la cadena con formato **REPOSITORY:TAG**.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-248">You can use the **IMAGE ID** or the **REPOSITORY:TAG** formatted string.</span></span>

```console
docker rmi myimage:latest
docker rmi mcr.microsoft.com/dotnet/core/aspnet:3.1
```

<span data-ttu-id="6dcfb-249">Use el comando `docker images` para ver una lista de las imágenes instaladas.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-249">Use the `docker images` command to see a list of images installed.</span></span>

> [!NOTE]
> <span data-ttu-id="6dcfb-250">Los archivos de imagen pueden ser grandes.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-250">Image files can be large.</span></span> <span data-ttu-id="6dcfb-251">Por lo general, quitaría los contenedores temporales que creó al probar y desarrollar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-251">Typically, you would remove temporary containers you created while testing and developing your app.</span></span> <span data-ttu-id="6dcfb-252">Habitualmente, estas imágenes base se conservan con el runtime instalado si se planea crear otras imágenes basadas en ese runtime.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-252">You usually keep the base images with the runtime installed if you plan on building other images based on that runtime.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6dcfb-253">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="6dcfb-253">Next steps</span></span>

- [<span data-ttu-id="6dcfb-254">Obtenga información sobre cómo incluir una aplicación ASP.NET Core en contenedores.</span><span class="sxs-lookup"><span data-stu-id="6dcfb-254">Learn how to containerize an ASP.NET Core application.</span></span>](/aspnet/core/host-and-deploy/docker/building-net-docker-images)
- <span data-ttu-id="6dcfb-255">[Consulte el tutorial de ASP.NET Core para los microservicios](https://dotnet.microsoft.com/learn/web/aspnet-microservice-tutorial/intro).</span><span class="sxs-lookup"><span data-stu-id="6dcfb-255">[Try the ASP.NET Core Microservice Tutorial.](https://dotnet.microsoft.com/learn/web/aspnet-microservice-tutorial/intro)</span></span>
- <span data-ttu-id="6dcfb-256">[Revise los servicios de Azure que admiten contenedores](https://azure.microsoft.com/overview/containers/).</span><span class="sxs-lookup"><span data-stu-id="6dcfb-256">[Review the Azure services that support containers.](https://azure.microsoft.com/overview/containers/)</span></span>
- <span data-ttu-id="6dcfb-257">[Lea sobre los comandos de Dockerfile](https://docs.docker.com/engine/reference/builder/).</span><span class="sxs-lookup"><span data-stu-id="6dcfb-257">[Read about Dockerfile commands.](https://docs.docker.com/engine/reference/builder/)</span></span>
- [<span data-ttu-id="6dcfb-258">Explorar las herramientas de contenedor para Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6dcfb-258">Explore the Container Tools for Visual Studio</span></span>](/visualstudio/containers/overview)
