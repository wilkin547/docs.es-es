---
title: Uso de administración de paquetes con F# para Azure
description: Usar Paket o Nuget para administrar F# dependencias de Azure
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: b180024e2276a2fd7786f35cb922b1aa1d91f0ad
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880016"
---
# <a name="package-management-for-f-azure-dependencies"></a><span data-ttu-id="e290c-103">Administración de paquetes para las dependencias de Azure de F #</span><span class="sxs-lookup"><span data-stu-id="e290c-103">Package Management for F# Azure Dependencies</span></span>

<span data-ttu-id="e290c-104">Obtención de paquetes para el desarrollo de Azure es fácil cuando se usa un administrador de paquetes.</span><span class="sxs-lookup"><span data-stu-id="e290c-104">Obtaining packages for Azure development is easy when you use a package manager.</span></span> <span data-ttu-id="e290c-105">Las dos opciones son [Paket](https://fsprojects.github.io/Paket/) y [NuGet](https://www.nuget.org/).</span><span class="sxs-lookup"><span data-stu-id="e290c-105">The two options are [Paket](https://fsprojects.github.io/Paket/) and [NuGet](https://www.nuget.org/).</span></span>

## <a name="using-paket"></a><span data-ttu-id="e290c-106">Uso de Paket</span><span class="sxs-lookup"><span data-stu-id="e290c-106">Using Paket</span></span>

<span data-ttu-id="e290c-107">Si usas [Paket](https://fsprojects.github.io/Paket/) como su administrador de dependencias, puede usar el `paket.exe` herramienta para agregar dependencias de Azure.</span><span class="sxs-lookup"><span data-stu-id="e290c-107">If you're using [Paket](https://fsprojects.github.io/Paket/) as your dependency manager, you can use the `paket.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="e290c-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e290c-108">For example:</span></span>

```
> paket add nuget WindowsAzure.Storage
```

<span data-ttu-id="e290c-109">O bien, si usas [Mono](https://www.mono-project.com/) para el desarrollo de .NET multiplataforma:</span><span class="sxs-lookup"><span data-stu-id="e290c-109">Or, if you're using [Mono](https://www.mono-project.com/) for cross-platform .NET development:</span></span>

```
> mono paket.exe add nuget WindowsAzure.Storage
```

<span data-ttu-id="e290c-110">Esto agregará `WindowsAzure.Storage` en el conjunto de dependencias de paquete para el proyecto en el directorio actual, modifique la `paket.dependencies` de archivos y descargar el paquete.</span><span class="sxs-lookup"><span data-stu-id="e290c-110">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, modify the `paket.dependencies` file, and download the package.</span></span> <span data-ttu-id="e290c-111">Si ha configurado previamente las dependencias, o está trabajando con un proyecto donde se han configurado las dependencias por otro desarrollador, puede resolver e instalar las dependencias localmente como esto:</span><span class="sxs-lookup"><span data-stu-id="e290c-111">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

```
> paket install
```

<span data-ttu-id="e290c-112">O bien, para el desarrollo de Mono:</span><span class="sxs-lookup"><span data-stu-id="e290c-112">Or, for Mono development:</span></span>

```
> mono paket.exe install
```

<span data-ttu-id="e290c-113">Puede actualizar todas las dependencias de paquete a la versión más reciente similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="e290c-113">You can update all your package dependencies to the latest version like this:</span></span>

```
> paket update
```

<span data-ttu-id="e290c-114">O bien, para el desarrollo de Mono:</span><span class="sxs-lookup"><span data-stu-id="e290c-114">Or, for Mono development:</span></span>

```
> mono paket.exe update
```

## <a name="using-nuget"></a><span data-ttu-id="e290c-115">Uso de Nuget</span><span class="sxs-lookup"><span data-stu-id="e290c-115">Using Nuget</span></span>

<span data-ttu-id="e290c-116">Si usas [NuGet](https://www.nuget.org/) como su administrador de dependencias, puede usar el `nuget.exe` herramienta para agregar dependencias de Azure.</span><span class="sxs-lookup"><span data-stu-id="e290c-116">If you're using [NuGet](https://www.nuget.org/) as your dependency manager, you can use the `nuget.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="e290c-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e290c-117">For example:</span></span>

```
> nuget install WindowsAzure.Storage -ExcludeVersion
```

<span data-ttu-id="e290c-118">O bien, para el desarrollo de Mono:</span><span class="sxs-lookup"><span data-stu-id="e290c-118">Or, for Mono development:</span></span>

```
> mono nuget.exe install WindowsAzure.Storage -ExcludeVersion
```

<span data-ttu-id="e290c-119">Esto agregará `WindowsAzure.Storage` al conjunto de dependencias de paquete para el proyecto en el directorio actual y el paquete de descarga.</span><span class="sxs-lookup"><span data-stu-id="e290c-119">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, and download the package.</span></span> <span data-ttu-id="e290c-120">Si ha configurado previamente las dependencias, o está trabajando con un proyecto donde se han configurado las dependencias por otro desarrollador, puede resolver e instalar las dependencias localmente como esto:</span><span class="sxs-lookup"><span data-stu-id="e290c-120">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

```
> nuget restore
```

<span data-ttu-id="e290c-121">O bien, para el desarrollo de Mono:</span><span class="sxs-lookup"><span data-stu-id="e290c-121">Or, for Mono development:</span></span>

```
> mono nuget.exe restore
```

<span data-ttu-id="e290c-122">Puede actualizar todas las dependencias de paquete a la versión más reciente similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="e290c-122">You can update all your package dependencies to the latest version like this:</span></span>

```
> nuget update
```

<span data-ttu-id="e290c-123">O bien, para el desarrollo de Mono:</span><span class="sxs-lookup"><span data-stu-id="e290c-123">Or, for Mono development:</span></span>

```
> mono nuget.exe update
```

## <a name="referencing-assemblies"></a><span data-ttu-id="e290c-124">Referencia a ensamblados</span><span class="sxs-lookup"><span data-stu-id="e290c-124">Referencing Assemblies</span></span>

<span data-ttu-id="e290c-125">Para poder usar los paquetes en su F# secuencia de comandos, deberá hacer referencia a los ensamblados incluidos en los paquetes mediante un `#r` directiva.</span><span class="sxs-lookup"><span data-stu-id="e290c-125">In order to use your packages in your F# script, you need to reference the assemblies included in the packages using a `#r` directive.</span></span> <span data-ttu-id="e290c-126">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e290c-126">For example:</span></span>

```
> #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"
```

<span data-ttu-id="e290c-127">Como puede ver, deberá especificar la ruta de acceso relativa del archivo DLL y el nombre de archivo DLL completo, que es posible que no sea exactamente el mismo que el nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="e290c-127">As you can see, you'll need to specify the relative path to the DLL and the full DLL name, which may not be exactly the same as the package name.</span></span> <span data-ttu-id="e290c-128">La ruta de acceso incluirá una versión de .NET framework y, posiblemente, un número de versión del paquete.</span><span class="sxs-lookup"><span data-stu-id="e290c-128">The path will include a framework version and possibly a package version number.</span></span> <span data-ttu-id="e290c-129">Para buscar todos los ensamblados instalados, puede usar algo parecido a esto en una línea de comandos de Windows:</span><span class="sxs-lookup"><span data-stu-id="e290c-129">To find all the installed assemblies, you can use something like this on a Windows command line:</span></span>

```
> cd packages/WindowsAzure.Storage
> dir /s/b *.dll
```

<span data-ttu-id="e290c-130">O bien, en un shell de Unix, algo como esto:</span><span class="sxs-lookup"><span data-stu-id="e290c-130">Or in a Unix shell, something like this:</span></span>

```
> find packages/WindowsAzure.Storage -name "*.dll"
```

<span data-ttu-id="e290c-131">Esto le dará las rutas de acceso a los ensamblados instalados.</span><span class="sxs-lookup"><span data-stu-id="e290c-131">This will give you the paths to the installed assemblies.</span></span> <span data-ttu-id="e290c-132">Desde allí, puede seleccionar la ruta de acceso correcta para su versión de framework.</span><span class="sxs-lookup"><span data-stu-id="e290c-132">From there, you can select the correct path for your framework version.</span></span>
