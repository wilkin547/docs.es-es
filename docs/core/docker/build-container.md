---
title: Tutorial sobre cómo incluir una aplicación en un contenedor con Docker
description: En este tutorial obtendrá información sobre cómo incluir una aplicación de .NET Core en un contenedor con Docker.
ms.date: 04/10/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: fcbac0e0d17d2481d42e715a7f2790586e31d085
ms.sourcegitcommit: 8080271c246b57f4fb68c28369634bff46843424
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2019
ms.locfileid: "59553841"
---
# <a name="tutorial-containerize-a-net-core-app"></a><span data-ttu-id="8ec74-103">Tutorial: Incluir una aplicación de .NET Core en un contenedor</span><span class="sxs-lookup"><span data-stu-id="8ec74-103">Tutorial: Containerize a .NET Core app</span></span>

<span data-ttu-id="8ec74-104">En este tutorial se ofrece información sobre cómo compilar una imagen de Docker que contiene una aplicación de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8ec74-104">This tutorial teaches you how to build a Docker image that contains your .NET Core application.</span></span> <span data-ttu-id="8ec74-105">La imagen puede usarse para crear contenedores para un entorno de desarrollo local, una nube privada o una nube pública.</span><span class="sxs-lookup"><span data-stu-id="8ec74-105">The image can be used to create containers for your local development environment, private cloud, or public cloud.</span></span>

<span data-ttu-id="8ec74-106">Aprenderá a hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8ec74-106">You'll learn to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="8ec74-107">Crear y publicar una aplicación .NET Core sencilla</span><span class="sxs-lookup"><span data-stu-id="8ec74-107">Create and publish a simple .NET Core app</span></span>
> * <span data-ttu-id="8ec74-108">Crear y configurar un archivo Dockerfile para .NET Core</span><span class="sxs-lookup"><span data-stu-id="8ec74-108">Create and configure a Dockerfile for .NET Core</span></span>
> * <span data-ttu-id="8ec74-109">Creación de una imagen de Docker</span><span class="sxs-lookup"><span data-stu-id="8ec74-109">Build a Docker image</span></span>
> * <span data-ttu-id="8ec74-110">Crear y ejecutar un contenedor de Docker</span><span class="sxs-lookup"><span data-stu-id="8ec74-110">Create and run a Docker container</span></span>

<span data-ttu-id="8ec74-111">Aprenderá sobre las tareas de compilación e implementación de un contenedor de Docker para una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8ec74-111">You'll understand the Docker container build and deploy tasks for a .NET Core application.</span></span> <span data-ttu-id="8ec74-112">La *plataforma Docker* usa el *motor de Docker* para compilar y empaquetar rápidamente aplicaciones como *imágenes de Docker*.</span><span class="sxs-lookup"><span data-stu-id="8ec74-112">The *Docker platform* uses the *Docker engine* to quickly build and package apps as *Docker images*.</span></span> <span data-ttu-id="8ec74-113">Estas imágenes se escriben en el formato *Dockerfile* para implementarse y ejecutarse en un contenedor superpuesto.</span><span class="sxs-lookup"><span data-stu-id="8ec74-113">These images are written in the *Dockerfile* format to be deployed and run in a layered container.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8ec74-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8ec74-114">Prerequisites</span></span>

<span data-ttu-id="8ec74-115">Instale estos requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="8ec74-115">Install the following prerequisites:</span></span>

