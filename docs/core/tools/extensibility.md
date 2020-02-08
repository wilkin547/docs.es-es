---
title: Modelo de extensibilidad de la CLI de .NET Core
description: Descubra cómo puede extender la CLI de .NET Core.
ms.date: 04/12/2017
ms.openlocfilehash: 74da895fb3a3f6c77640a2b9a64acdb2894a954b
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920527"
---
# <a name="net-core-cli-extensibility-model"></a><span data-ttu-id="436f7-103">Modelo de extensibilidad de la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="436f7-103">.NET Core CLI extensibility model</span></span>

<span data-ttu-id="436f7-104">En este artículo se tratan las distintas formas en que se puede extender la CLI de .NET Core y se explican los escenarios que controlan cada una de ellas.</span><span class="sxs-lookup"><span data-stu-id="436f7-104">This article covers the different ways you can extend the .NET Core CLI and explain the scenarios that drive each one of them.</span></span>
<span data-ttu-id="436f7-105">Verá cómo usar las herramientas así como la manera de crear los diferentes tipos de herramientas.</span><span class="sxs-lookup"><span data-stu-id="436f7-105">You'll see how to consume the tools as well as how to build the different types of tools.</span></span>

## <a name="how-to-extend-the-cli"></a><span data-ttu-id="436f7-106">Extensión de la CLI</span><span class="sxs-lookup"><span data-stu-id="436f7-106">How to extend the CLI</span></span>
<span data-ttu-id="436f7-107">La CLI se puede extender de tres maneras principales:</span><span class="sxs-lookup"><span data-stu-id="436f7-107">The CLI can be extended in three main ways:</span></span>

