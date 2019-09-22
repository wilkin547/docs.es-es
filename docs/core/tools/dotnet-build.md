---
title: Comando dotnet build
description: El comando dotnet build compila un proyecto y todas sus dependencias.
ms.date: 08/08/2019
ms.openlocfilehash: 0b353d60691fb4bb85536c68dc4ab248f45c3a76
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117755"
---
# <a name="dotnet-build"></a><span data-ttu-id="61b77-103">dotnet build</span><span class="sxs-lookup"><span data-stu-id="61b77-103">dotnet build</span></span>

<span data-ttu-id="61b77-104">**Este artículo se aplica a: ✓** SDK de .NET Core 1.x y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="61b77-104">**This article applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="61b77-105">Name</span><span class="sxs-lookup"><span data-stu-id="61b77-105">Name</span></span>

<span data-ttu-id="61b77-106">`dotnet build`: compila un proyecto y todas sus dependencias.</span><span class="sxs-lookup"><span data-stu-id="61b77-106">`dotnet build` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="61b77-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="61b77-107">Synopsis</span></span>

```dotnetcli
dotnet build [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--force] [--interactive] [--no-dependencies]
    [--no-incremental] [--no-restore] [--nologo] [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]

dotnet build [-h|--help]
```

## <a name="description"></a><span data-ttu-id="61b77-108">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="61b77-108">Description</span></span>

<span data-ttu-id="61b77-109">El comando `dotnet build` crea el proyecto y sus dependencias en un conjunto de archivos binarios.</span><span class="sxs-lookup"><span data-stu-id="61b77-109">The `dotnet build` command builds the project and its dependencies into a set of binaries.</span></span> <span data-ttu-id="61b77-110">Los archivos binarios incluyen el código del proyecto en archivos de lenguaje intermedio (IL) con una extensión *.dll* y los archivos de símbolos usados para la depuración con una extensión *.pdb*.</span><span class="sxs-lookup"><span data-stu-id="61b77-110">The binaries include the project's code in Intermediate Language (IL) files with a *.dll* extension and symbol files used for debugging with a *.pdb* extension.</span></span> <span data-ttu-id="61b77-111">Se genera un archivo JSON de dependencias ( *.deps.json*) que incluye las dependencias de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="61b77-111">A dependencies JSON file (*.deps.json*) is produced that lists the dependencies of the application.</span></span> <span data-ttu-id="61b77-112">Se genera un archivo *.runtimeconfig.json*, que especifica el tiempo de ejecución compartido y su versión de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="61b77-112">A *.runtimeconfig.json* file is produced, which specifies the shared runtime and its version for the application.</span></span>

<span data-ttu-id="61b77-113">Si el proyecto tiene dependencias de terceros, como bibliotecas de NuGet, estas se resuelven desde la caché de NuGet y no están disponibles en la salida compilada del proyecto.</span><span class="sxs-lookup"><span data-stu-id="61b77-113">If the project has third-party dependencies, such as libraries from NuGet, they're resolved from the NuGet cache and aren't available with the project's built output.</span></span> <span data-ttu-id="61b77-114">Teniendo eso en cuenta, el producto de `dotnet build` no está listo para transferirse a otra máquina para ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="61b77-114">With that in mind, the product of `dotnet build` isn't ready to be transferred to another machine to run.</span></span> <span data-ttu-id="61b77-115">Esto contrasta con el comportamiento de .NET Framework en el que al compilar un proyecto ejecutable (una aplicación) se genera ese ejecutable en cualquier máquina donde esté instalado .NET.</span><span class="sxs-lookup"><span data-stu-id="61b77-115">This is in contrast to the behavior of the .NET Framework in which building an executable project (an application) produces output that's runnable on any machine where the .NET Framework is installed.</span></span> <span data-ttu-id="61b77-116">Para tener una experiencia similar con .NET Core, es necesario usar el comando [dotnet publish](dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="61b77-116">To have a similar experience with .NET Core, you need to use the [dotnet publish](dotnet-publish.md) command.</span></span> <span data-ttu-id="61b77-117">Para obtener más información, consulte el tema [Implementación de aplicaciones .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="61b77-117">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span>

