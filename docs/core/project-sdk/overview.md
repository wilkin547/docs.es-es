---
title: Información general sobre el SDK de proyectos de .NET Core
description: Obtenga información sobre los SDK de proyectos de .NET Core.
ms.date: 02/02/2020
ms.topic: conceptual
ms.openlocfilehash: d0ac01dca31dffea482745126e00c34b1da20774
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389669"
---
# <a name="net-core-project-sdks"></a><span data-ttu-id="322ef-103">SDK de proyectos de .NET Core</span><span class="sxs-lookup"><span data-stu-id="322ef-103">.NET Core project SDKs</span></span>

<span data-ttu-id="322ef-104">Los proyectos de .NET Core están asociados a un kit de desarrollo de software (SDK).</span><span class="sxs-lookup"><span data-stu-id="322ef-104">.NET Core projects are associated with a software development kit (SDK).</span></span> <span data-ttu-id="322ef-105">Cada *SDK de proyecto* es un conjunto de [destinos de MSBuild](/visualstudio/msbuild/msbuild-targets) y [tareas](/visualstudio/msbuild/msbuild-tasks) asociadas que se encarga de compilar, empaquetar y publicar código.</span><span class="sxs-lookup"><span data-stu-id="322ef-105">Each *project SDK* is a set of MSBuild [targets](/visualstudio/msbuild/msbuild-targets) and associated [tasks](/visualstudio/msbuild/msbuild-tasks) that are responsible for compiling, packing, and publishing code.</span></span> <span data-ttu-id="322ef-106">Un proyecto que hace referencia a un SDK de proyecto en ocasiones se denomina *proyecto de estilo SDK*.</span><span class="sxs-lookup"><span data-stu-id="322ef-106">A project that references a project SDK is sometimes referred to as an *SDK-style project*.</span></span>

## <a name="available-sdks"></a><span data-ttu-id="322ef-107">SDK disponibles</span><span class="sxs-lookup"><span data-stu-id="322ef-107">Available SDKs</span></span>

<span data-ttu-id="322ef-108">Los siguientes SDK están disponibles para .NET Core:</span><span class="sxs-lookup"><span data-stu-id="322ef-108">The following SDKs are available for .NET Core:</span></span>

| <span data-ttu-id="322ef-109">ID</span><span class="sxs-lookup"><span data-stu-id="322ef-109">ID</span></span> | <span data-ttu-id="322ef-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="322ef-110">Description</span></span> | <span data-ttu-id="322ef-111">Repositorio</span><span class="sxs-lookup"><span data-stu-id="322ef-111">Repo</span></span>|
| - | - | - |
| `Microsoft.NET.Sdk` | <span data-ttu-id="322ef-112">El SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="322ef-112">The .NET Core SDK</span></span> | https://github.com/dotnet/sdk |
| `Microsoft.NET.Sdk.Web` | <span data-ttu-id="322ef-113">El [SDK web](/aspnet/core/razor-pages/web-sdk) de .NET Core</span><span class="sxs-lookup"><span data-stu-id="322ef-113">The .NET Core [Web SDK](/aspnet/core/razor-pages/web-sdk)</span></span> | https://github.com/aspnet/websdk |
| `Microsoft.NET.Sdk.Razor` | <span data-ttu-id="322ef-114">El [SDK de Razor](/aspnet/core/razor-pages/sdk) de .NET Core</span><span class="sxs-lookup"><span data-stu-id="322ef-114">The .NET Core [Razor SDK](/aspnet/core/razor-pages/sdk)</span></span> |
| `Microsoft.NET.Sdk.Worker` | <span data-ttu-id="322ef-115">El SDK del servicio de trabajo de .NET Core</span><span class="sxs-lookup"><span data-stu-id="322ef-115">The .NET Core Worker Service SDK</span></span> |
| `Microsoft.NET.Sdk.WindowsDesktop` | <span data-ttu-id="322ef-116">El SDK WinForms y WPF de .NET Core</span><span class="sxs-lookup"><span data-stu-id="322ef-116">The .NET Core WinForms and WPF SDK</span></span> |

