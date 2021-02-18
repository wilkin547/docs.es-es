---
title: Información general sobre el SDK de proyectos de .NET
titleSuffix: ''
description: Obtenga información sobre los SDK de proyectos de .NET.
ms.date: 09/17/2020
ms.topic: conceptual
no-loc:
- EmbeddedResource
- Compile
- None
ms.openlocfilehash: e5a6d0a1c988818e507936b567fa0188675cedc3
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100432652"
---
# <a name="net-project-sdks"></a><span data-ttu-id="1a74d-103">SDK de proyectos de .NET</span><span class="sxs-lookup"><span data-stu-id="1a74d-103">.NET project SDKs</span></span>

<span data-ttu-id="1a74d-104">Los proyectos de .NET Core y .NET 5.0 y posteriores están asociados a un kit de desarrollo de software (SDK).</span><span class="sxs-lookup"><span data-stu-id="1a74d-104">.NET Core and .NET 5.0 and later projects are associated with a software development kit (SDK).</span></span> <span data-ttu-id="1a74d-105">Cada *SDK de proyecto* es un conjunto de [destinos de MSBuild](/visualstudio/msbuild/msbuild-targets) y [tareas](/visualstudio/msbuild/msbuild-tasks) asociadas que se encarga de compilar, empaquetar y publicar código.</span><span class="sxs-lookup"><span data-stu-id="1a74d-105">Each *project SDK* is a set of MSBuild [targets](/visualstudio/msbuild/msbuild-targets) and associated [tasks](/visualstudio/msbuild/msbuild-tasks) that are responsible for compiling, packing, and publishing code.</span></span> <span data-ttu-id="1a74d-106">Un proyecto que hace referencia a un SDK de proyecto en ocasiones se denomina *proyecto de estilo SDK*.</span><span class="sxs-lookup"><span data-stu-id="1a74d-106">A project that references a project SDK is sometimes referred to as an *SDK-style project*.</span></span>

## <a name="available-sdks"></a><span data-ttu-id="1a74d-107">SDK disponibles</span><span class="sxs-lookup"><span data-stu-id="1a74d-107">Available SDKs</span></span>

<span data-ttu-id="1a74d-108">Están disponibles los siguientes SDK:</span><span class="sxs-lookup"><span data-stu-id="1a74d-108">The following SDKs are available:</span></span>

| <span data-ttu-id="1a74d-109">ID</span><span class="sxs-lookup"><span data-stu-id="1a74d-109">ID</span></span> | <span data-ttu-id="1a74d-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="1a74d-110">Description</span></span> | <span data-ttu-id="1a74d-111">Repositorio</span><span class="sxs-lookup"><span data-stu-id="1a74d-111">Repo</span></span>|
| - | - | - |
| `Microsoft.NET.Sdk` | <span data-ttu-id="1a74d-112">SDK de .NET</span><span class="sxs-lookup"><span data-stu-id="1a74d-112">The .NET SDK</span></span> | <https://github.com/dotnet/sdk> |
| `Microsoft.NET.Sdk.Web` | <span data-ttu-id="1a74d-113">[SDK web](/aspnet/core/razor-pages/web-sdk) de .NET</span><span class="sxs-lookup"><span data-stu-id="1a74d-113">The .NET [Web SDK](/aspnet/core/razor-pages/web-sdk)</span></span> | <https://github.com/dotnet/sdk> |
| `Microsoft.NET.Sdk.Razor` | <span data-ttu-id="1a74d-114">[SDK de Razor](/aspnet/core/razor-pages/sdk) de .NET</span><span class="sxs-lookup"><span data-stu-id="1a74d-114">The .NET [Razor SDK](/aspnet/core/razor-pages/sdk)</span></span> |
| `Microsoft.NET.Sdk.Worker` | <span data-ttu-id="1a74d-115">SDK del servicio de trabajo de .NET</span><span class="sxs-lookup"><span data-stu-id="1a74d-115">The .NET Worker Service SDK</span></span> |
| `Microsoft.NET.Sdk.WindowsDesktop` | <span data-ttu-id="1a74d-116">[SDK de Escritorio](msbuild-props-desktop.md) de .NET, que incluye Windows Forms (WinForms) y Windows Presentation Foundation (WPF).\*</span><span class="sxs-lookup"><span data-stu-id="1a74d-116">The .NET [Desktop SDK](msbuild-props-desktop.md), which includes Windows Forms (WinForms) and Windows Presentation Foundation (WPF).\*</span></span> | <span data-ttu-id="1a74d-117"><https://github.com/dotnet/winforms> y <https://github.com/dotnet/wpf></span><span class="sxs-lookup"><span data-stu-id="1a74d-117"><https://github.com/dotnet/winforms> and <https://github.com/dotnet/wpf></span></span> |

<span data-ttu-id="1a74d-118">El SDK de .NET es el SDK base para .NET.</span><span class="sxs-lookup"><span data-stu-id="1a74d-118">The .NET SDK is the base SDK for .NET.</span></span> <span data-ttu-id="1a74d-119">Los otros SDK hacen referencia al SDK de .NET, y los proyectos asociados a los demás SDK disponen de todas las propiedades del SDK de .NET.</span><span class="sxs-lookup"><span data-stu-id="1a74d-119">The other SDKs reference the .NET SDK, and projects that are associated with the other SDKs have all the .NET SDK properties available to them.</span></span> <span data-ttu-id="1a74d-120">El SDK web, por ejemplo, depende de los SDK de .NET y de Razor.</span><span class="sxs-lookup"><span data-stu-id="1a74d-120">The Web SDK, for example, depends on both the .NET SDK and the Razor SDK.</span></span>

