---
title: Propiedades de MSBuild para Microsoft.NET.Sdk.Desktop
description: Referencia de las propiedades y los elementos de MSBuild admitidos por el SDK de Escritorio de .NET, que incluye WPF y WinForms.
ms.date: 02/04/2021
ms.topic: reference
author: adegeo
ms.author: adegeo
ms.custom: updateeachrelease
no-loc:
- App.xaml
- Application.xaml
- ApplicationDefinition
- Page
- EmbeddedResource
- Compile
- None
ms.openlocfilehash: 6d1903558dd03776a72eb6ee56ddae09fb66615b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100488270"
---
# <a name="msbuild-reference-for-net-desktop-sdk-projects"></a><span data-ttu-id="90fe0-103">Referencia de MSBuild para proyectos del SDK de Escritorio de .NET</span><span class="sxs-lookup"><span data-stu-id="90fe0-103">MSBuild reference for .NET Desktop SDK projects</span></span>

<span data-ttu-id="90fe0-104">Esta página es una referencia sobre las propiedades y los elementos de MSBuild que se usan para configurar proyectos de Windows Forms (WinForms) y Windows Presentation Foundation (WPF) con el SDK de Escritorio de .NET.</span><span class="sxs-lookup"><span data-stu-id="90fe0-104">This page is a reference for the MSBuild properties and items that you use to configure Windows Forms (WinForms) and Windows Presentation Foundation (WPF) projects with the .NET Desktop SDK.</span></span>

