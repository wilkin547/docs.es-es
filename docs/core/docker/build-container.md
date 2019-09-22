---
title: Tutorial sobre cómo incluir una aplicación en un contenedor con Docker
description: En este tutorial obtendrá información sobre cómo incluir una aplicación de .NET Core en un contenedor con Docker.
ms.date: 06/26/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 5e05fd2a38770ce348fbbfcfaa88267217b806bf
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2019
ms.locfileid: "71116563"
---
# <a name="tutorial-containerize-a-net-core-app"></a><span data-ttu-id="f0751-103">Tutorial: Incluir una aplicación de .NET Core en un contenedor</span><span class="sxs-lookup"><span data-stu-id="f0751-103">Tutorial: Containerize a .NET Core app</span></span>

<span data-ttu-id="f0751-104">En este tutorial se ofrece información sobre cómo compilar una imagen de Docker que contiene una aplicación de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f0751-104">This tutorial teaches you how to build a Docker image that contains your .NET Core application.</span></span> <span data-ttu-id="f0751-105">La imagen puede usarse para crear contenedores para un entorno de desarrollo local, una nube privada o una nube pública.</span><span class="sxs-lookup"><span data-stu-id="f0751-105">The image can be used to create containers for your local development environment, private cloud, or public cloud.</span></span>

<span data-ttu-id="f0751-106">Aprenderá a hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f0751-106">You'll learn to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="f0751-107">Crear y publicar una aplicación .NET Core sencilla</span><span class="sxs-lookup"><span data-stu-id="f0751-107">Create and publish a simple .NET Core app</span></span>
> * <span data-ttu-id="f0751-108">Crear y configurar un archivo Dockerfile para .NET Core</span><span class="sxs-lookup"><span data-stu-id="f0751-108">Create and configure a Dockerfile for .NET Core</span></span>
> * <span data-ttu-id="f0751-109">Creación de una imagen de Docker</span><span class="sxs-lookup"><span data-stu-id="f0751-109">Build a Docker image</span></span>
> * <span data-ttu-id="f0751-110">Crear y ejecutar un contenedor de Docker</span><span class="sxs-lookup"><span data-stu-id="f0751-110">Create and run a Docker container</span></span>

<span data-ttu-id="f0751-111">Aprenderá sobre las tareas de compilación e implementación de un contenedor de Docker para una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f0751-111">You'll understand the Docker container build and deploy tasks for a .NET Core application.</span></span> <span data-ttu-id="f0751-112">La *plataforma Docker* usa el *motor de Docker* para compilar y empaquetar rápidamente aplicaciones como *imágenes de Docker*.</span><span class="sxs-lookup"><span data-stu-id="f0751-112">The *Docker platform* uses the *Docker engine* to quickly build and package apps as *Docker images*.</span></span> <span data-ttu-id="f0751-113">Estas imágenes se escriben en el formato *Dockerfile* para implementarse y ejecutarse en un contenedor superpuesto.</span><span class="sxs-lookup"><span data-stu-id="f0751-113">These images are written in the *Dockerfile* format to be deployed and run in a layered container.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f0751-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f0751-114">Prerequisites</span></span>

<span data-ttu-id="f0751-115">Instale estos requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="f0751-115">Install the following prerequisites:</span></span>