<span data-ttu-id="1a74d-121">También puede crear un SDK propio que se puede distribuir a través de NuGet.</span><span class="sxs-lookup"><span data-stu-id="1a74d-121">You can also author your own SDK that can be distributed via NuGet.</span></span>

<span data-ttu-id="1a74d-122">\* A partir de .NET 5.0, los proyectos de Windows Forms y Windows Presentation Foundation (WPF) deben especificar el SDK de .NET (`Microsoft.NET.Sdk`) en lugar de `Microsoft.NET.Sdk.WindowsDesktop`.</span><span class="sxs-lookup"><span data-stu-id="1a74d-122">\* Starting in .NET 5.0, Windows Forms and Windows Presentation Foundation (WPF) projects should specify the .NET SDK (`Microsoft.NET.Sdk`) instead of `Microsoft.NET.Sdk.WindowsDesktop`.</span></span> <span data-ttu-id="1a74d-123">Para estos proyectos, al establecer `TargetFramework` en `net5.0-windows` y `UseWPF` o `UseWindowsForms` en `true`, se importará automáticamente el SDK de escritorio de Windows.</span><span class="sxs-lookup"><span data-stu-id="1a74d-123">For these projects, setting `TargetFramework` to `net5.0-windows` and `UseWPF` or `UseWindowsForms` to `true` will automatically import the Windows desktop SDK.</span></span> <span data-ttu-id="1a74d-124">Si el proyecto tiene como destino .NET 5.0 o versiones posteriores y especifica el SDK de `Microsoft.NET.Sdk.WindowsDesktop`, obtendrá la advertencia de compilación NETSDK1137.</span><span class="sxs-lookup"><span data-stu-id="1a74d-124">If your project targets .NET 5.0 or later and specifies the `Microsoft.NET.Sdk.WindowsDesktop` SDK, you'll get build warning NETSDK1137.</span></span>

## <a name="project-files"></a><span data-ttu-id="1a74d-125">Archivos de proyecto</span><span class="sxs-lookup"><span data-stu-id="1a74d-125">Project files</span></span>

<span data-ttu-id="1a74d-126">Los proyectos de .NET se basan en el formato [MSBuild](/visualstudio/msbuild/msbuild).</span><span class="sxs-lookup"><span data-stu-id="1a74d-126">.NET projects are based on the [MSBuild](/visualstudio/msbuild/msbuild) format.</span></span> <span data-ttu-id="1a74d-127">Los archivos de proyecto, que tienen extensiones como *.csproj* para los proyectos de C# y *.fsproj* para los de F#, están en formato XML.</span><span class="sxs-lookup"><span data-stu-id="1a74d-127">Project files, which have extensions like *.csproj* for C# projects and *.fsproj* for F# projects, are in XML format.</span></span> <span data-ttu-id="1a74d-128">El elemento raíz de un archivo de proyecto de MSBuild es [Project](/visualstudio/msbuild/project-element-msbuild).</span><span class="sxs-lookup"><span data-stu-id="1a74d-128">The root element of an MSBuild project file is the [Project](/visualstudio/msbuild/project-element-msbuild) element.</span></span> <span data-ttu-id="1a74d-129">El elemento `Project` tiene un atributo `Sdk` opcional que especifica qué SDK (y versión) se van a usar.</span><span class="sxs-lookup"><span data-stu-id="1a74d-129">The `Project` element has an optional `Sdk` attribute that specifies which SDK (and version) to use.</span></span> <span data-ttu-id="1a74d-130">Para usar las herramientas de .NET y compilar el código, establezca el atributo `Sdk` en uno de los identificadores de la tabla [SDK disponibles](#available-sdks).</span><span class="sxs-lookup"><span data-stu-id="1a74d-130">To use the .NET tools and build your code, set the `Sdk` attribute to one of the IDs in the [Available SDKs](#available-sdks) table.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
</Project>
```

<span data-ttu-id="1a74d-131">Para especificar un SDK que proviene de NuGet, incluya la versión al final del nombre, o bien especifique el nombre y la versión en el archivo *global.json*.</span><span class="sxs-lookup"><span data-stu-id="1a74d-131">To specify an SDK that comes from NuGet, include the version at the end of the name, or specify the name and version in the *global.json* file.</span></span>

```xml
<Project Sdk="MSBuild.Sdk.Extras/2.0.54">
  ...
</Project>
```

<span data-ttu-id="1a74d-132">Otra manera de especificar el SDK es mediante el elemento [Sdk](/visualstudio/msbuild/sdk-element-msbuild) de nivel superior:</span><span class="sxs-lookup"><span data-stu-id="1a74d-132">Another way to specify the SDK is with the top-level [Sdk](/visualstudio/msbuild/sdk-element-msbuild) element:</span></span>

```xml
<Project>
  <Sdk Name="Microsoft.NET.Sdk" />
  ...
