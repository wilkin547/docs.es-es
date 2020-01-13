---
title: '$ - Interpolación de cadenas: referencia de C#'
description: La interpolación de cadenas proporciona una sintaxis más legible y cómoda para aplicar formato al resultado de la cadena, en comparación con el formato compuesto de cadenas tradicional.
ms.date: 09/02/2019
f1_keywords:
- $_CSharpKeyword
- $
helpviewer_keywords:
- $ special character [C#]
- string interpolation [C#]
- interpolated string [C#]
author: pkulikov
ms.openlocfilehash: b32bbbb0bd99878822d7ca5abdba80b46539846a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715085"
---
# <a name="---string-interpolation-c-reference"></a>$ - Interpolación de cadenas: referencia de C#

El carácter especial `$` identifica un literal de cadena como una *cadena interpolada*. Una cadena interpolada es un literal de cadena que puede contener *expresiones de interpolación*. Cuando una cadena interpolada se resuelve en una cadena de resultado, los elementos con expresiones de interpolación se reemplazan por las representaciones de cadena de los resultados de la expresión. Esta característica está disponible a partir de C# 6.

La interpolación de cadenas proporciona una sintaxis más legible y cómoda de crear cadenas con formato que si se usa la característica de [formato compuesto de cadena](../../../standard/base-types/composite-formatting.md). En este ejemplo se usan ambas características para producir el mismo resultado:

[!code-csharp-interactive[compare with composite formatting](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#1)]

## <a name="structure-of-an-interpolated-string"></a>Estructura de una cadena interpolada

Para distinguir un literal de cadena como una cadena interpolada, antepóngale el símbolo `$`. No puede haber ningún espacio en blanco entre el carácter `$` y el carácter `"` que inicia un literal de cadena.

La estructura de un elemento con una expresión de interpolación es como se muestra aquí:

```csharp
{<interpolationExpression>[,<alignment>][:<formatString>]}
```

Los elementos entre corchetes son opcionales. En esta tabla se describe cada elemento:

|Elemento|Descripción|
|-------------|-----------------|
|`interpolationExpression`|Expresión que genera un resultado al que se va a aplicar formato. La representación de cadena de `null` es <xref:System.String.Empty?displayProperty=nameWithType>.|
|`alignment`|La expresión constante cuyo valor define el número mínimo de caracteres en la representación de cadena del resultado de la expresión. Si es positivo, la representación de cadena está alineada a la derecha; si es negativo, está alineada a la izquierda. Para más información, vea [Alignment (Componente)](../../../standard/base-types/composite-formatting.md#alignment-component).|
|`formatString`|Cadena de formato compatible con el tipo de resultado de la expresión. Para más información, vea [Format String (Componente)](../../../standard/base-types/composite-formatting.md#format-string-component).|

En el ejemplo siguiente, se usan componentes opcionales de formato que se han descrito anteriormente:

[!code-csharp-interactive[specify alignment and format string](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#2)]

## <a name="special-characters"></a>Caracteres especiales

Para incluir una llave ("{" o "}") en el texto generado por una cadena interpolada, use dos llaves ("{{" o "}}"). Para más información, vea [Llaves de escape](../../../standard/base-types/composite-formatting.md#escaping-braces).

Como los dos puntos (":") tienen un significado especial en un elemento de expresión de interpolación, para poder usar un [operador condicional](../operators/conditional-operator.md) en una expresión de interpolación, incluya esa expresión entre paréntesis.

En este ejemplo, se muestra cómo incluir una llave en una cadena de resultado y cómo usar un operador condicional en una expresión de interpolación:

[!code-csharp-interactive[example with ternary conditional operator](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#3)]

Las cadenas textuales interpoladas comienzan por el carácter `$`, seguido del carácter `@`. Para más información sobre las cadenas textuales, vea los temas [string](../builtin-types/reference-types.md) e [Identificador textual](verbatim.md).

> [!NOTE]
> A partir de C# 8.0, puede usar los tokens `$` y `@` en cualquier orden; tanto `$@"..."` como `@$"..."` son cadenas textuales interpoladas válidas. En versiones de C# anteriores, el token `$` debe aparecer delante del token `@`.

## <a name="implicit-conversions-and-how-to-specify-iformatprovider-implementation"></a>Conversiones implícitas y cómo especificar la implementación de `IFormatProvider`

Hay tres conversiones implícitas de una cadena interpolada:

1. Conversión de una cadena interpolada a una instancia de <xref:System.String>, que es el resultado de la resolución de cadenas interpoladas con elementos de expresión de interpolación que se reemplazan con las representaciones de cadena con formato correcto de sus resultados. Esta conversión utiliza <xref:System.Globalization.CultureInfo.CurrentCulture> para dar formato a los resultados de la expresión.

1. Conversión de una cadena interpolada a una instancia <xref:System.FormattableString> que representa una cadena de formato compuesto junto con los resultados de expresión a los que se va a aplicar formato. Esto permite crear varias cadenas de resultado con contenido específico de la referencia cultural de una sola instancia de <xref:System.FormattableString>. Para ello, llame a uno de estos métodos:

      - Una sobrecarga de <xref:System.FormattableString.ToString> que genera una cadena de resultado para <xref:System.Globalization.CultureInfo.CurrentCulture>.
      - Método <xref:System.FormattableString.Invariant%2A> que genera una cadena de resultado para <xref:System.Globalization.CultureInfo.InvariantCulture>.
      - Un método <xref:System.FormattableString.ToString(System.IFormatProvider)> que genera una cadena de resultado para una referencia cultural especificada.

    También puede usar el método <xref:System.FormattableString.ToString(System.IFormatProvider)> para proporcionar una implementación definido por el usuario de la interfaz <xref:System.IFormatProvider> que admite formatos personalizados. Para más información, consulte la sección [Formato personalizado con ICustomFormatter](../../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter) del artículo [Aplicar formato a tipos en .NET](../../../standard/base-types/formatting-types.md).

1. Conversión de una cadena interpolada a una instancia <xref:System.IFormattable> que también permite crear varias cadenas de resultado con contenido específico de la referencia cultural de una sola instancia <xref:System.IFormattable>.

En el ejemplo siguiente, se usa la conversión implícita a <xref:System.FormattableString> para crear cadenas de resultado específicas de la referencia cultural:

[!code-csharp-interactive[create culture-specific result strings](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#4)]

## <a name="additional-resources"></a>Recursos adicionales

Si no está familiarizado con la interpolación de cadenas, vea el tutorial interactivo [Interpolación de cadenas en C#](../../tutorials/exploration/interpolated-strings.yml). También puede consultar otro tutorial de [interpolación de cadenas en C#](../../tutorials/string-interpolation.md) que muestra cómo usar cadenas interpoladas para generar cadenas con formato.

## <a name="compilation-of-interpolated-strings"></a>Compilación de cadenas interpoladas

Si una cadena interpolada tiene el tipo `string`, normalmente se transforma en una llamada de método <xref:System.String.Format%2A?displayProperty=nameWithType>. El compilador puede reemplazar <xref:System.String.Format%2A?displayProperty=nameWithType> por <xref:System.String.Concat%2A?displayProperty=nameWithType> si el comportamiento analizado es equivalente a una concatenación.

Si una cadena interpolada tiene el tipo <xref:System.IFormattable> o <xref:System.FormattableString>, el compilador genera una llamada al método <xref:System.Runtime.CompilerServices.FormattableStringFactory.Create%2A?displayProperty=nameWithType>.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, vea la sección [Interpolated strings](~/_csharplang/spec/expressions.md#interpolated-strings) (Cadenas interpoladas) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Caracteres especiales de C#](index.md)
- [Cadenas](../../programming-guide/strings/index.md)
- [Tabla de formatos de presentación para valores numéricos](../keywords/formatting-numeric-results-table.md)
- [Formatos compuestos](../../../standard/base-types/composite-formatting.md)
- <xref:System.String.Format%2A?displayProperty=nameWithType>
