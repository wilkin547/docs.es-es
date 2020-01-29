---
title: Comando dotnet clean
description: El comando dotnet clean limpia el directorio actual.
ms.date: 06/26/2019
ms.openlocfilehash: 736c0bba5d156e919534f1ad811641e815b3ffac
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734251"
---
# <a name="dotnet-clean"></a><span data-ttu-id="f5462-103">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="f5462-103">dotnet clean</span></span>

<span data-ttu-id="f5462-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 1.x y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="f5462-104">**This article applies to:** ✔️ .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="f5462-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="f5462-105">Name</span></span>

<span data-ttu-id="f5462-106">`dotnet clean`: limpia la salida de un proyecto.</span><span class="sxs-lookup"><span data-stu-id="f5462-106">`dotnet clean` - Cleans the output of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="f5462-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="f5462-107">Synopsis</span></span>

```dotnetcli
dotnet clean [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--interactive]
    [--nologo] [-o|--output] [-r|--runtime] [-v|--verbosity]
dotnet clean [-h|--help]
```

## <a name="description"></a><span data-ttu-id="f5462-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="f5462-108">Description</span></span>

<span data-ttu-id="f5462-109">El comando `dotnet clean` limpia la salida de la compilación anterior.</span><span class="sxs-lookup"><span data-stu-id="f5462-109">The `dotnet clean` command cleans the output of the previous build.</span></span> <span data-ttu-id="f5462-110">Se implementa como un [destino MSBuild](/visualstudio/msbuild/msbuild-targets), por lo que el proyecto se evalúa cuando se ejecuta el comando.</span><span class="sxs-lookup"><span data-stu-id="f5462-110">It's implemented as an [MSBuild target](/visualstudio/msbuild/msbuild-targets), so the project is evaluated when the command is run.</span></span> <span data-ttu-id="f5462-111">Solo se limpian las salidas que se crearon durante la compilación.</span><span class="sxs-lookup"><span data-stu-id="f5462-111">Only the outputs created during the build are cleaned.</span></span> <span data-ttu-id="f5462-112">Se limpian las carpetas intermedias (*obj*) y de la salida final (*bin*).</span><span class="sxs-lookup"><span data-stu-id="f5462-112">Both intermediate (*obj*) and final output (*bin*) folders are cleaned.</span></span>

## <a name="arguments"></a><span data-ttu-id="f5462-113">Argumentos</span><span class="sxs-lookup"><span data-stu-id="f5462-113">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="f5462-114">Proyecto o solución de MSBuild que se va a limpiar.</span><span class="sxs-lookup"><span data-stu-id="f5462-114">The MSBuild project or solution to clean.</span></span> <span data-ttu-id="f5462-115">Si no se especifica un archivo de proyecto o solución, MSBuild busca en el directorio de trabajo actual un archivo que tenga una extensión de archivo que termine en *proj* o *sln* y lo usa.</span><span class="sxs-lookup"><span data-stu-id="f5462-115">If a project or solution file is not specified, MSBuild searches the current working directory for a file that has a file extension that ends in *proj* or *sln*, and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="f5462-116">Opciones</span><span class="sxs-lookup"><span data-stu-id="f5462-116">Options</span></span>

* **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="f5462-117">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="f5462-117">Defines the build configuration.</span></span> <span data-ttu-id="f5462-118">El valor predeterminado es `Debug`.</span><span class="sxs-lookup"><span data-stu-id="f5462-118">The default value is `Debug`.</span></span> <span data-ttu-id="f5462-119">Esta opción solo es necesaria al realizar la limpieza si la especificó durante el tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="f5462-119">This option is only required when cleaning if you specified it during build time.</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="f5462-120">El [marco](../../standard/frameworks.md) que se especificó en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="f5462-120">The [framework](../../standard/frameworks.md) that was specified at build time.</span></span> <span data-ttu-id="f5462-121">El marco se debe definir en el [archivo de proyecto](csproj.md).</span><span class="sxs-lookup"><span data-stu-id="f5462-121">The framework must be defined in the [project file](csproj.md).</span></span> <span data-ttu-id="f5462-122">Si especificó el marco en tiempo de compilación, debe especificar el marco al realizar la limpieza.</span><span class="sxs-lookup"><span data-stu-id="f5462-122">If you specified the framework at build time, you must specify the framework when cleaning.</span></span>

* **`-h|--help`**

  <span data-ttu-id="f5462-123">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="f5462-123">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="f5462-124">Permite que el comando se detenga y espere una entrada o una acción del usuario.</span><span class="sxs-lookup"><span data-stu-id="f5462-124">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="f5462-125">Por ejemplo, para completar la autenticación.</span><span class="sxs-lookup"><span data-stu-id="f5462-125">For example, to complete authentication.</span></span> <span data-ttu-id="f5462-126">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="f5462-126">Available since .NET Core 3.0 SDK.</span></span>

* **`--nologo`**

  <span data-ttu-id="f5462-127">No se muestra la pancarta de inicio ni el mensaje de copyright.</span><span class="sxs-lookup"><span data-stu-id="f5462-127">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="f5462-128">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="f5462-128">Available since .NET Core 3.0 SDK.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="f5462-129">Directorio que contiene los artefactos compilados que se van a limpiar.</span><span class="sxs-lookup"><span data-stu-id="f5462-129">The directory that contains the build artifacts to clean.</span></span> <span data-ttu-id="f5462-130">Especifique el modificador `-f|--framework <FRAMEWORK>` con el modificador del directorio de salida si especificó el marco cuando se compiló el proyecto.</span><span class="sxs-lookup"><span data-stu-id="f5462-130">Specify the `-f|--framework <FRAMEWORK>` switch with the output directory switch if you specified the framework when the project was built.</span></span>

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="f5462-131">Limpia la carpeta de salida del tiempo de ejecución especificado.</span><span class="sxs-lookup"><span data-stu-id="f5462-131">Cleans the output folder of the specified runtime.</span></span> <span data-ttu-id="f5462-132">Esto se usa si se ha creado una [implementación autocontenida](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="f5462-132">This is used when a [self-contained deployment](../deploying/index.md#self-contained-deployments-scd) was created.</span></span> <span data-ttu-id="f5462-133">Opción disponible desde el SDK de .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="f5462-133">Option available since .NET Core 2.0 SDK.</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="f5462-134">Establece el nivel de detalle de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="f5462-134">Sets the MSBuild verbosity level.</span></span> <span data-ttu-id="f5462-135">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="f5462-135">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="f5462-136">De manera predeterminada, es `normal`.</span><span class="sxs-lookup"><span data-stu-id="f5462-136">The default is `normal`.</span></span>

## <a name="examples"></a><span data-ttu-id="f5462-137">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="f5462-137">Examples</span></span>

* <span data-ttu-id="f5462-138">Limpie una compilación predeterminada del proyecto:</span><span class="sxs-lookup"><span data-stu-id="f5462-138">Clean a default build of the project:</span></span>

  ```dotnetcli
  dotnet clean
  ```

* <span data-ttu-id="f5462-139">Limpie un proyecto creado con la configuración de lanzamiento:</span><span class="sxs-lookup"><span data-stu-id="f5462-139">Clean a project built using the Release configuration:</span></span>

  ```dotnetcli
  dotnet clean --configuration Release
  ```
