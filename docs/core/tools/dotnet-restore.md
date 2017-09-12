---
title: 'Comando dotnet restore: CLI de .NET Core'
description: "Aprenda a restaurar dependencias y herramientas específicas del proyecto con el comando dotnet restore."
keywords: dotnet-restore, CLI, comando de la CLI, .NET Core
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.translationtype: HT
ms.sourcegitcommit: 019461964ba63d874ce86511474aa37b4342bbc4
ms.openlocfilehash: 86de979257d4e1be3a29d8876494b7f4966e5b1c
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---
# <a name="dotnet-restore"></a><span data-ttu-id="d957b-104">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="d957b-104">dotnet restore</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="d957b-105">Nombre</span><span class="sxs-lookup"><span data-stu-id="d957b-105">Name</span></span>

<span data-ttu-id="d957b-106">`dotnet restore`: restaura las dependencias y las herramientas de un proyecto.</span><span class="sxs-lookup"><span data-stu-id="d957b-106">`dotnet restore` - Restores the dependencies and tools of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d957b-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="d957b-107">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d957b-108">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d957b-108">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--force] [--ignore-failed-sources] [--no-cache] [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity]
dotnet restore [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d957b-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d957b-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--ignore-failed-sources] [--no-cache] [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity]
dotnet restore [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="d957b-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="d957b-110">Description</span></span>

<span data-ttu-id="d957b-111">El comando `dotnet restore` usa NuGet para restaurar las dependencias, así como las herramientas específicas del proyecto que se especifican en el archivo project.json.</span><span class="sxs-lookup"><span data-stu-id="d957b-111">The `dotnet restore` command uses NuGet to restore dependencies as well as project-specific tools that are specified in the project file.</span></span> <span data-ttu-id="d957b-112">De forma predeterminada, la restauración de dependencias y herramientas se realiza en paralelo.</span><span class="sxs-lookup"><span data-stu-id="d957b-112">By default, the restoration of dependencies and tools are performed in parallel.</span></span>

<span data-ttu-id="d957b-113">Para restaurar las dependencias, NuGet necesita las fuentes donde se encuentran los paquetes.</span><span class="sxs-lookup"><span data-stu-id="d957b-113">In order to restore the dependencies, NuGet needs the feeds where the packages are located.</span></span> <span data-ttu-id="d957b-114">Las fuente se proporcionan normalmente mediante el archivo de configuración *NuGet.config*.</span><span class="sxs-lookup"><span data-stu-id="d957b-114">Feeds are usually provided via the *NuGet.config* configuration file.</span></span> <span data-ttu-id="d957b-115">Cuando se instalan las herramientas de la CLI, se proporciona un archivo de configuración predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d957b-115">A default configuration file is provided when the CLI tools are installed.</span></span> <span data-ttu-id="d957b-116">Puede especificar más fuentes creando su propio archivo *NuGet.config* en el directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="d957b-116">You specify additional feeds by creating your own *NuGet.config* file in the project directory.</span></span> <span data-ttu-id="d957b-117">También puede especificar fuentes adicionales por invocación en un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="d957b-117">You also specify additional feeds per invocation at a command prompt.</span></span>

<span data-ttu-id="d957b-118">Para las dependencias, puede especificar dónde se colocan los paquetes restaurados durante la operación de restauración mediante el argumento `--packages`.</span><span class="sxs-lookup"><span data-stu-id="d957b-118">For dependencies, you specify where the restored packages are placed during the restore operation using the `--packages` argument.</span></span> <span data-ttu-id="d957b-119">Si no se especifica, se usa la caché de paquetes NuGet predeterminada, que se encuentra en el directorio `.nuget/packages` en el directorio de inicio del usuario en todos los sistemas operativos (por ejemplo, */home/user1* en Linux o *C:\Users\user1* en Windows).</span><span class="sxs-lookup"><span data-stu-id="d957b-119">If not specified, the default NuGet package cache is used, which is found in the `.nuget/packages` directory in the user's home directory on all operating systems (for example, */home/user1* on Linux or *C:\Users\user1* on Windows).</span></span>

<span data-ttu-id="d957b-120">Para herramientas específicas del proyecto, `dotnet restore` restaura primero el paquete en el que se empaqueta la herramienta y, a continuación, continúa con la restauración de las dependencias de la herramienta especificadas en su project.json.</span><span class="sxs-lookup"><span data-stu-id="d957b-120">For project-specific tooling, `dotnet restore` first restores the package in which the tool is packed, and then proceeds to restore the tool's dependencies as specified in its project file.</span></span>

<span data-ttu-id="d957b-121">El comportamiento del comando `dotnet restore` depende de algunas de las opciones de configuración del archivo *Nuget.Config*, si están presentes.</span><span class="sxs-lookup"><span data-stu-id="d957b-121">The behavior of the `dotnet restore` command is affected by some of the settings in the *Nuget.Config* file, if present.</span></span> <span data-ttu-id="d957b-122">Por ejemplo, establecer `globalPackagesFolder` en *NuGet.Config* coloca los paquetes NuGet restaurados en la carpeta especificada.</span><span class="sxs-lookup"><span data-stu-id="d957b-122">For example, setting the `globalPackagesFolder` in *NuGet.Config* places the restored NuGet packages in the specified folder.</span></span> <span data-ttu-id="d957b-123">Esta es una alternativa para especificar la opción `--packages` en el comando `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="d957b-123">This is an alternative to specifying the `--packages` option on the `dotnet restore` command.</span></span> <span data-ttu-id="d957b-124">Para obtener más información, vea la [referencia de NuGet.Config](/nuget/schema/nuget-config-file).</span><span class="sxs-lookup"><span data-stu-id="d957b-124">For more information, see the [NuGet.Config reference](/nuget/schema/nuget-config-file).</span></span>

## <a name="arguments"></a><span data-ttu-id="d957b-125">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d957b-125">Arguments</span></span>

`ROOT`

<span data-ttu-id="d957b-126">Ruta de acceso opcional del archivo de proyecto para restaurar.</span><span class="sxs-lookup"><span data-stu-id="d957b-126">Optional path to the project file to restore.</span></span>

## <a name="options"></a><span data-ttu-id="d957b-127">Opciones</span><span class="sxs-lookup"><span data-stu-id="d957b-127">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d957b-128">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d957b-128">.NET Core 2.x</span></span>](#tab/netcore2x)

`--configfile <FILE>`

<span data-ttu-id="d957b-129">El archivo de configuración (*NuGet.config*) que se usa para la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="d957b-129">The NuGet configuration file (*NuGet.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="d957b-130">Deshabilita la restauración de varios proyectos en paralelo.</span><span class="sxs-lookup"><span data-stu-id="d957b-130">Disables restoring multiple projects in parallel.</span></span>

`--force`

<span data-ttu-id="d957b-131">Fuerza la resolución de todas las dependencias, incluso si la última restauración se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="d957b-131">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="d957b-132">Esto es equivalente a eliminar el archivo *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="d957b-132">This is equivalent to deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="d957b-133">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="d957b-133">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="d957b-134">Solo se advierte sobre los orígenes con error si hay paquetes que satisfagan el requisito de versión.</span><span class="sxs-lookup"><span data-stu-id="d957b-134">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="d957b-135">Especifica que no se almacenen en caché los paquetes y las solicitudes HTTP.</span><span class="sxs-lookup"><span data-stu-id="d957b-135">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="d957b-136">Al restaurar un proyecto con referencias de proyecto a proyecto (P2P), se restaura el proyecto raíz y no las referencias.</span><span class="sxs-lookup"><span data-stu-id="d957b-136">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="d957b-137">Especifica el directorio de los paquetes restaurados.</span><span class="sxs-lookup"><span data-stu-id="d957b-137">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="d957b-138">Especifica un tiempo de ejecución para la restauración del paquete.</span><span class="sxs-lookup"><span data-stu-id="d957b-138">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="d957b-139">Se usa para restaurar los paquetes con tiempos de ejecución que no se enumeran explícitamente en la etiqueta `<RuntimeIdentifiers>` del archivo *.csproj*.</span><span class="sxs-lookup"><span data-stu-id="d957b-139">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="d957b-140">Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="d957b-140">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="d957b-141">Para proporcionar varios RID; especifique esta opción varias veces.</span><span class="sxs-lookup"><span data-stu-id="d957b-141">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="d957b-142">Especifica un origen de paquetes de NuGet que se usará durante la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="d957b-142">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="d957b-143">Esto invalida todos los orígenes especificados en los archivos *NuGet.config*.</span><span class="sxs-lookup"><span data-stu-id="d957b-143">This overrides all of the sources specified in the *NuGet.config* file(s).</span></span> <span data-ttu-id="d957b-144">Al especificar esta opción varias veces, se pueden proporcionar varios orígenes.</span><span class="sxs-lookup"><span data-stu-id="d957b-144">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="d957b-145">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="d957b-145">Sets the verbosity level of the command.</span></span> <span data-ttu-id="d957b-146">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="d957b-146">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d957b-147">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d957b-147">.NET Core 1.x</span></span>](#tab/netcore1x)

`--configfile <FILE>`

<span data-ttu-id="d957b-148">El archivo de configuración (*NuGet.config*) que se usa para la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="d957b-148">The NuGet configuration file (*NuGet.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="d957b-149">Deshabilita la restauración de varios proyectos en paralelo.</span><span class="sxs-lookup"><span data-stu-id="d957b-149">Disables restoring multiple projects in parallel.</span></span>

`-h|--help`

<span data-ttu-id="d957b-150">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="d957b-150">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="d957b-151">Solo se advierte sobre los orígenes con error si hay paquetes que satisfagan el requisito de versión.</span><span class="sxs-lookup"><span data-stu-id="d957b-151">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="d957b-152">Especifica que no se almacenen en caché los paquetes y las solicitudes HTTP.</span><span class="sxs-lookup"><span data-stu-id="d957b-152">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="d957b-153">Al restaurar un proyecto con referencias de proyecto a proyecto (P2P), se restaura el proyecto raíz y no las referencias.</span><span class="sxs-lookup"><span data-stu-id="d957b-153">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="d957b-154">Especifica el directorio de los paquetes restaurados.</span><span class="sxs-lookup"><span data-stu-id="d957b-154">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="d957b-155">Especifica un tiempo de ejecución para la restauración del paquete.</span><span class="sxs-lookup"><span data-stu-id="d957b-155">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="d957b-156">Se usa para restaurar los paquetes con tiempos de ejecución que no se enumeran explícitamente en la etiqueta `<RuntimeIdentifiers>` del archivo *.csproj*.</span><span class="sxs-lookup"><span data-stu-id="d957b-156">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="d957b-157">Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="d957b-157">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="d957b-158">Para proporcionar varios RID; especifique esta opción varias veces.</span><span class="sxs-lookup"><span data-stu-id="d957b-158">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="d957b-159">Especifica un origen de paquetes de NuGet que se usará durante la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="d957b-159">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="d957b-160">Esto invalida todos los orígenes especificados en los archivos *NuGet.config*.</span><span class="sxs-lookup"><span data-stu-id="d957b-160">This overrides all of the sources specified in the *NuGet.config* file(s).</span></span> <span data-ttu-id="d957b-161">Al especificar esta opción varias veces, se pueden proporcionar varios orígenes.</span><span class="sxs-lookup"><span data-stu-id="d957b-161">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="d957b-162">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="d957b-162">Sets the verbosity level of the command.</span></span> <span data-ttu-id="d957b-163">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="d957b-163">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="d957b-164">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="d957b-164">Examples</span></span>

<span data-ttu-id="d957b-165">Restauración de dependencias y herramientas para el proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="d957b-165">Restore dependencies and tools for the project in the current directory:</span></span>

`dotnet restore`

<span data-ttu-id="d957b-166">Restauración de dependencias y herramientas para el proyecto `app1` encontrado en la ruta de acceso dada:</span><span class="sxs-lookup"><span data-stu-id="d957b-166">Restore dependencies and tools for the `app1` project found in the given path:</span></span>

`dotnet restore ~/projects/app1/app1.csproj`

<span data-ttu-id="d957b-167">Restaurar las dependencias y las herramientas para el proyecto en el directorio actual con la ruta de acceso de archivo proporcionada como origen:</span><span class="sxs-lookup"><span data-stu-id="d957b-167">Restore the dependencies and tools for the project in the current directory using the file path provided as the source:</span></span>

`dotnet restore -s c:\packages\mypackages`

<span data-ttu-id="d957b-168">Restaurar las dependencias y las herramientas para el proyecto en el directorio actual mediante las dos rutas de acceso de archivo proporcionadas como orígenes:</span><span class="sxs-lookup"><span data-stu-id="d957b-168">Restore the dependencies and tools for the project in the current directory using the two file paths provided as sources:</span></span>

`dotnet restore -s c:\packages\mypackages -s c:\packages\myotherpackages`

<span data-ttu-id="d957b-169">Restaurar las dependencias y herramientas para el proyecto en el directorio actual y mostrar únicamente la salida mínima:</span><span class="sxs-lookup"><span data-stu-id="d957b-169">Restore dependencies and tools for the project in the current directory and shows only minimal output:</span></span>

`dotnet restore --verbosity minimal`

