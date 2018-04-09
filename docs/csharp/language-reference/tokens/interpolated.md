---
title: $ - Interpolación de cadenas (Referencia de C#)
description: La interpolación de cadenas proporciona una sintaxis más legible y cómoda para aplicar formato al resultado de la cadena, en comparación con el formato compuesto de cadenas tradicional.
ms.date: 03/26/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- $_CSharpKeyword
- $
helpviewer_keywords:
- $ special character [C#]
- $ language element [C#]
- string interpolation [C#]
- interpolated string [C#]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b6873c3b419323fa9f5523143ad607289b6fd6e2
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="---string-interpolation-c-reference"></a>$ - Interpolación de cadenas (Referencia de C#)

El carácter especial `$` identifica un literal de cadena como una *cadena interpolada*. Una cadena interpolada es similar a una cadena de plantilla que contiene *expresiones interpoladas*. Cuando se resuelve la cadena interpolada, como por ejemplo en una instrucción de asignación o una llamada de método, las expresiones interpoladas se reemplazan por las representaciones de cadena de sus resultados para generar la cadena de resultado. Esta característica está disponible en C# 6 y versiones posteriores.

La interpolación de cadenas es una manera más legible y cómoda de crear cadenas con formato que si se usa la característica [formato de compuesto de cadena](../../../standard/base-types/composite-formatting.md). En este ejemplo se usan ambas características para producir el mismo resultado:

[!code-csharp-interactive[compare with composite formatting](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#1)]

> [!NOTE]
> No puede haber ningún espacio en blanco entre el carácter `$` y el carácter `"` que inicia la cadena. Si hay alguno, se producirá un error en tiempo de compilación.

La estructura de un elemento con una expresión interpolada es como se muestra aquí:

```
{<interpolatedExpression>[,<alignment>][:<formatString>]}
```

Los elementos entre corchetes son opcionales. En esta tabla se describe cada elemento.

|Elemento|Description|
|-------------|-----------------|
|`interpolatedExpression`|La expresión que se va a evaluar para obtener un resultado al que se va a aplicar formato. La representación de cadena del resultado de `null` es <xref:System.String.Empty?displayProperty=nameWithType>.|
|`alignment`|La expresión constante cuyo valor define el número mínimo de caracteres en la representación de cadena del resultado de la expresión interpolada. Si es positivo, la representación de cadena está alineada a la derecha; si es negativo, está alineada a la izquierda. Para más información, vea [Alignment (Componente)](../../../standard/base-types/composite-formatting.md#alignment-component).|
|`formatString`|Una cadena de formato estándar o personalizado que sea compatible con el tipo de resultado de la expresión. Para más información, vea [Format String (Componente)](../../../standard/base-types/composite-formatting.md#format-string-component).|

En este ejemplo se usan componentes opcionales de formato que se describen en la tabla anterior:

[!code-csharp-interactive[specify alignment and format string](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#2)]

Para incluir una llave ("{" o "}") en el texto producido por una cadena interpolada, use dos llaves, "{{" o "}}". Para más información, vea [Llaves de escape](../../../standard/base-types/composite-formatting.md#escaping-braces).

Como los dos puntos (:) tienen un significado especial en un elemento de expresión interpolada, para poder usar un [operador condicional](../operators/conditional-operator.md) en una expresión interpolada, incluya esa expresión entre paréntesis.

En este ejemplo se muestra cómo incluir una llave en la cadena de resultado y cómo usar un operador condicional en una expresión interpolada:

[!code-csharp-interactive[example with ternary conditional operator](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#3)]

Las cadenas interpoladas textuales usan el carácter `$` seguido del carácter `@`. Para más información sobre las cadenas textuales, vea el tema [string](../keywords/string.md).

> [!NOTE]
> El token `$` debe aparecer antes del token `@` en una cadena interpolada textual.

## <a name="implicit-conversions"></a>Conversiones implícitas

Hay tres conversiones de tipo implícito de una cadena interpolada:

1. Conversión de una cadena interpolada a una instancia de <xref:System.String>, que es el resultado de la resolución de cadenas interpoladas con elementos de expresión interpolada que se reemplazan con las representaciones de cadena con formato correcto de sus resultados. Esta conversión usa la referencia cultural actual.

1. La conversión de una cadena interpolada a una variable <xref:System.FormattableString> que representa una cadena de formato compuesto junto con los resultados de expresión a los que se va a aplicar formato. Esto permite crear varias cadenas de resultado con contenido específico de la referencia cultural de una sola instancia de <xref:System.FormattableString>. Para ello, llame a uno de estos métodos:

      - Una sobrecarga de <xref:System.FormattableString.ToString> que genera una cadena de resultado para <xref:System.Globalization.CultureInfo.CurrentCulture>.
      - Un método <xref:System.FormattableString.Invariant%2A> que genera una cadena de resultado para <xref:System.Globalization.CultureInfo.InvariantCulture>.
      - Un método <xref:System.FormattableString.ToString(System.IFormatProvider)> que genera una cadena de resultado para una referencia cultural especificada.

1. Conversión de una cadena interpolada a una variable <xref:System.IFormattable> que también permite crear varias cadenas de resultado con contenido específico de la referencia cultural de una sola instancia <xref:System.IFormattable>.

En este ejemplo se usa la conversión implícita a <xref:System.FormattableString> para crear cadenas de resultado específicas de la referencia cultural:

[!code-csharp-interactive[create culture-specific result strings](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#4)]

## <a name="additional-reading"></a>Lecturas adicionales

Si no está familiarizado con la interpolación de cadenas, eche un vistazo al inicio rápido [Cadenas interpoladas en C#](../../quick-starts//interpolated-strings.yml). Para ver más ejemplos, eche un vistazo al tutorial 
[Interpolación de cadenas en C#](../../tutorials/string-interpolation.md).

## <a name="see-also"></a>Vea también  
 <xref:System.String.Format%2A?displayProperty=nameWithType>  
 <xref:System.FormattableString?displayProperty=nameWithType>  
 <xref:System.IFormattable?displayProperty=nameWithType>  
 [Formatos compuestos](../../../standard/base-types/composite-formatting.md)  
 [Cadenas](../../../csharp/programming-guide/strings/index.md)  
 [Caracteres especiales de C#](../../../csharp/language-reference/tokens/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Referencia de C#](../../../csharp/language-reference/index.md)  