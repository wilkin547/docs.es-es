---
title: Comando dotnet store
description: El comando “dotnet store” almacena los ensamblados especificados en el almacenamiento de paquetes en tiempo de ejecución.
ms.date: 05/29/2018
ms.openlocfilehash: cc5b4b6160ba296e1529f006c15e238746d9e08a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733053"
---
# <a name="dotnet-store"></a><span data-ttu-id="5caf9-103">dotnet store</span><span class="sxs-lookup"><span data-stu-id="5caf9-103">dotnet store</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]

## <a name="name"></a><span data-ttu-id="5caf9-104">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="5caf9-104">Name</span></span>

<span data-ttu-id="5caf9-105">`dotnet store`: almacena los ensamblados especificados en el [almacenamiento de paquetes en tiempo de ejecución](../deploying/runtime-store.md).</span><span class="sxs-lookup"><span data-stu-id="5caf9-105">`dotnet store` - Stores the specified assemblies in the [runtime package store](../deploying/runtime-store.md).</span></span>

## <a name="synopsis"></a><span data-ttu-id="5caf9-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="5caf9-106">Synopsis</span></span>

`dotnet store -m|--manifest -f|--framework -r|--runtime  [--framework-version] [-h|--help] [--output] [--skip-optimization] [--skip-symbols] [-v|--verbosity] [--working-dir]`

## <a name="description"></a><span data-ttu-id="5caf9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="5caf9-107">Description</span></span>

<span data-ttu-id="5caf9-108">`dotnet store` almacena los ensamblados especificados en el [almacenamiento de paquetes en tiempo de ejecución](../deploying/runtime-store.md).</span><span class="sxs-lookup"><span data-stu-id="5caf9-108">`dotnet store` stores the specified assemblies in the [runtime package store](../deploying/runtime-store.md).</span></span> <span data-ttu-id="5caf9-109">De forma predeterminada, los ensamblados están optimizados para el tiempo de ejecución y el marco de trabajo de destino.</span><span class="sxs-lookup"><span data-stu-id="5caf9-109">By default, assemblies are optimized for the target runtime and framework.</span></span> <span data-ttu-id="5caf9-110">Para obtener más información, consulte el tema [Almacenamiento de paquetes en tiempo de ejecución](../deploying/runtime-store.md).</span><span class="sxs-lookup"><span data-stu-id="5caf9-110">For more information, see the [runtime package store](../deploying/runtime-store.md) topic.</span></span>

## <a name="required-options"></a><span data-ttu-id="5caf9-111">Opciones necesarias</span><span class="sxs-lookup"><span data-stu-id="5caf9-111">Required options</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="5caf9-112">Especifica la [plataforma de destino](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="5caf9-112">Specifies the [target framework](../../standard/frameworks.md).</span></span>

