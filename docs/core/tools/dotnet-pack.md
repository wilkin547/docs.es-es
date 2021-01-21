---
title: Comando dotnet
description: El comando dotnet pack crea paquetes NuGet para el proyecto de .NET.
ms.date: 04/28/2020
ms.openlocfilehash: a9a634c358f5de4f28c3de06edc9a2b4d2eb8d57
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "98190083"
---
# <a name="dotnet-pack"></a><span data-ttu-id="2b008-103">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="2b008-103">dotnet pack</span></span>

<span data-ttu-id="2b008-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.x y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="2b008-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="2b008-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="2b008-105">Name</span></span>

<span data-ttu-id="2b008-106">`dotnet pack`: empaqueta el código en un paquete de NuGet.</span><span class="sxs-lookup"><span data-stu-id="2b008-106">`dotnet pack` - Packs the code into a NuGet package.</span></span>

## <a name="synopsis"></a><span data-ttu-id="2b008-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="2b008-107">Synopsis</span></span>

```dotnetcli
dotnet pack [<PROJECT>|<SOLUTION>] [-c|--configuration <CONFIGURATION>]
    [--force] [--include-source] [--include-symbols] [--interactive]
    [--no-build] [--no-dependencies] [--no-restore] [--nologo]
    [-o|--output <OUTPUT_DIRECTORY>] [--runtime <RUNTIME_IDENTIFIER>]
    [-s|--serviceable] [-v|--verbosity <LEVEL>]
    [--version-suffix <VERSION_SUFFIX>]

dotnet pack -h|--help
```

## <a name="description"></a><span data-ttu-id="2b008-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="2b008-108">Description</span></span>

<span data-ttu-id="2b008-109">El comando `dotnet pack` compila el proyecto y crea paquetes de NuGet.</span><span class="sxs-lookup"><span data-stu-id="2b008-109">The `dotnet pack` command builds the project and creates NuGet packages.</span></span> <span data-ttu-id="2b008-110">El resultado de este comando es un paquete de NuGet (es decir, un archivo *.nupkg*).</span><span class="sxs-lookup"><span data-stu-id="2b008-110">The result of this command is a NuGet package (that is, a *.nupkg* file).</span></span>

<span data-ttu-id="2b008-111">Si quiere generar un paquete que contenga los símbolos de depuración, tiene dos opciones a su disposición:</span><span class="sxs-lookup"><span data-stu-id="2b008-111">If you want to generate a package that contains the debug symbols, you have two options available:</span></span>

- <span data-ttu-id="2b008-112">`--include-symbols`: crea el paquete de símbolos.</span><span class="sxs-lookup"><span data-stu-id="2b008-112">`--include-symbols` - it creates the symbols package.</span></span>
- <span data-ttu-id="2b008-113">`--include-source`: crea el paquete de símbolos con una carpeta `src` dentro que contiene los archivos de origen.</span><span class="sxs-lookup"><span data-stu-id="2b008-113">`--include-source` - it creates the symbols package with a `src` folder inside containing the source files.</span></span>

<span data-ttu-id="2b008-114">Las dependencias de NuGet del proyecto empaquetado se agregan al archivo *.nuspec*, por lo que se pueden resolver adecuadamente cuando se instala el paquete.</span><span class="sxs-lookup"><span data-stu-id="2b008-114">NuGet dependencies of the packed project are added to the *.nuspec* file, so they're properly resolved when the package is installed.</span></span> <span data-ttu-id="2b008-115">Las referencias de proyecto a proyecto no se empaquetan dentro del proyecto.</span><span class="sxs-lookup"><span data-stu-id="2b008-115">Project-to-project references aren't packaged inside the project.</span></span> <span data-ttu-id="2b008-116">Actualmente, debe disponer de un paquete por proyecto si tiene dependencias de proyecto a proyecto.</span><span class="sxs-lookup"><span data-stu-id="2b008-116">Currently, you must have a package per project if you have project-to-project dependencies.</span></span>

