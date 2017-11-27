---
title: Comando dotnet store
description: "El comando “dotnet store” almacena los ensamblados especificados en el almacenamiento de paquetes en tiempo de ejecución."
author: bleroy
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: fcf1eeba0709e05cff124bc3ae7bb93f4ca57128
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="dotnet-store"></a><span data-ttu-id="5dfa9-103">dotnet store</span><span class="sxs-lookup"><span data-stu-id="5dfa9-103">dotnet store</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]

## <a name="name"></a><span data-ttu-id="5dfa9-104">Name</span><span class="sxs-lookup"><span data-stu-id="5dfa9-104">Name</span></span>

<span data-ttu-id="5dfa9-105">`dotnet store`: almacena los ensamblados especificados en el [almacenamiento de paquetes en tiempo de ejecución](../deploying/runtime-store.md).</span><span class="sxs-lookup"><span data-stu-id="5dfa9-105">`dotnet store` - Stores the specified assemblies in the [runtime package store](../deploying/runtime-store.md).</span></span>

## <a name="synopsis"></a><span data-ttu-id="5dfa9-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="5dfa9-106">Synopsis</span></span>

`dotnet store -m|--manifest -f|--framework -r|--runtime  [--framework-version] [-h|--help] [--output] [--skip-optimization] [--skip-symbols] [-v|--verbosity] [--working-dir]`

## <a name="description"></a><span data-ttu-id="5dfa9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="5dfa9-107">Description</span></span>

