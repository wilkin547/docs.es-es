---
title: Comando dotnet restore
description: Aprenda a restaurar dependencias y herramientas específicas del proyecto con el comando dotnet restore.
ms.date: 05/29/2018
ms.openlocfilehash: dc73b7b2482d25872be922e68103fb86067146f7
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920559"
---
# <a name="dotnet-restore"></a><span data-ttu-id="34d45-103">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="34d45-103">dotnet restore</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="34d45-104">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="34d45-104">Name</span></span>

<span data-ttu-id="34d45-105">`dotnet restore`: restaura las dependencias y las herramientas de un proyecto.</span><span class="sxs-lookup"><span data-stu-id="34d45-105">`dotnet restore` - Restores the dependencies and tools of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="34d45-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="34d45-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="34d45-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="34d45-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```dotnetcli
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--force] [--ignore-failed-sources] [--no-cache]
    [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity] [--interactive]
dotnet restore [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="34d45-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="34d45-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--ignore-failed-sources] [--no-cache]
    [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity]
dotnet restore [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="34d45-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="34d45-109">Description</span></span>

<span data-ttu-id="34d45-110">El comando `dotnet restore` usa NuGet para restaurar las dependencias, así como las herramientas específicas del proyecto que se especifican en el archivo project.json.</span><span class="sxs-lookup"><span data-stu-id="34d45-110">The `dotnet restore` command uses NuGet to restore dependencies as well as project-specific tools that are specified in the project file.</span></span> <span data-ttu-id="34d45-111">De forma predeterminada, la restauración de dependencias y herramientas se ejecuta en paralelo.</span><span class="sxs-lookup"><span data-stu-id="34d45-111">By default, the restoration of dependencies and tools are executed in parallel.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="34d45-112">Para restaurar las dependencias, NuGet necesita las fuentes donde se encuentran los paquetes.</span><span class="sxs-lookup"><span data-stu-id="34d45-112">To restore the dependencies, NuGet needs the feeds where the packages are located.</span></span> <span data-ttu-id="34d45-113">Las fuente se proporcionan normalmente mediante el archivo de configuración *nuget.config*.</span><span class="sxs-lookup"><span data-stu-id="34d45-113">Feeds are usually provided via the *nuget.config* configuration file.</span></span> <span data-ttu-id="34d45-114">Cuando se instala el SDK de .NET Core, se proporciona un archivo de configuración predeterminado.</span><span class="sxs-lookup"><span data-stu-id="34d45-114">A default configuration file is provided when the .NET Core SDK is installed.</span></span> <span data-ttu-id="34d45-115">Puede especificar más fuentes creando su propio archivo *nuget.config* en el directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="34d45-115">You specify additional feeds by creating your own *nuget.config* file in the project directory.</span></span> <span data-ttu-id="34d45-116">Puede invalidar las fuentes *nuget.config* con la opción `-s`.</span><span class="sxs-lookup"><span data-stu-id="34d45-116">You can override the *nuget.config* feeds with the `-s` option.</span></span>

<span data-ttu-id="34d45-117">Para las dependencias, puede especificar dónde se colocan los paquetes restaurados durante la operación de restauración mediante el argumento `--packages`.</span><span class="sxs-lookup"><span data-stu-id="34d45-117">For dependencies, you specify where the restored packages are placed during the restore operation using the `--packages` argument.</span></span> <span data-ttu-id="34d45-118">Si no se especifica, se usa la caché de paquetes NuGet predeterminada, que se encuentra en el directorio `.nuget/packages` del directorio de inicio del usuario en todos los sistemas operativos.</span><span class="sxs-lookup"><span data-stu-id="34d45-118">If not specified, the default NuGet package cache is used, which is found in the `.nuget/packages` directory in the user's home directory on all operating systems.</span></span> <span data-ttu-id="34d45-119">Por ejemplo, */home/usuario1* en Linux o *C:\Usuarios\usuario1* en Windows.</span><span class="sxs-lookup"><span data-stu-id="34d45-119">For example, */home/user1* on Linux or *C:\Users\user1* on Windows.</span></span>

<span data-ttu-id="34d45-120">Para herramientas específicas del proyecto, `dotnet restore` restaura primero el paquete en el que se empaqueta la herramienta y, a continuación, continúa con la restauración de las dependencias de la herramienta especificadas en su project.json.</span><span class="sxs-lookup"><span data-stu-id="34d45-120">For project-specific tooling, `dotnet restore` first restores the package in which the tool is packed, and then proceeds to restore the tool's dependencies as specified in its project file.</span></span>

### <a name="nugetconfig-differences"></a><span data-ttu-id="34d45-121">Diferencias de nuget.config</span><span class="sxs-lookup"><span data-stu-id="34d45-121">nuget.config differences</span></span>

<span data-ttu-id="34d45-122">El comportamiento del comando `dotnet restore` depende de las opciones de configuración del archivo *nuget.config*, si existe.</span><span class="sxs-lookup"><span data-stu-id="34d45-122">The behavior of the `dotnet restore` command is affected by the settings in the *nuget.config* file, if present.</span></span> <span data-ttu-id="34d45-123">Por ejemplo, establecer `globalPackagesFolder` en *nuget.config* coloca los paquetes NuGet restaurados en la carpeta especificada.</span><span class="sxs-lookup"><span data-stu-id="34d45-123">For example, setting the `globalPackagesFolder` in *nuget.config* places the restored NuGet packages in the specified folder.</span></span> <span data-ttu-id="34d45-124">Esta es una alternativa para especificar la opción `--packages` en el comando `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="34d45-124">This is an alternative to specifying the `--packages` option on the `dotnet restore` command.</span></span> <span data-ttu-id="34d45-125">Para más información, consulte la [referencia de nuget.config](/nuget/schema/nuget-config-file).</span><span class="sxs-lookup"><span data-stu-id="34d45-125">For more information, see the [nuget.config reference](/nuget/schema/nuget-config-file).</span></span>

