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
ms.openlocfilehash: ee9297ae917345d44d8e630bd09beea2245b56da
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415523"
---
# <a name="ulong-data-type-visual-basic"></a>ULong (tipo de datos) (Visual Basic)

Contiene enteros de 64 bits (8 bytes) sin signo que van en el valor de 0 a 18446744073709551615 (más de 1,84 veces 10 ^ 19).

## <a name="remarks"></a>Observaciones

Utilice el `ULong` tipo de datos para contener datos binarios demasiado grandes para `UInteger` o los valores enteros sin signo más grandes posibles.

El valor predeterminado de `ULong` es 0.

## <a name="literal-assignments"></a>Asignaciones literales

Puede declarar e inicializar una `ULong` variable asignándole un literal decimal, un literal hexadecimal, un literal octal o (empezando por Visual Basic 2017) un literal binario. Si el literal entero está fuera del intervalo de `ULong` (es decir, si es inferior a <xref:System.UInt64.MinValue?displayProperty=nameWithType> o mayor que <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, se produce un error de compilación.

En el ejemplo siguiente, los enteros que equivalen a 7 934 076 125 que se representan como literales binarios, hexadecimales y decimales se asignan a valores `ULong`.

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ULong)]

> [!NOTE]
> Use el prefijo `&h` o `&H` para denotar un literal hexadecimal, el prefijo `&b` o `&B` para denotar un literal binario, y el prefijo `&o` o `&O` para denotar un literal octal. Los literales decimales no tienen prefijo.

A partir de Visual Basic 2017, también puede usar el carácter de subrayado, `_` , como separador de dígitos para mejorar la legibilidad, como se muestra en el ejemplo siguiente.

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

A partir de Visual Basic 15,5, también puede usar el carácter de subrayado ( `_` ) como separador inicial entre el prefijo y los dígitos hexadecimales, binarios o octales. Por ejemplo:

```vb
Dim number As ULong = &H_F9AC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Los literales numéricos también pueden incluir el `UL` `ul` [carácter de tipo](../../programming-guide/language-features/data-types/type-characters.md) o para denotar el `ULong` tipo de datos, como se muestra en el ejemplo siguiente.

```vb
Dim number = &H_00_00_0A_96_2F_AC_14_D7ul
```

## <a name="programming-tips"></a>sugerencias de programación

- **Números negativos.** Dado `ULong` que es un tipo sin signo, no puede representar un número negativo. Si usa el operador unario menos ( `-` ) en una expresión que se evalúa como tipo `ULong` , Visual Basic convierte primero la expresión en `Decimal` .

- **Conformidad con CLS.** El `ULong` tipo de datos no forma parte de la [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), por lo que el código conforme a CLS no puede consumir un componente que lo utiliza.

- **Consideraciones de interoperabilidad.** Si interactúa con componentes que no se han escrito para el .NET Framework, por ejemplo, objetos de automatización o COM, tenga en cuenta que los tipos como `ulong` pueden tener un ancho de datos diferente (32 bits) en otros entornos. Si va a pasar un argumento de 32 bits a este componente, declárelo como `UInteger` en lugar de `ULong` en el código de Visual Basic administrado.

  Además, Automation no admite enteros de 64 bits en Windows 95, Windows 98, Windows ME o Windows 2000. No se puede pasar un `ULong` argumento Visual Basic a un componente de automatización en estas plataformas.

- **Ampliación.** El `ULong` tipo de datos se amplía a `Decimal` , `Single` y `Double` . Esto significa que puede convertir `ULong` en cualquiera de estos tipos sin que se produzca un <xref:System.OverflowException?displayProperty=nameWithType> error.

- **Caracteres de tipo.** Anexar los caracteres de tipo literal `UL` a un literal lo convierte al `ULong` tipo de datos. `ULong`no tiene ningún carácter de tipo de identificador.

- **Tipo de Framework.** El tipo correspondiente en .NET Framework es la estructura <xref:System.UInt64?displayProperty=nameWithType>.

## <a name="see-also"></a>Consulte también

- <xref:System.UInt64>
- [Tipos de datos](index.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Resumen de las conversiones](../keywords/conversion-summary.md)
- [Procedimiento Llamada una función de Windows que adopta tipos sin signo](../../programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Uso eficiente de los tipos de datos](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
