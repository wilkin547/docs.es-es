---
title: Tipo de datos Integer
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
ms.openlocfilehash: aa7b64162308d6af2763b29034c5a7276c973876
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415614"
---
# <a name="integer-data-type-visual-basic"></a>Tipo de datos Integer (Visual Basic)

Contiene enteros de 32 bits con signo (4 bytes) comprendidos en el intervalo entre -2.147.483.648 y 2.147.483.647.  
  
## <a name="remarks"></a>Observaciones

 El tipo de datos `Integer` proporciona un rendimiento óptimo en un procesador de 32 bits. Los demás tipos enteros son más lentos a la hora de cargarse y almacenarse en la memoria.  
  
 El valor predeterminado de `Integer` es 0.  

## <a name="literal-assignments"></a>Asignaciones literales

Puede declarar e inicializar una `Integer` variable asignándole un literal decimal, un literal hexadecimal, un literal octal o (empezando por Visual Basic 2017) un literal binario. Si el literal entero está fuera del intervalo de `Integer` (es decir, si es inferior a <xref:System.Int32.MinValue?displayProperty=nameWithType> o mayor que <xref:System.Int32.MaxValue?displayProperty=nameWithType>, se produce un error de compilación.

En el ejemplo siguiente, los enteros que equivalen a 90 946 que se representan como literales binarios, hexadecimales y decimales se asignan a valores `Integer`.

[!code-vb[integer](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Int)]  

> [!NOTE]
> Use el prefijo `&h` o `&H` para denotar un literal hexadecimal, el prefijo `&b` o `&B` para denotar un literal binario, y el prefijo `&o` o `&O` para denotar un literal octal. Los literales decimales no tienen prefijo.

A partir de Visual Basic 2017, también puede usar el carácter de subrayado, `_` , como separador de dígitos para mejorar la legibilidad, como se muestra en el ejemplo siguiente.

[!code-vb[integer](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#IntS)]  

A partir de Visual Basic 15,5, también puede usar el carácter de subrayado ( `_` ) como separador inicial entre el prefijo y los dígitos hexadecimales, binarios o octales. Por ejemplo:

```vb
Dim number As Integer = &H_C305_F860
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Los literales numéricos también pueden incluir el `I` [carácter de tipo](../../programming-guide/language-features/data-types/type-characters.md) para denotar el `Integer` tipo de datos, como se muestra en el ejemplo siguiente.

```vb
Dim number = &H_035826I
```

## <a name="programming-tips"></a>sugerencias de programación

- **Consideraciones de interoperabilidad.** Si interactúa con componentes que no se han escrito para el .NET Framework, como objetos de automatización o COM, recuerde que `Integer` tiene un ancho de datos diferente (16 bits) en otros entornos. Al pasar un argumento de 16 bits a esos componentes, declárelo en el código de Visual Basic como `Short` en lugar de como `Integer`.  
  
- **Ampliación.** El tipo de datos `Integer` se amplía a `Long`, `Decimal`, `Single` o `Double`. Esto significa que puede convertir un tipo de datos `Integer` en cualquiera de estos tipos sin que se produzca un error <xref:System.OverflowException?displayProperty=nameWithType>.  
  
- **Caracteres de tipo.** Al agregar el carácter de tipo literal `I` a un literal, el tipo de datos se convierte forzosamente en el tipo de datos `Integer`. Si se agrega el carácter de tipo identificador `%` a cualquier identificador, se convierte forzosamente al tipo `Integer`.  
  
- **Tipo de Framework.** El tipo correspondiente en .NET Framework es la estructura <xref:System.Int32?displayProperty=nameWithType>.  
  
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

## <a name="see-also"></a>Consulte también

- <xref:System.Int32?displayProperty=nameWithType>
- [Tipos de datos](index.md)
- [Tipo de datos Long](long-data-type.md)
- [Tipo de datos Short](short-data-type.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Resumen de las conversiones](../keywords/conversion-summary.md)
- [Uso eficiente de los tipos de datos](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
