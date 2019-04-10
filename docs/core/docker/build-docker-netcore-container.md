---
title: Tutorial sobre cómo incluir una aplicación en un contenedor con Docker
description: En este tutorial obtendrá información sobre cómo incluir una aplicación de .NET Core en un contenedor con Docker.
ms.date: 03/20/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 8255a901c706e55e143cdf23dda0eb9bc79d245d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58844972"
---
# <a name="tutorial-containerize-a-net-core-app"></a><span data-ttu-id="a7f5d-103">Tutorial: Incluir una aplicación de .NET Core en un contenedor</span><span class="sxs-lookup"><span data-stu-id="a7f5d-103">Tutorial: Containerize a .NET Core app</span></span>

<span data-ttu-id="a7f5d-104">En este tutorial se ofrece información sobre cómo compilar una imagen de Docker que contiene una aplicación de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-104">This tutorial teaches you how to build a Docker image that contains your .NET Core application.</span></span> <span data-ttu-id="a7f5d-105">La imagen puede usarse para crear contenedores para un entorno de desarrollo local, una nube privada o una nube pública.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-105">The image can be used to create containers for your local development environment, private cloud, or public cloud.</span></span>

<span data-ttu-id="a7f5d-106">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="a7f5d-106">In this tutorial you will learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="a7f5d-107">Crear un Dockerfile</span><span class="sxs-lookup"><span data-stu-id="a7f5d-107">Create a Dockerfile</span></span>
> * <span data-ttu-id="a7f5d-108">Obtener una imagen base de Docker para Microsoft .NET Core</span><span class="sxs-lookup"><span data-stu-id="a7f5d-108">Pull a Microsoft .NET Core Docker base image</span></span>
> * <span data-ttu-id="a7f5d-109">Personalizar e implementar la aplicación en la imagen</span><span class="sxs-lookup"><span data-stu-id="a7f5d-109">Customize and deploy your app to the image</span></span>
> * <span data-ttu-id="a7f5d-110">Crear y ejecutar un contenedor</span><span class="sxs-lookup"><span data-stu-id="a7f5d-110">Create and run a container</span></span>
> * <span data-ttu-id="a7f5d-111">Implementar en Azure</span><span class="sxs-lookup"><span data-stu-id="a7f5d-111">Deploy to Azure</span></span>

<span data-ttu-id="a7f5d-112">Este tutorial trata sobre las tareas de compilación e implementación de un contenedor de Docker para una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-112">This tutorial teaches the Docker container build and deploy tasks for a .NET Core application.</span></span> <span data-ttu-id="a7f5d-113">La [plataforma Docker](https://docs.docker.com/engine/docker-overview/#the-docker-platform) usa el [motor de Docker](https://docs.docker.com/engine/docker-overview/#docker-engine) para compilar y empaquetar aplicaciones rápidamente como [imágenes de Docker](https://docs.docker.com/glossary/?term=image).</span><span class="sxs-lookup"><span data-stu-id="a7f5d-113">The [Docker platform](https://docs.docker.com/engine/docker-overview/#the-docker-platform) uses the [Docker Engine](https://docs.docker.com/engine/docker-overview/#docker-engine) to quickly build and package apps as [Docker images](https://docs.docker.com/glossary/?term=image).</span></span> <span data-ttu-id="a7f5d-114">Estas imágenes se escriben en el formato [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) para implementarse y ejecutarse en un [contenedor superpuesto](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).</span><span class="sxs-lookup"><span data-stu-id="a7f5d-114">These images are written in the [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) format to be deployed and run in a [layered container](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).</span></span>



## <a name="net-core-easiest-way-to-get-started"></a><span data-ttu-id="a7f5d-115">.NET Core: la manera más sencilla de empezar a trabajar</span><span class="sxs-lookup"><span data-stu-id="a7f5d-115">.NET Core: Easiest way to get started</span></span>

<span data-ttu-id="a7f5d-116">Antes de crear la imagen de Docker, necesita una aplicación que incluir en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-116">Before creating the Docker image, you need an application to containerize.</span></span> <span data-ttu-id="a7f5d-117">Puede crearla en Linux, MacOS o Windows.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-117">You can create it on Linux, MacOS, or Windows.</span></span> <span data-ttu-id="a7f5d-118">La forma más rápida y sencilla de hacerlo es usar .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-118">The quickest and easiest way to do that is to use .NET Core.</span></span>

