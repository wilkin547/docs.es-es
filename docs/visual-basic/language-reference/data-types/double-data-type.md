---
title: Tipo de datos Double
ms.date: 07/20/2015
f1_keywords:
- vb.Double
helpviewer_keywords:
- 'identifier type characters [Visual Basic], #'
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- 0 characters [Visual Basic], trailing
- literal type characters [Visual Basic], R
- data types [Visual Basic], assigning
- Double data type [Visual Basic]
- '# identifier type character'
- double-precision numbers
- floating-point numbers [Visual Basic], Double data type
- R literal type character [Visual Basic]
- zeros, trailing
- Double data type
ms.assetid: 0c5670f7-fcb1-453a-bef1-374730cd38fd
ms.openlocfilehash: 899554f427ac77ead465752c35e51ca88d045763
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415639"
---
# <a name="double-data-type-visual-basic"></a>Double (Tipo de datos, Visual Basic)

Contiene números de punto flotante de precisión doble de IEEE 64 bits (8 bytes) que van del valor de-1.79769313486231570 E + 308 a-4.94065645841246544 E-324 para los valores negativos y de 4.94065645841246544 E-324 a 1.79769313486231570 E + 308 para los valores positivos. Los números de precisión doble almacenan una aproximación de un número real.

## <a name="remarks"></a>Observaciones

El `Double` tipo de datos proporciona las magnitudes más grandes y pequeñas posibles para un número.

El valor predeterminado de `Double` es 0.

## <a name="programming-tips"></a>Sugerencias de programación

- **Precisión.** Al trabajar con números de punto flotante, recuerde que no siempre tienen una representación precisa en la memoria. Esto podría dar lugar a resultados inesperados de ciertas operaciones, como la comparación de valores y el `Mod` operador. Para obtener más información, vea [solución de problemas de tipos de datos](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).

- **Ceros a la derecha.** Los tipos de datos de punto flotante no tienen ninguna representación interna de los caracteres cero finales. Por ejemplo, no distinguen entre 4,2000 y 4,2. Por lo tanto, los caracteres cero finales no aparecen al mostrar o imprimir valores de punto flotante.

- **Caracteres de tipo.** Al agregar el carácter de tipo literal `R` a un literal, el tipo de datos se convierte forzosamente en el tipo de datos `Double`. Por ejemplo, si un valor entero va seguido de `R` , el valor se cambia a `Double` .

  ```vb
  ' Visual Basic expands the 4 in the statement Dim dub As Double = 4R to 4.0:
  Dim dub As Double = 4.0R
  ```

  Si se agrega el carácter de tipo identificador `#` a cualquier identificador, se convierte forzosamente al tipo `Double`. En el ejemplo siguiente, la variable `num` se escribe como `Double` :

  ```vb
  Dim num# = 3
  ```

- **Tipo de Framework.** El tipo correspondiente en .NET Framework es la estructura <xref:System.Double?displayProperty=nameWithType>.

## <a name="see-also"></a>Consulte también

- <xref:System.Double?displayProperty=nameWithType>
- [Tipos de datos](index.md)
- [Tipo de datos Decimal](decimal-data-type.md)
- [Tipo de datos Single](single-data-type.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Resumen de las conversiones](../keywords/conversion-summary.md)
- [Uso eficiente de los tipos de datos](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Solución de problemas de los tipos de datos](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Caracteres de tipo](../../programming-guide/language-features/data-types/type-characters.md)
