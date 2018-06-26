---
title: 'Comando dotnet migrate: CLI de .NET Core'
description: El comando dotnet migrate migra un proyecto y todas sus dependencias.
author: mairaw
ms.author: mairaw
ms.date: 05/25/2018
ms.openlocfilehash: 67a845f7604dededd00746fa6b74a320b3e134fa
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2018
ms.locfileid: "34697110"
---
# <a name="dotnet-migrate"></a><span data-ttu-id="21cf3-103">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="21cf3-103">dotnet migrate</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="21cf3-104">nombre</span><span class="sxs-lookup"><span data-stu-id="21cf3-104">Name</span></span>

<span data-ttu-id="21cf3-105">`dotnet migrate`: migra un proyecto .NET Core de la versión preliminar 2 a un proyecto del SDK 1.0 de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="21cf3-105">`dotnet migrate` - Migrates a Preview 2 .NET Core project to a .NET Core SDK 1.0 project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="21cf3-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="21cf3-106">Synopsis</span></span>

```
dotnet migrate [<SOLUTION_FILE|PROJECT_DIR>] [--format-report-file-json] [-r|--report-file] [-s|--skip-project-references] [--skip-backup] [-t|--template-file] [-v|--sdk-package-version] [-x|--xproj-file]
dotnet migrate [-h|--help]
```

## <a name="description"></a><span data-ttu-id="21cf3-107">Description</span><span class="sxs-lookup"><span data-stu-id="21cf3-107">Description</span></span>

<span data-ttu-id="21cf3-108">El comando `dotnet migrate` migra un proyecto válido basado en *project.json* de la versión preliminar 2 a un proyecto válido *csproj* del SDK 1.0 de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="21cf3-108">The `dotnet migrate` command migrates a valid Preview 2 *project.json*-based project to a valid .NET Core SDK 1.0 *csproj* project.</span></span>

<span data-ttu-id="21cf3-109">De forma predeterminada, el comando migra el proyecto raíz y todas las referencias de proyecto que contiene.</span><span class="sxs-lookup"><span data-stu-id="21cf3-109">By default, the command migrates the root project and any project references that the root project contains.</span></span> <span data-ttu-id="21cf3-110">Este comportamiento se deshabilita mediante la opción `--skip-project-references` en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="21cf3-110">This behavior is disabled using the `--skip-project-references` option at runtime.</span></span>

<span data-ttu-id="21cf3-111">La migración se puede realizar en los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="21cf3-111">Migration can be performed on the following assets:</span></span>

* <span data-ttu-id="21cf3-112">Un único proyecto mediante la especificación del archivo *project.json* que quiere migrar.</span><span class="sxs-lookup"><span data-stu-id="21cf3-112">A single project by specifying the *project.json* file to migrate.</span></span>
* <span data-ttu-id="21cf3-113">Todos los directorios especificados en el archivo *global.json* pasando una ruta al archivo *global.json*.</span><span class="sxs-lookup"><span data-stu-id="21cf3-113">All of the directories specified in the *global.json* file by passing in a path to the *global.json* file.</span></span>
* <span data-ttu-id="21cf3-114">Un archivo *solution.sln*, donde se migran los proyectos a los que se hace referencia en la solución.</span><span class="sxs-lookup"><span data-stu-id="21cf3-114">A *solution.sln* file, where it migrates the projects referenced in the solution.</span></span>
* <span data-ttu-id="21cf3-115">Todos los subdirectorios del directorio dado de manera recursiva.</span><span class="sxs-lookup"><span data-stu-id="21cf3-115">On all subdirectories of the given directory recursively.</span></span>

<span data-ttu-id="21cf3-116">El comando `dotnet migrate` mantiene el archivo *project.json* migrado dentro de un directorio `backup`, que se crea en caso de que no exista.</span><span class="sxs-lookup"><span data-stu-id="21cf3-116">The `dotnet migrate` command keeps the migrated *project.json* file inside a `backup` directory, which it creates if the directory doesn't exist.</span></span> <span data-ttu-id="21cf3-117">Este comportamiento se invalida con la opción `--skip-backup`.</span><span class="sxs-lookup"><span data-stu-id="21cf3-117">This behavior is overridden using the `--skip-backup` option.</span></span>

