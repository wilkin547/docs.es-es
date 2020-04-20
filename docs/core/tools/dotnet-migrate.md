---
title: Comando dotnet migrate
description: El comando dotnet migrate migra un proyecto y todas sus dependencias.
ms.date: 02/14/2020
ms.openlocfilehash: 71f587c1bfadd445aca818448bdd5f136f009fe0
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463634"
---
# <a name="dotnet-migrate"></a><span data-ttu-id="12607-103">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="12607-103">dotnet migrate</span></span>

<span data-ttu-id="12607-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="12607-104">**This article applies to:** ✔️ .NET Core 2.x SDK</span></span>

## <a name="name"></a><span data-ttu-id="12607-105">Name</span><span class="sxs-lookup"><span data-stu-id="12607-105">Name</span></span>

<span data-ttu-id="12607-106">`dotnet migrate`: migra un proyecto .NET Core de la versión preliminar 2 a un proyecto del estilo de SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="12607-106">`dotnet migrate` - Migrates a Preview 2 .NET Core project to a .NET Core SDK-style project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="12607-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="12607-107">Synopsis</span></span>

```dotnetcli
dotnet migrate [<SOLUTION_FILE|PROJECT_DIR>] [--format-report-file-json <REPORT_FILE>]
    [-r|--report-file <REPORT_FILE>] [-s|--skip-project-references [Debug|Release]]
    [--skip-backup] [-t|--template-file <TEMPLATE_FILE>] [-v|--sdk-package-version]
    [-x|--xproj-file]

dotnet migrate -h|--help
```

## <a name="description"></a><span data-ttu-id="12607-108">Description</span><span class="sxs-lookup"><span data-stu-id="12607-108">Description</span></span>

<span data-ttu-id="12607-109">Este comando está en desuso.</span><span class="sxs-lookup"><span data-stu-id="12607-109">This command is deprecated.</span></span> <span data-ttu-id="12607-110">El comando `dotnet migrate` ya no está disponible a partir del SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="12607-110">The `dotnet migrate` command is no longer available starting with .NET Core 3.0 SDK.</span></span> <span data-ttu-id="12607-111">Solo puede migrar un proyecto de .NET Core de la versión preliminar 2 a un proyecto de .NET Core 1.x, para el que no hay soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="12607-111">It can only migrate a Preview 2 .NET Core project to a 1.x .NET Core project, which is out of support.</span></span>

<span data-ttu-id="12607-112">De forma predeterminada, el comando migra el proyecto raíz y todas las referencias de proyecto que contiene.</span><span class="sxs-lookup"><span data-stu-id="12607-112">By default, the command migrates the root project and any project references that the root project contains.</span></span> <span data-ttu-id="12607-113">Este comportamiento se deshabilita mediante la opción `--skip-project-references` en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="12607-113">This behavior is disabled using the `--skip-project-references` option at runtime.</span></span>

<span data-ttu-id="12607-114">La migración se puede realizar en los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="12607-114">Migration can be performed on the following assets:</span></span>

* <span data-ttu-id="12607-115">Un único proyecto mediante la especificación del archivo *project.json* que quiere migrar.</span><span class="sxs-lookup"><span data-stu-id="12607-115">A single project by specifying the *project.json* file to migrate.</span></span>
* <span data-ttu-id="12607-116">Todos los directorios especificados en el archivo *global.json* pasando una ruta al archivo *global.json*.</span><span class="sxs-lookup"><span data-stu-id="12607-116">All of the directories specified in the *global.json* file by passing in a path to the *global.json* file.</span></span>
* <span data-ttu-id="12607-117">Un archivo *solution.sln*, donde se migran los proyectos a los que se hace referencia en la solución.</span><span class="sxs-lookup"><span data-stu-id="12607-117">A *solution.sln* file, where it migrates the projects referenced in the solution.</span></span>
* <span data-ttu-id="12607-118">Todos los subdirectorios del directorio dado de manera recursiva.</span><span class="sxs-lookup"><span data-stu-id="12607-118">On all subdirectories of the given directory recursively.</span></span>

