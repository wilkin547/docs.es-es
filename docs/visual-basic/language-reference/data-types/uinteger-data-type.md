---
description: 'Más información sobre: UInteger (tipo de datos)'
title: Tipo de datos UInteger
ms.date: 01/31/2018
f1_keywords:
- vb.uinteger
helpviewer_keywords:
- numbers [Visual Basic], whole
- UInteger data type
- literal type characters [Visual Basic], UI
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- UI literal type characters [Visual Basic]
- data types [Visual Basic], integral
ms.assetid: db7ddd34-4f23-46f5-84dd-8b0f83bb8729
ms.openlocfilehash: 5202619909de4a132bda8ab3dca63337c6f3493f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792107"
---
# <a name="uinteger-data-type"></a>UInteger (tipo de datos)

Contiene enteros de 32 bits sin signo (4 bytes) con un valor comprendido entre 0 y 4.294.967.295.

## <a name="remarks"></a>Observaciones

El `UInteger` tipo de datos proporciona el valor sin signo más grande en el ancho de datos más eficaz.

El valor predeterminado de `UInteger` es 0.

## <a name="literal-assignments"></a>Asignaciones literales

Puede declarar e inicializar una `UInteger` variable asignándole un literal decimal, un literal hexadecimal, un literal octal o (empezando por Visual Basic 2017) un literal binario. Si el literal entero está fuera del intervalo de `UInteger` (es decir, si es inferior a <xref:System.UInt32.MinValue?displayProperty=nameWithType> o mayor que <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, se produce un error de compilación.

En el ejemplo siguiente, los enteros que equivalen a 3 000 000 000 que se representan como literales binarios, hexadecimales y decimales se asignan a valores `UInteger`.

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UInt)]

> [!NOTE]
> Use el prefijo `&h` o `&H` para denotar un literal hexadecimal, el prefijo `&b` o `&B` para denotar un literal binario, y el prefijo `&o` o `&O` para denotar un literal octal. Los literales decimales no tienen prefijo.

A partir de Visual Basic 2017, también puede usar el carácter de subrayado, `_` , como separador de dígitos para mejorar la legibilidad, como se muestra en el ejemplo siguiente.

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UIntS)]

A partir de Visual Basic 15,5, también puede usar el carácter de subrayado ( `_` ) como separador inicial entre el prefijo y los dígitos hexadecimales, binarios o octales. Por ejemplo:

```vb
Dim number As UInteger = &H_0F8C_0326
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Los literales numéricos también pueden incluir el `UI` `ui` [carácter de tipo](../../programming-guide/language-features/data-types/type-characters.md) o para denotar el `UInteger` tipo de datos, como se muestra en el ejemplo siguiente.

```vb
Dim number = &H_0FAC_14D7ui
```

## <a name="programming-tips"></a>sugerencias de programación

Los `UInteger` `Integer` tipos de datos y proporcionan un rendimiento óptimo en un procesador de 32 bits, ya que los tipos enteros más pequeños ( `UShort` , `Short` , `Byte` y `SByte` ), aunque usen menos bits, tardarán más tiempo en cargarse, almacenarse y recuperarse.

- **Números negativos.** Dado `UInteger` que es un tipo sin signo, no puede representar un número negativo. Si usa el operador unario menos ( `-` ) en una expresión que se evalúa como tipo `UInteger` , Visual Basic convierte primero la expresión en `Long` .

- **Conformidad con CLS.** El `UInteger` tipo de datos no forma parte de la [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), por lo que el código conforme a CLS no puede consumir un componente que lo utiliza.

- **Consideraciones de interoperabilidad.** Si interactúa con componentes que no se han escrito para el .NET Framework, por ejemplo, objetos de automatización o COM, tenga en cuenta que los tipos como `uint` pueden tener un ancho de datos diferente (16 bits) en otros entornos. Si va a pasar un argumento de 16 bits a este componente, declárelo como `UShort` en lugar de `UInteger` en el código de Visual Basic administrado.

- **Ampliación.** El `UInteger` tipo de datos se amplía a `Long` , `ULong` , `Decimal` , `Single` y `Double` . Esto significa que puede convertir `UInteger` en cualquiera de estos tipos sin que se produzca un <xref:System.OverflowException?displayProperty=nameWithType> error.

- **Caracteres de tipo.** Anexar los caracteres de tipo literal `UI` a un literal lo convierte al `UInteger` tipo de datos. `UInteger` no tiene ningún carácter de tipo de identificador.

- **Tipo de Framework.** El tipo correspondiente en .NET Framework es la estructura <xref:System.UInt32?displayProperty=nameWithType>.

## <a name="see-also"></a>Vea también

- <xref:System.UInt32>
- [Tipo de datos](index.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Resumen de las conversiones](../keywords/conversion-summary.md)
- [Procedimiento Llamada una función de Windows que adopta tipos sin signo](../../programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Uso eficiente de los tipos de datos](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
