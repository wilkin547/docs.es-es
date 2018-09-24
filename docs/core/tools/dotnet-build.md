---
title: 'Comando dotnet build: CLI de .NET Core'
description: El comando dotnet build compila un proyecto y todas sus dependencias.
author: mairaw
ms.author: mairaw
ms.date: 05/25/2018
ms.openlocfilehash: da33647e583af8441218f64fb8ac76d5de3cee38
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2018
ms.locfileid: "46580114"
---
# <a name="dotnet-build"></a><span data-ttu-id="141d5-103">dotnet build</span><span class="sxs-lookup"><span data-stu-id="141d5-103">dotnet build</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="141d5-104">nombre</span><span class="sxs-lookup"><span data-stu-id="141d5-104">Name</span></span>

<span data-ttu-id="141d5-105">`dotnet build`: compila un proyecto y todas sus dependencias.</span><span class="sxs-lookup"><span data-stu-id="141d5-105">`dotnet build` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="141d5-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="141d5-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="141d5-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="141d5-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet build [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--no-dependencies] [--no-incremental]
    [--no-restore] [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]
dotnet build [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="141d5-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="141d5-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet build [<PROJECT>] [-c|--configuration] [-f|--framework] [--no-dependencies] [--no-incremental] [-o|--output]
    [-r|--runtime] [-v|--verbosity] [--version-suffix]
dotnet build [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="141d5-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="141d5-109">Description</span></span>

<span data-ttu-id="141d5-110">El comando `dotnet build` crea el proyecto y sus dependencias en un conjunto de archivos binarios.</span><span class="sxs-lookup"><span data-stu-id="141d5-110">The `dotnet build` command builds the project and its dependencies into a set of binaries.</span></span> <span data-ttu-id="141d5-111">Los archivos binarios incluyen el código del proyecto en archivos de lenguaje intermedio (IL) con una extensión *.dll* y los archivos de símbolos usados para la depuración con una extensión *.pdb*.</span><span class="sxs-lookup"><span data-stu-id="141d5-111">The binaries include the project's code in Intermediate Language (IL) files with a *.dll* extension and symbol files used for debugging with a *.pdb* extension.</span></span> <span data-ttu-id="141d5-112">Se genera un archivo JSON de dependencias (*\*. deps.json*) que incluye las dependencias de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="141d5-112">A dependencies JSON file (*\*.deps.json*) is produced that lists the dependencies of the application.</span></span> <span data-ttu-id="141d5-113">Se genera un archivo *\*.runtimeconfig.json*, que especifica el tiempo de ejecución compartido y su versión de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="141d5-113">A *\*.runtimeconfig.json* file is produced, which specifies the shared runtime and its version for the application.</span></span>

<span data-ttu-id="141d5-114">Si el proyecto tiene dependencias de terceros, como bibliotecas de NuGet, estas se resuelven desde la caché de NuGet y no están disponibles en la salida compilada del proyecto.</span><span class="sxs-lookup"><span data-stu-id="141d5-114">If the project has third-party dependencies, such as libraries from NuGet, they're resolved from the NuGet cache and aren't available with the project's built output.</span></span> <span data-ttu-id="141d5-115">Teniendo eso en cuenta, el producto de `dotnet build` no está listo para transferirse a otra máquina para ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="141d5-115">With that in mind, the product of `dotnet build` isn't ready to be transferred to another machine to run.</span></span> <span data-ttu-id="141d5-116">Esto contrasta con el comportamiento de .NET Framework en el que al compilar un proyecto ejecutable (una aplicación) se genera ese ejecutable en cualquier máquina donde esté instalado .NET.</span><span class="sxs-lookup"><span data-stu-id="141d5-116">This is in contrast to the behavior of the .NET Framework in which building an executable project (an application) produces output that's runnable on any machine where the .NET Framework is installed.</span></span> <span data-ttu-id="141d5-117">Para tener una experiencia similar con .NET Core, es necesario usar el comando [dotnet publish](dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="141d5-117">To have a similar experience with .NET Core, you need to use the [dotnet publish](dotnet-publish.md) command.</span></span> <span data-ttu-id="141d5-118">Para obtener más información, consulte el tema [Implementación de aplicaciones .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="141d5-118">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span>

<span data-ttu-id="141d5-119">La compilación requiere el archivo *project.assets.json*, que muestra las dependencias de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="141d5-119">Building requires the *project.assets.json* file, which lists the dependencies of your application.</span></span> <span data-ttu-id="141d5-120">El archivo se crea cuando se ejecuta [`dotnet restore`](dotnet-restore.md).</span><span class="sxs-lookup"><span data-stu-id="141d5-120">The file is created when [`dotnet restore`](dotnet-restore.md) is executed.</span></span> <span data-ttu-id="141d5-121">Sin el archivo de recursos, las herramientas no pueden resolver los ensamblados de referencia, lo que dará lugar a errores.</span><span class="sxs-lookup"><span data-stu-id="141d5-121">Without the assets file in place, the tooling cannot resolve reference assemblies, which results in errors.</span></span> <span data-ttu-id="141d5-122">Con el SDK de .NET Core 1.x, era necesario ejecutar de forma explícita `dotnet restore` antes de ejecutar `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="141d5-122">With .NET Core 1.x SDK, you needed to explicitly run the `dotnet restore` before running `dotnet build`.</span></span> <span data-ttu-id="141d5-123">A partir del SDK de .NET Core 2.0, `dotnet restore` se ejecuta implícitamente al ejecutar `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="141d5-123">Starting with .NET Core 2.0 SDK, `dotnet restore` runs implicitly when you run `dotnet build`.</span></span> <span data-ttu-id="141d5-124">Si quiere deshabilitar la restauración implícita cuando se ejecuta el comando de compilación, puede usar la opción `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="141d5-124">If you want to disable implicit restore when running the build command, you can pass the `--no-restore` option.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

<span data-ttu-id="141d5-125">`dotnet build` usa MSBuild para compilar el proyecto, por lo que admite las compilaciones en paralelo e incrementales.</span><span class="sxs-lookup"><span data-stu-id="141d5-125">`dotnet build` uses MSBuild to build the project, so it supports both parallel and incremental builds.</span></span> <span data-ttu-id="141d5-126">Para obtener más información, consulte [Compilaciones incrementales](/visualstudio/msbuild/incremental-builds).</span><span class="sxs-lookup"><span data-stu-id="141d5-126">For more information, see [Incremental Builds](/visualstudio/msbuild/incremental-builds).</span></span>

<span data-ttu-id="141d5-127">Además de sus opciones, el comando `dotnet build` acepta opciones de MSBuild, como `-p` para establecer propiedades o `-l` para definir un registrador.</span><span class="sxs-lookup"><span data-stu-id="141d5-127">In addition to its options, the `dotnet build` command accepts MSBuild options, such as `-p` for setting properties or `-l` to define a logger.</span></span> <span data-ttu-id="141d5-128">Para obtener más información sobre estas opciones, vea la [Referencia de la línea de comandos de MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="141d5-128">For more information about these options, see the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

<span data-ttu-id="141d5-129">Si el proyecto es ejecutable o no viene determinado por la propiedad `<OutputType>` en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="141d5-129">Whether the project is executable or not is determined by the `<OutputType>` property in the project file.</span></span> <span data-ttu-id="141d5-130">En el ejemplo siguiente se muestra un proyecto en el que se genera código ejecutable:</span><span class="sxs-lookup"><span data-stu-id="141d5-130">The following example shows a project that produces executable code:</span></span>

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="141d5-131">Para generar una biblioteca, omita la propiedad `<OutputType>`.</span><span class="sxs-lookup"><span data-stu-id="141d5-131">In order to produce a library, omit the `<OutputType>` property.</span></span> <span data-ttu-id="141d5-132">La principal diferencia en la salida compilada es que la DLL de IL para una biblioteca no contiene puntos de entrada y no se puede ejecutar.</span><span class="sxs-lookup"><span data-stu-id="141d5-132">The main difference in built output is that the IL DLL for a library doesn't contain entry points and can't be executed.</span></span>

## <a name="arguments"></a><span data-ttu-id="141d5-133">Argumentos</span><span class="sxs-lookup"><span data-stu-id="141d5-133">Arguments</span></span>

`PROJECT`

<span data-ttu-id="141d5-134">El archivo del proyecto que se va a compilar.</span><span class="sxs-lookup"><span data-stu-id="141d5-134">The project file to build.</span></span> <span data-ttu-id="141d5-135">Si no se especifica un archivo de proyecto, MSBuild busca en el directorio de trabajo actual un archivo que tenga una extensión de archivo que termine en *proj* y usa ese archivo.</span><span class="sxs-lookup"><span data-stu-id="141d5-135">If a project file is not specified, MSBuild searches the current working directory for a file that has a file extension that ends in *proj* and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="141d5-136">Opciones</span><span class="sxs-lookup"><span data-stu-id="141d5-136">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="141d5-137">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="141d5-137">.NET Core 2.x</span></span>](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="141d5-138">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="141d5-138">Defines the build configuration.</span></span> <span data-ttu-id="141d5-139">El valor predeterminado es `Debug`.</span><span class="sxs-lookup"><span data-stu-id="141d5-139">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="141d5-140">Compila para un [marco de trabajo](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="141d5-140">Compiles for a specific [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="141d5-141">El marco se debe definir en el [archivo de proyecto](csproj.md).</span><span class="sxs-lookup"><span data-stu-id="141d5-141">The framework must be defined in the [project file](csproj.md).</span></span>

`--force`

<span data-ttu-id="141d5-142">Fuerza la resolución de todas las dependencias, incluso si la última restauración se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="141d5-142">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="141d5-143">Especificar esta marca es lo mismo que eliminar el archivo *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="141d5-143">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="141d5-144">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="141d5-144">Prints out a short help for the command.</span></span>

`--no-dependencies`

<span data-ttu-id="141d5-145">Omite las referencias de proyecto a proyecto (P2P) y solo compila el proyecto raíz especificado.</span><span class="sxs-lookup"><span data-stu-id="141d5-145">Ignores project-to-project (P2P) references and only builds the specified root project.</span></span>

`--no-incremental`

<span data-ttu-id="141d5-146">Marca la compilación como no segura para la compilación incremental.</span><span class="sxs-lookup"><span data-stu-id="141d5-146">Marks the build as unsafe for incremental build.</span></span> <span data-ttu-id="141d5-147">Esta marca desactiva la compilación incremental y fuerza una recompilación limpia del gráfico de dependencias del proyecto.</span><span class="sxs-lookup"><span data-stu-id="141d5-147">This flag turns off incremental compilation and forces a clean rebuild of the project's dependency graph.</span></span>

`--no-restore`

<span data-ttu-id="141d5-148">No ejecuta una restauración implícita durante la compilación.</span><span class="sxs-lookup"><span data-stu-id="141d5-148">Doesn't execute an implicit restore during build.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="141d5-149">Directorio donde se colocan los archivos binarios compilados.</span><span class="sxs-lookup"><span data-stu-id="141d5-149">Directory in which to place the built binaries.</span></span> <span data-ttu-id="141d5-150">También debe definir `--framework` cuando se especifica esta opción.</span><span class="sxs-lookup"><span data-stu-id="141d5-150">You also need to define `--framework` when you specify this option.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="141d5-151">Especifica el tiempo de ejecución de destino.</span><span class="sxs-lookup"><span data-stu-id="141d5-151">Specifies the target runtime.</span></span> <span data-ttu-id="141d5-152">Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="141d5-152">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="141d5-153">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="141d5-153">Sets the verbosity level of the command.</span></span> <span data-ttu-id="141d5-154">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="141d5-154">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="141d5-155">Define el sufijo de la versión de un asterisco (`*`) en el campo de versión del archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="141d5-155">Defines the version suffix for an asterisk (`*`) in the version field of the project file.</span></span> <span data-ttu-id="141d5-156">El formato sigue las instrucciones de versión de NuGet.</span><span class="sxs-lookup"><span data-stu-id="141d5-156">The format follows NuGet's version guidelines.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="141d5-157">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="141d5-157">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="141d5-158">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="141d5-158">Defines the build configuration.</span></span> <span data-ttu-id="141d5-159">El valor predeterminado es `Debug`.</span><span class="sxs-lookup"><span data-stu-id="141d5-159">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="141d5-160">Compila para un [marco de trabajo](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="141d5-160">Compiles for a specific [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="141d5-161">El marco se debe definir en el [archivo de proyecto](csproj.md).</span><span class="sxs-lookup"><span data-stu-id="141d5-161">The framework must be defined in the [project file](csproj.md).</span></span>

`-h|--help`

<span data-ttu-id="141d5-162">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="141d5-162">Prints out a short help for the command.</span></span>

`--no-dependencies`

<span data-ttu-id="141d5-163">Omite las referencias de proyecto a proyecto (P2P) y solo compila el proyecto raíz especificado.</span><span class="sxs-lookup"><span data-stu-id="141d5-163">Ignores project-to-project (P2P) references and only builds the specified root project.</span></span>

`--no-incremental`

<span data-ttu-id="141d5-164">Marca la compilación como no segura para la compilación incremental.</span><span class="sxs-lookup"><span data-stu-id="141d5-164">Marks the build as unsafe for incremental build.</span></span> <span data-ttu-id="141d5-165">Esta marca desactiva la compilación incremental y fuerza una recompilación limpia del gráfico de dependencias del proyecto.</span><span class="sxs-lookup"><span data-stu-id="141d5-165">This flag turns off incremental compilation and forces a clean rebuild of the project's dependency graph.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="141d5-166">Directorio donde se colocan los archivos binarios compilados.</span><span class="sxs-lookup"><span data-stu-id="141d5-166">Directory in which to place the built binaries.</span></span> <span data-ttu-id="141d5-167">También debe definir `--framework` cuando se especifica esta opción.</span><span class="sxs-lookup"><span data-stu-id="141d5-167">You also need to define `--framework` when you specify this option.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="141d5-168">Especifica el tiempo de ejecución de destino.</span><span class="sxs-lookup"><span data-stu-id="141d5-168">Specifies the target runtime.</span></span> <span data-ttu-id="141d5-169">Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="141d5-169">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="141d5-170">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="141d5-170">Sets the verbosity level of the command.</span></span> <span data-ttu-id="141d5-171">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="141d5-171">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="141d5-172">Define el sufijo de la versión de un asterisco (`*`) en el campo de versión del archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="141d5-172">Defines the version suffix for an asterisk (`*`) in the version field of the project file.</span></span> <span data-ttu-id="141d5-173">El formato sigue las instrucciones de versión de NuGet.</span><span class="sxs-lookup"><span data-stu-id="141d5-173">The format follows NuGet's version guidelines.</span></span>

---

## <a name="examples"></a><span data-ttu-id="141d5-174">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="141d5-174">Examples</span></span>

<span data-ttu-id="141d5-175">Creación de un proyecto y sus dependencias:</span><span class="sxs-lookup"><span data-stu-id="141d5-175">Build a project and its dependencies:</span></span>

`dotnet build`

<span data-ttu-id="141d5-176">Creación de un proyecto y sus dependencias mediante la configuración de lanzamiento:</span><span class="sxs-lookup"><span data-stu-id="141d5-176">Build a project and its dependencies using Release configuration:</span></span>

`dotnet build --configuration Release`

<span data-ttu-id="141d5-177">Compilación de un proyecto y sus dependencias para un tiempo de ejecución específico (en este ejemplo, Ubuntu 16.04):</span><span class="sxs-lookup"><span data-stu-id="141d5-177">Build a project and its dependencies for a specific runtime (in this example, Ubuntu 16.04):</span></span>

`dotnet build --runtime ubuntu.16.04-x64`

<span data-ttu-id="141d5-178">Compile el proyecto y use origen del paquete NuGet especificado durante la operación de restauración (SDK de .NET Core 2.0 y versiones posteriores):</span><span class="sxs-lookup"><span data-stu-id="141d5-178">Build the project and use the specified NuGet package source during the restore operation (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet build --source c:\packages\mypackages`