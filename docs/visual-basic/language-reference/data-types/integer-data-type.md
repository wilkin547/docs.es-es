---
title: Integer (Tipo de datos)
ms.date: 01/31/2018
f1_keywords:
- vb.Integer
- Integer
helpviewer_keywords:
- numbers [Visual Basic], whole
- enumerated values [Visual Basic]
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- literal type characters [Visual Basic], I
- integers [Visual Basic], types
- data types [Visual Basic], integral
- '% identifier type character'
- data types [Visual Basic], assigning
- identifier type characters [Visual Basic], %
- I literal type character [Visual Basic]
- Integer data type
ms.assetid: a8f233b4-4be3-455c-861b-05af2fbb6c60
ms.openlocfilehash: c5b1041b8ef0ca9898a846fea03888537bb4abbf
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343980"
---
# <a name="integer-data-type-visual-basic"></a>Integer data type (Visual Basic)

Contiene enteros de 32 bits con signo (4 bytes) comprendidos en el intervalo entre -2.147.483.648 y 2.147.483.647.  
  
## <a name="remarks"></a>Comentarios

 El tipo de datos `Integer` proporciona un rendimiento óptimo en un procesador de 32 bits. Los demás tipos enteros son más lentos a la hora de cargarse y almacenarse en la memoria.  
  
 El valor predeterminado de `Integer` es 0.  

## <a name="literal-assignments"></a>Literal assignments

You can declare and initialize an `Integer` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal. Si el literal entero está fuera del intervalo de `Integer` (es decir, si es inferior a <xref:System.Int32.MinValue?displayProperty=nameWithType> o mayor que <xref:System.Int32.MaxValue?displayProperty=nameWithType>, se produce un error de compilación.

En el ejemplo siguiente, los enteros que equivalen a 90 946 que se representan como literales binarios, hexadecimales y decimales se asignan a valores `Integer`.

[!code-vb[integer](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Int)]  

> [!NOTE]
> You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal. Los literales decimales no tienen prefijo.

Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.

[!code-vb[integer](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#IntS)]  

Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits. Por ejemplo:

```vb
Dim number As Integer = &H_C305_F860
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Numeric literals can also include the `I` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `Integer` data type, as the following example shows.

```vb
Dim number = &H_035826I
```

## <a name="programming-tips"></a>sugerencias de programación

- **Interop Considerations.** If you are interfacing with components not written for the .NET Framework, such as Automation or COM objects, remember that `Integer` has a different data width (16 bits) in other environments. Al pasar un argumento de 16 bits a esos componentes, declárelo en el código de Visual Basic como `Short` en lugar de como `Integer`.  
  
- **Widening.** El tipo de datos `Integer` se amplía a `Long`, `Decimal`, `Single` o `Double`. Esto significa que puede convertir un tipo de datos `Integer` en cualquiera de estos tipos sin que se produzca un error <xref:System.OverflowException?displayProperty=nameWithType>.  
  
- **Type Characters.** Al agregar el carácter de tipo literal `I` a un literal, el tipo de datos se convierte forzosamente en el tipo de datos `Integer`. Si se agrega el carácter de tipo identificador `%` a cualquier identificador, se convierte forzosamente al tipo `Integer`.  
  
- **Framework Type.** El tipo correspondiente en .NET Framework es la estructura <xref:System.Int32?displayProperty=nameWithType>.  
  
## <a name="range"></a>Intervalo

Si intenta establecer una variable de un tipo entero en un número que está fuera del intervalo correspondiente a ese tipo, se produce un error. Si intenta establecerlo en una fracción, el número se redondea hacia arriba o hacia abajo al valor entero más cercano. Si el número está equidistante a dos valores enteros, el valor se redondea al entero par más próximo. Este comportamiento minimiza los errores de redondeo que se derivan de redondear de forma consistente un valor de punto medio en una dirección única. En el código siguiente se muestran ejemplos de redondeo.  

```vb  
' The valid range of an Integer variable is -2147483648 through +2147483647.  
Dim k As Integer  
' The following statement causes an error because the value is too large.  
k = 2147483648  
' The following statement sets k to 6.  
k = 5.9  
' The following statement sets k to 4  
k = 4.5  
' The following statement sets k to 6  
' Note, Visual Basic uses banker’s rounding (toward nearest even number)  
k = 5.5  
```

## <a name="see-also"></a>Vea también

- <xref:System.Int32?displayProperty=nameWithType>
- [Tipos de datos](../../../visual-basic/language-reference/data-types/index.md)
- [Long (tipo de datos)](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [Short (tipo de datos)](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
