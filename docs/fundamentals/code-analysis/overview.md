---
title: Análisis de código en .NET
titleSuffix: ''
description: Obtenga información sobre el análisis de código fuente en el SDK de .NET.
ms.date: 12/04/2020
ms.topic: overview
ms.custom: updateeachrelease
helpviewer_keywords:
- code analysis
- code analyzers
ms.openlocfilehash: 1a0b31f7aca6415510ed0fcd08e9f9a0f8f39bf5
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104876609"
---
# <a name="overview-of-net-source-code-analysis"></a>Información general sobre el análisis de código fuente de .NET

Los analizadores de .NET Compiler Platform (Roslyn) inspeccionan el código de C# o Visual Basic para supervisar la calidad e identificar problemas de estilo. A partir de .NET 5.0, estos analizadores se incluyen con el SDK de .NET y no es necesario instalarlos por separado. Si el proyecto tiene como destino .NET 5 o una versión posterior, el análisis de código está habilitado de forma predeterminada. Si el proyecto tiene como destino otra implementación de .NET, por ejemplo, .NET Core, .NET Standard o .NET Framework, debe establecer la propiedad [EnableNETAnalyzers](../../core/project-sdk/msbuild-props.md#enablenetanalyzers) en `true` para habilitar manualmente el análisis de código.