</Project>
```

<span data-ttu-id="1a74d-133">Al hacer referencia a un SDK de una de estas formas, se simplifican enormemente los archivos de proyecto de .NET.</span><span class="sxs-lookup"><span data-stu-id="1a74d-133">Referencing an SDK in one of these ways greatly simplifies project files for .NET.</span></span> <span data-ttu-id="1a74d-134">Durante la evaluación del proyecto, MSBuild agrega importaciones implícitas para `Sdk.props` en la parte superior del archivo del proyecto y para `Sdk.targets` en la inferior.</span><span class="sxs-lookup"><span data-stu-id="1a74d-134">While evaluating the project, MSBuild adds implicit imports for `Sdk.props` at the top of the project file and `Sdk.targets` at the bottom.</span></span>

```xml
<Project>
  <!-- Implicit top import -->
  <Import Project="Sdk.props" Sdk="Microsoft.NET.Sdk" />
  ...
  <!-- Implicit bottom import -->
  <Import Project="Sdk.targets" Sdk="Microsoft.NET.Sdk" />
</Project>
```

> [!TIP]
> <span data-ttu-id="1a74d-135">En un equipo con Windows, los archivos *Sdk.props* y *Sdk.targets* se pueden encontrar en la carpeta *%ProgramFiles%\dotnet\sdk\\[versión]\Sdks\Microsoft.NET.Sdk\Sdk*.</span><span class="sxs-lookup"><span data-stu-id="1a74d-135">On a Windows machine, the *Sdk.props* and *Sdk.targets* files can be found in the *%ProgramFiles%\dotnet\sdk\\[version]\Sdks\Microsoft.NET.Sdk\Sdk* folder.</span></span>

### <a name="preprocess-the-project-file"></a><span data-ttu-id="1a74d-136">Procesamiento previo del archivo del proyecto</span><span class="sxs-lookup"><span data-stu-id="1a74d-136">Preprocess the project file</span></span>

<span data-ttu-id="1a74d-137">Puede ver el proyecto totalmente expandido como MSBuild lo ve después de incluir el SDK y sus destinos mediante el comando `dotnet msbuild -preprocess`.</span><span class="sxs-lookup"><span data-stu-id="1a74d-137">You can see the fully expanded project as MSBuild sees it after the SDK and its targets are included by using the `dotnet msbuild -preprocess` command.</span></span> <span data-ttu-id="1a74d-138">El conmutador [preprocess](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) del comando [`dotnet msbuild`](../tools/dotnet-msbuild.md) muestra qué archivos se han importado, sus orígenes y sus contribuciones a la compilación sin tener que compilar el proyecto realmente.</span><span class="sxs-lookup"><span data-stu-id="1a74d-138">The [preprocess](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) switch of the [`dotnet msbuild`](../tools/dotnet-msbuild.md) command shows which files are imported, their sources, and their contributions to the build without actually building the project.</span></span>

<span data-ttu-id="1a74d-139">Si el proyecto tiene varias plataformas de destino, para centrar los resultados del comando en una sola, debe especificarla como una propiedad de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="1a74d-139">If the project has multiple target frameworks, focus the results of the command on only one framework by specifying it as an MSBuild property.</span></span> <span data-ttu-id="1a74d-140">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1a74d-140">For example:</span></span>

`dotnet msbuild -property:TargetFramework=netcoreapp2.0 -preprocess:output.xml`

## <a name="default-includes-and-excludes"></a><span data-ttu-id="1a74d-141">Inclusiones y exclusiones predeterminadas</span><span class="sxs-lookup"><span data-stu-id="1a74d-141">Default includes and excludes</span></span>

<span data-ttu-id="1a74d-142">Las inclusiones y exclusiones predeterminadas de los [elementos `Compile`](/visualstudio/msbuild/common-msbuild-project-items#compile), los [recursos insertados](/visualstudio/msbuild/common-msbuild-project-items#embeddedresource) y los [elementos `None`](/visualstudio/msbuild/common-msbuild-project-items#none) se definen en el SDK.</span><span class="sxs-lookup"><span data-stu-id="1a74d-142">The default includes and excludes for [`Compile` items](/visualstudio/msbuild/common-msbuild-project-items#compile), [embedded resources](/visualstudio/msbuild/common-msbuild-project-items#embeddedresource), and [`None` items](/visualstudio/msbuild/common-msbuild-project-items#none) are defined in the SDK.</span></span> <span data-ttu-id="1a74d-143">A diferencia de los proyectos de .NET Framework que no son de SDK, no es necesario especificar estos elementos en el archivo del proyecto, ya que los valores predeterminados cubren los casos de uso más comunes.</span><span class="sxs-lookup"><span data-stu-id="1a74d-143">Unlike non-SDK .NET Framework projects, you don't need to specify these items in your project file, because the defaults cover most common use cases.</span></span> <span data-ttu-id="1a74d-144">Este comportamiento hace que el archivo de proyecto sea más pequeño y más fácil de entender y editar manualmente, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="1a74d-144">This behavior makes the project file smaller and easier to understand and edit by hand, if needed.</span></span>

<span data-ttu-id="1a74d-145">En la tabla siguiente se muestra qué elementos y qué [globs](https://en.wikipedia.org/wiki/Glob_(programming)) se incluyen y excluyen en el SDK de .NET:</span><span class="sxs-lookup"><span data-stu-id="1a74d-145">The following table shows which elements and which [globs](https://en.wikipedia.org/wiki/Glob_(programming)) are included and excluded in the .NET SDK:</span></span>

| <span data-ttu-id="1a74d-146">Elemento</span><span class="sxs-lookup"><span data-stu-id="1a74d-146">Element</span></span>           | <span data-ttu-id="1a74d-147">Glob para incluir</span><span class="sxs-lookup"><span data-stu-id="1a74d-147">Include glob</span></span>                              | <span data-ttu-id="1a74d-148">Glob para excluir</span><span class="sxs-lookup"><span data-stu-id="1a74d-148">Exclude glob</span></span>                                                  | <span data-ttu-id="1a74d-149">Glob para quitar</span><span class="sxs-lookup"><span data-stu-id="1a74d-149">Remove glob</span></span>              |
|-------------------|-------------------------------------------|---------------------------------------------------------------|--------------------------|
| Compile           | <span data-ttu-id="1a74d-150">\*\*/\*.cs (u otras extensiones de lenguaje)</span><span class="sxs-lookup"><span data-stu-id="1a74d-150">\*\*/\*.cs (or other language extensions)</span></span> | <span data-ttu-id="1a74d-151">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="1a74d-151">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span></span>  | <span data-ttu-id="1a74d-152">N/D</span><span class="sxs-lookup"><span data-stu-id="1a74d-152">N/A</span></span>                      |
| EmbeddedResource  | <span data-ttu-id="1a74d-153">\*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="1a74d-153">\*\*/\*.resx</span></span>                              | <span data-ttu-id="1a74d-154">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="1a74d-154">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="1a74d-155">N/D</span><span class="sxs-lookup"><span data-stu-id="1a74d-155">N/A</span></span>                      |
| None              | \*\*/\*                                   | <span data-ttu-id="1a74d-156">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="1a74d-156">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="1a74d-157">\*\*/\*.cs; \*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="1a74d-157">\*\*/\*.cs; \*\*/\*.resx</span></span> |

> [!NOTE]
> <span data-ttu-id="1a74d-158">De forma predeterminada, las carpetas `./bin` y `./obj` (representadas por las propiedades de MSBuild `$(BaseOutputPath)` y `$(BaseIntermediateOutputPath)`) se excluyen de los globs.</span><span class="sxs-lookup"><span data-stu-id="1a74d-158">The `./bin` and `./obj` folders, which are represented by the `$(BaseOutputPath)` and `$(BaseIntermediateOutputPath)` MSBuild properties, are excluded from the globs by default.</span></span> <span data-ttu-id="1a74d-159">Las exclusiones se representan mediante la [propiedad DefaultItemExcludes](msbuild-props.md#defaultitemexcludes).</span><span class="sxs-lookup"><span data-stu-id="1a74d-159">Excludes are represented by the [DefaultItemExcludes property](msbuild-props.md#defaultitemexcludes).</span></span>

<span data-ttu-id="1a74d-160">El SDK de Escritorio de .NET tiene más inclusiones y exclusiones para WPF.</span><span class="sxs-lookup"><span data-stu-id="1a74d-160">The .NET Desktop SDK has more includes and excludes for WPF.</span></span> <span data-ttu-id="1a74d-161">Para obtener más información, vea [Inclusiones y exclusiones predeterminadas de WPF](msbuild-props-desktop.md#wpf-default-includes-and-excludes).</span><span class="sxs-lookup"><span data-stu-id="1a74d-161">For more information, see [WPF default includes and excludes](msbuild-props-desktop.md#wpf-default-includes-and-excludes).</span></span>

### <a name="build-errors"></a><span data-ttu-id="1a74d-162">Errores de compilación</span><span class="sxs-lookup"><span data-stu-id="1a74d-162">Build errors</span></span>

<span data-ttu-id="1a74d-163">Si define explícitamente cualquiera de estos elementos en el archivo del proyecto, es probable que obtenga un error de compilación "NETSDK1022" similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="1a74d-163">If you explicitly define any of these items in your project file, you're likely to get a "NETSDK1022" build error similar to the following:</span></span>

> <span data-ttu-id="1a74d-164">Se han incluido elementos "Compile" duplicados.</span><span class="sxs-lookup"><span data-stu-id="1a74d-164">Duplicate 'Compile' items were included.</span></span> <span data-ttu-id="1a74d-165">El SDK de .NET incluye elementos "Compile" del directorio del proyecto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1a74d-165">The .NET SDK includes 'Compile' items from your project directory by default.</span></span> <span data-ttu-id="1a74d-166">Puede quitar estos elementos del archivo del proyecto, o bien establecer la propiedad "EnableDefaultCompileItems" en "false" si quiere incluirlos de forma explícita en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="1a74d-166">You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file.</span></span>

> <span data-ttu-id="1a74d-167">Se han incluido elementos "EmbeddedResource" duplicados.</span><span class="sxs-lookup"><span data-stu-id="1a74d-167">Duplicate 'EmbeddedResource' items were included.</span></span> <span data-ttu-id="1a74d-168">El SDK de .NET incluye elementos "EmbeddedResource" del directorio del proyecto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1a74d-168">The .NET SDK includes 'EmbeddedResource' items from your project directory by default.</span></span> <span data-ttu-id="1a74d-169">Puede quitar estos elementos del archivo del proyecto, o bien establecer la propiedad "EnableDefaultEmbeddedResourceItems" en "false" si quiere incluirlos de forma explícita en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="1a74d-169">You can either remove these items from your project file, or set the 'EnableDefaultEmbeddedResourceItems' property to 'false' if you want to explicitly include them in your project file.</span></span>

<span data-ttu-id="1a74d-170">Para resolver los errores, lleve a cabo una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="1a74d-170">To resolve the errors, do one of the following:</span></span>

- <span data-ttu-id="1a74d-171">Quite los elementos `Compile`, `EmbeddedResource` o `None` explícitos que coincidan con los implícitos enumerados en la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="1a74d-171">Remove the explicit `Compile`, `EmbeddedResource`, or `None` items that match the implicit ones listed on the previous table.</span></span>

- <span data-ttu-id="1a74d-172">Establezca la [propiedad EnableDefaultItems](msbuild-props.md#enabledefaultitems) en `false` para deshabilitar toda la inclusión de archivos implícita:</span><span class="sxs-lookup"><span data-stu-id="1a74d-172">Set the [EnableDefaultItems property](msbuild-props.md#enabledefaultitems) to `false` to disable all implicit file inclusion:</span></span>

  ```xml
  <PropertyGroup>
    <EnableDefaultItems>false</EnableDefaultItems>
  </PropertyGroup>
  ```

  <span data-ttu-id="1a74d-173">Si quiere especificar que se publiquen archivos con la aplicación, puede seguir usando los mecanismos de MSBuild conocidos para ello, por ejemplo, el elemento `Content`.</span><span class="sxs-lookup"><span data-stu-id="1a74d-173">If you want to specify files to be published with your app, you can still use the known MSBuild mechanisms for that, for example, the `Content` element.</span></span>

- <span data-ttu-id="1a74d-174">Deshabilite de forma selectiva solo los patrones globales `Compile`, `EmbeddedResource` o `None` mediante el establecimiento de la propiedad [EnableDefaultCompileItems](msbuild-props.md#enabledefaultcompileitems), [EnableDefaultEmbeddedResourceItems](msbuild-props.md#enabledefaultembeddedresourceitems) o [EnableDefaultNoneItems](msbuild-props.md#enabledefaultnoneitems) en `false`:</span><span class="sxs-lookup"><span data-stu-id="1a74d-174">Selectively disable only `Compile`, `EmbeddedResource`, or `None` globs by setting the [EnableDefaultCompileItems](msbuild-props.md#enabledefaultcompileitems), [EnableDefaultEmbeddedResourceItems](msbuild-props.md#enabledefaultembeddedresourceitems), or [EnableDefaultNoneItems](msbuild-props.md#enabledefaultnoneitems) property to `false`:</span></span>

  ```xml
  <PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
    <EnableDefaultEmbeddedResourceItems>false</EnableDefaultEmbeddedResourceItems>
    <EnableDefaultNoneItems>false</EnableDefaultNoneItems>
  </PropertyGroup>
  ```

  <span data-ttu-id="1a74d-175">Si solo deshabilita los globs `Compile`, el Explorador de soluciones de Visual Studio sigue mostrando elementos \*.cs como parte del proyecto, incluidos como elementos `None`.</span><span class="sxs-lookup"><span data-stu-id="1a74d-175">If you only disable `Compile` globs, Solution Explorer in Visual Studio still shows \*.cs items as part of the project, included as `None` items.</span></span> <span data-ttu-id="1a74d-176">Para deshabilitar el glob `None` implícito, establezca `EnableDefaultNoneItems` en `false`.</span><span class="sxs-lookup"><span data-stu-id="1a74d-176">To disable the implicit `None` glob, set `EnableDefaultNoneItems` to `false` too.</span></span>

## <a name="implicit-package-references"></a><span data-ttu-id="1a74d-177">Referencias implícitas del paquete</span><span class="sxs-lookup"><span data-stu-id="1a74d-177">Implicit package references</span></span>

<span data-ttu-id="1a74d-178">Cuando el destino es .NET Core 1.0 - 2.2 o .NET Standard 1.0 - 2.0, el SDK de .NET agrega referencias implícitas a ciertos *metapaquetes*.</span><span class="sxs-lookup"><span data-stu-id="1a74d-178">When targeting .NET Core 1.0 - 2.2 or .NET Standard 1.0 - 2.0, the .NET SDK adds implicit references to certain *metapackages*.</span></span> <span data-ttu-id="1a74d-179">Un metapaquete es un paquete basado en la plataforma que consta únicamente de dependencias en otros paquetes.</span><span class="sxs-lookup"><span data-stu-id="1a74d-179">A metapackage is a framework-based package that consists only of dependencies on other packages.</span></span> <span data-ttu-id="1a74d-180">Se hace referencia implícitamente a los metapaquetes en función de las plataformas de destino especificadas en la propiedad [TargetFramework](msbuild-props.md#targetframework) o [TargetFrameworks](msbuild-props.md#targetframeworks) del archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="1a74d-180">Metapackages are implicitly referenced based on the target framework(s) specified in the [TargetFramework](msbuild-props.md#targetframework) or [TargetFrameworks](msbuild-props.md#targetframeworks) property of your project file.</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp2.1</TargetFramework>
</PropertyGroup>
```

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp2.1;net462</TargetFrameworks>
</PropertyGroup>
```

<span data-ttu-id="1a74d-181">Si es necesario, puede deshabilitar las referencias de paquete implícitas mediante la propiedad [DisableImplicitFrameworkReferences](msbuild-props.md#disableimplicitframeworkreferences) y agregar referencias explícitas solo a los marcos o paquetes que necesite.</span><span class="sxs-lookup"><span data-stu-id="1a74d-181">If needed, you can disable implicit package references using the [DisableImplicitFrameworkReferences](msbuild-props.md#disableimplicitframeworkreferences) property, and add explicit references to just the frameworks or packages you need.</span></span>

<span data-ttu-id="1a74d-182">Recomendaciones:</span><span class="sxs-lookup"><span data-stu-id="1a74d-182">Recommendations:</span></span>

- <span data-ttu-id="1a74d-183">Si el destino es .NET Framework, .NET Core 1.0 - 2.2 o .NET Standard 1.0 - 2.0, no incluya una referencia explícita a los metapaquetes `Microsoft.NETCore.App` o `NETStandard.Library` mediante un elemento `<PackageReference>` en el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="1a74d-183">When targeting .NET Framework, .NET Core 1.0 - 2.2, or .NET Standard 1.0 - 2.0, don't add an explicit reference to the `Microsoft.NETCore.App` or `NETStandard.Library` metapackages via a `<PackageReference>` item in your project file.</span></span> <span data-ttu-id="1a74d-184">En los proyectos de .NET Core 1.0 - 2.2 y .NET Standard 1.0 - 2.0 , se hace referencia implícitamente a estos metapaquetes.</span><span class="sxs-lookup"><span data-stu-id="1a74d-184">For .NET Core 1.0 - 2.2 and .NET Standard 1.0 - 2.0 projects, these metapackages are implicitly referenced.</span></span> <span data-ttu-id="1a74d-185">En los proyectos de .NET Framework, si se necesita alguna versión de `NETStandard.Library` al usar un paquete NuGet basado en .NET Standard, NuGet instala automáticamente esa versión.</span><span class="sxs-lookup"><span data-stu-id="1a74d-185">For .NET Framework projects, if any version of `NETStandard.Library` is needed when using a .NET Standard-based NuGet package, NuGet automatically installs that version.</span></span>
- <span data-ttu-id="1a74d-186">Si necesita una versión concreta del entorno de ejecución cuando el destino es .NET Core 1.0 - 2.2, use la propiedad `<RuntimeFrameworkVersion>` del proyecto (por ejemplo, `1.0.4`) en lugar de hacer referencia al metapaquete.</span><span class="sxs-lookup"><span data-stu-id="1a74d-186">If you need a specific version of the runtime when targeting .NET Core 1.0 - 2.2, use the `<RuntimeFrameworkVersion>` property in your project (for example, `1.0.4`) instead of referencing the metapackage.</span></span> <span data-ttu-id="1a74d-187">Por ejemplo, podría necesitar una versión específica de revisión del entorno de ejecución de LTS 1.0.0 si usa [implementaciones autocontenidas](../deploying/index.md#publish-self-contained).</span><span class="sxs-lookup"><span data-stu-id="1a74d-187">For example, you might need a specific patch version of 1.0.0 LTS runtime if you're using [self-contained deployments](../deploying/index.md#publish-self-contained).</span></span>
- <span data-ttu-id="1a74d-188">Si necesita una versión concreta del metapaquete `NETStandard.Library` cuando el destino es .NET Standard 1.0 - 2.0, puede usar la propiedad `<NetStandardImplicitPackageVersion>` y establecer la versión necesaria.</span><span class="sxs-lookup"><span data-stu-id="1a74d-188">If you need a specific version of the `NETStandard.Library` metapackage when targeting .NET Standard 1.0 - 2.0, you can use the `<NetStandardImplicitPackageVersion>` property and set the version you need.</span></span>

## <a name="build-events"></a><span data-ttu-id="1a74d-189">Eventos de compilación</span><span class="sxs-lookup"><span data-stu-id="1a74d-189">Build events</span></span>

<span data-ttu-id="1a74d-190">En los proyectos de estilo SDK, use un destino de MSBuild denominado `PreBuild` o `PostBuild`, y establezca la propiedad `BeforeTargets` para `PreBuild`, o bien la propiedad `AfterTargets` para `PostBuild`.</span><span class="sxs-lookup"><span data-stu-id="1a74d-190">In SDK-style projects, use an MSBuild target named `PreBuild` or `PostBuild` and set the `BeforeTargets` property for `PreBuild` or the `AfterTargets` property for `PostBuild`.</span></span>

```xml
<Target Name="PreBuild" BeforeTargets="PreBuildEvent">
    <Exec Command="&quot;$(ProjectDir)PreBuildEvent.bat&quot; &quot;$(ProjectDir)..\&quot; &quot;$(ProjectDir)&quot; &quot;$(TargetDir)&quot;" />
