---
title: Comando dotnet restore
description: Aprenda a restaurar dependencias y herramientas específicas del proyecto con el comando dotnet restore.
ms.date: 05/29/2018
ms.openlocfilehash: 3ddb9f679cfcab972483a4cb53ffe2b075867614
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2019
ms.locfileid: "59613975"
---
# <a name="dotnet-restore"></a><span data-ttu-id="dfbc9-103">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="dfbc9-103">dotnet restore</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="dfbc9-104">nombre</span><span class="sxs-lookup"><span data-stu-id="dfbc9-104">Name</span></span>

<span data-ttu-id="dfbc9-105">`dotnet restore`: restaura las dependencias y las herramientas de un proyecto.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-105">`dotnet restore` - Restores the dependencies and tools of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="dfbc9-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="dfbc9-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="dfbc9-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="dfbc9-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--force] [--ignore-failed-sources] [--no-cache]
    [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity] [--interactive]
dotnet restore [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="dfbc9-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="dfbc9-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--ignore-failed-sources] [--no-cache]
    [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity]
dotnet restore [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="dfbc9-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="dfbc9-109">Description</span></span>

<span data-ttu-id="dfbc9-110">El comando `dotnet restore` usa NuGet para restaurar las dependencias, así como las herramientas específicas del proyecto que se especifican en el archivo project.json.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-110">The `dotnet restore` command uses NuGet to restore dependencies as well as project-specific tools that are specified in the project file.</span></span> <span data-ttu-id="dfbc9-111">De forma predeterminada, la restauración de dependencias y herramientas se ejecuta en paralelo.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-111">By default, the restoration of dependencies and tools are executed in parallel.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="dfbc9-112">Para restaurar las dependencias, NuGet necesita las fuentes donde se encuentran los paquetes.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-112">To restore the dependencies, NuGet needs the feeds where the packages are located.</span></span> <span data-ttu-id="dfbc9-113">Las fuente se proporcionan normalmente mediante el archivo de configuración *NuGet.config*.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-113">Feeds are usually provided via the *NuGet.config* configuration file.</span></span> <span data-ttu-id="dfbc9-114">Cuando se instalan las herramientas de la CLI, se proporciona un archivo de configuración predeterminado.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-114">A default configuration file is provided when the CLI tools are installed.</span></span> <span data-ttu-id="dfbc9-115">Puede especificar más fuentes creando su propio archivo *NuGet.config* en el directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-115">You specify additional feeds by creating your own *NuGet.config* file in the project directory.</span></span> <span data-ttu-id="dfbc9-116">También puede especificar fuentes adicionales por invocación en un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-116">You also specify additional feeds per invocation at a command prompt.</span></span>

<span data-ttu-id="dfbc9-117">Para las dependencias, puede especificar dónde se colocan los paquetes restaurados durante la operación de restauración mediante el argumento `--packages`.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-117">For dependencies, you specify where the restored packages are placed during the restore operation using the `--packages` argument.</span></span> <span data-ttu-id="dfbc9-118">Si no se especifica, se usa la caché de paquetes NuGet predeterminada, que se encuentra en el directorio `.nuget/packages` del directorio de inicio del usuario en todos los sistemas operativos.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-118">If not specified, the default NuGet package cache is used, which is found in the `.nuget/packages` directory in the user's home directory on all operating systems.</span></span> <span data-ttu-id="dfbc9-119">Por ejemplo, */home/usuario1* en Linux o *C:\Usuarios\usuario1* en Windows.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-119">For example, */home/user1* on Linux or *C:\Users\user1* on Windows.</span></span>

<span data-ttu-id="dfbc9-120">Para herramientas específicas del proyecto, `dotnet restore` restaura primero el paquete en el que se empaqueta la herramienta y, a continuación, continúa con la restauración de las dependencias de la herramienta especificadas en su project.json.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-120">For project-specific tooling, `dotnet restore` first restores the package in which the tool is packed, and then proceeds to restore the tool's dependencies as specified in its project file.</span></span>

<span data-ttu-id="dfbc9-121">El comportamiento del comando `dotnet restore` depende de algunas de las opciones de configuración del archivo *Nuget.Config*, si están presentes.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-121">The behavior of the `dotnet restore` command is affected by some of the settings in the *Nuget.Config* file, if present.</span></span> <span data-ttu-id="dfbc9-122">Por ejemplo, establecer `globalPackagesFolder` en *NuGet.Config* coloca los paquetes NuGet restaurados en la carpeta especificada.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-122">For example, setting the `globalPackagesFolder` in *NuGet.Config* places the restored NuGet packages in the specified folder.</span></span> <span data-ttu-id="dfbc9-123">Esta es una alternativa para especificar la opción `--packages` en el comando `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-123">This is an alternative to specifying the `--packages` option on the `dotnet restore` command.</span></span> <span data-ttu-id="dfbc9-124">Para obtener más información, vea la [referencia de NuGet.Config](/nuget/schema/nuget-config-file).</span><span class="sxs-lookup"><span data-stu-id="dfbc9-124">For more information, see the [NuGet.Config reference](/nuget/schema/nuget-config-file).</span></span>

## <a name="implicit-dotnet-restore"></a><span data-ttu-id="dfbc9-125">`dotnet restore` implícito</span><span class="sxs-lookup"><span data-stu-id="dfbc9-125">Implicit `dotnet restore`</span></span>

<span data-ttu-id="dfbc9-126">A partir de .NET Core 2.0, `dotnet restore` se ejecuta de forma implícita si es necesario al emitir los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="dfbc9-126">Starting with .NET Core 2.0, `dotnet restore` is run implicitly if necessary when you issue the following commands:</span></span>

- [`dotnet new`](dotnet-new.md)
- [`dotnet build`](dotnet-build.md)
- [`dotnet build-server`](dotnet-build-server.md)
- [`dotnet run`](dotnet-run.md)
- [`dotnet test`](dotnet-test.md)
- [`dotnet publish`](dotnet-publish.md)
- [`dotnet pack`](dotnet-pack.md)

<span data-ttu-id="dfbc9-127">En la mayoría de los casos, ya no necesita utilizar explícitamente el comando `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-127">In most cases, you no longer need to explicitly use the `dotnet restore` command.</span></span>

<span data-ttu-id="dfbc9-128">En ocasiones, es posible que no sea conveniente ejecutar `dotnet restore` de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-128">Sometimes, it might be inconvenient to run `dotnet restore` implicitly.</span></span> <span data-ttu-id="dfbc9-129">Por ejemplo, algunos sistemas automatizados, como los sistemas de compilación, deben llamar a `dotnet restore` explícitamente para controlar cuándo se produce la restauración a fin de controlar el uso de la red.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-129">For example, some automated systems, such as build systems, need to call `dotnet restore` explicitly to control when the restore occurs so that they can control network usage.</span></span> <span data-ttu-id="dfbc9-130">Para evitar que `dotnet restore` se ejecute de forma implícita, se puede usar la marca `--no-restore` con cualquiera de estos comandos para deshabilitar la restauración implícita.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-130">To prevent `dotnet restore` from running implicitly, you can use the `--no-restore` flag with any of these commands to disable implicit restore.</span></span>

## <a name="arguments"></a><span data-ttu-id="dfbc9-131">Argumentos</span><span class="sxs-lookup"><span data-stu-id="dfbc9-131">Arguments</span></span>

`ROOT`

<span data-ttu-id="dfbc9-132">Ruta de acceso opcional del archivo de proyecto para restaurar.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-132">Optional path to the project file to restore.</span></span>

## <a name="options"></a><span data-ttu-id="dfbc9-133">Opciones</span><span class="sxs-lookup"><span data-stu-id="dfbc9-133">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="dfbc9-134">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="dfbc9-134">.NET Core 2.x</span></span>](#tab/netcore2x)

`--configfile <FILE>`

<span data-ttu-id="dfbc9-135">El archivo de configuración (*NuGet.config*) que se usa para la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-135">The NuGet configuration file (*NuGet.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="dfbc9-136">Deshabilita la restauración de varios proyectos en paralelo.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-136">Disables restoring multiple projects in parallel.</span></span>

`--force`

<span data-ttu-id="dfbc9-137">Fuerza la resolución de todas las dependencias, incluso si la última restauración se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-137">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="dfbc9-138">Especificar esta marca es lo mismo que eliminar el archivo *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-138">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="dfbc9-139">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-139">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="dfbc9-140">Solo se advierte sobre los orígenes con error si hay paquetes que satisfagan el requisito de versión.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-140">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="dfbc9-141">Especifica que no se almacenen en caché los paquetes y las solicitudes HTTP.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-141">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="dfbc9-142">Al restaurar un proyecto con referencias de proyecto a proyecto (P2P), se restaura el proyecto raíz y no las referencias.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-142">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="dfbc9-143">Especifica el directorio de los paquetes restaurados.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-143">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="dfbc9-144">Especifica un tiempo de ejecución para la restauración del paquete.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-144">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="dfbc9-145">Se usa para restaurar los paquetes con tiempos de ejecución que no se enumeran explícitamente en la etiqueta `<RuntimeIdentifiers>` del archivo *.csproj*.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-145">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="dfbc9-146">Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="dfbc9-146">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="dfbc9-147">Para proporcionar varios RID; especifique esta opción varias veces.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-147">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="dfbc9-148">Especifica un origen de paquetes de NuGet que se usará durante la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-148">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="dfbc9-149">Este valor invalida todos los orígenes especificados en los archivos *NuGet.config*.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-149">This setting overrides all of the sources specified in the *NuGet.config* files.</span></span> <span data-ttu-id="dfbc9-150">Al especificar esta opción varias veces, se pueden proporcionar varios orígenes.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-150">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="dfbc9-151">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-151">Sets the verbosity level of the command.</span></span> <span data-ttu-id="dfbc9-152">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-152">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--interactive`

<span data-ttu-id="dfbc9-153">Permite que el comando se detenga y espere la entrada o acción del usuario (por ejemplo, completar la autenticación).</span><span class="sxs-lookup"><span data-stu-id="dfbc9-153">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span> <span data-ttu-id="dfbc9-154">Desde .NET Core 2.1.400.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-154">Since .NET Core 2.1.400.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="dfbc9-155">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="dfbc9-155">.NET Core 1.x</span></span>](#tab/netcore1x)

`--configfile <FILE>`

<span data-ttu-id="dfbc9-156">El archivo de configuración (*NuGet.config*) que se usa para la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-156">The NuGet configuration file (*NuGet.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="dfbc9-157">Deshabilita la restauración de varios proyectos en paralelo.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-157">Disables restoring multiple projects in parallel.</span></span>

`-h|--help`

<span data-ttu-id="dfbc9-158">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-158">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="dfbc9-159">Solo se advierte sobre los orígenes con error si hay paquetes que satisfagan el requisito de versión.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-159">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="dfbc9-160">Especifica que no se almacenen en caché los paquetes y las solicitudes HTTP.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-160">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="dfbc9-161">Al restaurar un proyecto con referencias de proyecto a proyecto (P2P), se restaura el proyecto raíz y no las referencias.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-161">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="dfbc9-162">Especifica el directorio de los paquetes restaurados.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-162">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="dfbc9-163">Especifica un tiempo de ejecución para la restauración del paquete.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-163">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="dfbc9-164">Se usa para restaurar los paquetes con tiempos de ejecución que no se enumeran explícitamente en la etiqueta `<RuntimeIdentifiers>` del archivo *.csproj*.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-164">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="dfbc9-165">Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="dfbc9-165">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="dfbc9-166">Para proporcionar varios RID; especifique esta opción varias veces.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-166">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="dfbc9-167">Especifica un origen de paquetes de NuGet que se usará durante la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-167">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="dfbc9-168">Esto invalida todos los orígenes especificados en los archivos *NuGet.config*.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-168">This overrides all of the sources specified in the *NuGet.config* files.</span></span> <span data-ttu-id="dfbc9-169">Al especificar esta opción varias veces, se pueden proporcionar varios orígenes.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-169">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="dfbc9-170">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-170">Sets the verbosity level of the command.</span></span> <span data-ttu-id="dfbc9-171">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="dfbc9-171">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="dfbc9-172">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="dfbc9-172">Examples</span></span>

<span data-ttu-id="dfbc9-173">Restauración de dependencias y herramientas para el proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="dfbc9-173">Restore dependencies and tools for the project in the current directory:</span></span>

`dotnet restore`

<span data-ttu-id="dfbc9-174">Restauración de dependencias y herramientas para el proyecto `app1` encontrado en la ruta de acceso dada:</span><span class="sxs-lookup"><span data-stu-id="dfbc9-174">Restore dependencies and tools for the `app1` project found in the given path:</span></span>

`dotnet restore ~/projects/app1/app1.csproj`

<span data-ttu-id="dfbc9-175">Restaurar las dependencias y las herramientas para el proyecto en el directorio actual con la ruta de acceso de archivo proporcionada como origen:</span><span class="sxs-lookup"><span data-stu-id="dfbc9-175">Restore the dependencies and tools for the project in the current directory using the file path provided as the source:</span></span>

`dotnet restore -s c:\packages\mypackages`

<span data-ttu-id="dfbc9-176">Restaurar las dependencias y las herramientas para el proyecto en el directorio actual mediante las dos rutas de acceso de archivo proporcionadas como orígenes:</span><span class="sxs-lookup"><span data-stu-id="dfbc9-176">Restore the dependencies and tools for the project in the current directory using the two file paths provided as sources:</span></span>

`dotnet restore -s c:\packages\mypackages -s c:\packages\myotherpackages`

<span data-ttu-id="dfbc9-177">Restaurar las dependencias y herramientas para el proyecto en el directorio actual y mostrar únicamente la salida mínima:</span><span class="sxs-lookup"><span data-stu-id="dfbc9-177">Restore dependencies and tools for the project in the current directory and shows only minimal output:</span></span>

`dotnet restore --verbosity minimal`
