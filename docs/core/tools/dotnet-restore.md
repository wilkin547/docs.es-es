---
title: 'Comando dotnet restore: CLI de .NET Core'
description: "Aprenda a restaurar dependencias y herramientas específicas del proyecto con el comando dotnet restore."
keywords: dotnet-restore, CLI, comando de la CLI, .NET Core
author: mairaw
ms.author: mairaw
ms.date: 11/30/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: 887f562803226d99901a6ee13175c1a43956b0cd
ms.sourcegitcommit: f416ac259c1a771e4e6c72728d8c11a77082f11c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="dotnet-restore"></a><span data-ttu-id="cc146-104">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="cc146-104">dotnet restore</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="cc146-105">Name</span><span class="sxs-lookup"><span data-stu-id="cc146-105">Name</span></span>

<span data-ttu-id="cc146-106">`dotnet restore`: restaura las dependencias y las herramientas de un proyecto.</span><span class="sxs-lookup"><span data-stu-id="cc146-106">`dotnet restore` - Restores the dependencies and tools of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="cc146-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="cc146-107">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="cc146-108">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="cc146-108">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--force] [--ignore-failed-sources] [--no-cache] [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity]
dotnet restore [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="cc146-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="cc146-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--ignore-failed-sources] [--no-cache] [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity]
dotnet restore [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="cc146-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc146-110">Description</span></span>

<span data-ttu-id="cc146-111">El comando `dotnet restore` usa NuGet para restaurar las dependencias, así como las herramientas específicas del proyecto que se especifican en el archivo project.json.</span><span class="sxs-lookup"><span data-stu-id="cc146-111">The `dotnet restore` command uses NuGet to restore dependencies as well as project-specific tools that are specified in the project file.</span></span> <span data-ttu-id="cc146-112">De forma predeterminada, la restauración de dependencias y herramientas se realiza en paralelo.</span><span class="sxs-lookup"><span data-stu-id="cc146-112">By default, the restoration of dependencies and tools are performed in parallel.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="cc146-113">Para restaurar las dependencias, NuGet necesita las fuentes donde se encuentran los paquetes.</span><span class="sxs-lookup"><span data-stu-id="cc146-113">In order to restore the dependencies, NuGet needs the feeds where the packages are located.</span></span> <span data-ttu-id="cc146-114">Las fuente se proporcionan normalmente mediante el archivo de configuración *NuGet.config*.</span><span class="sxs-lookup"><span data-stu-id="cc146-114">Feeds are usually provided via the *NuGet.config* configuration file.</span></span> <span data-ttu-id="cc146-115">Cuando se instalan las herramientas de la CLI, se proporciona un archivo de configuración predeterminado.</span><span class="sxs-lookup"><span data-stu-id="cc146-115">A default configuration file is provided when the CLI tools are installed.</span></span> <span data-ttu-id="cc146-116">Puede especificar más fuentes creando su propio archivo *NuGet.config* en el directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="cc146-116">You specify additional feeds by creating your own *NuGet.config* file in the project directory.</span></span> <span data-ttu-id="cc146-117">También puede especificar fuentes adicionales por invocación en un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="cc146-117">You also specify additional feeds per invocation at a command prompt.</span></span>

<span data-ttu-id="cc146-118">Para las dependencias, puede especificar dónde se colocan los paquetes restaurados durante la operación de restauración mediante el argumento `--packages`.</span><span class="sxs-lookup"><span data-stu-id="cc146-118">For dependencies, you specify where the restored packages are placed during the restore operation using the `--packages` argument.</span></span> <span data-ttu-id="cc146-119">Si no se especifica, se usa la caché de paquetes NuGet predeterminada, que se encuentra en el directorio `.nuget/packages` en el directorio de inicio del usuario en todos los sistemas operativos (por ejemplo, */home/user1* en Linux o *C:\Users\user1* en Windows).</span><span class="sxs-lookup"><span data-stu-id="cc146-119">If not specified, the default NuGet package cache is used, which is found in the `.nuget/packages` directory in the user's home directory on all operating systems (for example, */home/user1* on Linux or *C:\Users\user1* on Windows).</span></span>

<span data-ttu-id="cc146-120">Para herramientas específicas del proyecto, `dotnet restore` restaura primero el paquete en el que se empaqueta la herramienta y, a continuación, continúa con la restauración de las dependencias de la herramienta especificadas en su project.json.</span><span class="sxs-lookup"><span data-stu-id="cc146-120">For project-specific tooling, `dotnet restore` first restores the package in which the tool is packed, and then proceeds to restore the tool's dependencies as specified in its project file.</span></span>

<span data-ttu-id="cc146-121">El comportamiento del comando `dotnet restore` depende de algunas de las opciones de configuración del archivo *Nuget.Config*, si están presentes.</span><span class="sxs-lookup"><span data-stu-id="cc146-121">The behavior of the `dotnet restore` command is affected by some of the settings in the *Nuget.Config* file, if present.</span></span> <span data-ttu-id="cc146-122">Por ejemplo, establecer `globalPackagesFolder` en *NuGet.Config* coloca los paquetes NuGet restaurados en la carpeta especificada.</span><span class="sxs-lookup"><span data-stu-id="cc146-122">For example, setting the `globalPackagesFolder` in *NuGet.Config* places the restored NuGet packages in the specified folder.</span></span> <span data-ttu-id="cc146-123">Esta es una alternativa para especificar la opción `--packages` en el comando `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="cc146-123">This is an alternative to specifying the `--packages` option on the `dotnet restore` command.</span></span> <span data-ttu-id="cc146-124">Para obtener más información, vea la [referencia de NuGet.Config](/nuget/schema/nuget-config-file).</span><span class="sxs-lookup"><span data-stu-id="cc146-124">For more information, see the [NuGet.Config reference](/nuget/schema/nuget-config-file).</span></span>

## <a name="implicit-dotnet-restore"></a><span data-ttu-id="cc146-125">`dotnet restore` implícito</span><span class="sxs-lookup"><span data-stu-id="cc146-125">Implicit `dotnet restore`</span></span>

<span data-ttu-id="cc146-126">A partir de .NET Core 2.0, `dotnet restore` se ejecuta de forma implícita si es necesario al emitir los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="cc146-126">Starting with .NET Core 2.0, `dotnet restore` is run implicitly if necessary when you issue the following commands:</span></span>

- [`dotnet new`](dotnet-new.md)
- [`dotnet build`](dotnet-build.md)
- [`dotnet run`](dotnet-run.md)
- [`dotnet test`](dotnet-test.md)
- [`dotnet publish`](dotnet-publish.md)
- [`dotnet pack`](dotnet-pack.md)

<span data-ttu-id="cc146-127">En la mayoría de los casos, ya no necesita utilizar explícitamente el comando `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="cc146-127">In most cases, you no longer need to explicitly use the `dotnet restore` command.</span></span> 

<span data-ttu-id="cc146-128">En algunos casos, la ejecución implícita resulta poco práctica para `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="cc146-128">In some cases, it is inconvenient for `dotnet restore` to run implicitly.</span></span> <span data-ttu-id="cc146-129">Por ejemplo, algunos sistemas automatizados, como los sistemas de compilación, deben llamar a `dotnet restore` explícitamente para controlar cuándo se produce la restauración a fin de controlar el uso de la red.</span><span class="sxs-lookup"><span data-stu-id="cc146-129">For example, some automated systems, such as build systems, need to call `dotnet restore` explicitly to control when the restore occurs so that they can control network usage.</span></span> <span data-ttu-id="cc146-130">Para evitar que `dotnet restore` se ejecute implícitamente, puede usar el conmutador `--no-restore` con cualquiera de estos comandos para deshabilitar la restauración implícita.</span><span class="sxs-lookup"><span data-stu-id="cc146-130">To prevent `dotnet restore` from running implicitly, you can use the `--no-restore` switch with any of these commands to disable implicit restore.</span></span>

## <a name="arguments"></a><span data-ttu-id="cc146-131">Argumentos</span><span class="sxs-lookup"><span data-stu-id="cc146-131">Arguments</span></span>

`ROOT`

<span data-ttu-id="cc146-132">Ruta de acceso opcional del archivo de proyecto para restaurar.</span><span class="sxs-lookup"><span data-stu-id="cc146-132">Optional path to the project file to restore.</span></span>

## <a name="options"></a><span data-ttu-id="cc146-133">Opciones</span><span class="sxs-lookup"><span data-stu-id="cc146-133">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="cc146-134">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="cc146-134">.NET Core 2.x</span></span>](#tab/netcore2x)

`--configfile <FILE>`

<span data-ttu-id="cc146-135">El archivo de configuración (*NuGet.config*) que se usa para la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="cc146-135">The NuGet configuration file (*NuGet.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="cc146-136">Deshabilita la restauración de varios proyectos en paralelo.</span><span class="sxs-lookup"><span data-stu-id="cc146-136">Disables restoring multiple projects in parallel.</span></span>

`--force`

<span data-ttu-id="cc146-137">Fuerza la resolución de todas las dependencias, incluso si la última restauración se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="cc146-137">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="cc146-138">Esto es equivalente a eliminar el archivo *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="cc146-138">This is equivalent to deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="cc146-139">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="cc146-139">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="cc146-140">Solo se advierte sobre los orígenes con error si hay paquetes que satisfagan el requisito de versión.</span><span class="sxs-lookup"><span data-stu-id="cc146-140">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="cc146-141">Especifica que no se almacenen en caché los paquetes y las solicitudes HTTP.</span><span class="sxs-lookup"><span data-stu-id="cc146-141">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="cc146-142">Al restaurar un proyecto con referencias de proyecto a proyecto (P2P), se restaura el proyecto raíz y no las referencias.</span><span class="sxs-lookup"><span data-stu-id="cc146-142">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="cc146-143">Especifica el directorio de los paquetes restaurados.</span><span class="sxs-lookup"><span data-stu-id="cc146-143">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="cc146-144">Especifica un tiempo de ejecución para la restauración del paquete.</span><span class="sxs-lookup"><span data-stu-id="cc146-144">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="cc146-145">Se usa para restaurar los paquetes con tiempos de ejecución que no se enumeran explícitamente en la etiqueta `<RuntimeIdentifiers>` del archivo *.csproj*.</span><span class="sxs-lookup"><span data-stu-id="cc146-145">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="cc146-146">Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="cc146-146">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="cc146-147">Para proporcionar varios RID; especifique esta opción varias veces.</span><span class="sxs-lookup"><span data-stu-id="cc146-147">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="cc146-148">Especifica un origen de paquetes de NuGet que se usará durante la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="cc146-148">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="cc146-149">Esto invalida todos los orígenes especificados en los archivos *NuGet.config*.</span><span class="sxs-lookup"><span data-stu-id="cc146-149">This overrides all of the sources specified in the *NuGet.config* file(s).</span></span> <span data-ttu-id="cc146-150">Al especificar esta opción varias veces, se pueden proporcionar varios orígenes.</span><span class="sxs-lookup"><span data-stu-id="cc146-150">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="cc146-151">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="cc146-151">Sets the verbosity level of the command.</span></span> <span data-ttu-id="cc146-152">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="cc146-152">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="cc146-153">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="cc146-153">.NET Core 1.x</span></span>](#tab/netcore1x)

`--configfile <FILE>`

<span data-ttu-id="cc146-154">El archivo de configuración (*NuGet.config*) que se usa para la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="cc146-154">The NuGet configuration file (*NuGet.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="cc146-155">Deshabilita la restauración de varios proyectos en paralelo.</span><span class="sxs-lookup"><span data-stu-id="cc146-155">Disables restoring multiple projects in parallel.</span></span>

`-h|--help`

<span data-ttu-id="cc146-156">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="cc146-156">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="cc146-157">Solo se advierte sobre los orígenes con error si hay paquetes que satisfagan el requisito de versión.</span><span class="sxs-lookup"><span data-stu-id="cc146-157">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="cc146-158">Especifica que no se almacenen en caché los paquetes y las solicitudes HTTP.</span><span class="sxs-lookup"><span data-stu-id="cc146-158">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="cc146-159">Al restaurar un proyecto con referencias de proyecto a proyecto (P2P), se restaura el proyecto raíz y no las referencias.</span><span class="sxs-lookup"><span data-stu-id="cc146-159">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="cc146-160">Especifica el directorio de los paquetes restaurados.</span><span class="sxs-lookup"><span data-stu-id="cc146-160">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="cc146-161">Especifica un tiempo de ejecución para la restauración del paquete.</span><span class="sxs-lookup"><span data-stu-id="cc146-161">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="cc146-162">Se usa para restaurar los paquetes con tiempos de ejecución que no se enumeran explícitamente en la etiqueta `<RuntimeIdentifiers>` del archivo *.csproj*.</span><span class="sxs-lookup"><span data-stu-id="cc146-162">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="cc146-163">Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="cc146-163">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="cc146-164">Para proporcionar varios RID; especifique esta opción varias veces.</span><span class="sxs-lookup"><span data-stu-id="cc146-164">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="cc146-165">Especifica un origen de paquetes de NuGet que se usará durante la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="cc146-165">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="cc146-166">Esto invalida todos los orígenes especificados en los archivos *NuGet.config*.</span><span class="sxs-lookup"><span data-stu-id="cc146-166">This overrides all of the sources specified in the *NuGet.config* file(s).</span></span> <span data-ttu-id="cc146-167">Al especificar esta opción varias veces, se pueden proporcionar varios orígenes.</span><span class="sxs-lookup"><span data-stu-id="cc146-167">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="cc146-168">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="cc146-168">Sets the verbosity level of the command.</span></span> <span data-ttu-id="cc146-169">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="cc146-169">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="cc146-170">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="cc146-170">Examples</span></span>

<span data-ttu-id="cc146-171">Restauración de dependencias y herramientas para el proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="cc146-171">Restore dependencies and tools for the project in the current directory:</span></span>

`dotnet restore`

<span data-ttu-id="cc146-172">Restauración de dependencias y herramientas para el proyecto `app1` encontrado en la ruta de acceso dada:</span><span class="sxs-lookup"><span data-stu-id="cc146-172">Restore dependencies and tools for the `app1` project found in the given path:</span></span>

`dotnet restore ~/projects/app1/app1.csproj`

<span data-ttu-id="cc146-173">Restaurar las dependencias y las herramientas para el proyecto en el directorio actual con la ruta de acceso de archivo proporcionada como origen:</span><span class="sxs-lookup"><span data-stu-id="cc146-173">Restore the dependencies and tools for the project in the current directory using the file path provided as the source:</span></span>

`dotnet restore -s c:\packages\mypackages`

<span data-ttu-id="cc146-174">Restaurar las dependencias y las herramientas para el proyecto en el directorio actual mediante las dos rutas de acceso de archivo proporcionadas como orígenes:</span><span class="sxs-lookup"><span data-stu-id="cc146-174">Restore the dependencies and tools for the project in the current directory using the two file paths provided as sources:</span></span>

`dotnet restore -s c:\packages\mypackages -s c:\packages\myotherpackages`

<span data-ttu-id="cc146-175">Restaurar las dependencias y herramientas para el proyecto en el directorio actual y mostrar únicamente la salida mínima:</span><span class="sxs-lookup"><span data-stu-id="cc146-175">Restore dependencies and tools for the project in the current directory and shows only minimal output:</span></span>

`dotnet restore --verbosity minimal`
