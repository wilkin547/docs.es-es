---
description: Opciones del compilador de C# para errores y advertencias. Estas opciones suprimen o habilitan las advertencias y controlan las advertencias como errores.
title: 'Opciones del compilador de C#: errores y advertencias'
ms.date: 03/12/2021
f1_keywords:
- cs.build.options
helpviewer_keywords:
- WarningLevel compiler option [C#]
- TreatWarningsAsErrors compiler option [C#]
- WarningsAsErrors compiler option [C#]
- WarningsNotAsErrors compiler option [C#]
- DisabledWarnings compiler option [C#]
- CodeAnalysisRuleSet compiler option [C#]
- ErrorLog compiler option [C#]
- ReportAnalyzer compiler option [C#]
ms.openlocfilehash: 2bdda13d6b8b2b75d80c228da678a5b7fbcb8892
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103482496"
---
# <a name="c-compiler-options-to-report-errors-and-warnings"></a>Opciones del compilador de C#: notificación de errores y advertencias

Las opciones siguientes controlan cómo el compilador notifica los errores y las advertencias. La nueva sintaxis de MSBuild se muestra en **negrita**. La sintaxis de *csc.exe* anterior se muestra en `code style`.

- **WarningLevel** / `-warn`: se establece el nivel de advertencia.
- **TreatWarningsAsErrors** / `-warnaserror`: todas las advertencias se tratan como errores.
- **WarningsAsErrors** / `-warnaserror`: una o varias advertencias se tratan como errores
- **WarningsNotAsErrors** / `-warnaserror`: una o varias advertencias no se tratan como errores
- **DisabledWarnings** / `-nowarn`: se establece una lista de advertencias deshabilitadas.
- **CodeAnalysisRuleSet** / `-ruleset`: se especifica un archivo de conjunto de reglas que deshabilita diagnósticos específicos.
- **ErrorLog** / `-errorlog`: se especifica un archivo para registrar todos los diagnósticos del compilador y el analizador.
- **ReportAnalyzer** / `-reportanalyzer`: se notifica información adicional del analizador, como el tiempo de ejecución.

## <a name="warninglevel"></a>WarningLevel

La opción **WarningLevel** especifica el nivel de advertencia que debe mostrar el compilador.

```xml
<WarningLevel>3</WarningLevel>
```

El valor del elemento es el nivel de advertencia que quiere que se muestre para la compilación: los números más bajos muestran solo advertencias de gravedad alta. Los números más altos muestran más advertencias. El valor debe ser cero o un entero positivo:

|Nivel de advertencia|Significado|
|-------------------|-------------|
|0|Desactiva la emisión de todos los mensajes de advertencia.|
|1|Muestra mensajes de advertencia graves.|  
|2|Muestra advertencias de nivel 1 además de determinadas advertencias menos graves, como advertencias sobre ocultar miembros de clase.|
|3|Muestra advertencias de nivel 2 además de determinadas advertencias menos graves, como advertencias sobre expresiones que siempre se evalúan como `true` o `false`.|
|4 (el valor predeterminado)|Muestra todas las advertencias de nivel 3 además de advertencias informativas.|
|5|Muestra las advertencias de nivel 4, además de [advertencias adicionales](https://github.com/dotnet/roslyn/blob/a6013f3213c902c0973b2d371c3007217d610533/docs/compilers/CSharp/Warnversion%20Warning%20Waves.md) del compilador incluido con C# 9.0.|
|Mayor que 5|Cualquier valor mayor que 5 se tratará como 5. Para asegurarse de que siempre reciba todas las advertencias si el compilador se actualiza con nuevos niveles de advertencia, proporciona un valor grande arbitrario (por ejemplo, `9999`).

Para obtener información sobre un error o advertencia, puede buscar el código de error en el Índice de la Ayuda. Para conocer otras maneras de obtener información sobre un error o advertencia, vea [Errores del compilador de C#](../compiler-messages/index.md). Use [**TreatWarningsAsErrors**](#treatwarningsaserrors) para tratar todas las advertencias como errores. Use [**DisabledWarnings**](#disabledwarnings) para deshabilitar advertencias concretas.  

## <a name="treatwarningsaserrors"></a>TreatWarningsAsErrors

La opción **TreatWarningsAsErrors** trata todas las advertencias como errores. También puede usar **TreatWarningsAsErrors** para establecer solo algunas advertencias como errores. Si activa **TreatWarningsAsErrors**, puede usar **TreatWarningsAsErrors** para enumerar las advertencias que no se deben tratar como errores.

```xml
<TreatWarningsAsErrors></TreatWarningsAsErrors>
```

En su lugar, todos los mensajes de advertencia se notifican como errores. El proceso de compilación se detiene (no se genera ningún archivo de salida). De forma predeterminada, **TreatWarningsAsErrors** no está en efecto, lo que significa que las advertencias no impedirán la generación de un archivo de salida. Opcionalmente, si solo quiere que algunas advertencias específicas se traten como errores, puede especificar una lista separada por comas de números de advertencia que se tratarán como errores. Se puede especificar el conjunto de todas las advertencias de nulabilidad con la abreviatura [**Nullable**](language.md#nullable). Use [**WarningLevel**](#warninglevel) para especificar el nivel de advertencias que quiere que muestre el compilador. Use [**DisabledWarnings**](#disabledwarnings) para deshabilitar advertencias concretas.

## <a name="warningsaserrors-and-warningsnotaserrors"></a>WarningsAsErrors y WarningsNotAsErrors

Las opciones **WarningsAsErrors** y **WarningsNotAsErrors** invalidan la opción **TreatWarningsAsErrors** de una lista de advertencias.

Habilite las advertencias 0219 y 0168 como errores:

```xml
<WarningsAsErrors>0219,0168</WarningsAsErrors>
```

Deshabilite las mismas advertencias como errores:

```xml
<WarningsNotAsErrors>0219,0168</WarningsNotAsErrors>
```

Use **WarningsAsErrors** para configurar un conjunto de advertencias como errores. Use **WarningsNotAsErrors** para configurar un conjunto de advertencias que no deben ser errores cuando se han establecido todas las advertencias como errores.

## <a name="disabledwarnings"></a>DisabledWarnings

La opción **DisabledWarnings** permite impedir que el compilador muestre una o más advertencias. Separe varios números de advertencia con una coma.

```xml
<DisabledWarnings>number1, number2</DisabledWarnings>
```

`number1`, `number2` Números de advertencia que quiere que el compilador suprima. Debe especificar la parte numérica del identificador de advertencia. Por ejemplo, si quiere suprimir *CS0028*, podría especificar `<DisabledWarnings>28</DisabledWarnings>`. El compilador omitirá silenciosamente los números de advertencia pasados a **DisabledWarnings** que eran válidos en versiones anteriores, pero que se han quitado. Por ejemplo, *CS0679* era válido en el compilador de Visual Studio .NET 2002, pero se ha eliminado posteriormente.

 Las advertencias siguientes no se pueden suprimir mediante la opción **DisabledWarnings**:

- Advertencia del compilador (nivel 1) CS2002  
- Advertencia del compilador (nivel 1) CS2023
- Advertencia del compilador (nivel 1) CS2029

## <a name="codeanalysisruleset"></a>CodeAnalysisRuleSet

Especifica un archivo de conjunto de reglas que configura diagnósticos específicos.

```xml
<CodeAnalysisRuleSet>MyConfiguration.ruleset</CodeAnalysisRuleSet>
```

`MyConfiguration.ruleset` es la ruta del archivo de conjunto de reglas. Para obtener más información sobre el uso de conjuntos de reglas, vea el artículo en la [documentación de Visual Studio sobre conjuntos de reglas](/visualstudio/code-quality/using-rule-sets-to-group-code-analysis-rules).

## <a name="errorlog"></a>ErrorLog

Especifique un archivo para registrar todos los diagnósticos del compilador y el analizador.

```xml
<ErrorLog>MyConfiguration.ruleset</ErrorLog>
```

La opción **ErrorLog** hace que el compilador genere un [registro de formato de intercambio de resultados de análisis estático (SARIF)](https://github.com/microsoft/sarif-tutorials/blob/main/docs/1-Introduction.md#:~:text=What%20is%20SARIF%3F,for%20use%20by%20simpler%20tools). Los registros SARIF suelen ser leídos por herramientas que analizan los resultados de los diagnósticos del compilador y el analizador.

## <a name="reportanalyzer"></a>ReportAnalyzer

Notifica información adicional del analizador, como el tiempo de ejecución.

```xml
<ReportAnalyzer>true</ReportAnalyzer>
```

La opción **ReportAnalyzer** hace que el compilador emita información de registro de MSBuild adicional en la que se detallan las características de rendimiento de los analizadores de la compilación. Los creadores del analizador la usan normalmente como parte de la validación del analizador.
