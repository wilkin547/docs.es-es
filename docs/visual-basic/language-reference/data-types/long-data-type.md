---
title: Long (Tipo de datos)
ms.date: 01/31/2018
f1_keywords:
- vb.Long
helpviewer_keywords:
- identifier type characters [Visual Basic], &
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- '& identifier type character'
- integer numbers
- literal type characters [Visual Basic], L
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- L literal type character [Visual Basic]
- integers [Visual Basic], types
- Long keyword [Visual Basic]
- data types [Visual Basic], integral
- data types [Visual Basic], assigning
- Long data type
ms.assetid: b4770c34-1804-4f8c-b512-c10b0893e516
ms.openlocfilehash: 16d7409c802e97b1f33474d810134db4d9f0ad6c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343976"
---
# <a name="long-data-type-visual-basic"></a>Long data type (Visual Basic)

Holds signed 64-bit (8-byte) integers ranging in value from -9,223,372,036,854,775,808 through 9,223,372,036,854,775,807 (9.2...E+18).

## <a name="remarks"></a>Comentarios

Use the `Long` data type to contain integer numbers that are too large to fit in the `Integer` data type.

El valor predeterminado de `Long` es 0.

## <a name="literal-assignments"></a>Literal assignments

You can declare and initialize a `Long` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal. Si el literal entero está fuera del intervalo de `Long` (es decir, si es inferior a <xref:System.Int64.MinValue?displayProperty=nameWithType> o mayor que <xref:System.Int64.MaxValue?displayProperty=nameWithType>, se produce un error de compilación.

En el ejemplo siguiente, los enteros que equivalen a 4 294 967 296 que se representan como literales binarios, hexadecimales y decimales se asignan a valores `Long`.

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Long)]

> [!NOTE]
> You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal. Los literales decimales no tienen prefijo.

Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits. Por ejemplo:

```vb
Dim number As Long = &H_0FAC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Numeric literals can also include the `L` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `Long` data type, as the following example shows.

```vb
Dim number = &H_0FAC_0326_1489_D68CL
```

## <a name="programming-tips"></a>sugerencias de programación

- **Interop Considerations.** If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, remember that `Long` has a different data width (32 bits) in other environments. If you are passing a 32-bit argument to such a component, declare it as `Integer` instead of `Long` in your new Visual Basic code.

- **Widening.** The `Long` data type widens to `Decimal`, `Single`, or `Double`. Esto significa que puede convertir un tipo de datos `Long` en cualquiera de estos tipos sin que se produzca un error <xref:System.OverflowException?displayProperty=nameWithType>.

- **Type Characters.** Al agregar el carácter de tipo literal `L` a un literal, el tipo de datos se convierte forzosamente en el tipo de datos `Long`. Si se agrega el carácter de tipo identificador `&` a cualquier identificador, se convierte forzosamente al tipo `Long`.

- **Framework Type.** El tipo correspondiente en .NET Framework es la estructura <xref:System.Int64?displayProperty=nameWithType>.

## <a name="see-also"></a>Vea también

- <xref:System.Int64>
- [Tipos de datos](../../../visual-basic/language-reference/data-types/index.md)
- [Integer (tipo de datos)](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [Short (tipo de datos)](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