<span data-ttu-id="61b77-118">La compilación requiere el archivo *project.assets.json*, que muestra las dependencias de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="61b77-118">Building requires the *project.assets.json* file, which lists the dependencies of your application.</span></span> <span data-ttu-id="61b77-119">El archivo se crea cuando se ejecuta [`dotnet restore`](dotnet-restore.md).</span><span class="sxs-lookup"><span data-stu-id="61b77-119">The file is created when [`dotnet restore`](dotnet-restore.md) is executed.</span></span> <span data-ttu-id="61b77-120">Sin el archivo de recursos en su lugar, las herramientas no pueden resolver los ensamblados de referencia, lo que se traduce en errores.</span><span class="sxs-lookup"><span data-stu-id="61b77-120">Without the assets file in place, the tooling can't resolve reference assemblies, which results in errors.</span></span> <span data-ttu-id="61b77-121">Con el SDK de .NET Core 1.x, era necesario ejecutar de forma explícita `dotnet restore` antes de ejecutar `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="61b77-121">With .NET Core 1.x SDK, you needed to explicitly run the `dotnet restore` before running `dotnet build`.</span></span> <span data-ttu-id="61b77-122">A partir del SDK de .NET Core 2.0, `dotnet restore` se ejecuta implícitamente al ejecutar `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="61b77-122">Starting with .NET Core 2.0 SDK, `dotnet restore` runs implicitly when you run `dotnet build`.</span></span> <span data-ttu-id="61b77-123">Si quiere deshabilitar la restauración implícita cuando se ejecuta el comando de compilación, puede usar la opción `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="61b77-123">If you want to disable implicit restore when running the build command, you can pass the `--no-restore` option.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

<span data-ttu-id="61b77-124">Si el proyecto es ejecutable o no viene determinado por la propiedad `<OutputType>` en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="61b77-124">Whether the project is executable or not is determined by the `<OutputType>` property in the project file.</span></span> <span data-ttu-id="61b77-125">En el ejemplo siguiente se muestra un proyecto en el que se genera código ejecutable:</span><span class="sxs-lookup"><span data-stu-id="61b77-125">The following example shows a project that produces executable code:</span></span>

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="61b77-126">Para generar una biblioteca, omita la propiedad `<OutputType>`.</span><span class="sxs-lookup"><span data-stu-id="61b77-126">To produce a library, omit the `<OutputType>` property.</span></span> <span data-ttu-id="61b77-127">La principal diferencia en la salida compilada es que la DLL de IL para una biblioteca no contiene puntos de entrada y no se puede ejecutar.</span><span class="sxs-lookup"><span data-stu-id="61b77-127">The main difference in built output is that the IL DLL for a library doesn't contain entry points and can't be executed.</span></span>

### <a name="msbuild"></a><span data-ttu-id="61b77-128">MSBuild</span><span class="sxs-lookup"><span data-stu-id="61b77-128">MSBuild</span></span>

<span data-ttu-id="61b77-129">`dotnet build` usa MSBuild para compilar el proyecto, por lo que admite las compilaciones en paralelo e incrementales.</span><span class="sxs-lookup"><span data-stu-id="61b77-129">`dotnet build` uses MSBuild to build the project, so it supports both parallel and incremental builds.</span></span> <span data-ttu-id="61b77-130">Para obtener más información, consulte [Compilaciones incrementales](/visualstudio/msbuild/incremental-builds).</span><span class="sxs-lookup"><span data-stu-id="61b77-130">For more information, see [Incremental Builds](/visualstudio/msbuild/incremental-builds).</span></span>

