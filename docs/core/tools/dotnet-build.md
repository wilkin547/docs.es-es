---
title: Comando dotnet build
description: El comando dotnet build compila un proyecto y todas sus dependencias.
ms.date: 02/14/2020
ms.openlocfilehash: 6f33b449301f40949ff5dfe4077564344a9de8ec
ms.sourcegitcommit: c8c3e1c63a00b7d27f76f5e50ee6469e6bdc8987
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87251171"
---
# <a name="dotnet-build"></a><span data-ttu-id="88889-103">dotnet build</span><span class="sxs-lookup"><span data-stu-id="88889-103">dotnet build</span></span>

<span data-ttu-id="88889-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.x y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="88889-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="88889-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="88889-105">Name</span></span>

<span data-ttu-id="88889-106">`dotnet build`: compila un proyecto y todas sus dependencias.</span><span class="sxs-lookup"><span data-stu-id="88889-106">`dotnet build` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="88889-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="88889-107">Synopsis</span></span>

```dotnetcli
dotnet build [<PROJECT>|<SOLUTION>] [-c|--configuration <CONFIGURATION>]
    [-f|--framework <FRAMEWORK>] [--force] [--interactive] [--no-dependencies]
    [--no-incremental] [--no-restore] [--nologo] [-o|--output <OUTPUT_DIRECTORY>]
    [-r|--runtime <RUNTIME_IDENTIFIER>] [--source <SOURCE>]
    [-v|--verbosity <LEVEL>] [--version-suffix <VERSION_SUFFIX>]

dotnet build -h|--help
```

## <a name="description"></a><span data-ttu-id="88889-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="88889-108">Description</span></span>

<span data-ttu-id="88889-109">El comando `dotnet build` crea el proyecto y sus dependencias en un conjunto de archivos binarios.</span><span class="sxs-lookup"><span data-stu-id="88889-109">The `dotnet build` command builds the project and its dependencies into a set of binaries.</span></span> <span data-ttu-id="88889-110">Los archivos binarios incluyen el código del proyecto en archivos de lenguaje intermedio (IL) con una extensión *.dll*.</span><span class="sxs-lookup"><span data-stu-id="88889-110">The binaries include the project's code in Intermediate Language (IL) files with a *.dll* extension.</span></span>  <span data-ttu-id="88889-111">Según el tipo de proyecto y la configuración, se pueden incluir otros archivos, como los siguientes:</span><span class="sxs-lookup"><span data-stu-id="88889-111">Depending on the project type and settings, other files may be included, such as:</span></span>

- <span data-ttu-id="88889-112">Un archivo ejecutable que se pueda usar para ejecutar la aplicación, si el tipo de proyecto es un archivo ejecutable que tiene como destino .NET Core 3.0 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="88889-112">An executable that can be used to run the application, if the project type is an executable targeting .NET Core 3.0 or later.</span></span>
- <span data-ttu-id="88889-113">Archivos de símbolos usados para la depuración con una extensión *.pdb*.</span><span class="sxs-lookup"><span data-stu-id="88889-113">Symbol files used for debugging with a *.pdb* extension.</span></span>
- <span data-ttu-id="88889-114">Un archivo *.deps.json*, que muestra las dependencias de la aplicación o la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="88889-114">A *.deps.json* file, which lists the dependencies of the application or library.</span></span>
- <span data-ttu-id="88889-115">Un archivo *.runtimeconfig.json*, que especifica el runtime compartido y su versión de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="88889-115">A *.runtimeconfig.json* file, which specifies the shared runtime and its version for an application.</span></span>
- <span data-ttu-id="88889-116">Otras bibliotecas de las que depende el proyecto (a través de referencias de proyecto o referencias de paquetes NuGet).</span><span class="sxs-lookup"><span data-stu-id="88889-116">Other libraries that the project depends on (via project references or NuGet package references).</span></span>

