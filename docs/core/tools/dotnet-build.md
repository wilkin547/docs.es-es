---
title: 'Comando dotnet build: CLI de .NET Core'
description: El comando dotnet build compila un proyecto y todas sus dependencias.
ms.date: 12/04/2018
ms.openlocfilehash: 5d47fdfca14d20b3f2a134a8e734f76b1c86c498
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53149164"
---
# <a name="dotnet-build"></a><span data-ttu-id="c3738-103">dotnet build</span><span class="sxs-lookup"><span data-stu-id="c3738-103">dotnet build</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="c3738-104">nombre</span><span class="sxs-lookup"><span data-stu-id="c3738-104">Name</span></span>

<span data-ttu-id="c3738-105">`dotnet build`: compila un proyecto y todas sus dependencias.</span><span class="sxs-lookup"><span data-stu-id="c3738-105">`dotnet build` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c3738-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="c3738-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="c3738-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="c3738-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet build [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--force] [--no-dependencies] [--no-incremental]
    [--no-restore] [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]

dotnet build [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c3738-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c3738-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet build [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--no-dependencies] [--no-incremental] [-o|--output]
    [-r|--runtime] [-v|--verbosity] [--version-suffix]

dotnet build [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="c3738-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="c3738-109">Description</span></span>

<span data-ttu-id="c3738-110">El comando `dotnet build` crea el proyecto y sus dependencias en un conjunto de archivos binarios.</span><span class="sxs-lookup"><span data-stu-id="c3738-110">The `dotnet build` command builds the project and its dependencies into a set of binaries.</span></span> <span data-ttu-id="c3738-111">Los archivos binarios incluyen el código del proyecto en archivos de lenguaje intermedio (IL) con una extensión *.dll* y los archivos de símbolos usados para la depuración con una extensión *.pdb*.</span><span class="sxs-lookup"><span data-stu-id="c3738-111">The binaries include the project's code in Intermediate Language (IL) files with a *.dll* extension and symbol files used for debugging with a *.pdb* extension.</span></span> <span data-ttu-id="c3738-112">Se genera un archivo JSON de dependencias (*\*. deps.json*) que incluye las dependencias de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c3738-112">A dependencies JSON file (*\*.deps.json*) is produced that lists the dependencies of the application.</span></span> <span data-ttu-id="c3738-113">Se genera un archivo *\*.runtimeconfig.json*, que especifica el tiempo de ejecución compartido y su versión de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c3738-113">A *\*.runtimeconfig.json* file is produced, which specifies the shared runtime and its version for the application.</span></span>

<span data-ttu-id="c3738-114">Si el proyecto tiene dependencias de terceros, como bibliotecas de NuGet, estas se resuelven desde la caché de NuGet y no están disponibles en la salida compilada del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c3738-114">If the project has third-party dependencies, such as libraries from NuGet, they're resolved from the NuGet cache and aren't available with the project's built output.</span></span> <span data-ttu-id="c3738-115">Teniendo eso en cuenta, el producto de `dotnet build` no está listo para transferirse a otra máquina para ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="c3738-115">With that in mind, the product of `dotnet build` isn't ready to be transferred to another machine to run.</span></span> <span data-ttu-id="c3738-116">Esto contrasta con el comportamiento de .NET Framework en el que al compilar un proyecto ejecutable (una aplicación) se genera ese ejecutable en cualquier máquina donde esté instalado .NET.</span><span class="sxs-lookup"><span data-stu-id="c3738-116">This is in contrast to the behavior of the .NET Framework in which building an executable project (an application) produces output that's runnable on any machine where the .NET Framework is installed.</span></span> <span data-ttu-id="c3738-117">Para tener una experiencia similar con .NET Core, es necesario usar el comando [dotnet publish](dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="c3738-117">To have a similar experience with .NET Core, you need to use the [dotnet publish](dotnet-publish.md) command.</span></span> <span data-ttu-id="c3738-118">Para obtener más información, consulte el tema [Implementación de aplicaciones .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="c3738-118">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span>

<span data-ttu-id="c3738-119">La compilación requiere el archivo *project.assets.json*, que muestra las dependencias de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c3738-119">Building requires the *project.assets.json* file, which lists the dependencies of your application.</span></span> <span data-ttu-id="c3738-120">El archivo se crea cuando se ejecuta [`dotnet restore`](dotnet-restore.md).</span><span class="sxs-lookup"><span data-stu-id="c3738-120">The file is created when [`dotnet restore`](dotnet-restore.md) is executed.</span></span> <span data-ttu-id="c3738-121">Sin el archivo de recursos, las herramientas no pueden resolver los ensamblados de referencia, lo que dará lugar a errores.</span><span class="sxs-lookup"><span data-stu-id="c3738-121">Without the assets file in place, the tooling cannot resolve reference assemblies, which results in errors.</span></span> <span data-ttu-id="c3738-122">Con el SDK de .NET Core 1.x, era necesario ejecutar de forma explícita `dotnet restore` antes de ejecutar `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="c3738-122">With .NET Core 1.x SDK, you needed to explicitly run the `dotnet restore` before running `dotnet build`.</span></span> <span data-ttu-id="c3738-123">A partir del SDK de .NET Core 2.0, `dotnet restore` se ejecuta implícitamente al ejecutar `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="c3738-123">Starting with .NET Core 2.0 SDK, `dotnet restore` runs implicitly when you run `dotnet build`.</span></span> <span data-ttu-id="c3738-124">Si quiere deshabilitar la restauración implícita cuando se ejecuta el comando de compilación, puede usar la opción `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="c3738-124">If you want to disable implicit restore when running the build command, you can pass the `--no-restore` option.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

<span data-ttu-id="c3738-125">Si el proyecto es ejecutable o no viene determinado por la propiedad `<OutputType>` en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c3738-125">Whether the project is executable or not is determined by the `<OutputType>` property in the project file.</span></span> <span data-ttu-id="c3738-126">En el ejemplo siguiente se muestra un proyecto en el que se genera código ejecutable:</span><span class="sxs-lookup"><span data-stu-id="c3738-126">The following example shows a project that produces executable code:</span></span>

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="c3738-127">Para generar una biblioteca, omita la propiedad `<OutputType>`.</span><span class="sxs-lookup"><span data-stu-id="c3738-127">In order to produce a library, omit the `<OutputType>` property.</span></span> <span data-ttu-id="c3738-128">La principal diferencia en la salida compilada es que la DLL de IL para una biblioteca no contiene puntos de entrada y no se puede ejecutar.</span><span class="sxs-lookup"><span data-stu-id="c3738-128">The main difference in built output is that the IL DLL for a library doesn't contain entry points and can't be executed.</span></span>

### <a name="msbuild"></a><span data-ttu-id="c3738-129">MSBuild</span><span class="sxs-lookup"><span data-stu-id="c3738-129">MSBuild</span></span>

<span data-ttu-id="c3738-130">`dotnet build` usa MSBuild para compilar el proyecto, por lo que admite las compilaciones en paralelo e incrementales.</span><span class="sxs-lookup"><span data-stu-id="c3738-130">`dotnet build` uses MSBuild to build the project, so it supports both parallel and incremental builds.</span></span> <span data-ttu-id="c3738-131">Para obtener más información, consulte [Compilaciones incrementales](/visualstudio/msbuild/incremental-builds).</span><span class="sxs-lookup"><span data-stu-id="c3738-131">For more information, see [Incremental Builds](/visualstudio/msbuild/incremental-builds).</span></span>

<span data-ttu-id="c3738-132">Además de sus opciones, el comando `dotnet build` acepta opciones de MSBuild, como `-p` para establecer propiedades o `-l` para definir un registrador.</span><span class="sxs-lookup"><span data-stu-id="c3738-132">In addition to its options, the `dotnet build` command accepts MSBuild options, such as `-p` for setting properties or `-l` to define a logger.</span></span> <span data-ttu-id="c3738-133">Para obtener más información sobre estas opciones, vea la [Referencia de la línea de comandos de MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="c3738-133">For more information about these options, see the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> <span data-ttu-id="c3738-134">O también puede usar el comando [dotnet msbuild](dotnet-msbuild.md).</span><span class="sxs-lookup"><span data-stu-id="c3738-134">Or you can also use the [dotnet msbuild](dotnet-msbuild.md) command.</span></span>

<span data-ttu-id="c3738-135">La ejecución de `dotnet build` es equivalente a `dotnet msbuild -restore -target:Build`.</span><span class="sxs-lookup"><span data-stu-id="c3738-135">Running `dotnet build` is equivalent to `dotnet msbuild -restore -target:Build`.</span></span>

## <a name="arguments"></a><span data-ttu-id="c3738-136">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c3738-136">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="c3738-137">El archivo de proyecto o solución para compilar.</span><span class="sxs-lookup"><span data-stu-id="c3738-137">The project or solution file to build.</span></span> <span data-ttu-id="c3738-138">Si no se especifica un archivo de proyecto o solución, MSBuild busca en el directorio de trabajo actual un archivo que tenga una extensión de archivo que termine en *proj* o *sln* y use ese archivo.</span><span class="sxs-lookup"><span data-stu-id="c3738-138">If a project or solution file is not specified, MSBuild searches the current working directory for a file that has a file extension that ends in either *proj* or *sln* and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="c3738-139">Opciones</span><span class="sxs-lookup"><span data-stu-id="c3738-139">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="c3738-140">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="c3738-140">.NET Core 2.x</span></span>](#tab/netcore2x)

* **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="c3738-141">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="c3738-141">Defines the build configuration.</span></span> <span data-ttu-id="c3738-142">El valor predeterminado es `Debug`.</span><span class="sxs-lookup"><span data-stu-id="c3738-142">The default value is `Debug`.</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c3738-143">Compila para un [marco de trabajo](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="c3738-143">Compiles for a specific [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="c3738-144">El marco se debe definir en el [archivo de proyecto](csproj.md).</span><span class="sxs-lookup"><span data-stu-id="c3738-144">The framework must be defined in the [project file](csproj.md).</span></span>

* **`--force`**

  <span data-ttu-id="c3738-145">Fuerza la resolución de todas las dependencias, incluso si la última restauración se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="c3738-145">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="c3738-146">Especificar esta marca es lo mismo que eliminar el archivo *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="c3738-146">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

* **`-h|--help`**

  <span data-ttu-id="c3738-147">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="c3738-147">Prints out a short help for the command.</span></span>

* **`--no-dependencies`**

  <span data-ttu-id="c3738-148">Omite las referencias de proyecto a proyecto (P2P) y solo compila el proyecto raíz especificado.</span><span class="sxs-lookup"><span data-stu-id="c3738-148">Ignores project-to-project (P2P) references and only builds the specified root project.</span></span>

* **`--no-incremental`**

  <span data-ttu-id="c3738-149">Marca la compilación como no segura para la compilación incremental.</span><span class="sxs-lookup"><span data-stu-id="c3738-149">Marks the build as unsafe for incremental build.</span></span> <span data-ttu-id="c3738-150">Esta marca desactiva la compilación incremental y fuerza una recompilación limpia del gráfico de dependencias del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c3738-150">This flag turns off incremental compilation and forces a clean rebuild of the project's dependency graph.</span></span>

* **`--no-restore`**

  <span data-ttu-id="c3738-151">No ejecuta una restauración implícita durante la compilación.</span><span class="sxs-lookup"><span data-stu-id="c3738-151">Doesn't execute an implicit restore during build.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="c3738-152">Directorio donde se colocan los archivos binarios compilados.</span><span class="sxs-lookup"><span data-stu-id="c3738-152">Directory in which to place the built binaries.</span></span> <span data-ttu-id="c3738-153">También debe definir `--framework` cuando se especifica esta opción.</span><span class="sxs-lookup"><span data-stu-id="c3738-153">You also need to define `--framework` when you specify this option.</span></span> <span data-ttu-id="c3738-154">Si no se especifica la ruta de acceso predeterminada es `./bin/<configuration>/<framework>/`.</span><span class="sxs-lookup"><span data-stu-id="c3738-154">If not specified, the default path is `./bin/<configuration>/<framework>/`.</span></span>

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="c3738-155">Especifica el tiempo de ejecución de destino.</span><span class="sxs-lookup"><span data-stu-id="c3738-155">Specifies the target runtime.</span></span> <span data-ttu-id="c3738-156">Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="c3738-156">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="c3738-157">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="c3738-157">Sets the verbosity level of the command.</span></span> <span data-ttu-id="c3738-158">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="c3738-158">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

* **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="c3738-159">Define el sufijo de la versión de un asterisco (`*`) en el campo de versión del archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c3738-159">Defines the version suffix for an asterisk (`*`) in the version field of the project file.</span></span> <span data-ttu-id="c3738-160">El formato sigue las instrucciones de versión de NuGet.</span><span class="sxs-lookup"><span data-stu-id="c3738-160">The format follows NuGet's version guidelines.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c3738-161">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c3738-161">.NET Core 1.x</span></span>](#tab/netcore1x)

* **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="c3738-162">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="c3738-162">Defines the build configuration.</span></span> <span data-ttu-id="c3738-163">El valor predeterminado es `Debug`.</span><span class="sxs-lookup"><span data-stu-id="c3738-163">The default value is `Debug`.</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c3738-164">Compila para un [marco de trabajo](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="c3738-164">Compiles for a specific [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="c3738-165">El marco se debe definir en el [archivo de proyecto](csproj.md).</span><span class="sxs-lookup"><span data-stu-id="c3738-165">The framework must be defined in the [project file](csproj.md).</span></span>

* **`-h|--help`**

  <span data-ttu-id="c3738-166">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="c3738-166">Prints out a short help for the command.</span></span>

* **`--no-dependencies`**

  <span data-ttu-id="c3738-167">Omite las referencias de proyecto a proyecto (P2P) y solo compila el proyecto raíz especificado.</span><span class="sxs-lookup"><span data-stu-id="c3738-167">Ignores project-to-project (P2P) references and only builds the specified root project.</span></span>

* **`--no-incremental`**

  <span data-ttu-id="c3738-168">Marca la compilación como no segura para la compilación incremental.</span><span class="sxs-lookup"><span data-stu-id="c3738-168">Marks the build as unsafe for incremental build.</span></span> <span data-ttu-id="c3738-169">Esta marca desactiva la compilación incremental y fuerza una recompilación limpia del gráfico de dependencias del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c3738-169">This flag turns off incremental compilation and forces a clean rebuild of the project's dependency graph.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="c3738-170">Directorio donde se colocan los archivos binarios compilados.</span><span class="sxs-lookup"><span data-stu-id="c3738-170">Directory in which to place the built binaries.</span></span> <span data-ttu-id="c3738-171">También debe definir `--framework` cuando se especifica esta opción.</span><span class="sxs-lookup"><span data-stu-id="c3738-171">You also need to define `--framework` when you specify this option.</span></span>

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="c3738-172">Especifica el tiempo de ejecución de destino.</span><span class="sxs-lookup"><span data-stu-id="c3738-172">Specifies the target runtime.</span></span> <span data-ttu-id="c3738-173">Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="c3738-173">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="c3738-174">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="c3738-174">Sets the verbosity level of the command.</span></span> <span data-ttu-id="c3738-175">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="c3738-175">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

* **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="c3738-176">Define el sufijo de la versión de un asterisco (`*`) en el campo de versión del archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c3738-176">Defines the version suffix for an asterisk (`*`) in the version field of the project file.</span></span> <span data-ttu-id="c3738-177">El formato sigue las instrucciones de versión de NuGet.</span><span class="sxs-lookup"><span data-stu-id="c3738-177">The format follows NuGet's version guidelines.</span></span>

---

## <a name="examples"></a><span data-ttu-id="c3738-178">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c3738-178">Examples</span></span>

* <span data-ttu-id="c3738-179">Creación de un proyecto y sus dependencias:</span><span class="sxs-lookup"><span data-stu-id="c3738-179">Build a project and its dependencies:</span></span>

  ```console
  dotnet build
  ```

* <span data-ttu-id="c3738-180">Creación de un proyecto y sus dependencias mediante la configuración de lanzamiento:</span><span class="sxs-lookup"><span data-stu-id="c3738-180">Build a project and its dependencies using Release configuration:</span></span>

  ```console
  dotnet build --configuration Release
  ```

* <span data-ttu-id="c3738-181">Compilación de un proyecto y sus dependencias para un tiempo de ejecución específico (en este ejemplo, Ubuntu 16.04):</span><span class="sxs-lookup"><span data-stu-id="c3738-181">Build a project and its dependencies for a specific runtime (in this example, Ubuntu 16.04):</span></span>

  ```console
  dotnet build --runtime ubuntu.16.04-x64
  ```

* <span data-ttu-id="c3738-182">Compile el proyecto y use origen del paquete NuGet especificado durante la operación de restauración (SDK de .NET Core 2.0 y versiones posteriores):</span><span class="sxs-lookup"><span data-stu-id="c3738-182">Build the project and use the specified NuGet package source during the restore operation (.NET Core 2.0 SDK and later versions):</span></span>

  ```console
  dotnet build --source c:\packages\mypackages
  ```

* <span data-ttu-id="c3738-183">Compile el proyecto y establezca la versión 1.2.3.4 como un parámetro de compilación:</span><span class="sxs-lookup"><span data-stu-id="c3738-183">Build the project and set 1.2.3.4 version as a build parameter:</span></span>

  ```console
  dotnet build -p:Version=1.2.3.4
  ```