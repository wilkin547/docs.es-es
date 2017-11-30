---
title: "Obtenga información acerca de los aspectos básicos de Docker con .NET Core"
description: "Un Docker y el Tutorial básico de .NET Core"
keywords: . NET, .NET core, Docker, Tutorial
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.topic: tutorial
ms.prod: .net-core
ms.technology: dotnet-docker
ms.devlang: dotnet
ms.assetid: 03c28597-7e73-46d6-a9c3-f9cb55642739
ms.custom: mvc
manager: wpickett
ms.openlocfilehash: 5935f67d7e4ca9c9e8768373e2bcaa9febccfdc5
ms.sourcegitcommit: 5fb6646b5ee3769ffb214e672041833ea4ceeb26
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2017
---
# <a name="learn-docker-basics-with-net-core"></a><span data-ttu-id="36f1c-104">Obtenga información acerca de los aspectos básicos de Docker con .NET Core</span><span class="sxs-lookup"><span data-stu-id="36f1c-104">Learn Docker Basics with .NET Core</span></span>

<span data-ttu-id="36f1c-105">Este tutorial enseña el contenedor compilar e implementar tareas para una aplicación de .NET Core de Docker.</span><span class="sxs-lookup"><span data-stu-id="36f1c-105">This tutorial teaches the Docker container build and deploy tasks for a .NET Core application.</span></span> <span data-ttu-id="36f1c-106">En el transcurso de este tutorial, aprenderá:</span><span class="sxs-lookup"><span data-stu-id="36f1c-106">During the course of this tutorial, you learn:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="36f1c-107">Cómo crear un archivo Dockerfile</span><span class="sxs-lookup"><span data-stu-id="36f1c-107">How to create a Dockerfile</span></span>
> * <span data-ttu-id="36f1c-108">Cómo crear una aplicación de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="36f1c-108">How to create a .NET Core app.</span></span>
> * <span data-ttu-id="36f1c-109">Cómo implementar la aplicación en un contenedor de Docker.</span><span class="sxs-lookup"><span data-stu-id="36f1c-109">How to deploy your app into a Docker container.</span></span>