<span data-ttu-id="34d45-126">Hay tres configuraciones específicas que `dotnet restore` omite:</span><span class="sxs-lookup"><span data-stu-id="34d45-126">There are three specific settings that `dotnet restore` ignores:</span></span>

- [<span data-ttu-id="34d45-127">bindingRedirects</span><span class="sxs-lookup"><span data-stu-id="34d45-127">bindingRedirects</span></span>](/nuget/schema/nuget-config-file#bindingredirects-section)

  <span data-ttu-id="34d45-128">Los redireccionamientos de enlace no funcionan con elementos de `<PackageReference>` y .NET Core solo admite elementos de `<PackageReference>` para los paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="34d45-128">Binding redirects don't work with `<PackageReference>` elements and .NET Core only supports `<PackageReference>` elements for NuGet packages.</span></span>

- [<span data-ttu-id="34d45-129">solution</span><span class="sxs-lookup"><span data-stu-id="34d45-129">solution</span></span>](/nuget/schema/nuget-config-file#solution-section)

  <span data-ttu-id="34d45-130">Esta configuración es específica para Visual Studio y no se aplica a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="34d45-130">This setting is Visual Studio specific and doesn't apply to .NET Core.</span></span> <span data-ttu-id="34d45-131">.NET Core no usa un archivo `packages.config` y, en su lugar, usa elementos de `<PackageReference>` para los paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="34d45-131">.NET Core doesn't use a `packages.config` file and instead uses `<PackageReference>` elements for NuGet packages.</span></span>

- [<span data-ttu-id="34d45-132">trustedSigners</span><span class="sxs-lookup"><span data-stu-id="34d45-132">trustedSigners</span></span>](/nuget/schema/nuget-config-file#trustedsigners-section)

  <span data-ttu-id="34d45-133">Esta configuración no es aplicable porque [NuGet ya no admite la comprobación multiplataforma](https://github.com/NuGet/Home/issues/7939) de los paquetes de confianza.</span><span class="sxs-lookup"><span data-stu-id="34d45-133">This setting isn't applicable as [NuGet doesn't yet support cross-platform verification](https://github.com/NuGet/Home/issues/7939) of trusted packages.</span></span>

## <a name="implicit-dotnet-restore"></a><span data-ttu-id="34d45-134">`dotnet restore` implícito</span><span class="sxs-lookup"><span data-stu-id="34d45-134">Implicit `dotnet restore`</span></span>

<span data-ttu-id="34d45-135">A partir de .NET Core 2.0, `dotnet restore` se ejecuta de forma implícita si es necesario al emitir los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="34d45-135">Starting with .NET Core 2.0, `dotnet restore` is run implicitly if necessary when you issue the following commands:</span></span>

- [`dotnet new`](dotnet-new.md)
- [`dotnet build`](dotnet-build.md)
- [`dotnet build-server`](dotnet-build-server.md)
- [`dotnet run`](dotnet-run.md)
- [`dotnet test`](dotnet-test.md)
- [`dotnet publish`](dotnet-publish.md)
- [`dotnet pack`](dotnet-pack.md)

<span data-ttu-id="34d45-136">En la mayoría de los casos, ya no necesita utilizar explícitamente el comando `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="34d45-136">In most cases, you no longer need to explicitly use the `dotnet restore` command.</span></span>

<span data-ttu-id="34d45-137">En ocasiones, es posible que no sea conveniente ejecutar `dotnet restore` de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="34d45-137">Sometimes, it might be inconvenient to run `dotnet restore` implicitly.</span></span> <span data-ttu-id="34d45-138">Por ejemplo, algunos sistemas automatizados, como los sistemas de compilación, deben llamar a `dotnet restore` explícitamente para controlar cuándo se produce la restauración a fin de controlar el uso de la red.</span><span class="sxs-lookup"><span data-stu-id="34d45-138">For example, some automated systems, such as build systems, need to call `dotnet restore` explicitly to control when the restore occurs so that they can control network usage.</span></span> <span data-ttu-id="34d45-139">Para evitar que `dotnet restore` se ejecute de forma implícita, se puede usar la marca `--no-restore` con cualquiera de estos comandos para deshabilitar la restauración implícita.</span><span class="sxs-lookup"><span data-stu-id="34d45-139">To prevent `dotnet restore` from running implicitly, you can use the `--no-restore` flag with any of these commands to disable implicit restore.</span></span>

## <a name="arguments"></a><span data-ttu-id="34d45-140">Argumentos</span><span class="sxs-lookup"><span data-stu-id="34d45-140">Arguments</span></span>

`ROOT`

<span data-ttu-id="34d45-141">Ruta de acceso opcional del archivo de proyecto para restaurar.</span><span class="sxs-lookup"><span data-stu-id="34d45-141">Optional path to the project file to restore.</span></span>

## <a name="options"></a><span data-ttu-id="34d45-142">Opciones</span><span class="sxs-lookup"><span data-stu-id="34d45-142">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="34d45-143">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="34d45-143">.NET Core 2.x</span></span>](#tab/netcore2x)

`--configfile <FILE>`

<span data-ttu-id="34d45-144">El archivo de configuración de NuGet (*nuget.config*) que se usa para la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="34d45-144">The NuGet configuration file (*nuget.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="34d45-145">Deshabilita la restauración de varios proyectos en paralelo.</span><span class="sxs-lookup"><span data-stu-id="34d45-145">Disables restoring multiple projects in parallel.</span></span>

`--force`

<span data-ttu-id="34d45-146">Fuerza la resolución de todas las dependencias, incluso si la última restauración se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="34d45-146">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="34d45-147">Especificar esta marca es lo mismo que eliminar el archivo *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="34d45-147">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="34d45-148">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="34d45-148">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="34d45-149">Solo se advierte sobre los orígenes con error si hay paquetes que satisfagan el requisito de versión.</span><span class="sxs-lookup"><span data-stu-id="34d45-149">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="34d45-150">Especifica que no se almacenen en caché los paquetes y las solicitudes HTTP.</span><span class="sxs-lookup"><span data-stu-id="34d45-150">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="34d45-151">Al restaurar un proyecto con referencias de proyecto a proyecto (P2P), se restaura el proyecto raíz y no las referencias.</span><span class="sxs-lookup"><span data-stu-id="34d45-151">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="34d45-152">Especifica el directorio de los paquetes restaurados.</span><span class="sxs-lookup"><span data-stu-id="34d45-152">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="34d45-153">Especifica un tiempo de ejecución para la restauración del paquete.</span><span class="sxs-lookup"><span data-stu-id="34d45-153">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="34d45-154">Se usa para restaurar los paquetes con tiempos de ejecución que no se enumeran explícitamente en la etiqueta `<RuntimeIdentifiers>` del archivo *.csproj*.</span><span class="sxs-lookup"><span data-stu-id="34d45-154">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="34d45-155">Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="34d45-155">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="34d45-156">Para proporcionar varios RID; especifique esta opción varias veces.</span><span class="sxs-lookup"><span data-stu-id="34d45-156">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="34d45-157">Especifica un origen de paquetes de NuGet que se usará durante la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="34d45-157">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="34d45-158">Este valor invalida todos los orígenes especificados en los archivos *nuget.config*.</span><span class="sxs-lookup"><span data-stu-id="34d45-158">This setting overrides all of the sources specified in the *nuget.config* files.</span></span> <span data-ttu-id="34d45-159">Al especificar esta opción varias veces, se pueden proporcionar varios orígenes.</span><span class="sxs-lookup"><span data-stu-id="34d45-159">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="34d45-160">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="34d45-160">Sets the verbosity level of the command.</span></span> <span data-ttu-id="34d45-161">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="34d45-161">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="34d45-162">El valor predeterminado es `minimal`.</span><span class="sxs-lookup"><span data-stu-id="34d45-162">Default value is `minimal`.</span></span>

`--interactive`

<span data-ttu-id="34d45-163">Permite que el comando se detenga y espere la entrada o acción del usuario (por ejemplo, completar la autenticación).</span><span class="sxs-lookup"><span data-stu-id="34d45-163">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span> <span data-ttu-id="34d45-164">Desde .NET Core 2.1.400.</span><span class="sxs-lookup"><span data-stu-id="34d45-164">Since .NET Core 2.1.400.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="34d45-165">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="34d45-165">.NET Core 1.x</span></span>](#tab/netcore1x)

`--configfile <FILE>`

<span data-ttu-id="34d45-166">El archivo de configuración de NuGet (*nuget.config*) que se usa para la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="34d45-166">The NuGet configuration file (*nuget.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="34d45-167">Deshabilita la restauración de varios proyectos en paralelo.</span><span class="sxs-lookup"><span data-stu-id="34d45-167">Disables restoring multiple projects in parallel.</span></span>

`-h|--help`

<span data-ttu-id="34d45-168">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="34d45-168">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="34d45-169">Solo se advierte sobre los orígenes con error si hay paquetes que satisfagan el requisito de versión.</span><span class="sxs-lookup"><span data-stu-id="34d45-169">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="34d45-170">Especifica que no se almacenen en caché los paquetes y las solicitudes HTTP.</span><span class="sxs-lookup"><span data-stu-id="34d45-170">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="34d45-171">Al restaurar un proyecto con referencias de proyecto a proyecto (P2P), se restaura el proyecto raíz y no las referencias.</span><span class="sxs-lookup"><span data-stu-id="34d45-171">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="34d45-172">Especifica el directorio de los paquetes restaurados.</span><span class="sxs-lookup"><span data-stu-id="34d45-172">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="34d45-173">Especifica un tiempo de ejecución para la restauración del paquete.</span><span class="sxs-lookup"><span data-stu-id="34d45-173">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="34d45-174">Se usa para restaurar los paquetes con tiempos de ejecución que no se enumeran explícitamente en la etiqueta `<RuntimeIdentifiers>` del archivo *.csproj*.</span><span class="sxs-lookup"><span data-stu-id="34d45-174">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="34d45-175">Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="34d45-175">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="34d45-176">Para proporcionar varios RID; especifique esta opción varias veces.</span><span class="sxs-lookup"><span data-stu-id="34d45-176">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="34d45-177">Especifica un origen de paquetes de NuGet que se usará durante la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="34d45-177">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="34d45-178">Esto invalida todos los orígenes especificados en los archivos *nuget.config*, al leer de forma eficaz el archivo *nuget.config* como si el elemento `<packageSource>` no estuviera allí.</span><span class="sxs-lookup"><span data-stu-id="34d45-178">This overrides all of the sources specified in the *nuget.config* files, effectively reading the *nuget.config* file as if the `<packageSource>` element was not there.</span></span> <span data-ttu-id="34d45-179">Al especificar esta opción varias veces, se pueden proporcionar varios orígenes.</span><span class="sxs-lookup"><span data-stu-id="34d45-179">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="34d45-180">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="34d45-180">Sets the verbosity level of the command.</span></span> <span data-ttu-id="34d45-181">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="34d45-181">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="34d45-182">De manera predeterminada, es `minimal`.</span><span class="sxs-lookup"><span data-stu-id="34d45-182">The default is `minimal`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="34d45-183">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="34d45-183">Examples</span></span>

<span data-ttu-id="34d45-184">Restauración de dependencias y herramientas para el proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="34d45-184">Restore dependencies and tools for the project in the current directory:</span></span>

`dotnet restore`

<span data-ttu-id="34d45-185">Restauración de dependencias y herramientas para el proyecto `app1` encontrado en la ruta de acceso dada:</span><span class="sxs-lookup"><span data-stu-id="34d45-185">Restore dependencies and tools for the `app1` project found in the given path:</span></span>

`dotnet restore ~/projects/app1/app1.csproj`

<span data-ttu-id="34d45-186">Restaurar las dependencias y las herramientas para el proyecto en el directorio actual con la ruta de acceso de archivo proporcionada como origen:</span><span class="sxs-lookup"><span data-stu-id="34d45-186">Restore the dependencies and tools for the project in the current directory using the file path provided as the source:</span></span>

`dotnet restore -s c:\packages\mypackages`

<span data-ttu-id="34d45-187">Restaurar las dependencias y las herramientas para el proyecto en el directorio actual mediante las dos rutas de acceso de archivo proporcionadas como orígenes:</span><span class="sxs-lookup"><span data-stu-id="34d45-187">Restore the dependencies and tools for the project in the current directory using the two file paths provided as sources:</span></span>

`dotnet restore -s c:\packages\mypackages -s c:\packages\myotherpackages`

<span data-ttu-id="34d45-188">Restauración de dependencias y herramientas para el proyecto en el directorio actual que muestra una salida detallada:</span><span class="sxs-lookup"><span data-stu-id="34d45-188">Restore dependencies and tools for the project in the current directory showing detailed output:</span></span>

`dotnet restore --verbosity detailed`