<span data-ttu-id="21cf3-118">De forma predeterminada, la operación de migración genera el estado del proceso de migración a la salida estándar (STDOUT).</span><span class="sxs-lookup"><span data-stu-id="21cf3-118">By default, the migration operation outputs the state of the migration process to standard output (STDOUT).</span></span> <span data-ttu-id="21cf3-119">Si usa la opción `--report-file <REPORT_FILE>`, la salida se guarda en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="21cf3-119">If you use the `--report-file <REPORT_FILE>` option, the output is saved to the file specify.</span></span>

<span data-ttu-id="21cf3-120">El comando `dotnet migrate` solo admite proyectos válidos basados en *project.json* de la versión preliminar 2.</span><span class="sxs-lookup"><span data-stu-id="21cf3-120">The `dotnet migrate` command only supports valid Preview 2 *project.json*-based projects.</span></span> <span data-ttu-id="21cf3-121">Esto significa que no se puede usar para migrar DNX o los proyectos basados en *project.json* de la versión preliminar 1 directamente a proyectos de MSBuild/csproj.</span><span class="sxs-lookup"><span data-stu-id="21cf3-121">This means that you cannot use it to migrate DNX or Preview 1 *project.json*-based projects directly to MSBuild/csproj projects.</span></span> <span data-ttu-id="21cf3-122">Primero debe migrar manualmente el proyecto a un proyecto basado en *project.json* de la versión preliminar 2 y luego usar el comando `dotnet migrate` para migrar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="21cf3-122">You first need to manually migrate the project to a Preview 2 *project.json*-based project and then use the `dotnet migrate` command to migrate the project.</span></span>

## <a name="arguments"></a><span data-ttu-id="21cf3-123">Argumentos</span><span class="sxs-lookup"><span data-stu-id="21cf3-123">Arguments</span></span>

`PROJECT_JSON/GLOBAL_JSON/SOLUTION_FILE/PROJECT_DIR`

<span data-ttu-id="21cf3-124">La ruta de acceso a uno de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="21cf3-124">The path to one of the following:</span></span>

* <span data-ttu-id="21cf3-125">Un archivo *project.json* para migrar.</span><span class="sxs-lookup"><span data-stu-id="21cf3-125">a *project.json* file to migrate.</span></span>
* <span data-ttu-id="21cf3-126">Un archivo *global.json*: se migran las carpetas especificadas en *global.json*.</span><span class="sxs-lookup"><span data-stu-id="21cf3-126">a *global.json* file: the folders specified in *global.json* are migrated.</span></span>
* <span data-ttu-id="21cf3-127">Un archivo *solution.sln*: se migran los proyectos a los que se hace referencia en la solución.</span><span class="sxs-lookup"><span data-stu-id="21cf3-127">a *solution.sln* file: the projects referenced in the solution are migrated.</span></span>
* <span data-ttu-id="21cf3-128">Un directorio para migrar: se buscan de forma recursiva los archivos *project.json* que se van a migrar dentro del directorio especificado.</span><span class="sxs-lookup"><span data-stu-id="21cf3-128">a directory to migrate: recursively searches for *project.json* files to migrate inside the specified directory.</span></span>

<span data-ttu-id="21cf3-129">Si no se especifica nada, se toma como valor predeterminado el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="21cf3-129">Defaults to current directory if nothing is specified.</span></span>

## <a name="options"></a><span data-ttu-id="21cf3-130">Opciones</span><span class="sxs-lookup"><span data-stu-id="21cf3-130">Options</span></span>

`--format-report-file-json <REPORT_FILE>`

<span data-ttu-id="21cf3-131">Salida del archivo de informe de migración como JSON en lugar de mensajes de usuario.</span><span class="sxs-lookup"><span data-stu-id="21cf3-131">Output migration report file as JSON rather than user messages.</span></span>

