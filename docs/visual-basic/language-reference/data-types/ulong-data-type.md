---
title: ULong (Tipo de datos)
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
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343879"
---
# <a name="ulong-data-type-visual-basic"></a>ULong (tipo de datos) (Visual Basic)

Contiene enteros de 64 bits (8 bytes) sin signo que van en el valor de 0 a 18446744073709551615 (más de 1,84 veces 10 ^ 19).

## <a name="remarks"></a>Comentarios

Utilice el tipo de datos `ULong` para contener datos binarios demasiado grandes para `UInteger`, o los valores enteros sin signo más grandes posibles.

El valor predeterminado de `ULong` es 0.

## <a name="literal-assignments"></a>Asignaciones literales

Puede declarar e inicializar una variable de `ULong` asignándole un literal decimal, un literal hexadecimal, un literal octal o (empezando por Visual Basic 2017) un literal binario. Si el literal entero está fuera del intervalo de `ULong` (es decir, si es inferior a <xref:System.UInt64.MinValue?displayProperty=nameWithType> o mayor que <xref:System.UInt64.MaxValue?displayProperty=nameWithType>), se produce un error de compilación.

En el ejemplo siguiente, los enteros que equivalen a 7 934 076 125 que se representan como literales binarios, hexadecimales y decimales se asignan a valores `ULong`.

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ULong)]

> [!NOTE]
> Use el prefijo `&h` o `&H` para indicar un literal hexadecimal, el prefijo `&b` o `&B` para denotar un literal binario y el prefijo `&o` o `&O` para denotar un literal octal. Los literales decimales no tienen prefijo.

A partir de Visual Basic 2017, también puede usar el carácter de subrayado, `_`, como separador de dígitos para mejorar la legibilidad, como se muestra en el ejemplo siguiente.

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

A partir de Visual Basic 15,5, también puede usar el carácter de subrayado (`_`) como separador inicial entre el prefijo y los dígitos hexadecimales, binarios o octales. Por ejemplo:

```vb
Dim number As ULong = &H_F9AC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Los literales numéricos también pueden incluir el [carácter de tipo](../../programming-guide/language-features/data-types/type-characters.md) `UL` o `ul` para indicar el tipo de datos `ULong`, como se muestra en el ejemplo siguiente.

```vb
Dim number = &H_00_00_0A_96_2F_AC_14_D7ul
```

## <a name="programming-tips"></a>sugerencias de programación

- **Números negativos.** Dado que `ULong` es un tipo sin signo, no puede representar un número negativo. Si usa el operador unario menos (`-`) en una expresión que se evalúa como tipo `ULong`, Visual Basic convierte la expresión en `Decimal` primero.

- **Conformidad con CLS.** El tipo de datos `ULong` no forma parte de la [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), por lo que el código conforme a CLS no puede consumir un componente que lo utiliza.

- **Consideraciones de interoperabilidad.** Si interactúa con componentes que no se han escrito para el .NET Framework, por ejemplo, objetos de automatización o COM, tenga en cuenta que los tipos como `ulong` pueden tener un ancho de datos diferente (32 bits) en otros entornos. Si pasa un argumento de 32 bits a este componente, declárelo como `UInteger` en lugar de `ULong` en el código Visual Basic administrado.

  Además, Automation no admite enteros de 64 bits en Windows 95, Windows 98, Windows ME o Windows 2000. No se puede pasar un argumento de `ULong` de Visual Basic a un componente de automatización en estas plataformas.

- **Ampliación.** El tipo de datos `ULong` se amplía a `Decimal`, `Single`y `Double`. Esto significa que puede convertir `ULong` en cualquiera de estos tipos sin encontrar un error de <xref:System.OverflowException?displayProperty=nameWithType>.

- **Caracteres de tipo.** Anexar los caracteres de tipo literal `UL` a un literal lo convierte al tipo de datos `ULong`. `ULong` no tiene ningún carácter de tipo de identificador.

- **Tipo de marco.** El tipo correspondiente en .NET Framework es la estructura <xref:System.UInt64?displayProperty=nameWithType>.

## <a name="see-also"></a>Vea también

- <xref:System.UInt64>
- [Tipos de datos](../../../visual-basic/language-reference/data-types/index.md)
- [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Llamar a una función de Windows que adopta tipos sin signo](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