<span data-ttu-id="2b008-117">De forma predeterminada, `dotnet pack` compila primero el proyecto.</span><span class="sxs-lookup"><span data-stu-id="2b008-117">By default, `dotnet pack` builds the project first.</span></span> <span data-ttu-id="2b008-118">Si desea evitar este comportamiento, pase la opción `--no-build`.</span><span class="sxs-lookup"><span data-stu-id="2b008-118">If you wish to avoid this behavior, pass the `--no-build` option.</span></span> <span data-ttu-id="2b008-119">Esta opción a menudo resulta útil en escenarios de compilación de integración continua (CI) donde se conoce el código que se compiló anteriormente.</span><span class="sxs-lookup"><span data-stu-id="2b008-119">This option is often useful in Continuous Integration (CI) build scenarios where you know the code was previously built.</span></span>

> [!NOTE]
> <span data-ttu-id="2b008-120">En algunos casos, no se puede realizar la compilación implícita.</span><span class="sxs-lookup"><span data-stu-id="2b008-120">In some cases, the implicit build cannot be performed.</span></span> <span data-ttu-id="2b008-121">Esto puede ocurrir cuando se establece `GeneratePackageOnBuild`, para evitar una dependencia cíclica entre los destinos de compilación y de paquete.</span><span class="sxs-lookup"><span data-stu-id="2b008-121">This can occur when `GeneratePackageOnBuild` is set, to avoid a cyclic dependency between build and pack targets.</span></span> <span data-ttu-id="2b008-122">La compilación también puede producir un error si hay un archivo bloqueado u otro problema.</span><span class="sxs-lookup"><span data-stu-id="2b008-122">The build can also fail if there is a locked file or other issue.</span></span>