<span data-ttu-id="322ef-117">El SDK de .NET Core es el SDK base de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="322ef-117">The .NET Core SDK is the base SDK for .NET Core.</span></span> <span data-ttu-id="322ef-118">Los otros SDK hacen referencia al SDK de .NET Core, y los proyectos asociados a los demás SDK disponen de todas las propiedades del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="322ef-118">The other SDKs reference the .NET Core SDK, and projects that are associated with the other SDKs have all the .NET Core SDK properties available to them.</span></span> <span data-ttu-id="322ef-119">El SDK Web, por ejemplo, depende de los SDK de .NET Core y de Razor.</span><span class="sxs-lookup"><span data-stu-id="322ef-119">The Web SDK, for example, depends on both the .NET Core SDK and the Razor SDK.</span></span>

<span data-ttu-id="322ef-120">También puede crear un SDK propio que se puede distribuir a través de NuGet.</span><span class="sxs-lookup"><span data-stu-id="322ef-120">You can also author your own SDK that can be distributed via NuGet.</span></span>

## <a name="project-files"></a><span data-ttu-id="322ef-121">Archivos de proyecto</span><span class="sxs-lookup"><span data-stu-id="322ef-121">Project files</span></span>

<span data-ttu-id="322ef-122">Los proyectos de .NET Core se basan en el formato [MSBuild](/visualstudio/msbuild/msbuild).</span><span class="sxs-lookup"><span data-stu-id="322ef-122">.NET Core projects are based on the [MSBuild](/visualstudio/msbuild/msbuild) format.</span></span> <span data-ttu-id="322ef-123">Los archivos de proyecto, que tienen extensiones como *.csproj* para los proyectos de C# y *.fsproj* para los de F#, están en formato XML.</span><span class="sxs-lookup"><span data-stu-id="322ef-123">Project files, which have extensions like *.csproj* for C# projects and *.fsproj* for F# projects, are in XML format.</span></span> <span data-ttu-id="322ef-124">El elemento raíz de un archivo de proyecto de MSBuild es [Project](/visualstudio/msbuild/project-element-msbuild).</span><span class="sxs-lookup"><span data-stu-id="322ef-124">The root element of an MSBuild project file is the [Project](/visualstudio/msbuild/project-element-msbuild) element.</span></span> <span data-ttu-id="322ef-125">El elemento `Project` tiene un atributo `Sdk` opcional que especifica qué SDK (y versión) se van a usar.</span><span class="sxs-lookup"><span data-stu-id="322ef-125">The `Project` element has an optional `Sdk` attribute that specifies which SDK (and version) to use.</span></span> <span data-ttu-id="322ef-126">Para usar las herramientas de .NET Core y compilar el código, establezca el atributo `Sdk` en uno de los identificadores de la tabla [SDK disponibles](#available-sdks).</span><span class="sxs-lookup"><span data-stu-id="322ef-126">To use the .NET Core tools and build your code, set the `Sdk` attribute to one of the IDs in the [Available SDKs](#available-sdks) table.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
</Project>
```

<span data-ttu-id="322ef-127">Para especificar un SDK que proviene de NuGet, incluya la versión al final del nombre, o bien especifique el nombre y la versión en el archivo *global.json*.</span><span class="sxs-lookup"><span data-stu-id="322ef-127">To specify an SDK that comes from NuGet, include the version at the end of the name, or specify the name and version in the *global.json* file.</span></span>

```xml
<Project Sdk="MSBuild.Sdk.Extras/2.0.54">
  ...
</Project>
```

<span data-ttu-id="322ef-128">Otra manera de especificar el SDK es mediante el elemento [Sdk](/visualstudio/msbuild/sdk-element-msbuild) de nivel superior:</span><span class="sxs-lookup"><span data-stu-id="322ef-128">Another way to specify the SDK is with the top-level [Sdk](/visualstudio/msbuild/sdk-element-msbuild) element:</span></span>

```xml
<Project>
  <Sdk Name="Microsoft.NET.Sdk" />
  ...