<span data-ttu-id="5dfa9-108">`dotnet store` almacena los ensamblados especificados en el [almacenamiento de paquetes en tiempo de ejecución](../deploying/runtime-store.md).</span><span class="sxs-lookup"><span data-stu-id="5dfa9-108">`dotnet store` stores the specified assemblies in the [runtime package store](../deploying/runtime-store.md).</span></span> <span data-ttu-id="5dfa9-109">De forma predeterminada, los ensamblados están optimizados para el tiempo de ejecución y el marco de trabajo de destino.</span><span class="sxs-lookup"><span data-stu-id="5dfa9-109">By default, assemblies are optimized for the target runtime and framework.</span></span> <span data-ttu-id="5dfa9-110">Para obtener más información, consulte el tema [runtime package store](../deploying/runtime-store.md) (almacenamiento de paquetes en tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="5dfa9-110">For more information, see the [runtime package store](../deploying/runtime-store.md) topic.</span></span>

## <a name="required-options"></a><span data-ttu-id="5dfa9-111">Opciones necesarias</span><span class="sxs-lookup"><span data-stu-id="5dfa9-111">Required options</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="5dfa9-112">Especifica la [plataforma de destino](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="5dfa9-112">Specifies the [target framework](../../standard/frameworks.md).</span></span>

`-m|--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="5dfa9-113">El *archivo de manifiesto de almacenamiento de paquetes* es un archivo XML que contiene la lista de paquetes que se va a almacenar.</span><span class="sxs-lookup"><span data-stu-id="5dfa9-113">The *package store manifest file* is an XML file that contains the list of packages to store.</span></span> <span data-ttu-id="5dfa9-114">El formato del archivo de manifiesto es compatible con el formato *csproj*.</span><span class="sxs-lookup"><span data-stu-id="5dfa9-114">The format of the manifest file is compatible with the *csproj* format.</span></span> <span data-ttu-id="5dfa9-115">Por lo tanto, puede usarse un archivo de proyecto *csproj* que hace referencia a los paquetes que quiera con la opción `-m|--manifest` para almacenar los ensamblados en el almacenamiento de paquetes en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5dfa9-115">So, a *csproj* project file that references the desired packages can be used with the `-m|--manifest` option to store assemblies in the runtime package store.</span></span> <span data-ttu-id="5dfa9-116">Para especificar varios archivos de manifiesto, repita la opción y la ruta de acceso para cada archivo: `--manifest packages1.csproj --manifest packages2.csproj`.</span><span class="sxs-lookup"><span data-stu-id="5dfa9-116">To specify multiple manifest files, repeat the option and path for each file: `--manifest packages1.csproj --manifest packages2.csproj`.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="5dfa9-117">El identificador en tiempo de ejecución de destino.</span><span class="sxs-lookup"><span data-stu-id="5dfa9-117">The runtime identifier to target.</span></span>

## <a name="optional-options"></a><span data-ttu-id="5dfa9-118">Opciones no necesarias</span><span class="sxs-lookup"><span data-stu-id="5dfa9-118">Optional options</span></span>

`--framework-version <FRAMEWORK_VERSION>`

<span data-ttu-id="5dfa9-119">Especifica la versión del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5dfa9-119">Specifies the .NET Core SDK version.</span></span> <span data-ttu-id="5dfa9-120">Esta opción le permite seleccionar una versión de un marco concreto más allá del marco de trabajo especificado en la opción `-f|--framework`.</span><span class="sxs-lookup"><span data-stu-id="5dfa9-120">This option enables you to select a specific framework version beyond the framework specified by the `-f|--framework` option.</span></span>

`-h|--help`

<span data-ttu-id="5dfa9-121">Muestra información de ayuda.</span><span class="sxs-lookup"><span data-stu-id="5dfa9-121">Shows help information.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="5dfa9-122">Especifica la ruta de acceso al almacenamiento de paquetes en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5dfa9-122">Specifies the path to the runtime package store.</span></span> <span data-ttu-id="5dfa9-123">Si no se especifica, el valor predeterminado es el subdirectorio *store* del directorio de instalación de .NET Core de perfil de usuario.</span><span class="sxs-lookup"><span data-stu-id="5dfa9-123">If not specified, it defaults to the *store* subdirectory of the user profile .NET Core installation directory.</span></span>

`--skip-optimization`

<span data-ttu-id="5dfa9-124">Omite la fase de optimización.</span><span class="sxs-lookup"><span data-stu-id="5dfa9-124">Skips the optimization phase.</span></span>

`--skip-symbols`

<span data-ttu-id="5dfa9-125">Omite la generación de símbolos.</span><span class="sxs-lookup"><span data-stu-id="5dfa9-125">Skips symbol generation.</span></span> <span data-ttu-id="5dfa9-126">Actualmente, solo se pueden generar símbolos en Windows y Linux.</span><span class="sxs-lookup"><span data-stu-id="5dfa9-126">Currently, you can only generate symbols on Windows and Linux.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="5dfa9-127">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="5dfa9-127">Sets the verbosity level of the command.</span></span> <span data-ttu-id="5dfa9-128">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="5dfa9-128">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`-w|--working-dir <INTERMEDIATE_WORKING_DIRECTORY>`

<span data-ttu-id="5dfa9-129">El directorio de trabajo que usa el comando.</span><span class="sxs-lookup"><span data-stu-id="5dfa9-129">The working directory used by the command.</span></span> <span data-ttu-id="5dfa9-130">Si no se especifica, usa el subdirectorio *obj* del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="5dfa9-130">If not specified, it uses the *obj* subdirectory of the current directory.</span></span>

## <a name="examples"></a><span data-ttu-id="5dfa9-131">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="5dfa9-131">Examples</span></span>

<span data-ttu-id="5dfa9-132">Almacenamiento de los paquetes especificados en el archivo de proyecto *packages.csproj* para .NET Core 2.0.0:</span><span class="sxs-lookup"><span data-stu-id="5dfa9-132">Store the packages specified in the *packages.csproj* project file for .NET Core 2.0.0:</span></span>

`dotnet store --manifest packages.csproj --framework-version 2.0.0`

<span data-ttu-id="5dfa9-133">Almacenamiento de los paquetes especificados en *packages.csproj* sin optimización:</span><span class="sxs-lookup"><span data-stu-id="5dfa9-133">Store the packages specified in the *packages.csproj* without optimization:</span></span>

`dotnet store --manifest packages.csproj --skip-optimization`

## <a name="see-also"></a><span data-ttu-id="5dfa9-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="5dfa9-134">See also</span></span>

<span data-ttu-id="5dfa9-135">[Runtime package store](../deploying/runtime-store.md) (Almacenamiento de paquetes en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="5dfa9-135">[Runtime package store](../deploying/runtime-store.md)</span></span>   