`-h|--help`

<span data-ttu-id="21cf3-132">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="21cf3-132">Prints out a short help for the command.</span></span>

`-r|--report-file <REPORT_FILE>`

<span data-ttu-id="21cf3-133">Salida del informe de migración a un archivo además de a la consola.</span><span class="sxs-lookup"><span data-stu-id="21cf3-133">Output migration report to a file in addition to the console.</span></span>

`-s|--skip-project-references [Debug|Release]`

<span data-ttu-id="21cf3-134">Omite la migración de referencias de proyecto.</span><span class="sxs-lookup"><span data-stu-id="21cf3-134">Skip migrating project references.</span></span> <span data-ttu-id="21cf3-135">De forma predeterminada, las referencias de proyecto se migran de forma recursiva.</span><span class="sxs-lookup"><span data-stu-id="21cf3-135">By default, project references are migrated recursively.</span></span>

`--skip-backup`

<span data-ttu-id="21cf3-136">Omite el traslado de *project.json*, *global.json* y *\*.xproj* a un directorio `backup` tras la realización correcta de la migración.</span><span class="sxs-lookup"><span data-stu-id="21cf3-136">Skip moving *project.json*, *global.json*, and *\*.xproj* to a `backup` directory after successful migration.</span></span>

`-t|--template-file <TEMPLATE_FILE>`

<span data-ttu-id="21cf3-137">Archivo csproj de plantilla que se utilizará para la migración.</span><span class="sxs-lookup"><span data-stu-id="21cf3-137">Template csproj file to use for migration.</span></span> <span data-ttu-id="21cf3-138">De forma predeterminada, se usa la misma plantilla que la descartada por `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="21cf3-138">By default, the same template as the one dropped by `dotnet new console` is used.</span></span>

`-v|--sdk-package-version <VERSION>`

<span data-ttu-id="21cf3-139">La versión del paquete sdk a la que se hace referencia en la aplicación migrada.</span><span class="sxs-lookup"><span data-stu-id="21cf3-139">The version of the sdk package that's referenced in the migrated app.</span></span> <span data-ttu-id="21cf3-140">El valor predeterminado es la versión del SDK en `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="21cf3-140">The default is the version of the SDK in `dotnet new`.</span></span>

`-x|--xproj-file <FILE>`

<span data-ttu-id="21cf3-141">La ruta de acceso al archivo xproj que se usará.</span><span class="sxs-lookup"><span data-stu-id="21cf3-141">The path to the xproj file to use.</span></span> <span data-ttu-id="21cf3-142">Necesario cuando hay más de un archivo xproj en un directorio de proyecto.</span><span class="sxs-lookup"><span data-stu-id="21cf3-142">Required when there is more than one xproj in a project directory.</span></span>

## <a name="examples"></a><span data-ttu-id="21cf3-143">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="21cf3-143">Examples</span></span>

<span data-ttu-id="21cf3-144">Migrar un proyecto del directorio actual y todas sus dependencias de proyecto a proyecto:</span><span class="sxs-lookup"><span data-stu-id="21cf3-144">Migrate a project in the current directory and all of its project-to-project dependencies:</span></span>

`dotnet migrate`

<span data-ttu-id="21cf3-145">Migrar todos los proyectos que incluyen el archivo *global.json*:</span><span class="sxs-lookup"><span data-stu-id="21cf3-145">Migrate all projects that *global.json* file includes:</span></span>

`dotnet migrate path/to/global.json`

<span data-ttu-id="21cf3-146">Migrar solo el proyecto actual y ninguna dependencia de proyecto a proyecto (P2P).</span><span class="sxs-lookup"><span data-stu-id="21cf3-146">Migrate only the current project and no project-to-project (P2P) dependencies.</span></span> <span data-ttu-id="21cf3-147">Además, usar una versión específica de SDK:</span><span class="sxs-lookup"><span data-stu-id="21cf3-147">Also, use a specific SDK version:</span></span>

`dotnet migrate -s -v 1.0.0-preview4`