> [!NOTE]
> <span data-ttu-id="90fe0-105">En este artículo se documenta un subconjunto de las propiedades de MSBuild para el SDK de .NET en lo que se refiere a las aplicaciones de escritorio.</span><span class="sxs-lookup"><span data-stu-id="90fe0-105">This article documents a subset of the MSBuild properties for the .NET SDK as it relates to desktop apps.</span></span> <span data-ttu-id="90fe0-106">Para obtener una lista de propiedades de MSBuild específicas del SDK de .NET, vea [Referencia de MSBuild para proyectos de SDK de .NET](msbuild-props.md).</span><span class="sxs-lookup"><span data-stu-id="90fe0-106">For a list of common .NET SDK-specific MSBuild properties, see [MSBuild reference for .NET SDK projects](msbuild-props.md).</span></span> <span data-ttu-id="90fe0-107">Para obtener una lista de las propiedades comunes de MSBuild, vea [Propiedades comunes de MSBuild](/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="90fe0-107">For a list of common MSBuild properties, see [Common MSBuild properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="enable-net-desktop-sdk"></a><span data-ttu-id="90fe0-108">Habilitación del SDK de Escritorio de .NET</span><span class="sxs-lookup"><span data-stu-id="90fe0-108">Enable .NET Desktop SDK</span></span>

<span data-ttu-id="90fe0-109">Para usar WinForms o WPF, configure el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="90fe0-109">To use WinForms or WPF, configure your project file.</span></span>

### <a name="net-50"></a><span data-ttu-id="90fe0-110">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="90fe0-110">.NET 5.0</span></span>

<span data-ttu-id="90fe0-111">Especifique los valores de configuración siguientes en el archivo del proyecto de WinForms o WPF:</span><span class="sxs-lookup"><span data-stu-id="90fe0-111">Specify the following settings in the project file of your WinForms or WPF project:</span></span>

- <span data-ttu-id="90fe0-112">Seleccione como destino el SDK `Microsoft.NET.Sdk` de .NET.</span><span class="sxs-lookup"><span data-stu-id="90fe0-112">Target the .NET SDK `Microsoft.NET.Sdk`.</span></span> <span data-ttu-id="90fe0-113">Para obtener más información, vea [Archivos del proyecto](overview.md#project-files).</span><span class="sxs-lookup"><span data-stu-id="90fe0-113">For more information, see [Project files](overview.md#project-files).</span></span>
- <span data-ttu-id="90fe0-114">Establezca [`TargetFramework`](msbuild-props.md#targetframework) en `net5.0-windows`.</span><span class="sxs-lookup"><span data-stu-id="90fe0-114">Set [`TargetFramework`](msbuild-props.md#targetframework) to `net5.0-windows`.</span></span>
- <span data-ttu-id="90fe0-115">Agregue una propiedad de marco de interfaz de usuario (o ambas, si es necesario):</span><span class="sxs-lookup"><span data-stu-id="90fe0-115">Add a UI framework property (or both, if necessary):</span></span>
  - <span data-ttu-id="90fe0-116">Establezca [`UseWPF`](#usewpf) en `true` para importar y usar WPF.</span><span class="sxs-lookup"><span data-stu-id="90fe0-116">Set [`UseWPF`](#usewpf) to `true` to import and use WPF.</span></span>
  - <span data-ttu-id="90fe0-117">Establezca [`UseWindowsForms`](#usewindowsforms) en `true` para importar y usar WinForms.</span><span class="sxs-lookup"><span data-stu-id="90fe0-117">Set [`UseWindowsForms`](#usewindowsforms) to `true` to import and use WinForms.</span></span>
- <span data-ttu-id="90fe0-118">(Opcional) Establezca `OutputType` en `WinExe`.</span><span class="sxs-lookup"><span data-stu-id="90fe0-118">(Optional) Set `OutputType` to `WinExe`.</span></span> <span data-ttu-id="90fe0-119">Esto genera una aplicación en lugar de una biblioteca.</span><span class="sxs-lookup"><span data-stu-id="90fe0-119">This produces an app as opposed to a library.</span></span> <span data-ttu-id="90fe0-120">Para generar una biblioteca, omita esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="90fe0-120">To produce a library, omit this property.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>net5.0-windows</TargetFramework>

    <UseWPF>true</UseWPF>
    <!-- and/or -->
    <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>

</Project>
```

### <a name="net-core-31"></a><span data-ttu-id="90fe0-121">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="90fe0-121">.NET Core 3.1</span></span>

<span data-ttu-id="90fe0-122">Especifique los valores de configuración siguientes en el archivo del proyecto de WinForms o WPF:</span><span class="sxs-lookup"><span data-stu-id="90fe0-122">Specify the following settings in the project file of your WinForms or WPF project:</span></span>

- <span data-ttu-id="90fe0-123">Seleccione como destino el SDK `Microsoft.NET.Sdk.WindowsDesktop` de .NET.</span><span class="sxs-lookup"><span data-stu-id="90fe0-123">Target the .NET SDK `Microsoft.NET.Sdk.WindowsDesktop`.</span></span> <span data-ttu-id="90fe0-124">Para obtener más información, vea [Archivos del proyecto](overview.md#project-files).</span><span class="sxs-lookup"><span data-stu-id="90fe0-124">For more information, see [Project files](overview.md#project-files).</span></span>
- <span data-ttu-id="90fe0-125">Establezca [`TargetFramework`](msbuild-props.md#targetframework) en `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="90fe0-125">Set [`TargetFramework`](msbuild-props.md#targetframework) to `netcoreapp3.1`.</span></span>
- <span data-ttu-id="90fe0-126">Agregue una propiedad de marco de interfaz de usuario (o ambas, si es necesario):</span><span class="sxs-lookup"><span data-stu-id="90fe0-126">Add a UI framework property (or both, if necessary):</span></span>
  - <span data-ttu-id="90fe0-127">Establezca [`UseWPF`](#usewpf) en `true` para importar y usar WPF.</span><span class="sxs-lookup"><span data-stu-id="90fe0-127">Set [`UseWPF`](#usewpf) to `true` to import and use WPF.</span></span>
  - <span data-ttu-id="90fe0-128">Establezca [`UseWindowsForms`](#usewindowsforms) en `true` para importar y usar WinForms.</span><span class="sxs-lookup"><span data-stu-id="90fe0-128">Set [`UseWindowsForms`](#usewindowsforms) to `true` to import and use WinForms.</span></span>
- <span data-ttu-id="90fe0-129">(Opcional) Establezca `OutputType` en `WinExe`.</span><span class="sxs-lookup"><span data-stu-id="90fe0-129">(Optional) Set `OutputType` to `WinExe`.</span></span> <span data-ttu-id="90fe0-130">Esto genera una aplicación en lugar de una biblioteca.</span><span class="sxs-lookup"><span data-stu-id="90fe0-130">This produces an app as opposed to a library.</span></span> <span data-ttu-id="90fe0-131">Para generar una biblioteca, omita esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="90fe0-131">To produce a library, omit this property.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.1</TargetFramework>

    <UseWPF>true</UseWPF>
    <!-- and/or -->
    <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>

</Project>
```

## <a name="wpf-default-includes-and-excludes"></a><span data-ttu-id="90fe0-132">Inclusiones y exclusiones predeterminadas de WPF</span><span class="sxs-lookup"><span data-stu-id="90fe0-132">WPF default includes and excludes</span></span>

<span data-ttu-id="90fe0-133">Los proyectos de SDK definen un conjunto de reglas para incluir o excluir archivos del proyecto de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="90fe0-133">SDK projects define a set of rules to implicitly include or exclude files from the project.</span></span> <span data-ttu-id="90fe0-134">Estas reglas también establecen automáticamente la acción de compilación del archivo.</span><span class="sxs-lookup"><span data-stu-id="90fe0-134">These rules also automatically set the file's build action.</span></span> <span data-ttu-id="90fe0-135">Esto es diferente a los proyectos de .NET Framework anteriores que no son de SDK, que no tienen reglas predeterminadas de inclusión o exclusión.</span><span class="sxs-lookup"><span data-stu-id="90fe0-135">This is unlike the older non-SDK .NET Framework projects, which have no default include or exclude rules.</span></span> <span data-ttu-id="90fe0-136">En los proyectos de .NET Framework es necesario declarar de forma explícita los archivos que se van a incluir en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="90fe0-136">.NET Framework projects require you to explicitly declare which files to include in the project.</span></span>

<span data-ttu-id="90fe0-137">Los archivos del proyecto de .NET incluyen un [conjunto estándar de reglas](overview.md#default-includes-and-excludes) para el procesamiento automático de los archivos.</span><span class="sxs-lookup"><span data-stu-id="90fe0-137">.NET project files include a [standard set of rules](overview.md#default-includes-and-excludes) for automatically processing files.</span></span> <span data-ttu-id="90fe0-138">Los proyectos de WPF agregan reglas adicionales.</span><span class="sxs-lookup"><span data-stu-id="90fe0-138">WPF projects add additional rules.</span></span>

<span data-ttu-id="90fe0-139">En la tabla siguiente se muestra qué elementos y qué [patrones globales](https://en.wikipedia.org/wiki/Glob_(programming)) se incluyen y excluyen en el SDK de Escritorio de .NET cuando la propiedad del proyecto [`UseWPF`](#usewpf) se establece en `true`:</span><span class="sxs-lookup"><span data-stu-id="90fe0-139">The following table shows which elements and [globs](https://en.wikipedia.org/wiki/Glob_(programming)) are included and excluded in the .NET Desktop SDK when the [`UseWPF`](#usewpf) project property is set to `true`:</span></span>

| <span data-ttu-id="90fe0-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="90fe0-140">Element</span></span>               | <span data-ttu-id="90fe0-141">Glob para incluir</span><span class="sxs-lookup"><span data-stu-id="90fe0-141">Include glob</span></span>                 | <span data-ttu-id="90fe0-142">Glob para excluir</span><span class="sxs-lookup"><span data-stu-id="90fe0-142">Exclude glob</span></span>                                                                                           | <span data-ttu-id="90fe0-143">Glob para quitar</span><span class="sxs-lookup"><span data-stu-id="90fe0-143">Remove glob</span></span>  |
|-----------------------|------------------------------|--------------------------------------------------------------------|--------------|
| ApplicationDefinition | <span data-ttu-id="90fe0-144">App.xaml o Application.xaml</span><span class="sxs-lookup"><span data-stu-id="90fe0-144">App.xaml or Application.xaml</span></span> | <span data-ttu-id="90fe0-145">N/D</span><span class="sxs-lookup"><span data-stu-id="90fe0-145">N/A</span></span>                                                                | <span data-ttu-id="90fe0-146">N/D</span><span class="sxs-lookup"><span data-stu-id="90fe0-146">N/A</span></span>          |
| Page                  | <span data-ttu-id="90fe0-147">\*\*/\*.xaml</span><span class="sxs-lookup"><span data-stu-id="90fe0-147">\*\*/\*.xaml</span></span>                 | <span data-ttu-id="90fe0-148">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="90fe0-148">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span><br><span data-ttu-id="90fe0-149">Cualquier XAML definido por *ApplicationDefinition*</span><span class="sxs-lookup"><span data-stu-id="90fe0-149">Any XAML defined by *ApplicationDefinition*</span></span> | <span data-ttu-id="90fe0-150">N/D</span><span class="sxs-lookup"><span data-stu-id="90fe0-150">N/A</span></span>          |
| None                  | <span data-ttu-id="90fe0-151">N/D</span><span class="sxs-lookup"><span data-stu-id="90fe0-151">N/A</span></span>                          | <span data-ttu-id="90fe0-152">N/D</span><span class="sxs-lookup"><span data-stu-id="90fe0-152">N/A</span></span>                                                                | <span data-ttu-id="90fe0-153">\*\*/\*.xaml</span><span class="sxs-lookup"><span data-stu-id="90fe0-153">\*\*/\*.xaml</span></span> |

<span data-ttu-id="90fe0-154">Estos son los valores de configuración de las inclusiones y exclusiones predeterminadas para todos los tipos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="90fe0-154">Here are the default include and exclude settings for all project types.</span></span> <span data-ttu-id="90fe0-155">Para obtener más información, consulte [Inclusiones y exclusiones predeterminadas](overview.md#default-includes-and-excludes).</span><span class="sxs-lookup"><span data-stu-id="90fe0-155">For more information, see [Default includes and excludes](overview.md#default-includes-and-excludes).</span></span>

| <span data-ttu-id="90fe0-156">Elemento</span><span class="sxs-lookup"><span data-stu-id="90fe0-156">Element</span></span>           | <span data-ttu-id="90fe0-157">Glob para incluir</span><span class="sxs-lookup"><span data-stu-id="90fe0-157">Include glob</span></span>                              | <span data-ttu-id="90fe0-158">Glob para excluir</span><span class="sxs-lookup"><span data-stu-id="90fe0-158">Exclude glob</span></span>                                                  | <span data-ttu-id="90fe0-159">Glob para quitar</span><span class="sxs-lookup"><span data-stu-id="90fe0-159">Remove glob</span></span>              |
|-------------------|-------------------------------------------|---------------------------------------------------------------|--------------------------|
| Compile           | <span data-ttu-id="90fe0-160">\*\*/\*.cs; \*\*/\*.vb (o extensiones de otros lenguajes)</span><span class="sxs-lookup"><span data-stu-id="90fe0-160">\*\*/\*.cs; \*\*/\*.vb (or other language extensions)</span></span> | <span data-ttu-id="90fe0-161">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="90fe0-161">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span></span>  | <span data-ttu-id="90fe0-162">N/D</span><span class="sxs-lookup"><span data-stu-id="90fe0-162">N/A</span></span>          |
| EmbeddedResource  | <span data-ttu-id="90fe0-163">\*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="90fe0-163">\*\*/\*.resx</span></span>                              | <span data-ttu-id="90fe0-164">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="90fe0-164">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="90fe0-165">N/D</span><span class="sxs-lookup"><span data-stu-id="90fe0-165">N/A</span></span>                      |
| None              | \*\*/\*                                   | <span data-ttu-id="90fe0-166">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="90fe0-166">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="90fe0-167">\*\*/\*.cs; \*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="90fe0-167">\*\*/\*.cs; \*\*/\*.resx</span></span> |

### <a name="errors-related-to-duplicate-items"></a><span data-ttu-id="90fe0-168">Errores relacionados con elementos "duplicados"</span><span class="sxs-lookup"><span data-stu-id="90fe0-168">Errors related to "duplicate" items</span></span>

<span data-ttu-id="90fe0-169">Si ha agregado archivos de forma explícita al proyecto, o bien si tiene patrones globales de XAML para incluir archivos automáticamente en el proyecto, es posible que se produzca uno de los errores siguientes:</span><span class="sxs-lookup"><span data-stu-id="90fe0-169">If you explicitly added files to your project, or have XAML globs to automatically include files in your project, you might get one of the following errors:</span></span>

* <span data-ttu-id="90fe0-170">Se han incluido elementos "ApplicationDefinition" duplicados.</span><span class="sxs-lookup"><span data-stu-id="90fe0-170">Duplicate 'ApplicationDefinition' items were included.</span></span>
* <span data-ttu-id="90fe0-171">Se han incluido elementos "Page" duplicados.</span><span class="sxs-lookup"><span data-stu-id="90fe0-171">Duplicate 'Page' items were included.</span></span>

<span data-ttu-id="90fe0-172">Estos errores son el resultado de patrones globales *Include* implícitos en conflicto con la configuración.</span><span class="sxs-lookup"><span data-stu-id="90fe0-172">These errors are a result of the implicit *Include* globs conflicting with your settings.</span></span> <span data-ttu-id="90fe0-173">Para solucionar temporalmente este problema, establezca [`EnableDefaultApplicationDefinition`](#enabledefaultapplicationdefinition) o [`EnableDefaultPageItems`](#enabledefaultpageitems) en `false`.</span><span class="sxs-lookup"><span data-stu-id="90fe0-173">To work around this problem, set either [`EnableDefaultApplicationDefinition`](#enabledefaultapplicationdefinition) or [`EnableDefaultPageItems`](#enabledefaultpageitems) to `false`.</span></span> <span data-ttu-id="90fe0-174">Al establecer estos valores en `false`, se revierte el comportamiento de los SDK anteriores en los que tenía que definir explícitamente los patrones globales predeterminados en el proyecto, o bien definir de forma explícita los archivos que se iban a incluir en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="90fe0-174">Setting these values to `false` reverts to the behavior of previous SDKs where you had to explicitly define the default globs in your project, or explicitly define the files to include in the project.</span></span>

<span data-ttu-id="90fe0-175">Puede deshabilitar completamente todas las inclusiones implícitas si establece la [propiedad `EnableDefaultItems`](msbuild-props.md#enabledefaultitems) en `false`.</span><span class="sxs-lookup"><span data-stu-id="90fe0-175">You can completely disable all implicit includes by setting the [`EnableDefaultItems` property](msbuild-props.md#enabledefaultitems) to `false`.</span></span>

## <a name="wpf-settings"></a><span data-ttu-id="90fe0-176">Configuración de WPF</span><span class="sxs-lookup"><span data-stu-id="90fe0-176">WPF settings</span></span>

- [<span data-ttu-id="90fe0-177">UseWPF</span><span class="sxs-lookup"><span data-stu-id="90fe0-177">UseWPF</span></span>](#usewpf)
- [<span data-ttu-id="90fe0-178">EnableDefaultApplicationDefinition</span><span class="sxs-lookup"><span data-stu-id="90fe0-178">EnableDefaultApplicationDefinition</span></span>](#enabledefaultapplicationdefinition)
- [<span data-ttu-id="90fe0-179">EnableDefaultPageItems</span><span class="sxs-lookup"><span data-stu-id="90fe0-179">EnableDefaultPageItems</span></span>](#enabledefaultpageitems)

<span data-ttu-id="90fe0-180">Para obtener información sobre la configuración de proyectos no específicos de WPF, vea [Referencia de MSBuild para los proyectos del SDK de .NET](msbuild-props.md).</span><span class="sxs-lookup"><span data-stu-id="90fe0-180">For information about non-WPF-specific project settings, see [MSBuild reference for .NET SDK projects](msbuild-props.md).</span></span>

### <a name="usewpf"></a><span data-ttu-id="90fe0-181">UseWPF</span><span class="sxs-lookup"><span data-stu-id="90fe0-181">UseWPF</span></span>

<span data-ttu-id="90fe0-182">La propiedad `UseWPF` controla si se deben incluir o no referencias a las bibliotecas de WPF.</span><span class="sxs-lookup"><span data-stu-id="90fe0-182">The `UseWPF` property controls whether or not to include references to WPF libraries.</span></span> <span data-ttu-id="90fe0-183">Esto también altera la canalización de MSBuild para procesar correctamente un proyecto de WPF y los archivos relacionados.</span><span class="sxs-lookup"><span data-stu-id="90fe0-183">This also alters the MSBuild pipeline to correctly process a WPF project and related files.</span></span> <span data-ttu-id="90fe0-184">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="90fe0-184">The default value is `false`.</span></span> <span data-ttu-id="90fe0-185">Establezca la propiedad `UseWPF` en `true` para habilitar la compatibilidad con WPF.</span><span class="sxs-lookup"><span data-stu-id="90fe0-185">Set the `UseWPF` property to `true` to enable WPF support.</span></span> <span data-ttu-id="90fe0-186">Cuando esta propiedad está habilitada, solo puede seleccionar como destino la plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="90fe0-186">You can only target the Windows platform when this property is enabled.</span></span>

```xml
<PropertyGroup>
  <UseWPF>true</UseWPF>
</PropertyGroup>
```

<span data-ttu-id="90fe0-187">Cuando esta propiedad se establece en `true`, los proyectos de .NET 5.0 y versiones posteriores importarán de forma automática el [SDK de Escritorio de .NET](#enable-net-desktop-sdk).</span><span class="sxs-lookup"><span data-stu-id="90fe0-187">When this property is set to `true`, .NET 5.0+ projects will automatically import the [.NET Desktop SDK](#enable-net-desktop-sdk).</span></span>

<span data-ttu-id="90fe0-188">Los proyectos de .NET Core 3.1 deben tener como destino explícitamente el [SDK de Escritorio de .NET](#enable-net-desktop-sdk) para usar esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="90fe0-188">.NET Core 3.1 projects need to explicitly target the [.NET Desktop SDK](#enable-net-desktop-sdk) to use this property.</span></span>

### <a name="enabledefaultapplicationdefinition"></a><span data-ttu-id="90fe0-189">EnableDefaultApplicationDefinition</span><span class="sxs-lookup"><span data-stu-id="90fe0-189">EnableDefaultApplicationDefinition</span></span>

<span data-ttu-id="90fe0-190">La propiedad `EnableDefaultApplicationDefinition` controla si los elementos `ApplicationDefinition` se incluyen en el proyecto de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="90fe0-190">The `EnableDefaultApplicationDefinition` property controls whether `ApplicationDefinition` items are implicitly included in the project.</span></span> <span data-ttu-id="90fe0-191">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="90fe0-191">The default value is `true`.</span></span> <span data-ttu-id="90fe0-192">Establezca la propiedad `EnableDefaultApplicationDefinition` en `false` para deshabilitar la inclusión de archivos implícita.</span><span class="sxs-lookup"><span data-stu-id="90fe0-192">Set the `EnableDefaultApplicationDefinition` property to `false` to disable the implicit file inclusion.</span></span>

```xml
<PropertyGroup>
  <EnableDefaultApplicationDefinition>false</EnableDefaultApplicationDefinition>
</PropertyGroup>
```

<span data-ttu-id="90fe0-193">Esta propiedad necesita que la [propiedad `EnableDefaultItems`](msbuild-props.md#enabledefaultitems) esté establecida en `true`, que es el valor de configuración predeterminado.</span><span class="sxs-lookup"><span data-stu-id="90fe0-193">This property requires that the [`EnableDefaultItems` property](msbuild-props.md#enabledefaultitems) property is set to `true`, which is the default setting.</span></span>

### <a name="enabledefaultpageitems"></a><span data-ttu-id="90fe0-194">EnableDefaultPageItems</span><span class="sxs-lookup"><span data-stu-id="90fe0-194">EnableDefaultPageItems</span></span>

<span data-ttu-id="90fe0-195">La propiedad `EnableDefaultPageItems` controla si los elementos `Page`, que son archivos _.xaml_, se incluyen en el proyecto de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="90fe0-195">The `EnableDefaultPageItems` property controls whether `Page` items, which are _.xaml_ files, are implicitly included in the project.</span></span> <span data-ttu-id="90fe0-196">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="90fe0-196">The default value is `true`.</span></span> <span data-ttu-id="90fe0-197">Establezca la propiedad `EnableDefaultPageItems` en `false` para deshabilitar la inclusión de archivos implícita.</span><span class="sxs-lookup"><span data-stu-id="90fe0-197">Set the `EnableDefaultPageItems` property to `false` to disable the implicit file inclusion.</span></span>

```xml
<PropertyGroup>
  <EnableDefaultPageItems>false</EnableDefaultPageItems>
</PropertyGroup>
```

<span data-ttu-id="90fe0-198">Esta propiedad necesita que la [propiedad `EnableDefaultItems`](msbuild-props.md#enabledefaultitems) esté establecida en `true`, que es el valor de configuración predeterminado.</span><span class="sxs-lookup"><span data-stu-id="90fe0-198">This property requires that the [`EnableDefaultItems` property](msbuild-props.md#enabledefaultitems) property is set to `true`, which is the default setting.</span></span>

## <a name="windows-forms-settings"></a><span data-ttu-id="90fe0-199">Configuración de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="90fe0-199">Windows Forms settings</span></span>

- [<span data-ttu-id="90fe0-200">UseWindowsForms</span><span class="sxs-lookup"><span data-stu-id="90fe0-200">UseWindowsForms</span></span>](#usewindowsforms)

<span data-ttu-id="90fe0-201">Para obtener información sobre las propiedades de proyecto que no son específicas de WinForms, vea [Referencia de MSBuild para los proyectos del SDK de .NET](msbuild-props.md).</span><span class="sxs-lookup"><span data-stu-id="90fe0-201">For information about non-WinForms-specific project properties, see [MSBuild reference for .NET SDK projects](msbuild-props.md).</span></span>

### <a name="usewindowsforms"></a><span data-ttu-id="90fe0-202">UseWindowsForms</span><span class="sxs-lookup"><span data-stu-id="90fe0-202">UseWindowsForms</span></span>

<span data-ttu-id="90fe0-203">La propiedad `UseWindowsForms` controla si la aplicación se compila o no para destinarla a Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="90fe0-203">The `UseWindowsForms` property controls whether or not your application is built to target Windows Forms.</span></span> <span data-ttu-id="90fe0-204">Esta propiedad también altera la canalización de MSBuild para procesar correctamente un proyecto de Windows Forms y los archivos relacionados.</span><span class="sxs-lookup"><span data-stu-id="90fe0-204">This property alters the MSBuild pipeline to correctly process a Windows Forms project and related files.</span></span> <span data-ttu-id="90fe0-205">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="90fe0-205">The default value is `false`.</span></span> <span data-ttu-id="90fe0-206">Establezca la propiedad `UseWindowsForms` en `true` para habilitar la compatibilidad con Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="90fe0-206">Set the `UseWindowsForms` property to `true` to enable Windows Forms support.</span></span> <span data-ttu-id="90fe0-207">Cuando este valor de configuración está habilitado, solo puede seleccionar como destino la plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="90fe0-207">You can only target the Windows platform when this setting is enabled.</span></span>

```xml
<PropertyGroup>
  <UseWindowsForms>true</UseWindowsForms>
</PropertyGroup>
```

<span data-ttu-id="90fe0-208">Cuando esta propiedad se establece en `true`, los proyectos de .NET 5.0 y versiones posteriores importarán de forma automática el [SDK de Escritorio de .NET](#enable-net-desktop-sdk).</span><span class="sxs-lookup"><span data-stu-id="90fe0-208">When this property is set to `true`, .NET 5.0+ projects will automatically import the [.NET Desktop SDK](#enable-net-desktop-sdk).</span></span>

<span data-ttu-id="90fe0-209">Los proyectos de .NET Core 3.1 deben tener como destino explícitamente el [SDK de Escritorio de .NET](#enable-net-desktop-sdk) para usar esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="90fe0-209">.NET Core 3.1 projects need to explicitly target the [.NET Desktop SDK](#enable-net-desktop-sdk) to use this property.</span></span>

## <a name="shared-settings"></a><span data-ttu-id="90fe0-210">Configuración compartida</span><span class="sxs-lookup"><span data-stu-id="90fe0-210">Shared settings</span></span>

- [<span data-ttu-id="90fe0-211">DisableWinExeOutputInference</span><span class="sxs-lookup"><span data-stu-id="90fe0-211">DisableWinExeOutputInference</span></span>](#disablewinexeoutputinference)

### <a name="disablewinexeoutputinference"></a><span data-ttu-id="90fe0-212">DisableWinExeOutputInference</span><span class="sxs-lookup"><span data-stu-id="90fe0-212">DisableWinExeOutputInference</span></span>

<span data-ttu-id="90fe0-213">Se aplica al SDK de .NET 5.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="90fe0-213">Applies to .NET 5.0 SDK and later.</span></span>

<span data-ttu-id="90fe0-214">Cuando una aplicación tiene el valor `Exe` establecido para la propiedad `OutputType`, se crea una ventana de consola si la aplicación no se ejecuta desde una consola.</span><span class="sxs-lookup"><span data-stu-id="90fe0-214">When an app has the `Exe` value set for the `OutputType` property, a console window is created if the app isn't running from a console.</span></span> <span data-ttu-id="90fe0-215">Normalmente este no es el comportamiento deseado de una aplicación de escritorio de Windows.</span><span class="sxs-lookup"><span data-stu-id="90fe0-215">This is generally not the desired behavior of a Windows Desktop app.</span></span> <span data-ttu-id="90fe0-216">Con el valor `WinExe`, no se crea una ventana de consola.</span><span class="sxs-lookup"><span data-stu-id="90fe0-216">With the `WinExe` value, a console window isn't created.</span></span> <span data-ttu-id="90fe0-217">A partir del SDK de .NET 5.0, el valor `Exe` se transforma automáticamente en `WinExe`.</span><span class="sxs-lookup"><span data-stu-id="90fe0-217">Starting with the .NET 5.0 SDK, the `Exe` value is automatically transformed to `WinExe`.</span></span>

<span data-ttu-id="90fe0-218">La propiedad `DisableWinExeOutputInference` revierte el comportamiento de tratar `Exe` como `WinExe`.</span><span class="sxs-lookup"><span data-stu-id="90fe0-218">The `DisableWinExeOutputInference` property reverts the behavior of treating `Exe` as `WinExe`.</span></span> <span data-ttu-id="90fe0-219">Establezca este valor en `true` para restaurar el comportamiento del valor de la propiedad `OutputType` de `Exe`.</span><span class="sxs-lookup"><span data-stu-id="90fe0-219">Set this value to `true` to restore the behavior of the `OutputType` property value of `Exe`.</span></span> <span data-ttu-id="90fe0-220">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="90fe0-220">The default value is `false`.</span></span>

```xml
<PropertyGroup>
  <DisableWinExeOutputInference>true</DisableWinExeOutputInference>
</PropertyGroup>
```

## <a name="see-also"></a><span data-ttu-id="90fe0-221">Vea también</span><span class="sxs-lookup"><span data-stu-id="90fe0-221">See also</span></span>

- [<span data-ttu-id="90fe0-222">SDK de proyectos de .NET</span><span class="sxs-lookup"><span data-stu-id="90fe0-222">.NET project SDKs</span></span>](overview.md)
- [<span data-ttu-id="90fe0-223">Referencia de MSBuild para proyectos del SDK de .NET</span><span class="sxs-lookup"><span data-stu-id="90fe0-223">MSBuild reference for .NET SDK projects</span></span>](msbuild-props.md)
- [<span data-ttu-id="90fe0-224">Referencia del esquema de MSBuild</span><span class="sxs-lookup"><span data-stu-id="90fe0-224">MSBuild schema reference</span></span>](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [<span data-ttu-id="90fe0-225">Propiedades comunes de MSBuild</span><span class="sxs-lookup"><span data-stu-id="90fe0-225">Common MSBuild properties</span></span>](/visualstudio/msbuild/common-msbuild-project-properties)
- [<span data-ttu-id="90fe0-226">Personalización de una compilación</span><span class="sxs-lookup"><span data-stu-id="90fe0-226">Customize a build</span></span>](/visualstudio/msbuild/customize-your-build)
