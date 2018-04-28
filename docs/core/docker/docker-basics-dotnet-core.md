---
title: Información sobre los aspectos básicos de Docker con .NET Core
description: Tutorial básico sobre Docker y .NET Core
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.topic: tutorial
ms.prod: dotnet-core
ms.technology: dotnet-docker
ms.devlang: dotnet
ms.custom: mvc
manager: wpickett
ms.workload:
- dotnetcore
ms.openlocfilehash: 085ddb58aae78737fae642e7334e7f0139f0cfec
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="learn-docker-basics-with-net-core"></a><span data-ttu-id="835c7-103">Información sobre los aspectos básicos de Docker con .NET Core</span><span class="sxs-lookup"><span data-stu-id="835c7-103">Learn Docker Basics with .NET Core</span></span>

<span data-ttu-id="835c7-104">Este tutorial trata sobre las tareas de compilación e implementación de un contenedor de Docker para una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="835c7-104">This tutorial teaches the Docker container build and deploy tasks for a .NET Core application.</span></span> <span data-ttu-id="835c7-105">Este tutorial ayuda a:</span><span class="sxs-lookup"><span data-stu-id="835c7-105">During the course of this tutorial, you learn:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="835c7-106">Crear un Dockerfile</span><span class="sxs-lookup"><span data-stu-id="835c7-106">How to create a Dockerfile</span></span>
> * <span data-ttu-id="835c7-107">Crear una aplicación .NET Core</span><span class="sxs-lookup"><span data-stu-id="835c7-107">How to create a .NET Core app.</span></span>
> * <span data-ttu-id="835c7-108">Implementar la aplicación en un contenedor de Docker</span><span class="sxs-lookup"><span data-stu-id="835c7-108">How to deploy your app into a Docker container.</span></span>

