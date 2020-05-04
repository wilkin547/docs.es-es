---
title: Herramientas para desarrolladores de .NET y .NET Core de Azure
description: Obtenga las herramientas para empezar a usar las bibliotecas .NET de Azure desde un entorno de Windows, Linux y Mac.
ms.date: 10/01/2018
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: 1c6370e4b3e5e6e901ba6ef56c65d794f3da5abe
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2020
ms.locfileid: "81433167"
---
# <a name="tools-for-net-and-net-core-azure-developers"></a><span data-ttu-id="d5cc2-103">Herramientas para desarrolladores de .NET y .NET Core de Azure</span><span class="sxs-lookup"><span data-stu-id="d5cc2-103">Tools for .NET and .NET Core Azure developers</span></span>

## <a name="sdk-downloads"></a><span data-ttu-id="d5cc2-104">Descargas de SDK</span><span class="sxs-lookup"><span data-stu-id="d5cc2-104">SDK downloads</span></span>

<span data-ttu-id="d5cc2-105">Las bibliotecas de Azure para .NET se implementan como [paquetes NuGet](https://www.nuget.org/packages?q=windowsazureofficial).</span><span class="sxs-lookup"><span data-stu-id="d5cc2-105">Azure libraries for .NET are implemented as [NuGet packages](https://www.nuget.org/packages?q=windowsazureofficial).</span></span> <span data-ttu-id="d5cc2-106">Vaya a la [referencia de API](/dotnet/api/overview/azure/?view=azure-dotnet) para obtener instrucciones de instalación organizadas por servicio de Azure.</span><span class="sxs-lookup"><span data-stu-id="d5cc2-106">See the [API Reference](/dotnet/api/overview/azure/?view=azure-dotnet) for installation instructions organized by Azure service.</span></span>

## <a name="development-tools"></a><span data-ttu-id="d5cc2-107">Herramientas de desarrollo</span><span class="sxs-lookup"><span data-stu-id="d5cc2-107">Development tools</span></span>

<span data-ttu-id="d5cc2-108">Visual Studio tiene integradas herramientas para muchos servicios de Azure.</span><span class="sxs-lookup"><span data-stu-id="d5cc2-108">Visual Studio has tooling for many Azure services built-in.</span></span> <span data-ttu-id="d5cc2-109">Algunos servicios de Azure disponen de más herramientas o emuladores, como el [Explorador de Azure Storage](https://azure.microsoft.com/features/storage-explorer/).</span><span class="sxs-lookup"><span data-stu-id="d5cc2-109">Some Azure services have additional tools or emulators available, such as [Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/).</span></span> <span data-ttu-id="d5cc2-110">Consulte la documentación del servicio de Azure correspondiente para ver las herramientas adicionales si así lo precisa.</span><span class="sxs-lookup"><span data-stu-id="d5cc2-110">See the documentation for your Azure service for any additional tools, if necessary.</span></span>

<span data-ttu-id="d5cc2-111">Con estas instrucciones se instala el entorno de desarrollo recomendado de su sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="d5cc2-111">These instructions install the recommended starting development environment for your operating system.</span></span>

## <a name="windows"></a>[<span data-ttu-id="d5cc2-112">Windows</span><span class="sxs-lookup"><span data-stu-id="d5cc2-112">Windows</span></span>](#tab/windows)

<span data-ttu-id="d5cc2-113">Las versiones 2017 y posteriores de Visual Studio incluyen compatibilidad integrada con el desarrollo de Azure.</span><span class="sxs-lookup"><span data-stu-id="d5cc2-113">Visual Studio versions 2017 and later have built-in support for Azure development.</span></span> <span data-ttu-id="d5cc2-114">Los siguientes pasos describen cómo habilitar la compatibilidad con el desarrollo de Azure en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d5cc2-114">The below steps describe enabling Azure development support in Visual Studio.</span></span>

<span data-ttu-id="d5cc2-115"><a href="vs2015-install.md">Siga estas instrucciones</a> con Visual Studio 2015 y versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="d5cc2-115">For Visual Studio 2015 and earlier, <a href="vs2015-install.md">follow these instructions</a>.</span></span>

### <a name="step-1-download-visual-studio-2019"></a><span data-ttu-id="d5cc2-116">Paso 1: Descargar Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="d5cc2-116">Step 1: Download Visual Studio 2019</span></span>

<span data-ttu-id="d5cc2-117">Si ya tiene instalado Visual Studio 2019, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="d5cc2-117">You can skip this step if you already have Visual Studio 2019 installed.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d5cc2-118">Descargar Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="d5cc2-118">Download Visual Studio 2019</span></span>](https://www.visualstudio.com/downloads/)

### <a name="step-2-install-the-two-azure-workloads"></a><span data-ttu-id="d5cc2-119">Paso 2: Instalación de las dos cargas de trabajo de Azure</span><span class="sxs-lookup"><span data-stu-id="d5cc2-119">Step 2: Install the two Azure workloads</span></span>

<span data-ttu-id="d5cc2-120">En el instalador de Visual Studio, instale Visual Studio (o modifique una instalación existente).</span><span class="sxs-lookup"><span data-stu-id="d5cc2-120">In the Visual Studio installer, install Visual Studio (or modify an existing installation).</span></span> <span data-ttu-id="d5cc2-121">Asegúrese de que las cargas de trabajo *Desarrollo de Azure* y *Desarrollo de ASP.NET y web* están seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="d5cc2-121">Make sure the *Azure development* and *ASP.NET and web development* workloads are selected.</span></span>

### <a name="step-3-develop-with-net-on-azure"></a><span data-ttu-id="d5cc2-122">Paso 3: Desarrollo con .NET en Azure</span><span class="sxs-lookup"><span data-stu-id="d5cc2-122">Step 3: Develop with .NET on Azure</span></span>

<span data-ttu-id="d5cc2-123">Comience por [implementar su primera aplicación web ASP.NET Core en Azure App Service](https://docs.microsoft.com/azure/app-service-web/app-service-web-get-started-dotnet).</span><span class="sxs-lookup"><span data-stu-id="d5cc2-123">Get started by [deploying your first ASP.NET Core web app on Azure App Service](https://docs.microsoft.com/azure/app-service-web/app-service-web-get-started-dotnet).</span></span>

## <a name="macos"></a>[<span data-ttu-id="d5cc2-124">macOS</span><span class="sxs-lookup"><span data-stu-id="d5cc2-124">macOS</span></span>](#tab/macos)

<span data-ttu-id="d5cc2-125">Visual Studio para Mac tiene todo lo que necesita para el desarrollo de Azure.</span><span class="sxs-lookup"><span data-stu-id="d5cc2-125">Visual Studio for Mac has everything you need for Azure development.</span></span>

### <a name="step-1-download-visual-studio-for-mac"></a><span data-ttu-id="d5cc2-126">Paso 1: Descarga de Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="d5cc2-126">Step 1: Download Visual Studio for Mac</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d5cc2-127">Descargar Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="d5cc2-127">Download Visual Studio for Mac</span></span>](https://www.visualstudio.com/vs/visual-studio-mac/)

<span data-ttu-id="d5cc2-128">Durante la instalación, las herramientas de Azure se seleccionan de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d5cc2-128">During installation, Azure tools are selected by default.</span></span>

## <a name="linux"></a>[<span data-ttu-id="d5cc2-129">Linux</span><span class="sxs-lookup"><span data-stu-id="d5cc2-129">Linux</span></span>](#tab/linux)

<span data-ttu-id="d5cc2-130">Visual Studio Code tiene todo lo que necesita para el desarrollo de Azure en Linux.</span><span class="sxs-lookup"><span data-stu-id="d5cc2-130">Visual Studio Code has everything you need for Azure development on Linux.</span></span>

### <a name="step-1-download-the-net-core-sdk"></a><span data-ttu-id="d5cc2-131">Paso 1: Descarga del SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="d5cc2-131">Step 1: Download the .NET Core SDK</span></span>

<span data-ttu-id="d5cc2-132">El SDK y las herramientas de línea de comandos de las aplicaciones .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d5cc2-132">The SDK and command-line tools for .NET Core apps.</span></span>

> [!div class="nextstepaction"]
> <span data-ttu-id="d5cc2-133">[Download .NET Core SDK](https://dotnet.microsoft.com/download) (Descarga del SDK de .NET Core)</span><span class="sxs-lookup"><span data-stu-id="d5cc2-133">[Download .NET Core SDK](https://dotnet.microsoft.com/download)</span></span>

### <a name="step-2-visual-studio-code"></a><span data-ttu-id="d5cc2-134">Paso 2: Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="d5cc2-134">Step 2: Visual Studio Code</span></span>

<span data-ttu-id="d5cc2-135">Edite y depure aplicaciones .NET Core en cualquier sistema operativo: Windows, Mac y Linux.</span><span class="sxs-lookup"><span data-stu-id="d5cc2-135">Edit and debug .NET Core apps on any operating system: Windows, Mac, and Linux.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d5cc2-136">Descargar Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="d5cc2-136">Download Visual Studio Code</span></span>](https://code.visualstudio.com)

---