<span data-ttu-id="88889-117">En el caso de los proyectos ejecutables que tienen como destino versiones anteriores a .NET Core 3.0, las dependencias de biblioteca de NuGet normalmente no se copian en la carpeta de salida.</span><span class="sxs-lookup"><span data-stu-id="88889-117">For executable projects targeting versions earlier than .NET Core 3.0, library dependencies from NuGet are typically NOT copied to the output folder.</span></span>  <span data-ttu-id="88889-118">Se resuelven desde la carpeta de paquetes globales NuGet en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="88889-118">They're resolved from the NuGet global packages folder at run time.</span></span> <span data-ttu-id="88889-119">Teniendo eso en cuenta, el producto de `dotnet build` no está listo para transferirse a otra máquina para ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="88889-119">With that in mind, the product of `dotnet build` isn't ready to be transferred to another machine to run.</span></span> <span data-ttu-id="88889-120">Para crear una versión de la aplicación que se pueda implementar, se debe publicar (por ejemplo, con el comando [dotnet publish](dotnet-publish.md)).</span><span class="sxs-lookup"><span data-stu-id="88889-120">To create a version of the application that can be deployed, you need to publish it (for example, with the [dotnet publish](dotnet-publish.md) command).</span></span> <span data-ttu-id="88889-121">Para obtener más información, consulte el tema [Implementación de aplicaciones .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="88889-121">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span>

<span data-ttu-id="88889-122">En el caso de los proyectos ejecutables que tienen como destino .NET Core 3.0 y versiones posteriores, las dependencias de biblioteca se copian en la carpeta de salida.</span><span class="sxs-lookup"><span data-stu-id="88889-122">For executable projects targeting .NET Core 3.0 and later, library dependencies are copied to the output folder.</span></span> <span data-ttu-id="88889-123">Esto significa que, si no hay ninguna otra lógica específica de la publicación (como los proyectos web), se debería poder implementar la salida de la compilación.</span><span class="sxs-lookup"><span data-stu-id="88889-123">This means that if there isn't any other publish-specific logic (such as Web projects have), the build output should be deployable.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="88889-124">Restauración implícita</span><span class="sxs-lookup"><span data-stu-id="88889-124">Implicit restore</span></span>

<span data-ttu-id="88889-125">La compilación requiere el archivo *project.assets.json*, que muestra las dependencias de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="88889-125">Building requires the *project.assets.json* file, which lists the dependencies of your application.</span></span> <span data-ttu-id="88889-126">El archivo se crea cuando se ejecuta [`dotnet restore`](dotnet-restore.md).</span><span class="sxs-lookup"><span data-stu-id="88889-126">The file is created when [`dotnet restore`](dotnet-restore.md) is executed.</span></span> <span data-ttu-id="88889-127">Sin el archivo de recursos en su lugar, las herramientas no pueden resolver los ensamblados de referencia, lo que se traduce en errores.</span><span class="sxs-lookup"><span data-stu-id="88889-127">Without the assets file in place, the tooling can't resolve reference assemblies, which results in errors.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

### <a name="executable-or-library-output"></a><span data-ttu-id="88889-128">Salida de biblioteca o ejecutable</span><span class="sxs-lookup"><span data-stu-id="88889-128">Executable or library output</span></span>

<span data-ttu-id="88889-129">Si el proyecto es ejecutable o no viene determinado por la propiedad `<OutputType>` en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="88889-129">Whether the project is executable or not is determined by the `<OutputType>` property in the project file.</span></span> <span data-ttu-id="88889-130">En el ejemplo siguiente se muestra un proyecto en el que se genera código ejecutable:</span><span class="sxs-lookup"><span data-stu-id="88889-130">The following example shows a project that produces executable code:</span></span>

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="88889-131">Para generar una biblioteca, omita la propiedad `<OutputType>` o cambie su valor a `Library`.</span><span class="sxs-lookup"><span data-stu-id="88889-131">To produce a library, omit the `<OutputType>` property or change its value to `Library`.</span></span> <span data-ttu-id="88889-132">La DLL de IL para una biblioteca no contiene puntos de entrada y no se puede ejecutar.</span><span class="sxs-lookup"><span data-stu-id="88889-132">The IL DLL for a library doesn't contain entry points and can't be executed.</span></span>

### <a name="msbuild"></a><span data-ttu-id="88889-133">MSBuild</span><span class="sxs-lookup"><span data-stu-id="88889-133">MSBuild</span></span>

<span data-ttu-id="88889-134">`dotnet build` usa MSBuild para compilar el proyecto, por lo que admite las compilaciones en paralelo e incrementales.</span><span class="sxs-lookup"><span data-stu-id="88889-134">`dotnet build` uses MSBuild to build the project, so it supports both parallel and incremental builds.</span></span> <span data-ttu-id="88889-135">Para obtener más información, consulte [Compilaciones incrementales](/visualstudio/msbuild/incremental-builds).</span><span class="sxs-lookup"><span data-stu-id="88889-135">For more information, see [Incremental Builds](/visualstudio/msbuild/incremental-builds).</span></span>

<span data-ttu-id="88889-136">Además de sus opciones, el comando `dotnet build` acepta opciones de MSBuild, como `-p` para establecer propiedades o `-l` para definir un registrador.</span><span class="sxs-lookup"><span data-stu-id="88889-136">In addition to its options, the `dotnet build` command accepts MSBuild options, such as `-p` for setting properties or `-l` to define a logger.</span></span> <span data-ttu-id="88889-137">Para obtener más información sobre estas opciones, vea la [Referencia de la línea de comandos de MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="88889-137">For more information about these options, see the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> <span data-ttu-id="88889-138">O también puede usar el comando [dotnet msbuild](dotnet-msbuild.md).</span><span class="sxs-lookup"><span data-stu-id="88889-138">Or you can also use the [dotnet msbuild](dotnet-msbuild.md) command.</span></span>

<span data-ttu-id="88889-139">Ejecutar `dotnet build` es equivalente a ejecutar `dotnet msbuild -restore`; sin embargo, el nivel de detalle predeterminado de la salida es distinto.</span><span class="sxs-lookup"><span data-stu-id="88889-139">Running `dotnet build` is equivalent to running `dotnet msbuild -restore`; however, the default verbosity of the output is different.</span></span>

## <a name="arguments"></a><span data-ttu-id="88889-140">Argumentos</span><span class="sxs-lookup"><span data-stu-id="88889-140">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="88889-141">El archivo de proyecto o solución para compilar.</span><span class="sxs-lookup"><span data-stu-id="88889-141">The project or solution file to build.</span></span> <span data-ttu-id="88889-142">Si no se especifica un archivo de proyecto o solución, MSBuild busca en el directorio de trabajo actual un archivo que tiene una extensión de archivo que termina por *proj* o *sln* y usa ese archivo.</span><span class="sxs-lookup"><span data-stu-id="88889-142">If a project or solution file isn't specified, MSBuild searches the current working directory for a file that has a file extension that ends in either *proj* or *sln* and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="88889-143">Opciones</span><span class="sxs-lookup"><span data-stu-id="88889-143">Options</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="88889-144">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="88889-144">Defines the build configuration.</span></span> <span data-ttu-id="88889-145">El valor predeterminado para la mayoría de los proyectos es `Debug`, pero puede invalidar los valores de configuración de compilación en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="88889-145">The default for most projects is `Debug`, but you can override the build configuration settings in your project.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="88889-146">Compila para un [marco de trabajo](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="88889-146">Compiles for a specific [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="88889-147">El marco se debe definir en el [archivo de proyecto](csproj.md).</span><span class="sxs-lookup"><span data-stu-id="88889-147">The framework must be defined in the [project file](csproj.md).</span></span>

- **`--force`**

  <span data-ttu-id="88889-148">Fuerza la resolución de todas las dependencias, incluso si la última restauración se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="88889-148">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="88889-149">Especificar esta marca es lo mismo que eliminar el archivo *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="88889-149">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

- **`-h|--help`**

  <span data-ttu-id="88889-150">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="88889-150">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="88889-151">Permite que el comando se detenga y espere una entrada o una acción del usuario.</span><span class="sxs-lookup"><span data-stu-id="88889-151">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="88889-152">Por ejemplo, para completar la autenticación.</span><span class="sxs-lookup"><span data-stu-id="88889-152">For example, to complete authentication.</span></span> <span data-ttu-id="88889-153">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="88889-153">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="88889-154">Omite las referencias de proyecto a proyecto (P2P) y solo compila el proyecto raíz especificado.</span><span class="sxs-lookup"><span data-stu-id="88889-154">Ignores project-to-project (P2P) references and only builds the specified root project.</span></span>

- **`--no-incremental`**

  <span data-ttu-id="88889-155">Marca la compilación como no segura para la compilación incremental.</span><span class="sxs-lookup"><span data-stu-id="88889-155">Marks the build as unsafe for incremental build.</span></span> <span data-ttu-id="88889-156">Esta marca desactiva la compilación incremental y fuerza una recompilación limpia del gráfico de dependencias del proyecto.</span><span class="sxs-lookup"><span data-stu-id="88889-156">This flag turns off incremental compilation and forces a clean rebuild of the project's dependency graph.</span></span>

- **`--no-restore`**

  <span data-ttu-id="88889-157">No ejecuta una restauración implícita durante la compilación.</span><span class="sxs-lookup"><span data-stu-id="88889-157">Doesn't execute an implicit restore during build.</span></span>

- **`--nologo`**

  <span data-ttu-id="88889-158">No se muestra la pancarta de inicio ni el mensaje de copyright.</span><span class="sxs-lookup"><span data-stu-id="88889-158">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="88889-159">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="88889-159">Available since .NET Core 3.0 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="88889-160">Directorio donde se colocan los archivos binarios compilados.</span><span class="sxs-lookup"><span data-stu-id="88889-160">Directory in which to place the built binaries.</span></span> <span data-ttu-id="88889-161">Si no se especifica la ruta de acceso predeterminada es `./bin/<configuration>/<framework>/`.</span><span class="sxs-lookup"><span data-stu-id="88889-161">If not specified, the default path is `./bin/<configuration>/<framework>/`.</span></span>  <span data-ttu-id="88889-162">En el caso de los proyectos con varias plataformas de destino (a través de la propiedad `TargetFrameworks`), también debe definir `--framework` al especificar esta opción.</span><span class="sxs-lookup"><span data-stu-id="88889-162">For projects with multiple target frameworks (via the `TargetFrameworks` property), you also need to define `--framework` when you specify this option.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="88889-163">Especifica el tiempo de ejecución de destino.</span><span class="sxs-lookup"><span data-stu-id="88889-163">Specifies the target runtime.</span></span> <span data-ttu-id="88889-164">Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="88889-164">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

- **`--source <SOURCE>`**

  <span data-ttu-id="88889-165">URI del origen del paquete NuGet que se usará durante la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="88889-165">The URI of the NuGet package source to use during the restore operation.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="88889-166">Establece el nivel de detalle de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="88889-166">Sets the MSBuild verbosity level.</span></span> <span data-ttu-id="88889-167">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="88889-167">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="88889-168">De manera predeterminada, es `minimal`.</span><span class="sxs-lookup"><span data-stu-id="88889-168">The default is `minimal`.</span></span>

- **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="88889-169">Establece el valor de la propiedad `$(VersionSuffix)` que se va a usar al compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="88889-169">Sets the value of the `$(VersionSuffix)` property to use when building the project.</span></span> <span data-ttu-id="88889-170">Solo funciona si no se establece la propiedad `$(Version)`.</span><span class="sxs-lookup"><span data-stu-id="88889-170">This only works if the `$(Version)` property isn't set.</span></span> <span data-ttu-id="88889-171">A continuación, `$(Version)` se establece en `$(VersionPrefix)` combinada con `$(VersionSuffix)`, separadas por un guion.</span><span class="sxs-lookup"><span data-stu-id="88889-171">Then, `$(Version)` is set to the `$(VersionPrefix)` combined with the `$(VersionSuffix)`, separated by a dash.</span></span>

## <a name="examples"></a><span data-ttu-id="88889-172">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="88889-172">Examples</span></span>

- <span data-ttu-id="88889-173">Creación de un proyecto y sus dependencias:</span><span class="sxs-lookup"><span data-stu-id="88889-173">Build a project and its dependencies:</span></span>

  ```dotnetcli
  dotnet build
  ```

- <span data-ttu-id="88889-174">Creación de un proyecto y sus dependencias mediante la configuración de lanzamiento:</span><span class="sxs-lookup"><span data-stu-id="88889-174">Build a project and its dependencies using Release configuration:</span></span>

  ```dotnetcli
  dotnet build --configuration Release
  ```

- <span data-ttu-id="88889-175">Compilación de un proyecto y sus dependencias para un tiempo de ejecución concreto (en este ejemplo, Ubuntu 18.04):</span><span class="sxs-lookup"><span data-stu-id="88889-175">Build a project and its dependencies for a specific runtime (in this example, Ubuntu 18.04):</span></span>

  ```dotnetcli
  dotnet build --runtime ubuntu.18.04-x64
  ```

- <span data-ttu-id="88889-176">Compile el proyecto y use origen del paquete NuGet especificado durante la operación de restauración (SDK de .NET Core 2.0 y versiones posteriores):</span><span class="sxs-lookup"><span data-stu-id="88889-176">Build the project and use the specified NuGet package source during the restore operation (.NET Core 2.0 SDK and later versions):</span></span>

  ```dotnetcli
  dotnet build --source c:\packages\mypackages
  ```

- <span data-ttu-id="88889-177">Compile el proyecto y establezca la versión 1.2.3.4 como un parámetro de compilación mediante la [opción de MSBuild](#msbuild) `-p`:</span><span class="sxs-lookup"><span data-stu-id="88889-177">Build the project and set version 1.2.3.4 as a build parameter using the `-p` [MSBuild option](#msbuild):</span></span>

  ```dotnetcli
  dotnet build -p:Version=1.2.3.4
  ```