<span data-ttu-id="12607-119">El comando `dotnet migrate` mantiene el archivo *project.json* migrado dentro de un directorio `backup`, que se crea en caso de que no exista.</span><span class="sxs-lookup"><span data-stu-id="12607-119">The `dotnet migrate` command keeps the migrated *project.json* file inside a `backup` directory, which it creates if the directory doesn't exist.</span></span> <span data-ttu-id="12607-120">Este comportamiento se invalida con la opción `--skip-backup`.</span><span class="sxs-lookup"><span data-stu-id="12607-120">This behavior is overridden using the `--skip-backup` option.</span></span>

<span data-ttu-id="12607-121">De forma predeterminada, la operación de migración genera el estado del proceso de migración a la salida estándar (STDOUT).</span><span class="sxs-lookup"><span data-stu-id="12607-121">By default, the migration operation outputs the state of the migration process to standard output (STDOUT).</span></span> <span data-ttu-id="12607-122">Si usa la opción `--report-file <REPORT_FILE>`, la salida se guarda en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="12607-122">If you use the `--report-file <REPORT_FILE>` option, the output is saved to the file specify.</span></span>

<span data-ttu-id="12607-123">El comando `dotnet migrate` solo admite proyectos válidos basados en *project.json* de la versión preliminar 2.</span><span class="sxs-lookup"><span data-stu-id="12607-123">The `dotnet migrate` command only supports valid Preview 2 *project.json*-based projects.</span></span> <span data-ttu-id="12607-124">Esto significa que no se puede usar para migrar DNX o los proyectos basados en *project.json* de la versión preliminar 1 directamente a proyectos de MSBuild/csproj.</span><span class="sxs-lookup"><span data-stu-id="12607-124">This means that you cannot use it to migrate DNX or Preview 1 *project.json*-based projects directly to MSBuild/csproj projects.</span></span> <span data-ttu-id="12607-125">Primero debe migrar manualmente el proyecto a un proyecto basado en *project.json* de la versión preliminar 2 y luego usar el comando `dotnet migrate` para migrar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="12607-125">You first need to manually migrate the project to a Preview 2 *project.json*-based project and then use the `dotnet migrate` command to migrate the project.</span></span>

## <a name="arguments"></a><span data-ttu-id="12607-126">Argumentos</span><span class="sxs-lookup"><span data-stu-id="12607-126">Arguments</span></span>

`PROJECT_JSON/GLOBAL_JSON/SOLUTION_FILE/PROJECT_DIR`

<span data-ttu-id="12607-127">La ruta de acceso a uno de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="12607-127">The path to one of the following:</span></span>

* <span data-ttu-id="12607-128">Un archivo *project.json* para migrar.</span><span class="sxs-lookup"><span data-stu-id="12607-128">a *project.json* file to migrate.</span></span>
* <span data-ttu-id="12607-129">Un archivo *global.json*: se migran las carpetas especificadas en *global.json*.</span><span class="sxs-lookup"><span data-stu-id="12607-129">a *global.json* file: the folders specified in *global.json* are migrated.</span></span>
* <span data-ttu-id="12607-130">Un archivo *solution.sln*: se migran los proyectos a los que se hace referencia en la solución.</span><span class="sxs-lookup"><span data-stu-id="12607-130">a *solution.sln* file: the projects referenced in the solution are migrated.</span></span>
* <span data-ttu-id="12607-131">Un directorio para migrar: se buscan de forma recursiva los archivos *project.json* que se van a migrar dentro del directorio especificado.</span><span class="sxs-lookup"><span data-stu-id="12607-131">a directory to migrate: recursively searches for *project.json* files to migrate inside the specified directory.</span></span>

<span data-ttu-id="12607-132">Si no se especifica nada, se toma como valor predeterminado el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="12607-132">Defaults to current directory if nothing is specified.</span></span>

## <a name="options"></a><span data-ttu-id="12607-133">Opciones</span><span class="sxs-lookup"><span data-stu-id="12607-133">Options</span></span>

`--format-report-file-json <REPORT_FILE>`