<span data-ttu-id="2b008-123">Puede proporcionar propiedades de MSBuild en el comando `dotnet pack` para el proceso de empaquetado.</span><span class="sxs-lookup"><span data-stu-id="2b008-123">You can provide MSBuild properties to the `dotnet pack` command for the packing process.</span></span> <span data-ttu-id="2b008-124">Para obtener más información, vea [pack y restore de NuGet como destinos de MSBuild](/nuget/reference/msbuild-targets#pack-target) y [Referencia de la línea de comandos de MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="2b008-124">For more information, see [NuGet pack target properties](/nuget/reference/msbuild-targets#pack-target) and the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> <span data-ttu-id="2b008-125">La sección [Ejemplos](#examples) muestra cómo utilizar el modificador `-p` de MSBuild en un par de escenarios diferentes.</span><span class="sxs-lookup"><span data-stu-id="2b008-125">The [Examples](#examples) section shows how to use the MSBuild `-p` switch for a couple of different scenarios.</span></span>

<span data-ttu-id="2b008-126">Los proyectos web no están empaquetados de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2b008-126">Web projects aren't packable by default.</span></span> <span data-ttu-id="2b008-127">Para invalidar el comportamiento predeterminado, agregue la siguiente propiedad a su archivo *.csproj*:</span><span class="sxs-lookup"><span data-stu-id="2b008-127">To override the default behavior, add the following property to your *.csproj* file:</span></span>

```xml
<PropertyGroup>
   <IsPackable>true</IsPackable>
</PropertyGroup>
```

### <a name="implicit-restore"></a><span data-ttu-id="2b008-128">Restauración implícita</span><span class="sxs-lookup"><span data-stu-id="2b008-128">Implicit restore</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a><span data-ttu-id="2b008-129">Argumentos</span><span class="sxs-lookup"><span data-stu-id="2b008-129">Arguments</span></span>

`PROJECT | SOLUTION`

  <span data-ttu-id="2b008-130">El archivo de proyecto o solución para empaquetar.</span><span class="sxs-lookup"><span data-stu-id="2b008-130">The project or solution to pack.</span></span> <span data-ttu-id="2b008-131">Se trata de una ruta a un archivo .csproj, .vbproj o .fsproj, o a un archivo de solución o un directorio.</span><span class="sxs-lookup"><span data-stu-id="2b008-131">It's either a path to a csproj, vbproj, or fsproj file, or to a solution file or directory.</span></span> <span data-ttu-id="2b008-132">Si no se especifica, el comando busca un archivo del proyecto o de la solución en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="2b008-132">If not specified, the command searches the current directory for a project or solution file.</span></span>

## <a name="options"></a><span data-ttu-id="2b008-133">Opciones</span><span class="sxs-lookup"><span data-stu-id="2b008-133">Options</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="2b008-134">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="2b008-134">Defines the build configuration.</span></span> <span data-ttu-id="2b008-135">El valor predeterminado para la mayoría de los proyectos es `Debug`, pero puede invalidar los valores de configuración de compilación en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="2b008-135">The default for most projects is `Debug`, but you can override the build configuration settings in your project.</span></span>

- **`--force`**

  <span data-ttu-id="2b008-136">Fuerza la resolución de todas las dependencias, incluso si la última restauración se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="2b008-136">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="2b008-137">Especificar esta marca es lo mismo que eliminar el archivo *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="2b008-137">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

- **`-h|--help`**

  <span data-ttu-id="2b008-138">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="2b008-138">Prints out a short help for the command.</span></span>

- **`--include-source`**

  <span data-ttu-id="2b008-139">Incluye los paquetes NuGet de símbolos de depuración, además de los paquetes NuGet normales en el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="2b008-139">Includes the debug symbols NuGet packages in addition to the regular NuGet packages in the output directory.</span></span> <span data-ttu-id="2b008-140">Los archivos de origen se incluyen en la carpeta `src` dentro del paquete de símbolos.</span><span class="sxs-lookup"><span data-stu-id="2b008-140">The sources files are included in the `src` folder within the symbols package.</span></span>

- **`--include-symbols`**

  <span data-ttu-id="2b008-141">Incluye los paquetes NuGet de símbolos de depuración, además de los paquetes NuGet normales en el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="2b008-141">Includes the debug symbols NuGet packages in addition to the regular NuGet packages in the output directory.</span></span>

- **`--interactive`**

  <span data-ttu-id="2b008-142">Permite que el comando se detenga y espere la entrada o acción del usuario (por ejemplo, completar la autenticación).</span><span class="sxs-lookup"><span data-stu-id="2b008-142">Allows the command to stop and wait for user input or action (for example, to complete authentication).</span></span> <span data-ttu-id="2b008-143">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="2b008-143">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-build`**

  <span data-ttu-id="2b008-144">No compila el proyecto antes de empaquetarlo.</span><span class="sxs-lookup"><span data-stu-id="2b008-144">Doesn't build the project before packing.</span></span> <span data-ttu-id="2b008-145">También establece la marca `--no-restore` de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="2b008-145">It also implicitly sets the `--no-restore` flag.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="2b008-146">Omite las referencias de proyecto a proyecto y solo restaura el proyecto raíz.</span><span class="sxs-lookup"><span data-stu-id="2b008-146">Ignores project-to-project references and only restores the root project.</span></span>

- **`--no-restore`**

  <span data-ttu-id="2b008-147">No ejecuta una restauración implícita al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="2b008-147">Doesn't execute an implicit restore when running the command.</span></span>

- **`--nologo`**

  <span data-ttu-id="2b008-148">No se muestra la pancarta de inicio ni el mensaje de copyright.</span><span class="sxs-lookup"><span data-stu-id="2b008-148">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="2b008-149">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="2b008-149">Available since .NET Core 3.0 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="2b008-150">Coloca los paquetes compilados en el directorio especificado.</span><span class="sxs-lookup"><span data-stu-id="2b008-150">Places the built packages in the directory specified.</span></span>

- **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="2b008-151">Especifica el tiempo de ejecución de destino para el que restaurar los paquetes.</span><span class="sxs-lookup"><span data-stu-id="2b008-151">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="2b008-152">Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="2b008-152">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

- **`-s|--serviceable`**

  <span data-ttu-id="2b008-153">Establece la marca de servicio en el paquete.</span><span class="sxs-lookup"><span data-stu-id="2b008-153">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="2b008-154">Para obtener más información, vea [.NET Blog: .NET Framework 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing) (Blog de .NET: .NET Framework 4.5.1 admite actualizaciones de seguridad de Microsoft para bibliotecas NuGet de .NET).</span><span class="sxs-lookup"><span data-stu-id="2b008-154">For more information, see [.NET Blog: .NET Framework 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

- **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="2b008-155">Define el valor de la propiedad de `$(VersionSuffix)` en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="2b008-155">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="2b008-156">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="2b008-156">Sets the verbosity level of the command.</span></span> <span data-ttu-id="2b008-157">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="2b008-157">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="2b008-158">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="2b008-158">Examples</span></span>

- <span data-ttu-id="2b008-159">Empaquetado del proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="2b008-159">Pack the project in the current directory:</span></span>

  ```dotnetcli
  dotnet pack
  ```

- <span data-ttu-id="2b008-160">Empaquetar el proyecto `app1`:</span><span class="sxs-lookup"><span data-stu-id="2b008-160">Pack the `app1` project:</span></span>

  ```dotnetcli
  dotnet pack ~/projects/app1/project.csproj
  ```

- <span data-ttu-id="2b008-161">Empaquetar el proyecto en el directorio actual y colocar los paquetes resultantes en la carpeta `nupkgs`:</span><span class="sxs-lookup"><span data-stu-id="2b008-161">Pack the project in the current directory and place the resulting packages into the `nupkgs` folder:</span></span>

  ```dotnetcli
  dotnet pack --output nupkgs
  ```

- <span data-ttu-id="2b008-162">Empaquetar el proyecto en el directorio actual en la carpeta `nupkgs` y omitir del paso de compilación:</span><span class="sxs-lookup"><span data-stu-id="2b008-162">Pack the project in the current directory into the `nupkgs` folder and skip the build step:</span></span>

  ```dotnetcli
  dotnet pack --no-build --output nupkgs
  ```

- <span data-ttu-id="2b008-163">Con el sufijo de la versión del proyecto configurado como `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` en el archivo *.csproj*, empaquetar el proyecto actual y actualizar la versión del paquete resultante con el sufijo dado:</span><span class="sxs-lookup"><span data-stu-id="2b008-163">With the project's version suffix configured as `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` in the *.csproj* file, pack the current project and update the resulting package version with the given suffix:</span></span>

  ```dotnetcli
  dotnet pack --version-suffix "ci-1234"
  ```

- <span data-ttu-id="2b008-164">Establecer la versión del paquete en `2.1.0` con la propiedad de MSBuild `PackageVersion`:</span><span class="sxs-lookup"><span data-stu-id="2b008-164">Set the package version to `2.1.0` with the `PackageVersion` MSBuild property:</span></span>

  ```dotnetcli
  dotnet pack -p:PackageVersion=2.1.0
  ```

- <span data-ttu-id="2b008-165">Empaquete el proyecto para un determinado [marco de destino](../../standard/frameworks.md):</span><span class="sxs-lookup"><span data-stu-id="2b008-165">Pack the project for a specific [target framework](../../standard/frameworks.md):</span></span>

  ```dotnetcli
  dotnet pack -p:TargetFrameworks=net45
  ```

- <span data-ttu-id="2b008-166">Empaquete el proyecto y use un entorno de ejecución específico (Windows 10) para la operación de restauración:</span><span class="sxs-lookup"><span data-stu-id="2b008-166">Pack the project and use a specific runtime (Windows 10) for the restore operation:</span></span>

  ```dotnetcli
  dotnet pack --runtime win10-x64
  ```

- <span data-ttu-id="2b008-167">Empaquete el proyecto mediante un archivo *.nuspec*:</span><span class="sxs-lookup"><span data-stu-id="2b008-167">Pack the project using a *.nuspec* file:</span></span>

  ```dotnetcli
  dotnet pack ~/projects/app1/project.csproj -p:NuspecFile=~/projects/app1/project.nuspec -p:NuspecBasePath=~/projects/app1/nuget
  ```

  <span data-ttu-id="2b008-168">Para obtener información sobre cómo usar `NuspecFile`, `NuspecBasePath` y `NuspecProperties`, vea los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="2b008-168">For information about how to use `NuspecFile`, `NuspecBasePath`, and `NuspecProperties`, see the following resources:</span></span>

  - [<span data-ttu-id="2b008-169">Empaquetado mediante un archivo .nuspec</span><span class="sxs-lookup"><span data-stu-id="2b008-169">Packing using a .nuspec</span></span>](/nuget/reference/msbuild-targets#packing-using-a-nuspec)
  - [<span data-ttu-id="2b008-170">Puntos de extensión avanzados para crear un paquete personalizado</span><span class="sxs-lookup"><span data-stu-id="2b008-170">Advanced extension points to create customized package</span></span>](/nuget/reference/msbuild-targets#advanced-extension-points-to-create-customized-package)
  - [<span data-ttu-id="2b008-171">Propiedades globales</span><span class="sxs-lookup"><span data-stu-id="2b008-171">Global properties</span></span>](/visualstudio/msbuild/msbuild-properties#global-properties)
