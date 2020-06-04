---
title: Tipo de datos SByte
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
ms.openlocfilehash: e7d45c74056ce5b6aa66674c99e48b5ab60015f0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415575"
---
# <a name="sbyte-data-type-visual-basic"></a>SByte (tipo de datos, Visual Basic)

Contiene enteros de 8 bits con signo (1 byte) que oscilan entre-128 y 127.

## <a name="remarks"></a>Observaciones

Utilice el `SByte` tipo de datos para contener valores enteros que no requieran el ancho completo de los datos `Integer` o incluso el ancho medio de los datos `Short` . En algunos casos, es posible que el Common Language Runtime pueda empaquetar las `SByte` variables en estrecha colaboración y ahorrar consumo de memoria.

El valor predeterminado de `SByte` es 0.

## <a name="literal-assignments"></a>Asignaciones literales

Puede declarar e inicializar una `SByte` variable asignándole un literal decimal, un literal hexadecimal, un literal octal o (empezando por Visual Basic 2017) un literal binario.

En el ejemplo siguiente, los enteros iguales a-102 que se representan como literales binarios, hexadecimales y decimales se asignan a `SByte` valores. Este ejemplo requiere que se compile con el `/removeintchecks` modificador del compilador.

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]

> [!NOTE]
> Use el prefijo `&h` o `&H` para denotar un literal hexadecimal, el prefijo `&b` o `&B` para denotar un literal binario, y el prefijo `&o` o `&O` para denotar un literal octal. Los literales decimales no tienen prefijo.

A partir de Visual Basic 2017, también puede usar el carácter de subrayado, `_` , como separador de dígitos para mejorar la legibilidad, como se muestra en el ejemplo siguiente.

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]

A partir de Visual Basic 15,5, también puede usar el carácter de subrayado ( `_` ) como separador inicial entre el prefijo y los dígitos hexadecimales, binarios o octales. Por ejemplo:

```vb
Dim number As SByte = &H_F9
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Si el literal entero está fuera del intervalo de `SByte` (es decir, si es inferior a <xref:System.SByte.MinValue?displayProperty=nameWithType> o mayor que <xref:System.SByte.MaxValue?displayProperty=nameWithType>, se produce un error de compilación. Cuando un literal entero no tiene sufijo, se infiere un [entero](integer-data-type.md) . Si el literal entero está fuera del intervalo del `Integer` tipo, se deduce un [valor Long](long-data-type.md) . Esto significa que, en los ejemplos anteriores, los literales numéricos `0x9A` y `0b10011010` se interpretan como enteros con signo de 32 bits con un valor de 156, que supera <xref:System.SByte.MaxValue?displayProperty=nameWithType> . Para compilar correctamente código como este que asigna un entero no decimal a un `SByte` , puede realizar una de las siguientes acciones:

- Deshabilite las comprobaciones de los límites de enteros compilando con el `/removeintchecks` modificador del compilador.

- Use un [carácter de tipo](../../programming-guide/language-features/data-types/type-characters.md) para definir explícitamente el valor literal que desea asignar a `SByte` . En el ejemplo siguiente se asigna un valor literal negativo `Short` a un `SByte` . Tenga en cuenta que, para los números negativos, debe establecerse el bit de orden superior de la palabra de orden superior del literal numérico. En el caso de nuestro ejemplo, es el bit 15 del valor literal `Short` .

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a>sugerencias de programación

- **Conformidad con CLS.** El `SByte` tipo de datos no forma parte de la [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), por lo que el código conforme a CLS no puede consumir un componente que lo utiliza.

- **Ampliación.** El `SByte` tipo de datos se amplía a `Short` , `Integer` , `Long` , `Decimal` , `Single` y `Double` . Esto significa que puede convertir `SByte` en cualquiera de estos tipos sin que se produzca un <xref:System.OverflowException?displayProperty=nameWithType> error.

- **Caracteres de tipo.** `SByte`no tiene un carácter de tipo literal o un carácter de tipo de identificador.

- **Tipo de Framework.** El tipo correspondiente en .NET Framework es la estructura <xref:System.SByte?displayProperty=nameWithType>.

## <a name="see-also"></a>Consulte también

- <xref:System.SByte?displayProperty=nameWithType>
- [Tipos de datos](index.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Resumen de las conversiones](../keywords/conversion-summary.md)
- [Tipo de datos Short](short-data-type.md)
- [Tipo de datos Integer](integer-data-type.md)
- [Tipo de datos Long](long-data-type.md)
- [Uso eficiente de los tipos de datos](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
