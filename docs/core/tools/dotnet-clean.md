---
title: 'Comando dotnet clean: CLI de .NET Core'
description: El comando dotnet clean limpia el directorio actual.
ms.date: 12/04/2018
ms.openlocfilehash: 9930d2905f234e7125f27367cda36aa85ae23b87
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53144460"
---
# <a name="dotnet-clean"></a><span data-ttu-id="3d914-103">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="3d914-103">dotnet clean</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="3d914-104">nombre</span><span class="sxs-lookup"><span data-stu-id="3d914-104">Name</span></span>

<span data-ttu-id="3d914-105">`dotnet clean`: limpia la salida de un proyecto.</span><span class="sxs-lookup"><span data-stu-id="3d914-105">`dotnet clean` - Cleans the output of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="3d914-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="3d914-106">Synopsis</span></span>

```
dotnet clean [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity]
dotnet clean [-h|--help]
```

## <a name="description"></a><span data-ttu-id="3d914-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="3d914-107">Description</span></span>

<span data-ttu-id="3d914-108">El comando `dotnet clean` limpia la salida de la compilación anterior.</span><span class="sxs-lookup"><span data-stu-id="3d914-108">The `dotnet clean` command cleans the output of the previous build.</span></span> <span data-ttu-id="3d914-109">Se implementa como un [destino MSBuild](/visualstudio/msbuild/msbuild-targets), por lo que el proyecto se evalúa cuando se ejecuta el comando.</span><span class="sxs-lookup"><span data-stu-id="3d914-109">It's implemented as an [MSBuild target](/visualstudio/msbuild/msbuild-targets), so the project is evaluated when the command is run.</span></span> <span data-ttu-id="3d914-110">Solo se limpian las salidas que se crearon durante la compilación.</span><span class="sxs-lookup"><span data-stu-id="3d914-110">Only the outputs created during the build are cleaned.</span></span> <span data-ttu-id="3d914-111">Se limpian las carpetas intermedias (*obj*) y de la salida final (*bin*).</span><span class="sxs-lookup"><span data-stu-id="3d914-111">Both intermediate (*obj*) and final output (*bin*) folders are cleaned.</span></span>

## <a name="arguments"></a><span data-ttu-id="3d914-112">Argumentos</span><span class="sxs-lookup"><span data-stu-id="3d914-112">Arguments</span></span>

`PROJECT`

<span data-ttu-id="3d914-113">El proyecto de MSBuild para limpiar.</span><span class="sxs-lookup"><span data-stu-id="3d914-113">The MSBuild project to clean.</span></span> <span data-ttu-id="3d914-114">Si no se especifica un archivo de proyecto, MSBuild busca en el directorio de trabajo actual un archivo que tenga una extensión de archivo que termine en *proj* y usa ese archivo.</span><span class="sxs-lookup"><span data-stu-id="3d914-114">If a project file is not specified, MSBuild searches the current working directory for a file that has a file extension that ends in *proj* and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="3d914-115">Opciones</span><span class="sxs-lookup"><span data-stu-id="3d914-115">Options</span></span>

* **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="3d914-116">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="3d914-116">Defines the build configuration.</span></span> <span data-ttu-id="3d914-117">El valor predeterminado es `Debug`.</span><span class="sxs-lookup"><span data-stu-id="3d914-117">The default value is `Debug`.</span></span> <span data-ttu-id="3d914-118">Esta opción solo es necesaria al realizar la limpieza si la especificó durante el tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="3d914-118">This option is only required when cleaning if you specified it during build time.</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="3d914-119">El [marco](../../standard/frameworks.md) que se especificó en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="3d914-119">The [framework](../../standard/frameworks.md) that was specified at build time.</span></span> <span data-ttu-id="3d914-120">El marco se debe definir en el [archivo de proyecto](csproj.md).</span><span class="sxs-lookup"><span data-stu-id="3d914-120">The framework must be defined in the [project file](csproj.md).</span></span> <span data-ttu-id="3d914-121">Si especificó el marco en tiempo de compilación, debe especificar el marco al realizar la limpieza.</span><span class="sxs-lookup"><span data-stu-id="3d914-121">If you specified the framework at build time, you must specify the framework when cleaning.</span></span>

* **`-h|--help`**

  <span data-ttu-id="3d914-122">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="3d914-122">Prints out a short help for the command.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="3d914-123">Directorio en el que se colocan las salidas de compilación.</span><span class="sxs-lookup"><span data-stu-id="3d914-123">Directory in which the build outputs are placed.</span></span> <span data-ttu-id="3d914-124">Especifique el modificador `-f|--framework <FRAMEWORK>` con el modificador del directorio de salida si especificó el marco cuando se compiló el proyecto.</span><span class="sxs-lookup"><span data-stu-id="3d914-124">Specify the `-f|--framework <FRAMEWORK>` switch with the output directory switch if you specified the framework when the project was built.</span></span>

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="3d914-125">Limpia la carpeta de salida del tiempo de ejecución especificado.</span><span class="sxs-lookup"><span data-stu-id="3d914-125">Cleans the output folder of the specified runtime.</span></span> <span data-ttu-id="3d914-126">Esto se usa si se ha creado una [implementación autocontenida](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="3d914-126">This is used when a [self-contained deployment](../deploying/index.md#self-contained-deployments-scd) was created.</span></span> <span data-ttu-id="3d914-127">Opción disponible desde el SDK de .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="3d914-127">Option available since .NET Core 2.0 SDK.</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="3d914-128">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="3d914-128">Sets the verbosity level of the command.</span></span> <span data-ttu-id="3d914-129">Niveles permitidos son q[uiet], m[inimal], n[ormal], d[etailed] y diag[nostic].</span><span class="sxs-lookup"><span data-stu-id="3d914-129">Allowed levels are q[uiet], m[inimal], n[ormal], d[etailed], and diag[nostic].</span></span>

## <a name="examples"></a><span data-ttu-id="3d914-130">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3d914-130">Examples</span></span>

* <span data-ttu-id="3d914-131">Limpie una compilación predeterminada del proyecto:</span><span class="sxs-lookup"><span data-stu-id="3d914-131">Clean a default build of the project:</span></span>

  ```console
  dotnet clean
  ```

* <span data-ttu-id="3d914-132">Limpie un proyecto creado con la configuración de lanzamiento:</span><span class="sxs-lookup"><span data-stu-id="3d914-132">Clean a project built using the Release configuration:</span></span>

  ```console
  dotnet clean --configuration Release
  ```