</Project>
```

<span data-ttu-id="322ef-129">Al hacer referencia a un SDK de una de estas formas, se simplifican enormemente los archivos de proyecto de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="322ef-129">Referencing an SDK in one of these ways greatly simplifies project files for .NET Core.</span></span> <span data-ttu-id="322ef-130">Durante la evaluación del proyecto, MSBuild agrega importaciones implícitas para `Sdk.props` en la parte superior del archivo del proyecto y para `Sdk.targets` en la inferior.</span><span class="sxs-lookup"><span data-stu-id="322ef-130">While evaluating the project, MSBuild adds implicit imports for `Sdk.props` at the top of the project file and `Sdk.targets` at the bottom.</span></span>

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
> <span data-ttu-id="322ef-131">En un equipo con Windows, los archivos *Sdk.props* y *Sdk.targets* se pueden encontrar en la carpeta *%ProgramFiles%\dotnet\sdk\\[versión]\Sdks\Microsoft.NET.Sdk\Sdk*.</span><span class="sxs-lookup"><span data-stu-id="322ef-131">On a Windows machine, the *Sdk.props* and *Sdk.targets* files can be found in the *%ProgramFiles%\dotnet\sdk\\[version]\Sdks\Microsoft.NET.Sdk\Sdk* folder.</span></span>

### <a name="preprocess-the-project-file"></a><span data-ttu-id="322ef-132">Procesamiento previo del archivo del proyecto</span><span class="sxs-lookup"><span data-stu-id="322ef-132">Preprocess the project file</span></span>

<span data-ttu-id="322ef-133">Puede ver el proyecto totalmente expandido como MSBuild lo ve después de incluir el SDK y sus destinos mediante el comando `dotnet msbuild -preprocess`.</span><span class="sxs-lookup"><span data-stu-id="322ef-133">You can see the fully expanded project as MSBuild sees it after the SDK and its targets are included by using the `dotnet msbuild -preprocess` command.</span></span> <span data-ttu-id="322ef-134">El conmutador [preprocess](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) del comando [`dotnet msbuild`](../tools/dotnet-msbuild.md) muestra qué archivos se han importado, sus orígenes y sus contribuciones a la compilación sin tener que compilar el proyecto realmente.</span><span class="sxs-lookup"><span data-stu-id="322ef-134">The [preprocess](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) switch of the [`dotnet msbuild`](../tools/dotnet-msbuild.md) command shows which files are imported, their sources, and their contributions to the build without actually building the project.</span></span>

<span data-ttu-id="322ef-135">Si el proyecto tiene varias plataformas de destino, para centrar los resultados del comando en una sola, debe especificarla como una propiedad de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="322ef-135">If the project has multiple target frameworks, focus the results of the command on only one framework by specifying it as an MSBuild property.</span></span> <span data-ttu-id="322ef-136">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="322ef-136">For example:</span></span>

`dotnet msbuild -property:TargetFramework=netcoreapp2.0 -preprocess:output.xml`

### <a name="default-compilation-includes"></a><span data-ttu-id="322ef-137">Inclusiones de compilación predeterminadas</span><span class="sxs-lookup"><span data-stu-id="322ef-137">Default compilation includes</span></span>

<span data-ttu-id="322ef-138">Las inclusiones y exclusiones predeterminadas para los elementos de compilación y los recursos insertados se definen en el SDK.</span><span class="sxs-lookup"><span data-stu-id="322ef-138">The default includes and excludes for compile items and embedded resources are defined in the SDK.</span></span> <span data-ttu-id="322ef-139">A diferencia de los proyectos de .NET Framework que no son de SDK, no es necesario especificar estos elementos en el archivo del proyecto, ya que los valores predeterminados cubren los casos de uso más comunes.</span><span class="sxs-lookup"><span data-stu-id="322ef-139">Unlike non-SDK .NET Framework projects, you don't need to specify these items in your project file, because the defaults cover most common use cases.</span></span> <span data-ttu-id="322ef-140">Esto da lugar a archivos del proyecto más pequeños y más fáciles de entender, así como de editar de forma manual si fuera necesario.</span><span class="sxs-lookup"><span data-stu-id="322ef-140">This leads to smaller project files that are easier to understand as well as edit by hand, if needed.</span></span>

<span data-ttu-id="322ef-141">En la tabla siguiente se muestra qué elementos y qué [globs](https://en.wikipedia.org/wiki/Glob_(programming)) se incluyen y excluyen en el SDK de .NET Core:</span><span class="sxs-lookup"><span data-stu-id="322ef-141">The following table shows which element and which [globs](https://en.wikipedia.org/wiki/Glob_(programming)) are included and excluded in the .NET Core SDK:</span></span>

| <span data-ttu-id="322ef-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="322ef-142">Element</span></span>           | <span data-ttu-id="322ef-143">Glob para incluir</span><span class="sxs-lookup"><span data-stu-id="322ef-143">Include glob</span></span>                              | <span data-ttu-id="322ef-144">Glob para excluir</span><span class="sxs-lookup"><span data-stu-id="322ef-144">Exclude glob</span></span>                                                  | <span data-ttu-id="322ef-145">Glob para quitar</span><span class="sxs-lookup"><span data-stu-id="322ef-145">Remove glob</span></span>              |
|-------------------|-------------------------------------------|---------------------------------------------------------------|--------------------------|
| <span data-ttu-id="322ef-146">Compile</span><span class="sxs-lookup"><span data-stu-id="322ef-146">Compile</span></span>           | <span data-ttu-id="322ef-147">\*\*/\*.cs (u otras extensiones de lenguaje)</span><span class="sxs-lookup"><span data-stu-id="322ef-147">\*\*/\*.cs (or other language extensions)</span></span> | <span data-ttu-id="322ef-148">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="322ef-148">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span></span>  | <span data-ttu-id="322ef-149">N/D</span><span class="sxs-lookup"><span data-stu-id="322ef-149">N/A</span></span>                      |
| <span data-ttu-id="322ef-150">EmbeddedResource</span><span class="sxs-lookup"><span data-stu-id="322ef-150">EmbeddedResource</span></span>  | <span data-ttu-id="322ef-151">\*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="322ef-151">\*\*/\*.resx</span></span>                              | <span data-ttu-id="322ef-152">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="322ef-152">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="322ef-153">N/D</span><span class="sxs-lookup"><span data-stu-id="322ef-153">N/A</span></span>                      |
| <span data-ttu-id="322ef-154">None</span><span class="sxs-lookup"><span data-stu-id="322ef-154">None</span></span>              | \*\*/\*                                   | <span data-ttu-id="322ef-155">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="322ef-155">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="322ef-156">\*\*/\*.cs; \*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="322ef-156">\*\*/\*.cs; \*\*/\*.resx</span></span> |

> [!NOTE]
> <span data-ttu-id="322ef-157">De forma predeterminada, las carpetas `./bin` y `./obj` (representadas por las propiedades de MSBuild `$(BaseOutputPath)` y `$(BaseIntermediateOutputPath)`) se excluyen de los globs.</span><span class="sxs-lookup"><span data-stu-id="322ef-157">The `./bin` and `./obj` folders, which are represented by the `$(BaseOutputPath)` and `$(BaseIntermediateOutputPath)` MSBuild properties, are excluded from the globs by default.</span></span> <span data-ttu-id="322ef-158">Las exclusiones se representan por medio de la propiedad `$(DefaultItemExcludes)`.</span><span class="sxs-lookup"><span data-stu-id="322ef-158">Excludes are represented by the property `$(DefaultItemExcludes)`.</span></span>

<span data-ttu-id="322ef-159">Si define de forma explícita estos elementos en el archivo del proyecto, es probable que reciba el error siguiente:</span><span class="sxs-lookup"><span data-stu-id="322ef-159">If you explicitly define these items in your project file, you're likely to get the following error:</span></span>

<span data-ttu-id="322ef-160">**Se han incluido elementos de compilación duplicados. El SDK de .NET incluye elementos de compilación del directorio del proyecto de forma predeterminada. Puede quitar estos elementos del archivo del proyecto, o bien establecer la propiedad "EnableDefaultCompileItems" en "false" si quiere incluirlos de forma explícita en el archivo del proyecto.**</span><span class="sxs-lookup"><span data-stu-id="322ef-160">**Duplicate Compile items were included. The .NET SDK includes Compile items from your project directory by default. You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file.**</span></span>

<span data-ttu-id="322ef-161">Para resolver el error, quite los elementos `Compile` explícitos que coincidan con los implícitos enumerados en la tabla anterior, o bien establezca la propiedad `EnableDefaultCompileItems` en `false` para deshabilitar la inclusión implícita:</span><span class="sxs-lookup"><span data-stu-id="322ef-161">To resolve the error, either remove the explicit `Compile` items that match the implicit ones listed on the previous table, or set the `EnableDefaultCompileItems` property to `false`, which disables implicit inclusion:</span></span>

```xml
<PropertyGroup>
  <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```

<span data-ttu-id="322ef-162">Si, por ejemplo, quiere especificar que algunos archivos se publiquen con la aplicación, puede seguir usando los mecanismos de MSBuild conocidos para ello, por ejemplo, el elemento `Content`.</span><span class="sxs-lookup"><span data-stu-id="322ef-162">If you want to specify, for example, some files to get published with your app, you can still use the known MSBuild mechanisms for that, for example, the `Content` element.</span></span>

<span data-ttu-id="322ef-163">`EnableDefaultCompileItems` solo deshabilita los globs `Compile`, pero no afecta a otros, como el glob `None` implícito, que también se aplica a los elementos \*.cs.</span><span class="sxs-lookup"><span data-stu-id="322ef-163">`EnableDefaultCompileItems` only disables `Compile` globs but doesn't affect other globs, like the implicit `None` glob that also applies to \*.cs items.</span></span> <span data-ttu-id="322ef-164">Por eso, en el Explorador de soluciones de Visual Studio se muestran los elementos \*.cs como parte del proyecto, incluidos como elementos `None`.</span><span class="sxs-lookup"><span data-stu-id="322ef-164">Because of that, Solution Explorer in Visual Studio shows \*.cs items as part of the project, included as `None` items.</span></span> <span data-ttu-id="322ef-165">Para deshabilitar el glob `None` implícito, establezca `EnableDefaultNoneItems` en `false`:</span><span class="sxs-lookup"><span data-stu-id="322ef-165">To disable the implicit `None` glob, set `EnableDefaultNoneItems` to `false`:</span></span>

```xml
<PropertyGroup>
  <EnableDefaultNoneItems>false</EnableDefaultNoneItems>
