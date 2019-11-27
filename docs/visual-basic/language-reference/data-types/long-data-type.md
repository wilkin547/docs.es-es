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
# <a name="long-data-type-visual-basic"></a>Long (tipo de datos) (Visual Basic)

Contiene enteros de 64 bits (8 bytes) con signo comprendido entre-9.223.372.036.854.775.808 y 9.223.372.036.854.775.807 (9.2... E + 18).

## <a name="remarks"></a>Comentarios

Utilice el tipo de datos `Long` para contener números enteros demasiado grandes como para caber en el tipo de datos `Integer`.

El valor predeterminado de `Long` es 0.

## <a name="literal-assignments"></a>Asignaciones literales

Puede declarar e inicializar una variable de `Long` asignándole un literal decimal, un literal hexadecimal, un literal octal o (empezando por Visual Basic 2017) un literal binario. Si el literal entero está fuera del intervalo de `Long` (es decir, si es inferior a <xref:System.Int64.MinValue?displayProperty=nameWithType> o mayor que <xref:System.Int64.MaxValue?displayProperty=nameWithType>), se produce un error de compilación.

En el ejemplo siguiente, los enteros que equivalen a 4 294 967 296 que se representan como literales binarios, hexadecimales y decimales se asignan a valores `Long`.

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Long)]

> [!NOTE]
> Use el prefijo `&h` o `&H` para indicar un literal hexadecimal, el prefijo `&b` o `&B` para denotar un literal binario y el prefijo `&o` o `&O` para denotar un literal octal. Los literales decimales no tienen prefijo.

A partir de Visual Basic 2017, también puede usar el carácter de subrayado, `_`, como separador de dígitos para mejorar la legibilidad, como se muestra en el ejemplo siguiente.

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

A partir de Visual Basic 15,5, también puede usar el carácter de subrayado (`_`) como separador inicial entre el prefijo y los dígitos hexadecimales, binarios o octales. Por ejemplo:

```vb
Dim number As Long = &H_0FAC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Los literales numéricos también pueden incluir el [carácter de tipo](../../programming-guide/language-features/data-types/type-characters.md) `L` para indicar el tipo de datos `Long`, como se muestra en el ejemplo siguiente.

```vb
Dim number = &H_0FAC_0326_1489_D68CL
```

## <a name="programming-tips"></a>sugerencias de programación

- **Consideraciones de interoperabilidad.** Si interactúa con componentes que no se han escrito para el .NET Framework, por ejemplo, objetos de automatización o COM, recuerde que `Long` tiene un ancho de datos diferente (32 bits) en otros entornos. Si pasa un argumento de 32 bits a este componente, declárelo como `Integer` en lugar de `Long` en el nuevo código de Visual Basic.

- **Ampliación.** El tipo de datos `Long` se amplía a `Decimal`, `Single`o `Double`. Esto significa que puede convertir un tipo de datos `Long` en cualquiera de estos tipos sin que se produzca un error <xref:System.OverflowException?displayProperty=nameWithType>.

- **Caracteres de tipo.** Al agregar el carácter de tipo literal `L` a un literal, el tipo de datos se convierte forzosamente en el tipo de datos `Long`. Si se agrega el carácter de tipo identificador `&` a cualquier identificador, se convierte forzosamente al tipo `Long`.

- **Tipo de marco.** El tipo correspondiente en .NET Framework es la estructura <xref:System.Int64?displayProperty=nameWithType>.

## <a name="see-also"></a>Vea también

- <xref:System.Int64>
- [Tipos de datos](../../../visual-basic/language-reference/data-types/index.md)
- [Integer (tipo de datos)](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [Short (tipo de datos)](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
