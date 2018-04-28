---
title: 'Comando dotnet pack: CLI de .NET Core'
description: El comando dotnet pack crea paquetes de NuGet para el proyecto de .NET Core.
author: mairaw
ms.author: mairaw
ms.date: 03/10/2018
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: fdbf3b23813f09ad9902f6b0457f176139b405a4
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-pack"></a><span data-ttu-id="c053a-103">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="c053a-103">dotnet pack</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="c053a-104">nombre</span><span class="sxs-lookup"><span data-stu-id="c053a-104">Name</span></span>

<span data-ttu-id="c053a-105">`dotnet pack`: empaqueta el código en un paquete de NuGet.</span><span class="sxs-lookup"><span data-stu-id="c053a-105">`dotnet pack` - Packs the code into a NuGet package.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c053a-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="c053a-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="c053a-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="c053a-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet pack [<PROJECT>] [-c|--configuration] [--force] [--include-source] [--include-symbols] [--no-build] [--no-dependencies]
    [--no-restore] [-o|--output] [--runtime] [-s|--serviceable] [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c053a-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c053a-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet pack [<PROJECT>] [-c|--configuration] [--include-source] [--include-symbols] [--no-build] [-o|--output] [-s|--serviceable] [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="c053a-109">Description</span><span class="sxs-lookup"><span data-stu-id="c053a-109">Description</span></span>

<span data-ttu-id="c053a-110">El comando `dotnet pack` compila el proyecto y crea paquetes de NuGet.</span><span class="sxs-lookup"><span data-stu-id="c053a-110">The `dotnet pack` command builds the project and creates NuGet packages.</span></span> <span data-ttu-id="c053a-111">El resultado de este comando es un paquete de NuGet.</span><span class="sxs-lookup"><span data-stu-id="c053a-111">The result of this command is a NuGet package.</span></span> <span data-ttu-id="c053a-112">Si la opción `--include-symbols` está presente, se crea otro paquete que contiene los símbolos de depuración.</span><span class="sxs-lookup"><span data-stu-id="c053a-112">If the `--include-symbols` option is present, another package containing the debug symbols is created.</span></span>

<span data-ttu-id="c053a-113">Las dependencias de NuGet del proyecto empaquetado se agregan al archivo *.nuspec*, por lo que se pueden resolver adecuadamente cuando se instala el paquete.</span><span class="sxs-lookup"><span data-stu-id="c053a-113">NuGet dependencies of the packed project are added to the *.nuspec* file, so they're properly resolved when the package is installed.</span></span> <span data-ttu-id="c053a-114">Las referencias de proyecto a proyecto no se empaquetan dentro del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c053a-114">Project-to-project references aren't packaged inside the project.</span></span> <span data-ttu-id="c053a-115">Actualmente, debe disponer de un paquete por proyecto si tiene dependencias de proyecto a proyecto.</span><span class="sxs-lookup"><span data-stu-id="c053a-115">Currently, you must have a package per project if you have project-to-project dependencies.</span></span>

<span data-ttu-id="c053a-116">De forma predeterminada, `dotnet pack` compila primero el proyecto.</span><span class="sxs-lookup"><span data-stu-id="c053a-116">By default, `dotnet pack` builds the project first.</span></span> <span data-ttu-id="c053a-117">Si desea evitar este comportamiento, pase la opción `--no-build`.</span><span class="sxs-lookup"><span data-stu-id="c053a-117">If you wish to avoid this behavior, pass the `--no-build` option.</span></span> <span data-ttu-id="c053a-118">A menudo resulta útil en escenarios de compilación de integración continua (CI) donde se conoce el código que se compiló anteriormente.</span><span class="sxs-lookup"><span data-stu-id="c053a-118">This is often useful in Continuous Integration (CI) build scenarios where you know the code was previously built.</span></span>

<span data-ttu-id="c053a-119">Puede proporcionar propiedades de MSBuild en el comando `dotnet pack` para el proceso de empaquetado.</span><span class="sxs-lookup"><span data-stu-id="c053a-119">You can provide MSBuild properties to the `dotnet pack` command for the packing process.</span></span> <span data-ttu-id="c053a-120">Para obtener más información, vea [Propiedades de metadatos de NuGet](csproj.md#nuget-metadata-properties) y la [Referencia de la línea de comandos de MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="c053a-120">For more information, see [NuGet metadata properties](csproj.md#nuget-metadata-properties) and the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> <span data-ttu-id="c053a-121">La sección [Ejemplos](#examples) muestra cómo utilizar el modificador /p de MSBuild en un par de escenarios diferentes.</span><span class="sxs-lookup"><span data-stu-id="c053a-121">The [Examples](#examples) section shows how to use the MSBuild /p switch for a couple of different scenarios.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a><span data-ttu-id="c053a-122">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c053a-122">Arguments</span></span>

`PROJECT`

<span data-ttu-id="c053a-123">El proyecto para empaquetar.</span><span class="sxs-lookup"><span data-stu-id="c053a-123">The project to pack.</span></span> <span data-ttu-id="c053a-124">O bien una ruta de acceso a un [archivo csproj](csproj.md) o a un directorio.</span><span class="sxs-lookup"><span data-stu-id="c053a-124">It's either a path to a [csproj file](csproj.md) or to a directory.</span></span> <span data-ttu-id="c053a-125">Si se omite, se toma como predeterminado el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="c053a-125">If omitted, it defaults to the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="c053a-126">Opciones</span><span class="sxs-lookup"><span data-stu-id="c053a-126">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="c053a-127">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="c053a-127">.NET Core 2.x</span></span>](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="c053a-128">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="c053a-128">Defines the build configuration.</span></span> <span data-ttu-id="c053a-129">El valor predeterminado es `Debug`.</span><span class="sxs-lookup"><span data-stu-id="c053a-129">The default value is `Debug`.</span></span>

<span data-ttu-id="c053a-130">`--force`: fuerza la resolución de todas las dependencias, incluso si la última restauración se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="c053a-130">`--force` Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="c053a-131">Esto es equivalente a eliminar el archivo *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="c053a-131">This is equivalent to deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="c053a-132">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="c053a-132">Prints out a short help for the command.</span></span>

`--include-source`

<span data-ttu-id="c053a-133">Incluye los archivos de origen en el paquete de NuGet.</span><span class="sxs-lookup"><span data-stu-id="c053a-133">Includes the source files in the NuGet package.</span></span> <span data-ttu-id="c053a-134">Los archivos de origen se incluyen en la carpeta `src` dentro de `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="c053a-134">The sources files are included in the `src` folder within the `nupkg`.</span></span>

`--include-symbols`

<span data-ttu-id="c053a-135">Genera símbolos `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="c053a-135">Generates the symbols `nupkg`.</span></span>

`--no-build`

<span data-ttu-id="c053a-136">No compila el proyecto antes de empaquetarlo.</span><span class="sxs-lookup"><span data-stu-id="c053a-136">Doesn't build the project before packing.</span></span>

`--no-dependencies`

<span data-ttu-id="c053a-137">Omite las referencias de proyecto a proyecto y solo restaura el proyecto raíz.</span><span class="sxs-lookup"><span data-stu-id="c053a-137">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="c053a-138">No realiza una restauración implícita al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="c053a-138">Doesn't perform an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="c053a-139">Coloca los paquetes compilados en el directorio especificado.</span><span class="sxs-lookup"><span data-stu-id="c053a-139">Places the built packages in the directory specified.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="c053a-140">Especifica el tiempo de ejecución de destino para el que restaurar los paquetes.</span><span class="sxs-lookup"><span data-stu-id="c053a-140">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="c053a-141">Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="c053a-141">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-s|--serviceable`

<span data-ttu-id="c053a-142">Establece la marca de servicio en el paquete.</span><span class="sxs-lookup"><span data-stu-id="c053a-142">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="c053a-143">Para más información, consulte [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing) (Blog de .NET: .NET 4.5.1 admite actualizaciones de seguridad de Microsoft para bibliotecas NuGet de .NET).</span><span class="sxs-lookup"><span data-stu-id="c053a-143">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="c053a-144">Define el valor de la propiedad de `$(VersionSuffix)` en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="c053a-144">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="c053a-145">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="c053a-145">Sets the verbosity level of the command.</span></span> <span data-ttu-id="c053a-146">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="c053a-146">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c053a-147">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c053a-147">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="c053a-148">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="c053a-148">Defines the build configuration.</span></span> <span data-ttu-id="c053a-149">El valor predeterminado es `Debug`.</span><span class="sxs-lookup"><span data-stu-id="c053a-149">The default value is `Debug`.</span></span>

`-h|--help`

<span data-ttu-id="c053a-150">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="c053a-150">Prints out a short help for the command.</span></span>

`--include-source`

<span data-ttu-id="c053a-151">Incluye los archivos de origen en el paquete de NuGet.</span><span class="sxs-lookup"><span data-stu-id="c053a-151">Includes the source files in the NuGet package.</span></span> <span data-ttu-id="c053a-152">Los archivos de origen se incluyen en la carpeta `src` dentro de `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="c053a-152">The sources files are included in the `src` folder within the `nupkg`.</span></span>

`--include-symbols`

<span data-ttu-id="c053a-153">Genera símbolos `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="c053a-153">Generates the symbols `nupkg`.</span></span>

`--no-build`

<span data-ttu-id="c053a-154">No compila el proyecto antes de empaquetarlo.</span><span class="sxs-lookup"><span data-stu-id="c053a-154">Doesn't build the project before packing.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="c053a-155">Coloca los paquetes compilados en el directorio especificado.</span><span class="sxs-lookup"><span data-stu-id="c053a-155">Places the built packages in the directory specified.</span></span>

`-s|--serviceable`

<span data-ttu-id="c053a-156">Establece la marca de servicio en el paquete.</span><span class="sxs-lookup"><span data-stu-id="c053a-156">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="c053a-157">Para más información, consulte [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing) (Blog de .NET: .NET 4.5.1 admite actualizaciones de seguridad de Microsoft para bibliotecas NuGet de .NET).</span><span class="sxs-lookup"><span data-stu-id="c053a-157">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="c053a-158">Define el valor de la propiedad de `$(VersionSuffix)` en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="c053a-158">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="c053a-159">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="c053a-159">Sets the verbosity level of the command.</span></span> <span data-ttu-id="c053a-160">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="c053a-160">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="c053a-161">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c053a-161">Examples</span></span>

<span data-ttu-id="c053a-162">Empaquetado del proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="c053a-162">Pack the project in the current directory:</span></span>

`dotnet pack`

<span data-ttu-id="c053a-163">Empaquetar el proyecto `app1`:</span><span class="sxs-lookup"><span data-stu-id="c053a-163">Pack the `app1` project:</span></span>

`dotnet pack ~/projects/app1/project.csproj`

<span data-ttu-id="c053a-164">Empaquetar el proyecto en el directorio actual y colocar los paquetes resultantes en la carpeta `nupkgs`:</span><span class="sxs-lookup"><span data-stu-id="c053a-164">Pack the project in the current directory and place the resulting packages into the `nupkgs` folder:</span></span>

`dotnet pack --output nupkgs`

<span data-ttu-id="c053a-165">Empaquetar el proyecto en el directorio actual en la carpeta `nupkgs` y omitir del paso de compilación:</span><span class="sxs-lookup"><span data-stu-id="c053a-165">Pack the project in the current directory into the `nupkgs` folder and skip the build step:</span></span>

`dotnet pack --no-build --output nupkgs`

<span data-ttu-id="c053a-166">Con el sufijo de la versión del proyecto configurado como `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` en el archivo *.csproj*, empaquetar el proyecto actual y actualizar la versión del paquete resultante con el sufijo dado:</span><span class="sxs-lookup"><span data-stu-id="c053a-166">With the project's version suffix configured as `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` in the *.csproj* file, pack the current project and update the resulting package version with the given suffix:</span></span>

`dotnet pack --version-suffix "ci-1234"`

<span data-ttu-id="c053a-167">Establecer la versión del paquete en `2.1.0` con la propiedad de MSBuild `PackageVersion`:</span><span class="sxs-lookup"><span data-stu-id="c053a-167">Set the package version to `2.1.0` with the `PackageVersion` MSBuild property:</span></span>

`dotnet pack /p:PackageVersion=2.1.0`

<span data-ttu-id="c053a-168">Empaquete el proyecto para un determinado [marco de destino](../../standard/frameworks.md):</span><span class="sxs-lookup"><span data-stu-id="c053a-168">Pack the project for a specific [target framework](../../standard/frameworks.md):</span></span>

`dotnet pack /p:TargetFrameworks=net45`

<span data-ttu-id="c053a-169">Empaquete el proyecto y use un tiempo de ejecución específico (Windows 10) para la operación de restauración (SDK de .NET Core 2.0 y versiones superiores):</span><span class="sxs-lookup"><span data-stu-id="c053a-169">Pack the project and use a specific runtime (Windows 10) for the restore operation (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet pack --runtime win10-x64`