* <span data-ttu-id="f0751-116">[SDK de .NET Core 2.2](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="f0751-116">[.NET Core 2.2 SDK](https://dotnet.microsoft.com/download)</span></span>\
<span data-ttu-id="f0751-117">Si tiene instalado .NET Core, use el comando `dotnet --info` para determinar el SDK que está usando.</span><span class="sxs-lookup"><span data-stu-id="f0751-117">If you have .NET Core installed, use the `dotnet --info` command to determine which SDK you're using.</span></span>

* [<span data-ttu-id="f0751-118">Docker Community Edition</span><span class="sxs-lookup"><span data-stu-id="f0751-118">Docker Community Edition</span></span>](https://www.docker.com/products/docker-desktop)

* <span data-ttu-id="f0751-119">Una carpeta de trabajo temporal para *Dockerfile* y una aplicación .NET Core de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f0751-119">A temporary working folder for the *Dockerfile* and .NET Core example app.</span></span> <span data-ttu-id="f0751-120">En este tutorial, el nombre `docker-working` se usa como la carpeta de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f0751-120">In this tutorial, the name `docker-working` is used as the working folder.</span></span>

### <a name="use-sdk-version-22"></a><span data-ttu-id="f0751-121">Uso de la versión 2.2 del SDK</span><span class="sxs-lookup"><span data-stu-id="f0751-121">Use SDK version 2.2</span></span>

<span data-ttu-id="f0751-122">Si usa un SDK más reciente, como 3.0, asegúrese de que la aplicación tenga que usar el SDK 2.2.</span><span class="sxs-lookup"><span data-stu-id="f0751-122">If you're using an SDK that is newer, like 3.0, make sure that your app is forced to use the 2.2 SDK.</span></span> <span data-ttu-id="f0751-123">Cree un archivo denominado `global.json` en la carpeta de trabajo y pegue el código JSON siguiente:</span><span class="sxs-lookup"><span data-stu-id="f0751-123">Create a file named `global.json` in your working folder and paste in the following json code:</span></span>

```json
{
  "sdk": {
    "version": "2.2.100"
  }
}
```

<span data-ttu-id="f0751-124">Guarde este archivo.</span><span class="sxs-lookup"><span data-stu-id="f0751-124">Save this file.</span></span> <span data-ttu-id="f0751-125">La presencia del archivo obligará a .NET Core a usar la versión 2.2 para cualquier comando `dotnet` llamado desde esta carpeta y por debajo.</span><span class="sxs-lookup"><span data-stu-id="f0751-125">The presence of file will force .NET Core to use version 2.2 for any `dotnet` command called from this folder and below.</span></span>

## <a name="create-net-core-app"></a><span data-ttu-id="f0751-126">Creación de una aplicación .NET Core</span><span class="sxs-lookup"><span data-stu-id="f0751-126">Create .NET Core app</span></span>

<span data-ttu-id="f0751-127">Necesita una aplicación .NET Core que el contenedor de Docker ejecutará.</span><span class="sxs-lookup"><span data-stu-id="f0751-127">You need a .NET Core app that the Docker container will run.</span></span> <span data-ttu-id="f0751-128">Abra el terminal, cree una carpeta de trabajo si todavía no lo ha hecho y entre en ella.</span><span class="sxs-lookup"><span data-stu-id="f0751-128">Open your terminal, create a working folder if you haven't already, and enter it.</span></span> <span data-ttu-id="f0751-129">En la carpeta de trabajo, ejecute el comando siguiente para crear un proyecto en un subdirectorio denominado app:</span><span class="sxs-lookup"><span data-stu-id="f0751-129">In the working folder, run the following command to create a new project in a subdirectory named app:</span></span>

```dotnetcli
dotnet new console -o app -n myapp
```

<span data-ttu-id="f0751-130">El árbol de carpetas tendrá un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="f0751-130">Your folder tree will look like the following:</span></span>

```
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

<span data-ttu-id="f0751-131">Con el comando `dotnet new` se crea una carpeta denominada *app* y se genera una aplicación "Hola mundo".</span><span class="sxs-lookup"><span data-stu-id="f0751-131">The `dotnet new` command creates a new folder named *app* and generates a "Hello World" app.</span></span> <span data-ttu-id="f0751-132">Entre en la carpeta *app* y ejecute el comando `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="f0751-132">Enter the *app* folder and run the command `dotnet run`.</span></span> <span data-ttu-id="f0751-133">Verá la salida siguiente:</span><span class="sxs-lookup"><span data-stu-id="f0751-133">You'll see the following output:</span></span>

```console
> dotnet run
Hello World!
```

<span data-ttu-id="f0751-134">La plantilla predeterminada crea una aplicación que imprime en el terminal y luego se cierra.</span><span class="sxs-lookup"><span data-stu-id="f0751-134">The default template creates an app that prints to the terminal and then exits.</span></span> <span data-ttu-id="f0751-135">En este tutorial, se usará una aplicación que se repite en bucle de manera indefinida.</span><span class="sxs-lookup"><span data-stu-id="f0751-135">For this tutorial, you'll use an app that loops indefinitely.</span></span> <span data-ttu-id="f0751-136">Abra el archivo **Program.cs** en un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="f0751-136">Open the **Program.cs** file in a text editor.</span></span> <span data-ttu-id="f0751-137">Actualmente debe ser similar al código siguiente:</span><span class="sxs-lookup"><span data-stu-id="f0751-137">It should currently look like the following code:</span></span>

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

<span data-ttu-id="f0751-138">Reemplace el archivo por el código siguiente que cuenta números cada segundo:</span><span class="sxs-lookup"><span data-stu-id="f0751-138">Replace the file with the following code that counts numbers every second:</span></span>

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

<span data-ttu-id="f0751-139">Guarde el archivo y vuelva a probar el programa con `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="f0751-139">Save the file and test the program again with `dotnet run`.</span></span> <span data-ttu-id="f0751-140">Recuerde que esta aplicación se ejecuta de manera indefinida.</span><span class="sxs-lookup"><span data-stu-id="f0751-140">Remember that this app runs indefinitely.</span></span> <span data-ttu-id="f0751-141">Use el comando Cancelar <kbd>CTRL + C</kbd> para detenerla.</span><span class="sxs-lookup"><span data-stu-id="f0751-141">Use the cancel command <kbd>CTRL + C</kbd> to stop it.</span></span> <span data-ttu-id="f0751-142">Verá la salida siguiente:</span><span class="sxs-lookup"><span data-stu-id="f0751-142">You'll see the following output:</span></span>

```console
> dotnet run
Counter: 1
Counter: 2
Counter: 3
Counter: 4
^C
```

<span data-ttu-id="f0751-143">Si pasa un número en la línea de comandos a la aplicación, solo se contará hasta esa cantidad y se cerrará.</span><span class="sxs-lookup"><span data-stu-id="f0751-143">If you pass a number on the command line to the app, it will only count up to that amount and then exit.</span></span> <span data-ttu-id="f0751-144">Inténtelo con `dotnet run -- 5` para contar hasta cinco.</span><span class="sxs-lookup"><span data-stu-id="f0751-144">Try it with `dotnet run -- 5` to count to five.</span></span>

> [!NOTE]
> <span data-ttu-id="f0751-145">Cualquier parámetro posterior a `--` no se pasa al comando `dotnet run` y, en su lugar, se pasa a su aplicación.</span><span class="sxs-lookup"><span data-stu-id="f0751-145">Any parameters after `--` are not passed to the `dotnet run` command and instead are passed to your application.</span></span>

## <a name="publish-net-core-app"></a><span data-ttu-id="f0751-146">Publicación de una aplicación .NET Core</span><span class="sxs-lookup"><span data-stu-id="f0751-146">Publish .NET Core app</span></span>

<span data-ttu-id="f0751-147">Antes de agregar la aplicación .NET Core a la imagen de Docker, publíquela.</span><span class="sxs-lookup"><span data-stu-id="f0751-147">Before you add your .NET Core app to the Docker image, publish it.</span></span> <span data-ttu-id="f0751-148">Quiere asegurarse de que el contenedor ejecuta la versión publicada de la aplicación al iniciarse.</span><span class="sxs-lookup"><span data-stu-id="f0751-148">You want to make sure that the container runs the published version of the app when it's started.</span></span>

<span data-ttu-id="f0751-149">Desde la carpeta de trabajo, entre en la carpeta **app** con el código fuente de ejemplo y ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="f0751-149">From the working folder, enter the **app** folder with the example source code and run the following command:</span></span>

```dotnetcli
dotnet publish -c Release
```

<span data-ttu-id="f0751-150">Con este comando se compila la aplicación en la carpeta **publish**.</span><span class="sxs-lookup"><span data-stu-id="f0751-150">This command compiles your app to the **publish** folder.</span></span> <span data-ttu-id="f0751-151">La ruta de acceso a la carpeta **publish** desde la carpeta de trabajo debería ser `.\app\bin\Release\netcoreapp2.2\publish\`.</span><span class="sxs-lookup"><span data-stu-id="f0751-151">The path to the **publish** folder from the working folder should be `.\app\bin\Release\netcoreapp2.2\publish\`</span></span>

<span data-ttu-id="f0751-152">Obtenga un listado de los directorios de la carpeta publish para comprobar que se creó el archivo **myapp.dll**.</span><span class="sxs-lookup"><span data-stu-id="f0751-152">Get a directory listing of the publish folder to verify that the **myapp.dll** was created.</span></span> <span data-ttu-id="f0751-153">Desde la carpeta **app**, ejecute uno de los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f0751-153">From the **app** folder, run one of the following commands:</span></span>

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

## <a name="create-the-dockerfile"></a><span data-ttu-id="f0751-154">Creación del archivo Dockerfile</span><span class="sxs-lookup"><span data-stu-id="f0751-154">Create the Dockerfile</span></span>

<span data-ttu-id="f0751-155">El archivo *Dockerfile* lo usa el comando `docker build` para crear una imagen de contenedor.</span><span class="sxs-lookup"><span data-stu-id="f0751-155">The *Dockerfile* file is used by the `docker build` command to create a container image.</span></span> <span data-ttu-id="f0751-156">Este archivo es un archivo de texto no cifrado denominado *Dockerfile* que no tiene ninguna extensión.</span><span class="sxs-lookup"><span data-stu-id="f0751-156">This file is a plaintext file named *Dockerfile* that does not have an extension.</span></span>

<span data-ttu-id="f0751-157">En el terminal, suba un directorio a la carpeta de trabajo creada al principio.</span><span class="sxs-lookup"><span data-stu-id="f0751-157">In your terminal, navigate up a directory to the working folder you created at the start.</span></span> <span data-ttu-id="f0751-158">Cree un archivo denominado *Dockerfile* en la carpeta de trabajo y ábralo en un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="f0751-158">Create a file named *Dockerfile* in your working folder and open it in a text editor.</span></span> <span data-ttu-id="f0751-159">Agregue el comando siguiente como la primera línea del archivo:</span><span class="sxs-lookup"><span data-stu-id="f0751-159">Add the following command as the first line of the file:</span></span>

```dockerfile
FROM mcr.microsoft.com/dotnet/core/runtime:2.2
```

<span data-ttu-id="f0751-160">El comando `FROM` indica a Docker que extraiga la imagen con la etiqueta **2.2** desde el repositorio **mcr.microsoft.com/dotnet/core/runtime**.</span><span class="sxs-lookup"><span data-stu-id="f0751-160">The `FROM` command tells Docker to pull down the image tagged **2.2** from the **mcr.microsoft.com/dotnet/core/runtime** repository.</span></span> <span data-ttu-id="f0751-161">Asegúrese de extraer el runtime de .NET Core que coincida con el runtime que el SDK tiene como destino.</span><span class="sxs-lookup"><span data-stu-id="f0751-161">Make sure that you pull the .NET Core runtime that matches the runtime targeted by your SDK.</span></span> <span data-ttu-id="f0751-162">Por ejemplo, en la aplicación que se creó en la sección anterior se usó el SDK de .NET Core 2.2 y se creó una aplicación destinada a .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="f0751-162">For example, the app created in the previous section used the .NET Core 2.2 SDK and created an app that targeted .NET Core 2.2.</span></span> <span data-ttu-id="f0751-163">Por lo tanto, la imagen base a la que se hace referencia en *Dockerfile* tiene la etiqueta **2.2**.</span><span class="sxs-lookup"><span data-stu-id="f0751-163">So the base image referred to in the *Dockerfile* is tagged with **2.2**.</span></span>

<span data-ttu-id="f0751-164">Guarde el archivo *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="f0751-164">Save the *Dockerfile* file.</span></span> <span data-ttu-id="f0751-165">La estructura de directorios de la carpeta de trabajo debería tener el siguiente aspecto.</span><span class="sxs-lookup"><span data-stu-id="f0751-165">The directory structure of the working folder should look like the following.</span></span> <span data-ttu-id="f0751-166">Algunos de los archivos de carpetas y archivos inferiores se han cortado para ahorrar espacio en este artículo:</span><span class="sxs-lookup"><span data-stu-id="f0751-166">Some of the deeper-level files and folders have been cut to save space in the article:</span></span>

```
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

<span data-ttu-id="f0751-167">Desde un terminal, ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="f0751-167">From your terminal, run the following command:</span></span>

```console
docker build -t myimage -f Dockerfile .
```

<span data-ttu-id="f0751-168">Docker procesará cada línea en el archivo *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="f0751-168">Docker will process each line in the *Dockerfile*.</span></span> <span data-ttu-id="f0751-169">`.` del comando `docker build` indica a Docker que use la carpeta actual para encontrar un archivo *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="f0751-169">The `.` in the `docker build` command tells Docker to use the current folder to find a *Dockerfile*.</span></span> <span data-ttu-id="f0751-170">Este comando crea la imagen y un repositorio local denominado **myimage** que apunta a esa imagen.</span><span class="sxs-lookup"><span data-stu-id="f0751-170">This command builds the image and creates a local repository named **myimage** that points to that image.</span></span> <span data-ttu-id="f0751-171">Una vez que finalice este comando, ejecute `docker images` para ver una lista de las imágenes instaladas:</span><span class="sxs-lookup"><span data-stu-id="f0751-171">After this command finishes, run `docker images` to see a list of images installed:</span></span>

```console
> docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
mcr.microsoft.com/dotnet/core/runtime   2.2                 d51bb4452469        2 days ago          314MB
myimage                                 latest              d51bb4452469        2 days ago          314MB
```

<span data-ttu-id="f0751-172">Observe que ambas imágenes comparten el mismo valor **IMAGE ID**.</span><span class="sxs-lookup"><span data-stu-id="f0751-172">Notice that the two images share the same **IMAGE ID** value.</span></span> <span data-ttu-id="f0751-173">El valor es el mismo entre ambas imágenes porque el único comando en *Dockerfile* era basar la imagen nueva en una imagen existente.</span><span class="sxs-lookup"><span data-stu-id="f0751-173">The value is the same between both images because the only command in the *Dockerfile* was to base the new image on an existing image.</span></span> <span data-ttu-id="f0751-174">Agreguemos dos comandos a *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="f0751-174">Let's add two commands to the *Dockerfile*.</span></span> <span data-ttu-id="f0751-175">Cada comando crear una capa de imagen nueva con el comando final que representa la imagen a la que apuntará el repositorio **myimage**.</span><span class="sxs-lookup"><span data-stu-id="f0751-175">Each command creates a new image layer with the final command representing the image the **myimage** repository will point to.</span></span>

```dockerfile
COPY app/bin/Release/netcoreapp2.2/publish/ app/

ENTRYPOINT ["dotnet", "app/myapp.dll"]
```

<span data-ttu-id="f0751-176">El comando `COPY` indica a Docker que copie la carpeta especificada en el equipo a una carpeta del contenedor.</span><span class="sxs-lookup"><span data-stu-id="f0751-176">The `COPY` command tells Docker to copy the specified folder on your computer to a folder in the container.</span></span> <span data-ttu-id="f0751-177">En este ejemplo, la carpeta **publish** se copia a una carpeta denominada **app** del contenedor.</span><span class="sxs-lookup"><span data-stu-id="f0751-177">In this example, the **publish** folder is copied to a folder named **app** in the container.</span></span>

<span data-ttu-id="f0751-178">El comando siguiente, `ENTRYPOINT`, indica a Docker que configure el contenedor para que se ejecute como ejecutable.</span><span class="sxs-lookup"><span data-stu-id="f0751-178">The next command, `ENTRYPOINT`, tells Docker to configure the container to run as an executable.</span></span> <span data-ttu-id="f0751-179">Cuando el contenedor se inicia, se ejecuta el comando `ENTRYPOINT`.</span><span class="sxs-lookup"><span data-stu-id="f0751-179">When the container starts, the `ENTRYPOINT` command runs.</span></span> <span data-ttu-id="f0751-180">Cuando este comando finaliza, el contenedor se detiene automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f0751-180">When this command ends, the container will automatically stop.</span></span>

<span data-ttu-id="f0751-181">Desde el terminal, ejecute `docker build -t myimage -f Dockerfile .` y, cuando el comando finalice, ejecute `docker images`.</span><span class="sxs-lookup"><span data-stu-id="f0751-181">From your terminal, run `docker build -t myimage -f Dockerfile .` and when that command finishes, run `docker images`.</span></span>

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

<span data-ttu-id="f0751-182">Cada comando de *Dockerfile* generó una capa y creó un valor **IMAGE ID**.</span><span class="sxs-lookup"><span data-stu-id="f0751-182">Each command in the *Dockerfile* generated a layer and created an **IMAGE ID**.</span></span> <span data-ttu-id="f0751-183">El valor **IMAGE ID** final (el suyo será distinto) es **ddcc6646461b** y, a continuación, usted creará un contenedor basado en esta imagen.</span><span class="sxs-lookup"><span data-stu-id="f0751-183">The final **IMAGE ID** (yours will be different) is **ddcc6646461b** and next you'll create a container based on this image.</span></span>

## <a name="create-a-container"></a><span data-ttu-id="f0751-184">Crear un contenedor</span><span class="sxs-lookup"><span data-stu-id="f0751-184">Create a container</span></span>

<span data-ttu-id="f0751-185">Ahora que tiene una imagen que contiene la aplicación, puede crear un contenedor.</span><span class="sxs-lookup"><span data-stu-id="f0751-185">Now that you have an image that contains your app, you can create a container.</span></span> <span data-ttu-id="f0751-186">Hay dos formas de crear un contenedor.</span><span class="sxs-lookup"><span data-stu-id="f0751-186">You can create a container in two ways.</span></span> <span data-ttu-id="f0751-187">En primer lugar, cree un contenedor que esté detenido.</span><span class="sxs-lookup"><span data-stu-id="f0751-187">First, create a new container that is stopped.</span></span>

```console
> docker create myimage
0e8f3c2ca32ce773712a5cca38750f41259a4e54e04bdf0946087e230ad7066c
```

<span data-ttu-id="f0751-188">El comando `docker create` anterior creará un contenedor basado en la imagen **myimage**.</span><span class="sxs-lookup"><span data-stu-id="f0751-188">The `docker create` command from above will create a container based on the **myimage** image.</span></span> <span data-ttu-id="f0751-189">La salida de ese comando muestra el valor **CONTAINER ID** (el suyo será distinto) del contenedor creado.</span><span class="sxs-lookup"><span data-stu-id="f0751-189">The output of that command shows you the **CONTAINER ID** (yours will be different) of the created container.</span></span> <span data-ttu-id="f0751-190">Para ver una lista de *todos* los contenedores, use el comando `docker ps -a`:</span><span class="sxs-lookup"><span data-stu-id="f0751-190">To see a list of *all* containers, use the `docker ps -a` command:</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS        PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   4 seconds ago       Created               boring_matsumoto
```

### <a name="manage-the-container"></a><span data-ttu-id="f0751-191">Administración del contenedor</span><span class="sxs-lookup"><span data-stu-id="f0751-191">Manage the container</span></span>

<span data-ttu-id="f0751-192">Cada contenedor tiene asignado un nombre aleatorio que puede usar para hacer referencia a la instancia de contenedor.</span><span class="sxs-lookup"><span data-stu-id="f0751-192">Each container is assigned a random name that you can use to refer to that container instance.</span></span> <span data-ttu-id="f0751-193">Por ejemplo, el contenedor que se creó automáticamente eligió el nombre **boring_matsumoto** (el suyo será distinto) y ese nombre se puede usar para iniciar el contenedor.</span><span class="sxs-lookup"><span data-stu-id="f0751-193">For example, the container that was created automatically chose the name **boring_matsumoto** (yours will be different) and that name can be used to start the container.</span></span> <span data-ttu-id="f0751-194">Puede reemplazar el nombre automático por uno específico si usa el parámetro `docker create --name`.</span><span class="sxs-lookup"><span data-stu-id="f0751-194">You override the automatic name with a specific one by using the `docker create --name` parameter.</span></span>

<span data-ttu-id="f0751-195">En el ejemplo siguiente se usa el comando `docker start` para iniciar el contenedor y luego se usa el comando `docker ps` para mostrar solo los contenedores que están en ejecución:</span><span class="sxs-lookup"><span data-stu-id="f0751-195">The following example uses the `docker start` command to start the container, and then uses the `docker ps` command to only show containers that are running:</span></span>

```console
> docker start boring_matsumoto
boring_matsumoto

> docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS         PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   7 minutes ago       Up 8 seconds           boring_matsumoto
```

<span data-ttu-id="f0751-196">De manera similar, el comando `docker stop` detendrá el contenedor.</span><span class="sxs-lookup"><span data-stu-id="f0751-196">Similarly, the `docker stop` command will stop the container.</span></span> <span data-ttu-id="f0751-197">En el ejemplo siguiente se usa el comando `docker stop` para detener el contenedor y luego se usa el comando `docker ps` para mostrar que no hay ningún contenedor en ejecución.</span><span class="sxs-lookup"><span data-stu-id="f0751-197">The following example uses the `docker stop` command to stop the container, and then uses the `docker ps` command to show that no containers are running.</span></span>

```console
> docker stop boring_matsumoto
boring_matsumoto

> docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS   NAMES
```

### <a name="connect-to-a-container"></a><span data-ttu-id="f0751-198">Conectarse a un contenedor</span><span class="sxs-lookup"><span data-stu-id="f0751-198">Connect to a container</span></span>

<span data-ttu-id="f0751-199">Una vez que se ejecuta un contenedor, puede conectarse a él para ver la salida.</span><span class="sxs-lookup"><span data-stu-id="f0751-199">After a container is running, you can connect to it to see the output.</span></span> <span data-ttu-id="f0751-200">Use los comandos `docker start` y `docker attach` para iniciar el contenedor y echar un vistazo al flujo de salida.</span><span class="sxs-lookup"><span data-stu-id="f0751-200">Use the `docker start` and `docker attach` commands to start the container and peek at the output stream.</span></span> <span data-ttu-id="f0751-201">En este ejemplo, el comando <kbd>CTRL + C</kbd> se usa para desasociarse del contenedor en ejecución.</span><span class="sxs-lookup"><span data-stu-id="f0751-201">In this example, the <kbd>CTRL + C</kbd> command is used to detach from the running container.</span></span> <span data-ttu-id="f0751-202">Esto podría realmente finalizar el proceso en el contenedor, lo que detendrá el contenedor.</span><span class="sxs-lookup"><span data-stu-id="f0751-202">This may actually end the process in the container, which will stop the container.</span></span> <span data-ttu-id="f0751-203">El parámetro `--sig-proxy=false` garantiza que <kbd>CTRL + C</kbd> no detendrá el proceso en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="f0751-203">The `--sig-proxy=false` parameter ensures that <kbd>CTRL + C</kbd> won't stop the process in the container.</span></span>

<span data-ttu-id="f0751-204">Después de desasociarse del contenedor, reasócielo para comprobar que sigue en ejecución.</span><span class="sxs-lookup"><span data-stu-id="f0751-204">After you detach from the container, reattach to verify that it's still running and counting.</span></span>

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

### <a name="delete-a-container"></a><span data-ttu-id="f0751-205">Eliminación de un contenedor</span><span class="sxs-lookup"><span data-stu-id="f0751-205">Delete a container</span></span>

<span data-ttu-id="f0751-206">Para el propósito de este artículo, no queremos contenedores que solo existan y no hagan nada.</span><span class="sxs-lookup"><span data-stu-id="f0751-206">For the purposes of this article you don't want containers just hanging around doing nothing.</span></span> <span data-ttu-id="f0751-207">Elimine el contenedor que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f0751-207">Delete the container you previously created.</span></span> <span data-ttu-id="f0751-208">Si el contenedor está en ejecución, deténgalo.</span><span class="sxs-lookup"><span data-stu-id="f0751-208">If the container is running, stop it.</span></span>

```console
> docker stop boring_matsumoto
```

<span data-ttu-id="f0751-209">En el ejemplo siguiente se muestran todos los contenedores.</span><span class="sxs-lookup"><span data-stu-id="f0751-209">The following example lists all containers.</span></span> <span data-ttu-id="f0751-210">Luego, usa el comando `docker rm` para eliminar el contenedor y después vuelve a comprobar si hay algún contenedor en ejecución.</span><span class="sxs-lookup"><span data-stu-id="f0751-210">It then uses the `docker rm` command to delete the container, and then checks a second time for any running containers.</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS     PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   19 minutes ago      Exited             boring_matsumoto

> docker rm boring_matsumoto
boring_matsumoto

> docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS    NAMES
```

### <a name="single-run"></a><span data-ttu-id="f0751-211">Ejecución única</span><span class="sxs-lookup"><span data-stu-id="f0751-211">Single run</span></span>

<span data-ttu-id="f0751-212">Docker proporciona el comando `docker run` para crear y ejecutar el contenedor como comando único.</span><span class="sxs-lookup"><span data-stu-id="f0751-212">Docker provides the `docker run` command to create and run the container as a single command.</span></span> <span data-ttu-id="f0751-213">Este comando elimina la necesidad de ejecutar `docker create` y luego `docker start`.</span><span class="sxs-lookup"><span data-stu-id="f0751-213">This command eliminates the need to run `docker create` and then `docker start`.</span></span> <span data-ttu-id="f0751-214">También puede establecer este comando en que elimine automáticamente el contenedor cuando este se detenga.</span><span class="sxs-lookup"><span data-stu-id="f0751-214">You can also set this command to automatically delete the container when the container stops.</span></span> <span data-ttu-id="f0751-215">Por ejemplo, use `docker run -it --rm` para hacer dos cosas: primero, use automáticamente el terminal actual para conectarse al contenedor y cuando el contenedor finalice, quítelo:</span><span class="sxs-lookup"><span data-stu-id="f0751-215">For example, use `docker run -it --rm` to do two things, first, automatically use the current terminal to connect to the container, and then when the container finishes, remove it:</span></span>

```console
> docker run -it --rm myimage
Counter: 1
Counter: 2
Counter: 3
Counter: 4
Counter: 5
^C
```

<span data-ttu-id="f0751-216">Con `docker run -it`, el comando <kbd>CTRL + C</kbd> detendrá el proceso que está en ejecución en el contenedor, lo que, a su vez, detendrá el contenedor.</span><span class="sxs-lookup"><span data-stu-id="f0751-216">With `docker run -it`, the <kbd>CTRL + C</kbd> command will stop process that is running in the container, which in turn, stops the container.</span></span> <span data-ttu-id="f0751-217">Como se proporcionó el parámetro `--rm`, el contenedor se elimina automáticamente cuando se detiene el proceso.</span><span class="sxs-lookup"><span data-stu-id="f0751-217">Since the `--rm` parameter was provided, the container is automatically deleted when the process is stopped.</span></span> <span data-ttu-id="f0751-218">Compruebe que no existe:</span><span class="sxs-lookup"><span data-stu-id="f0751-218">Verify that it does not exist:</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS    PORTS   NAMES
```

### <a name="change-the-entrypoint"></a><span data-ttu-id="f0751-219">Cambio de ENTRYPOINT</span><span class="sxs-lookup"><span data-stu-id="f0751-219">Change the ENTRYPOINT</span></span>

<span data-ttu-id="f0751-220">El comando `docker run` también permite modificar el comando `ENTRYPOINT` desde el archivo *Dockerfile* y ejecute algún otro elemento, pero solo para ese contenedor.</span><span class="sxs-lookup"><span data-stu-id="f0751-220">The `docker run` command also lets you modify the `ENTRYPOINT` command from the *Dockerfile* and run something else, but only for that container.</span></span> <span data-ttu-id="f0751-221">Por ejemplo, use el comando siguiente para ejecutar `bash` o `cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="f0751-221">For example, use the following command to run `bash` or `cmd.exe`.</span></span> <span data-ttu-id="f0751-222">Edite el comando según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="f0751-222">Edit the command as necessary.</span></span>

#### <a name="windows"></a><span data-ttu-id="f0751-223">Windows</span><span class="sxs-lookup"><span data-stu-id="f0751-223">Windows</span></span>
<span data-ttu-id="f0751-224">En este ejemplo, `ENTRYPOINT` cambia a `cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="f0751-224">In this example, `ENTRYPOINT` is changed to `cmd.exe`.</span></span> <span data-ttu-id="f0751-225">Se presiona <kbd>CTRL + C</kbd> para finalizar el proceso y detener el contenedor.</span><span class="sxs-lookup"><span data-stu-id="f0751-225"><kbd>CTRL + C</kbd> is pressed to end the process and stop the container.</span></span>

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

#### <a name="linux"></a><span data-ttu-id="f0751-226">Linux</span><span class="sxs-lookup"><span data-stu-id="f0751-226">Linux</span></span>

<span data-ttu-id="f0751-227">En este ejemplo, `ENTRYPOINT` cambia a `bash`.</span><span class="sxs-lookup"><span data-stu-id="f0751-227">In this example, `ENTRYPOINT` is changed to `bash`.</span></span> <span data-ttu-id="f0751-228">Se ejecuta el comando `quit`, lo que finaliza el proceso y detiene el contenedor.</span><span class="sxs-lookup"><span data-stu-id="f0751-228">The `quit` command is run which ends the process and stop the container.</span></span>

```bash
root@user:~# docker run -it --rm --entrypoint "bash" myimage
root@8515e897c893:/# ls app
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
root@8515e897c893:/# exit
exit
```

## <a name="essential-commands"></a><span data-ttu-id="f0751-229">Comandos esenciales</span><span class="sxs-lookup"><span data-stu-id="f0751-229">Essential commands</span></span>

<span data-ttu-id="f0751-230">Docker tiene muchos comandos distintos que abarcan las acciones que quiere hacer con el contenedor y las imágenes.</span><span class="sxs-lookup"><span data-stu-id="f0751-230">Docker has many different commands that cover what you want to do with your container and images.</span></span> <span data-ttu-id="f0751-231">Estos comandos de Docker son esenciales para la administración de los contenedores:</span><span class="sxs-lookup"><span data-stu-id="f0751-231">These Docker commands are essential to managing your containers:</span></span>

* [<span data-ttu-id="f0751-232">docker build</span><span class="sxs-lookup"><span data-stu-id="f0751-232">docker build</span></span>](https://docs.docker.com/engine/reference/commandline/build/)
* [<span data-ttu-id="f0751-233">docker run</span><span class="sxs-lookup"><span data-stu-id="f0751-233">docker run</span></span>](https://docs.docker.com/engine/reference/commandline/run/)
* [<span data-ttu-id="f0751-234">docker ps</span><span class="sxs-lookup"><span data-stu-id="f0751-234">docker ps</span></span>](https://docs.docker.com/engine/reference/commandline/ps/)
* [<span data-ttu-id="f0751-235">docker stop</span><span class="sxs-lookup"><span data-stu-id="f0751-235">docker stop</span></span>](https://docs.docker.com/engine/reference/commandline/stop/)
* [<span data-ttu-id="f0751-236">docker rm</span><span class="sxs-lookup"><span data-stu-id="f0751-236">docker rm</span></span>](https://docs.docker.com/engine/reference/commandline/rm/)
* [<span data-ttu-id="f0751-237">docker rmi</span><span class="sxs-lookup"><span data-stu-id="f0751-237">docker rmi</span></span>](https://docs.docker.com/engine/reference/commandline/rmi/)
* [<span data-ttu-id="f0751-238">docker image</span><span class="sxs-lookup"><span data-stu-id="f0751-238">docker image</span></span>](https://docs.docker.com/engine/reference/commandline/image/)

## <a name="clean-up-resources"></a><span data-ttu-id="f0751-239">Limpiar los recursos</span><span class="sxs-lookup"><span data-stu-id="f0751-239">Clean up resources</span></span>

<span data-ttu-id="f0751-240">Durante este tutorial, creó contenedores e imágenes.</span><span class="sxs-lookup"><span data-stu-id="f0751-240">During this tutorial you created containers and images.</span></span> <span data-ttu-id="f0751-241">Elimine estos recursos si quiere hacerlo.</span><span class="sxs-lookup"><span data-stu-id="f0751-241">If you want, delete these resources.</span></span> <span data-ttu-id="f0751-242">Use los comandos siguientes para</span><span class="sxs-lookup"><span data-stu-id="f0751-242">Use the following commands to</span></span>

01. <span data-ttu-id="f0751-243">Mostrar todos los contenedores</span><span class="sxs-lookup"><span data-stu-id="f0751-243">List all containers</span></span>

    ```console
    > docker ps -a
    ```

02. <span data-ttu-id="f0751-244">Detener los contenedores que están en ejecución</span><span class="sxs-lookup"><span data-stu-id="f0751-244">Stop containers that are running.</span></span> <span data-ttu-id="f0751-245">`CONTAINER_NAME` representa el nombre que se asignó automáticamente al contenedor.</span><span class="sxs-lookup"><span data-stu-id="f0751-245">The `CONTAINER_NAME` represents the name automatically assigned to the container.</span></span>

    ```console
    > docker stop CONTAINER_NAME
    ```

03. <span data-ttu-id="f0751-246">Eliminar el contenedor</span><span class="sxs-lookup"><span data-stu-id="f0751-246">Delete the container</span></span>

    ```console
    > docker rm CONTAINER_NAME
    ```

<span data-ttu-id="f0751-247">A continuación, elimine las imágenes que ya no quiere tener en la máquina.</span><span class="sxs-lookup"><span data-stu-id="f0751-247">Next, delete any images that you no longer want on your machine.</span></span> <span data-ttu-id="f0751-248">Elimine la imagen que creó el archivo *Dockerfile* y luego elimine la imagen de .NET Core en que se basó el archivo *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="f0751-248">Delete the image created by your *Dockerfile* and then delete the .NET Core image the *Dockerfile* was based on.</span></span> <span data-ttu-id="f0751-249">Puede usar el valor **IMAGE ID** o la cadena con formato **REPOSITORY:TAG**.</span><span class="sxs-lookup"><span data-stu-id="f0751-249">You can use the **IMAGE ID** or the **REPOSITORY:TAG** formatted string.</span></span>

```console
docker rmi myimage:latest
docker rmi mcr.microsoft.com/dotnet/core/runtime:2.2
```

<span data-ttu-id="f0751-250">Use el comando `docker images` para ver una lista de las imágenes instaladas.</span><span class="sxs-lookup"><span data-stu-id="f0751-250">Use the `docker images` command to see a list of images installed.</span></span>

> [!NOTE]
> <span data-ttu-id="f0751-251">Los archivos de imagen pueden ser grandes.</span><span class="sxs-lookup"><span data-stu-id="f0751-251">Image files can be large.</span></span> <span data-ttu-id="f0751-252">Por lo general, quitaría los contenedores temporales que creó al probar y desarrollar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f0751-252">Typically, you would remove temporary containers you created while testing and developing your app.</span></span> <span data-ttu-id="f0751-253">Habitualmente, estas imágenes base se conservan con el runtime instalado si se planea crear otras imágenes basadas en ese runtime.</span><span class="sxs-lookup"><span data-stu-id="f0751-253">You usually keep the base images with the runtime installed if you plan on building other images based on that runtime.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f0751-254">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="f0751-254">Next steps</span></span>

* <span data-ttu-id="f0751-255">[Consulte el tutorial de ASP.NET Core para los microservicios](https://dotnet.microsoft.com/learn/web/aspnet-microservice-tutorial/intro).</span><span class="sxs-lookup"><span data-stu-id="f0751-255">[Try the ASP.NET Core Microservice Tutorial.](https://dotnet.microsoft.com/learn/web/aspnet-microservice-tutorial/intro)</span></span>
* <span data-ttu-id="f0751-256">[Revise los servicios de Azure que admiten contenedores](https://azure.microsoft.com/overview/containers/).</span><span class="sxs-lookup"><span data-stu-id="f0751-256">[Review the Azure services that support containers.](https://azure.microsoft.com/overview/containers/)</span></span>
* <span data-ttu-id="f0751-257">[Lea sobre los comandos de Dockerfile](https://docs.docker.com/engine/reference/builder/).</span><span class="sxs-lookup"><span data-stu-id="f0751-257">[Read about Dockerfile commands.](https://docs.docker.com/engine/reference/builder/)</span></span>
* [<span data-ttu-id="f0751-258">Explorar las herramientas de contenedor para Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f0751-258">Explore the Container Tools for Visual Studio</span></span>](/visualstudio/containers/overview)
