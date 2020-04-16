---
title: Herramientas para desarrolladores de .NET y .NET Core de Azure
description: Obtenga las herramientas para empezar a usar las bibliotecas .NET de Azure desde un entorno de Windows, Linux y Mac.
ms.date: 10/01/2018
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: 1c6370e4b3e5e6e901ba6ef56c65d794f3da5abe
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2020
ms.locfileid: "81433167"
---
# <a name="tools-for-net-and-net-core-azure-developers"></a><span data-ttu-id="ead0e-103">Herramientas para desarrolladores de .NET y .NET Core de Azure</span><span class="sxs-lookup"><span data-stu-id="ead0e-103">Tools for .NET and .NET Core Azure developers</span></span>

## <a name="sdk-downloads"></a><span data-ttu-id="ead0e-104">Descargas de SDK</span><span class="sxs-lookup"><span data-stu-id="ead0e-104">SDK downloads</span></span>

<span data-ttu-id="ead0e-105">Las bibliotecas de Azure para .NET se implementan como [paquetes NuGet.](https://www.nuget.org/packages?q=windowsazureofficial)</span><span class="sxs-lookup"><span data-stu-id="ead0e-105">Azure libraries for .NET are implemented as [NuGet packages](https://www.nuget.org/packages?q=windowsazureofficial).</span></span> <span data-ttu-id="ead0e-106">Consulte la Referencia de [la API](/dotnet/api/overview/azure/?view=azure-dotnet) para obtener instrucciones de instalación organizadas por el servicio Azure.</span><span class="sxs-lookup"><span data-stu-id="ead0e-106">See the [API Reference](/dotnet/api/overview/azure/?view=azure-dotnet) for installation instructions organized by Azure service.</span></span>

## <a name="development-tools"></a><span data-ttu-id="ead0e-107">Herramientas de desarrollo</span><span class="sxs-lookup"><span data-stu-id="ead0e-107">Development tools</span></span>

<span data-ttu-id="ead0e-108">Visual Studio tiene herramientas para muchos servicios de Azure integrados.</span><span class="sxs-lookup"><span data-stu-id="ead0e-108">Visual Studio has tooling for many Azure services built-in.</span></span> <span data-ttu-id="ead0e-109">Algunos servicios de Azure tienen herramientas o emuladores adicionales disponibles, como el Explorador de [Azure Storage](https://azure.microsoft.com/features/storage-explorer/).</span><span class="sxs-lookup"><span data-stu-id="ead0e-109">Some Azure services have additional tools or emulators available, such as [Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/).</span></span> <span data-ttu-id="ead0e-110">Consulte la documentación del servicio de Azure para ver si es necesario las herramientas adicionales.</span><span class="sxs-lookup"><span data-stu-id="ead0e-110">See the documentation for your Azure service for any additional tools, if necessary.</span></span>

<span data-ttu-id="ead0e-111">Estas instrucciones instalan el entorno de desarrollo de inicio recomendado para el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="ead0e-111">These instructions install the recommended starting development environment for your operating system.</span></span>

## <a name="windows"></a>[<span data-ttu-id="ead0e-112">Windows</span><span class="sxs-lookup"><span data-stu-id="ead0e-112">Windows</span></span>](#tab/windows)

<span data-ttu-id="ead0e-113">Las versiones de Visual Studio 2017 y versiones posteriores tienen compatibilidad integrada para el desarrollo de Azure.</span><span class="sxs-lookup"><span data-stu-id="ead0e-113">Visual Studio versions 2017 and later have built-in support for Azure development.</span></span> <span data-ttu-id="ead0e-114">Los pasos siguientes describen habilitar la compatibilidad de desarrollo de Azure en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ead0e-114">The below steps describe enabling Azure development support in Visual Studio.</span></span>

<span data-ttu-id="ead0e-115">Para Visual Studio 2015 y versiones anteriores, <a href="vs2015-install.md">siga estas instrucciones.</a></span><span class="sxs-lookup"><span data-stu-id="ead0e-115">For Visual Studio 2015 and earlier, <a href="vs2015-install.md">follow these instructions</a>.</span></span>

### <a name="step-1-download-visual-studio-2019"></a><span data-ttu-id="ead0e-116">Paso 1: Descargar Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="ead0e-116">Step 1: Download Visual Studio 2019</span></span>

<span data-ttu-id="ead0e-117">Puede omitir este paso si ya tiene Visual Studio 2019 instalado.</span><span class="sxs-lookup"><span data-stu-id="ead0e-117">You can skip this step if you already have Visual Studio 2019 installed.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ead0e-118">Descargar Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="ead0e-118">Download Visual Studio 2019</span></span>](https://www.visualstudio.com/downloads/)

### <a name="step-2-install-the-two-azure-workloads"></a><span data-ttu-id="ead0e-119">Paso 2: Instalación de las dos cargas de trabajo de Azure</span><span class="sxs-lookup"><span data-stu-id="ead0e-119">Step 2: Install the two Azure workloads</span></span>

<span data-ttu-id="ead0e-120">En el instalador de Visual Studio, instale Visual Studio (o modifique una instalación existente).</span><span class="sxs-lookup"><span data-stu-id="ead0e-120">In the Visual Studio installer, install Visual Studio (or modify an existing installation).</span></span> <span data-ttu-id="ead0e-121">Asegúrese de que las cargas de trabajo de desarrollo y *ASP.NET y desarrollo web* de *Azure* están seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="ead0e-121">Make sure the *Azure development* and *ASP.NET and web development* workloads are selected.</span></span>

### <a name="step-3-develop-with-net-on-azure"></a><span data-ttu-id="ead0e-122">Paso 3: Desarrollo con .NET en Azure</span><span class="sxs-lookup"><span data-stu-id="ead0e-122">Step 3: Develop with .NET on Azure</span></span>

<span data-ttu-id="ead0e-123">Comience por [implementar su primera aplicación web ASP.NET Core en Azure App Service](https://docs.microsoft.com/azure/app-service-web/app-service-web-get-started-dotnet).</span><span class="sxs-lookup"><span data-stu-id="ead0e-123">Get started by [deploying your first ASP.NET Core web app on Azure App Service](https://docs.microsoft.com/azure/app-service-web/app-service-web-get-started-dotnet).</span></span>

## <a name="macos"></a>[<span data-ttu-id="ead0e-124">macOS</span><span class="sxs-lookup"><span data-stu-id="ead0e-124">macOS</span></span>](#tab/macos)

<span data-ttu-id="ead0e-125">Visual Studio para Mac tiene todo lo que necesita para el desarrollo de Azure.</span><span class="sxs-lookup"><span data-stu-id="ead0e-125">Visual Studio for Mac has everything you need for Azure development.</span></span>

### <a name="step-1-download-visual-studio-for-mac"></a><span data-ttu-id="ead0e-126">Paso 1: Descarga de Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="ead0e-126">Step 1: Download Visual Studio for Mac</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ead0e-127">Descargar Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="ead0e-127">Download Visual Studio for Mac</span></span>](https://www.visualstudio.com/vs/visual-studio-mac/)

<span data-ttu-id="ead0e-128">Durante la instalación, las herramientas de Azure se seleccionan de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ead0e-128">During installation, Azure tools are selected by default.</span></span>

## <a name="linux"></a>[<span data-ttu-id="ead0e-129">Linux</span><span class="sxs-lookup"><span data-stu-id="ead0e-129">Linux</span></span>](#tab/linux)

<span data-ttu-id="ead0e-130">Visual Studio Code tiene todo lo que necesita para el desarrollo de Azure en Linux.</span><span class="sxs-lookup"><span data-stu-id="ead0e-130">Visual Studio Code has everything you need for Azure development on Linux.</span></span>

### <a name="step-1-download-the-net-core-sdk"></a><span data-ttu-id="ead0e-131">Step 1: Descarga del SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="ead0e-131">Step 1: Download the .NET Core SDK</span></span>

<span data-ttu-id="ead0e-132">El SDK y las herramientas de línea de comandos de las aplicaciones .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ead0e-132">The SDK and command-line tools for .NET Core apps.</span></span>

> [!div class="nextstepaction"]
> <span data-ttu-id="ead0e-133">[Download .NET Core SDK](https://dotnet.microsoft.com/download) (Descarga del SDK de .NET Core)</span><span class="sxs-lookup"><span data-stu-id="ead0e-133">[Download .NET Core SDK](https://dotnet.microsoft.com/download)</span></span>

### <a name="step-2-visual-studio-code"></a><span data-ttu-id="ead0e-134">Paso 2: Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="ead0e-134">Step 2: Visual Studio Code</span></span>

<span data-ttu-id="ead0e-135">Edite y depure aplicaciones .NET Core en cualquier sistema operativo: Windows, Mac y Linux.</span><span class="sxs-lookup"><span data-stu-id="ead0e-135">Edit and debug .NET Core apps on any operating system: Windows, Mac, and Linux.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ead0e-136">Descarga de Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="ead0e-136">Download Visual Studio Code</span></span>](https://code.visualstudio.com)

---
