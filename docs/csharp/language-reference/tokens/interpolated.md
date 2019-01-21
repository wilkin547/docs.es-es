---
title: '$ - Interpolación de cadenas: Referencia de C#'
ms.custom: seodec18
description: La interpolación de cadenas proporciona una sintaxis más legible y cómoda para aplicar formato al resultado de la cadena, en comparación con el formato compuesto de cadenas tradicional.
ms.date: 03/26/2018
f1_keywords:
- $_CSharpKeyword
- $
helpviewer_keywords:
- $ special character [C#]
- $ language element [C#]
- string interpolation [C#]
- interpolated string [C#]
author: pkulikov
ms.author: ronpet
ms.openlocfilehash: 97c8580b5573348e58acb85b7368eb23927cde17
ms.sourcegitcommit: 75567a3cb437009db55949c6092f4e77ed1a9da4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2019
ms.locfileid: "54307180"
---
# <a name="---string-interpolation-c-reference"></a>$ - Interpolación de cadenas (Referencia de C#)

El carácter especial `$` identifica un literal de cadena como una *cadena interpolada*. Una cadena interpolada es un literal de cadena que contiene *expresiones interpoladas*. Cuando una cadena interpolada se resuelve en una cadena de resultado, los elementos con expresiones interpoladas se reemplazan por las representaciones de cadena de los resultados de la expresión. Esta característica está disponible en C# 6 y versiones posteriores del lenguaje.

La interpolación de cadenas proporciona una sintaxis más legible y cómoda de crear cadenas con formato que si se usa la característica de [formato compuesto de cadena](../../../standard/base-types/composite-formatting.md). En este ejemplo se usan ambas características para producir el mismo resultado:

[!code-csharp-interactive[compare with composite formatting](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#1)]

## <a name="structure-of-an-interpolated-string"></a>Estructura de una cadena interpolada

Para distinguir un literal de cadena como una cadena interpolada, antepóngale el símbolo `$`. No puede haber ningún espacio en blanco entre el carácter `$` y el carácter `"` que inicia un literal de cadena. Si hay alguno, se producirá un error en tiempo de compilación.

La estructura de un elemento con una expresión interpolada es como se muestra aquí:

```
{<interpolatedExpression>[,<alignment>][:<formatString>]}
```

Los elementos entre corchetes son opcionales. En esta tabla se describe cada elemento:

|Elemento|Descripción|
|-------------|-----------------|
|`interpolatedExpression`|Expresión que genera un resultado al que se va a aplicar formato. La representación de cadena del resultado de `null` es <xref:System.String.Empty?displayProperty=nameWithType>.|
|`alignment`|La expresión constante cuyo valor define el número mínimo de caracteres en la representación de cadena del resultado de la expresión interpolada. Si es positivo, la representación de cadena está alineada a la derecha; si es negativo, está alineada a la izquierda. Para más información, vea [Alignment (Componente)](../../../standard/base-types/composite-formatting.md#alignment-component).|
|`formatString`|Cadena de formato compatible con el tipo de resultado de la expresión. Para más información, vea [Format String (Componente)](../../../standard/base-types/composite-formatting.md#format-string-component).|

En el ejemplo siguiente, se usan componentes opcionales de formato que se han descrito anteriormente:

[!code-csharp-interactive[specify alignment and format string](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#2)]

## <a name="special-characters"></a>Caracteres especiales

Para incluir una llave ("{" o "}") en el texto generado por una cadena interpolada, use dos llaves ("{{" o "}}"). Para más información, vea [Llaves de escape](../../../standard/base-types/composite-formatting.md#escaping-braces).

Como los dos puntos (":") tienen un significado especial en un elemento de expresión interpolada, para poder usar un [operador condicional](../operators/conditional-operator.md) en una expresión interpolada, incluya esa expresión entre paréntesis.

En este ejemplo, se muestra cómo incluir una llave en una cadena de resultado y cómo usar un operador condicional en una expresión interpolada:

[!code-csharp-interactive[example with ternary conditional operator](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#3)]

Las cadenas interpoladas textuales comienzan por el carácter `$`, seguido del carácter `@`. Para más información sobre las cadenas textuales, vea los temas [string](../keywords/string.md) e [Identificador textual](verbatim.md).

> [!NOTE]
> El token `$` debe aparecer antes del token `@` en una cadena interpolada textual.

## <a name="implicit-conversions-and-specifying-iformatprovider-implementation"></a>Conversiones implícitas y especificar una implementación de `IFormatProvider`

Hay tres conversiones implícitas de una cadena interpolada:

1. Conversión de una cadena interpolada a una instancia de <xref:System.String>, que es el resultado de la resolución de cadenas interpoladas con elementos de expresión interpolada que se reemplazan con las representaciones de cadena con formato correcto de sus resultados. Esta conversión usa la referencia cultural actual.

1. Conversión de una cadena interpolada a una instancia <xref:System.FormattableString> que representa una cadena de formato compuesto junto con los resultados de expresión a los que se va a aplicar formato. Esto permite crear varias cadenas de resultado con contenido específico de la referencia cultural de una sola instancia de <xref:System.FormattableString>. Para ello, llame a uno de estos métodos:

      - Una sobrecarga de <xref:System.FormattableString.ToString> que genera una cadena de resultado para <xref:System.Globalization.CultureInfo.CurrentCulture>.
      - Método <xref:System.FormattableString.Invariant%2A> que genera una cadena de resultado para <xref:System.Globalization.CultureInfo.InvariantCulture>.
      - Un método <xref:System.FormattableString.ToString(System.IFormatProvider)> que genera una cadena de resultado para una referencia cultural especificada.

    También puede usar el método <xref:System.FormattableString.ToString(System.IFormatProvider)> para proporcionar una implementación definido por el usuario de la interfaz <xref:System.IFormatProvider> que admite formatos personalizados. Para más información, vea [Formato personalizado con ICustomFormatter](../../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter).

1. Conversión de una cadena interpolada a una instancia <xref:System.IFormattable> que también permite crear varias cadenas de resultado con contenido específico de la referencia cultural de una sola instancia <xref:System.IFormattable>.

En el ejemplo siguiente, se usa la conversión implícita a <xref:System.FormattableString> para crear cadenas de resultado específicas de la referencia cultural:

[!code-csharp-interactive[create culture-specific result strings](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#4)]

## <a name="additional-resources"></a>Recursos adicionales

Si no está familiarizado con la interpolación de cadenas, vea el tutorial interactivo [Interpolación de cadenas en C#](../../tutorials/intro-to-csharp/interpolated-strings.yml). O bien, puede probar el tutorial [Interpolación de cadenas en C# ](../../tutorials/string-interpolation.md) localmente en el equipo.

## <a name="see-also"></a>Vea también

- <xref:System.String.Format%2A?displayProperty=nameWithType>
- <xref:System.FormattableString?displayProperty=nameWithType>
- <xref:System.IFormattable?displayProperty=nameWithType>
- [Formatos compuestos](../../../standard/base-types/composite-formatting.md)
- [Tabla de formatos de presentación para valores numéricos](../keywords/formatting-numeric-results-table.md)
- [Cadenas](../../programming-guide/strings/index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Caracteres especiales de C#](index.md)
- [Referencia de C#](../index.md)