</Target>

<Target Name="PostBuild" AfterTargets="PostBuildEvent">
   <Exec Command="echo Output written to $(TargetDir)" />
</Target>
```

> [!NOTE]
>
> - <span data-ttu-id="1a74d-191">Puede usar cualquier nombre para los destinos de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="1a74d-191">You can use any name for the MSBuild targets.</span></span> <span data-ttu-id="1a74d-192">A pesar de ello, el IDE de Visual Studio reconoce los destinos `PreBuild` y `PostBuild`, por lo que, al usar esos nombres, puede editar los comandos en el IDE.</span><span class="sxs-lookup"><span data-stu-id="1a74d-192">However, the Visual Studio IDE recognizes `PreBuild` and `PostBuild` targets, so by using those names, you can edit the commands in the IDE.</span></span>
> - <span data-ttu-id="1a74d-193">No se recomiendan las propiedades `PreBuildEvent` ni `PostBuildEvent` en los proyectos de tipo SDK, ya que las macros como `$(ProjectDir)` no se resuelven.</span><span class="sxs-lookup"><span data-stu-id="1a74d-193">The properties `PreBuildEvent` and `PostBuildEvent` are not recommended in SDK-style projects, because macros such as `$(ProjectDir)` aren't resolved.</span></span> <span data-ttu-id="1a74d-194">Por ejemplo, no se admite el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="1a74d-194">For example, the following code is not supported:</span></span>
>
> ```xml
> <PropertyGroup>
>   <PreBuildEvent>"$(ProjectDir)PreBuildEvent.bat" "$(ProjectDir)..\" "$(ProjectDir)" "$(TargetDir)"</PreBuildEvent>
> </PropertyGroup>
> ```

## <a name="customize-the-build"></a><span data-ttu-id="1a74d-195">Personalización de la compilación</span><span class="sxs-lookup"><span data-stu-id="1a74d-195">Customize the build</span></span>

<span data-ttu-id="1a74d-196">Hay varias maneras de [personalizar una compilación](/visualstudio/msbuild/customize-your-build).</span><span class="sxs-lookup"><span data-stu-id="1a74d-196">There are various ways to [customize a build](/visualstudio/msbuild/customize-your-build).</span></span> <span data-ttu-id="1a74d-197">Es posible que quiera invalidar una propiedad y pasarla como argumento a un comando [msbuild](/visualstudio/msbuild/msbuild-command-line-reference) o [dotnet](../tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="1a74d-197">You may want to override a property by passing it as an argument to an [msbuild](/visualstudio/msbuild/msbuild-command-line-reference) or [dotnet](../tools/index.md) command.</span></span> <span data-ttu-id="1a74d-198">También puede agregar la propiedad al archivo del proyecto o a un archivo *Directory.Build.props*.</span><span class="sxs-lookup"><span data-stu-id="1a74d-198">You can also add the property to the project file or to a *Directory.Build.props* file.</span></span> <span data-ttu-id="1a74d-199">Para obtener una lista de propiedades útiles para los proyectos de .NET, consulte [Referencia de MSBuild para proyectos de SDK de .NET](msbuild-props.md).</span><span class="sxs-lookup"><span data-stu-id="1a74d-199">For a list of useful properties for .NET projects, see [MSBuild reference for .NET SDK projects](msbuild-props.md).</span></span>

### <a name="custom-targets"></a><span data-ttu-id="1a74d-200">Destinos personalizados</span><span class="sxs-lookup"><span data-stu-id="1a74d-200">Custom targets</span></span>

<span data-ttu-id="1a74d-201">Los proyectos de .NET pueden empaquetar propiedades y destinos de MSBuild personalizados para su uso en proyectos que consuman el paquete.</span><span class="sxs-lookup"><span data-stu-id="1a74d-201">.NET projects can package custom MSBuild targets and properties for use by projects that consume the package.</span></span> <span data-ttu-id="1a74d-202">Use este tipo de extensibilidad cuando quiera:</span><span class="sxs-lookup"><span data-stu-id="1a74d-202">Use this type of extensibility when you want to:</span></span>

- <span data-ttu-id="1a74d-203">Extender el proceso de compilación.</span><span class="sxs-lookup"><span data-stu-id="1a74d-203">Extend the build process.</span></span>
- <span data-ttu-id="1a74d-204">Acceder a artefactos del proceso de compilación, como los archivos generados.</span><span class="sxs-lookup"><span data-stu-id="1a74d-204">Access artifacts of the build process, such as generated files.</span></span>
- <span data-ttu-id="1a74d-205">Inspeccionar una configuración en la que se va a invocar la compilación.</span><span class="sxs-lookup"><span data-stu-id="1a74d-205">Inspect the configuration under which the build is invoked.</span></span>

<span data-ttu-id="1a74d-206">Para agregar propiedades o destinos de compilación personalizados, coloque los archivos con el formato `<package_id>.targets` o `<package_id>.props` (por ejemplo, `Contoso.Utility.UsefulStuff.targets`) en la carpeta *build* del proyecto.</span><span class="sxs-lookup"><span data-stu-id="1a74d-206">You add custom build targets or properties by placing files in the form `<package_id>.targets` or `<package_id>.props` (for example, `Contoso.Utility.UsefulStuff.targets`) in the *build* folder of the project.</span></span>

<span data-ttu-id="1a74d-207">El fragmento de código XML siguiente es de un archivo *.csproj* que indica al comando [`dotnet pack`](../tools/dotnet-pack.md) lo que debe empaquetar.</span><span class="sxs-lookup"><span data-stu-id="1a74d-207">The following XML is a snippet from a *.csproj* file that instructs the [`dotnet pack`](../tools/dotnet-pack.md) command what to package.</span></span> <span data-ttu-id="1a74d-208">El elemento `<ItemGroup Label="dotnet pack instructions">` coloca los archivos de destino en la carpeta *build* dentro del paquete.</span><span class="sxs-lookup"><span data-stu-id="1a74d-208">The `<ItemGroup Label="dotnet pack instructions">` element places the targets files into the *build* folder inside the package.</span></span> <span data-ttu-id="1a74d-209">El elemento `<Target Name="CollectRuntimeOutputs" BeforeTargets="_GetPackageFiles">` coloca los ensamblados y los archivos *.json* en la carpeta *build*.</span><span class="sxs-lookup"><span data-stu-id="1a74d-209">The `<Target Name="CollectRuntimeOutputs" BeforeTargets="_GetPackageFiles">` element places the assemblies and *.json* files into the *build* folder.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  ...
  <ItemGroup Label="dotnet pack instructions">
    <Content Include="build\*.targets">
      <Pack>true</Pack>
      <PackagePath>build\</PackagePath>
    </Content>
  </ItemGroup>
  <Target Name="CollectRuntimeOutputs" BeforeTargets="_GetPackageFiles">
    <!-- Collect these items inside a target that runs after build but before packaging. -->
    <ItemGroup>
      <Content Include="$(OutputPath)\*.dll;$(OutputPath)\*.json">
        <Pack>true</Pack>
        <PackagePath>build\</PackagePath>
      </Content>
    </ItemGroup>
  </Target>
  ...

</Project>
```

