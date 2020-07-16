---
title: Herramientas para desarrolladores de .NET de Azure
description: Obtenga las herramientas para empezar a usar las bibliotecas .NET de Azure desde un entorno de Windows, Linux y Mac.
ms.date: 06/19/2020
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: fa645b152f15550b25a3542ba0cdbb43799536b9
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174879"
---
# <a name="azure-tools-for-developing-with-net"></a><span data-ttu-id="348f1-103">Azure Tools para desarrollar con .NET</span><span class="sxs-lookup"><span data-stu-id="348f1-103">Azure tools for developing with .NET</span></span>

## <a name="sdk-downloads"></a><span data-ttu-id="348f1-104">Descargas de SDK</span><span class="sxs-lookup"><span data-stu-id="348f1-104">SDK downloads</span></span>

<span data-ttu-id="348f1-105">Las bibliotecas de Azure para .NET se implementan como [paquetes NuGet](https://www.nuget.org/packages?q=windowsazureofficial).</span><span class="sxs-lookup"><span data-stu-id="348f1-105">Azure libraries for .NET are implemented as [NuGet packages](https://www.nuget.org/packages?q=windowsazureofficial).</span></span> <span data-ttu-id="348f1-106">Consulte la [referencia de API](/dotnet/api/overview/azure/?view=azure-dotnet) para obtener documentación de referencia organizada por el servicio de Azure.</span><span class="sxs-lookup"><span data-stu-id="348f1-106">See the [API Reference](/dotnet/api/overview/azure/?view=azure-dotnet) for reference documentation organized by Azure service.</span></span>

## <a name="development-tools"></a><span data-ttu-id="348f1-107">Herramientas de desarrollo</span><span class="sxs-lookup"><span data-stu-id="348f1-107">Development tools</span></span>

<span data-ttu-id="348f1-108">Visual Studio tiene integradas herramientas para muchos servicios de Azure.</span><span class="sxs-lookup"><span data-stu-id="348f1-108">Visual Studio has tooling for many Azure services built-in.</span></span> <span data-ttu-id="348f1-109">Algunos servicios de Azure disponen de más herramientas o emuladores, como el [Explorador de Azure Storage](https://azure.microsoft.com/features/storage-explorer/).</span><span class="sxs-lookup"><span data-stu-id="348f1-109">Some Azure services have additional tools or emulators available, such as [Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/).</span></span> <span data-ttu-id="348f1-110">Consulte la documentación del servicio de Azure correspondiente para ver las herramientas adicionales si así lo precisa.</span><span class="sxs-lookup"><span data-stu-id="348f1-110">See the documentation for your Azure service for any additional tools, if necessary.</span></span>

<span data-ttu-id="348f1-111">Seleccione a continuación el entorno de desarrollo que prefiera.</span><span class="sxs-lookup"><span data-stu-id="348f1-111">Select your preferred development environment below.</span></span>

## <a name="visual-studio-on-windows"></a>[<span data-ttu-id="348f1-112">Visual Studio en Windows</span><span class="sxs-lookup"><span data-stu-id="348f1-112">Visual Studio on Windows</span></span>](#tab/vs)

<span data-ttu-id="348f1-113">La versión 2017 y posteriores de Visual Studio incluyen compatibilidad integrada con el desarrollo de Azure.</span><span class="sxs-lookup"><span data-stu-id="348f1-113">Visual Studio version 2017 and later have built-in support for Azure development.</span></span> <span data-ttu-id="348f1-114">Los siguientes pasos describen cómo habilitar la compatibilidad con el desarrollo de Azure en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="348f1-114">The below steps describe enabling Azure development support in Visual Studio.</span></span>

<span data-ttu-id="348f1-115"><a href="vs2015-install.md">Siga estas instrucciones</a> con Visual Studio 2015 y versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="348f1-115">For Visual Studio 2015 and earlier, <a href="vs2015-install.md">follow these instructions</a>.</span></span>

### <a name="step-1-download-visual-studio-2019"></a><span data-ttu-id="348f1-116">Paso 1: Descargar Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="348f1-116">Step 1: Download Visual Studio 2019</span></span>

<span data-ttu-id="348f1-117">Si ya tiene instalado Visual Studio 2019, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="348f1-117">You can skip this step if you already have Visual Studio 2019 installed.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="348f1-118">Descargar Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="348f1-118">Download Visual Studio 2019</span></span>](https://www.visualstudio.com/downloads/)

### <a name="step-2-install-the-two-azure-workloads"></a><span data-ttu-id="348f1-119">Paso 2: Instalación de las dos cargas de trabajo de Azure</span><span class="sxs-lookup"><span data-stu-id="348f1-119">Step 2: Install the two Azure workloads</span></span>

<span data-ttu-id="348f1-120">En el instalador de Visual Studio, instale Visual Studio (o modifique una instalación existente).</span><span class="sxs-lookup"><span data-stu-id="348f1-120">In the Visual Studio installer, install Visual Studio (or modify an existing installation).</span></span> <span data-ttu-id="348f1-121">Asegúrese de que las cargas de trabajo *Desarrollo de Azure* y *Desarrollo de ASP.NET y web* están seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="348f1-121">Make sure the *Azure development* and *ASP.NET and web development* workloads are selected.</span></span>

### <a name="step-3-develop-with-net-on-azure"></a><span data-ttu-id="348f1-122">Paso 3: Desarrollo con .NET en Azure</span><span class="sxs-lookup"><span data-stu-id="348f1-122">Step 3: Develop with .NET on Azure</span></span>

<span data-ttu-id="348f1-123">Comience por [implementar su primera aplicación web ASP.NET Core en Azure App Service](/azure/app-service-web/app-service-web-get-started-dotnet).</span><span class="sxs-lookup"><span data-stu-id="348f1-123">Get started by [deploying your first ASP.NET Core web app on Azure App Service](/azure/app-service-web/app-service-web-get-started-dotnet).</span></span>

## <a name="visual-studio-code-cross-platform"></a>[<span data-ttu-id="348f1-124">Visual Studio Code (multiplataforma)</span><span class="sxs-lookup"><span data-stu-id="348f1-124">Visual Studio Code (cross-platform)</span></span>](#tab/vscode)

<span data-ttu-id="348f1-125">Visual Studio Code tiene todo lo que necesita para el desarrollo multiplataforma de Azure.</span><span class="sxs-lookup"><span data-stu-id="348f1-125">Visual Studio Code has everything you need for cross-platform Azure development.</span></span>

### <a name="step-1-download-the-net-core-sdk"></a><span data-ttu-id="348f1-126">Paso 1: Descarga del SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="348f1-126">Step 1: Download the .NET Core SDK</span></span>

<span data-ttu-id="348f1-127">El SDK y las herramientas de línea de comandos de las aplicaciones .NET Core.</span><span class="sxs-lookup"><span data-stu-id="348f1-127">The SDK and command-line tools for .NET Core apps.</span></span>

> [!div class="nextstepaction"]
> <span data-ttu-id="348f1-128">[Download .NET Core SDK](https://dotnet.microsoft.com/download) (Descarga del SDK de .NET Core)</span><span class="sxs-lookup"><span data-stu-id="348f1-128">[Download .NET Core SDK](https://dotnet.microsoft.com/download)</span></span>

### <a name="step-2-visual-studio-code"></a><span data-ttu-id="348f1-129">Paso 2: Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="348f1-129">Step 2: Visual Studio Code</span></span>

<span data-ttu-id="348f1-130">Edite y depure aplicaciones .NET Core en cualquier sistema operativo: Windows, Mac y Linux.</span><span class="sxs-lookup"><span data-stu-id="348f1-130">Edit and debug .NET Core apps on any operating system: Windows, Mac, and Linux.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="348f1-131">Descargar Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="348f1-131">Download Visual Studio Code</span></span>](https://code.visualstudio.com)

### <a name="step-3-azure-tools-extension"></a><span data-ttu-id="348f1-132">Paso 3: Extensión de Azure Tools</span><span class="sxs-lookup"><span data-stu-id="348f1-132">Step 3: Azure Tools extension</span></span>

<span data-ttu-id="348f1-133">Instale la extensión de Azure Tools en Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="348f1-133">Install the Azure Tools extension in Visual Studio Code.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="348f1-134">Instalación de la extensión de Azure Tools</span><span class="sxs-lookup"><span data-stu-id="348f1-134">Install Azure Tools extension</span></span>](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-node-azure-pack)

### <a name="step-4-develop-with-net-on-azure"></a><span data-ttu-id="348f1-135">Paso 4: Desarrollo con .NET en Azure</span><span class="sxs-lookup"><span data-stu-id="348f1-135">Step 4: Develop with .NET on Azure</span></span>

<span data-ttu-id="348f1-136">Comience por [implementar su primera aplicación web ASP.NET Core en Azure App Service en Linux](/azure/app-service/containers/quickstart-dotnetcore).</span><span class="sxs-lookup"><span data-stu-id="348f1-136">Get started by [deploying your first ASP.NET Core web app on Azure App Service on Linux](/azure/app-service/containers/quickstart-dotnetcore).</span></span>

---
