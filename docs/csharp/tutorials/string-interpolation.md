---
title: Interpolación de cadenas en C#
description: Obtenga información sobre cómo incluir resultados de expresión con formato en una cadena de resultado en C# con la interpolación de cadenas.
author: pkulikov
ms.date: 05/09/2018
ms.openlocfilehash: 447e87cd4aae49896f0efbb8ece6097181079266
ms.sourcegitcommit: ff1d40507b3eb6e2185478e37c66c66be6de46f1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2018
ms.locfileid: "34058944"
---
# <a name="string-interpolation-in-c"></a>Interpolación de cadenas en C# #

En este tutorial se explica cómo usar la [interpolación de cadenas](../language-reference/tokens/interpolated.md) para dar formato a resultados de expresión e incluirlos en una cadena de resultado. En los ejemplos se da por hecho que ya está familiarizado con los conceptos básicos de C# y el formato de tipos .NET. Si no conoce la interpolación de cadenas o el formato de tipos .NET, vea antes el [inicio rápido de interpolación de cadenas interactivo](../quick-starts/interpolated-strings.yml). Para más información sobre cómo aplicar formato a tipos .NET, vea el tema [Aplicar formato a tipos en .NET](../../standard/base-types/formatting-types.md).

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

## <a name="introduction"></a>Introducción

La característica de [interpolación de cadenas](../language-reference/tokens/interpolated.md) se basa en la característica de [formato compuesto](../../standard/base-types/composite-formatting.md) y proporciona una sintaxis más legible y cómoda para incluir resultados de expresiones con formato en una cadena de resultado.

Para distinguir un literal de cadena como una cadena interpolada, antepóngale el símbolo `$`. Puede insertar cualquier expresión de C# válida que devuelva un valor en una cadena interpolada. En el siguiente ejemplo, en cuanto la expresión se evalúa, su resultado se convierte en una cadena y se incluye en una cadena de resultado:

