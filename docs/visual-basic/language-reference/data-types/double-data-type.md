---
title: Double (Tipo de datos)
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
ms.openlocfilehash: 347b5c7b7af4c4aafec0f91aca46a8cf640236b9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344011"
---
# <a name="double-data-type-visual-basic"></a>Double (Tipo de datos, Visual Basic)

Holds signed IEEE 64-bit (8-byte) double-precision floating-point numbers that range in value from -1.79769313486231570E+308 through -4.94065645841246544E-324 for negative values and from 4.94065645841246544E-324 through 1.79769313486231570E+308 for positive values. Double-precision numbers store an approximation of a real number.

## <a name="remarks"></a>Comentarios

The `Double` data type provides the largest and smallest possible magnitudes for a number.

El valor predeterminado de `Double` es 0.

## <a name="programming-tips"></a>Sugerencias de programación

- **Precision.** When you work with floating-point numbers, remember that they do not always have a precise representation in memory. This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator. For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).

- **Trailing Zeros.** The floating-point data types do not have any internal representation of trailing zero characters. For example, they do not distinguish between 4.2000 and 4.2. Consequently, trailing zero characters do not appear when you display or print floating-point values.

- **Type Characters.** Al agregar el carácter de tipo literal `R` a un literal, el tipo de datos se convierte forzosamente en el tipo de datos `Double`. For example, if an integer value is followed by `R`, the value is changed to a `Double`.

  ```vb
  ' Visual Basic expands the 4 in the statement Dim dub As Double = 4R to 4.0:
  Dim dub As Double = 4.0R
  ```

  Si se agrega el carácter de tipo identificador `#` a cualquier identificador, se convierte forzosamente al tipo `Double`. In the following example, the variable `num` is typed as a `Double`:

  ```vb
  Dim num# = 3
  ```

- **Framework Type.** El tipo correspondiente en .NET Framework es la estructura <xref:System.Double?displayProperty=nameWithType>.

## <a name="see-also"></a>Vea también

- <xref:System.Double?displayProperty=nameWithType>
- [Tipos de datos](../../../visual-basic/language-reference/data-types/index.md)
- [Decimal (tipo de datos)](../../../visual-basic/language-reference/data-types/decimal-data-type.md)
- [Single (tipo de datos)](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Solución de problemas de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Caracteres de tipo](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
