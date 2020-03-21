---
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
ms.openlocfilehash: ccff61608aed797734cb4f5ca0571d7ed73ba98b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401380"
---
# <a name="uinteger-data-type"></a>UInteger (tipo de datos)

Contiene enteros de 32 bits sin signo (4 bytes) que varían en valor de 0 a 4.294.967.295.

## <a name="remarks"></a>Observaciones

El `UInteger` tipo de datos proporciona el valor sin signo más grande en el ancho de datos más eficaz.

El valor predeterminado de `UInteger` es 0.

## <a name="literal-assignments"></a>Asignaciones literales

Puede declarar e `UInteger` inicializar una variable asignándole un literal decimal, un literal hexadecimal, un literal octal o (a partir de Visual Basic 2017) un literal binario. Si el literal entero está fuera del intervalo de `UInteger` (es decir, si es inferior a <xref:System.UInt32.MinValue?displayProperty=nameWithType> o mayor que <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, se produce un error de compilación.

En el ejemplo siguiente, los enteros que equivalen a 3 000 000 000 que se representan como literales binarios, hexadecimales y decimales se asignan a valores `UInteger`.

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UInt)]

> [!NOTE]
> Utilice el `&h` prefijo `&H` o para denotar un `&b` `&B` literal hexadecimal, el prefijo o `&o` `&O` para denotar un literal binario, y el prefijo o para denotar un literal octal. Los literales decimales no tienen prefijo.

A partir de Visual Basic 2017, también `_`puede usar el carácter de subrayado, , como separador de dígitos para mejorar la legibilidad, como se muestra en el ejemplo siguiente.

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UIntS)]

A partir de Visual Basic 15.5, también`_`puede usar el carácter de subrayado ( ) como separador inicial entre el prefijo y los dígitos hexadecimales, binarios u octales. Por ejemplo:

```vb
Dim number As UInteger = &H_0F8C_0326
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Los literales numéricos `UI` `ui` también pueden incluir `UInteger` el [carácter](../../programming-guide/language-features/data-types/type-characters.md) o tipo para denotar el tipo de datos, como se muestra en el ejemplo siguiente.

```vb
Dim number = &H_0FAC_14D7ui
```

## <a name="programming-tips"></a>sugerencias de programación

Los `UInteger` `Integer` tipos de datos y y proporcionan un rendimiento óptimo en`UShort` `Short`un `Byte`procesador `SByte`de 32 bits, ya que los tipos enteros más pequeños ( , , , y ), aunque usan menos bits, tardan más tiempo en cargarse, almacenarlos y recuperarse.

- **Números negativos.** Dado `UInteger` que es un tipo sin signo, no puede representar un número negativo. Si utiliza el operador`-`unario menos ( ) en `UInteger`una expresión que se `Long` evalúa como tipo , Visual Basic convierte la expresión en primer lugar.

- **Cumplimiento de CLS.** El `UInteger` tipo de datos no forma parte de [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), por lo que el código compatible con CLS no puede consumir un componente que lo utilice.

- **Consideraciones de interoperabilidad.** Si está interactuando con componentes no escritos para .NET Framework, por ejemplo, objetos de automatización o COM, tenga en cuenta que tipos como `uint` pueden tener un ancho de datos diferente (16 bits) en otros entornos. Si va a pasar un argumento de 16 bits `UShort` a `UInteger` un componente de este tipo, declárelo como en lugar de en el código administrado de Visual Basic.

- **Ampliación.** El `UInteger` tipo de datos `Long` `ULong`se `Decimal` `Single`amplía `Double`a , , , y . Esto significa que `UInteger` puede convertir a cualquiera <xref:System.OverflowException?displayProperty=nameWithType> de estos tipos sin encontrar un error.

- **Escriba Caracteres.** Anexar los caracteres `UI` de tipo literal `UInteger` a un literal lo fuerza al tipo de datos. `UInteger`no tiene ningún carácter de tipo identificador.

- **Tipo de Framework.** El tipo correspondiente en .NET Framework es la estructura <xref:System.UInt32?displayProperty=nameWithType>.

## <a name="see-also"></a>Consulte también

- <xref:System.UInt32>
- [Tipos de datos](../../../visual-basic/language-reference/data-types/index.md)
- [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Llamar a una función de Windows que adopta tipos sin signo](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
