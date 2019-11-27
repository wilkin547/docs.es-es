---
title: SByte (Tipo de datos)
ms.date: 04/20/2017
f1_keywords:
- vb.sbyte
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- SByte data type
ms.assetid: 5c38374a-18a1-4cc2-b493-299e3dcaa60f
ms.openlocfilehash: 01a0a4a261213d7e6e2016bf49128092e5b22308
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343948"
---
# <a name="sbyte-data-type-visual-basic"></a>SByte (tipo de datos, Visual Basic)

Contiene enteros de 8 bits con signo (1 byte) que oscilan entre-128 y 127.

## <a name="remarks"></a>Comentarios

Utilice el tipo de datos `SByte` para contener valores enteros que no requieran el ancho completo de los datos de `Integer` ni siquiera el ancho de datos medio de `Short`. En algunos casos, es posible que el Common Language Runtime pueda empaquetar las variables de `SByte` en estrecha colaboración y ahorrar consumo de memoria.

El valor predeterminado de `SByte` es 0.

## <a name="literal-assignments"></a>Asignaciones literales

Puede declarar e inicializar una variable de `SByte` asignándole un literal decimal, un literal hexadecimal, un literal octal o (empezando por Visual Basic 2017) un literal binario.

En el ejemplo siguiente, los enteros iguales a-102 que se representan como literales binarios, hexadecimales y decimales se asignan a los valores de `SByte`. En este ejemplo, es necesario compilar con el `/removeintchecks` modificador del compilador.

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]

> [!NOTE]
> Use el prefijo `&h` o `&H` para indicar un literal hexadecimal, el prefijo `&b` o `&B` para denotar un literal binario y el prefijo `&o` o `&O` para denotar un literal octal. Los literales decimales no tienen prefijo.

A partir de Visual Basic 2017, también puede usar el carácter de subrayado, `_`, como separador de dígitos para mejorar la legibilidad, como se muestra en el ejemplo siguiente.

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]

A partir de Visual Basic 15,5, también puede usar el carácter de subrayado (`_`) como separador inicial entre el prefijo y los dígitos hexadecimales, binarios o octales. Por ejemplo:

```vb
Dim number As SByte = &H_F9
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Si el literal entero está fuera del intervalo de `SByte` (es decir, si es inferior a <xref:System.SByte.MinValue?displayProperty=nameWithType> o mayor que <xref:System.SByte.MaxValue?displayProperty=nameWithType>), se produce un error de compilación. Cuando un literal entero no tiene sufijo, se infiere un [entero](integer-data-type.md) . Si el literal entero está fuera del intervalo del tipo de `Integer`, se deduce un [valor Long](long-data-type.md) . Esto significa que, en los ejemplos anteriores, los literales numéricos `0x9A` y `0b10011010` se interpretan como enteros con signo de 32 bits con un valor de 156, que supera <xref:System.SByte.MaxValue?displayProperty=nameWithType>. Para compilar correctamente un código similar al siguiente que asigna un entero no decimal a un `SByte`, puede realizar una de las siguientes acciones:

- Deshabilite las comprobaciones de los límites de enteros compilando con el `/removeintchecks` modificador del compilador.

- Use un [carácter de tipo](../../programming-guide/language-features/data-types/type-characters.md) para definir explícitamente el valor literal que desea asignar a la `SByte`. En el ejemplo siguiente se asigna un literal negativo `Short` valor a un `SByte`. Tenga en cuenta que, para los números negativos, debe establecerse el bit de orden superior de la palabra de orden superior del literal numérico. En el caso de nuestro ejemplo, es el bit 15 del valor literal `Short`.

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a>sugerencias de programación

- **Conformidad con CLS.** El tipo de datos `SByte` no forma parte de la [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), por lo que el código conforme a CLS no puede consumir un componente que lo utiliza.

- **Ampliación.** El tipo de datos `SByte` se amplía a `Short`, `Integer`, `Long`, `Decimal`, `Single`y `Double`. Esto significa que puede convertir `SByte` en cualquiera de estos tipos sin encontrar un error de <xref:System.OverflowException?displayProperty=nameWithType>.

- **Caracteres de tipo.** `SByte` no tiene un carácter de tipo literal o un carácter de tipo de identificador.

- **Tipo de marco.** El tipo correspondiente en .NET Framework es la estructura <xref:System.SByte?displayProperty=nameWithType>.

## <a name="see-also"></a>Vea también

- <xref:System.SByte?displayProperty=nameWithType>
- [Tipos de datos](../../../visual-basic/language-reference/data-types/index.md)
- [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Short (tipo de datos)](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [Integer (tipo de datos)](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [Long (tipo de datos)](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
