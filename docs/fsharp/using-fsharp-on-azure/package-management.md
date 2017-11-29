---
title: "Uso de administración de paquetes con F # para Azure"
description: 'Usar Paket o Nuget para administrar las dependencias de Azure de F #'
keywords: "Visual f #, f #, funcional de programación,. NET, .NET Core, Azure"
author: sylvanc
ms.author: phcart
ms.date: 09/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: dd32ef9c-5416-467e-9fa3-c9ee3bb08456
ms.openlocfilehash: 22dc94ea69e0dfb95e22da4bc64ce915398190d2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="package-management-for-f-azure-dependencies"></a><span data-ttu-id="fc5c1-104">Administración de paquetes para las dependencias de Azure de F #</span><span class="sxs-lookup"><span data-stu-id="fc5c1-104">Package Management for F# Azure Dependencies</span></span>

<span data-ttu-id="fc5c1-105">Obtención de paquetes para el desarrollo de Azure es fácil cuando se usa un administrador de paquetes.</span><span class="sxs-lookup"><span data-stu-id="fc5c1-105">Obtaining packages for Azure development is easy when you use a package manager.</span></span> <span data-ttu-id="fc5c1-106">Las dos opciones son [Paket](https://fsprojects.github.io/Paket/) y [NuGet](https://www.nuget.org/).</span><span class="sxs-lookup"><span data-stu-id="fc5c1-106">The two options are [Paket](https://fsprojects.github.io/Paket/) and [NuGet](https://www.nuget.org/).</span></span>

## <a name="using-paket"></a><span data-ttu-id="fc5c1-107">Usar Paket</span><span class="sxs-lookup"><span data-stu-id="fc5c1-107">Using Paket</span></span>

<span data-ttu-id="fc5c1-108">Si usas [Paket](https://fsprojects.github.io/Paket/) como el Administrador de la dependencia, puede utilizar el `paket.exe` herramienta para agregar dependencias de Azure.</span><span class="sxs-lookup"><span data-stu-id="fc5c1-108">If you're using [Paket](https://fsprojects.github.io/Paket/) as your dependency manager, you can use the `paket.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="fc5c1-109">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fc5c1-109">For example:</span></span>

    > paket add nuget WindowsAzure.Storage

<span data-ttu-id="fc5c1-110">O bien, si usa [Mono](http://www.mono-project.com/) para el desarrollo de .NET de multiplataforma:</span><span class="sxs-lookup"><span data-stu-id="fc5c1-110">Or, if you're using [Mono](http://www.mono-project.com/) for cross-platform .NET development:</span></span>

    > mono paket.exe add nuget WindowsAzure.Storage

<span data-ttu-id="fc5c1-111">Esto agregará `WindowsAzure.Storage` para el conjunto de dependencias de paquete para el proyecto en el directorio actual, modifique la `paket.dependencies` de archivos y descargar el paquete.</span><span class="sxs-lookup"><span data-stu-id="fc5c1-111">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, modify the `paket.dependencies` file, and download the package.</span></span> <span data-ttu-id="fc5c1-112">Si se ha establecido previamente las dependencias o está trabajando con un proyecto que se han configurado las dependencias con otros desarrolladores, puede resolver e instalar las dependencias de forma local como el siguiente:</span><span class="sxs-lookup"><span data-stu-id="fc5c1-112">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

    > paket install

<span data-ttu-id="fc5c1-113">O bien, para el desarrollo de Mono:</span><span class="sxs-lookup"><span data-stu-id="fc5c1-113">Or, for Mono development:</span></span>

    > mono paket.exe install

<span data-ttu-id="fc5c1-114">Puede actualizar todas las dependencias de paquete a la versión más reciente similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="fc5c1-114">You can update all your package dependencies to the latest version like this:</span></span>

    > paket update

<span data-ttu-id="fc5c1-115">O bien, para el desarrollo de Mono:</span><span class="sxs-lookup"><span data-stu-id="fc5c1-115">Or, for Mono development:</span></span>

    > mono paket.exe update

## <a name="using-nuget"></a><span data-ttu-id="fc5c1-116">Uso de Nuget</span><span class="sxs-lookup"><span data-stu-id="fc5c1-116">Using Nuget</span></span>

<span data-ttu-id="fc5c1-117">Si usas [NuGet](https://www.nuget.org/) como el Administrador de la dependencia, puede utilizar el `nuget.exe` herramienta para agregar dependencias de Azure.</span><span class="sxs-lookup"><span data-stu-id="fc5c1-117">If you're using [NuGet](https://www.nuget.org/) as your dependency manager, you can use the `nuget.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="fc5c1-118">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fc5c1-118">For example:</span></span>

    > nuget install WindowsAzure.Storage -ExcludeVersion

<span data-ttu-id="fc5c1-119">O bien, para el desarrollo de Mono:</span><span class="sxs-lookup"><span data-stu-id="fc5c1-119">Or, for Mono development:</span></span>

    > mono nuget.exe install WindowsAzure.Storage -ExcludeVersion

<span data-ttu-id="fc5c1-120">Esto agregará `WindowsAzure.Storage` al conjunto de dependencias del paquete para el proyecto en el directorio actual y descargue el paquete.</span><span class="sxs-lookup"><span data-stu-id="fc5c1-120">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, and download the package.</span></span> <span data-ttu-id="fc5c1-121">Si se ha establecido previamente las dependencias o está trabajando con un proyecto que se han configurado las dependencias con otros desarrolladores, puede resolver e instalar las dependencias de forma local como el siguiente:</span><span class="sxs-lookup"><span data-stu-id="fc5c1-121">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

    > nuget restore 

<span data-ttu-id="fc5c1-122">O bien, para el desarrollo de Mono:</span><span class="sxs-lookup"><span data-stu-id="fc5c1-122">Or, for Mono development:</span></span>

    > mono nuget.exe restore

<span data-ttu-id="fc5c1-123">Puede actualizar todas las dependencias de paquete a la versión más reciente similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="fc5c1-123">You can update all your package dependencies to the latest version like this:</span></span>

    > nuget update

<span data-ttu-id="fc5c1-124">O bien, para el desarrollo de Mono:</span><span class="sxs-lookup"><span data-stu-id="fc5c1-124">Or, for Mono development:</span></span>

    > mono nuget.exe update

## <a name="referencing-assemblies"></a><span data-ttu-id="fc5c1-125">Referencia a ensamblados</span><span class="sxs-lookup"><span data-stu-id="fc5c1-125">Referencing Assemblies</span></span>

<span data-ttu-id="fc5c1-126">Para utilizar los paquetes en el script de F #, tiene que hacer referencia a los ensamblados incluidos en los paquetes mediante un `#r` directiva.</span><span class="sxs-lookup"><span data-stu-id="fc5c1-126">In order to use your packages in your F# script, you need to reference the assemblies included in the packages using a `#r` directive.</span></span> <span data-ttu-id="fc5c1-127">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fc5c1-127">For example:</span></span>

    > #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"

<span data-ttu-id="fc5c1-128">Como puede ver, debe especificar la ruta de acceso relativa del archivo DLL y el nombre completo de DLL, que puede no ser exactamente el mismo que el nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="fc5c1-128">As you can see, you'll need to specify the relative path to the DLL and the full DLL name, which may not be exactly the same as the package name.</span></span> <span data-ttu-id="fc5c1-129">La ruta de acceso incluye una versión de framework y, posiblemente, un número de versión del paquete.</span><span class="sxs-lookup"><span data-stu-id="fc5c1-129">The path will include a framework version and possibly a package version number.</span></span> <span data-ttu-id="fc5c1-130">Para buscar todos los ensamblados instalados, puede usar algo parecido a esto en una línea de comandos de Windows:</span><span class="sxs-lookup"><span data-stu-id="fc5c1-130">To find all the installed assemblies, you can use something like this on a Windows command line:</span></span>

    > cd packages/WindowsAzure.Storage
    > dir /s/b *.dll

<span data-ttu-id="fc5c1-131">O bien, en un shell de Unix, algo similar a éste:</span><span class="sxs-lookup"><span data-stu-id="fc5c1-131">Or in a Unix shell, something like this:</span></span>

    > find packages/WindowsAzure.Storage -name "*.dll"

<span data-ttu-id="fc5c1-132">Esto le proporcionará las rutas de acceso a los ensamblados instalados.</span><span class="sxs-lookup"><span data-stu-id="fc5c1-132">This will give you the paths to the installed assemblies.</span></span> <span data-ttu-id="fc5c1-133">Desde allí, puede seleccionar la ruta de acceso correcta para su versión de framework.</span><span class="sxs-lookup"><span data-stu-id="fc5c1-133">From there, you can select the correct path for your framework version.</span></span>
