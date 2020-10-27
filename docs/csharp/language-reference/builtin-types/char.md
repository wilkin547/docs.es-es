---
description: Más información sobre el tipo de carácter integrado en C#
title: 'Tipo char: Referencia de C#'
ms.date: 05/11/2020
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: 1cb40759b81a1fcedcf5962b57d79cf3a64df561
ms.sourcegitcommit: 870bc4b4087510f6fba3c7b1c0d391f02bcc1f3e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2020
ms.locfileid: "92471881"
---
# <a name="char-c-reference"></a>char (referencia de C#)

La palabra clave de tipo `char` es un alias para el tipo de estructura de .NET <xref:System.Char?displayProperty=nameWithType> que representa un carácter Unicode UTF-16.

|Tipo|Intervalo|Tamaño|Tipo de .NET|
|----------|-----------|----------|-------------------------|
|`char`|U+0000 a U+FFFF|16 bits|<xref:System.Char?displayProperty=nameWithType>|

El valor predeterminado del tipo `char` es `\0`, es decir, U+0000.

El tipo `char` admite operadores de [comparación](../operators/comparison-operators.md), [igualdad](../operators/equality-operators.md), [incremento](../operators/arithmetic-operators.md#increment-operator-) y [decremento](../operators/arithmetic-operators.md#decrement-operator---). Además, en el caso de los operandos `char`, los operadores [aritméticos](../operators/arithmetic-operators.md) y [lógicos bit a bit](../operators/bitwise-and-shift-operators.md) realizan una operación en los códigos de caracteres correspondientes y producen el resultado del tipo `int`.

El tipo [string](reference-types.md#the-string-type) representa el texto como una secuencia de valores `char`.

## <a name="literals"></a>Literales

Puede especificar un valor de `char` con:

- un literal de carácter.
- una secuencia de escape Unicode, que es `\u` seguido de la representación hexadecimal de cuatro símbolos de un código de carácter.
- una secuencia de escape hexadecimal, que es `\x` seguido de la representación hexadecimal de un código de carácter.

[!code-csharp-interactive[char literals](snippets/shared/CharType.cs#Literals)]

Como se muestra en el ejemplo anterior, también puede convertir el valor de un código de carácter en el valor de `char` correspondiente.

> [!NOTE]
> En el caso de una secuencia de escape Unicode, debe especificar los cuatro dígitos hexadecimales. Es decir, `\u006A` es una secuencia de escape válida, mientras que `\u06A` y `\u6A` no son válidas.
>
> En el caso de una secuencia de escape hexadecimal, puede omitir los ceros a la izquierda. Es decir, las secuencias de escape `\x006A`, `\x06A`y `\x6A` son válidas y se corresponden con el mismo carácter.

## <a name="conversions"></a>Conversiones

El tipo `char` se puede convertir implícitamente en los tipos [enteros](integral-numeric-types.md) siguientes: `ushort`, `int`, `uint`, `long` y `ulong`. También se puede convertir implícitamente en los tipos numéricos de [punto flotante](floating-point-numeric-types.md) integrados: `float`, `double` y `decimal`. Se puede convertir explícitamente en los tipos enteros `sbyte`, `byte` y `short`.

No hay ninguna conversión implícita de otros tipos al tipo `char`. Sin embargo, cualquier tipo numérico [entero](integral-numeric-types.md) o de [punto flotante](floating-point-numeric-types.md) es implícitamente convertible a `char`.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, consulte la sección [Tipos enteros](~/_csharplang/spec/types.md#integral-types) de [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Tipos de valor](value-types.md)
- [Cadenas](../../programming-guide/strings/index.md)
- <xref:System.Text.Rune?displayProperty=nameWithType>
- [Codificación de caracteres de .NET](../../../standard/base-types/character-encoding-introduction.md)
