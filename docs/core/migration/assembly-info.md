---
title: Propiedades de AssemblyInfo
description: Obtenga información sobre los atributos de ensamblado y cómo se corresponden con las propiedades de MSBuild en .NET Core 2.1 y versiones posteriores.
ms.topic: reference
ms.date: 01/08/2021
ms.openlocfilehash: a2c431b3fe3da428f21582624ca5f357887e2815
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "98192879"
---
# <a name="map-assemblyinfo-attributes-to-properties"></a><span data-ttu-id="63936-103">Asignación de atributos AssemblyInfo a propiedades</span><span class="sxs-lookup"><span data-stu-id="63936-103">Map AssemblyInfo attributes to properties</span></span>

<span data-ttu-id="63936-104">Los [atributos de ensamblado](../../standard/assembly/set-attributes.md) que normalmente estaban presentes en un archivo *AssemblyInfo* en .NET Core 2.0 y versiones anteriores se generan automáticamente a partir de las propiedades de MSBuild en .NET Core 2.1 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="63936-104">[Assembly attributes](../../standard/assembly/set-attributes.md) that were typically present in an *AssemblyInfo* file in .NET Core 2.0 and earlier versions are automatically generated from MSBuild properties, starting in .NET Core 2.1.</span></span>

## <a name="properties-per-attribute"></a><span data-ttu-id="63936-105">Propiedades por atributo</span><span class="sxs-lookup"><span data-stu-id="63936-105">Properties per attribute</span></span>

<span data-ttu-id="63936-106">Como se muestra en la tabla siguiente, cada atributo tiene una propiedad correspondiente que controla el contenido y otra que deshabilita su generación:</span><span class="sxs-lookup"><span data-stu-id="63936-106">As shown in the following table, each attribute has a corresponding property that controls its content and another that disables its generation:</span></span>

| <span data-ttu-id="63936-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="63936-107">Attribute</span></span>                                                      | <span data-ttu-id="63936-108">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="63936-108">Property</span></span>               | <span data-ttu-id="63936-109">Propiedad que se va a deshabilitar</span><span class="sxs-lookup"><span data-stu-id="63936-109">Property to disable</span></span>                             |
|----------------------------------------------------------------|------------------------|-------------------------------------------------|
| <xref:System.Reflection.AssemblyCompanyAttribute>              | `Company`              | `GenerateAssemblyCompanyAttribute`              |
| <xref:System.Reflection.AssemblyConfigurationAttribute>        | `Configuration`        | `GenerateAssemblyConfigurationAttribute`        |
| <xref:System.Reflection.AssemblyCopyrightAttribute>            | `Copyright`            | `GenerateAssemblyCopyrightAttribute`            |
| <xref:System.Reflection.AssemblyDescriptionAttribute>          | `Description`          | `GenerateAssemblyDescriptionAttribute`          |
| <xref:System.Reflection.AssemblyFileVersionAttribute>          | `FileVersion`          | `GenerateAssemblyFileVersionAttribute`          |
| <xref:System.Reflection.AssemblyInformationalVersionAttribute> | `InformationalVersion` | `GenerateAssemblyInformationalVersionAttribute` |
| <xref:System.Reflection.AssemblyProductAttribute>              | `Product`              | `GenerateAssemblyProductAttribute`              |
| <xref:System.Reflection.AssemblyTitleAttribute>                | `AssemblyTitle`        | `GenerateAssemblyTitleAttribute`                |
| <xref:System.Reflection.AssemblyVersionAttribute>              | `AssemblyVersion`      | `GenerateAssemblyVersionAttribute`              |
| <xref:System.Resources.NeutralResourcesLanguageAttribute>      | `NeutralLanguage`      | `GenerateNeutralResourcesLanguageAttribute`     |

<span data-ttu-id="63936-110">Notas:</span><span class="sxs-lookup"><span data-stu-id="63936-110">Notes:</span></span>

- <span data-ttu-id="63936-111">`AssemblyVersion` y `FileVersion` tienen como valor predeterminado el valor de `$(Version)` sin el sufijo.</span><span class="sxs-lookup"><span data-stu-id="63936-111">`AssemblyVersion` and `FileVersion` default to the value of `$(Version)` without the suffix.</span></span> <span data-ttu-id="63936-112">Por ejemplo, si `$(Version)` es `1.2.3-beta.4`, entonces el valor sería `1.2.3`.</span><span class="sxs-lookup"><span data-stu-id="63936-112">For example, if `$(Version)` is `1.2.3-beta.4`, then the value would be `1.2.3`.</span></span>
- <span data-ttu-id="63936-113">El valor predeterminado de `InformationalVersion` es el de `$(Version)`.</span><span class="sxs-lookup"><span data-stu-id="63936-113">`InformationalVersion` defaults to the value of `$(Version)`.</span></span>
- <span data-ttu-id="63936-114">Si la propiedad `$(SourceRevisionId)` está presente, se anexa a `InformationalVersion`.</span><span class="sxs-lookup"><span data-stu-id="63936-114">If the `$(SourceRevisionId)` property is present, it's appended to `InformationalVersion`.</span></span> <span data-ttu-id="63936-115">Puede deshabilitar este comportamiento mediante `IncludeSourceRevisionInInformationalVersion`.</span><span class="sxs-lookup"><span data-stu-id="63936-115">You can disable this behavior using `IncludeSourceRevisionInInformationalVersion`.</span></span>
- <span data-ttu-id="63936-116">Las propiedades `Copyright` y `Description` también se utilizan para metadatos de NuGet.</span><span class="sxs-lookup"><span data-stu-id="63936-116">`Copyright` and `Description` properties are also used for NuGet metadata.</span></span>
- <span data-ttu-id="63936-117">`Configuration`, que tiene `Debug` como valor predeterminado, se comparte con todos los destinos de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="63936-117">`Configuration`, which defaults to `Debug`, is shared with all MSBuild targets.</span></span> <span data-ttu-id="63936-118">Se puede establecer con la opción `--configuration` de los comandos `dotnet`; por ejemplo, [dotnet pack](../tools/dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="63936-118">You can set it via the `--configuration` option of `dotnet` commands, for example, [dotnet pack](../tools/dotnet-pack.md).</span></span>

## <a name="generateassemblyinfo"></a><span data-ttu-id="63936-119">GenerateAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="63936-119">GenerateAssemblyInfo</span></span>

<span data-ttu-id="63936-120">Booleano que habilita o deshabilita la generación de AssemblyInfo.</span><span class="sxs-lookup"><span data-stu-id="63936-120">A Boolean that enables or disables the AssemblyInfo generation.</span></span> <span data-ttu-id="63936-121">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="63936-121">The default value is `true`.</span></span>

## <a name="generatedassemblyinfofile"></a><span data-ttu-id="63936-122">GeneratedAssemblyInfoFile</span><span class="sxs-lookup"><span data-stu-id="63936-122">GeneratedAssemblyInfoFile</span></span>

<span data-ttu-id="63936-123">Ruta de acceso relativa o completa del archivo de información de ensamblado generado.</span><span class="sxs-lookup"><span data-stu-id="63936-123">The relative or absolute path of the generated assembly info file.</span></span> <span data-ttu-id="63936-124">Tiene un archivo denominado *[nombre-proyecto].AssemblyInfo.[cs|vb]* en el directorio `$(IntermediateOutputPath)` (*obj*) como valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="63936-124">Defaults to a file named *[project-name].AssemblyInfo.[cs|vb]* in the `$(IntermediateOutputPath)` (*obj*) directory.</span></span>
