---
title: 'Comando dotnet clean: CLI de .NET Core'
description: El comando dotnet clean limpia el directorio actual.
author: mairaw
ms.author: mairaw
ms.date: 05/25/2018
ms.openlocfilehash: 5553e4b4423a2d824c05caf7114c47b5f1c20477
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "45988340"
---
# <a name="dotnet-clean"></a><span data-ttu-id="32c33-103">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="32c33-103">dotnet clean</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="32c33-104">nombre</span><span class="sxs-lookup"><span data-stu-id="32c33-104">Name</span></span>

<span data-ttu-id="32c33-105">`dotnet clean`: limpia la salida de un proyecto.</span><span class="sxs-lookup"><span data-stu-id="32c33-105">`dotnet clean` - Cleans the output of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="32c33-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="32c33-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="32c33-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="32c33-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet clean [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity]
dotnet clean [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="32c33-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="32c33-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet clean [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-v|--verbosity]
dotnet clean [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="32c33-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="32c33-109">Description</span></span>

<span data-ttu-id="32c33-110">El comando `dotnet clean` limpia la salida de la compilación anterior.</span><span class="sxs-lookup"><span data-stu-id="32c33-110">The `dotnet clean` command cleans the output of the previous build.</span></span> <span data-ttu-id="32c33-111">Se implementa como un [destino MSBuild](/visualstudio/msbuild/msbuild-targets), por lo que el proyecto se evalúa cuando se ejecuta el comando.</span><span class="sxs-lookup"><span data-stu-id="32c33-111">It's implemented as an [MSBuild target](/visualstudio/msbuild/msbuild-targets), so the project is evaluated when the command is run.</span></span> <span data-ttu-id="32c33-112">Solo se limpian las salidas que se crearon durante la compilación.</span><span class="sxs-lookup"><span data-stu-id="32c33-112">Only the outputs created during the build are cleaned.</span></span> <span data-ttu-id="32c33-113">Se limpian las carpetas intermedias (*obj*) y de la salida final (*bin*).</span><span class="sxs-lookup"><span data-stu-id="32c33-113">Both intermediate (*obj*) and final output (*bin*) folders are cleaned.</span></span>

## <a name="arguments"></a><span data-ttu-id="32c33-114">Argumentos</span><span class="sxs-lookup"><span data-stu-id="32c33-114">Arguments</span></span>

`PROJECT`

<span data-ttu-id="32c33-115">El proyecto de MSBuild para limpiar.</span><span class="sxs-lookup"><span data-stu-id="32c33-115">The MSBuild project to clean.</span></span> <span data-ttu-id="32c33-116">Si no se especifica un archivo de proyecto, MSBuild busca en el directorio de trabajo actual un archivo que tenga una extensión de archivo que termine en *proj* y usa ese archivo.</span><span class="sxs-lookup"><span data-stu-id="32c33-116">If a project file is not specified, MSBuild searches the current working directory for a file that has a file extension that ends in *proj* and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="32c33-117">Opciones</span><span class="sxs-lookup"><span data-stu-id="32c33-117">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="32c33-118">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="32c33-118">.NET Core 2.x</span></span>](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="32c33-119">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="32c33-119">Defines the build configuration.</span></span> <span data-ttu-id="32c33-120">El valor predeterminado es `Debug`.</span><span class="sxs-lookup"><span data-stu-id="32c33-120">The default value is `Debug`.</span></span> <span data-ttu-id="32c33-121">Esta opción solo es necesaria al realizar la limpieza si la especificó durante el tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="32c33-121">This option is only required when cleaning if you specified it during build time.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="32c33-122">El [marco](../../standard/frameworks.md) que se especificó en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="32c33-122">The [framework](../../standard/frameworks.md) that was specified at build time.</span></span> <span data-ttu-id="32c33-123">El marco se debe definir en el [archivo de proyecto](csproj.md).</span><span class="sxs-lookup"><span data-stu-id="32c33-123">The framework must be defined in the [project file](csproj.md).</span></span> <span data-ttu-id="32c33-124">Si especificó el marco en tiempo de compilación, debe especificar el marco al realizar la limpieza.</span><span class="sxs-lookup"><span data-stu-id="32c33-124">If you specified the framework at build time, you must specify the framework when cleaning.</span></span>

`-h|--help`

<span data-ttu-id="32c33-125">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="32c33-125">Prints out a short help for the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="32c33-126">Directorio en el que se colocan las salidas de compilación.</span><span class="sxs-lookup"><span data-stu-id="32c33-126">Directory in which the build outputs are placed.</span></span> <span data-ttu-id="32c33-127">Especifique el modificador `-f|--framework <FRAMEWORK>` con el modificador del directorio de salida si especificó el marco cuando se compiló el proyecto.</span><span class="sxs-lookup"><span data-stu-id="32c33-127">Specify the `-f|--framework <FRAMEWORK>` switch with the output directory switch if you specified the framework when the project was built.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="32c33-128">Limpia la carpeta de salida del tiempo de ejecución especificado.</span><span class="sxs-lookup"><span data-stu-id="32c33-128">Cleans the output folder of the specified runtime.</span></span> <span data-ttu-id="32c33-129">Esto se usa si se ha creado una [implementación autocontenida](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="32c33-129">This is used when a [self-contained deployment](../deploying/index.md#self-contained-deployments-scd) was created.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="32c33-130">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="32c33-130">Sets the verbosity level of the command.</span></span> <span data-ttu-id="32c33-131">Niveles permitidos son q[uiet], m[inimal], n[ormal], d[etailed] y diag[nostic].</span><span class="sxs-lookup"><span data-stu-id="32c33-131">Allowed levels are q[uiet], m[inimal], n[ormal], d[etailed], and diag[nostic].</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="32c33-132">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="32c33-132">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="32c33-133">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="32c33-133">Defines the build configuration.</span></span> <span data-ttu-id="32c33-134">El valor predeterminado es `Debug`.</span><span class="sxs-lookup"><span data-stu-id="32c33-134">The default value is `Debug`.</span></span> <span data-ttu-id="32c33-135">Esta opción solo es necesaria al realizar la limpieza si la especificó durante el tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="32c33-135">This option is only required when cleaning if you specified it during build time.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="32c33-136">El [marco](../../standard/frameworks.md) que se especificó en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="32c33-136">The [framework](../../standard/frameworks.md) that was specified at build time.</span></span> <span data-ttu-id="32c33-137">El marco se debe definir en el [archivo de proyecto](csproj.md).</span><span class="sxs-lookup"><span data-stu-id="32c33-137">The framework must be defined in the [project file](csproj.md).</span></span> <span data-ttu-id="32c33-138">Si especificó el marco en tiempo de compilación, debe especificar el marco al realizar la limpieza.</span><span class="sxs-lookup"><span data-stu-id="32c33-138">If you specified the framework at build time, you must specify the framework when cleaning.</span></span>

`-h|--help`

<span data-ttu-id="32c33-139">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="32c33-139">Prints out a short help for the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="32c33-140">Directorio en el que se colocan las salidas de compilación.</span><span class="sxs-lookup"><span data-stu-id="32c33-140">Directory in which the build outputs are placed.</span></span> <span data-ttu-id="32c33-141">Especifique el modificador `-f|--framework <FRAMEWORK>` con el modificador del directorio de salida si especificó el marco cuando se compiló el proyecto.</span><span class="sxs-lookup"><span data-stu-id="32c33-141">Specify the `-f|--framework <FRAMEWORK>` switch with the output directory switch if you specified the framework when the project was built.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="32c33-142">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="32c33-142">Sets the verbosity level of the command.</span></span> <span data-ttu-id="32c33-143">Niveles permitidos son q[uiet], m[inimal], n[ormal], d[etailed] y diag[nostic].</span><span class="sxs-lookup"><span data-stu-id="32c33-143">Allowed levels are q[uiet], m[inimal], n[ormal], d[etailed], and diag[nostic].</span></span>

---

## <a name="examples"></a><span data-ttu-id="32c33-144">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="32c33-144">Examples</span></span>

<span data-ttu-id="32c33-145">Limpie una compilación predeterminada del proyecto:</span><span class="sxs-lookup"><span data-stu-id="32c33-145">Clean a default build of the project:</span></span>

`dotnet clean`

<span data-ttu-id="32c33-146">Limpie un proyecto creado con la configuración de lanzamiento:</span><span class="sxs-lookup"><span data-stu-id="32c33-146">Clean a project built using the Release configuration:</span></span>

`dotnet clean --configuration Release`
