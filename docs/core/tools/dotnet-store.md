---
title: Comando dotnet store
description: El comando “dotnet store” almacena los ensamblados especificados en el almacenamiento de paquetes en tiempo de ejecución.
ms.date: 02/14/2020
ms.openlocfilehash: da1d132b2b873ff55ec104b5bb092d0194889bdc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503585"
---
# <a name="dotnet-store"></a><span data-ttu-id="adfb1-103">dotnet store</span><span class="sxs-lookup"><span data-stu-id="adfb1-103">dotnet store</span></span>

<span data-ttu-id="adfb1-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.x y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="adfb1-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="adfb1-105">Name</span><span class="sxs-lookup"><span data-stu-id="adfb1-105">Name</span></span>

<span data-ttu-id="adfb1-106">`dotnet store`: almacena los ensamblados especificados en el [almacenamiento de paquetes en tiempo de ejecución](../deploying/runtime-store.md).</span><span class="sxs-lookup"><span data-stu-id="adfb1-106">`dotnet store` - Stores the specified assemblies in the [runtime package store](../deploying/runtime-store.md).</span></span>

## <a name="synopsis"></a><span data-ttu-id="adfb1-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="adfb1-107">Synopsis</span></span>

```dotnetcli
dotnet store -m|--manifest -f|--framework -r|--runtime  [--framework-version] [-h|--help] [--output] [--skip-optimization] [--skip-symbols] [-v|--verbosity] [--working-dir]
```

## <a name="description"></a><span data-ttu-id="adfb1-108">Description</span><span class="sxs-lookup"><span data-stu-id="adfb1-108">Description</span></span>

<span data-ttu-id="adfb1-109">`dotnet store` almacena los ensamblados especificados en el [almacenamiento de paquetes en tiempo de ejecución](../deploying/runtime-store.md).</span><span class="sxs-lookup"><span data-stu-id="adfb1-109">`dotnet store` stores the specified assemblies in the [runtime package store](../deploying/runtime-store.md).</span></span> <span data-ttu-id="adfb1-110">De forma predeterminada, los ensamblados están optimizados para el tiempo de ejecución y el marco de trabajo de destino.</span><span class="sxs-lookup"><span data-stu-id="adfb1-110">By default, assemblies are optimized for the target runtime and framework.</span></span> <span data-ttu-id="adfb1-111">Para obtener más información, consulte el tema [Almacenamiento de paquetes en tiempo de ejecución](../deploying/runtime-store.md).</span><span class="sxs-lookup"><span data-stu-id="adfb1-111">For more information, see the [runtime package store](../deploying/runtime-store.md) topic.</span></span>

## <a name="required-options"></a><span data-ttu-id="adfb1-112">Opciones necesarias</span><span class="sxs-lookup"><span data-stu-id="adfb1-112">Required options</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="adfb1-113">Especifica la [plataforma de destino](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="adfb1-113">Specifies the [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="adfb1-114">La plataforma de destino tiene que especificarse en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="adfb1-114">The target framework has to be specified in the project file.</span></span>