<span data-ttu-id="1a74d-210">Para consumir un destino personalizado en el proyecto, agregue un elemento `PackageReference` que apunte al paquete y su versión.</span><span class="sxs-lookup"><span data-stu-id="1a74d-210">To consume a custom target in your project, add a `PackageReference` element that points to the package and its version.</span></span> <span data-ttu-id="1a74d-211">A diferencia de las herramientas, el paquete de destinos personalizados se incluye en el cierre de dependencia del proyecto que lo usa.</span><span class="sxs-lookup"><span data-stu-id="1a74d-211">Unlike the tools, the custom targets package is included in the consuming project's dependency closure.</span></span>

<span data-ttu-id="1a74d-212">Puede configurar cómo se usa el destino personalizado.</span><span class="sxs-lookup"><span data-stu-id="1a74d-212">You can configure how to use the custom target.</span></span> <span data-ttu-id="1a74d-213">Como es un destino de MSBuild, puede depender de un destino concreto, ejecutarse después de otro destino o bien invocarse de forma manual mediante el comando `dotnet msbuild -t:<target-name>`.</span><span class="sxs-lookup"><span data-stu-id="1a74d-213">Since it's an MSBuild target, it can depend on a given target, run after another target, or be manually invoked by using the `dotnet msbuild -t:<target-name>` command.</span></span> <span data-ttu-id="1a74d-214">Pero para proporcionar una mejor experiencia de usuario, puede combinar las herramientas y los destinos personalizados por proyecto.</span><span class="sxs-lookup"><span data-stu-id="1a74d-214">However, to provide a better user experience, you can combine per-project tools and custom targets.</span></span> <span data-ttu-id="1a74d-215">En este escenario, la herramienta por proyecto acepta los parámetros necesarios y los traduce en la invocación de [`dotnet msbuild`](../tools/dotnet-msbuild.md) necesaria que ejecuta el destino.</span><span class="sxs-lookup"><span data-stu-id="1a74d-215">In this scenario, the per-project tool accepts whatever parameters are needed and translates that into the required [`dotnet msbuild`](../tools/dotnet-msbuild.md) invocation that executes the target.</span></span> <span data-ttu-id="1a74d-216">Puede ver una muestra de esta clase de sinergia en el [repositorio de ejemplos de MVP Summit 2016 Hackathon](https://github.com/dotnet/MVPSummitHackathon2016) del proyecto [`dotnet-packer`](https://github.com/dotnet/MVPSummitHackathon2016/tree/master/dotnet-packer).</span><span class="sxs-lookup"><span data-stu-id="1a74d-216">You can see a sample of this kind of synergy on the [MVP Summit 2016 Hackathon samples](https://github.com/dotnet/MVPSummitHackathon2016) repo in the [`dotnet-packer`](https://github.com/dotnet/MVPSummitHackathon2016/tree/master/dotnet-packer) project.</span></span>

## <a name="see-also"></a><span data-ttu-id="1a74d-217">Vea también</span><span class="sxs-lookup"><span data-stu-id="1a74d-217">See also</span></span>

- [<span data-ttu-id="1a74d-218">Instalación de .NET Core</span><span class="sxs-lookup"><span data-stu-id="1a74d-218">Install .NET Core</span></span>](../install/index.yml)
- [<span data-ttu-id="1a74d-219">Procedimiento para usar los SDK de proyecto de MSBuild</span><span class="sxs-lookup"><span data-stu-id="1a74d-219">How to use MSBuild project SDKs</span></span>](/visualstudio/msbuild/how-to-use-project-sdk)
- [<span data-ttu-id="1a74d-220">Empaquetado de destinos y propiedades de MSBuild personalizados con NuGet</span><span class="sxs-lookup"><span data-stu-id="1a74d-220">Package custom MSBuild targets and props with NuGet</span></span>](/nuget/create-packages/creating-a-package#include-msbuild-props-and-targets-in-a-package)
