---
title: Procedimiento para rellenar un número con ceros a la izquierda
description: Aprenda a rellenar un número con ceros iniciales. Agregue ceros a la izquierda a números enteros o valores numéricos hasta una longitud total concreta o un número específico de ceros a la izquierda.
ms.date: 02/25/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- numeric format strings [.NET]
- formatting [.NET], numbers
- number formatting [.NET]
- numbers [.NET], format strings
ms.assetid: 0b2c2cb5-c580-4891-8d81-cb632f5ec384
ms.openlocfilehash: 911d6059d3594ca35eb1c1c3e2d29a5684bce738
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94822053"
---
# <a name="how-to-pad-a-number-with-leading-zeros"></a>Procedimiento para rellenar un número con ceros a la izquierda

Si quiere agregar ceros a la izquierda de un entero, puede hacerlo mediante la [cadena de formato numérico estándar](standard-numeric-format-strings.md) "D" con un especificador de precisión. Para agregar ceros a la izquierda tanto de enteros como de números de punto flotante, use una [cadena de formato numérico personalizada](custom-numeric-format-strings.md). En este artículo se explica cómo usar ambos métodos para rellenar un número con ceros a la izquierda.

## <a name="to-pad-an-integer-with-leading-zeros-to-a-specific-length"></a>Para rellenar un entero con ceros a la izquierda hasta una longitud concreta

1. Determine el número mínimo de dígitos que desea que muestre el valor entero. Incluya los dígitos a la izquierda en este número.

1. Determine si desea mostrar el entero como valor decimal o hexadecimal.

    - Para mostrar el entero como valor decimal, llame a su método `ToString(String)` y pase la cadena "D *n*" como valor del parámetro `format`, donde *n* representa la longitud mínima de la cadena.

    - Para mostrar el entero como valor hexadecimal, llame a su método `ToString(String)` y pase la cadena "X *n*" como valor del parámetro format, donde *n* representa la longitud mínima de la cadena.

También puede usar la cadena de formato en una cadena interpolada en ambos, [C#](../../csharp/language-reference/tokens/interpolated.md) y [Visual Basic](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md), o puede llamar a un método, como <xref:System.String.Format%2A?displayProperty=nameWithType> o <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, que usa [formato compuesto](composite-formatting.md).

En el ejemplo siguiente se aplica formato a varios valores enteros con ceros a la izquierda de modo que la longitud mínima total del número con formato sea de ocho caracteres.

[!code-csharp[Formatting.HowTo.PadNumber#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#1)]
[!code-vb[Formatting.HowTo.PadNumber#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#1)]

## <a name="to-pad-an-integer-with-a-specific-number-of-leading-zeros"></a>Para rellenar un entero con una determinada cantidad de ceros a la izquierda

1. Determine cuántos ceros a la izquierda desea que muestre el valor entero.

1. Determine si desea mostrar el entero como valor decimal o hexadecimal.

    - Para darle formato como valor decimal, se requiere que use el especificador de formato estándar "D".

    - Para darle formato como valor hexadecimal, se requiere que use el especificador de formato estándar "X".

1. Determine la longitud de la cadena numérica sin rellenar mediante una llamada a los métodos `ToString("D").Length` o `ToString("X").Length` del valor entero.

1. Agregue el número de ceros a la izquierda que desea incluir en la cadena con formato a la longitud de la cadena numérica sin rellenar. Al agregar el número de ceros iniciales se define la longitud total de la cadena rellenada.

1. Llame al método `ToString(String)` del valor entero y pase la cadena "D *n*" para cadenas decimales y "X *n*" para cadenas hexadecimales, donde *n* representa la longitud total de la cadena rellenada. También puede usar la cadena de formato "D *n*" o "X *n*" en un método que admita formato compuesto.

En el ejemplo siguiente se rellena un valor entero con cinco ceros a la izquierda.

[!code-csharp[Formatting.HowTo.PadNumber#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#2)]
[!code-vb[Formatting.HowTo.PadNumber#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#2)]

## <a name="to-pad-a-numeric-value-with-leading-zeros-to-a-specific-length"></a>Para rellenar un valor numérico con ceros a la izquierda hasta una longitud concreta

1. Determine con cuántos dígitos a la izquierda del decimal desea que se represente la cadena del número. Incluya los ceros a la izquierda en este número total de dígitos.

1. Defina una cadena de formato numérico personalizado en la que se use el marcador de posición cero "0" para representar el número mínimo de ceros.

1. Llame al método `ToString(String)` del número y pase la cadena de formato personalizado. También puede usar la cadena de formato personalizado con interpolación de cadena o con un método que admita formato compuesto.

En el ejemplo siguiente se da formato a varios valores numéricos con ceros iniciales. Como resultado, la longitud total del número con formato es de al menos ocho dígitos a la izquierda del separador decimal.

[!code-csharp[Formatting.HowTo.PadNumber#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#3)]
[!code-vb[Formatting.HowTo.PadNumber#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#3)]

## <a name="to-pad-a-numeric-value-with-a-specific-number-of-leading-zeros"></a>Para rellenar un valor numérico con una determinada cantidad de ceros a la izquierda

1. Determine cuántos ceros a la izquierda desea que tenga el valor numérico.

1. Determine el número de dígitos a la izquierda del separador decimal que tendrá la cadena numérica sin rellenar:

    1. Determine si la representación de cadena de un número incluye un símbolo de separador decimal.

    1. Si incluye un símbolo de separador decimal, determine el número de caracteres a la izquierda del separador decimal.

         o bien

         Si no incluye un símbolo de separador decimal, determine la longitud de la cadena.

1. Cree una cadena de formato personalizado que utilice:

    - El marcador de posición cero "0" para cada uno de los ceros a la izquierda que aparecen en la cadena.

    - El marcador de posición cero o el marcador de posición de dígito "#" para representar cada dígito en la cadena predeterminada.

1. Proporcione la cadena de formato personalizado como un parámetro bien al método `ToString(String)` del número, bien a un método que admita el formato compuesto.

En el ejemplo siguiente se rellenan dos valores <xref:System.Double> con cinco ceros a la izquierda.

[!code-csharp[Formatting.HowTo.PadNumber#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#4)]
[!code-vb[Formatting.HowTo.PadNumber#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#4)]

## <a name="see-also"></a>Vea también

- [Cadenas con formato numérico personalizado](custom-numeric-format-strings.md)
- [Cadenas con formato numérico estándar](standard-numeric-format-strings.md)
- [Formatos compuestos](composite-formatting.md)