`-m|--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="5caf9-113">El *archivo de manifiesto de almacenamiento de paquetes* es un archivo XML que contiene la lista de paquetes que se va a almacenar.</span><span class="sxs-lookup"><span data-stu-id="5caf9-113">The *package store manifest file* is an XML file that contains the list of packages to store.</span></span> <span data-ttu-id="5caf9-114">El formato del archivo de manifiesto es compatible con el formato de proyecto de estilo de SDK.</span><span class="sxs-lookup"><span data-stu-id="5caf9-114">The format of the manifest file is compatible with the SDK-style project format.</span></span> <span data-ttu-id="5caf9-115">Por tanto, se puede usar un archivo de proyecto que haga referencia a los paquetes deseados con la opción `-m|--manifest` para almacenar los ensamblados en el almacenamiento de paquetes en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5caf9-115">So, a project file that references the desired packages can be used with the `-m|--manifest` option to store assemblies in the runtime package store.</span></span> <span data-ttu-id="5caf9-116">Para especificar varios archivos de manifiesto, repita la opción y la ruta de acceso para cada archivo.</span><span class="sxs-lookup"><span data-stu-id="5caf9-116">To specify multiple manifest files, repeat the option and path for each file.</span></span> <span data-ttu-id="5caf9-117">Por ejemplo: `--manifest packages1.csproj --manifest packages2.csproj`.</span><span class="sxs-lookup"><span data-stu-id="5caf9-117">For example: `--manifest packages1.csproj --manifest packages2.csproj`.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="5caf9-118">El [identificador en tiempo de ejecución](../rid-catalog.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="5caf9-118">The [runtime identifier](../rid-catalog.md) to target.</span></span>

## <a name="optional-options"></a><span data-ttu-id="5caf9-119">Opciones no necesarias</span><span class="sxs-lookup"><span data-stu-id="5caf9-119">Optional options</span></span>

`--framework-version <FRAMEWORK_VERSION>`

<span data-ttu-id="5caf9-120">Especifica la versión del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5caf9-120">Specifies the .NET Core SDK version.</span></span> <span data-ttu-id="5caf9-121">Esta opción le permite seleccionar una versión de un marco concreto más allá del marco de trabajo especificado en la opción `-f|--framework`.</span><span class="sxs-lookup"><span data-stu-id="5caf9-121">This option enables you to select a specific framework version beyond the framework specified by the `-f|--framework` option.</span></span>

`-h|--help`

<span data-ttu-id="5caf9-122">Muestra información de ayuda.</span><span class="sxs-lookup"><span data-stu-id="5caf9-122">Shows help information.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="5caf9-123">Especifica la ruta de acceso al almacenamiento de paquetes en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5caf9-123">Specifies the path to the runtime package store.</span></span> <span data-ttu-id="5caf9-124">Si no se especifica, el valor predeterminado es el subdirectorio *store* del directorio de instalación de .NET Core de perfil de usuario.</span><span class="sxs-lookup"><span data-stu-id="5caf9-124">If not specified, it defaults to the *store* subdirectory of the user profile .NET Core installation directory.</span></span>

`--skip-optimization`

<span data-ttu-id="5caf9-125">Omite la fase de optimización.</span><span class="sxs-lookup"><span data-stu-id="5caf9-125">Skips the optimization phase.</span></span>

`--skip-symbols`

<span data-ttu-id="5caf9-126">Omite la generación de símbolos.</span><span class="sxs-lookup"><span data-stu-id="5caf9-126">Skips symbol generation.</span></span> <span data-ttu-id="5caf9-127">Actualmente, solo se pueden generar símbolos en Windows y Linux.</span><span class="sxs-lookup"><span data-stu-id="5caf9-127">Currently, you can only generate symbols on Windows and Linux.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="5caf9-128">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="5caf9-128">Sets the verbosity level of the command.</span></span> <span data-ttu-id="5caf9-129">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="5caf9-129">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`-w|--working-dir <INTERMEDIATE_WORKING_DIRECTORY>`

<span data-ttu-id="5caf9-130">El directorio de trabajo que usa el comando.</span><span class="sxs-lookup"><span data-stu-id="5caf9-130">The working directory used by the command.</span></span> <span data-ttu-id="5caf9-131">Si no se especifica, usa el subdirectorio *obj* del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="5caf9-131">If not specified, it uses the *obj* subdirectory of the current directory.</span></span>

## <a name="examples"></a><span data-ttu-id="5caf9-132">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="5caf9-132">Examples</span></span>

<span data-ttu-id="5caf9-133">Almacenamiento de los paquetes especificados en el archivo de proyecto *packages.csproj* para .NET Core 2.0.0:</span><span class="sxs-lookup"><span data-stu-id="5caf9-133">Store the packages specified in the *packages.csproj* project file for .NET Core 2.0.0:</span></span>

`dotnet store --manifest packages.csproj --framework-version 2.0.0`

<span data-ttu-id="5caf9-134">Almacenamiento de los paquetes especificados en *packages.csproj* sin optimización:</span><span class="sxs-lookup"><span data-stu-id="5caf9-134">Store the packages specified in the *packages.csproj* without optimization:</span></span>

`dotnet store --manifest packages.csproj --skip-optimization`

## <a name="see-also"></a><span data-ttu-id="5caf9-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="5caf9-135">See also</span></span>

- <span data-ttu-id="5caf9-136">[Runtime package store](../deploying/runtime-store.md) (Almacenamiento de paquetes en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="5caf9-136">[Runtime package store](../deploying/runtime-store.md)</span></span>