<span data-ttu-id="835c7-109">La [plataforma Docker](https://docs.docker.com/engine/docker-overview/#the-docker-platform) usa el [motor de Docker](https://docs.docker.com/engine/docker-overview/#docker-engine) para compilar y empaquetar aplicaciones rápidamente como [imágenes de Docker](https://docs.docker.com/glossary/?term=image).</span><span class="sxs-lookup"><span data-stu-id="835c7-109">The [Docker platform](https://docs.docker.com/engine/docker-overview/#the-docker-platform) uses the [Docker Engine](https://docs.docker.com/engine/docker-overview/#docker-engine) to quickly build and package apps as [Docker images](https://docs.docker.com/glossary/?term=image).</span></span> <span data-ttu-id="835c7-110">Estas imágenes se escriben en el formato [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) para implementarse y ejecutarse en un [contenedor superpuesto](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).</span><span class="sxs-lookup"><span data-stu-id="835c7-110">These images are written in the [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) format to be deployed and run in a [layered container](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).</span></span>

## <a name="net-core-easiest-way-to-get-started"></a><span data-ttu-id="835c7-111">.NET Core: la manera más sencilla de empezar a trabajar</span><span class="sxs-lookup"><span data-stu-id="835c7-111">.NET Core: Easiest way to get started</span></span>

<span data-ttu-id="835c7-112">Antes de crear la imagen de Docker, necesita una aplicación que incluir en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="835c7-112">Before creating the Docker image, you need an application to containerize.</span></span> <span data-ttu-id="835c7-113">Puede crearla en Linux, MacOS o Windows.</span><span class="sxs-lookup"><span data-stu-id="835c7-113">You can create it on Linux, MacOS, or Windows.</span></span> <span data-ttu-id="835c7-114">La forma más rápida y sencilla de hacerlo es usar .NET Core.</span><span class="sxs-lookup"><span data-stu-id="835c7-114">The quickest and easiest way to do that is to use .NET Core.</span></span>

<span data-ttu-id="835c7-115">Si no está familiarizado con el conjunto de herramientas de la CLI de .NET Core, vea la [información general del SDK de .NET Core](../tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="835c7-115">If you're unfamiliar with the .NET Core CLI toolset, read the [.NET Core SDK overview](../tools/index.md).</span></span>

<span data-ttu-id="835c7-116">Puede compilar contenedores de Windows y Linux con [etiquetas de varias arquitecturas](https://github.com/dotnet/announcements/issues/14).</span><span class="sxs-lookup"><span data-stu-id="835c7-116">You can build both Windows and Linux containers with [multi-arch based tags](https://github.com/dotnet/announcements/issues/14).</span></span>

## <a name="your-first-net-core-docker-app"></a><span data-ttu-id="835c7-117">La primera aplicación de .NET Core Docker</span><span class="sxs-lookup"><span data-stu-id="835c7-117">Your first .NET Core Docker app</span></span>

### <a name="prerequisites"></a><span data-ttu-id="835c7-118">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="835c7-118">Prerequisites</span></span>

<span data-ttu-id="835c7-119">Para realizar este tutorial:</span><span class="sxs-lookup"><span data-stu-id="835c7-119">To complete this tutorial:</span></span>

#### <a name="net-core-20-sdk"></a><span data-ttu-id="835c7-120">SDK de .NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="835c7-120">.NET Core 2.0 SDK</span></span>

* <span data-ttu-id="835c7-121">Instale el [SDK de .NET Core 2.0](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="835c7-121">Install [.NET Core SDK 2.0](https://www.microsoft.com/net/core).</span></span>

<span data-ttu-id="835c7-122">Vea [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) (.NET Core 2.x: versiones de SO compatibles) para obtener una lista completa de sistemas operativos compatibles con .NET Core 2.x, fuera de las versiones de sistema operativo compatibles y los vínculos de directiva de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="835c7-122">See [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) for the complete list of .NET Core 2.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

* <span data-ttu-id="835c7-123">Instale el editor de código que prefiera si aún no lo ha hecho.</span><span class="sxs-lookup"><span data-stu-id="835c7-123">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="835c7-124">¿Es necesario instalar un editor de código?</span><span class="sxs-lookup"><span data-stu-id="835c7-124">Need to install a code editor?</span></span> <span data-ttu-id="835c7-125">Pruebe [Visual Studio](https://visualstudio.com/downloads).</span><span class="sxs-lookup"><span data-stu-id="835c7-125">Try [Visual Studio](https://visualstudio.com/downloads)!</span></span>

#### <a name="installing-docker-client"></a><span data-ttu-id="835c7-126">Instalación del cliente Docker</span><span class="sxs-lookup"><span data-stu-id="835c7-126">Installing Docker Client</span></span>

<span data-ttu-id="835c7-127">Instale la versión [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) o posterior del cliente Docker.</span><span class="sxs-lookup"><span data-stu-id="835c7-127">Install [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) or later of the Docker client.</span></span>

<span data-ttu-id="835c7-128">El cliente Docker se puede instalar en:</span><span class="sxs-lookup"><span data-stu-id="835c7-128">The Docker client can be installed in:</span></span>

* <span data-ttu-id="835c7-129">Distribuciones de Linux</span><span class="sxs-lookup"><span data-stu-id="835c7-129">Linux distributions</span></span>

   * [<span data-ttu-id="835c7-130">CentOS</span><span class="sxs-lookup"><span data-stu-id="835c7-130">CentOS</span></span>](https://www.docker.com/docker-centos-distribution)

   * [<span data-ttu-id="835c7-131">Debian</span><span class="sxs-lookup"><span data-stu-id="835c7-131">Debian</span></span>](https://www.docker.com/docker-debian)

   * [<span data-ttu-id="835c7-132">Fedora</span><span class="sxs-lookup"><span data-stu-id="835c7-132">Fedora</span></span>](https://www.docker.com/docker-fedora)

   * [<span data-ttu-id="835c7-133">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="835c7-133">Ubuntu</span></span>](https://www.docker.com/docker-ubuntu)

* [<span data-ttu-id="835c7-134">macOS</span><span class="sxs-lookup"><span data-stu-id="835c7-134">macOS</span></span>](https://docs.docker.com/docker-for-mac/)

* <span data-ttu-id="835c7-135">[Windows](https://docs.docker.com/docker-for-windows/).</span><span class="sxs-lookup"><span data-stu-id="835c7-135">[Windows](https://docs.docker.com/docker-for-windows/).</span></span>

### <a name="create-a-net-core-20-console-app-for-dockerization"></a><span data-ttu-id="835c7-136">Crear una aplicación de consola de .NET Core 2.0 para aplicarle Docker</span><span class="sxs-lookup"><span data-stu-id="835c7-136">Create a .NET Core 2.0 console app for Dockerization</span></span>

<span data-ttu-id="835c7-137">Abra un símbolo del sistema y cree una carpeta denominada *Hello*.</span><span class="sxs-lookup"><span data-stu-id="835c7-137">Open a command prompt and create a folder named *Hello*.</span></span> <span data-ttu-id="835c7-138">Vaya a la carpeta que ha creado y escriba los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="835c7-138">Navigate to the folder you created and type the following commands:</span></span>

```console
dotnet new console
dotnet run
```

<span data-ttu-id="835c7-139">Veamos un tutorial rápido:</span><span class="sxs-lookup"><span data-stu-id="835c7-139">Let's do a quick walkthrough:</span></span>

1. `$ dotnet new console`

   <span data-ttu-id="835c7-140">[`dotnet new`](../tools/dotnet-new.md) crea un archivo de proyecto `Hello.csproj` actualizado con las dependencias necesarias para compilar una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="835c7-140">[`dotnet new`](../tools/dotnet-new.md) creates an up-to-date `Hello.csproj` project file with the dependencies necessary to build a console app.</span></span>  <span data-ttu-id="835c7-141">Además, se crea un archivo `Program.cs`, un archivo básico que contiene el punto de entrada para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="835c7-141">It also creates a `Program.cs`, a basic file containing the entry point for the application.</span></span>
   
   <span data-ttu-id="835c7-142">`Hello.csproj`:</span><span class="sxs-lookup"><span data-stu-id="835c7-142">`Hello.csproj`:</span></span>

   <span data-ttu-id="835c7-143">El archivo de proyecto especifica todo lo que es necesario para restaurar las dependencias y compilar el programa.</span><span class="sxs-lookup"><span data-stu-id="835c7-143">The project file specifies everything that's needed to restore dependencies and build the program.</span></span>

   * <span data-ttu-id="835c7-144">La etiqueta `OutputType` especifica que estamos creando un archivo ejecutable, es decir, una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="835c7-144">The `OutputType` tag specifies that we're building an executable, in other words a console application.</span></span>
   * <span data-ttu-id="835c7-145">La etiqueta `TargetFramework` especifica la implementación .NET a la que nos dirigimos.</span><span class="sxs-lookup"><span data-stu-id="835c7-145">The `TargetFramework` tag specifies what .NET implementation we're targeting.</span></span> <span data-ttu-id="835c7-146">En un escenario avanzado, puede especificar varios marcos de destino y compilar en los especificados en una sola operación.</span><span class="sxs-lookup"><span data-stu-id="835c7-146">In an advanced scenario, you can specify multiple target frameworks and build to the specified frameworks in a single operation.</span></span> <span data-ttu-id="835c7-147">En este tutorial se compila para .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="835c7-147">In this tutorial, we build for .NET Core 2.0.</span></span>

   <span data-ttu-id="835c7-148">`Program.cs`:</span><span class="sxs-lookup"><span data-stu-id="835c7-148">`Program.cs`:</span></span>

   <span data-ttu-id="835c7-149">`using System` inicia el programa.</span><span class="sxs-lookup"><span data-stu-id="835c7-149">The program starts by `using System`.</span></span> <span data-ttu-id="835c7-150">Esta instrucción significa "llevar cada cosa del espacio de nombres `System` al ámbito de este archivo".</span><span class="sxs-lookup"><span data-stu-id="835c7-150">This statement means, "Bring everything in the `System` namespace into scope for this file."</span></span> <span data-ttu-id="835c7-151">El espacio de nombres `System` incluye construcciones básicas, como `string` o tipos numéricos.</span><span class="sxs-lookup"><span data-stu-id="835c7-151">The `System` namespace includes basic constructs such as `string`, or numeric types.</span></span>

   <span data-ttu-id="835c7-152">Después, definimos un espacio de nombres denominado `Hello`.</span><span class="sxs-lookup"><span data-stu-id="835c7-152">We then define a namespace called `Hello`.</span></span> <span data-ttu-id="835c7-153">Puede cambiar el espacio de nombres por lo que quiera.</span><span class="sxs-lookup"><span data-stu-id="835c7-153">You can change namespace to anything you want.</span></span> <span data-ttu-id="835c7-154">Se define una clase denominada `Program` dentro del espacio de nombres, con un método `Main` que toma una matriz de cadenas como argumento.</span><span class="sxs-lookup"><span data-stu-id="835c7-154">A class named `Program` is defined within that namespace, with a `Main` method that takes an array of strings as its argument.</span></span> <span data-ttu-id="835c7-155">Esta matriz contiene la lista de argumentos que se ha pasado cuando se llama al programa compilado.</span><span class="sxs-lookup"><span data-stu-id="835c7-155">This array contains the list of arguments passed in when the compiled program is called.</span></span> <span data-ttu-id="835c7-156">En el ejemplo, el programa solo escribe "¡Hello World!"</span><span class="sxs-lookup"><span data-stu-id="835c7-156">In our example, the program only writes "Hello World!"</span></span> <span data-ttu-id="835c7-157">en la consola.</span><span class="sxs-lookup"><span data-stu-id="835c7-157">to the console.</span></span>

2. `$ dotnet restore`

   <span data-ttu-id="835c7-158">En .NET Core 2.x, **dotnet new** ejecuta el comando [`dotnet restore`](../tools/dotnet-restore.md).</span><span class="sxs-lookup"><span data-stu-id="835c7-158">In .NET Core 2.x, **dotnet new** runs the [`dotnet restore`](../tools/dotnet-restore.md) command.</span></span> <span data-ttu-id="835c7-159">**Dotnet restore** restaura el árbol de dependencias con una llamada a [NuGet](https://www.nuget.org/) (administrador de paquetes de .NET).</span><span class="sxs-lookup"><span data-stu-id="835c7-159">**Dotnet restore** restores the tree of dependencies with a [NuGet](https://www.nuget.org/)(.NET package manager) call.</span></span>
   <span data-ttu-id="835c7-160">NuGet realiza las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="835c7-160">NuGet performs the following tasks:</span></span>
   * <span data-ttu-id="835c7-161">analiza el archivo *Hello.csproj*</span><span class="sxs-lookup"><span data-stu-id="835c7-161">analyzes the *Hello.csproj* file</span></span> 
   * <span data-ttu-id="835c7-162">descarga las dependencias del archivo (o las obtiene de la caché del equipo)</span><span class="sxs-lookup"><span data-stu-id="835c7-162">downloads the file dependencies (or grabs from your machine cache)</span></span>
   * <span data-ttu-id="835c7-163">escribe el archivo *obj/project.assets.json*</span><span class="sxs-lookup"><span data-stu-id="835c7-163">writes the *obj/project.assets.json* file</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
   
   <span data-ttu-id="835c7-164">El archivo *project.assets.json* es un conjunto completo del gráfico de dependencias de NuGet, las resoluciones de enlaces y otros metadatos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="835c7-164">The *project.assets.json* file is a complete set of the NuGet dependencies graph, binding resolutions, and other app metadata.</span></span> <span data-ttu-id="835c7-165">Este archivo obligatorio se usa con otras herramientas, como [`dotnet build`](../tools/dotnet-build.md) y [`dotnet run`](../tools/dotnet-run.md), para procesar correctamente el código fuente.</span><span class="sxs-lookup"><span data-stu-id="835c7-165">This required file is used by other tools, such as [`dotnet build`](../tools/dotnet-build.md) and [`dotnet run`](../tools/dotnet-run.md), to correctly process the source code.</span></span>
   
3. `$ dotnet run`

   <span data-ttu-id="835c7-166">[`dotnet run`](../tools/dotnet-run.md) llama a [`dotnet build`](../tools/dotnet-build.md) para confirmar una compilación correcta y luego llama a `dotnet <assembly.dll>` para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="835c7-166">[`dotnet run`](../tools/dotnet-run.md) calls [`dotnet build`](../tools/dotnet-build.md) to confirm a successful build, and then calls `dotnet <assembly.dll>` to run the application.</span></span>
   
    ```console
    $ dotnet run
    
    Hello World!
    ```

    <span data-ttu-id="835c7-167">En escenarios avanzados, vea [Implementación de aplicaciones .NET Core](../deploying/index.md) para obtener detalles.</span><span class="sxs-lookup"><span data-stu-id="835c7-167">For advanced scenarios,  see [.NET Core Application Deployment](../deploying/index.md) for details.</span></span>

## <a name="dockerize-the-net-core-application"></a><span data-ttu-id="835c7-168">Aplicar Docker a la aplicación .NET Core</span><span class="sxs-lookup"><span data-stu-id="835c7-168">Dockerize the .NET Core application</span></span>

<span data-ttu-id="835c7-169">La aplicación de consola Hello de .NET Core se ejecuta correctamente en local.</span><span class="sxs-lookup"><span data-stu-id="835c7-169">The Hello .NET Core console app successfully runs locally.</span></span> <span data-ttu-id="835c7-170">El siguiente paso es compilar y ejecutar la aplicación en Docker.</span><span class="sxs-lookup"><span data-stu-id="835c7-170">Now let's take it a step further and build and run the app in Docker.</span></span>

### <a name="your-first-dockerfile"></a><span data-ttu-id="835c7-171">El primer Dockerfile</span><span class="sxs-lookup"><span data-stu-id="835c7-171">Your first Dockerfile</span></span>

<span data-ttu-id="835c7-172">Abra el editor de texto para empezar.</span><span class="sxs-lookup"><span data-stu-id="835c7-172">Open your text editor and let's get started!</span></span> <span data-ttu-id="835c7-173">Todavía no está trabajando desde el directorio Hello en que se ha compilado la aplicación.</span><span class="sxs-lookup"><span data-stu-id="835c7-173">We're still working from the Hello directory we built the app in.</span></span>

<span data-ttu-id="835c7-174">Agregue las siguientes instrucciones de Docker para cada [contenedor de Windows o Linux](https://docs.microsoft.com/virtualization/windowscontainers/about/) a un archivo nuevo.</span><span class="sxs-lookup"><span data-stu-id="835c7-174">Add the following Docker instructions for either Linux or [Windows Containers](https://docs.microsoft.com/virtualization/windowscontainers/about/) to a new file.</span></span> <span data-ttu-id="835c7-175">Cuando termine, guárdelo en la raíz del directorio Hello como **Dockerfile**, sin extensión (puede que necesite establecer el tipo de archivo en `All types (*.*)` o similar).</span><span class="sxs-lookup"><span data-stu-id="835c7-175">When finished, save it in the root of your Hello directory as **Dockerfile**, with no extension (You may need to set your file type to `All types (*.*)` or something similar).</span></span>

```Dockerfile
FROM microsoft/dotnet:2.0-sdk
WORKDIR /app

# copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# copy and build everything else
COPY . ./
RUN dotnet publish -c Release -o out
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

<span data-ttu-id="835c7-176">El Dockerfile contiene las instrucciones de compilación de Docker que se ejecutan secuencialmente.</span><span class="sxs-lookup"><span data-stu-id="835c7-176">The Dockerfile contains Docker build instructions that run sequentially.</span></span>

<span data-ttu-id="835c7-177">La primera instrucción debe ser [**FROM**](https://docs.docker.com/engine/reference/builder/#from).</span><span class="sxs-lookup"><span data-stu-id="835c7-177">The first instruction must be [**FROM**](https://docs.docker.com/engine/reference/builder/#from).</span></span> <span data-ttu-id="835c7-178">Esta instrucción inicializa una nueva fase de compilación y establece la imagen base para las instrucciones restantes.</span><span class="sxs-lookup"><span data-stu-id="835c7-178">This instruction initializes a new build stage and sets the Base Image for the remaining instructions.</span></span> <span data-ttu-id="835c7-179">Las etiquetas de varias arquitecturas extraen contenedores de Windows o Linux según [el modo de contenedor](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers) de Docker para Windows.</span><span class="sxs-lookup"><span data-stu-id="835c7-179">The multi-arch tags pull either Windows or Linux containers depending on the Docker for Windows [container mode](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers).</span></span> <span data-ttu-id="835c7-180">La imagen base del ejemplo es la imagen 2.0-sdk del repositorio microsoft/dotnet.</span><span class="sxs-lookup"><span data-stu-id="835c7-180">The Base Image for our sample is the 2.0-sdk image from the microsoft/dotnet repository,</span></span>

```Dockerfile
FROM microsoft/dotnet:2.0-sdk
```

<span data-ttu-id="835c7-181">La instrucción [**WORKDIR**](https://docs.docker.com/engine/reference/builder/#workdir) establece el directorio de trabajo de cualquier instrucción RUN, CMD, ENTRYPOINT, COPY y ADD Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="835c7-181">The [**WORKDIR**](https://docs.docker.com/engine/reference/builder/#workdir) instruction sets the working directory for any remaining RUN, CMD, ENTRYPOINT, COPY, and ADD Dockerfile instructions.</span></span> <span data-ttu-id="835c7-182">Si el directorio no existe, se crea.</span><span class="sxs-lookup"><span data-stu-id="835c7-182">If the directory doesn't exist, it's created.</span></span> <span data-ttu-id="835c7-183">En este caso, WORKDIR se establece en el directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="835c7-183">In this case, WORKDIR is set to the app directory.</span></span>

```Dockerfile
WORKDIR /app
```

<span data-ttu-id="835c7-184">La instrucción [**COPY**](https://docs.docker.com/engine/reference/builder/#copy) copia nuevos archivos o directorios de la ruta de acceso de origen y los agrega al sistema de archivos del contenedor de destino.</span><span class="sxs-lookup"><span data-stu-id="835c7-184">The [**COPY**](https://docs.docker.com/engine/reference/builder/#copy) instruction copies new files or directories from the source path and adds them to the destination container filesystem.</span></span> <span data-ttu-id="835c7-185">Con esta instrucción, se copia el archivo de proyecto de C# en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="835c7-185">With this instruction, we are copying the C# project file to the container.</span></span>

```Dockerfile
COPY *.csproj ./
```

<span data-ttu-id="835c7-186">La instrucción [**RUN**](https://docs.docker.com/engine/reference/builder/#run) ejecuta los comandos en una nueva capa sobre la imagen actual y confirma los resultados.</span><span class="sxs-lookup"><span data-stu-id="835c7-186">The [**RUN**](https://docs.docker.com/engine/reference/builder/#run) instruction executes any commands in a new layer on top of the current image and commit the results.</span></span> <span data-ttu-id="835c7-187">La imagen resultante confirmada se usa para el siguiente paso en el Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="835c7-187">The resulting committed image is used for the next step in the Dockerfile.</span></span> <span data-ttu-id="835c7-188">Se está ejecutando **dotnet restore** para obtener las dependencias necesarias del archivo de proyecto de C#.</span><span class="sxs-lookup"><span data-stu-id="835c7-188">We are running **dotnet restore** to get the needed dependencies of the C# project file.</span></span> 

```Dockerfile
RUN dotnet restore
```

<span data-ttu-id="835c7-189">Esta instrucción **COPY** copia el resto de los archivos en el contenedor en nuevas [capas](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers).</span><span class="sxs-lookup"><span data-stu-id="835c7-189">This **COPY** instruction copies the rest of the files into our container into new [layers](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers).</span></span>

```Dockerfile
COPY . ./
```

<span data-ttu-id="835c7-190">Se está publicando la aplicación con esta instrucción **RUN**.</span><span class="sxs-lookup"><span data-stu-id="835c7-190">We are publishing the app with this **RUN** instruction.</span></span> <span data-ttu-id="835c7-191">El comando [**dotnet publish**](../tools/dotnet-publish.md) compila la aplicación, lee sus dependencias especificadas en el archivo de proyecto y publica el conjunto resultante de archivos en un directorio.</span><span class="sxs-lookup"><span data-stu-id="835c7-191">The [**dotnet publish**](../tools/dotnet-publish.md) command compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="835c7-192">La aplicación se publica con una configuración de **versión** y se escribe en el directorio predeterminado.</span><span class="sxs-lookup"><span data-stu-id="835c7-192">Our app is published with a **Release** configuration and output to the default directory.</span></span>

```Dockerfile
RUN dotnet publish -c Release -o out
```

<span data-ttu-id="835c7-193">La instrucción [**ENTRYPOINT**](https://docs.docker.com/engine/reference/builder/#entrypoint) permite al contenedor ejecutarse como un archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="835c7-193">The [**ENTRYPOINT**](https://docs.docker.com/engine/reference/builder/#entrypoint) instruction allows the container to run as an executable.</span></span>

```Dockerfile
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

<span data-ttu-id="835c7-194">Ya tiene un Dockerfile que:</span><span class="sxs-lookup"><span data-stu-id="835c7-194">Now you have a Dockerfile that:</span></span>

* <span data-ttu-id="835c7-195">copia la aplicación en la imagen</span><span class="sxs-lookup"><span data-stu-id="835c7-195">copies your app to the image</span></span>
* <span data-ttu-id="835c7-196">copia las dependencias de la aplicación en la imagen</span><span class="sxs-lookup"><span data-stu-id="835c7-196">your app's dependencies to the image</span></span>
* <span data-ttu-id="835c7-197">compila la aplicación para que se ejecute como un archivo ejecutable</span><span class="sxs-lookup"><span data-stu-id="835c7-197">builds the app to run as an executable</span></span>

### <a name="build-and-run-the-hello-net-core-20-app"></a><span data-ttu-id="835c7-198">Compilar y ejecutar la aplicación Hello de .NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="835c7-198">Build and run the Hello .NET Core 2.0 app</span></span>

#### <a name="essential-docker-commands"></a><span data-ttu-id="835c7-199">Comandos de Docker esenciales</span><span class="sxs-lookup"><span data-stu-id="835c7-199">Essential Docker commands</span></span>

<span data-ttu-id="835c7-200">Estos comandos de Docker son esenciales:</span><span class="sxs-lookup"><span data-stu-id="835c7-200">These Docker commands are essential:</span></span>

* [<span data-ttu-id="835c7-201">docker build</span><span class="sxs-lookup"><span data-stu-id="835c7-201">docker build</span></span>](https://docs.docker.com/engine/reference/commandline/build/)
* [<span data-ttu-id="835c7-202">docker run</span><span class="sxs-lookup"><span data-stu-id="835c7-202">docker run</span></span>](https://docs.docker.com/engine/reference/commandline/run/)
* [<span data-ttu-id="835c7-203">docker ps</span><span class="sxs-lookup"><span data-stu-id="835c7-203">docker ps</span></span>](https://docs.docker.com/engine/reference/commandline/ps/)
* [<span data-ttu-id="835c7-204">docker stop</span><span class="sxs-lookup"><span data-stu-id="835c7-204">docker stop</span></span>](https://docs.docker.com/engine/reference/commandline/stop/)
* [<span data-ttu-id="835c7-205">docker rm</span><span class="sxs-lookup"><span data-stu-id="835c7-205">docker rm</span></span>](https://docs.docker.com/engine/reference/commandline/rm/)
* [<span data-ttu-id="835c7-206">docker rmi</span><span class="sxs-lookup"><span data-stu-id="835c7-206">docker rmi</span></span>](https://docs.docker.com/engine/reference/commandline/rmi/)
* [<span data-ttu-id="835c7-207">docker image</span><span class="sxs-lookup"><span data-stu-id="835c7-207">docker image</span></span>](https://docs.docker.com/engine/reference/commandline/image/)

#### <a name="build-and-run"></a><span data-ttu-id="835c7-208">Compilar y ejecutar</span><span class="sxs-lookup"><span data-stu-id="835c7-208">Build and run</span></span>

<span data-ttu-id="835c7-209">Ha escrito el Dockerfile; ahora Docker compila la aplicación y luego ejecuta el contenedor.</span><span class="sxs-lookup"><span data-stu-id="835c7-209">You wrote the dockerfile; now Docker builds your app and then runs the container.</span></span>

```console
docker build -t dotnetapp-dev .
docker run --rm dotnetapp-dev Hello from Docker
```

<span data-ttu-id="835c7-210">La salida del comando `docker build` debe ser similar a la siguiente salida de consola:</span><span class="sxs-lookup"><span data-stu-id="835c7-210">The output from the `docker build` command should be similar to the following console output:</span></span>

```console
Sending build context to Docker daemon   72.7kB
Step 1/7 : FROM microsoft/dotnet:2.0-sdk
 ---> d84f64b126a6
Step 2/7 : WORKDIR /app
 ---> Using cache
 ---> 9af1fbdc7972
Step 3/7 : COPY *.csproj ./
 ---> Using cache
 ---> 86c8c332d4b3
Step 4/7 : RUN dotnet restore
 ---> Using cache
 ---> 86fcd7dd0ea4
Step 5/7 : COPY . ./
 ---> Using cache
 ---> 6faf0a53607f
Step 6/7 : RUN dotnet publish -c Release -o out
 ---> Using cache
 ---> f972328318c8
Step 7/7 : ENTRYPOINT dotnet out/Hello.dll
 ---> Using cache
 ---> 53c337887e18
Successfully built 53c337887e18
Successfully tagged dotnetapp-dev:latest
```

<span data-ttu-id="835c7-211">Como puede ver en la salida, el motor de Docker ha usado el Dockerfile para compilar el contenedor.</span><span class="sxs-lookup"><span data-stu-id="835c7-211">As you can see from the output, the Docker Engine used the Dockerfile to build our container.</span></span>

<span data-ttu-id="835c7-212">La salida del comando `docker run` debe ser similar a la siguiente salida de consola:</span><span class="sxs-lookup"><span data-stu-id="835c7-212">The output from the `docker run` command should be similar to the following console output:</span></span>

```console
Hello World!
```

<span data-ttu-id="835c7-213">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="835c7-213">Congratulations!</span></span> <span data-ttu-id="835c7-214">Acaba de:</span><span class="sxs-lookup"><span data-stu-id="835c7-214">you have just:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="835c7-215">Crear una aplicación .NET Core local</span><span class="sxs-lookup"><span data-stu-id="835c7-215">Created a local .NET Core app</span></span>
> * <span data-ttu-id="835c7-216">Crear un Dockerfile para compilar el primer contenedor</span><span class="sxs-lookup"><span data-stu-id="835c7-216">Created a Dockerfile to build your first container</span></span>
> * <span data-ttu-id="835c7-217">Compilar y ejecutar la aplicación a la que se ha aplicado Docker</span><span class="sxs-lookup"><span data-stu-id="835c7-217">Built and ran your Dockerized app</span></span>



## <a name="next-steps"></a><span data-ttu-id="835c7-218">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="835c7-218">Next Steps</span></span>

<span data-ttu-id="835c7-219">Estos son algunos de los pasos que puede realizar a continuación:</span><span class="sxs-lookup"><span data-stu-id="835c7-219">Here are some next steps you can take:</span></span>

* [<span data-ttu-id="835c7-220">Introducción a vídeo e imágenes de .NET Docker</span><span class="sxs-lookup"><span data-stu-id="835c7-220">Introduction to .NET Docker Images Video</span></span>](https://channel9.msdn.com/Shows/Code-Conversations/Introduction-to-NET-Docker-Images-with-Kendra-Havens?term=docker)
* [<span data-ttu-id="835c7-221">Instancias de Visual Studio, Docker y Azure Container juntas</span><span class="sxs-lookup"><span data-stu-id="835c7-221">Visual Studio, Docker & Azure Container Instances better together!</span></span>](https://blogs.msdn.microsoft.com/alimaz/2017/08/17/visual-studio-docker-azure-container-instances-better-together/)
* [<span data-ttu-id="835c7-222">Docker para tutoriales rápidos de Azure</span><span class="sxs-lookup"><span data-stu-id="835c7-222">Docker for Azure Quickstarts</span></span>](https://docs.docker.com/docker-for-azure/#docker-community-edition-ce-for-azure)
* [<span data-ttu-id="835c7-223">Implementar la aplicación en Docker para Azure</span><span class="sxs-lookup"><span data-stu-id="835c7-223">Deploy your app on Docker for Azure</span></span>](https://docs.docker.com/docker-for-azure/deploy/)

> [!Note]
> <span data-ttu-id="835c7-224">Si no tiene una suscripción de Azure, [regístrese hoy](https://azure.microsoft.com/free/?b=16.48) para obtener una cuenta gratuita durante 30 días y obtenga 200 dólares en créditos de Azure para probar cualquier combinación de servicios de Azure.</span><span class="sxs-lookup"><span data-stu-id="835c7-224">If you do not have an Azure subscription, [sign up today](https://azure.microsoft.com/free/?b=16.48) for a free 30-day account and get $200 in Azure Credits to try out any combination of Azure services.</span></span>

## <a name="docker-images-used-in-this-sample"></a><span data-ttu-id="835c7-225">Imágenes de Docker usadas en este ejemplo</span><span class="sxs-lookup"><span data-stu-id="835c7-225">Docker Images used in this sample</span></span>

<span data-ttu-id="835c7-226">En este ejemplo se usan las siguientes imágenes de Docker</span><span class="sxs-lookup"><span data-stu-id="835c7-226">The following Docker images are used in this sample</span></span>

* [`microsoft/dotnet:2.0-sdk`](https://hub.docker.com/r/microsoft/dotnet)

## <a name="related-resources"></a><span data-ttu-id="835c7-227">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="835c7-227">Related Resources</span></span>

* [<span data-ttu-id="835c7-228">Ejemplos de .NET Core Docker</span><span class="sxs-lookup"><span data-stu-id="835c7-228">.NET Core Docker samples</span></span>](https://github.com/dotnet/dotnet-docker-samples/README.md)
* [<span data-ttu-id="835c7-229">Dockerfile en contenedores de Windows</span><span class="sxs-lookup"><span data-stu-id="835c7-229">Dockerfile on Windows Containers</span></span>](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [<span data-ttu-id="835c7-230">Ejemplos de .NET Framework Docker</span><span class="sxs-lookup"><span data-stu-id="835c7-230">.NET Framework Docker samples</span></span>](https://github.com/Microsoft/dotnet-framework-docker-samples)
* [<span data-ttu-id="835c7-231">ASP.NET Core en DockerHub</span><span class="sxs-lookup"><span data-stu-id="835c7-231">ASP.NET Core on DockerHub</span></span>](https://hub.docker.com/r/microsoft/aspnetcore/)
* [<span data-ttu-id="835c7-232">Aplicar Docker a una aplicación .NET Core: Tutorial de Docker</span><span class="sxs-lookup"><span data-stu-id="835c7-232">Dockerize a .NET Core application - Docker Tutorial</span></span>](https://docs.docker.com/engine/examples/dotnetcore/)
* <span data-ttu-id="835c7-233">[Working with Visual Studio Docker Tools](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker) (Trabajo con Visual Studio Docker Tools)</span><span class="sxs-lookup"><span data-stu-id="835c7-233">[Working with Visual Studio Docker Tools](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)</span></span>
* <span data-ttu-id="835c7-234">[Deploying Docker Images from the Azure Container Registry to Azure Container Instances](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/) (Implementación de imágenes de Docker desde Azure Container Registry a Azure Container Instances)</span><span class="sxs-lookup"><span data-stu-id="835c7-234">[Deploying Docker Images from the Azure Container Registry to Azure Container Instances](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)</span></span>