[!code-csharp-interactive[string interpolation example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#1)]

Como se ilustra en el ejemplo, para incluir una expresión en una cadena interpolada hay que meterla entre llaves:

```
{<interpolatedExpression>}
```

En tiempo de compilación, una cadena interpolada se suele transformar en una llamada de método <xref:System.String.Format%2A?displayProperty=nameWithType>, lo que permite que todas las capacidades de la característica de [formato compuesto de cadena](../../standard/base-types/composite-formatting.md) estén disponibles para su uso también con cadenas interpoladas.

## <a name="how-to-specify-a-format-string-for-an-interpolated-expression"></a>Cómo especificar una cadena de formato para una expresión interpolada

Para especificar una cadena de formato compatible con el tipo de resultado de expresión, coloque después de la expresión interpolada dos puntos (":") y la cadena de formato:

```
{<interpolatedExpression>:<formatString>}
```

En el siguiente ejemplo se muestra cómo especificar cadenas de formato estándar y personalizadas para expresiones que generan resultados numéricos o de fecha y hora:

[!code-csharp-interactive[format string example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#2)]

Para más información, vea la sección [Format String (Componente)](../../standard/base-types/composite-formatting.md#format-string-component) del tema [Formatos compuestos](../../standard/base-types/composite-formatting.md). En esa sección encontrará vínculos a temas en los que se describen las cadenas de formato estándar y personalizadas compatibles con los tipos base .NET.

## <a name="how-to-control-the-field-width-and-alignment-of-the-formatted-interpolated-expression"></a>Cómo controlar el ancho de campo y la alineación de las expresiones interpoladas con formato

Para especificar el ancho de campo mínimo y la alineación del resultado de expresión con formato, coloque después de la expresión interpolada una coma puntos (",") y la expresión constante:

```
{<interpolatedExpression>,<alignment>}
```

Si el valor de *alignment* es positivo, el resultado de la expresión con formato se alineará a la derecha y, si es negativo, lo hará a la izquierda.

En caso de que haya que especificar una alineación y una cadena de formato, comience por el componente de alineación:

```
{<interpolatedExpression>,<alignment>:<formatString>}
```

En el siguiente ejemplo se muestra cómo especificar la alineación y se emplean caracteres de barra vertical ("|") para delimitar los campos de texto:

[!code-csharp-interactive[alignment example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#3)]

Tal y como refleja la salida del ejemplo, si la longitud del resultado de expresión con formato supera el ancho de campo especificado, se omitirá el valor de *alignment*.

Para más información, vea la sección [Alignment (Componente)](../../standard/base-types/composite-formatting.md#alignment-component) del tema [Formatos compuestos](../../standard/base-types/composite-formatting.md).

## <a name="how-to-use-escape-sequences-in-an-interpolated-string"></a>Cómo usar secuencias de escape en una cadena interpolada

Las cadenas interpoladas admiten todas las secuencias de escape que se usan en los literales de cadena ordinarios. Para más información, vea [Secuencias de escape de cadena](../programming-guide/strings/index.md#string-escape-sequences).

Para interpretar las secuencias de escape literalmente, use un literal de cadena [textual](../language-reference/tokens/verbatim.md). Las cadenas interpoladas textuales comienzan por el carácter `$`, seguido del carácter `@`.

Para incluir una llave ("{" o "}") en una cadena de resultado, use dos llaves ("{{" o "}}"). Para más información, vea la sección [Llaves de escape](../../standard/base-types/composite-formatting.md#escaping-braces) del tema [Formatos compuestos](../../standard/base-types/composite-formatting.md).

En el siguiente ejemplo se muestra cómo incluir llaves en una cadena de resultado y cómo construir una cadena interpolada textual:

[!code-csharp-interactive[escape sequence example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#4)]

## <a name="how-to-use-a-ternary-conditional-operator--in-an-interpolated-expression"></a>Cómo usar un operador condicional ternario `?:` en una expresión interpolada

Dado que los dos puntos (:) tienen un significado especial en un elemento con una expresión interpolada, para poder usar un [operador condicional](../language-reference/operators/conditional-operator.md) en una expresión de este tipo, habrá que ponerlo entre paréntesis, como vemos en el siguiente ejemplo:

[!code-csharp-interactive[conditional operator example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#5)]

## <a name="how-to-create-a-culture-specific-result-string-with-string-interpolation"></a>Cómo crear una cadena de resultado específica de la referencia cultural con interpolación de cadenas

Las cadenas interpoladas usan de forma predeterminada la referencia cultural definida actualmente por la propiedad <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=nameWithType> en todas las operaciones de formato. Use la conversión implícita de una cadena interpolada en una instancia de <xref:System.FormattableString?displayProperty=nameWithType> y llame al método <xref:System.FormattableString.ToString(System.IFormatProvider)> correspondiente para crear una cadena de resultado específica de referencia cultural. En el siguiente ejemplo se muestra cómo hacerlo:

[!code-csharp-interactive[specify different cultures](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#6)]

Tal y como se muestra en el ejemplo, se puede usar una instancia de <xref:System.FormattableString> para generar varias cadenas de resultado para varias referencias culturales.

## <a name="how-to-create-a-result-string-using-the-invariant-culture"></a>Cómo crear una cadena de resultado usando la referencia de cultura invariable

Puede usar el método estático <xref:System.FormattableString.Invariant%2A?displayProperty=nameWithType> junto con el método <xref:System.FormattableString.ToString(System.IFormatProvider)?displayProperty=nameWithType> para resolver una cadena interpolada en una cadena de resultado de <xref:System.Globalization.CultureInfo.InvariantCulture>. En el siguiente ejemplo se muestra cómo hacerlo:

[!code-csharp-interactive[format with invariant culture](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#7)]

## <a name="conclusion"></a>Conclusión

En este tutorial se han descrito escenarios habituales en los que se usa la interpolación de cadenas. Para más información sobre la interpolación de cadenas, vea el tema [Interpolación de cadenas](../language-reference/tokens/interpolated.md). Para más información sobre cómo aplicar formato a tipos .NET, vea los temas [Aplicar formato a tipos en .NET](../../standard/base-types/formatting-types.md) y [Formatos compuestos](../../standard/base-types/composite-formatting.md).

## <a name="see-also"></a>Vea también

<xref:System.String.Format%2A?displayProperty=nameWithType>  
<xref:System.FormattableString?displayProperty=nameWithType>  
<xref:System.IFormattable?displayProperty=nameWithType>  
[Cadenas](../programming-guide/strings/index.md)  