</PropertyGroup>
```

<span data-ttu-id="322ef-166">Para deshabilitar *todos* los globs implícitos, establezca la propiedad `EnableDefaultItems` en `false`:</span><span class="sxs-lookup"><span data-stu-id="322ef-166">To disable *all* implicit globs, set the `EnableDefaultItems` property to `false`:</span></span>

```xml
<PropertyGroup>
  <EnableDefaultItems>false</EnableDefaultItems>
</PropertyGroup>
```

## <a name="customize-the-build"></a><span data-ttu-id="322ef-167">Personalización de la compilación</span><span class="sxs-lookup"><span data-stu-id="322ef-167">Customize the build</span></span>

<span data-ttu-id="322ef-168">Hay varias maneras de [personalizar una compilación](/visualstudio/msbuild/customize-your-build).</span><span class="sxs-lookup"><span data-stu-id="322ef-168">There are various ways to [customize a build](/visualstudio/msbuild/customize-your-build).</span></span> <span data-ttu-id="322ef-169">Es posible que quiera invalidar una propiedad y pasarla como argumento a un comando [msbuild](/visualstudio/msbuild/msbuild-command-line-reference) o [dotnet](../tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="322ef-169">You may want to override a property by passing it as an argument to an [msbuild](/visualstudio/msbuild/msbuild-command-line-reference) or [dotnet](../tools/index.md) command.</span></span> <span data-ttu-id="322ef-170">También puede agregar la propiedad al archivo del proyecto o a un archivo *Directory.Build.props*.</span><span class="sxs-lookup"><span data-stu-id="322ef-170">You can also add the property to the project file or to a *Directory.Build.props* file.</span></span> <span data-ttu-id="322ef-171">Para obtener una lista de propiedades útiles para los proyectos de .NET Core, vea [Propiedades de MSBuild para proyectos de SDK de .NET Core](msbuild-props.md).</span><span class="sxs-lookup"><span data-stu-id="322ef-171">For a list of useful properties for .NET Core projects, see [MSBuild properties for .NET Core SDK projects](msbuild-props.md).</span></span>

### <a name="custom-targets"></a><span data-ttu-id="322ef-172">Destinos personalizados</span><span class="sxs-lookup"><span data-stu-id="322ef-172">Custom targets</span></span>

<span data-ttu-id="322ef-173">Los proyectos de .NET Core pueden empaquetar propiedades y destinos de MSBuild personalizados para su uso en proyectos que consuman el paquete.</span><span class="sxs-lookup"><span data-stu-id="322ef-173">.NET Core projects can package custom MSBuild targets and properties for use by projects that consume the package.</span></span> <span data-ttu-id="322ef-174">Use este tipo de extensibilidad cuando quiera:</span><span class="sxs-lookup"><span data-stu-id="322ef-174">Use this type of extensibility when you want to:</span></span>

- <span data-ttu-id="322ef-175">Extender el proceso de compilación.</span><span class="sxs-lookup"><span data-stu-id="322ef-175">Extend the build process.</span></span>
- <span data-ttu-id="322ef-176">Acceder a artefactos del proceso de compilación, como los archivos generados.</span><span class="sxs-lookup"><span data-stu-id="322ef-176">Access artifacts of the build process, such as generated files.</span></span>
- <span data-ttu-id="322ef-177">Inspeccionar una configuración en la que se va a invocar la compilación.</span><span class="sxs-lookup"><span data-stu-id="322ef-177">Inspect the configuration under which the build is invoked.</span></span>

<span data-ttu-id="322ef-178">Para agregar propiedades o destinos de compilación personalizados, coloque los archivos con el formato `<package_id>.targets` o `<package_id>.props` (por ejemplo, `Contoso.Utility.UsefulStuff.targets`) en la carpeta *build* del proyecto.</span><span class="sxs-lookup"><span data-stu-id="322ef-178">You add custom build targets or properties by placing files in the form `<package_id>.targets` or `<package_id>.props` (for example, `Contoso.Utility.UsefulStuff.targets`) in the *build* folder of the project.</span></span>

<span data-ttu-id="322ef-179">El fragmento de código XML siguiente es de un archivo *.csproj* que indica al comando [`dotnet pack`](../tools/dotnet-pack.md) lo que debe empaquetar.</span><span class="sxs-lookup"><span data-stu-id="322ef-179">The following XML is a snippet from a *.csproj* file that instructs the [`dotnet pack`](../tools/dotnet-pack.md) command what to package.</span></span> <span data-ttu-id="322ef-180">El elemento `<ItemGroup Label="dotnet pack instructions">` coloca los archivos de destino en la carpeta *build* dentro del paquete.</span><span class="sxs-lookup"><span data-stu-id="322ef-180">The `<ItemGroup Label="dotnet pack instructions">` element places the targets files into the *build* folder inside the package.</span></span> <span data-ttu-id="322ef-181">El elemento `<Target Name="CollectRuntimeOutputs" BeforeTargets="_GetPackageFiles">` coloca los ensamblados y los archivos *.json* en la carpeta *build*.</span><span class="sxs-lookup"><span data-stu-id="322ef-181">The `<Target Name="CollectRuntimeOutputs" BeforeTargets="_GetPackageFiles">` element places the assemblies and *.json* files into the *build* folder.</span></span>

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

<span data-ttu-id="322ef-182">Para consumir un destino personalizado en el proyecto, agregue un elemento `PackageReference` que apunte al paquete y su versión.</span><span class="sxs-lookup"><span data-stu-id="322ef-182">To consume a custom target in your project, add a `PackageReference` element that points to the package and its version.</span></span> <span data-ttu-id="322ef-183">A diferencia de las herramientas, el paquete de destinos personalizados se incluye en el cierre de dependencia del proyecto que lo usa.</span><span class="sxs-lookup"><span data-stu-id="322ef-183">Unlike the tools, the custom targets package is included in the consuming project's dependency closure.</span></span>

<span data-ttu-id="322ef-184">Puede configurar cómo se usa el destino personalizado.</span><span class="sxs-lookup"><span data-stu-id="322ef-184">You can configure how to use the custom target.</span></span> <span data-ttu-id="322ef-185">Como es un destino de MSBuild, puede depender de un destino concreto, ejecutarse después de otro destino o bien invocarse de forma manual mediante el comando `dotnet msbuild -t:<target-name>`.</span><span class="sxs-lookup"><span data-stu-id="322ef-185">Since it's an MSBuild target, it can depend on a given target, run after another target, or be manually invoked by using the `dotnet msbuild -t:<target-name>` command.</span></span> <span data-ttu-id="322ef-186">Pero para proporcionar una mejor experiencia de usuario, puede combinar las herramientas y los destinos personalizados por proyecto.</span><span class="sxs-lookup"><span data-stu-id="322ef-186">However, to provide a better user experience, you can combine per-project tools and custom targets.</span></span> <span data-ttu-id="322ef-187">En este escenario, la herramienta por proyecto acepta los parámetros necesarios y los traduce en la invocación de [`dotnet msbuild`](../tools/dotnet-msbuild.md) necesaria que ejecuta el destino.</span><span class="sxs-lookup"><span data-stu-id="322ef-187">In this scenario, the per-project tool accepts whatever parameters are needed and translates that into the required [`dotnet msbuild`](../tools/dotnet-msbuild.md) invocation that executes the target.</span></span> <span data-ttu-id="322ef-188">Puede ver una muestra de esta clase de sinergia en el [repositorio de ejemplos de MVP Summit 2016 Hackathon](https://github.com/dotnet/MVPSummitHackathon2016) del proyecto [`dotnet-packer`](https://github.com/dotnet/MVPSummitHackathon2016/tree/master/dotnet-packer).</span><span class="sxs-lookup"><span data-stu-id="322ef-188">You can see a sample of this kind of synergy on the [MVP Summit 2016 Hackathon samples](https://github.com/dotnet/MVPSummitHackathon2016) repo in the [`dotnet-packer`](https://github.com/dotnet/MVPSummitHackathon2016/tree/master/dotnet-packer) project.</span></span>

## <a name="see-also"></a><span data-ttu-id="322ef-189">Vea también</span><span class="sxs-lookup"><span data-stu-id="322ef-189">See also</span></span>

- [<span data-ttu-id="322ef-190">Instalación de .NET Core</span><span class="sxs-lookup"><span data-stu-id="322ef-190">Install .NET Core</span></span>](../install/index.md)
- [<span data-ttu-id="322ef-191">Procedimiento para usar los SDK de proyecto de MSBuild</span><span class="sxs-lookup"><span data-stu-id="322ef-191">How to use MSBuild project SDKs</span></span>](/visualstudio/msbuild/how-to-use-project-sdk)
- [<span data-ttu-id="322ef-192">Empaquetado de destinos y propiedades de MSBuild personalizados con NuGet</span><span class="sxs-lookup"><span data-stu-id="322ef-192">Package custom MSBuild targets and props with NuGet</span></span>](/nuget/create-packages/creating-a-package#include-msbuild-props-and-targets-in-a-package)