<span data-ttu-id="61b77-131">Además de sus opciones, el comando `dotnet build` acepta opciones de MSBuild, como `-p` para establecer propiedades o `-l` para definir un registrador.</span><span class="sxs-lookup"><span data-stu-id="61b77-131">In addition to its options, the `dotnet build` command accepts MSBuild options, such as `-p` for setting properties or `-l` to define a logger.</span></span> <span data-ttu-id="61b77-132">Para obtener más información sobre estas opciones, vea la [Referencia de la línea de comandos de MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="61b77-132">For more information about these options, see the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> <span data-ttu-id="61b77-133">O también puede usar el comando [dotnet msbuild](dotnet-msbuild.md).</span><span class="sxs-lookup"><span data-stu-id="61b77-133">Or you can also use the [dotnet msbuild](dotnet-msbuild.md) command.</span></span>

<span data-ttu-id="61b77-134">La ejecución de `dotnet build` es equivalente a `dotnet msbuild -restore -target:Build`.</span><span class="sxs-lookup"><span data-stu-id="61b77-134">Running `dotnet build` is equivalent to `dotnet msbuild -restore -target:Build`.</span></span>

## <a name="arguments"></a><span data-ttu-id="61b77-135">Argumentos</span><span class="sxs-lookup"><span data-stu-id="61b77-135">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="61b77-136">El archivo de proyecto o solución para compilar.</span><span class="sxs-lookup"><span data-stu-id="61b77-136">The project or solution file to build.</span></span> <span data-ttu-id="61b77-137">Si no se especifica un archivo de proyecto o solución, MSBuild busca en el directorio de trabajo actual un archivo que tiene una extensión de archivo que termina por *proj* o *sln* y usa ese archivo.</span><span class="sxs-lookup"><span data-stu-id="61b77-137">If a project or solution file isn't specified, MSBuild searches the current working directory for a file that has a file extension that ends in either *proj* or *sln* and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="61b77-138">Opciones</span><span class="sxs-lookup"><span data-stu-id="61b77-138">Options</span></span>

* **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="61b77-139">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="61b77-139">Defines the build configuration.</span></span> <span data-ttu-id="61b77-140">El valor predeterminado es `Debug`.</span><span class="sxs-lookup"><span data-stu-id="61b77-140">The default value is `Debug`.</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="61b77-141">Compila para un [marco de trabajo](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="61b77-141">Compiles for a specific [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="61b77-142">El marco se debe definir en el [archivo de proyecto](csproj.md).</span><span class="sxs-lookup"><span data-stu-id="61b77-142">The framework must be defined in the [project file](csproj.md).</span></span>

* **`--force`**

  <span data-ttu-id="61b77-143">Fuerza la resolución de todas las dependencias, incluso si la última restauración se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="61b77-143">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="61b77-144">Especificar esta marca es lo mismo que eliminar el archivo *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="61b77-144">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span> <span data-ttu-id="61b77-145">Disponible a partir del SDK de .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="61b77-145">Available since .NET Core 2.0 SDK.</span></span>

* **`-h|--help`**

  <span data-ttu-id="61b77-146">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="61b77-146">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="61b77-147">Permite que el comando se detenga y espere una entrada o una acción del usuario.</span><span class="sxs-lookup"><span data-stu-id="61b77-147">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="61b77-148">Por ejemplo, para completar la autenticación.</span><span class="sxs-lookup"><span data-stu-id="61b77-148">For example, to complete authentication.</span></span> <span data-ttu-id="61b77-149">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="61b77-149">Available since .NET Core 3.0 SDK.</span></span>

* **`--no-dependencies`**

  <span data-ttu-id="61b77-150">Omite las referencias de proyecto a proyecto (P2P) y solo compila el proyecto raíz especificado.</span><span class="sxs-lookup"><span data-stu-id="61b77-150">Ignores project-to-project (P2P) references and only builds the specified root project.</span></span>

* **`--no-incremental`**

  <span data-ttu-id="61b77-151">Marca la compilación como no segura para la compilación incremental.</span><span class="sxs-lookup"><span data-stu-id="61b77-151">Marks the build as unsafe for incremental build.</span></span> <span data-ttu-id="61b77-152">Esta marca desactiva la compilación incremental y fuerza una recompilación limpia del gráfico de dependencias del proyecto.</span><span class="sxs-lookup"><span data-stu-id="61b77-152">This flag turns off incremental compilation and forces a clean rebuild of the project's dependency graph.</span></span>

* **`--no-restore`**

  <span data-ttu-id="61b77-153">No ejecuta una restauración implícita durante la compilación.</span><span class="sxs-lookup"><span data-stu-id="61b77-153">Doesn't execute an implicit restore during build.</span></span> <span data-ttu-id="61b77-154">Disponible a partir del SDK de .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="61b77-154">Available since .NET Core 2.0 SDK.</span></span>

* **`--nologo`**

  <span data-ttu-id="61b77-155">No se muestra la pancarta de inicio ni el mensaje de copyright.</span><span class="sxs-lookup"><span data-stu-id="61b77-155">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="61b77-156">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="61b77-156">Available since .NET Core 3.0 SDK.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="61b77-157">Directorio donde se colocan los archivos binarios compilados.</span><span class="sxs-lookup"><span data-stu-id="61b77-157">Directory in which to place the built binaries.</span></span> <span data-ttu-id="61b77-158">También debe definir `--framework` cuando se especifica esta opción.</span><span class="sxs-lookup"><span data-stu-id="61b77-158">You also need to define `--framework` when you specify this option.</span></span> <span data-ttu-id="61b77-159">Si no se especifica la ruta de acceso predeterminada es `./bin/<configuration>/<framework>/`.</span><span class="sxs-lookup"><span data-stu-id="61b77-159">If not specified, the default path is `./bin/<configuration>/<framework>/`.</span></span>

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="61b77-160">Especifica el tiempo de ejecución de destino.</span><span class="sxs-lookup"><span data-stu-id="61b77-160">Specifies the target runtime.</span></span> <span data-ttu-id="61b77-161">Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="61b77-161">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="61b77-162">Establece el nivel de detalle de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="61b77-162">Sets the MSBuild verbosity level.</span></span> <span data-ttu-id="61b77-163">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="61b77-163">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="61b77-164">De manera predeterminada, es `minimal`.</span><span class="sxs-lookup"><span data-stu-id="61b77-164">The default is `minimal`.</span></span>

* **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="61b77-165">Establece el valor de la propiedad `$(VersionSuffix)` que se va a usar al compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="61b77-165">Sets the value of the `$(VersionSuffix)` property to use when building the project.</span></span> <span data-ttu-id="61b77-166">Solo funciona si no se establece la propiedad `$(Version)`.</span><span class="sxs-lookup"><span data-stu-id="61b77-166">This only works if the `$(Version)` property isn't set.</span></span> <span data-ttu-id="61b77-167">A continuación, `$(Version)` se establece en `$(VersionPrefix)` combinada con `$(VersionSuffix)`, separadas por un guion.</span><span class="sxs-lookup"><span data-stu-id="61b77-167">Then, `$(Version)` is set to the `$(VersionPrefix)` combined with the `$(VersionSuffix)`, separated by a dash.</span></span>

## <a name="examples"></a><span data-ttu-id="61b77-168">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="61b77-168">Examples</span></span>

* <span data-ttu-id="61b77-169">Creación de un proyecto y sus dependencias:</span><span class="sxs-lookup"><span data-stu-id="61b77-169">Build a project and its dependencies:</span></span>

  ```dotnetcli
  dotnet build
  ```

* <span data-ttu-id="61b77-170">Creación de un proyecto y sus dependencias mediante la configuración de lanzamiento:</span><span class="sxs-lookup"><span data-stu-id="61b77-170">Build a project and its dependencies using Release configuration:</span></span>

  ```dotnetcli
  dotnet build --configuration Release
  ```

* <span data-ttu-id="61b77-171">Compilación de un proyecto y sus dependencias para un tiempo de ejecución concreto (en este ejemplo, Ubuntu 18.04):</span><span class="sxs-lookup"><span data-stu-id="61b77-171">Build a project and its dependencies for a specific runtime (in this example, Ubuntu 18.04):</span></span>

  ```dotnetcli
  dotnet build --runtime ubuntu.18.04-x64
  ```

* <span data-ttu-id="61b77-172">Compile el proyecto y use origen del paquete NuGet especificado durante la operación de restauración (SDK de .NET Core 2.0 y versiones posteriores):</span><span class="sxs-lookup"><span data-stu-id="61b77-172">Build the project and use the specified NuGet package source during the restore operation (.NET Core 2.0 SDK and later versions):</span></span>

  ```dotnetcli
  dotnet build --source c:\packages\mypackages
  ```

* <span data-ttu-id="61b77-173">Compile el proyecto y establezca la versión 1.2.3.4 como un parámetro de compilación mediante la `-p`opción [ de MSBuild](#msbuild):</span><span class="sxs-lookup"><span data-stu-id="61b77-173">Build the project and set version 1.2.3.4 as a build parameter using the `-p` [MSBuild option](#msbuild):</span></span>

  ```dotnetcli
  dotnet build -p:Version=1.2.3.4
  ```
