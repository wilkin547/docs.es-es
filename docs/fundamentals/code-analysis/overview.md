---
title: Análisis de código en .NET
titleSuffix: ''
description: Obtenga información sobre el análisis de código fuente en el SDK de .NET.
ms.date: 08/22/2020
ms.topic: overview
ms.custom: updateeachrelease
helpviewer_keywords:
- code analysis
- code analyzers
ms.openlocfilehash: 8efac4d5e3fddcb9fdc6e08bcc933f2776420ced
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739979"
---
# <a name="overview-of-net-source-code-analysis"></a>Información general sobre el análisis de código fuente de .NET

Los analizadores de .NET Compiler Platform (Roslyn) inspeccionan el código de C# o Visual Basic para supervisar la calidad del código y verificar si contiene problemas de estilo. A partir de .NET 5.0, estos analizadores se incluyen con el SDK de .NET. Si no desea pasar al SDK de .NET 5 o si prefiere un modelo basado en paquetes NuGet, los analizadores también están disponibles en el `Microsoft.CodeAnalysis.NetAnalyzers` [paquete Nuget](https://www.nuget.org/packages/Microsoft.CodeAnalysis.NetAnalyzers). Podría preferir un modelo basado en paquetes para las actualizaciones de versión a petición.

> [!NOTE]
> Los analizadores de .NET son independientes de la plataforma de destino. Es decir, el proyecto no necesita tener como destino una plataforma .NET específica. Los analizadores funcionan para los proyectos que tienen `net5.0` como destino y versiones anteriores de .net, como `netcoreapp` , `netstandard` y `net472` .

