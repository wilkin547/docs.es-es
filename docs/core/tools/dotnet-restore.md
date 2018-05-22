---
title: 'Comando dotnet restore: CLI de .NET Core'
description: Aprenda a restaurar dependencias y herramientas específicas del proyecto con el comando dotnet restore.
author: mairaw
ms.author: mairaw
ms.date: 11/30/2017
ms.openlocfilehash: 6f8aaa2060ab7e6b2e9b99ce4d35588c2bf54d36
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="dotnet-restore"></a><span data-ttu-id="79787-103">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="79787-103">dotnet restore</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="79787-104">nombre</span><span class="sxs-lookup"><span data-stu-id="79787-104">Name</span></span>

<span data-ttu-id="79787-105">`dotnet restore`: restaura las dependencias y las herramientas de un proyecto.</span><span class="sxs-lookup"><span data-stu-id="79787-105">`dotnet restore` - Restores the dependencies and tools of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="79787-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="79787-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="79787-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="79787-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--force] [--ignore-failed-sources] [--no-cache] [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity]
dotnet restore [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="79787-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="79787-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--ignore-failed-sources] [--no-cache] [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity]
dotnet restore [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="79787-109">Description</span><span class="sxs-lookup"><span data-stu-id="79787-109">Description</span></span>

<span data-ttu-id="79787-110">El comando `dotnet restore` usa NuGet para restaurar las dependencias, así como las herramientas específicas del proyecto que se especifican en el archivo project.json.</span><span class="sxs-lookup"><span data-stu-id="79787-110">The `dotnet restore` command uses NuGet to restore dependencies as well as project-specific tools that are specified in the project file.</span></span> <span data-ttu-id="79787-111">De forma predeterminada, la restauración de dependencias y herramientas se realiza en paralelo.</span><span class="sxs-lookup"><span data-stu-id="79787-111">By default, the restoration of dependencies and tools are performed in parallel.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="79787-112">Para restaurar las dependencias, NuGet necesita las fuentes donde se encuentran los paquetes.</span><span class="sxs-lookup"><span data-stu-id="79787-112">In order to restore the dependencies, NuGet needs the feeds where the packages are located.</span></span> <span data-ttu-id="79787-113">Las fuente se proporcionan normalmente mediante el archivo de configuración *NuGet.config*.</span><span class="sxs-lookup"><span data-stu-id="79787-113">Feeds are usually provided via the *NuGet.config* configuration file.</span></span> <span data-ttu-id="79787-114">Cuando se instalan las herramientas de la CLI, se proporciona un archivo de configuración predeterminado.</span><span class="sxs-lookup"><span data-stu-id="79787-114">A default configuration file is provided when the CLI tools are installed.</span></span> <span data-ttu-id="79787-115">Puede especificar más fuentes creando su propio archivo *NuGet.config* en el directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="79787-115">You specify additional feeds by creating your own *NuGet.config* file in the project directory.</span></span> <span data-ttu-id="79787-116">También puede especificar fuentes adicionales por invocación en un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="79787-116">You also specify additional feeds per invocation at a command prompt.</span></span>

<span data-ttu-id="79787-117">Para las dependencias, puede especificar dónde se colocan los paquetes restaurados durante la operación de restauración mediante el argumento `--packages`.</span><span class="sxs-lookup"><span data-stu-id="79787-117">For dependencies, you specify where the restored packages are placed during the restore operation using the `--packages` argument.</span></span> <span data-ttu-id="79787-118">Si no se especifica, se usa la caché de paquetes NuGet predeterminada, que se encuentra en el directorio `.nuget/packages` en el directorio de inicio del usuario en todos los sistemas operativos (por ejemplo, */home/user1* en Linux o *C:\Users\user1* en Windows).</span><span class="sxs-lookup"><span data-stu-id="79787-118">If not specified, the default NuGet package cache is used, which is found in the `.nuget/packages` directory in the user's home directory on all operating systems (for example, */home/user1* on Linux or *C:\Users\user1* on Windows).</span></span>

<span data-ttu-id="79787-119">Para herramientas específicas del proyecto, `dotnet restore` restaura primero el paquete en el que se empaqueta la herramienta y, a continuación, continúa con la restauración de las dependencias de la herramienta especificadas en su project.json.</span><span class="sxs-lookup"><span data-stu-id="79787-119">For project-specific tooling, `dotnet restore` first restores the package in which the tool is packed, and then proceeds to restore the tool's dependencies as specified in its project file.</span></span>

<span data-ttu-id="79787-120">El comportamiento del comando `dotnet restore` depende de algunas de las opciones de configuración del archivo *Nuget.Config*, si están presentes.</span><span class="sxs-lookup"><span data-stu-id="79787-120">The behavior of the `dotnet restore` command is affected by some of the settings in the *Nuget.Config* file, if present.</span></span> <span data-ttu-id="79787-121">Por ejemplo, establecer `globalPackagesFolder` en *NuGet.Config* coloca los paquetes NuGet restaurados en la carpeta especificada.</span><span class="sxs-lookup"><span data-stu-id="79787-121">For example, setting the `globalPackagesFolder` in *NuGet.Config* places the restored NuGet packages in the specified folder.</span></span> <span data-ttu-id="79787-122">Esta es una alternativa para especificar la opción `--packages` en el comando `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="79787-122">This is an alternative to specifying the `--packages` option on the `dotnet restore` command.</span></span> <span data-ttu-id="79787-123">Para obtener más información, vea la [referencia de NuGet.Config](/nuget/schema/nuget-config-file).</span><span class="sxs-lookup"><span data-stu-id="79787-123">For more information, see the [NuGet.Config reference](/nuget/schema/nuget-config-file).</span></span>

## <a name="implicit-dotnet-restore"></a><span data-ttu-id="79787-124">`dotnet restore` implícito</span><span class="sxs-lookup"><span data-stu-id="79787-124">Implicit `dotnet restore`</span></span>

<span data-ttu-id="79787-125">A partir de .NET Core 2.0, `dotnet restore` se ejecuta de forma implícita si es necesario al emitir los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="79787-125">Starting with .NET Core 2.0, `dotnet restore` is run implicitly if necessary when you issue the following commands:</span></span>

- [`dotnet new`](dotnet-new.md)
- [`dotnet build`](dotnet-build.md)
- [`dotnet run`](dotnet-run.md)
- [`dotnet test`](dotnet-test.md)
- [`dotnet publish`](dotnet-publish.md)
- [`dotnet pack`](dotnet-pack.md)

<span data-ttu-id="79787-126">En la mayoría de los casos, ya no necesita utilizar explícitamente el comando `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="79787-126">In most cases, you no longer need to explicitly use the `dotnet restore` command.</span></span> 

<span data-ttu-id="79787-127">En algunos casos, la ejecución implícita resulta poco práctica para `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="79787-127">In some cases, it is inconvenient for `dotnet restore` to run implicitly.</span></span> <span data-ttu-id="79787-128">Por ejemplo, algunos sistemas automatizados, como los sistemas de compilación, deben llamar a `dotnet restore` explícitamente para controlar cuándo se produce la restauración a fin de controlar el uso de la red.</span><span class="sxs-lookup"><span data-stu-id="79787-128">For example, some automated systems, such as build systems, need to call `dotnet restore` explicitly to control when the restore occurs so that they can control network usage.</span></span> <span data-ttu-id="79787-129">Para evitar que `dotnet restore` se ejecute implícitamente, puede usar el conmutador `--no-restore` con cualquiera de estos comandos para deshabilitar la restauración implícita.</span><span class="sxs-lookup"><span data-stu-id="79787-129">To prevent `dotnet restore` from running implicitly, you can use the `--no-restore` switch with any of these commands to disable implicit restore.</span></span>

## <a name="arguments"></a><span data-ttu-id="79787-130">Argumentos</span><span class="sxs-lookup"><span data-stu-id="79787-130">Arguments</span></span>

`ROOT`

<span data-ttu-id="79787-131">Ruta de acceso opcional del archivo de proyecto para restaurar.</span><span class="sxs-lookup"><span data-stu-id="79787-131">Optional path to the project file to restore.</span></span>

## <a name="options"></a><span data-ttu-id="79787-132">Opciones</span><span class="sxs-lookup"><span data-stu-id="79787-132">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="79787-133">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="79787-133">.NET Core 2.x</span></span>](#tab/netcore2x)

`--configfile <FILE>`

<span data-ttu-id="79787-134">El archivo de configuración (*NuGet.config*) que se usa para la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="79787-134">The NuGet configuration file (*NuGet.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="79787-135">Deshabilita la restauración de varios proyectos en paralelo.</span><span class="sxs-lookup"><span data-stu-id="79787-135">Disables restoring multiple projects in parallel.</span></span>

`--force`

<span data-ttu-id="79787-136">Fuerza la resolución de todas las dependencias, incluso si la última restauración se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="79787-136">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="79787-137">Esto es equivalente a eliminar el archivo *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="79787-137">This is equivalent to deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="79787-138">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="79787-138">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="79787-139">Solo se advierte sobre los orígenes con error si hay paquetes que satisfagan el requisito de versión.</span><span class="sxs-lookup"><span data-stu-id="79787-139">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="79787-140">Especifica que no se almacenen en caché los paquetes y las solicitudes HTTP.</span><span class="sxs-lookup"><span data-stu-id="79787-140">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="79787-141">Al restaurar un proyecto con referencias de proyecto a proyecto (P2P), se restaura el proyecto raíz y no las referencias.</span><span class="sxs-lookup"><span data-stu-id="79787-141">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="79787-142">Especifica el directorio de los paquetes restaurados.</span><span class="sxs-lookup"><span data-stu-id="79787-142">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="79787-143">Especifica un tiempo de ejecución para la restauración del paquete.</span><span class="sxs-lookup"><span data-stu-id="79787-143">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="79787-144">Se usa para restaurar los paquetes con tiempos de ejecución que no se enumeran explícitamente en la etiqueta `<RuntimeIdentifiers>` del archivo *.csproj*.</span><span class="sxs-lookup"><span data-stu-id="79787-144">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="79787-145">Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="79787-145">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="79787-146">Para proporcionar varios RID; especifique esta opción varias veces.</span><span class="sxs-lookup"><span data-stu-id="79787-146">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="79787-147">Especifica un origen de paquetes de NuGet que se usará durante la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="79787-147">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="79787-148">Esto invalida todos los orígenes especificados en los archivos *NuGet.config*.</span><span class="sxs-lookup"><span data-stu-id="79787-148">This overrides all of the sources specified in the *NuGet.config* files.</span></span> <span data-ttu-id="79787-149">Al especificar esta opción varias veces, se pueden proporcionar varios orígenes.</span><span class="sxs-lookup"><span data-stu-id="79787-149">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="79787-150">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="79787-150">Sets the verbosity level of the command.</span></span> <span data-ttu-id="79787-151">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="79787-151">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="79787-152">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="79787-152">.NET Core 1.x</span></span>](#tab/netcore1x)

`--configfile <FILE>`

<span data-ttu-id="79787-153">El archivo de configuración (*NuGet.config*) que se usa para la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="79787-153">The NuGet configuration file (*NuGet.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="79787-154">Deshabilita la restauración de varios proyectos en paralelo.</span><span class="sxs-lookup"><span data-stu-id="79787-154">Disables restoring multiple projects in parallel.</span></span>

`-h|--help`

<span data-ttu-id="79787-155">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="79787-155">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="79787-156">Solo se advierte sobre los orígenes con error si hay paquetes que satisfagan el requisito de versión.</span><span class="sxs-lookup"><span data-stu-id="79787-156">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="79787-157">Especifica que no se almacenen en caché los paquetes y las solicitudes HTTP.</span><span class="sxs-lookup"><span data-stu-id="79787-157">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="79787-158">Al restaurar un proyecto con referencias de proyecto a proyecto (P2P), se restaura el proyecto raíz y no las referencias.</span><span class="sxs-lookup"><span data-stu-id="79787-158">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="79787-159">Especifica el directorio de los paquetes restaurados.</span><span class="sxs-lookup"><span data-stu-id="79787-159">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="79787-160">Especifica un tiempo de ejecución para la restauración del paquete.</span><span class="sxs-lookup"><span data-stu-id="79787-160">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="79787-161">Se usa para restaurar los paquetes con tiempos de ejecución que no se enumeran explícitamente en la etiqueta `<RuntimeIdentifiers>` del archivo *.csproj*.</span><span class="sxs-lookup"><span data-stu-id="79787-161">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="79787-162">Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="79787-162">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="79787-163">Para proporcionar varios RID; especifique esta opción varias veces.</span><span class="sxs-lookup"><span data-stu-id="79787-163">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="79787-164">Especifica un origen de paquetes de NuGet que se usará durante la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="79787-164">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="79787-165">Esto invalida todos los orígenes especificados en los archivos *NuGet.config*.</span><span class="sxs-lookup"><span data-stu-id="79787-165">This overrides all of the sources specified in the *NuGet.config* files.</span></span> <span data-ttu-id="79787-166">Al especificar esta opción varias veces, se pueden proporcionar varios orígenes.</span><span class="sxs-lookup"><span data-stu-id="79787-166">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="79787-167">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="79787-167">Sets the verbosity level of the command.</span></span> <span data-ttu-id="79787-168">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="79787-168">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="79787-169">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="79787-169">Examples</span></span>

<span data-ttu-id="79787-170">Restauración de dependencias y herramientas para el proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="79787-170">Restore dependencies and tools for the project in the current directory:</span></span>

`dotnet restore`

<span data-ttu-id="79787-171">Restauración de dependencias y herramientas para el proyecto `app1` encontrado en la ruta de acceso dada:</span><span class="sxs-lookup"><span data-stu-id="79787-171">Restore dependencies and tools for the `app1` project found in the given path:</span></span>

`dotnet restore ~/projects/app1/app1.csproj`

<span data-ttu-id="79787-172">Restaurar las dependencias y las herramientas para el proyecto en el directorio actual con la ruta de acceso de archivo proporcionada como origen:</span><span class="sxs-lookup"><span data-stu-id="79787-172">Restore the dependencies and tools for the project in the current directory using the file path provided as the source:</span></span>

`dotnet restore -s c:\packages\mypackages`

<span data-ttu-id="79787-173">Restaurar las dependencias y las herramientas para el proyecto en el directorio actual mediante las dos rutas de acceso de archivo proporcionadas como orígenes:</span><span class="sxs-lookup"><span data-stu-id="79787-173">Restore the dependencies and tools for the project in the current directory using the two file paths provided as sources:</span></span>

`dotnet restore -s c:\packages\mypackages -s c:\packages\myotherpackages`

<span data-ttu-id="79787-174">Restaurar las dependencias y herramientas para el proyecto en el directorio actual y mostrar únicamente la salida mínima:</span><span class="sxs-lookup"><span data-stu-id="79787-174">Restore dependencies and tools for the project in the current directory and shows only minimal output:</span></span>

`dotnet restore --verbosity minimal`