1. [<span data-ttu-id="436f7-108">A través de paquetes NuGet por proyecto</span><span class="sxs-lookup"><span data-stu-id="436f7-108">Via NuGet packages on a per-project basis</span></span>](#per-project-based-extensibility)

   <span data-ttu-id="436f7-109">Las herramientas por proyecto se incluyen en el contexto del proyecto, pero permiten la instalación fácil mediante la restauración.</span><span class="sxs-lookup"><span data-stu-id="436f7-109">Per-project tools are contained within the project's context, but they allow easy installation through restoration.</span></span>

2. [<span data-ttu-id="436f7-110">A través de paquetes NuGet con destinos personalizados</span><span class="sxs-lookup"><span data-stu-id="436f7-110">Via NuGet packages with custom targets</span></span>](#custom-targets)

   <span data-ttu-id="436f7-111">Los destinos personalizados permiten extender fácilmente el proceso de compilación con tareas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="436f7-111">Custom targets allow you to easily extend the build process with custom tasks.</span></span>

3. [<span data-ttu-id="436f7-112">A través de la RUTA DE ACCESO del sistema</span><span class="sxs-lookup"><span data-stu-id="436f7-112">Via the system's PATH</span></span>](#path-based-extensibility)

   <span data-ttu-id="436f7-113">Las herramientas basadas en la RUTA DE ACCESO son buenas para herramientas entre proyectos generales que se pueden usar en una sola máquina.</span><span class="sxs-lookup"><span data-stu-id="436f7-113">PATH-based tools are good for general, cross-project tools that are usable on a single machine.</span></span>

<span data-ttu-id="436f7-114">Los tres mecanismos de extensibilidad descritos anteriormente no son exclusivos.</span><span class="sxs-lookup"><span data-stu-id="436f7-114">The three extensibility mechanisms outlined above are not exclusive.</span></span> <span data-ttu-id="436f7-115">Puede usar uno, o todos, o una combinación de ellos.</span><span class="sxs-lookup"><span data-stu-id="436f7-115">You can use one, or all, or a combination of them.</span></span> <span data-ttu-id="436f7-116">La selección de uno u otro depende en gran medida del objetivo que intenta alcanzar con su extensión.</span><span class="sxs-lookup"><span data-stu-id="436f7-116">Which one to pick depends largely on the goal you are trying to achieve with your extension.</span></span>

## <a name="per-project-based-extensibility"></a><span data-ttu-id="436f7-117">Extensibilidad por proyecto</span><span class="sxs-lookup"><span data-stu-id="436f7-117">Per-project based extensibility</span></span>
<span data-ttu-id="436f7-118">Las herramientas por proyecto son [implementaciones dependientes del marco](../deploying/index.md#framework-dependent-deployments-fdd) que se distribuyen como paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="436f7-118">Per-project tools are [framework-dependent deployments](../deploying/index.md#framework-dependent-deployments-fdd) that are distributed as NuGet packages.</span></span> <span data-ttu-id="436f7-119">Las herramientas solo están disponibles en el contexto del proyecto que les hace referencia y para el que se restauran.</span><span class="sxs-lookup"><span data-stu-id="436f7-119">Tools are only available in the context of the project that references them and for which they are restored.</span></span> <span data-ttu-id="436f7-120">La invocación fuera del contexto del proyecto (por ejemplo, fuera del directorio que contiene el proyecto) producirá un error porque el comando no puede encontrarse.</span><span class="sxs-lookup"><span data-stu-id="436f7-120">Invocation outside of the context of the project (for example, outside of the directory that contains the project) will fail because the command cannot be found.</span></span>

<span data-ttu-id="436f7-121">Estas herramientas son perfectas para servidores de compilación, dado que no se necesita nada fuera del archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="436f7-121">These tools are perfect for build servers, since nothing outside of the project file is needed.</span></span> <span data-ttu-id="436f7-122">El proceso de compilación ejecuta la restauración para el proyecto que se compila y hay herramientas disponibles.</span><span class="sxs-lookup"><span data-stu-id="436f7-122">The build process runs restore for the project it builds and tools will be available.</span></span> <span data-ttu-id="436f7-123">Los proyectos de lenguajes, como F#, también están en esta categoría ya que cada proyecto solo se puede escribir en un lenguaje específico.</span><span class="sxs-lookup"><span data-stu-id="436f7-123">Language projects, such as F#, are also in this category since each project can only be written in one specific language.</span></span>

<span data-ttu-id="436f7-124">Finalmente, este modelo de extensibilidad proporciona compatibilidad con la creación de herramientas que necesitan acceso a la salida compilada del proyecto.</span><span class="sxs-lookup"><span data-stu-id="436f7-124">Finally, this extensibility model provides support for creation of tools that need access to the built output of the project.</span></span> <span data-ttu-id="436f7-125">Por ejemplo, varias herramientas de vista de Razor de aplicaciones [ASP.NET](https://www.asp.net/) MVC se incluyen dentro de esta categoría.</span><span class="sxs-lookup"><span data-stu-id="436f7-125">For instance, various Razor view tools in [ASP.NET](https://www.asp.net/) MVC applications fall into this category.</span></span>

### <a name="consuming-per-project-tools"></a><span data-ttu-id="436f7-126">Consumo de herramientas por proyecto</span><span class="sxs-lookup"><span data-stu-id="436f7-126">Consuming per-project tools</span></span>
<span data-ttu-id="436f7-127">Para consumir estas herramientas es necesario agregar un elemento `<DotNetCliToolReference>` a su archivo del proyecto para cada herramienta que quiera usar.</span><span class="sxs-lookup"><span data-stu-id="436f7-127">Consuming these tools requires you to add a `<DotNetCliToolReference>` element to your project file for each tool you want to use.</span></span> <span data-ttu-id="436f7-128">Dentro del elemento `<DotNetCliToolReference>`, se hace referencia al paquete en el que reside la herramienta y se especifica la versión necesaria.</span><span class="sxs-lookup"><span data-stu-id="436f7-128">Inside the `<DotNetCliToolReference>` element, you reference the package in which the tool resides and specify the version you need.</span></span> <span data-ttu-id="436f7-129">Después de ejecutar [`dotnet restore`](dotnet-restore.md), se restauran la herramienta y sus dependencias.</span><span class="sxs-lookup"><span data-stu-id="436f7-129">After running [`dotnet restore`](dotnet-restore.md), the tool and its dependencies are restored.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="436f7-130">Para las herramientas que necesitan cargar la salida de compilación del proyecto para su ejecución, hay normalmente otra dependencia que aparece en las dependencias normales del archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="436f7-130">For tools that need to load the build output of the project for execution, there is usually another dependency which is listed under the regular dependencies in the project file.</span></span> <span data-ttu-id="436f7-131">Como la CLI usa MSBuild como motor de compilación, recomendamos que estas partes de la herramienta se escriban como [destinos](/visualstudio/msbuild/msbuild-targets) y [tareas](/visualstudio/msbuild/msbuild-tasks) de MSBuild personalizados, ya que pueden formar parte del proceso de compilación general.</span><span class="sxs-lookup"><span data-stu-id="436f7-131">Since CLI uses MSBuild as its build engine, we recommend that these parts of the tool be written as custom MSBuild [targets](/visualstudio/msbuild/msbuild-targets) and [tasks](/visualstudio/msbuild/msbuild-tasks), since they can then take part in the overall build process.</span></span> <span data-ttu-id="436f7-132">Además, pueden obtener fácilmente todos y cada uno de los datos que se producen mediante la compilación, como la ubicación de los archivos de salida, la configuración actual que se compila, etc.</span><span class="sxs-lookup"><span data-stu-id="436f7-132">Also, they can get any and all data easily that is produced via the build, such as the location of the output files, the current configuration being built, and so on.</span></span> <span data-ttu-id="436f7-133">Toda esta información se convierte en un conjunto de propiedades de MSBuild que se puede leer desde cualquier destino.</span><span class="sxs-lookup"><span data-stu-id="436f7-133">All this information becomes a set of MSBuild properties that can be read from any target.</span></span> <span data-ttu-id="436f7-134">Más adelante en este documento puede ver cómo agregar un destino personalizado mediante NuGet.</span><span class="sxs-lookup"><span data-stu-id="436f7-134">You can see how to add a custom target using NuGet later in this document.</span></span>

<span data-ttu-id="436f7-135">Vamos a ver un ejemplo de cómo agregar una herramienta sencilla tools-only a un proyecto sencillo.</span><span class="sxs-lookup"><span data-stu-id="436f7-135">Let's review an example of adding a simple tools-only tool to a simple project.</span></span> <span data-ttu-id="436f7-136">Dado un comando de ejemplo llamado `dotnet-api-search` que le permite examinar los paquetes de NuGet hasta encontrar la API especificada, este es un archivo de proyecto de la aplicación de consola que usa esa herramienta:</span><span class="sxs-lookup"><span data-stu-id="436f7-136">Given an example command called `dotnet-api-search` that allows you to search through the NuGet packages for the specified API, here is a console application's project file that uses that tool:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
  </PropertyGroup>

  <!-- The tools reference -->
  <ItemGroup>
    <DotNetCliToolReference Include="dotnet-api-search" Version="1.0.0" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="436f7-137">El elemento `<DotNetCliToolReference>` está estructurado de forma similar al elemento `<PackageReference>`.</span><span class="sxs-lookup"><span data-stu-id="436f7-137">The `<DotNetCliToolReference>` element is structured in a similar way as the `<PackageReference>` element.</span></span> <span data-ttu-id="436f7-138">Necesita el identificador del paquete que contiene la herramienta y su versión para que pueda realizarse la restauración.</span><span class="sxs-lookup"><span data-stu-id="436f7-138">It needs the package ID of the package containing the tool and its version to be able to restore.</span></span>

### <a name="building-tools"></a><span data-ttu-id="436f7-139">Compilación de herramientas</span><span class="sxs-lookup"><span data-stu-id="436f7-139">Building tools</span></span>
<span data-ttu-id="436f7-140">Como se ha mencionado, las herramientas son simples aplicaciones de consola portátiles.</span><span class="sxs-lookup"><span data-stu-id="436f7-140">As mentioned, tools are just portable console applications.</span></span> <span data-ttu-id="436f7-141">Compila herramientas como lo haría en cualquier otra aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="436f7-141">You build tools as you would build any other console application.</span></span>
<span data-ttu-id="436f7-142">Después de compilarla, puede usar el comando [`dotnet pack`](dotnet-pack.md) para crear un paquete de NuGet (archivo .nupkg) que contiene el código e información sobre sus dependencias, entre otros.</span><span class="sxs-lookup"><span data-stu-id="436f7-142">After you build it, you use the [`dotnet pack`](dotnet-pack.md) command to create a NuGet package (.nupkg file) that contains your code, information about its dependencies, and so on.</span></span> <span data-ttu-id="436f7-143">Puede proporcionar cualquier nombre al paquete, pero la aplicación que contiene, el archivo binario de la herramienta real, debe respetar las convenciones de `dotnet-<command>` para que `dotnet` pueda invocarlo.</span><span class="sxs-lookup"><span data-stu-id="436f7-143">You can give any name to the package, but the application inside, the actual tool binary, has to conform to the convention of `dotnet-<command>` in order for `dotnet` to be able to invoke it.</span></span>

> [!NOTE]
> <span data-ttu-id="436f7-144">En las versiones anteriores a RC3 de las herramientas de línea de comandos de .NET Core, el comando `dotnet pack` tenía un error que provocaba que *.runtimeconfig.json* no se empaquetase con la herramienta.</span><span class="sxs-lookup"><span data-stu-id="436f7-144">In pre-RC3 versions of the .NET Core command-line tools, the `dotnet pack` command had a bug that caused the *.runtimeconfig.json* to not be packed with the tool.</span></span> <span data-ttu-id="436f7-145">La falta de dicho archivo provoca errores en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="436f7-145">Lacking that file results in errors at runtime.</span></span> <span data-ttu-id="436f7-146">Si se produce este comportamiento, asegúrese de actualizar a las últimas herramientas y pruebe `dotnet pack` nuevo.</span><span class="sxs-lookup"><span data-stu-id="436f7-146">If you encounter this behavior, be sure to update to the latest tooling and try the `dotnet pack` again.</span></span>

<span data-ttu-id="436f7-147">Como las herramientas son aplicaciones portátiles, el usuario que las consume debe tener la versión de las bibliotecas .NET Core con la que se ha compilado la herramienta para poder ejecutar esta.</span><span class="sxs-lookup"><span data-stu-id="436f7-147">Since tools are portable applications, the user consuming the tool must have the version of the .NET Core libraries that the tool was built against in order to run the tool.</span></span> <span data-ttu-id="436f7-148">Cualquier otra dependencia que use la herramienta y que no esté contenida en las bibliotecas .NET Core se restauran y colocan en la caché de NuGet.</span><span class="sxs-lookup"><span data-stu-id="436f7-148">Any other dependency that the tool uses and that is not contained within the .NET Core libraries is restored and placed in the NuGet cache.</span></span> <span data-ttu-id="436f7-149">Por lo tanto, la herramienta entera se ejecuta con los ensamblados de las bibliotecas .NET Core, así como los ensamblados de la caché de NuGet.</span><span class="sxs-lookup"><span data-stu-id="436f7-149">The entire tool is, therefore, run using the assemblies from the .NET Core libraries as well as assemblies from the NuGet cache.</span></span>

<span data-ttu-id="436f7-150">Estas clases de herramientas tienen un gráfico de dependencias que es completamente independiente del gráfico de dependencias del proyecto que los usa.</span><span class="sxs-lookup"><span data-stu-id="436f7-150">These kinds of tools have a dependency graph that is completely separate from the dependency graph of the project that uses them.</span></span> <span data-ttu-id="436f7-151">El proceso de restauración restaura primero las dependencias del proyecto y, después, cada una de las herramientas y sus dependencias.</span><span class="sxs-lookup"><span data-stu-id="436f7-151">The restore process first restores the project's dependencies and then restores each of the tools and their dependencies.</span></span>

<span data-ttu-id="436f7-152">Puede encontrar más ejemplos y diferentes combinaciones de esto en el [repositorio de la CLI de .NET Core](https://github.com/dotnet/cli/tree/release/2.1/TestAssets/TestProjects).</span><span class="sxs-lookup"><span data-stu-id="436f7-152">You can find richer examples and different combinations of this in the [.NET Core CLI repo](https://github.com/dotnet/cli/tree/release/2.1/TestAssets/TestProjects).</span></span>
<span data-ttu-id="436f7-153">También puede ver las [herramientas de implementación usadas](https://github.com/dotnet/cli/tree/release/2.1/TestAssets/TestPackages) en el mismo repositorio.</span><span class="sxs-lookup"><span data-stu-id="436f7-153">You can also see the [implementation of tools used](https://github.com/dotnet/cli/tree/release/2.1/TestAssets/TestPackages) in the same repo.</span></span>

## <a name="custom-targets"></a><span data-ttu-id="436f7-154">Destinos personalizados</span><span class="sxs-lookup"><span data-stu-id="436f7-154">Custom targets</span></span>

<span data-ttu-id="436f7-155">NuGet tiene la capacidad de [empaquetar archivos de propiedades y destinos de MSBuild personalizados](/nuget/create-packages/creating-a-package#include-msbuild-props-and-targets-in-a-package).</span><span class="sxs-lookup"><span data-stu-id="436f7-155">NuGet has the capability to [package custom MSBuild targets and props files](/nuget/create-packages/creating-a-package#include-msbuild-props-and-targets-in-a-package).</span></span> <span data-ttu-id="436f7-156">Con el paso de .NET Core para usar MSBuild, el mismo mecanismo de extensibilidad se aplica ahora en proyectos de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="436f7-156">With the move of the .NET Core to use MSBuild, the same mechanism of extensibility now applies to .NET Core projects.</span></span> <span data-ttu-id="436f7-157">Este tipo de extensibilidad se usaría cuando quisiera extender el proceso de compilación o quisiera acceder a alguno de los artefactos de dicho proceso, como los archivos generados, o si quiere inspeccionar la configuración bajo la que se invoca la compilación, etc.</span><span class="sxs-lookup"><span data-stu-id="436f7-157">You would use this type of extensibility when you want to extend the build process, or when you want to access any of the artifacts in the build process, such as generated files, or you want to inspect the configuration under which the build is invoked, and so on.</span></span>

<span data-ttu-id="436f7-158">En el ejemplo siguiente, puede ver el archivo del proyecto de destino con la sintaxis `csproj`.</span><span class="sxs-lookup"><span data-stu-id="436f7-158">In the following example, you can see the target's project file using the `csproj` syntax.</span></span> <span data-ttu-id="436f7-159">Esto indica al comando [`dotnet pack`](dotnet-pack.md) qué empaquetar, colocando los archivos de destinos así como los ensamblados en la carpeta *build* dentro del paquete.</span><span class="sxs-lookup"><span data-stu-id="436f7-159">This instructs the [`dotnet pack`](dotnet-pack.md) command what to package, placing the targets files as well as the assemblies into the *build* folder inside the package.</span></span> <span data-ttu-id="436f7-160">Observe el elemento `<ItemGroup>` que tiene la propiedad `Label` establecida en `dotnet pack instructions`, y el destino que se define por debajo.</span><span class="sxs-lookup"><span data-stu-id="436f7-160">Notice the `<ItemGroup>` element that has the `Label` property set to `dotnet pack instructions`, and the Target defined beneath it.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <Description>Sample Packer</Description>
    <VersionPrefix>0.1.0-preview</VersionPrefix>
    <TargetFramework>netstandard1.3</TargetFramework>
    <DebugType>portable</DebugType>
    <AssemblyName>SampleTargets.PackerTarget</AssemblyName>
  </PropertyGroup>
  <ItemGroup>
    <EmbeddedResource Include="Resources\Pkg\dist-template.xml;compiler\resources\**\*" Exclude="bin\**;obj\**;**\*.xproj;packages\**" />
    <None Include="build\SampleTargets.PackerTarget.targets" />
  </ItemGroup>
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
  <ItemGroup>
    <PackageReference Include="Microsoft.Extensions.DependencyModel" Version="1.0.1-beta-000933"/>
    <PackageReference Include="Microsoft.Build.Framework" Version="0.1.0-preview-00028-160627" />
    <PackageReference Include="Microsoft.Build.Utilities.Core" Version="0.1.0-preview-00028-160627" />
    <PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
  </ItemGroup>
  <ItemGroup />
  <PropertyGroup Label="Globals">
    <ProjectGuid>463c66f0-921d-4d34-8bde-7c9d0bffaf7b</ProjectGuid>
  </PropertyGroup>
  <PropertyGroup Condition=" '$(TargetFramework)' == 'netstandard1.3' ">
    <DefineConstants>$(DefineConstants);NETSTANDARD1_3</DefineConstants>
  </PropertyGroup>
  <PropertyGroup Condition=" '$(Configuration)' == 'Release' ">
    <DefineConstants>$(DefineConstants);RELEASE</DefineConstants>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="436f7-161">Para consumir destinos personalizados se proporciona un elemento `<PackageReference>` que apunta al paquete y su versión dentro del proyecto que se extiende.</span><span class="sxs-lookup"><span data-stu-id="436f7-161">Consuming custom targets is done by providing a `<PackageReference>` that points to the package and its version inside the project that is being extended.</span></span> <span data-ttu-id="436f7-162">A diferencia de las herramientas, el paquete de destinos personalizados se incluye en el cierre de dependencia del proyecto de consumo.</span><span class="sxs-lookup"><span data-stu-id="436f7-162">Unlike the tools, the custom targets package does get included into the consuming project's dependency closure.</span></span>

<span data-ttu-id="436f7-163">El uso del destino personalizado depende exclusivamente de cómo se configure.</span><span class="sxs-lookup"><span data-stu-id="436f7-163">Using the custom target depends solely on how you configure it.</span></span> <span data-ttu-id="436f7-164">Como es un destino de MSBuild, puede depender de un destino dado, ejecutarse después de otro destino e invocarse también manualmente mediante el comando `dotnet msbuild -t:<target-name>`.</span><span class="sxs-lookup"><span data-stu-id="436f7-164">Since it's an MSBuild target, it can depend on a given target, run after another target and can also be manually invoked using the `dotnet msbuild -t:<target-name>` command.</span></span>

<span data-ttu-id="436f7-165">En cambio, si quiere proporcionar una mejor experiencia de usuario, puede combinar las herramientas por proyecto y los destinos personalizados.</span><span class="sxs-lookup"><span data-stu-id="436f7-165">However, if you want to provide a better user experience to your users, you can combine per-project tools and custom targets.</span></span> <span data-ttu-id="436f7-166">En este escenario, la herramienta por proyecto básicamente solo aceptaría todos los parámetros necesarios y lo traduciría en la invocación de [`dotnet msbuild`](dotnet-msbuild.md) necesaria que ejecutaría el destino.</span><span class="sxs-lookup"><span data-stu-id="436f7-166">In this scenario, the per-project tool would essentially just accept whatever needed parameters and would translate that into the required [`dotnet msbuild`](dotnet-msbuild.md) invocation that would execute the target.</span></span> <span data-ttu-id="436f7-167">Puede ver una muestra de esta clase de sinergia en el [repositorio de ejemplos de MVP Summit 2016 Hackathon](https://github.com/dotnet/MVPSummitHackathon2016) del proyecto [`dotnet-packer`](https://github.com/dotnet/MVPSummitHackathon2016/tree/master/dotnet-packer).</span><span class="sxs-lookup"><span data-stu-id="436f7-167">You can see a sample of this kind of synergy on the [MVP Summit 2016 Hackathon samples](https://github.com/dotnet/MVPSummitHackathon2016) repo in the [`dotnet-packer`](https://github.com/dotnet/MVPSummitHackathon2016/tree/master/dotnet-packer) project.</span></span>

## <a name="path-based-extensibility"></a><span data-ttu-id="436f7-168">Extensibilidad basada en la RUTA DE ACCESO</span><span class="sxs-lookup"><span data-stu-id="436f7-168">PATH-based extensibility</span></span>
<span data-ttu-id="436f7-169">La extensibilidad basada en la RUTA DE ACCESO se suele usar con equipos de desarrollo, donde necesita una herramienta que abarque conceptualmente más de un único proyecto.</span><span class="sxs-lookup"><span data-stu-id="436f7-169">PATH-based extensibility is usually used for development machines where you need a tool that conceptually covers more than a single project.</span></span> <span data-ttu-id="436f7-170">La principal desventaja de este mecanismo de extensión es que está vinculado a la máquina donde existe la herramienta.</span><span class="sxs-lookup"><span data-stu-id="436f7-170">The main drawback of this extension mechanism is that it's tied to the machine where the tool exists.</span></span> <span data-ttu-id="436f7-171">Si lo necesita en otro equipo, tendría que implementarlo.</span><span class="sxs-lookup"><span data-stu-id="436f7-171">If you need it on another machine, you would have to deploy it.</span></span>

<span data-ttu-id="436f7-172">Este patrón de extensibilidad del conjunto de herramientas de la CLI es muy sencillo.</span><span class="sxs-lookup"><span data-stu-id="436f7-172">This pattern of CLI toolset extensibility is very simple.</span></span> <span data-ttu-id="436f7-173">Como se explica en la [información general de la CLI de .NET Core](index.md), el controlador `dotnet` puede ejecutar cualquier comando que se nombre según la convención `dotnet-<command>`.</span><span class="sxs-lookup"><span data-stu-id="436f7-173">As covered in the [.NET Core CLI overview](index.md), `dotnet` driver can run any command that is named after the `dotnet-<command>` convention.</span></span> <span data-ttu-id="436f7-174">La lógica de resolución predeterminada sondea primero varias ubicaciones y finalmente vuelve a la RUTA DE ACCESO del sistema.</span><span class="sxs-lookup"><span data-stu-id="436f7-174">The default resolution logic first probes several locations and finally falls back to the system PATH.</span></span> <span data-ttu-id="436f7-175">Si el comando solicitado existe en la RUTA DE ACCESO del sistema y es un archivo binario que se puede invocar, el controlador `dotnet` lo invoca.</span><span class="sxs-lookup"><span data-stu-id="436f7-175">If the requested command exists in the system PATH and is a binary that can be invoked, `dotnet` driver will invoke it.</span></span>

<span data-ttu-id="436f7-176">El archivo debe ser ejecutable.</span><span class="sxs-lookup"><span data-stu-id="436f7-176">The file must be executable.</span></span> <span data-ttu-id="436f7-177">En sistemas Unix, esto significa todo lo que tiene el bit de ejecución establecido mediante `chmod +x`.</span><span class="sxs-lookup"><span data-stu-id="436f7-177">On Unix systems, this means anything that has the execute bit set via `chmod +x`.</span></span> <span data-ttu-id="436f7-178">En Windows, puede usar archivos *cmd*.</span><span class="sxs-lookup"><span data-stu-id="436f7-178">On Windows, you can use *cmd* files.</span></span>

<span data-ttu-id="436f7-179">Echemos un vistazo a una implementación muy sencilla de una herramienta "Hola mundo".</span><span class="sxs-lookup"><span data-stu-id="436f7-179">Let's take a look at the very simple implementation of a "Hello World" tool.</span></span> <span data-ttu-id="436f7-180">Usaremos `bash` y `cmd` en Windows.</span><span class="sxs-lookup"><span data-stu-id="436f7-180">We will use both `bash` and `cmd` on Windows.</span></span>
<span data-ttu-id="436f7-181">En el siguiente comando simplemente reflejaremos "Hola mundo" en la consola.</span><span class="sxs-lookup"><span data-stu-id="436f7-181">The following command will simply echo "Hello World" to the console.</span></span>

```bash
#!/bin/bash

echo "Hello World!"
```

```cmd
echo "Hello World"
```

<span data-ttu-id="436f7-182">En macOS, podemos guardar este script como `dotnet-hello` y establecer su bit ejecutable con `chmod +x dotnet-hello`.</span><span class="sxs-lookup"><span data-stu-id="436f7-182">On macOS, we can save this script as `dotnet-hello` and set its executable bit with `chmod +x dotnet-hello`.</span></span> <span data-ttu-id="436f7-183">Luego, podemos crear un vínculo simbólico a él en `/usr/local/bin` con el comando `ln -s <full_path>/dotnet-hello /usr/local/bin/`.</span><span class="sxs-lookup"><span data-stu-id="436f7-183">We can then create a symbolic link to it in `/usr/local/bin` using the command `ln -s <full_path>/dotnet-hello /usr/local/bin/`.</span></span> <span data-ttu-id="436f7-184">De esta manera se podrá invocar el comando mediante la sintaxis `dotnet hello`.</span><span class="sxs-lookup"><span data-stu-id="436f7-184">This will make it possible to invoke the command using the `dotnet hello` syntax.</span></span>

<span data-ttu-id="436f7-185">En Windows, podemos guardar este script como `dotnet-hello.cmd` y colocarlo en una ubicación que esté en una ruta de acceso del sistema (o puede agregarlo en una carpeta que ya se encuentre en la ruta de acceso).</span><span class="sxs-lookup"><span data-stu-id="436f7-185">On Windows, we can save this script as `dotnet-hello.cmd` and put it in a location that is in a system path (or you can add it to a folder that is already in the path).</span></span> <span data-ttu-id="436f7-186">Después de esto, simplemente puede usar `dotnet hello` para ejecutar este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="436f7-186">After this, you can just use `dotnet hello` to run this example.</span></span>