- [Análisis de calidad del código (reglas "CAxxxx")](#code-quality-analysis)
- [Análisis de estilo de código (reglas "IDExxxx")](#code-style-analysis)

Si un analizador encuentra infracciones de reglas, se les indica como una sugerencia, una advertencia o un error, en función de cómo esté [configurada](configuration-options.md)cada regla. Las infracciones del análisis de código aparecen con el prefijo "CA" o "IDE" para diferenciarlas de los errores del compilador.

> [!TIP]
>
> - También puede instalar analizadores de terceros, como [StyleCop](https://www.nuget.org/packages/StyleCop.Analyzers/), [Roslynator](https://www.nuget.org/packages/Roslynator.Analyzers/), [analizadores de xUnit](https://www.nuget.org/packages/xunit.analyzers/)y analizador de [Sónar](https://www.nuget.org/packages/SonarAnalyzer.CSharp/).
> - Si utiliza Visual Studio, muchas reglas del analizador tienen *correcciones de código* asociadas que puede aplicar para corregir el problema. Las correcciones de código se muestran en el menú de icono de bombilla.

## <a name="code-quality-analysis"></a>Análisis de calidad del código

_Las reglas de análisis de calidad del código ("CA")_ inspeccionan el código de C# o Visual Basic para la seguridad, el rendimiento, el diseño y otros problemas. De forma predeterminada, el análisis se habilita para los proyectos que tienen como destino .NET 5,0 o posterior. Puede habilitar el análisis de código en los proyectos que tienen como destino versiones anteriores de .NET estableciendo la propiedad [EnableNETAnalyzers](../../core/project-sdk/msbuild-props.md#enablenetanalyzers) en `true` . También puede deshabilitar el análisis de código del proyecto si establece `EnableNETAnalyzers` en `false` .

> [!TIP]
> En Visual Studio, puede habilitar o deshabilitar el análisis de código mediante el ventana Propiedades del proyecto. Para acceder al ventana Propiedades del proyecto, haga clic con el botón derecho en un proyecto de Explorador de soluciones y seleccione **propiedades**. A continuación, seleccione la pestaña **análisis de código** y, a continuación, Active o desactive la casilla para **habilitar los analizadores de .net**.

### <a name="enabled-rules"></a>Reglas habilitadas

Las siguientes reglas están habilitadas de forma predeterminada en .NET 5,0 Preview 8.

| Id. de diagnóstico | Category | severity | Descripción |
| - | - | - | - |
| [CA1416](/visualstudio/code-quality/ca1416) | Interoperabilidad | Advertencia | Analizador de compatibilidad de plataformas |
| [CA1417](/visualstudio/code-quality/ca1417) | Interoperabilidad | Advertencia | No usar `OutAttribute` en parámetros de cadena para P/Invoke |
| [CA1831](/visualstudio/code-quality/ca1831) | Rendimiento | Advertencia | Use `AsSpan` en lugar de indizadores basados en intervalos para la cadena cuando corresponda. |
| [CA2013](/visualstudio/code-quality/ca2013) | Confiabilidad | Advertencia | No usar `ReferenceEquals` con tipos de valor |
| [CA2014](/visualstudio/code-quality/ca2014) | Confiabilidad | Advertencia | No usar `stackalloc` en bucles |
| [CA2015](/visualstudio/code-quality/ca2015) | Confiabilidad | Advertencia | No defina finalizadores para los tipos derivados de <xref:System.Buffers.MemoryManager%601> |
| [CA2200](/visualstudio/code-quality/ca2200) | Uso | Advertencia | Reiniciar para mantener los detalles de la pila
| [CA2247](/visualstudio/code-quality/ca2247) | Uso | Advertencia | El argumento pasado al constructor TaskCompletionSource debe ser <xref:System.Threading.Tasks.TaskCreationOptions> enum en lugar de <xref:System.Threading.Tasks.TaskContinuationOptions> |

Puede cambiar la gravedad de estas reglas para deshabilitarlas o elevarlas a errores.

Para obtener una lista completa de las reglas de calidad de código disponibles, consulte [reglas de calidad del código](quality-rules/index.md).

### <a name="enable-additional-rules"></a>Habilitar reglas adicionales

A partir de .NET 5.0 RC2, el SDK de .NET incluye todas las [reglas "CA" de calidad del código](/visualstudio/code-quality/code-analysis-for-managed-code-warnings). Para obtener una lista completa de las reglas que se incluyen con cada versión del SDK de .NET, vea [versiones del analizador](https://github.com/dotnet/roslyn-analyzers/blob/master/src/NetAnalyzers/Core/AnalyzerReleases.Shipped.md).

#### <a name="default-analysis-mode"></a>Modo de análisis predeterminado

En el modo de análisis predeterminado, algunas reglas están [habilitadas de forma predeterminada](#enabled-rules) como advertencias de compilación. Algunas otras reglas están habilitadas de forma predeterminada solo como sugerencias del IDE de Visual Studio con las correcciones de código correspondientes. Las reglas restantes están deshabilitadas de forma predeterminada. La [lista completa de reglas](https://github.com/dotnet/roslyn-analyzers/blob/master/src/NetAnalyzers/Core/AnalyzerReleases.Shipped.md) incluye la gravedad predeterminada de cada regla y si la regla está habilitada o no de forma predeterminada en el modo de análisis predeterminado.

#### <a name="custom-analysis-mode"></a>Modo de análisis personalizado

Puede [Configurar reglas de análisis de código](configuration-options.md) para habilitar o deshabilitar una regla individual o una categoría de reglas. Además, puede usar la propiedad [AnalysisMode](../../core/project-sdk/msbuild-props.md#analysismode) para cambiar a uno de los siguientes modos de análisis personalizado:

- Modo _agresivo_ o _de exclusión_ : todas las reglas están habilitadas de forma predeterminada como advertencias de compilación. Puede [excluir](configuration-options.md) de forma selectiva reglas individuales para deshabilitarlas.
- Modo _conservador_ o _de participación_ : todas las reglas están deshabilitadas de forma predeterminada. Puede [incluir](configuration-options.md) de forma selectiva reglas individuales para habilitarlas.

### <a name="treat-warnings-as-errors"></a>Tratar advertencias como errores

Si usa la `-warnaserror` marca al compilar los proyectos, todas las advertencias de análisis de código también se tratan como errores. Si no desea que las advertencias de calidad del código (CAxxxx) se traten como errores en presencia de `-warnaserror` , puede establecer la `CodeAnalysisTreatWarningsAsErrors` propiedad de MSBuild en `false` en el archivo del proyecto.

```xml
<PropertyGroup>
  <CodeAnalysisTreatWarningsAsErrors>false</CodeAnalysisTreatWarningsAsErrors>
</PropertyGroup>
```

Seguirá viendo advertencias de análisis de código, pero no interrumpirá la compilación.

### <a name="latest-updates"></a>Actualizaciones más recientes

De forma predeterminada, obtendrá las reglas de análisis de código más recientes y las gravedades de las reglas predeterminadas a medida que actualice a las versiones más recientes del SDK de .NET. Si no desea este comportamiento, por ejemplo, si desea asegurarse de que no hay nuevas reglas habilitadas o deshabilitadas, puede invalidarlo de una de las siguientes maneras:

- Establezca la `AnalysisLevel` propiedad MSBuild en un valor específico para bloquear las advertencias a ese conjunto. Al actualizar a un SDK más reciente, todavía obtendrá correcciones de errores para esas advertencias, pero no se habilitarán nuevas advertencias y no se deshabilitarán las advertencias existentes. Por ejemplo, para bloquear el conjunto de reglas a las que se incluyen en la versión 5,0 del SDK de .NET, agregue la entrada siguiente al archivo de proyecto.

  ```xml
  <PropertyGroup>
    <AnalysisLevel>5.0</AnalysisLevel>
  </PropertyGroup>
  ```

  > [!TIP]
  > El valor predeterminado de la `AnalysisLevel` propiedad es `latest` , lo que significa que siempre obtendrá las reglas de análisis de código más recientes al pasar a las versiones más recientes del SDK de .net.

  Para obtener más información y para ver una lista de los valores posibles, vea [AnalysisLevel](../../core/project-sdk/msbuild-props.md#analysislevel).

- Instale el [paquete NuGet Microsoft. CodeAnalysis. NetAnalyzers](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisnetanalyzers) para desacoplar las actualizaciones de reglas de las actualizaciones del SDK de .net. Al instalar el paquete, se desactivan los analizadores integrados del SDK y se genera una advertencia de compilación si el SDK contiene una versión más reciente del ensamblado del analizador que la del paquete NuGet.

## <a name="code-style-analysis"></a>Análisis de estilo de código

Las reglas de [análisis de estilo de código](/visualstudio/ide/editorconfig-code-style-settings-reference) ("IDExxxx") permiten definir y mantener un estilo de código coherente en el código base. A continuación se muestran los valores predeterminados:

- Compilación de línea de comandos: el análisis de estilo de código está deshabilitado de forma predeterminada para todos los proyectos de .NET en compilaciones de línea de comandos.
- Visual Studio: el análisis de estilo de código está habilitado, de forma predeterminada, para todos los proyectos de .NET dentro de Visual Studio como [acciones rápidas de refactorización de código](/visualstudio/ide/code-generation-in-visual-studio).

A partir de .NET 5,0 RC2, puede habilitar el análisis de estilo de código en la compilación, tanto en la línea de comandos como en Visual Studio. Las infracciones de estilo de código aparecen como advertencias o errores con un prefijo "IDE". Esto le permite aplicar estilos de código coherentes en tiempo de compilación.

> [!NOTE]
> La característica de análisis de estilo de código es experimental y puede cambiar entre las versiones .NET 5 y .NET 6.

Pasos para habilitar el análisis de estilo de código en la compilación:

1. Establezca la propiedad de MSBuild [EnforceCodeStyleInBuild](../../core/project-sdk/msbuild-props.md#enforcecodestyleinbuild) en `true` .

1. En un archivo *. editorconfig* , [Configure](configuration-options.md) cada regla de estilo de código "IDE" que desee ejecutar en la compilación como una advertencia o un error. Por ejemplo:

   ```ini
   [*.{cs,vb}]
   # IDE0040: Accessibility modifiers required (escalated to a build warning)
   dotnet_diagnostic.IDE0040.severity = warning
   ```

   Como alternativa, puede configurar la categoría de "estilo" completa como advertencia o error, de forma predeterminada y, a continuación, desactivar selectivamente las reglas que no desea que se ejecuten en la compilación. Por ejemplo:

   ```ini
   [*.{cs,vb}]

   # Default severity for analyzer diagnostics with category 'Style' (escalated to build warnings)
   dotnet_analyzer_diagnostic.category-Style.severity = warning

   # IDE0040: Accessibility modifiers required (disabled on build)
   dotnet_diagnostic.IDE0040.severity = silent
   ```

## <a name="suppress-a-warning"></a>Suprimir una advertencia

Para suprimir una infracción de regla, establezca la opción Severity para ese ID `none` . de regla en en un archivo EditorConfig. Por ejemplo:

```ini
dotnet_diagnostic.CA1822.severity = none
```

Visual Studio proporciona formas adicionales de suprimir las advertencias de las reglas de análisis de código. Para obtener más información, vea [suprimir infracciones](/visualstudio/code-quality/use-roslyn-analyzers#suppress-violations).

Para obtener más información sobre los niveles de gravedad de las reglas, consulte [configurar la gravedad](configuration-options.md#severity-level)de la regla.

## <a name="see-also"></a>Consulte también

- [Referencia de reglas de análisis de calidad de código](quality-rules/index.md)
- [Referencia de reglas de análisis de estilo de código](style-rules/index.md)
- [Análisis de código en Visual Studio](/visualstudio/code-quality/roslyn-analyzers-overview)
- [SDK de la plataforma del compilador de .NET](../../csharp/roslyn-sdk/index.md)
- [Tutorial: Crear el primer analizador y la corrección de código](../../csharp/roslyn-sdk/tutorials/how-to-write-csharp-analyzer-code-fix.md)