<span data-ttu-id="a7f5d-119">Si no está familiarizado con el conjunto de herramientas de la CLI de .NET Core, vea la [información general del SDK de .NET Core](../tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="a7f5d-119">If you're unfamiliar with the .NET Core CLI toolset, read the [.NET Core SDK overview](../tools/index.md).</span></span>

<span data-ttu-id="a7f5d-120">Puede compilar contenedores de Windows y Linux con [etiquetas de varias arquitecturas](https://github.com/dotnet/announcements/issues/14).</span><span class="sxs-lookup"><span data-stu-id="a7f5d-120">You can build both Windows and Linux containers with [multi-arch based tags](https://github.com/dotnet/announcements/issues/14).</span></span>

## <a name="your-first-net-core-docker-app"></a><span data-ttu-id="a7f5d-121">La primera aplicación de .NET Core Docker</span><span class="sxs-lookup"><span data-stu-id="a7f5d-121">Your first .NET Core Docker app</span></span>

### <a name="prerequisites"></a><span data-ttu-id="a7f5d-122">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a7f5d-122">Prerequisites</span></span>

<span data-ttu-id="a7f5d-123">Para realizar este tutorial:</span><span class="sxs-lookup"><span data-stu-id="a7f5d-123">To complete this tutorial:</span></span>

#### <a name="net-core-sdk"></a><span data-ttu-id="a7f5d-124">SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="a7f5d-124">.NET Core SDK</span></span>

* <span data-ttu-id="a7f5d-125">Instale el [SDK de .NET Core 2.1](https://www.microsoft.com/net/download) o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-125">Install [.NET Core 2.1 SDK](https://www.microsoft.com/net/download) or later.</span></span>

<span data-ttu-id="a7f5d-126">Vea [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) (.NET Core 2.1: versiones de SO compatibles) para obtener una lista completa de los sistemas operativos compatibles con .NET Core 2.1, las versiones sin soporte del sistema operativo y los vínculos a la directiva de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-126">See [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) for the complete list of .NET Core 2.1 supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

* <span data-ttu-id="a7f5d-127">Instale el editor de código que prefiera si aún no lo ha hecho.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-127">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="a7f5d-128">¿Es necesario instalar un editor de código?</span><span class="sxs-lookup"><span data-stu-id="a7f5d-128">Need to install a code editor?</span></span> <span data-ttu-id="a7f5d-129">Pruebe [Visual Studio Code](https://code.visualstudio.com/download).</span><span class="sxs-lookup"><span data-stu-id="a7f5d-129">Try [Visual Studio Code](https://code.visualstudio.com/download)!</span></span>

#### <a name="installing-docker-client"></a><span data-ttu-id="a7f5d-130">Instalación del cliente Docker</span><span class="sxs-lookup"><span data-stu-id="a7f5d-130">Installing Docker Client</span></span>

<span data-ttu-id="a7f5d-131">Instale la versión [Docker 18.06](https://docs.docker.com/release-notes/docker-ce/) o posterior del cliente Docker.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-131">Install [Docker 18.06](https://docs.docker.com/release-notes/docker-ce/) or later of the Docker client.</span></span>

<span data-ttu-id="a7f5d-132">El cliente Docker se puede instalar en:</span><span class="sxs-lookup"><span data-stu-id="a7f5d-132">The Docker client can be installed in:</span></span>

* <span data-ttu-id="a7f5d-133">Distribuciones de Linux</span><span class="sxs-lookup"><span data-stu-id="a7f5d-133">Linux distributions</span></span>

   * [<span data-ttu-id="a7f5d-134">CentOS</span><span class="sxs-lookup"><span data-stu-id="a7f5d-134">CentOS</span></span>](https://docs.docker.com/install/linux/docker-ce/centos/)

   * [<span data-ttu-id="a7f5d-135">Debian</span><span class="sxs-lookup"><span data-stu-id="a7f5d-135">Debian</span></span>](https://docs.docker.com/install/linux/docker-ce/debian/)

   * [<span data-ttu-id="a7f5d-136">Fedora</span><span class="sxs-lookup"><span data-stu-id="a7f5d-136">Fedora</span></span>](https://docs.docker.com/install/linux/docker-ce/fedora/)

   * [<span data-ttu-id="a7f5d-137">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="a7f5d-137">Ubuntu</span></span>](https://docs.docker.com/install/linux/docker-ce/ubuntu/)

* [<span data-ttu-id="a7f5d-138">macOS</span><span class="sxs-lookup"><span data-stu-id="a7f5d-138">macOS</span></span>](https://docs.docker.com/docker-for-mac/install/)

* <span data-ttu-id="a7f5d-139">[Windows](https://docs.docker.com/docker-for-windows/install/).</span><span class="sxs-lookup"><span data-stu-id="a7f5d-139">[Windows](https://docs.docker.com/docker-for-windows/install/).</span></span>

### <a name="create-a-net-core-21-console-app-for-dockerization"></a><span data-ttu-id="a7f5d-140">Creación de una aplicación de consola de .NET Core 2.1 para incluirla en Docker</span><span class="sxs-lookup"><span data-stu-id="a7f5d-140">Create a .NET Core 2.1 console app for Dockerization</span></span>

<span data-ttu-id="a7f5d-141">Abra un símbolo del sistema y cree una carpeta denominada *Hello*.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-141">Open a command prompt and create a folder named *Hello*.</span></span> <span data-ttu-id="a7f5d-142">Vaya a la carpeta que ha creado y escriba los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="a7f5d-142">Navigate to the folder you created and type the following commands:</span></span>

```console
dotnet new console
dotnet run
```

<span data-ttu-id="a7f5d-143">Veamos un tutorial rápido:</span><span class="sxs-lookup"><span data-stu-id="a7f5d-143">Let's do a quick walkthrough:</span></span>

1. `$ dotnet new console`

   <span data-ttu-id="a7f5d-144">[`dotnet new`](../tools/dotnet-new.md) crea un archivo de proyecto `Hello.csproj` actualizado con las dependencias necesarias para compilar una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-144">[`dotnet new`](../tools/dotnet-new.md) creates an up-to-date `Hello.csproj` project file with the dependencies necessary to build a console app.</span></span>  <span data-ttu-id="a7f5d-145">Además, se crea un archivo `Program.cs`, un archivo básico que contiene el punto de entrada para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-145">It also creates a `Program.cs`, a basic file containing the entry point for the application.</span></span>

   <span data-ttu-id="a7f5d-146">`Hello.csproj`:</span><span class="sxs-lookup"><span data-stu-id="a7f5d-146">`Hello.csproj`:</span></span>

   <span data-ttu-id="a7f5d-147">El archivo de proyecto especifica todo lo que es necesario para restaurar las dependencias y compilar el programa.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-147">The project file specifies everything that's needed to restore dependencies and build the program.</span></span>

   * <span data-ttu-id="a7f5d-148">La etiqueta `OutputType` especifica que estamos creando un archivo ejecutable, es decir, una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-148">The `OutputType` tag specifies that we're building an executable, in other words a console application.</span></span>
   * <span data-ttu-id="a7f5d-149">La etiqueta `TargetFramework` especifica la implementación .NET a la que nos dirigimos.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-149">The `TargetFramework` tag specifies what .NET implementation we're targeting.</span></span> <span data-ttu-id="a7f5d-150">En un escenario avanzado, puede especificar varios marcos de destino y compilar en los especificados en una sola operación.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-150">In an advanced scenario, you can specify multiple target frameworks and build to the specified frameworks in a single operation.</span></span> <span data-ttu-id="a7f5d-151">En este tutorial se compila para .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-151">In this tutorial, we build for .NET Core 2.1.</span></span>

   <span data-ttu-id="a7f5d-152">`Program.cs`:</span><span class="sxs-lookup"><span data-stu-id="a7f5d-152">`Program.cs`:</span></span>

   <span data-ttu-id="a7f5d-153">`using System` inicia el programa.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-153">The program starts by `using System`.</span></span> <span data-ttu-id="a7f5d-154">Esta instrucción significa "llevar cada cosa del espacio de nombres `System` al ámbito de este archivo".</span><span class="sxs-lookup"><span data-stu-id="a7f5d-154">This statement means, "Bring everything in the `System` namespace into scope for this file."</span></span> <span data-ttu-id="a7f5d-155">El espacio de nombres `System` incluye construcciones básicas, como `string` o tipos numéricos.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-155">The `System` namespace includes basic constructs such as `string`, or numeric types.</span></span>

   <span data-ttu-id="a7f5d-156">Después, definimos un espacio de nombres denominado `Hello`.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-156">We then define a namespace called `Hello`.</span></span> <span data-ttu-id="a7f5d-157">Puede cambiar el espacio de nombres por lo que quiera.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-157">You can change namespace to anything you want.</span></span> <span data-ttu-id="a7f5d-158">Se define una clase denominada `Program` dentro del espacio de nombres, con un método `Main` que toma una matriz de cadenas como argumento.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-158">A class named `Program` is defined within that namespace, with a `Main` method that takes an array of strings as its argument.</span></span> <span data-ttu-id="a7f5d-159">Esta matriz contiene la lista de argumentos que se ha pasado cuando se llama al programa compilado.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-159">This array contains the list of arguments passed in when the compiled program is called.</span></span> <span data-ttu-id="a7f5d-160">En el ejemplo, el programa solo escribe "¡Hello World!"</span><span class="sxs-lookup"><span data-stu-id="a7f5d-160">In our example, the program only writes "Hello World!"</span></span> <span data-ttu-id="a7f5d-161">en la consola.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-161">to the console.</span></span>

   <span data-ttu-id="a7f5d-162">**dotnet new** ejecuta el comando [`dotnet restore`](../tools/dotnet-restore.md).</span><span class="sxs-lookup"><span data-stu-id="a7f5d-162">**dotnet new** runs the [`dotnet restore`](../tools/dotnet-restore.md) command.</span></span> <span data-ttu-id="a7f5d-163">**Dotnet restore** restaura el árbol de dependencias con una llamada a [NuGet](https://www.nuget.org/) (administrador de paquetes de .NET).</span><span class="sxs-lookup"><span data-stu-id="a7f5d-163">**Dotnet restore** restores the tree of dependencies with a [NuGet](https://www.nuget.org/)(.NET package manager) call.</span></span>
   <span data-ttu-id="a7f5d-164">NuGet realiza las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="a7f5d-164">NuGet performs the following tasks:</span></span>
   * <span data-ttu-id="a7f5d-165">Analiza el archivo *Hello.csproj*.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-165">analyzes the *Hello.csproj* file.</span></span>
   * <span data-ttu-id="a7f5d-166">Descarga las dependencias del archivo (o las obtiene de la caché de la máquina).</span><span class="sxs-lookup"><span data-stu-id="a7f5d-166">downloads the file dependencies (or grabs from your machine cache).</span></span>
   * <span data-ttu-id="a7f5d-167">Escribe el archivo *obj/project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-167">writes the *obj/project.assets.json* file.</span></span>

   <span data-ttu-id="a7f5d-168">El archivo *project.assets.json* es un conjunto completo del gráfico de dependencias de NuGet, las resoluciones de enlaces y otros metadatos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-168">The *project.assets.json* file is a complete set of the NuGet dependencies graph, binding resolutions, and other app metadata.</span></span> <span data-ttu-id="a7f5d-169">Este archivo obligatorio se usa con otras herramientas, como [`dotnet build`](../tools/dotnet-build.md) y [`dotnet run`](../tools/dotnet-run.md), para procesar correctamente el código fuente.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-169">This required file is used by other tools, such as [`dotnet build`](../tools/dotnet-build.md) and [`dotnet run`](../tools/dotnet-run.md), to correctly process the source code.</span></span>

2. `$ dotnet run`

   <span data-ttu-id="a7f5d-170">[`dotnet run`](../tools/dotnet-run.md) llama a [`dotnet build`](../tools/dotnet-build.md) para confirmar una compilación correcta y luego llama a `dotnet <assembly.dll>` para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-170">[`dotnet run`](../tools/dotnet-run.md) calls [`dotnet build`](../tools/dotnet-build.md) to confirm a successful build, and then calls `dotnet <assembly.dll>` to run the application.</span></span>

    ```console
    $ dotnet run

    Hello World!
    ```

    <span data-ttu-id="a7f5d-171">En escenarios avanzados, vea [Implementación de aplicaciones .NET Core](../deploying/index.md) para obtener detalles.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-171">For advanced scenarios,  see [.NET Core Application Deployment](../deploying/index.md) for details.</span></span>

## <a name="dockerize-the-net-core-application"></a><span data-ttu-id="a7f5d-172">Aplicar Docker a la aplicación .NET Core</span><span class="sxs-lookup"><span data-stu-id="a7f5d-172">Dockerize the .NET Core application</span></span>

<span data-ttu-id="a7f5d-173">La aplicación de consola Hello de .NET Core se ejecuta correctamente en local.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-173">The Hello .NET Core console app successfully runs locally.</span></span> <span data-ttu-id="a7f5d-174">El siguiente paso es compilar y ejecutar la aplicación en Docker.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-174">Now let's take it a step further and build and run the app in Docker.</span></span>

### <a name="your-first-dockerfile"></a><span data-ttu-id="a7f5d-175">El primer Dockerfile</span><span class="sxs-lookup"><span data-stu-id="a7f5d-175">Your first Dockerfile</span></span>

<span data-ttu-id="a7f5d-176">Abra el editor de texto para empezar.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-176">Open your text editor and let's get started!</span></span> <span data-ttu-id="a7f5d-177">Todavía no está trabajando desde el directorio Hello en que se ha compilado la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-177">We're still working from the Hello directory we built the app in.</span></span>

<span data-ttu-id="a7f5d-178">Agregue las siguientes instrucciones de Docker para cada [contenedor de Windows o Linux](https://docs.microsoft.com/virtualization/windowscontainers/about/) a un archivo nuevo.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-178">Add the following Docker instructions for either Linux or [Windows Containers](https://docs.microsoft.com/virtualization/windowscontainers/about/) to a new file.</span></span> <span data-ttu-id="a7f5d-179">Cuando termine, guárdelo en la raíz del directorio Hello como **Dockerfile**, sin extensión (puede que necesite establecer el tipo de archivo en `All types (*.*)` o similar).</span><span class="sxs-lookup"><span data-stu-id="a7f5d-179">When finished, save it in the root of your Hello directory as **Dockerfile**, with no extension (You may need to set your file type to `All types (*.*)` or something similar).</span></span>

```Dockerfile
FROM microsoft/dotnet:2.1-sdk
WORKDIR /app

# copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# copy and build everything else
COPY . ./
RUN dotnet publish -c Release -o out
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

<span data-ttu-id="a7f5d-180">El Dockerfile contiene las instrucciones de compilación de Docker que se ejecutan secuencialmente.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-180">The Dockerfile contains Docker build instructions that run sequentially.</span></span>

<span data-ttu-id="a7f5d-181">La primera instrucción debe ser [**FROM**](https://docs.docker.com/engine/reference/builder/#from).</span><span class="sxs-lookup"><span data-stu-id="a7f5d-181">The first instruction must be [**FROM**](https://docs.docker.com/engine/reference/builder/#from).</span></span> <span data-ttu-id="a7f5d-182">Esta instrucción inicializa una nueva fase de compilación y establece la imagen base para las instrucciones restantes.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-182">This instruction initializes a new build stage and sets the Base Image for the remaining instructions.</span></span> <span data-ttu-id="a7f5d-183">Las etiquetas de varias arquitecturas extraen contenedores de Windows o Linux según [el modo de contenedor](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers) de Docker para Windows.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-183">The multi-arch tags pull either Windows or Linux containers depending on the Docker for Windows [container mode](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers).</span></span> <span data-ttu-id="a7f5d-184">La imagen base del ejemplo es la imagen 2.1-sdk del repositorio microsoft/dotnet.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-184">The Base Image for our sample is the 2.1-sdk image from the microsoft/dotnet repository,</span></span>

```Dockerfile
FROM microsoft/dotnet:2.1-sdk
```

<span data-ttu-id="a7f5d-185">La instrucción [**WORKDIR**](https://docs.docker.com/engine/reference/builder/#workdir) establece el directorio de trabajo de cualquier instrucción RUN, CMD, ENTRYPOINT, COPY y ADD Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-185">The [**WORKDIR**](https://docs.docker.com/engine/reference/builder/#workdir) instruction sets the working directory for any remaining RUN, CMD, ENTRYPOINT, COPY, and ADD Dockerfile instructions.</span></span> <span data-ttu-id="a7f5d-186">Si el directorio no existe, se crea.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-186">If the directory doesn't exist, it's created.</span></span> <span data-ttu-id="a7f5d-187">En este caso, WORKDIR se establece en el directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-187">In this case, WORKDIR is set to the app directory.</span></span>

```Dockerfile
WORKDIR /app
```

<span data-ttu-id="a7f5d-188">La instrucción [**COPY**](https://docs.docker.com/engine/reference/builder/#copy) copia nuevos archivos o directorios de la ruta de acceso de origen y los agrega al sistema de archivos del contenedor de destino.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-188">The [**COPY**](https://docs.docker.com/engine/reference/builder/#copy) instruction copies new files or directories from the source path and adds them to the destination container filesystem.</span></span> <span data-ttu-id="a7f5d-189">Con esta instrucción, se copia el archivo de proyecto de C# en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-189">With this instruction, we are copying the C# project file to the container.</span></span>

```Dockerfile
COPY *.csproj ./
```

<span data-ttu-id="a7f5d-190">La instrucción [**RUN**](https://docs.docker.com/engine/reference/builder/#run) ejecuta los comandos en una nueva capa sobre la imagen actual y confirma los resultados.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-190">The [**RUN**](https://docs.docker.com/engine/reference/builder/#run) instruction executes any commands in a new layer on top of the current image and commit the results.</span></span> <span data-ttu-id="a7f5d-191">La imagen resultante confirmada se usa para el siguiente paso en el Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-191">The resulting committed image is used for the next step in the Dockerfile.</span></span> <span data-ttu-id="a7f5d-192">Se está ejecutando **dotnet restore** para obtener las dependencias necesarias del archivo de proyecto de C#.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-192">We are running **dotnet restore** to get the needed dependencies of the C# project file.</span></span>

```Dockerfile
RUN dotnet restore
```

<span data-ttu-id="a7f5d-193">Esta instrucción **COPY** copia el resto de los archivos en el contenedor en nuevas [capas](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers).</span><span class="sxs-lookup"><span data-stu-id="a7f5d-193">This **COPY** instruction copies the rest of the files into our container into new [layers](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers).</span></span>

```Dockerfile
COPY . ./
```

<span data-ttu-id="a7f5d-194">Se está publicando la aplicación con esta instrucción **RUN**.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-194">We are publishing the app with this **RUN** instruction.</span></span> <span data-ttu-id="a7f5d-195">El comando [**dotnet publish**](../tools/dotnet-publish.md) compila la aplicación, lee sus dependencias especificadas en el archivo de proyecto y publica el conjunto resultante de archivos en un directorio.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-195">The [**dotnet publish**](../tools/dotnet-publish.md) command compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="a7f5d-196">La aplicación se publica con una configuración de **versión** y se escribe en el directorio predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-196">Our app is published with a **Release** configuration and output to the default directory.</span></span>

```Dockerfile
RUN dotnet publish -c Release -o out
```

<span data-ttu-id="a7f5d-197">La instrucción [**ENTRYPOINT**](https://docs.docker.com/engine/reference/builder/#entrypoint) permite al contenedor ejecutarse como un archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-197">The [**ENTRYPOINT**](https://docs.docker.com/engine/reference/builder/#entrypoint) instruction allows the container to run as an executable.</span></span>

```Dockerfile
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

<span data-ttu-id="a7f5d-198">Ya tiene un Dockerfile que:</span><span class="sxs-lookup"><span data-stu-id="a7f5d-198">Now you have a Dockerfile that:</span></span>

* <span data-ttu-id="a7f5d-199">copia la aplicación en la imagen</span><span class="sxs-lookup"><span data-stu-id="a7f5d-199">copies your app to the image</span></span>
* <span data-ttu-id="a7f5d-200">copia las dependencias de la aplicación en la imagen</span><span class="sxs-lookup"><span data-stu-id="a7f5d-200">your app's dependencies to the image</span></span>
* <span data-ttu-id="a7f5d-201">compila la aplicación para que se ejecute como un archivo ejecutable</span><span class="sxs-lookup"><span data-stu-id="a7f5d-201">builds the app to run as an executable</span></span>

### <a name="build-and-run-the-hello-net-core-app"></a><span data-ttu-id="a7f5d-202">Compilación y ejecución de la aplicación Hello de .NET Core</span><span class="sxs-lookup"><span data-stu-id="a7f5d-202">Build and run the Hello .NET Core app</span></span>

#### <a name="essential-docker-commands"></a><span data-ttu-id="a7f5d-203">Comandos de Docker esenciales</span><span class="sxs-lookup"><span data-stu-id="a7f5d-203">Essential Docker commands</span></span>

<span data-ttu-id="a7f5d-204">Estos comandos de Docker son esenciales:</span><span class="sxs-lookup"><span data-stu-id="a7f5d-204">These Docker commands are essential:</span></span>

* [<span data-ttu-id="a7f5d-205">docker build</span><span class="sxs-lookup"><span data-stu-id="a7f5d-205">docker build</span></span>](https://docs.docker.com/engine/reference/commandline/build/)
* [<span data-ttu-id="a7f5d-206">docker run</span><span class="sxs-lookup"><span data-stu-id="a7f5d-206">docker run</span></span>](https://docs.docker.com/engine/reference/commandline/run/)
* [<span data-ttu-id="a7f5d-207">docker ps</span><span class="sxs-lookup"><span data-stu-id="a7f5d-207">docker ps</span></span>](https://docs.docker.com/engine/reference/commandline/ps/)
* [<span data-ttu-id="a7f5d-208">docker stop</span><span class="sxs-lookup"><span data-stu-id="a7f5d-208">docker stop</span></span>](https://docs.docker.com/engine/reference/commandline/stop/)
* [<span data-ttu-id="a7f5d-209">docker rm</span><span class="sxs-lookup"><span data-stu-id="a7f5d-209">docker rm</span></span>](https://docs.docker.com/engine/reference/commandline/rm/)
* [<span data-ttu-id="a7f5d-210">docker rmi</span><span class="sxs-lookup"><span data-stu-id="a7f5d-210">docker rmi</span></span>](https://docs.docker.com/engine/reference/commandline/rmi/)
* [<span data-ttu-id="a7f5d-211">docker image</span><span class="sxs-lookup"><span data-stu-id="a7f5d-211">docker image</span></span>](https://docs.docker.com/engine/reference/commandline/image/)

#### <a name="build-and-run"></a><span data-ttu-id="a7f5d-212">Compilar y ejecutar</span><span class="sxs-lookup"><span data-stu-id="a7f5d-212">Build and run</span></span>

<span data-ttu-id="a7f5d-213">Ha escrito el Dockerfile; ahora Docker compila la aplicación y luego ejecuta el contenedor.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-213">You wrote the dockerfile; now Docker builds your app and then runs the container.</span></span>

```console
docker build -t dotnetapp-dev .
docker run --rm dotnetapp-dev Hello from Docker
```

<span data-ttu-id="a7f5d-214">La salida del comando `docker build` debe ser similar a la siguiente salida de consola:</span><span class="sxs-lookup"><span data-stu-id="a7f5d-214">The output from the `docker build` command should be similar to the following console output:</span></span>

```console
Sending build context to Docker daemon   173.1kB
Step 1/7 : FROM microsoft/dotnet:2.1-sdk
 ---> 288f8c45f7c2
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
Successfully built 46db075bd98d
Successfully tagged dotnetapp-dev:latest
```

<span data-ttu-id="a7f5d-215">Como puede ver en la salida, el motor de Docker ha usado el Dockerfile para compilar el contenedor.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-215">As you can see from the output, the Docker Engine used the Dockerfile to build our container.</span></span>

<span data-ttu-id="a7f5d-216">La salida del comando `docker run` debe ser similar a la siguiente salida de consola:</span><span class="sxs-lookup"><span data-stu-id="a7f5d-216">The output from the `docker run` command should be similar to the following console output:</span></span>

```console
Hello World!
```

<span data-ttu-id="a7f5d-217">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="a7f5d-217">Congratulations!</span></span> <span data-ttu-id="a7f5d-218">Acaba de:</span><span class="sxs-lookup"><span data-stu-id="a7f5d-218">You have just:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="a7f5d-219">Crear una aplicación .NET Core local</span><span class="sxs-lookup"><span data-stu-id="a7f5d-219">Created a local .NET Core app</span></span>
> * <span data-ttu-id="a7f5d-220">Crear un Dockerfile para compilar el primer contenedor</span><span class="sxs-lookup"><span data-stu-id="a7f5d-220">Created a Dockerfile to build your first container</span></span>
> * <span data-ttu-id="a7f5d-221">Compilar y ejecutar la aplicación a la que se ha aplicado Docker</span><span class="sxs-lookup"><span data-stu-id="a7f5d-221">Built and ran your Dockerized app</span></span>

## <a name="next-steps"></a><span data-ttu-id="a7f5d-222">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a7f5d-222">Next steps</span></span>

<span data-ttu-id="a7f5d-223">Estos son algunos de los pasos que puede realizar a continuación:</span><span class="sxs-lookup"><span data-stu-id="a7f5d-223">Here are some next steps you can take:</span></span>

* [<span data-ttu-id="a7f5d-224">Introducción a vídeo e imágenes de .NET Docker</span><span class="sxs-lookup"><span data-stu-id="a7f5d-224">Introduction to .NET Docker Images Video</span></span>](https://channel9.msdn.com/Shows/Code-Conversations/Introduction-to-NET-Docker-Images-with-Kendra-Havens?term=docker)
* [<span data-ttu-id="a7f5d-225">Instancias de Visual Studio, Docker y Azure Container juntas</span><span class="sxs-lookup"><span data-stu-id="a7f5d-225">Visual Studio, Docker & Azure Container Instances better together!</span></span>](https://medium.com/@AliMazaheri/visual-studio-docker-azure-container-instances-better-together-bf8c2f0419ae)
* [<span data-ttu-id="a7f5d-226">Docker para tutoriales rápidos de Azure</span><span class="sxs-lookup"><span data-stu-id="a7f5d-226">Docker for Azure Quickstarts</span></span>](https://docs.docker.com/docker-for-azure/#docker-community-edition-ce-for-azure)
* [<span data-ttu-id="a7f5d-227">Implementar la aplicación en Docker para Azure</span><span class="sxs-lookup"><span data-stu-id="a7f5d-227">Deploy your app on Docker for Azure</span></span>](https://docs.docker.com/docker-for-azure/deploy/)

> [!NOTE]
> <span data-ttu-id="a7f5d-228">Si no tiene una suscripción de Azure, [regístrese hoy](https://azure.microsoft.com/free/?b=16.48) para obtener una cuenta gratuita durante 30 días y obtenga 200 dólares en créditos de Azure para probar cualquier combinación de servicios de Azure.</span><span class="sxs-lookup"><span data-stu-id="a7f5d-228">If you do not have an Azure subscription, [sign up today](https://azure.microsoft.com/free/?b=16.48) for a free 30-day account and get $200 in Azure Credits to try out any combination of Azure services.</span></span>

## <a name="docker-images-used-in-this-sample"></a><span data-ttu-id="a7f5d-229">Imágenes de Docker usadas en este ejemplo</span><span class="sxs-lookup"><span data-stu-id="a7f5d-229">Docker Images used in this sample</span></span>

<span data-ttu-id="a7f5d-230">En este ejemplo se usan las siguientes imágenes de Docker</span><span class="sxs-lookup"><span data-stu-id="a7f5d-230">The following Docker images are used in this sample</span></span>

* [`microsoft/dotnet:2.1-sdk`](https://hub.docker.com/r/microsoft/dotnet)

## <a name="related-resources"></a><span data-ttu-id="a7f5d-231">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="a7f5d-231">Related resources</span></span>

* [<span data-ttu-id="a7f5d-232">Ejemplos de .NET Core Docker</span><span class="sxs-lookup"><span data-stu-id="a7f5d-232">.NET Core Docker samples</span></span>](https://github.com/dotnet/dotnet-docker/tree/master/samples)
* [<span data-ttu-id="a7f5d-233">Dockerfile en contenedores de Windows</span><span class="sxs-lookup"><span data-stu-id="a7f5d-233">Dockerfile on Windows Containers</span></span>](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [<span data-ttu-id="a7f5d-234">Ejemplos de .NET Framework Docker</span><span class="sxs-lookup"><span data-stu-id="a7f5d-234">.NET Framework Docker samples</span></span>](https://github.com/Microsoft/dotnet-framework-docker-samples)
* [<span data-ttu-id="a7f5d-235">ASP.NET Core en DockerHub</span><span class="sxs-lookup"><span data-stu-id="a7f5d-235">ASP.NET Core on DockerHub</span></span>](https://hub.docker.com/r/microsoft/aspnetcore/)
* [<span data-ttu-id="a7f5d-236">Aplicar Docker a una aplicación .NET Core: Tutorial de Docker</span><span class="sxs-lookup"><span data-stu-id="a7f5d-236">Dockerize a .NET Core application - Docker Tutorial</span></span>](https://docs.docker.com/engine/examples/dotnetcore/)
* <span data-ttu-id="a7f5d-237">[Working with Visual Studio Docker Tools](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker) (Trabajo con Visual Studio Docker Tools)</span><span class="sxs-lookup"><span data-stu-id="a7f5d-237">[Working with Visual Studio Docker Tools](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)</span></span>
* <span data-ttu-id="a7f5d-238">[Deploying Docker Images from the Azure Container Registry to Azure Container Instances](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/) (Implementación de imágenes de Docker desde Azure Container Registry a Azure Container Instances)</span><span class="sxs-lookup"><span data-stu-id="a7f5d-238">[Deploying Docker Images from the Azure Container Registry to Azure Container Instances](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)</span></span>