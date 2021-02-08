---
description: 'Más información acerca de: tipo de datos Long (Visual Basic)'
title: Tipo de datos Long
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
ms.openlocfilehash: cb4a22fa3b9d1440f755c8a3412aa3a918b7f261
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792185"
---
# <a name="long-data-type-visual-basic"></a>Long (tipo de datos) (Visual Basic)

Contiene enteros de 64 bits (8 bytes) con signo comprendido entre-9.223.372.036.854.775.808 y 9.223.372.036.854.775.807 (9.2... E + 18).

## <a name="remarks"></a>Observaciones

Utilice el `Long` tipo de datos para incluir números enteros demasiado grandes como para caber en el `Integer` tipo de datos.

El valor predeterminado de `Long` es 0.

## <a name="literal-assignments"></a>Asignaciones literales

Puede declarar e inicializar una `Long` variable asignándole un literal decimal, un literal hexadecimal, un literal octal o (empezando por Visual Basic 2017) un literal binario. Si el literal entero está fuera del intervalo de `Long` (es decir, si es inferior a <xref:System.Int64.MinValue?displayProperty=nameWithType> o mayor que <xref:System.Int64.MaxValue?displayProperty=nameWithType>, se produce un error de compilación.

En el ejemplo siguiente, los enteros que equivalen a 4 294 967 296 que se representan como literales binarios, hexadecimales y decimales se asignan a valores `Long`.

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Long)]

> [!NOTE]
> Use el prefijo `&h` o `&H` para denotar un literal hexadecimal, el prefijo `&b` o `&B` para denotar un literal binario, y el prefijo `&o` o `&O` para denotar un literal octal. Los literales decimales no tienen prefijo.

A partir de Visual Basic 2017, también puede usar el carácter de subrayado, `_` , como separador de dígitos para mejorar la legibilidad, como se muestra en el ejemplo siguiente.

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

A partir de Visual Basic 15,5, también puede usar el carácter de subrayado ( `_` ) como separador inicial entre el prefijo y los dígitos hexadecimales, binarios o octales. Por ejemplo:

```vb
Dim number As Long = &H_0FAC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Los literales numéricos también pueden incluir el `L` [carácter de tipo](../../programming-guide/language-features/data-types/type-characters.md) para denotar el `Long` tipo de datos, como se muestra en el ejemplo siguiente.

```vb
Dim number = &H_0FAC_0326_1489_D68CL
```

## <a name="programming-tips"></a>sugerencias de programación

- **Consideraciones de interoperabilidad.** Si interactúa con componentes que no se han escrito para el .NET Framework, por ejemplo, objetos de automatización o COM, recuerde que `Long` tiene un ancho de datos diferente (32 bits) en otros entornos. Si va a pasar un argumento de 32 bits a este componente, declárelo como `Integer` en lugar de `Long` en el nuevo código de Visual Basic.

- **Ampliación.** El `Long` tipo de datos se amplía a `Decimal` , `Single` o `Double` . Esto significa que puede convertir un tipo de datos `Long` en cualquiera de estos tipos sin que se produzca un error <xref:System.OverflowException?displayProperty=nameWithType>.

- **Caracteres de tipo.** Al agregar el carácter de tipo literal `L` a un literal, el tipo de datos se convierte forzosamente en el tipo de datos `Long`. Si se agrega el carácter de tipo identificador `&` a cualquier identificador, se convierte forzosamente al tipo `Long`.

- **Tipo de Framework.** El tipo correspondiente en .NET Framework es la estructura <xref:System.Int64?displayProperty=nameWithType>.

## <a name="see-also"></a>Vea también

- <xref:System.Int64>
- [Tipo de datos](index.md)
- [Tipo de datos Integer](integer-data-type.md)
- [Tipo de datos Short](short-data-type.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Resumen de las conversiones](../keywords/conversion-summary.md)
- [Uso eficiente de los tipos de datos](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
