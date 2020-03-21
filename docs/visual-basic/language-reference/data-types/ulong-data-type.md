---
title: Tipo de datos ULong
ms.date: 01/31/2018
f1_keywords:
- vb.ulong
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- literal type characters [Visual Basic], UL
- ULong data type
- UL literal type characters [Visual Basic]
ms.assetid: 017e0702-774e-44ae-bedc-786b424ca84e
ms.openlocfilehash: 3c6cd4086e08b808c158948756b4806f098196b9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401320"
---
# <a name="ulong-data-type-visual-basic"></a>Tipo de datos ULong (Visual Basic)

Contiene enteros de 64 bits sin signo (8 bytes) que varían en valor de 0 a 18,446,744,073,709,551,615 (más de 1,84 veces 10 x 19).

## <a name="remarks"></a>Observaciones

Utilice `ULong` el tipo de datos para `UInteger`contener datos binarios demasiado grandes para , o los valores enteros sin signo más grandes posibles.

El valor predeterminado de `ULong` es 0.

## <a name="literal-assignments"></a>Asignaciones literales

Puede declarar e `ULong` inicializar una variable asignándole un literal decimal, un literal hexadecimal, un literal octal o (a partir de Visual Basic 2017) un literal binario. Si el literal entero está fuera del intervalo de `ULong` (es decir, si es inferior a <xref:System.UInt64.MinValue?displayProperty=nameWithType> o mayor que <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, se produce un error de compilación.

En el ejemplo siguiente, los enteros que equivalen a 7 934 076 125 que se representan como literales binarios, hexadecimales y decimales se asignan a valores `ULong`.

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ULong)]

> [!NOTE]
> Utilice el `&h` prefijo `&H` o para denotar un `&b` `&B` literal hexadecimal, el prefijo o `&o` `&O` para denotar un literal binario, y el prefijo o para denotar un literal octal. Los literales decimales no tienen prefijo.

A partir de Visual Basic 2017, también `_`puede usar el carácter de subrayado, , como separador de dígitos para mejorar la legibilidad, como se muestra en el ejemplo siguiente.

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

A partir de Visual Basic 15.5, también`_`puede usar el carácter de subrayado ( ) como separador inicial entre el prefijo y los dígitos hexadecimales, binarios u octales. Por ejemplo:

```vb
Dim number As ULong = &H_F9AC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Los literales numéricos `UL` `ul` también pueden incluir `ULong` el [carácter](../../programming-guide/language-features/data-types/type-characters.md) o tipo para denotar el tipo de datos, como se muestra en el ejemplo siguiente.

```vb
Dim number = &H_00_00_0A_96_2F_AC_14_D7ul
```

## <a name="programming-tips"></a>sugerencias de programación

- **Números negativos.** Dado `ULong` que es un tipo sin signo, no puede representar un número negativo. Si utiliza el operador`-`unario menos ( ) en `ULong`una expresión que se `Decimal` evalúa como tipo , Visual Basic convierte la expresión en primer lugar.

- **Cumplimiento de CLS.** El `ULong` tipo de datos no forma parte de [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), por lo que el código compatible con CLS no puede consumir un componente que lo utilice.

- **Consideraciones de interoperabilidad.** Si está interactuando con componentes no escritos para .NET Framework, por ejemplo, objetos de automatización o COM, tenga en cuenta que tipos como `ulong` pueden tener un ancho de datos diferente (32 bits) en otros entornos. Si va a pasar un argumento de 32 bits `UInteger` a `ULong` un componente de este tipo, declárelo como en lugar de en el código administrado de Visual Basic.

  Además, Automation no admite enteros de 64 bits en Windows 95, Windows 98, Windows ME o Windows 2000. No se puede `ULong` pasar un argumento de Visual Basic a un componente de automatización en estas plataformas.

- **Ampliación.** El `ULong` tipo de datos `Decimal` `Single`se `Double`amplía a , , y . Esto significa que `ULong` puede convertir a cualquiera <xref:System.OverflowException?displayProperty=nameWithType> de estos tipos sin encontrar un error.

- **Escriba Caracteres.** Anexar los caracteres `UL` de tipo literal `ULong` a un literal lo fuerza al tipo de datos. `ULong`no tiene ningún carácter de tipo identificador.

- **Tipo de Framework.** El tipo correspondiente en .NET Framework es la estructura <xref:System.UInt64?displayProperty=nameWithType>.

## <a name="see-also"></a>Consulte también

- <xref:System.UInt64>
- [Tipos de datos](../../../visual-basic/language-reference/data-types/index.md)
- [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Llamar a una función de Windows que adopta tipos sin signo](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
