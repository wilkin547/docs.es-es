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
ms.openlocfilehash: 01a0a4a261213d7e6e2016bf49128092e5b22308
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401386"
---
# <a name="sbyte-data-type-visual-basic"></a>Tipo de datos SByte (Visual Basic)

Contiene enteros de 8 bits (1 byte) con signo que oscilan en valor de -128 a 127.

## <a name="remarks"></a>Observaciones

Utilice `SByte` el tipo de datos para contener valores enteros `Integer` que no requieren `Short`el ancho de datos completo o incluso el medio ancho de datos de . En algunos casos, Common Language Runtime podría `SByte` empaquetar las variables estrechamente juntas y ahorrar consumo de memoria.

El valor predeterminado de `SByte` es 0.

## <a name="literal-assignments"></a>Asignaciones literales

Puede declarar e `SByte` inicializar una variable asignándole un literal decimal, un literal hexadecimal, un literal octal o (a partir de Visual Basic 2017) un literal binario.

En el ejemplo siguiente, los enteros iguales a -102 que se representan `SByte` como literales decimales, hexadecimales y binarios se asignan a los valores. En este ejemplo es necesario `/removeintchecks` compilar con el modificador del compilador.

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]

> [!NOTE]
> Utilice el `&h` prefijo `&H` o para denotar un `&b` `&B` literal hexadecimal, el prefijo o `&o` `&O` para denotar un literal binario, y el prefijo o para denotar un literal octal. Los literales decimales no tienen prefijo.

A partir de Visual Basic 2017, también `_`puede usar el carácter de subrayado, , como separador de dígitos para mejorar la legibilidad, como se muestra en el ejemplo siguiente.

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]

A partir de Visual Basic 15.5, también`_`puede usar el carácter de subrayado ( ) como separador inicial entre el prefijo y los dígitos hexadecimales, binarios u octales. Por ejemplo:

```vb
Dim number As SByte = &H_F9
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Si el literal entero está fuera del intervalo de `SByte` (es decir, si es inferior a <xref:System.SByte.MinValue?displayProperty=nameWithType> o mayor que <xref:System.SByte.MaxValue?displayProperty=nameWithType>, se produce un error de compilación. Cuando un literal entero no tiene sufijo, se deduce un [entero.](integer-data-type.md) Si el literal entero está `Integer` fuera del intervalo del tipo, se deduce un [Long.](long-data-type.md) Esto significa que, en los ejemplos `0x9A` anteriores, los literales numéricos y `0b10011010` se interpretan como enteros <xref:System.SByte.MaxValue?displayProperty=nameWithType>con signo de 32 bits con un valor de 156, que supera . Para compilar correctamente código como este que asigna un `SByte`entero no decimal a un , puede realizar una de las siguientes acciones:

- Deshabilite las comprobaciones de límites `/removeintchecks` enteros compilando con el modificador del compilador.

- Utilice un [carácter](../../programming-guide/language-features/data-types/type-characters.md) de tipo para definir explícitamente `SByte`el valor literal que desea asignar al archivo . En el ejemplo siguiente `Short` se asigna `SByte`un valor literal negativo a un archivo . Tenga en cuenta que, para los números negativos, se debe establecer el bit de orden superior de la palabra de orden superior del literal numérico. En el caso de nuestro ejemplo, este `Short` es el bit 15 del valor literal.

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a>sugerencias de programación

- **Cumplimiento de CLS.** El `SByte` tipo de datos no forma parte de [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), por lo que el código compatible con CLS no puede consumir un componente que lo utilice.

- **Ampliación.** El `SByte` tipo de datos `Short` `Integer`se `Long` `Decimal`amplía `Single`a `Double`, , , , y . Esto significa que `SByte` puede convertir a cualquiera <xref:System.OverflowException?displayProperty=nameWithType> de estos tipos sin encontrar un error.

- **Escriba Caracteres.** `SByte`no tiene ningún carácter de tipo literal o carácter de tipo identificador.

- **Tipo de Framework.** El tipo correspondiente en .NET Framework es la estructura <xref:System.SByte?displayProperty=nameWithType>.

## <a name="see-also"></a>Consulte también

- <xref:System.SByte?displayProperty=nameWithType>
- [Tipos de datos](../../../visual-basic/language-reference/data-types/index.md)
- [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Short (tipo de datos)](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [Tipo de datos enteros](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [Long (tipo de datos)](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