Si no quiere cambiar al SDK de .NET 5+, tiene un proyecto de .NET Framework de estilo de SDK, o bien prefiere un modelo basado en paquetes NuGet, los analizadores también están disponibles en el [paquete NuGet Microsoft.CodeAnalysis.NetAnalyzers](https://www.nuget.org/packages/Microsoft.CodeAnalysis.NetAnalyzers). Es posible que prefiera un modelo basado en paquetes para las actualizaciones de versión a petición.

> [!NOTE]
> Los analizadores de .NET son independientes de la plataforma de destino. Es decir, el proyecto no necesita tener como destino una implementación de .NET específica. Los analizadores funcionan para los proyectos que tienen `net5.0` como destino, así como las versiones anteriores de .NET, como `netcoreapp3.1` y `net472`. Pero para habilitar el análisis de código mediante la propiedad [EnableNETAnalyzers](../../core/project-sdk/msbuild-props.md#enablenetanalyzers), el proyecto debe hacer referencia a un [SDK de proyecto](../../core/project-sdk/overview.md).

Si un analizador detecta infracciones de reglas, se notifican como una sugerencia, una advertencia o un error, en función de cómo esté [configurada](configuration-options.md) cada regla. Las infracciones de análisis de código aparecen con el prefijo "CA" o "IDE" para diferenciarlas de los errores del compilador.

## <a name="code-quality-analysis"></a>Análisis de calidad del código

Las reglas de *análisis de calidad del código* ("CAxxxx") inspeccionan el código de C# o Visual Basic en busca de incidencias de seguridad, rendimiento, diseño y de otro tipo. De forma predeterminada, el análisis está habilitado para los proyectos que tienen como destino .NET 5.0 o una versión posterior. Puede habilitar el análisis de código en los proyectos que tengan como destino versiones anteriores de .NET estableciendo la propiedad [EnableNETAnalyzers](../../core/project-sdk/msbuild-props.md#enablenetanalyzers) en `true`. También puede deshabilitar el análisis de código para el proyecto si establece `EnableNETAnalyzers` en `false`.

> [!TIP]
> Si usa Visual Studio:
>
> - Muchas reglas de analizador tienen *correcciones de código* asociadas que se pueden aplicar para corregir el problema. Las correcciones de código se muestran en el menú del icono de bombilla.
> - Para habilitar o deshabilitar el análisis de código, haga clic con el botón derecho en un proyecto en el Explorador de soluciones y seleccione **Propiedades** > pestaña **Análisis de código** > **Habilitar los analizadores de .NET**.

### <a name="enabled-rules"></a>Reglas habilitadas

Las siguientes reglas están habilitadas de forma predeterminada en .NET 5.0.

| Id. de diagnóstico | Category | severity | Descripción |
| - | - | - | - |
| [CA1416](/visualstudio/code-quality/ca1416) | Interoperabilidad | Advertencia | Analizador de compatibilidad de plataformas |
| [CA1417](/visualstudio/code-quality/ca1417) | Interoperabilidad | Advertencia | No usar `OutAttribute` en parámetros de cadena para P/Invoke |
| [CA1831](/visualstudio/code-quality/ca1831) | Rendimiento | Advertencia | Usar `AsSpan` en lugar de indizadores basados en intervalos para una cadena cuando proceda |
| [CA2013](/visualstudio/code-quality/ca2013) | Confiabilidad | Advertencia | No usar `ReferenceEquals` con tipos de valor |
| [CA2014](/visualstudio/code-quality/ca2014) | Confiabilidad | Advertencia | No usar `stackalloc` en bucles |
| [CA2015](/visualstudio/code-quality/ca2015) | Confiabilidad | Advertencia | No definir finalizadores para los tipos derivados de <xref:System.Buffers.MemoryManager%601> |
| [CA2200](/visualstudio/code-quality/ca2200) | Uso | Advertencia | Reiniciar para mantener los detalles de la pila
| [CA2247](/visualstudio/code-quality/ca2247) | Uso | Advertencia | El argumento pasado al constructor TaskCompletionSource debe ser una enumeración <xref:System.Threading.Tasks.TaskCreationOptions> en lugar de <xref:System.Threading.Tasks.TaskContinuationOptions> |

Puede cambiar la gravedad de estas reglas para deshabilitarlas o elevarlas a errores. También puede [habilitar más reglas](#enable-additional-rules).

- Para obtener una lista de las reglas que se incluyen con cada versión del SDK de .NET, vea [Versiones del analizador](https://github.com/dotnet/roslyn-analyzers/blob/main/src/NetAnalyzers/Core/AnalyzerReleases.Shipped.md).
- Para obtener una lista de todas las reglas de calidad del código, vea [Reglas de calidad del código](quality-rules/index.md).

### <a name="enable-additional-rules"></a>Habilitación de reglas adicionales

El *modo de análisis* hace referencia a una configuración de análisis de código predefinida en la que ninguna, algunas o todas las reglas están habilitadas. En el modo de análisis predeterminado, solo se habilita un pequeño número de reglas [como advertencias de compilación](#enabled-rules). Puede cambiar el modo de análisis del proyecto si establece la propiedad [\<AnalysisMode>](../../core/project-sdk/msbuild-props.md#analysismode) en el archivo del proyecto. Entre los valores permitidos se incluyen los siguientes:

| Valor | Descripción |
| - | - |
| `AllDisabledByDefault` | Este es el modo más conservador. Todas las reglas están deshabilitadas de manera predeterminada. Puede [incluir](configuration-options.md) de forma selectiva reglas individuales para habilitarlas.<br /><br />`<AnalysisMode>AllDisabledByDefault</AnalysisMode>` |
| `AllEnabledByDefault` | Este es el modo más agresivo. Todas las reglas están habilitadas como advertencias de compilación. Puede [excluir](configuration-options.md) de forma selectiva reglas individuales para deshabilitarlas.<br /><br />`<AnalysisMode>AllEnabledByDefault</AnalysisMode>` |
| `Default` | El modo predeterminado, en el que una serie de reglas se habilitan como advertencias, otras solo se habilitan como sugerencias del IDE de Visual Studio con las correcciones de código correspondientes y el resto se deshabilitan por completo. Puede [excluir o incluir](configuration-options.md) de forma selectiva reglas individuales para deshabilitarlas.<br /><br />`<AnalysisMode>Default</AnalysisMode>` |

Para buscar la gravedad predeterminada de cada regla disponible y si la regla está habilitada o no en el modo de análisis predeterminado, vea la [lista completa de reglas](https://github.com/dotnet/roslyn-analyzers/blob/main/src/NetAnalyzers/Core/AnalyzerReleases.Shipped.md).

### <a name="treat-warnings-as-errors"></a>Tratar advertencias como errores

Si usa la marca `-warnaserror` al compilar los proyectos, todas las advertencias de análisis de código también se tratan como errores. Si no quiere que las advertencias de calidad del código (CAxxxx) se traten como errores cuando `-warnaserror` está presente, puede establecer la propiedad `CodeAnalysisTreatWarningsAsErrors` de MSBuild en `false` en el archivo del proyecto.

```xml
<PropertyGroup>
  <CodeAnalysisTreatWarningsAsErrors>false</CodeAnalysisTreatWarningsAsErrors>
</PropertyGroup>
```

Todavía verá advertencias de análisis de código, pero no interrumpirán la compilación.

### <a name="latest-updates"></a>Actualizaciones más recientes

De forma predeterminada, obtendrá las reglas de análisis de código más recientes y las gravedades de las reglas predeterminadas a medida que actualice a las versiones más recientes del SDK de .NET. Si no quiere este comportamiento, por ejemplo, si quiere asegurarse de que no se habiliten o deshabiliten las reglas nuevas, puede invalidarlo de una de las siguientes maneras:

- Establezca la propiedad `AnalysisLevel` de MSBuild en un valor específico para bloquear las advertencias a ese conjunto. Al actualizar a un SDK más reciente, todavía obtendrá correcciones de errores para esas advertencias, pero no se habilitarán nuevas advertencias y no se deshabilitarán las existentes. Por ejemplo, para limitar el conjunto de reglas a las que se incluyen en la versión 5.0 del SDK de .NET, agregue la entrada siguiente al archivo del proyecto.

  ```xml
  <PropertyGroup>
    <AnalysisLevel>5.0</AnalysisLevel>
  </PropertyGroup>
  ```

  > [!TIP]
  > El valor predeterminado de la propiedad `AnalysisLevel` es `latest`, lo que significa que siempre obtendrá las reglas de análisis de código más recientes al cambiar a versiones más recientes del SDK de .NET.

  Para obtener más información y una lista de los valores posibles, vea [AnalysisLevel](../../core/project-sdk/msbuild-props.md#analysislevel).

- Instale el [paquete NuGet Microsoft.CodeAnalysis.NetAnalyzers](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisnetanalyzers) para desacoplar las actualizaciones de reglas de las actualizaciones del SDK de .NET. En los proyectos que tienen como destino .NET 5+, la instalación del paquete desactiva los analizadores integrados del SDK. Obtendrá una advertencia de compilación si el SDK contiene una versión más reciente del ensamblado del analizador que la del paquete NuGet. Para deshabilitar la advertencia, establezca la propiedad `_SkipUpgradeNetAnalyzersNuGetWarning` en `true`.

  > [!NOTE]
  > Si instala el paquete NuGet Microsoft.CodeAnalysis.NetAnalyzers, no debe agregar la propiedad [EnableNETAnalyzers](../../core/project-sdk/msbuild-props.md#enablenetanalyzers) al archivo del proyecto ni a un archivo *Directory.Build.props*. Cuando se instala el paquete NuGet y la propiedad `EnableNETAnalyzers` se establece en `true`, se genera una advertencia de compilación.

## <a name="code-style-analysis"></a>Análisis de estilo de código

Las reglas de *análisis de estilo de código* ("IDExxxx") permiten definir y mantener un estilo de código coherente en el código base. Los valores de habilitación predeterminados son los siguientes:

- Compilación de línea de comandos: el análisis de estilo de código está deshabilitado de forma predeterminada para todos los proyectos de .NET en compilaciones de línea de comandos.

  A partir de .NET 5.0, puede [habilitar el análisis de estilo de código durante la compilación](#enable-on-build), tanto en la línea de comandos como en Visual Studio. Las infracciones de estilo de código aparecen como advertencias o errores con un prefijo "IDE". Esto le permite aplicar estilos de código coherentes en tiempo de compilación.

- Visual Studio: el análisis de estilo de código está habilitado, de forma predeterminada, para todos los proyectos de .NET dentro de Visual Studio como [acciones rápidas de refactorización de código](/visualstudio/ide/code-generation-in-visual-studio).

Para obtener una lista completa de las reglas de análisis de estilo de código, vea [Reglas de estilo de código](style-rules/index.md).

### <a name="enable-on-build"></a>Habilitación durante la compilación

Con el SDK de .NET 5.0 y versiones posteriores, puede habilitar el análisis de estilo de código al realizar la compilación desde la línea de comandos y en Visual Studio. (Pero por motivos de rendimiento, se seguirán aplicando [una serie de reglas de estilo de código](https://github.com/dotnet/roslyn/blob/9f87b444da9c48a4d492b19f8337339056bf2b95/src/Analyzers/Core/Analyzers/EnforceOnBuildValues.cs#L95) solo en el IDE de Visual Studio).

Siga estos pasos para habilitar el análisis de estilo de código durante la compilación:

1. Establezca la propiedad [EnforceCodeStyleInBuild](../../core/project-sdk/msbuild-props.md#enforcecodestyleinbuild) de MSBuild en `true`.

1. En un archivo *.editorconfig*, [configure](configuration-options.md) cada regla de estilo de código "IDE" que quiera ejecutar durante la compilación como una advertencia o un error. Por ejemplo:

   ```ini
   [*.{cs,vb}]
   # IDE0040: Accessibility modifiers required (escalated to a build warning)
   dotnet_diagnostic.IDE0040.severity = warning
   ```

   Como alternativa, puede configurar una categoría completa para que sea una advertencia o un error, de forma predeterminada y, después, desactivar de forma selectiva las reglas de esa categoría que no quiera que se ejecuten durante la compilación. Por ejemplo:

   ```ini
   [*.{cs,vb}]

   # Default severity for analyzer diagnostics with category 'Style' (escalated to build warnings)
   dotnet_analyzer_diagnostic.category-Style.severity = warning

   # IDE0040: Accessibility modifiers required (disabled on build)
   dotnet_diagnostic.IDE0040.severity = silent
   ```

> [!NOTE]
> La característica de análisis de estilo de código es experimental y puede cambiar entre las versiones .NET 5 y .NET 6.

## <a name="suppress-a-warning"></a>Supresión de una advertencia

Una manera de suprimir una infracción de una regla consiste en establecer la opción de gravedad del id. de esa regla en `none` en un archivo EditorConfig. Por ejemplo:

```ini
dotnet_diagnostic.CA1822.severity = none
```

Para obtener más información y otras formas de suprimir las advertencias, vea [Cómo suprimir advertencias de análisis de código](suppress-warnings.md).

## <a name="third-party-analyzers"></a>Analizadores de terceros

Además de los analizadores de .NET oficiales, también puede instalar analizadores de terceros, como [StyleCop](https://www.nuget.org/packages/StyleCop.Analyzers/), [Roslynator](https://www.nuget.org/packages/Roslynator.Analyzers/),[Analizadores de XUnit](https://www.nuget.org/packages/xunit.analyzers/) y [Sonar Analyzer](https://www.nuget.org/packages/SonarAnalyzer.CSharp/).

## <a name="see-also"></a>Vea también

- [Referencia de reglas de análisis de calidad del código](quality-rules/index.md)
- [Referencia de reglas de análisis de estilo del código](style-rules/index.md)
- [Análisis de código en Visual Studio](/visualstudio/code-quality/roslyn-analyzers-overview)
- [SDK de la plataforma del compilador de .NET](../../csharp/roslyn-sdk/index.md)
- [Tutorial: Crear el primer analizador y la corrección de código](../../csharp/roslyn-sdk/tutorials/how-to-write-csharp-analyzer-code-fix.md)
