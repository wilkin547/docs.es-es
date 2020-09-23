---
title: 'Uso de Administración de paquetes con F # para Azure'
description: 'Uso de Paket o Nuget para administrar las dependencias de Azure de F #'
author: sylvanc
ms.date: 09/20/2016
ms.custom: devx-track-fsharp
ms.openlocfilehash: 011a363b264079599e8b7d402fe9896045b1fe04
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91100118"
---
# <a name="package-management-for-f-azure-dependencies"></a><span data-ttu-id="be509-103">Administración de paquetes para las dependencias de Azure de F #</span><span class="sxs-lookup"><span data-stu-id="be509-103">Package Management for F# Azure Dependencies</span></span>

<span data-ttu-id="be509-104">La obtención de paquetes para el desarrollo de Azure es fácil cuando se usa un administrador de paquetes.</span><span class="sxs-lookup"><span data-stu-id="be509-104">Obtaining packages for Azure development is easy when you use a package manager.</span></span> <span data-ttu-id="be509-105">Las dos opciones son [Paket](https://fsprojects.github.io/Paket/) y [NuGet](https://www.nuget.org/).</span><span class="sxs-lookup"><span data-stu-id="be509-105">The two options are [Paket](https://fsprojects.github.io/Paket/) and [NuGet](https://www.nuget.org/).</span></span>

## <a name="using-paket"></a><span data-ttu-id="be509-106">Usar Paket</span><span class="sxs-lookup"><span data-stu-id="be509-106">Using Paket</span></span>

<span data-ttu-id="be509-107">Si usa [Paket](https://fsprojects.github.io/Paket/) como administrador de dependencias, puede usar la `paket.exe` herramienta para agregar dependencias de Azure.</span><span class="sxs-lookup"><span data-stu-id="be509-107">If you're using [Paket](https://fsprojects.github.io/Paket/) as your dependency manager, you can use the `paket.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="be509-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="be509-108">For example:</span></span>

```console
> paket add nuget WindowsAzure.Storage
```

<span data-ttu-id="be509-109">O bien, si usa [mono](https://www.mono-project.com/) para el desarrollo .net multiplataforma:</span><span class="sxs-lookup"><span data-stu-id="be509-109">Or, if you're using [Mono](https://www.mono-project.com/) for cross-platform .NET development:</span></span>

```console
> mono paket.exe add nuget WindowsAzure.Storage
```

<span data-ttu-id="be509-110">Esto agregará `WindowsAzure.Storage` al conjunto de dependencias de paquete del proyecto en el directorio actual, modificará el `paket.dependencies` archivo y descargará el paquete.</span><span class="sxs-lookup"><span data-stu-id="be509-110">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, modify the `paket.dependencies` file, and download the package.</span></span> <span data-ttu-id="be509-111">Si ha configurado previamente las dependencias o está trabajando con un proyecto en el que otro desarrollador ha configurado las dependencias, puede resolver e instalar las dependencias localmente de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="be509-111">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

```console
> paket install
```

<span data-ttu-id="be509-112">O para el desarrollo en mono:</span><span class="sxs-lookup"><span data-stu-id="be509-112">Or, for Mono development:</span></span>

```console
> mono paket.exe install
```

<span data-ttu-id="be509-113">Puede actualizar todas las dependencias del paquete a la versión más reciente de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="be509-113">You can update all your package dependencies to the latest version like this:</span></span>

```console
> paket update
```

<span data-ttu-id="be509-114">O para el desarrollo en mono:</span><span class="sxs-lookup"><span data-stu-id="be509-114">Or, for Mono development:</span></span>

```console
> mono paket.exe update
```

## <a name="using-nuget"></a><span data-ttu-id="be509-115">Uso de Nuget</span><span class="sxs-lookup"><span data-stu-id="be509-115">Using Nuget</span></span>

<span data-ttu-id="be509-116">Si usa [NuGet](https://www.nuget.org/) como administrador de dependencias, puede usar la `nuget.exe` herramienta para agregar dependencias de Azure.</span><span class="sxs-lookup"><span data-stu-id="be509-116">If you're using [NuGet](https://www.nuget.org/) as your dependency manager, you can use the `nuget.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="be509-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="be509-117">For example:</span></span>

```console
> nuget install WindowsAzure.Storage -ExcludeVersion
```

<span data-ttu-id="be509-118">O para el desarrollo en mono:</span><span class="sxs-lookup"><span data-stu-id="be509-118">Or, for Mono development:</span></span>

```console
> mono nuget.exe install WindowsAzure.Storage -ExcludeVersion
```

<span data-ttu-id="be509-119">Esto agregará `WindowsAzure.Storage` al conjunto de dependencias de paquete del proyecto en el directorio actual y descargará el paquete.</span><span class="sxs-lookup"><span data-stu-id="be509-119">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, and download the package.</span></span> <span data-ttu-id="be509-120">Si ha configurado previamente las dependencias o está trabajando con un proyecto en el que otro desarrollador ha configurado las dependencias, puede resolver e instalar las dependencias localmente de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="be509-120">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

```console
> nuget restore
```

<span data-ttu-id="be509-121">O para el desarrollo en mono:</span><span class="sxs-lookup"><span data-stu-id="be509-121">Or, for Mono development:</span></span>

```console
> mono nuget.exe restore
```

<span data-ttu-id="be509-122">Puede actualizar todas las dependencias del paquete a la versión más reciente de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="be509-122">You can update all your package dependencies to the latest version like this:</span></span>

```console
> nuget update
```

<span data-ttu-id="be509-123">O para el desarrollo en mono:</span><span class="sxs-lookup"><span data-stu-id="be509-123">Or, for Mono development:</span></span>

```console
> mono nuget.exe update
```

## <a name="referencing-assemblies"></a><span data-ttu-id="be509-124">Referencia a ensamblados</span><span class="sxs-lookup"><span data-stu-id="be509-124">Referencing Assemblies</span></span>

<span data-ttu-id="be509-125">Para usar los paquetes en el script de F #, debe hacer referencia a los ensamblados incluidos en los paquetes mediante una `#r` Directiva.</span><span class="sxs-lookup"><span data-stu-id="be509-125">In order to use your packages in your F# script, you need to reference the assemblies included in the packages using a `#r` directive.</span></span> <span data-ttu-id="be509-126">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="be509-126">For example:</span></span>

```fsharp
> #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"
```

<span data-ttu-id="be509-127">Como puede ver, debe especificar la ruta de acceso relativa a la DLL y el nombre completo de la DLL, que puede no ser exactamente igual que el nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="be509-127">As you can see, you'll need to specify the relative path to the DLL and the full DLL name, which may not be exactly the same as the package name.</span></span> <span data-ttu-id="be509-128">La ruta de acceso incluirá una versión de .NET Framework y, posiblemente, un número de versión del paquete.</span><span class="sxs-lookup"><span data-stu-id="be509-128">The path will include a framework version and possibly a package version number.</span></span> <span data-ttu-id="be509-129">Para encontrar todos los ensamblados instalados, puede usar algo parecido a esto en una línea de comandos de Windows:</span><span class="sxs-lookup"><span data-stu-id="be509-129">To find all the installed assemblies, you can use something like this on a Windows command line:</span></span>

```console
> cd packages/WindowsAzure.Storage
> dir /s/b *.dll
```

<span data-ttu-id="be509-130">O en un shell de UNIX, algo parecido a esto:</span><span class="sxs-lookup"><span data-stu-id="be509-130">Or in a Unix shell, something like this:</span></span>

```console
> find packages/WindowsAzure.Storage -name "*.dll"
```

<span data-ttu-id="be509-131">Esto le proporcionará las rutas de acceso a los ensamblados instalados.</span><span class="sxs-lookup"><span data-stu-id="be509-131">This will give you the paths to the installed assemblies.</span></span> <span data-ttu-id="be509-132">Desde allí, puede seleccionar la ruta de acceso correcta para la versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="be509-132">From there, you can select the correct path for your framework version.</span></span>