<span data-ttu-id="36f1c-110">El [plataforma Docker](https://docs.docker.com/engine/docker-overview/#the-docker-platform) utiliza la [motor de Docker](https://docs.docker.com/engine/docker-overview/#docker-engine) para generar y empaquetar aplicaciones como rápidamente [imágenes de Docker](https://docs.docker.com/glossary/?term=image).</span><span class="sxs-lookup"><span data-stu-id="36f1c-110">The [Docker platform](https://docs.docker.com/engine/docker-overview/#the-docker-platform) uses the [Docker Engine](https://docs.docker.com/engine/docker-overview/#docker-engine) to quickly build and package apps as [Docker images](https://docs.docker.com/glossary/?term=image).</span></span> <span data-ttu-id="36f1c-111">Estas imágenes se escriben el [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) formato para implementar y ejecutar un [superpuesto contenedor](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).</span><span class="sxs-lookup"><span data-stu-id="36f1c-111">These images are written in the [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) format to be deployed and run in a [layered container](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).</span></span>

## <a name="net-core-easiest-way-to-get-started"></a><span data-ttu-id="36f1c-112">.NET core: De manera más fácil para empezar a trabajar</span><span class="sxs-lookup"><span data-stu-id="36f1c-112">.NET Core: Easiest way to get started</span></span>

<span data-ttu-id="36f1c-113">Antes de crear la imagen de Docker, se necesita una aplicación que incluya.</span><span class="sxs-lookup"><span data-stu-id="36f1c-113">Before creating the Docker image, you need an application to containerize.</span></span> <span data-ttu-id="36f1c-114">Puede crearla en Linux, Mac OS o Windows.</span><span class="sxs-lookup"><span data-stu-id="36f1c-114">You can create it on Linux, MacOS, or Windows.</span></span> <span data-ttu-id="36f1c-115">La forma más rápida y sencilla de hacerlo es usar .NET Core.</span><span class="sxs-lookup"><span data-stu-id="36f1c-115">The quickest and easiest way to do that is to use .NET Core.</span></span>

<span data-ttu-id="36f1c-116">Si no está familiarizado con el conjunto de herramientas de la CLI de .NET Core, vea la [información general del SDK de .NET Core](../tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="36f1c-116">If you're unfamiliar with the .NET Core CLI toolset, read the [.NET Core SDK overview](../tools/index.md).</span></span>

<span data-ttu-id="36f1c-117">Puede crear contenedores de Windows y Linux con [arch múltiples según etiquetas](https://github.com/dotnet/announcements/issues/14).</span><span class="sxs-lookup"><span data-stu-id="36f1c-117">You can build both Windows and Linux containers with [multi-arch based tags](https://github.com/dotnet/announcements/issues/14).</span></span>

## <a name="your-first-net-core-docker-app"></a><span data-ttu-id="36f1c-118">La primera aplicación de .NET Core Docker</span><span class="sxs-lookup"><span data-stu-id="36f1c-118">Your first .NET Core Docker app</span></span>

### <a name="prerequisites"></a><span data-ttu-id="36f1c-119">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="36f1c-119">Prerequisites</span></span>

<span data-ttu-id="36f1c-120">Para completar este tutorial:</span><span class="sxs-lookup"><span data-stu-id="36f1c-120">To complete this tutorial:</span></span>

#### <a name="net-core-20-sdk"></a><span data-ttu-id="36f1c-121">.NET core SDK 2.0</span><span class="sxs-lookup"><span data-stu-id="36f1c-121">.NET Core 2.0 SDK</span></span>

* <span data-ttu-id="36f1c-122">Instalar [.NET Core SDK 2.0](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="36f1c-122">Install [.NET Core SDK 2.0](https://www.microsoft.com/net/core).</span></span>

<span data-ttu-id="36f1c-123">Vea [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) (.NET Core 2.x: versiones de SO compatibles) para obtener una lista completa de sistemas operativos compatibles con .NET Core 2.x, fuera de las versiones de sistema operativo compatibles y los vínculos de directiva de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="36f1c-123">See [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) for the complete list of .NET Core 2.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

* <span data-ttu-id="36f1c-124">Instale al editor de código favoritos, si no lo ha hecho ya.</span><span class="sxs-lookup"><span data-stu-id="36f1c-124">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="36f1c-125">¿Es necesario instalar a un editor de código?</span><span class="sxs-lookup"><span data-stu-id="36f1c-125">Need to install a code editor?</span></span> <span data-ttu-id="36f1c-126">Intente [Visual Studio](https://visualstudio.com/downloads)!</span><span class="sxs-lookup"><span data-stu-id="36f1c-126">Try [Visual Studio](https://visualstudio.com/downloads)!</span></span>

#### <a name="installing-docker-client"></a><span data-ttu-id="36f1c-127">Instalación de cliente de Docker</span><span class="sxs-lookup"><span data-stu-id="36f1c-127">Installing Docker Client</span></span>

<span data-ttu-id="36f1c-128">Instalar [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) u otra posterior del cliente.</span><span class="sxs-lookup"><span data-stu-id="36f1c-128">Install [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) or later of the Docker client.</span></span>

<span data-ttu-id="36f1c-129">El cliente se puede instalar en:</span><span class="sxs-lookup"><span data-stu-id="36f1c-129">The Docker client can be installed in:</span></span>

* <span data-ttu-id="36f1c-130">Distribuciones de Linux</span><span class="sxs-lookup"><span data-stu-id="36f1c-130">Linux distributions</span></span>

   * [<span data-ttu-id="36f1c-131">CentOS</span><span class="sxs-lookup"><span data-stu-id="36f1c-131">CentOS</span></span>](https://www.docker.com/docker-centos-distribution)

   * [<span data-ttu-id="36f1c-132">Debian</span><span class="sxs-lookup"><span data-stu-id="36f1c-132">Debian</span></span>](https://www.docker.com/docker-debian)

   * [<span data-ttu-id="36f1c-133">Fedora</span><span class="sxs-lookup"><span data-stu-id="36f1c-133">Fedora</span></span>](https://www.docker.com/docker-fedora)

   * [<span data-ttu-id="36f1c-134">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="36f1c-134">Ubuntu</span></span>](https://www.docker.com/docker-ubuntu)

* [<span data-ttu-id="36f1c-135">macOS</span><span class="sxs-lookup"><span data-stu-id="36f1c-135">macOS</span></span>](https://docs.docker.com/docker-for-mac/)

* <span data-ttu-id="36f1c-136">[Windows](https://docs.docker.com/docker-for-windows/).</span><span class="sxs-lookup"><span data-stu-id="36f1c-136">[Windows](https://docs.docker.com/docker-for-windows/).</span></span>

### <a name="create-a-net-core-20-console-app-for-dockerization"></a><span data-ttu-id="36f1c-137">Crear una aplicación de consola .NET Core 2.0 para Dockerization</span><span class="sxs-lookup"><span data-stu-id="36f1c-137">Create a .NET Core 2.0 console app for Dockerization</span></span>

<span data-ttu-id="36f1c-138">Abra un símbolo del sistema y cree una carpeta denominada *Hello*.</span><span class="sxs-lookup"><span data-stu-id="36f1c-138">Open a command prompt and create a folder named *Hello*.</span></span> <span data-ttu-id="36f1c-139">Navegue hasta la carpeta que creó y escriba los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="36f1c-139">Navigate to the folder you created and type the following commands:</span></span>

```console
dotnet new console
dotnet run
```

<span data-ttu-id="36f1c-140">Veamos un tutorial rápido:</span><span class="sxs-lookup"><span data-stu-id="36f1c-140">Let's do a quick walkthrough:</span></span>

1. `$ dotnet new console`

   <span data-ttu-id="36f1c-141">[`dotnet new`](../tools/dotnet-new.md) crea un archivo de proyecto `Hello.csproj` actualizado con las dependencias necesarias para compilar una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="36f1c-141">[`dotnet new`](../tools/dotnet-new.md) creates an up-to-date `Hello.csproj` project file with the dependencies necessary to build a console app.</span></span>  <span data-ttu-id="36f1c-142">Además, se crea un archivo `Program.cs`, un archivo básico que contiene el punto de entrada para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="36f1c-142">It also creates a `Program.cs`, a basic file containing the entry point for the application.</span></span>
   
   <span data-ttu-id="36f1c-143">`Hello.csproj`:</span><span class="sxs-lookup"><span data-stu-id="36f1c-143">`Hello.csproj`:</span></span>

   <span data-ttu-id="36f1c-144">El archivo de proyecto especifica todo lo que es necesario para restaurar las dependencias y compilar el programa.</span><span class="sxs-lookup"><span data-stu-id="36f1c-144">The project file specifies everything that's needed to restore dependencies and build the program.</span></span>

   * <span data-ttu-id="36f1c-145">La etiqueta `OutputType` especifica que estamos creando un archivo ejecutable, es decir, una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="36f1c-145">The `OutputType` tag specifies that we're building an executable, in other words a console application.</span></span>
   * <span data-ttu-id="36f1c-146">La etiqueta `TargetFramework` especifica la implementación .NET a la que nos dirigimos.</span><span class="sxs-lookup"><span data-stu-id="36f1c-146">The `TargetFramework` tag specifies what .NET implementation we're targeting.</span></span> <span data-ttu-id="36f1c-147">En un escenario más avanzado, puede especificar varios marcos de trabajo de destino y la compilación en los marcos de trabajo especificados en una sola operación.</span><span class="sxs-lookup"><span data-stu-id="36f1c-147">In an advanced scenario, you can specify multiple target frameworks and build to the specified frameworks in a single operation.</span></span> <span data-ttu-id="36f1c-148">En este tutorial, se compila para .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="36f1c-148">In this tutorial, we build for .NET Core 2.0.</span></span>

   <span data-ttu-id="36f1c-149">`Program.cs`:</span><span class="sxs-lookup"><span data-stu-id="36f1c-149">`Program.cs`:</span></span>

   <span data-ttu-id="36f1c-150">Inicia el programa por `using System`.</span><span class="sxs-lookup"><span data-stu-id="36f1c-150">The program starts by `using System`.</span></span> <span data-ttu-id="36f1c-151">Esta instrucción significa, "poner todo el `System` espacio de nombres en el ámbito de este archivo."</span><span class="sxs-lookup"><span data-stu-id="36f1c-151">This statement means, "Bring everything in the `System` namespace into scope for this file."</span></span> <span data-ttu-id="36f1c-152">El espacio de nombres `System` incluye construcciones básicas, como `string` o tipos numéricos.</span><span class="sxs-lookup"><span data-stu-id="36f1c-152">The `System` namespace includes basic constructs such as `string`, or numeric types.</span></span>

   <span data-ttu-id="36f1c-153">Después, definimos un espacio de nombres denominado `Hello`.</span><span class="sxs-lookup"><span data-stu-id="36f1c-153">We then define a namespace called `Hello`.</span></span> <span data-ttu-id="36f1c-154">Puede cambiar el espacio de nombres para el que desee.</span><span class="sxs-lookup"><span data-stu-id="36f1c-154">You can change namespace to anything you want.</span></span> <span data-ttu-id="36f1c-155">Se define una clase denominada `Program` dentro del espacio de nombres, con un método `Main` que toma una matriz de cadenas como argumento.</span><span class="sxs-lookup"><span data-stu-id="36f1c-155">A class named `Program` is defined within that namespace, with a `Main` method that takes an array of strings as its argument.</span></span> <span data-ttu-id="36f1c-156">Esta matriz contiene la lista de argumentos que se ha pasado cuando se llama al programa compilado.</span><span class="sxs-lookup"><span data-stu-id="36f1c-156">This array contains the list of arguments passed in when the compiled program is called.</span></span> <span data-ttu-id="36f1c-157">En nuestro ejemplo, el programa escribe sólo "¡Hello World!"</span><span class="sxs-lookup"><span data-stu-id="36f1c-157">In our example, the program only writes "Hello World!"</span></span> <span data-ttu-id="36f1c-158">en la consola.</span><span class="sxs-lookup"><span data-stu-id="36f1c-158">to the console.</span></span>

2. `$ dotnet restore`

   <span data-ttu-id="36f1c-159">En .NET Core 2.x, **dotnet nueva** se ejecuta la [ `dotnet restore` ](../tools/dotnet-restore.md) comando.</span><span class="sxs-lookup"><span data-stu-id="36f1c-159">In .NET Core 2.x, **dotnet new** runs the [`dotnet restore`](../tools/dotnet-restore.md) command.</span></span> <span data-ttu-id="36f1c-160">**Restauración de dotnet** restaura el árbol de dependencias con un [NuGet](https://www.nuget.org/)llamada (Administrador de paquetes. NET).</span><span class="sxs-lookup"><span data-stu-id="36f1c-160">**Dotnet restore** restores the tree of dependencies with a [NuGet](https://www.nuget.org/)(.NET package manager) call.</span></span>
   <span data-ttu-id="36f1c-161">NuGet lleva a cabo las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="36f1c-161">NuGet performs the following tasks:</span></span>
   * <span data-ttu-id="36f1c-162">analiza la *Hello.csproj* archivo</span><span class="sxs-lookup"><span data-stu-id="36f1c-162">analyzes the *Hello.csproj* file</span></span> 
   * <span data-ttu-id="36f1c-163">descarga el archivo de dependencias (o grabs desde la caché del equipo)</span><span class="sxs-lookup"><span data-stu-id="36f1c-163">downloads the file dependencies (or grabs from your machine cache)</span></span>
   * <span data-ttu-id="36f1c-164">Escribe el *obj/project.assets.json* archivo</span><span class="sxs-lookup"><span data-stu-id="36f1c-164">writes the *obj/project.assets.json* file</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
   
   <span data-ttu-id="36f1c-165">El *project.assets.json* archivo es un conjunto completo del gráfico de dependencias de NuGet, resoluciones de enlace y otros metadatos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="36f1c-165">The *project.assets.json* file is a complete set of the NuGet dependencies graph, binding resolutions, and other app metadata.</span></span> <span data-ttu-id="36f1c-166">Esto requiere el archivo se usa con otras herramientas, como [ `dotnet build` ](../tools/dotnet-build.md) y [ `dotnet run` ](../tools/dotnet-run.md), para que procese correctamente el código fuente.</span><span class="sxs-lookup"><span data-stu-id="36f1c-166">This required file is used by other tools, such as [`dotnet build`](../tools/dotnet-build.md) and [`dotnet run`](../tools/dotnet-run.md), to correctly process the source code.</span></span>
   
3. `$ dotnet run`

   <span data-ttu-id="36f1c-167">[`dotnet run`](../tools/dotnet-run.md)llamadas [ `dotnet build` ](../tools/dotnet-build.md) para confirmar una compilación correcta y, a continuación, llama `dotnet <assembly.dll>` para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="36f1c-167">[`dotnet run`](../tools/dotnet-run.md) calls [`dotnet build`](../tools/dotnet-build.md) to confirm a successful build, and then calls `dotnet <assembly.dll>` to run the application.</span></span>
   
    ```console
    $ dotnet run
    
    Hello World!
    ```

    <span data-ttu-id="36f1c-168">Para escenarios avanzados, consulte [implementación de aplicaciones de .NET Core](../deploying/index.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="36f1c-168">For advanced scenarios,  see [.NET Core Application Deployment](../deploying/index.md) for details.</span></span>

## <a name="dockerize-the-net-core-application"></a><span data-ttu-id="36f1c-169">Dockerize la aplicación de .NET Core</span><span class="sxs-lookup"><span data-stu-id="36f1c-169">Dockerize the .NET Core application</span></span>

<span data-ttu-id="36f1c-170">La aplicación de consola de Hello .NET Core correctamente se ejecuta localmente.</span><span class="sxs-lookup"><span data-stu-id="36f1c-170">The Hello .NET Core console app successfully runs locally.</span></span> <span data-ttu-id="36f1c-171">Ahora vamos a dar un paso más y compilar y ejecutar la aplicación en Docker.</span><span class="sxs-lookup"><span data-stu-id="36f1c-171">Now let's take it a step further and build and run the app in Docker.</span></span>

### <a name="your-first-dockerfile"></a><span data-ttu-id="36f1c-172">El primer Dockerfile</span><span class="sxs-lookup"><span data-stu-id="36f1c-172">Your first Dockerfile</span></span>

<span data-ttu-id="36f1c-173">¡Abra el editor de texto y Comencemos!</span><span class="sxs-lookup"><span data-stu-id="36f1c-173">Open your text editor and let's get started!</span></span> <span data-ttu-id="36f1c-174">Todavía estamos trabajando desde el directorio de Hello en que creamos la aplicación.</span><span class="sxs-lookup"><span data-stu-id="36f1c-174">We're still working from the Hello directory we built the app in.</span></span>

<span data-ttu-id="36f1c-175">Agregue las siguientes instrucciones de Docker para cualquier Linux o [contenedores de Windows](https://docs.microsoft.com/virtualization/windowscontainers/about/) en un archivo nuevo.</span><span class="sxs-lookup"><span data-stu-id="36f1c-175">Add the following Docker instructions for either Linux or [Windows Containers](https://docs.microsoft.com/virtualization/windowscontainers/about/) to a new file.</span></span> <span data-ttu-id="36f1c-176">Cuando termine, puede guardarlo en la raíz del directorio Hello como **Dockerfile**, sin extensión (puede que necesite establecer el tipo de archivo `All types (*.*)` o algo similar).</span><span class="sxs-lookup"><span data-stu-id="36f1c-176">When finished, save it in the root of your Hello directory as **Dockerfile**, with no extension (You may need to set your file type to `All types (*.*)` or something similar).</span></span>

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

<span data-ttu-id="36f1c-177">El Dockerfile contiene las instrucciones de compilación de Docker que se ejecutan secuencialmente.</span><span class="sxs-lookup"><span data-stu-id="36f1c-177">The Dockerfile contains Docker build instructions that run sequentially.</span></span>

<span data-ttu-id="36f1c-178">Debe ser la primera instrucción [ **FROM**](https://docs.docker.com/engine/reference/builder/#from).</span><span class="sxs-lookup"><span data-stu-id="36f1c-178">The first instruction must be [**FROM**](https://docs.docker.com/engine/reference/builder/#from).</span></span> <span data-ttu-id="36f1c-179">Esta instrucción Inicializa una nueva fase de compilación y establece la imagen Base para las instrucciones restantes.</span><span class="sxs-lookup"><span data-stu-id="36f1c-179">This instruction initializes a new build stage and sets the Base Image for the remaining instructions.</span></span> <span data-ttu-id="36f1c-180">Las etiquetas arch varios contenedores de Windows o Linux de extracción según la Docker para Windows [el modo de contenedor](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers).</span><span class="sxs-lookup"><span data-stu-id="36f1c-180">The multi-arch tags pull either Windows or Linux containers depending on the Docker for Windows [container mode](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers).</span></span> <span data-ttu-id="36f1c-181">La imagen Base para nuestro ejemplo es la 2.0 sdk desde el repositorio de microsoft/dotnet</span><span class="sxs-lookup"><span data-stu-id="36f1c-181">The Base Image for our sample is the 2.0-sdk image from the microsoft/dotnet repository,</span></span>

```Dockerfile
FROM microsoft/dotnet:2.0-sdk
```

<span data-ttu-id="36f1c-182">El [ **WORKDIR** ](https://docs.docker.com/engine/reference/builder/#workdir) instrucción establece el directorio de trabajo para cualquier ejecución, CMD, ENTRYPOINT, copiar y agregar Dockerfile restantes instrucciones.</span><span class="sxs-lookup"><span data-stu-id="36f1c-182">The [**WORKDIR**](https://docs.docker.com/engine/reference/builder/#workdir) instruction sets the working directory for any remaining RUN, CMD, ENTRYPOINT, COPY, and ADD Dockerfile instructions.</span></span> <span data-ttu-id="36f1c-183">Si el directorio no existe, se crea.</span><span class="sxs-lookup"><span data-stu-id="36f1c-183">If the directory doesn't exist, it's created.</span></span> <span data-ttu-id="36f1c-184">En este caso, WORKDIR se establece en el directorio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="36f1c-184">In this case, WORKDIR is set to the app directory.</span></span>

```Dockerfile
WORKDIR /app
```

<span data-ttu-id="36f1c-185">El [ **copia** ](https://docs.docker.com/engine/reference/builder/#copy) instrucción copia nuevos archivos o directorios de la ruta de acceso de origen y los agrega al sistema de archivos del contenedor de destino.</span><span class="sxs-lookup"><span data-stu-id="36f1c-185">The [**COPY**](https://docs.docker.com/engine/reference/builder/#copy) instruction copies new files or directories from the source path and adds them to the destination container filesystem.</span></span> <span data-ttu-id="36f1c-186">Con esta instrucción, que estamos copiando el archivo de proyecto de C# para el contenedor.</span><span class="sxs-lookup"><span data-stu-id="36f1c-186">With this instruction, we are copying the C# project file to the container.</span></span>

```Dockerfile
COPY *.csproj ./
```

<span data-ttu-id="36f1c-187">El [ **ejecutar** ](https://docs.docker.com/engine/reference/builder/#run) instrucción ejecuta los comandos en una nueva capa encima de la imagen actual y confirmar los resultados.</span><span class="sxs-lookup"><span data-stu-id="36f1c-187">The [**RUN**](https://docs.docker.com/engine/reference/builder/#run) instruction executes any commands in a new layer on top of the current image and commit the results.</span></span> <span data-ttu-id="36f1c-188">La imagen resultante confirmada se usa para el siguiente paso en el Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="36f1c-188">The resulting committed image is used for the next step in the Dockerfile.</span></span> <span data-ttu-id="36f1c-189">Se está ejecutando **dotnet restauración** para obtener las dependencias necesarias del archivo de proyecto de C#.</span><span class="sxs-lookup"><span data-stu-id="36f1c-189">We are running **dotnet restore** to get the needed dependencies of the C# project file.</span></span> 

```Dockerfile
RUN dotnet restore
```

<span data-ttu-id="36f1c-190">Esto **copia** instrucción copia el resto de los archivos en el contenedor en nuevos [capas](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers).</span><span class="sxs-lookup"><span data-stu-id="36f1c-190">This **COPY** instruction copies the rest of the files into our container into new [layers](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers).</span></span>

```Dockerfile
COPY . ./
```

<span data-ttu-id="36f1c-191">Estamos publicando la aplicación con esta **ejecutar** instrucción.</span><span class="sxs-lookup"><span data-stu-id="36f1c-191">We are publishing the app with this **RUN** instruction.</span></span> <span data-ttu-id="36f1c-192">El [ **publicar dotnet** ](../tools/dotnet-publish.md) comando compila la aplicación, lee a través de sus dependencias especificados en el archivo de proyecto y publica el conjunto resultante de archivos en un directorio.</span><span class="sxs-lookup"><span data-stu-id="36f1c-192">The [**dotnet publish**](../tools/dotnet-publish.md) command compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="36f1c-193">Nuestra aplicación se publica con un **versión** configuración y se escribe en el directorio predeterminado.</span><span class="sxs-lookup"><span data-stu-id="36f1c-193">Our app is published with a **Release** configuration and output to the default directory.</span></span>

```Dockerfile
RUN dotnet publish -c Release -o out
```

<span data-ttu-id="36f1c-194">El [ **ENTRYPOINT** ](https://docs.docker.com/engine/reference/builder/#entrypoint) instrucción permite al contenedor para que se ejecute como un ejecutable.</span><span class="sxs-lookup"><span data-stu-id="36f1c-194">The [**ENTRYPOINT**](https://docs.docker.com/engine/reference/builder/#entrypoint) instruction allows the container to run as an executable.</span></span>

```Dockerfile
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

<span data-ttu-id="36f1c-195">Ahora ya tiene un archivo Dockerfile que:</span><span class="sxs-lookup"><span data-stu-id="36f1c-195">Now you have a Dockerfile that:</span></span>

* <span data-ttu-id="36f1c-196">copia la aplicación a la imagen</span><span class="sxs-lookup"><span data-stu-id="36f1c-196">copies your app to the image</span></span>
* <span data-ttu-id="36f1c-197">dependencias de la aplicación a la imagen</span><span class="sxs-lookup"><span data-stu-id="36f1c-197">your app's dependencies to the image</span></span>
* <span data-ttu-id="36f1c-198">compila la aplicación para que se ejecute como un ejecutable</span><span class="sxs-lookup"><span data-stu-id="36f1c-198">builds the app to run as an executable</span></span>

### <a name="build-and-run-the-hello-net-core-20-app"></a><span data-ttu-id="36f1c-199">Compilar y ejecutar la aplicación Hello .NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="36f1c-199">Build and run the Hello .NET Core 2.0 app</span></span>

#### <a name="essential-docker-commands"></a><span data-ttu-id="36f1c-200">Comandos de Docker esenciales</span><span class="sxs-lookup"><span data-stu-id="36f1c-200">Essential Docker commands</span></span>

<span data-ttu-id="36f1c-201">Estos comandos de Docker son esenciales:</span><span class="sxs-lookup"><span data-stu-id="36f1c-201">These Docker commands are essential:</span></span>

* [<span data-ttu-id="36f1c-202">compilación de docker</span><span class="sxs-lookup"><span data-stu-id="36f1c-202">docker build</span></span>](https://docs.docker.com/engine/reference/commandline/build/)
* [<span data-ttu-id="36f1c-203">ejecución de docker</span><span class="sxs-lookup"><span data-stu-id="36f1c-203">docker run</span></span>](https://docs.docker.com/engine/reference/commandline/run/)
* [<span data-ttu-id="36f1c-204">docker ps</span><span class="sxs-lookup"><span data-stu-id="36f1c-204">docker ps</span></span>](https://docs.docker.com/engine/reference/commandline/ps/)
* [<span data-ttu-id="36f1c-205">detención de docker</span><span class="sxs-lookup"><span data-stu-id="36f1c-205">docker stop</span></span>](https://docs.docker.com/engine/reference/commandline/stop/)
* [<span data-ttu-id="36f1c-206">docker rm</span><span class="sxs-lookup"><span data-stu-id="36f1c-206">docker rm</span></span>](https://docs.docker.com/engine/reference/commandline/rm/)
* [<span data-ttu-id="36f1c-207">rmi docker</span><span class="sxs-lookup"><span data-stu-id="36f1c-207">docker rmi</span></span>](https://docs.docker.com/engine/reference/commandline/rmi/)
* [<span data-ttu-id="36f1c-208">imagen de docker</span><span class="sxs-lookup"><span data-stu-id="36f1c-208">docker image</span></span>](https://docs.docker.com/engine/reference/commandline/image/)

#### <a name="build-and-run"></a><span data-ttu-id="36f1c-209">Compilar y ejecutar</span><span class="sxs-lookup"><span data-stu-id="36f1c-209">Build and run</span></span>

<span data-ttu-id="36f1c-210">Escribió el dockerfile; Ahora Docker compila una aplicación y, a continuación, ejecuta el contenedor.</span><span class="sxs-lookup"><span data-stu-id="36f1c-210">You wrote the dockerfile; now Docker builds your app and then runs the container.</span></span>

```console
docker build -t dotnetapp-dev .
docker run --rm dotnetapp-dev Hello from Docker
```

<span data-ttu-id="36f1c-211">La salida de la `docker build` comando debe ser similar a la siguiente salida de consola:</span><span class="sxs-lookup"><span data-stu-id="36f1c-211">The output from the `docker build` command should be similar to the following console output:</span></span>

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

<span data-ttu-id="36f1c-212">Como puede ver en el resultado, el motor de Docker usan el Dockerfile para crear el contenedor.</span><span class="sxs-lookup"><span data-stu-id="36f1c-212">As you can see from the output, the Docker Engine used the Dockerfile to build our container.</span></span>

<span data-ttu-id="36f1c-213">La salida de la `docker run` comando debe ser similar a la siguiente salida de consola:</span><span class="sxs-lookup"><span data-stu-id="36f1c-213">The output from the `docker run` command should be similar to the following console output:</span></span>

```console
Hello World!
```

<span data-ttu-id="36f1c-214">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="36f1c-214">Congratulations!</span></span> <span data-ttu-id="36f1c-215">simplemente deberá:</span><span class="sxs-lookup"><span data-stu-id="36f1c-215">you have just:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="36f1c-216">Crea una aplicación de .NET Core local</span><span class="sxs-lookup"><span data-stu-id="36f1c-216">Created a local .NET Core app</span></span>
> * <span data-ttu-id="36f1c-217">Crea un archivo Dockerfile para crear el primer contenedor</span><span class="sxs-lookup"><span data-stu-id="36f1c-217">Created a Dockerfile to build your first container</span></span>
> * <span data-ttu-id="36f1c-218">Compila y se ejecutó la aplicación Dockerized</span><span class="sxs-lookup"><span data-stu-id="36f1c-218">Built and ran your Dockerized app</span></span>



## <a name="next-steps"></a><span data-ttu-id="36f1c-219">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="36f1c-219">Next Steps</span></span>

<span data-ttu-id="36f1c-220">Aquí le mostramos algunos procedimientos que puede realizar:</span><span class="sxs-lookup"><span data-stu-id="36f1c-220">Here are some next steps you can take:</span></span>

* [<span data-ttu-id="36f1c-221">Introducción a .NET Docker imágenes vídeo</span><span class="sxs-lookup"><span data-stu-id="36f1c-221">Introduction to .NET Docker Images Video</span></span>](https://channel9.msdn.com/Shows/Code-Conversations/Introduction-to-NET-Docker-Images-with-Kendra-Havens?term=docker)
* [<span data-ttu-id="36f1c-222">Visual Studio, Docker & instancias de contenedor de Azure mejor juntos.</span><span class="sxs-lookup"><span data-stu-id="36f1c-222">Visual Studio, Docker & Azure Container Instances better together!</span></span>](https://blogs.msdn.microsoft.com/alimaz/2017/08/17/visual-studio-docker-azure-container-instances-better-together/)
* [<span data-ttu-id="36f1c-223">Docker para tutoriales rápidos de Azure</span><span class="sxs-lookup"><span data-stu-id="36f1c-223">Docker for Azure Quickstarts</span></span>](https://docs.docker.com/docker-for-azure/#docker-community-edition-ce-for-azure)
* [<span data-ttu-id="36f1c-224">Implementar la aplicación en Docker de Azure</span><span class="sxs-lookup"><span data-stu-id="36f1c-224">Deploy your app on Docker for Azure</span></span>](https://docs.docker.com/docker-for-azure/deploy/)

> [!Note]
> <span data-ttu-id="36f1c-225">Si no tiene una suscripción de Azure, [Regístrese hoy](https://azure.microsoft.com/free/?b=16.48) para una cuenta gratuita de 30 días y get 200 dólares en créditos de Azure para probar cualquier combinación de los servicios de Azure.</span><span class="sxs-lookup"><span data-stu-id="36f1c-225">If you do not have an Azure subscription, [sign up today](https://azure.microsoft.com/free/?b=16.48) for a free 30-day account and get $200 in Azure Credits to try out any combination of Azure services.</span></span>

## <a name="docker-images-used-in-this-sample"></a><span data-ttu-id="36f1c-226">Imágenes de docker que se utilizan en este ejemplo</span><span class="sxs-lookup"><span data-stu-id="36f1c-226">Docker Images used in this sample</span></span>

<span data-ttu-id="36f1c-227">Las siguientes imágenes de Docker se usan en este ejemplo</span><span class="sxs-lookup"><span data-stu-id="36f1c-227">The following Docker images are used in this sample</span></span>

* [`microsoft/dotnet:2.0-sdk`](https://hub.docker.com/r/microsoft/dotnet)

## <a name="related-resources"></a><span data-ttu-id="36f1c-228">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="36f1c-228">Related Resources</span></span>

* [<span data-ttu-id="36f1c-229">Ejemplos de .NET core Docker</span><span class="sxs-lookup"><span data-stu-id="36f1c-229">.NET Core Docker samples</span></span>](https://github.com/dotnet/dotnet-docker-samples/README.md)
* [<span data-ttu-id="36f1c-230">Dockerfile en contenedores de Windows</span><span class="sxs-lookup"><span data-stu-id="36f1c-230">Dockerfile on Windows Containers</span></span>](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [<span data-ttu-id="36f1c-231">Ejemplos de .NET framework Docker</span><span class="sxs-lookup"><span data-stu-id="36f1c-231">.NET Framework Docker samples</span></span>](https://github.com/Microsoft/dotnet-framework-docker-samples)
* [<span data-ttu-id="36f1c-232">Núcleo de ASP.NET en DockerHub</span><span class="sxs-lookup"><span data-stu-id="36f1c-232">ASP.NET Core on DockerHub</span></span>](https://hub.docker.com/r/microsoft/aspnetcore/)
* [<span data-ttu-id="36f1c-233">Dockerize una aplicación de .NET Core - Tutorial de Docker</span><span class="sxs-lookup"><span data-stu-id="36f1c-233">Dockerize a .NET Core application - Docker Tutorial</span></span>](https://docs.docker.com/engine/examples/dotnetcore/)
* [<span data-ttu-id="36f1c-234">Trabajar con herramientas de Docker de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="36f1c-234">Working with Visual Studio Docker Tools</span></span>](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [<span data-ttu-id="36f1c-235">Implementación de imágenes de Docker desde el registro de contenedor de Azure a las instancias de contenedor de Azure</span><span class="sxs-lookup"><span data-stu-id="36f1c-235">Deploying Docker Images from the Azure Container Registry to Azure Container Instances</span></span>](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)