<span data-ttu-id="12607-134">Salida del archivo de informe de migración como JSON en lugar de mensajes de usuario.</span><span class="sxs-lookup"><span data-stu-id="12607-134">Output migration report file as JSON rather than user messages.</span></span>

`-h|--help`

<span data-ttu-id="12607-135">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="12607-135">Prints out a short help for the command.</span></span>

`-r|--report-file <REPORT_FILE>`

<span data-ttu-id="12607-136">Salida del informe de migración a un archivo además de a la consola.</span><span class="sxs-lookup"><span data-stu-id="12607-136">Output migration report to a file in addition to the console.</span></span>

`-s|--skip-project-references [Debug|Release]`

<span data-ttu-id="12607-137">Omite la migración de referencias de proyecto.</span><span class="sxs-lookup"><span data-stu-id="12607-137">Skip migrating project references.</span></span> <span data-ttu-id="12607-138">De forma predeterminada, las referencias de proyecto se migran de forma recursiva.</span><span class="sxs-lookup"><span data-stu-id="12607-138">By default, project references are migrated recursively.</span></span>

`--skip-backup`

<span data-ttu-id="12607-139">Omite el traslado de *project.json*, *global.json* y *\*.xproj* a un directorio `backup` tras la realización correcta de la migración.</span><span class="sxs-lookup"><span data-stu-id="12607-139">Skip moving *project.json*, *global.json*, and *\*.xproj* to a `backup` directory after successful migration.</span></span>

`-t|--template-file <TEMPLATE_FILE>`

<span data-ttu-id="12607-140">Archivo csproj de plantilla que se utilizará para la migración.</span><span class="sxs-lookup"><span data-stu-id="12607-140">Template csproj file to use for migration.</span></span> <span data-ttu-id="12607-141">De forma predeterminada, se usa la misma plantilla que la descartada por `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="12607-141">By default, the same template as the one dropped by `dotnet new console` is used.</span></span>

`-v|--sdk-package-version <VERSION>`

<span data-ttu-id="12607-142">La versión del paquete sdk a la que se hace referencia en la aplicación migrada.</span><span class="sxs-lookup"><span data-stu-id="12607-142">The version of the sdk package that's referenced in the migrated app.</span></span> <span data-ttu-id="12607-143">El valor predeterminado es la versión del SDK en `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="12607-143">The default is the version of the SDK in `dotnet new`.</span></span>

`-x|--xproj-file <FILE>`

<span data-ttu-id="12607-144">La ruta de acceso al archivo xproj que se usará.</span><span class="sxs-lookup"><span data-stu-id="12607-144">The path to the xproj file to use.</span></span> <span data-ttu-id="12607-145">Necesario cuando hay más de un archivo xproj en un directorio de proyecto.</span><span class="sxs-lookup"><span data-stu-id="12607-145">Required when there is more than one xproj in a project directory.</span></span>

## <a name="examples"></a><span data-ttu-id="12607-146">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="12607-146">Examples</span></span>

<span data-ttu-id="12607-147">Migrar un proyecto del directorio actual y todas sus dependencias de proyecto a proyecto:</span><span class="sxs-lookup"><span data-stu-id="12607-147">Migrate a project in the current directory and all of its project-to-project dependencies:</span></span>

`dotnet migrate`

<span data-ttu-id="12607-148">Migrar todos los proyectos que incluyen el archivo *global.json*:</span><span class="sxs-lookup"><span data-stu-id="12607-148">Migrate all projects that *global.json* file includes:</span></span>

`dotnet migrate path/to/global.json`

<span data-ttu-id="12607-149">Migrar solo el proyecto actual y ninguna dependencia de proyecto a proyecto (P2P).</span><span class="sxs-lookup"><span data-stu-id="12607-149">Migrate only the current project and no project-to-project (P2P) dependencies.</span></span> <span data-ttu-id="12607-150">Además, usar una versión específica de SDK:</span><span class="sxs-lookup"><span data-stu-id="12607-150">Also, use a specific SDK version:</span></span>

`dotnet migrate -s -v 1.0.0-preview4`