- <span data-ttu-id="8ec74-116">[SDK de .NET Core 2.2](https://dotnet.microsoft.com/download)\\</span><span class="sxs-lookup"><span data-stu-id="8ec74-116">[.NET Core 2.2 SDK](https://dotnet.microsoft.com/download)\\</span></span>
<span data-ttu-id="8ec74-117">Si tiene instalado .NET Core, use el comando `dotnet --info` para determinar el SDK que está usando.</span><span class="sxs-lookup"><span data-stu-id="8ec74-117">If you have .NET Core installed, use the `dotnet --info` command to determine which SDK you're using.</span></span>

- [<span data-ttu-id="8ec74-118">Docker Community Edition</span><span class="sxs-lookup"><span data-stu-id="8ec74-118">Docker Community Edition</span></span>](https://www.docker.com/products/docker-desktop)

- <span data-ttu-id="8ec74-119">Un directorio de trabajo temporal para *Dockerfile* y una aplicación .NET Core de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8ec74-119">A temporary working directory for the *Dockerfile* and .NET Core example app.</span></span>

### <a name="use-sdk-version-22"></a><span data-ttu-id="8ec74-120">Uso de la versión 2.2 del SDK</span><span class="sxs-lookup"><span data-stu-id="8ec74-120">Use SDK version 2.2</span></span>

<span data-ttu-id="8ec74-121">Si usa un SDK más reciente, como 3.0, asegúrese de que la aplicación tenga que usar el SDK 2.2.</span><span class="sxs-lookup"><span data-stu-id="8ec74-121">If you're using an SDK that is newer, like 3.0, make sure that your app is forced to use the 2.2 SDK.</span></span> <span data-ttu-id="8ec74-122">Cree un archivo denominado `global.json` en el directorio de trabajo y pegue el código JSON siguiente:</span><span class="sxs-lookup"><span data-stu-id="8ec74-122">Create a file named `global.json` in your working directory and paste in the following json code:</span></span>

```json
{
  "sdk": {
    "version": "2.2.100"
  }
}
```

<span data-ttu-id="8ec74-123">Guarde este archivo.</span><span class="sxs-lookup"><span data-stu-id="8ec74-123">Save this file.</span></span> <span data-ttu-id="8ec74-124">La presencia del archivo obligará a .NET Core a usar la versión 2.2 para cualquier comando `dotnet` llamado desde este directorio y por debajo.</span><span class="sxs-lookup"><span data-stu-id="8ec74-124">The presence of file will force .NET Core to use version 2.2 for any `dotnet` command called from this directory and below.</span></span>

## <a name="create-net-core-app"></a><span data-ttu-id="8ec74-125">Creación de una aplicación .NET Core</span><span class="sxs-lookup"><span data-stu-id="8ec74-125">Create .NET Core app</span></span>

<span data-ttu-id="8ec74-126">Necesita una aplicación .NET Core que el contenedor de Docker ejecutará.</span><span class="sxs-lookup"><span data-stu-id="8ec74-126">You need a .NET Core app that the Docker container will run.</span></span> <span data-ttu-id="8ec74-127">Abra el terminal, cree un directorio de trabajo e ingrese en él.</span><span class="sxs-lookup"><span data-stu-id="8ec74-127">Open your terminal, create a working directory, and enter it.</span></span> <span data-ttu-id="8ec74-128">En el directorio de trabajo, ejecute el comando siguiente para crear un proyecto en un subdirectorio denominado app:</span><span class="sxs-lookup"><span data-stu-id="8ec74-128">In the working directory, run the following command to create a new project in a subdirectory named app:</span></span>

```console
dotnet new console -o app -n myapp
```

<span data-ttu-id="8ec74-129">Ese comando crea un directorio denominado *app* y genera una aplicación "Hola mundo".</span><span class="sxs-lookup"><span data-stu-id="8ec74-129">That command creates a new directory named *app* and generates a "Hello World" app.</span></span> <span data-ttu-id="8ec74-130">Puede probar esta aplicación para saber qué hace.</span><span class="sxs-lookup"><span data-stu-id="8ec74-130">You can test this app to see what it does.</span></span> <span data-ttu-id="8ec74-131">Escriba el directorio *app* y ejecute el comando `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="8ec74-131">Enter the *app* directory and execute the command `dotnet run`.</span></span> <span data-ttu-id="8ec74-132">Verá la salida siguiente:</span><span class="sxs-lookup"><span data-stu-id="8ec74-132">You'll see the following output:</span></span>

```console
> dotnet run
Hello World!
```

<span data-ttu-id="8ec74-133">La plantilla predeterminada crea una aplicación que imprime en el terminal y luego se cierra.</span><span class="sxs-lookup"><span data-stu-id="8ec74-133">The default template creates an app that prints to the terminal and then exits.</span></span> <span data-ttu-id="8ec74-134">En este tutorial, se usará una aplicación que se repite en bucle de manera indefinida.</span><span class="sxs-lookup"><span data-stu-id="8ec74-134">For this tutorial, you'll use an app that loops indefinitely.</span></span> <span data-ttu-id="8ec74-135">Abra el archivo **Program.cs** en un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="8ec74-135">Open the **Program.cs** file in a text editor.</span></span> <span data-ttu-id="8ec74-136">Actualmente debe ser similar al código siguiente:</span><span class="sxs-lookup"><span data-stu-id="8ec74-136">It should currently look like the following code:</span></span>

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

<span data-ttu-id="8ec74-137">Reemplace el archivo por el código siguiente que cuenta números cada segundo:</span><span class="sxs-lookup"><span data-stu-id="8ec74-137">Replace the file with the following code that counts numbers every second:</span></span>

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

<span data-ttu-id="8ec74-138">Guarde el archivo y vuelva a probar el programa con `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="8ec74-138">Save the file and test the program again with `dotnet run`.</span></span> <span data-ttu-id="8ec74-139">Recuerde que esta aplicación se ejecuta de manera indefinida.</span><span class="sxs-lookup"><span data-stu-id="8ec74-139">Remember that this app runs indefinitely.</span></span> <span data-ttu-id="8ec74-140">Use el comando Cancelar <kbd>CTRL + C</kbd> para detenerla.</span><span class="sxs-lookup"><span data-stu-id="8ec74-140">Use the cancel command <kbd>CTRL + C</kbd> to stop it.</span></span> <span data-ttu-id="8ec74-141">Verá la salida siguiente:</span><span class="sxs-lookup"><span data-stu-id="8ec74-141">You'll see the following output:</span></span>

```console
> dotnet run
Counter: 1
Counter: 2
Counter: 3
Counter: 4
^C
```

<span data-ttu-id="8ec74-142">Si pasa un número en la línea de comandos a la aplicación, solo se contará hasta esa cantidad y se cerrará.</span><span class="sxs-lookup"><span data-stu-id="8ec74-142">If you pass a number on the command line to the app, it will only count up to that amount and then exit.</span></span> <span data-ttu-id="8ec74-143">Inténtelo con `dotnet run -- 5` para contar hasta cinco.</span><span class="sxs-lookup"><span data-stu-id="8ec74-143">Try it with `dotnet run -- 5` to count to five.</span></span>

> [!NOTE]
> <span data-ttu-id="8ec74-144">Cualquier parámetro después de `--` se pasa a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8ec74-144">Any parameters after `--` are passed to your application.</span></span>

## <a name="publish-net-core-app"></a><span data-ttu-id="8ec74-145">Publicación de una aplicación .NET Core</span><span class="sxs-lookup"><span data-stu-id="8ec74-145">Publish .NET Core app</span></span>

<span data-ttu-id="8ec74-146">Antes de agregar la aplicación .NET Core a la imagen de Docker, publíquela.</span><span class="sxs-lookup"><span data-stu-id="8ec74-146">Before you add your .NET Core app to the Docker image, publish it.</span></span> <span data-ttu-id="8ec74-147">El contenedor ejecutará la versión publicada de la aplicación cuando se inicie.</span><span class="sxs-lookup"><span data-stu-id="8ec74-147">The container will execute the published version of the app when it's started.</span></span>

<span data-ttu-id="8ec74-148">Desde el directorio de trabajo, ingrese al directorio **app** con el código fuente de ejemplo y ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="8ec74-148">From the working directory, enter the **app** directory with the example source code and run the following command:</span></span>

```console
dotnet publish -c Release
```

<span data-ttu-id="8ec74-149">Este comando compila la aplicación en la carpeta **publish** de la carpeta de salida de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8ec74-149">This command compiles your app to the **publish** folder in the output folder of your app.</span></span> <span data-ttu-id="8ec74-150">La ruta de acceso a la carpeta **publish** desde el directorio de trabajo debería ser `.\app\bin\Release\netcoreapp2.2\publish\`.</span><span class="sxs-lookup"><span data-stu-id="8ec74-150">The path to the **publish** folder from the working directory should be `.\app\bin\Release\netcoreapp2.2\publish\`</span></span>

<span data-ttu-id="8ec74-151">Obtenga un listado de los directorios de la carpeta publish para comprobar que se creó el archivo **myapp.dll**.</span><span class="sxs-lookup"><span data-stu-id="8ec74-151">Get a directory listing of the publish folder to verify that the **myapp.dll** was created.</span></span> <span data-ttu-id="8ec74-152">Desde el directorio **app**, ejecute uno de los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="8ec74-152">From the **app** directory, run one of the following commands:</span></span>

```console
> dir bin\Release\netcoreapp2.2\publish
 Directory of C:\path-to-working-dir\app\bin\Release\netcoreapp2.2\publish

04/05/2019  11:00 AM    <DIR>          .
04/05/2019  11:00 AM    <DIR>          ..
04/05/2019  11:00 AM               447 myapp.deps.json
04/05/2019  11:00 AM             4,608 myapp.dll
04/05/2019  11:00 AM               448 myapp.pdb
04/05/2019  11:00 AM               154 myapp.runtimeconfig.json
```

```bash
me@DESKTOP:/path-to-working-dir/app$ ls bin/Release/netcoreapp2.2/publish
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
```

<span data-ttu-id="8ec74-153">En el terminal, suba un directorio hasta el directorio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8ec74-153">In your terminal, go up a directory to the working directory.</span></span>

## <a name="create-the-dockerfile"></a><span data-ttu-id="8ec74-154">Creación del archivo Dockerfile</span><span class="sxs-lookup"><span data-stu-id="8ec74-154">Create the Dockerfile</span></span>

<span data-ttu-id="8ec74-155">El archivo *Dockerfile* lo usa el comando `docker build` para crear una imagen de contenedor.</span><span class="sxs-lookup"><span data-stu-id="8ec74-155">The *Dockerfile* file is used by the `docker build` command to create a container image.</span></span> <span data-ttu-id="8ec74-156">Este archivo es un archivo de texto no cifrado denominado *Dockerfile* que no tiene ninguna extensión.</span><span class="sxs-lookup"><span data-stu-id="8ec74-156">This file is a plaintext file named *Dockerfile* that does not have an extension.</span></span> <span data-ttu-id="8ec74-157">Cree un archivo denominado *Dockerfile* en el directorio de trabajo y ábralo en un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="8ec74-157">Create a file named *Dockerfile* in your working directory and open it in a text editor.</span></span> <span data-ttu-id="8ec74-158">Agregue el comando siguiente como la primera línea del archivo:</span><span class="sxs-lookup"><span data-stu-id="8ec74-158">Add the following command as the first line of the file:</span></span>

```dockerfile
FROM mcr.microsoft.com/dotnet/core/runtime:2.2
```

<span data-ttu-id="8ec74-159">El comando `FROM` indica a Docker que extraiga la imagen con la etiqueta **2.2** desde el repositorio **mcr.microsoft.com/dotnet/core/runtime**.</span><span class="sxs-lookup"><span data-stu-id="8ec74-159">The `FROM` command tells Docker to pull down the image tagged **2.2** from the **mcr.microsoft.com/dotnet/core/runtime** repository.</span></span> <span data-ttu-id="8ec74-160">Asegúrese de extraer el runtime de .NET Core que coincida con el runtime que el SDK tiene como destino.</span><span class="sxs-lookup"><span data-stu-id="8ec74-160">Make sure that you pull the .NET Core runtime that matches the runtime targeted by your SDK.</span></span> <span data-ttu-id="8ec74-161">Por ejemplo, en la aplicación que se creó en la sección anterior se usó el SDK de .NET Core 2.2 y se creó una aplicación destinada a .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="8ec74-161">For example, the app created in the previous section used the .NET Core 2.2 SDK and created an app that targeted .NET Core 2.2.</span></span> <span data-ttu-id="8ec74-162">Por lo tanto, la imagen base a la que se hace referencia en *Dockerfile* tiene la etiqueta **2.2**.</span><span class="sxs-lookup"><span data-stu-id="8ec74-162">So the base image referred to in the *Dockerfile* is tagged with **2.2**.</span></span>

<span data-ttu-id="8ec74-163">Guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="8ec74-163">Save the file.</span></span> <span data-ttu-id="8ec74-164">Desde el terminal, ejecute `docker build -t myimage .` y Docker procesará cada línea del *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="8ec74-164">From your terminal, run `docker build -t myimage .` and Docker will process each line in the *Dockerfile*.</span></span> <span data-ttu-id="8ec74-165">`.` del comando `docker build` indica a Docker que use el directorio actual para encontrar un archivo *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="8ec74-165">The `.` in the `docker build` command tells docker to use the current directory to find a *Dockerfile*.</span></span> <span data-ttu-id="8ec74-166">Este comando crea la imagen y un repositorio local denominado **myimage** que apunta a esa imagen.</span><span class="sxs-lookup"><span data-stu-id="8ec74-166">This command builds the image and creates a local repository named **myimage** that points to that image.</span></span> <span data-ttu-id="8ec74-167">Una vez que finalice este comando, ejecute `docker images` para ver una lista de las imágenes instaladas:</span><span class="sxs-lookup"><span data-stu-id="8ec74-167">After this command finishes, run `docker images` to see a list of images installed:</span></span>

```console
> docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
mcr.microsoft.com/dotnet/core/runtime   2.2                 d51bb4452469        2 days ago          314MB
myimage                                 latest              d51bb4452469        2 days ago          314MB
```

<span data-ttu-id="8ec74-168">Observe que ambas imágenes comparten el mismo valor **IMAGE ID**.</span><span class="sxs-lookup"><span data-stu-id="8ec74-168">Notice that the two images share the same **IMAGE ID** value.</span></span> <span data-ttu-id="8ec74-169">El valor es el mismo entre ambas imágenes porque el único comando en *Dockerfile* era basar la imagen nueva en una imagen existente.</span><span class="sxs-lookup"><span data-stu-id="8ec74-169">The value is the same between both images because the only command in the *Dockerfile* was to base the new image on an existing image.</span></span> <span data-ttu-id="8ec74-170">Agreguemos dos comandos a *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="8ec74-170">Let's add two commands to the *Dockerfile*.</span></span> <span data-ttu-id="8ec74-171">Cada comando crear una capa de imagen nueva con el comando final que representa la imagen a la que apuntará el repositorio **myimage**.</span><span class="sxs-lookup"><span data-stu-id="8ec74-171">Each command creates a new image layer with the final command representing the image the **myimage** repository will point to.</span></span>

```dockerfile
COPY app/bin/Release/netcoreapp2.2/publish/ app/

ENTRYPOINT ["dotnet", "app/myapp.dll"]
```

<span data-ttu-id="8ec74-172">El comando `COPY` indica a Docker que copie la carpeta especificada en el equipo a una carpeta del contenedor.</span><span class="sxs-lookup"><span data-stu-id="8ec74-172">The `COPY` command tells Docker to copy the specified folder on your computer to a folder in the container.</span></span> <span data-ttu-id="8ec74-173">En este ejemplo, la carpeta **publish** se copia a una carpeta denominada **app** del contenedor.</span><span class="sxs-lookup"><span data-stu-id="8ec74-173">In this example, the **publish** folder is copied to a folder named **app** in the container.</span></span>

<span data-ttu-id="8ec74-174">El comando siguiente, `ENTRYPOINT`, indica a Docker que configure el contenedor para que se ejecute como ejecutable.</span><span class="sxs-lookup"><span data-stu-id="8ec74-174">The next command, `ENTRYPOINT`, tells docker to configure the container to run as an executable.</span></span> <span data-ttu-id="8ec74-175">Cuando el contenedor se inicia, se ejecuta el comando `ENTRYPOINT`.</span><span class="sxs-lookup"><span data-stu-id="8ec74-175">When the container starts, the `ENTRYPOINT` command runs.</span></span> <span data-ttu-id="8ec74-176">Cuando este comando finaliza, el contenedor se detiene automáticamente.</span><span class="sxs-lookup"><span data-stu-id="8ec74-176">When this command ends, the container will automatically stop.</span></span>

<span data-ttu-id="8ec74-177">Guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="8ec74-177">Save the file.</span></span> <span data-ttu-id="8ec74-178">Desde el terminal, ejecute `docker build -t myimage .` y, cuando el comando finalice, ejecute `docker images`.</span><span class="sxs-lookup"><span data-stu-id="8ec74-178">From your terminal, run `docker build -t myimage .` and when that command finishes, run `docker images`.</span></span>

```console
> docker build -t myimage .
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

<span data-ttu-id="8ec74-179">Cada comando de *Dockerfile* generó una capa y creó un valor **IMAGE ID**.</span><span class="sxs-lookup"><span data-stu-id="8ec74-179">Each command in the *Dockerfile* generated a layer and created an **IMAGE ID**.</span></span> <span data-ttu-id="8ec74-180">El valor **IMAGE ID** final (el suyo será distinto) es **ddcc6646461b** y, a continuación, usted creará un contenedor basado en esta imagen.</span><span class="sxs-lookup"><span data-stu-id="8ec74-180">The final **IMAGE ID** (yours will be different) is **ddcc6646461b** and next you'll create a container based on this image.</span></span>

## <a name="create-a-container"></a><span data-ttu-id="8ec74-181">Crear un contenedor</span><span class="sxs-lookup"><span data-stu-id="8ec74-181">Create a container</span></span>

<span data-ttu-id="8ec74-182">Ahora que tiene una imagen que contiene la aplicación, puede crear un contenedor.</span><span class="sxs-lookup"><span data-stu-id="8ec74-182">Now that you have an image that contains your app, you can create a container.</span></span> <span data-ttu-id="8ec74-183">Hay dos formas de crear un contenedor.</span><span class="sxs-lookup"><span data-stu-id="8ec74-183">You can create a container in two ways.</span></span> <span data-ttu-id="8ec74-184">En primer lugar, cree un contenedor que esté detenido.</span><span class="sxs-lookup"><span data-stu-id="8ec74-184">First, create a new container that is stopped.</span></span>

```console
> docker create myimage
0e8f3c2ca32ce773712a5cca38750f41259a4e54e04bdf0946087e230ad7066c
```

<span data-ttu-id="8ec74-185">El comando `docker create` anterior creará un contenedor basado en la imagen **myimage**.</span><span class="sxs-lookup"><span data-stu-id="8ec74-185">The `docker create` command from above will create a container based on the **myimage** image.</span></span> <span data-ttu-id="8ec74-186">La salida de ese comando muestra el valor **CONTAINER ID** (el suyo será distinto) del contenedor creado.</span><span class="sxs-lookup"><span data-stu-id="8ec74-186">The output of that command shows you the **CONTAINER ID** (yours will be different) of the created container.</span></span> <span data-ttu-id="8ec74-187">Para ver una lista de *todos* los contenedores, use el comando `docker ps -a`:</span><span class="sxs-lookup"><span data-stu-id="8ec74-187">To see a list of *all* containers, use the `docker ps -a` command:</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS        PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   4 seconds ago       Created               boring_matsumoto
```

### <a name="manage-the-container"></a><span data-ttu-id="8ec74-188">Administración del contenedor</span><span class="sxs-lookup"><span data-stu-id="8ec74-188">Manage the container</span></span>

<span data-ttu-id="8ec74-189">Cada contenedor tiene asignado un nombre aleatorio que puede usar para hacer referencia a la instancia de contenedor.</span><span class="sxs-lookup"><span data-stu-id="8ec74-189">Each container is assigned a random name that you can use to refer to that container instance.</span></span> <span data-ttu-id="8ec74-190">Por ejemplo, el contenedor que se creó automáticamente eligió el nombre **boring_matsumoto** (el suyo será distinto) y ese nombre se puede usar para iniciar el contenedor.</span><span class="sxs-lookup"><span data-stu-id="8ec74-190">For example, the container that was created automatically chose the name **boring_matsumoto** (yours will be different) and that name can be used to start the container.</span></span> <span data-ttu-id="8ec74-191">Puede reemplazar el nombre automático por uno específico si usa el parámetro `docker create --name`.</span><span class="sxs-lookup"><span data-stu-id="8ec74-191">You override the automatic name with a specific one by using the `docker create --name` parameter.</span></span>

<span data-ttu-id="8ec74-192">En el ejemplo siguiente se usa el comando `docker start` para iniciar el contenedor y luego se usa el comando `docker ps` para mostrar solo los contenedores que están en ejecución:</span><span class="sxs-lookup"><span data-stu-id="8ec74-192">The following example uses the `docker start` command to start the container, and then uses the `docker ps` command to only show containers that are running:</span></span>

```console
> docker start boring_matsumoto
boring_matsumoto

> docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS         PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   7 minutes ago       Up 8 seconds           boring_matsumoto
```

<span data-ttu-id="8ec74-193">De manera similar, el comando `docker stop` detendrá el contenedor.</span><span class="sxs-lookup"><span data-stu-id="8ec74-193">Similarly, the `docker stop` command will stop the container.</span></span> <span data-ttu-id="8ec74-194">En el ejemplo siguiente se usa el comando `docker stop` para detener el contenedor y luego se usa el comando `docker ps` para mostrar que no hay ningún contenedor en ejecución.</span><span class="sxs-lookup"><span data-stu-id="8ec74-194">The following example uses the `docker stop` command to stop the container, and then uses the `docker ps` command to show that no containers are running.</span></span>

```console
> docker stop boring_matsumoto
boring_matsumoto

> docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS   NAMES
```

### <a name="connect-to-a-container"></a><span data-ttu-id="8ec74-195">Conectarse a un contenedor</span><span class="sxs-lookup"><span data-stu-id="8ec74-195">Connect to a container</span></span>

<span data-ttu-id="8ec74-196">Una vez que se ejecuta un contenedor, puede conectarse a él para ver la salida.</span><span class="sxs-lookup"><span data-stu-id="8ec74-196">After a container is running, you can connect to it to see the output.</span></span> <span data-ttu-id="8ec74-197">Use los comandos `docker start` y `docker attach` para iniciar el contenedor y echar un vistazo al flujo de salida.</span><span class="sxs-lookup"><span data-stu-id="8ec74-197">Use the `docker start` and `docker attach` commands to start the container and peek at the output stream.</span></span> <span data-ttu-id="8ec74-198">En este ejemplo, el comando <kbd>CTRL + C</kbd> se usa para desasociarse del contenedor en ejecución.</span><span class="sxs-lookup"><span data-stu-id="8ec74-198">In this example, the <kbd>CTRL + C</kbd> command is used to detach from the running container.</span></span> <span data-ttu-id="8ec74-199">Esto podría realmente finalizar el proceso en el contenedor, lo que detendrá el contenedor.</span><span class="sxs-lookup"><span data-stu-id="8ec74-199">This may actually end the process in the container, which will stop the container.</span></span> <span data-ttu-id="8ec74-200">El parámetro `--sig-proxy=false` garantiza que <kbd>CTRL + C</kbd> no detendrá el proceso en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="8ec74-200">The `--sig-proxy=false` parameter ensures that <kbd>CTRL + C</kbd> will not stop the process in the container.</span></span>

<span data-ttu-id="8ec74-201">Después de desasociarse del contenedor, reasócielo para comprobar que sigue en ejecución.</span><span class="sxs-lookup"><span data-stu-id="8ec74-201">After you detach from the container, reattach to verify that it's still running and counting.</span></span>

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

### <a name="delete-a-container"></a><span data-ttu-id="8ec74-202">Eliminación de un contenedor</span><span class="sxs-lookup"><span data-stu-id="8ec74-202">Delete a container</span></span>

<span data-ttu-id="8ec74-203">Para el propósito de este artículo, no queremos contenedores que solo existan y no hagan nada.</span><span class="sxs-lookup"><span data-stu-id="8ec74-203">For the purposes of this article you don't want containers just hanging around doing nothing.</span></span> <span data-ttu-id="8ec74-204">Elimine el contenedor que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="8ec74-204">Delete the container you previously created.</span></span> <span data-ttu-id="8ec74-205">Si el contenedor está en ejecución, deténgalo.</span><span class="sxs-lookup"><span data-stu-id="8ec74-205">If the container is running, stop it.</span></span>

```console
> docker stop boring_matsumoto
```

<span data-ttu-id="8ec74-206">En el ejemplo siguiente se muestran todos los contenedores.</span><span class="sxs-lookup"><span data-stu-id="8ec74-206">The following example lists all containers.</span></span> <span data-ttu-id="8ec74-207">Luego, usa el comando `docker rm` para eliminar el contenedor y después vuelve a comprobar si hay algún contenedor en ejecución.</span><span class="sxs-lookup"><span data-stu-id="8ec74-207">It then uses the `docker rm` command to delete the container, and then checks a second time for any running containers.</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS     PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   19 minutes ago      Exited             boring_matsumoto

> docker rm boring_matsumoto
boring_matsumoto

> docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS    NAMES
```

### <a name="single-run"></a><span data-ttu-id="8ec74-208">Ejecución única</span><span class="sxs-lookup"><span data-stu-id="8ec74-208">Single run</span></span>

<span data-ttu-id="8ec74-209">Docker proporciona el comando `docker run` para crear y ejecutar el contenedor como comando único.</span><span class="sxs-lookup"><span data-stu-id="8ec74-209">Docker provides the `docker run` command to create and run the container as a single command.</span></span> <span data-ttu-id="8ec74-210">Este comando elimina la necesidad de ejecutar `docker create` y luego `docker start`.</span><span class="sxs-lookup"><span data-stu-id="8ec74-210">This command eliminates the need to run `docker create` and then `docker start`.</span></span> <span data-ttu-id="8ec74-211">También puede establecer este comando en que elimine automáticamente el contenedor cuando este se detenga.</span><span class="sxs-lookup"><span data-stu-id="8ec74-211">You can also set this command to automatically delete the container when the container stops.</span></span> <span data-ttu-id="8ec74-212">Por ejemplo, use `docker run -it --rm` para hacer dos cosas: primero, use automáticamente el terminal actual para conectarse al contenedor y cuando el contenedor finalice, quítelo:</span><span class="sxs-lookup"><span data-stu-id="8ec74-212">For example, use `docker run -it --rm` to do two things, first, automatically use the current terminal to connect to the container, and then when the container finishes, remove it:</span></span>

```
> docker run -it --rm myimage
Counter: 1
Counter: 2
Counter: 3
Counter: 4
Counter: 5
^C
```

<span data-ttu-id="8ec74-213">Con `docker run -it`, el comando <kbd>CTRL + C</kbd> detendrá el proceso que está en ejecución en el contenedor, lo que, a su vez, detendrá el contenedor.</span><span class="sxs-lookup"><span data-stu-id="8ec74-213">With `docker run -it`, the <kbd>CTRL + C</kbd> command will stop process that is running in the container, which in turn, stops the container.</span></span> <span data-ttu-id="8ec74-214">Como se proporcionó el parámetro `--rm`, el contenedor se elimina automáticamente cuando se detiene el proceso.</span><span class="sxs-lookup"><span data-stu-id="8ec74-214">Since the `--rm` parameter was provided, the container is automatically deleted when the process is stopped.</span></span> <span data-ttu-id="8ec74-215">Compruebe que no existe:</span><span class="sxs-lookup"><span data-stu-id="8ec74-215">Verify that it does not exist:</span></span>

```
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS    PORTS   NAMES
```

### <a name="change-the-entrypoint"></a><span data-ttu-id="8ec74-216">Cambio de ENTRYPOINT</span><span class="sxs-lookup"><span data-stu-id="8ec74-216">Change the ENTRYPOINT</span></span>

<span data-ttu-id="8ec74-217">El comando `docker run` también permite modificar el comando `ENTRYPOINT` desde el archivo *Dockerfile* y ejecute algún otro elemento, pero solo para ese contenedor.</span><span class="sxs-lookup"><span data-stu-id="8ec74-217">The `docker run` command also lets you modify the `ENTRYPOINT` command from the *Dockerfile* and run something else, but only for that container.</span></span> <span data-ttu-id="8ec74-218">Por ejemplo, use el comando siguiente para ejecutar `bash` o `cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="8ec74-218">For example, use the following command to run `bash` or `cmd.exe`.</span></span> <span data-ttu-id="8ec74-219">Edite el comando según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="8ec74-219">Edit the command as necessary.</span></span>

#### <a name="windows"></a><span data-ttu-id="8ec74-220">Windows</span><span class="sxs-lookup"><span data-stu-id="8ec74-220">Windows</span></span>
<span data-ttu-id="8ec74-221">En este ejemplo, `ENTRYPOINT` se cambia a `cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="8ec74-221">In this example the `ENTRYPOINT` is changed to `cmd.exe`.</span></span> <span data-ttu-id="8ec74-222">Se presiona <kbd>CTRL + C</kbd> para finalizar el proceso y detener el contenedor.</span><span class="sxs-lookup"><span data-stu-id="8ec74-222"><kbd>CTRL + C</kbd> is pressed to end the process and stop the container.</span></span>

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

#### <a name="linux"></a><span data-ttu-id="8ec74-223">Linux</span><span class="sxs-lookup"><span data-stu-id="8ec74-223">Linux</span></span>

<span data-ttu-id="8ec74-224">En este ejemplo, `ENTRYPOINT` cambia a `bash`.</span><span class="sxs-lookup"><span data-stu-id="8ec74-224">In this example the `ENTRYPOINT` is changed to `bash`.</span></span> <span data-ttu-id="8ec74-225">Se ejecuta el comando `quit`, lo que finaliza el proceso y detiene el contenedor.</span><span class="sxs-lookup"><span data-stu-id="8ec74-225">The `quit` command is run which ends the process and stop the container.</span></span>

```bash
root@user:~# docker run -it --rm --entrypoint "bash" myimage
root@8515e897c893:/# ls app
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
root@8515e897c893:/# exit
exit
```

## <a name="essential-commands"></a><span data-ttu-id="8ec74-226">Comandos esenciales</span><span class="sxs-lookup"><span data-stu-id="8ec74-226">Essential commands</span></span>

<span data-ttu-id="8ec74-227">Docker tiene muchos comandos distintos que abarcan las acciones que quiere hacer con el contenedor y las imágenes.</span><span class="sxs-lookup"><span data-stu-id="8ec74-227">Docker has many different commands that cover what you want to do with your container and images.</span></span> <span data-ttu-id="8ec74-228">Estos comandos de Docker son esenciales para la administración de los contenedores:</span><span class="sxs-lookup"><span data-stu-id="8ec74-228">These Docker commands are essential to managing your containers:</span></span>

* [<span data-ttu-id="8ec74-229">docker build</span><span class="sxs-lookup"><span data-stu-id="8ec74-229">docker build</span></span>](https://docs.docker.com/engine/reference/commandline/build/)
* [<span data-ttu-id="8ec74-230">docker run</span><span class="sxs-lookup"><span data-stu-id="8ec74-230">docker run</span></span>](https://docs.docker.com/engine/reference/commandline/run/)
* [<span data-ttu-id="8ec74-231">docker ps</span><span class="sxs-lookup"><span data-stu-id="8ec74-231">docker ps</span></span>](https://docs.docker.com/engine/reference/commandline/ps/)
* [<span data-ttu-id="8ec74-232">docker stop</span><span class="sxs-lookup"><span data-stu-id="8ec74-232">docker stop</span></span>](https://docs.docker.com/engine/reference/commandline/stop/)
* [<span data-ttu-id="8ec74-233">docker rm</span><span class="sxs-lookup"><span data-stu-id="8ec74-233">docker rm</span></span>](https://docs.docker.com/engine/reference/commandline/rm/)
* [<span data-ttu-id="8ec74-234">docker rmi</span><span class="sxs-lookup"><span data-stu-id="8ec74-234">docker rmi</span></span>](https://docs.docker.com/engine/reference/commandline/rmi/)
* [<span data-ttu-id="8ec74-235">docker image</span><span class="sxs-lookup"><span data-stu-id="8ec74-235">docker image</span></span>](https://docs.docker.com/engine/reference/commandline/image/)

## <a name="clean-up-resources"></a><span data-ttu-id="8ec74-236">Limpiar los recursos</span><span class="sxs-lookup"><span data-stu-id="8ec74-236">Clean up resources</span></span>

<span data-ttu-id="8ec74-237">Durante este tutorial, creó contenedores e imágenes.</span><span class="sxs-lookup"><span data-stu-id="8ec74-237">During this tutorial you created containers and images.</span></span> <span data-ttu-id="8ec74-238">Elimine estos recursos si quiere hacerlo.</span><span class="sxs-lookup"><span data-stu-id="8ec74-238">If you want, delete these resources.</span></span> <span data-ttu-id="8ec74-239">Use los comandos siguientes para</span><span class="sxs-lookup"><span data-stu-id="8ec74-239">Use the following commands to</span></span>

01. <span data-ttu-id="8ec74-240">Mostrar todos los contenedores</span><span class="sxs-lookup"><span data-stu-id="8ec74-240">List all containers</span></span>

    ```console
    > docker ps -a
    ```

02. <span data-ttu-id="8ec74-241">Detener los contenedores que están en ejecución</span><span class="sxs-lookup"><span data-stu-id="8ec74-241">Stop containers that are running.</span></span> <span data-ttu-id="8ec74-242">`CONTAINER_NAME` representa el nombre que se asignó automáticamente al contenedor.</span><span class="sxs-lookup"><span data-stu-id="8ec74-242">The `CONTAINER_NAME` represents the name automatically assigned to the container.</span></span>

    ```console
    > docker stop CONTAINER_NAME
    ```

03. <span data-ttu-id="8ec74-243">Eliminar el contenedor</span><span class="sxs-lookup"><span data-stu-id="8ec74-243">Delete the container</span></span>

    ```console
    > docker rm CONTAINER_NAME
    ```

<span data-ttu-id="8ec74-244">A continuación, elimine las imágenes que ya no quiere tener en la máquina.</span><span class="sxs-lookup"><span data-stu-id="8ec74-244">Next, delete any images that you no longer want on your machine.</span></span> <span data-ttu-id="8ec74-245">Elimine la imagen que creó el archivo *Dockerfile* y luego elimine la imagen de .NET Core en que se basó el archivo *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="8ec74-245">Delete the image created by your *Dockerfile* and then delete the .NET Core image the *Dockerfile* was based on.</span></span> <span data-ttu-id="8ec74-246">Puede usar el valor **IMAGE ID** o la cadena con formato **REPOSITORY:TAG**.</span><span class="sxs-lookup"><span data-stu-id="8ec74-246">You can use the **IMAGE ID** or the **REPOSITORY:TAG** formatted string.</span></span>

```console
docker rmi myimage:latest
docker rmi mcr.microsoft.com/dotnet/core/runtime:2.2
```

<span data-ttu-id="8ec74-247">Use el comando `docker images` para ver una lista de las imágenes instaladas.</span><span class="sxs-lookup"><span data-stu-id="8ec74-247">Use the `docker images` command to see a list of images installed.</span></span>

> [!NOTE]
> <span data-ttu-id="8ec74-248">Los archivos de imagen pueden ser grandes.</span><span class="sxs-lookup"><span data-stu-id="8ec74-248">Image files can be large.</span></span> <span data-ttu-id="8ec74-249">Por lo general, quitaría los contenedores temporales que creó al probar y desarrollar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8ec74-249">Typically, you would remove temporary containers you created while testing and developing your app.</span></span> <span data-ttu-id="8ec74-250">Habitualmente, estas imágenes base se conservan con el runtime instalado si se planea crear otras imágenes basadas en ese runtime.</span><span class="sxs-lookup"><span data-stu-id="8ec74-250">You usually keep the base images with the runtime installed if you plan on building other images based on that runtime.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8ec74-251">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="8ec74-251">Next steps</span></span>

* <span data-ttu-id="8ec74-252">[Consulte el tutorial de ASP.NET Core para los microservicios](https://dotnet.microsoft.com/learn/web/aspnet-microservice-tutorial/intro).</span><span class="sxs-lookup"><span data-stu-id="8ec74-252">[Try the ASP.NET Core Microservice Tutorial.](https://dotnet.microsoft.com/learn/web/aspnet-microservice-tutorial/intro)</span></span>
* <span data-ttu-id="8ec74-253">[Revise los servicios de Azure que admiten contenedores](https://azure.microsoft.com/en-us/overview/containers/).</span><span class="sxs-lookup"><span data-stu-id="8ec74-253">[Review the Azure services that support containers.](https://azure.microsoft.com/en-us/overview/containers/)</span></span>
* <span data-ttu-id="8ec74-254">[Lea sobre los comandos de Dockerfile](https://docs.docker.com/engine/reference/builder/).</span><span class="sxs-lookup"><span data-stu-id="8ec74-254">[Read about Dockerfile commands.](https://docs.docker.com/engine/reference/builder/)</span></span>
