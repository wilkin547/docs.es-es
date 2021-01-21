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
# <a name="map-assemblyinfo-attributes-to-properties"></a>Asignación de atributos AssemblyInfo a propiedades

Los [atributos de ensamblado](../../standard/assembly/set-attributes.md) que normalmente estaban presentes en un archivo *AssemblyInfo* en .NET Core 2.0 y versiones anteriores se generan automáticamente a partir de las propiedades de MSBuild en .NET Core 2.1 y versiones posteriores.

## <a name="properties-per-attribute"></a>Propiedades por atributo

Como se muestra en la tabla siguiente, cada atributo tiene una propiedad correspondiente que controla el contenido y otra que deshabilita su generación:

| Atributo                                                      | Propiedad.               | Propiedad que se va a deshabilitar                             |
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

Notas:

- `AssemblyVersion` y `FileVersion` tienen como valor predeterminado el valor de `$(Version)` sin el sufijo. Por ejemplo, si `$(Version)` es `1.2.3-beta.4`, entonces el valor sería `1.2.3`.
- El valor predeterminado de `InformationalVersion` es el de `$(Version)`.
- Si la propiedad `$(SourceRevisionId)` está presente, se anexa a `InformationalVersion`. Puede deshabilitar este comportamiento mediante `IncludeSourceRevisionInInformationalVersion`.
- Las propiedades `Copyright` y `Description` también se utilizan para metadatos de NuGet.
- `Configuration`, que tiene `Debug` como valor predeterminado, se comparte con todos los destinos de MSBuild. Se puede establecer con la opción `--configuration` de los comandos `dotnet`; por ejemplo, [dotnet pack](../tools/dotnet-pack.md).

## <a name="generateassemblyinfo"></a>GenerateAssemblyInfo

Booleano que habilita o deshabilita la generación de AssemblyInfo. El valor predeterminado es `true`.

## <a name="generatedassemblyinfofile"></a>GeneratedAssemblyInfoFile

Ruta de acceso relativa o completa del archivo de información de ensamblado generado. Tiene un archivo denominado *[nombre-proyecto].AssemblyInfo.[cs|vb]* en el directorio `$(IntermediateOutputPath)` (*obj*) como valor predeterminado.