- **`-m|--manifest <PATH_TO_MANIFEST_FILE>`**

  <span data-ttu-id="adfb1-115">El *archivo de manifiesto de almacenamiento de paquetes* es un archivo XML que contiene la lista de paquetes que se va a almacenar.</span><span class="sxs-lookup"><span data-stu-id="adfb1-115">The *package store manifest file* is an XML file that contains the list of packages to store.</span></span> <span data-ttu-id="adfb1-116">El formato del archivo de manifiesto es compatible con el formato de proyecto de estilo de SDK.</span><span class="sxs-lookup"><span data-stu-id="adfb1-116">The format of the manifest file is compatible with the SDK-style project format.</span></span> <span data-ttu-id="adfb1-117">Por tanto, se puede usar un archivo de proyecto que haga referencia a los paquetes deseados con la opción `-m|--manifest` para almacenar los ensamblados en el almacenamiento de paquetes en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="adfb1-117">So, a project file that references the desired packages can be used with the `-m|--manifest` option to store assemblies in the runtime package store.</span></span> <span data-ttu-id="adfb1-118">Para especificar varios archivos de manifiesto, repita la opción y la ruta de acceso para cada archivo.</span><span class="sxs-lookup"><span data-stu-id="adfb1-118">To specify multiple manifest files, repeat the option and path for each file.</span></span> <span data-ttu-id="adfb1-119">Por ejemplo: `--manifest packages1.csproj --manifest packages2.csproj`.</span><span class="sxs-lookup"><span data-stu-id="adfb1-119">For example: `--manifest packages1.csproj --manifest packages2.csproj`.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="adfb1-120">El [identificador en tiempo de ejecución](../rid-catalog.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="adfb1-120">The [runtime identifier](../rid-catalog.md) to target.</span></span>

## <a name="optional-options"></a><span data-ttu-id="adfb1-121">Opciones no necesarias</span><span class="sxs-lookup"><span data-stu-id="adfb1-121">Optional options</span></span>

- **`--framework-version <FRAMEWORK_VERSION>`**

  <span data-ttu-id="adfb1-122">Especifica la versión del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="adfb1-122">Specifies the .NET Core SDK version.</span></span> <span data-ttu-id="adfb1-123">Esta opción le permite seleccionar una versión de un marco concreto más allá del marco de trabajo especificado en la opción `-f|--framework`.</span><span class="sxs-lookup"><span data-stu-id="adfb1-123">This option enables you to select a specific framework version beyond the framework specified by the `-f|--framework` option.</span></span>

- **`-h|--help`**

  <span data-ttu-id="adfb1-124">Muestra información de ayuda.</span><span class="sxs-lookup"><span data-stu-id="adfb1-124">Shows help information.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="adfb1-125">Especifica la ruta de acceso al almacenamiento de paquetes en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="adfb1-125">Specifies the path to the runtime package store.</span></span> <span data-ttu-id="adfb1-126">Si no se especifica, el valor predeterminado es el subdirectorio *store* del directorio de instalación de .NET Core de perfil de usuario.</span><span class="sxs-lookup"><span data-stu-id="adfb1-126">If not specified, it defaults to the *store* subdirectory of the user profile .NET Core installation directory.</span></span>

- **`--skip-optimization`**

  <span data-ttu-id="adfb1-127">Omite la fase de optimización.</span><span class="sxs-lookup"><span data-stu-id="adfb1-127">Skips the optimization phase.</span></span>

- **`--skip-symbols`**

  <span data-ttu-id="adfb1-128">Omite la generación de símbolos.</span><span class="sxs-lookup"><span data-stu-id="adfb1-128">Skips symbol generation.</span></span> <span data-ttu-id="adfb1-129">Actualmente, solo se pueden generar símbolos en Windows y Linux.</span><span class="sxs-lookup"><span data-stu-id="adfb1-129">Currently, you can only generate symbols on Windows and Linux.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="adfb1-130">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="adfb1-130">Sets the verbosity level of the command.</span></span> <span data-ttu-id="adfb1-131">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="adfb1-131">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

- **`-w|--working-dir <WORKING_DIRECTORY>`**

  <span data-ttu-id="adfb1-132">El directorio de trabajo que usa el comando.</span><span class="sxs-lookup"><span data-stu-id="adfb1-132">The working directory used by the command.</span></span> <span data-ttu-id="adfb1-133">Si no se especifica, usa el subdirectorio *obj* del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="adfb1-133">If not specified, it uses the *obj* subdirectory of the current directory.</span></span>

## <a name="examples"></a><span data-ttu-id="adfb1-134">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="adfb1-134">Examples</span></span>

- <span data-ttu-id="adfb1-135">Almacenamiento de los paquetes especificados en el archivo de proyecto *packages.csproj* para .NET Core 2.0.0:</span><span class="sxs-lookup"><span data-stu-id="adfb1-135">Store the packages specified in the *packages.csproj* project file for .NET Core 2.0.0:</span></span>

  ```dotnetcli
  dotnet store --manifest packages.csproj --framework-version 2.0.0
  ```

- <span data-ttu-id="adfb1-136">Almacenamiento de los paquetes especificados en *packages.csproj* sin optimización:</span><span class="sxs-lookup"><span data-stu-id="adfb1-136">Store the packages specified in the *packages.csproj* without optimization:</span></span>

  ```dotnetcli
  dotnet store --manifest packages.csproj --skip-optimization
  ```

## <a name="see-also"></a><span data-ttu-id="adfb1-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="adfb1-137">See also</span></span>

- <span data-ttu-id="adfb1-138">[Runtime package store](../deploying/runtime-store.md) (Almacenamiento de paquetes en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="adfb1-138">[Runtime package store](../deploying/runtime-store.md)</span></span>
