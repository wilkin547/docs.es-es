---
title: 'Palabra clave char: referencia de C#'
ms.custom: seodec18
ms.date: 10/22/2019
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: 1b9f8d1bb205a6cbfe521830a11bd8878ccde991
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771803"
---
# <a name="char-c-reference"></a>char (referencia de C#)

La palabra clave de tipo `char` es un alias para el tipo de estructura de .NET <xref:System.Char?displayProperty=nameWithType> que representa un carácter Unicode UTF-16:

|Tipo|Intervalo|Tamaño|Tipo de .NET|
|----------|-----------|----------|-------------------------|
|`char`|U+0000 a U+FFFF|16 bits|<xref:System.Char?displayProperty=nameWithType>|

## <a name="literals"></a>Literales

Las constantes de tipo `char` pueden escribirse como literales de caracteres, secuencias de escape hexadecimal o representaciones Unicode. También puede convertir un código de carácter entero en el valor `char` correspondiente. En el siguiente ejemplo, los cuatro elementos de una matriz de `char` se inicializan con el mismo carácter `X`:

[!code-csharp[csrefKeywordsTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#19)]

## <a name="conversions"></a>Conversiones

El tipo `char` se puede convertir implícitamente en los tipos [enteros](../builtin-types/integral-numeric-types.md) siguientes: `ushort`, `int`, `uint`, `long` y `ulong`. También se puede convertir implícitamente en los tipos numéricos de [punto flotante](../builtin-types/floating-point-numeric-types.md) integrados: `float`, `double` y `decimal`. Se puede convertir explícitamente en los tipos enteros `sbyte`, `byte` y `short`.

No hay ninguna conversión implícita de otros tipos al tipo `char`. Sin embargo, cualquier tipo numérico [entero](../builtin-types/integral-numeric-types.md) o de [punto flotante](../builtin-types/floating-point-numeric-types.md) es implícitamente convertible a `char`.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, consulte la sección [Tipos enteros](~/_csharplang/spec/types.md#integral-types) de [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Palabras clave de C#](./index.md)
- [Tabla de tipos integrados](./built-in-types-table.md)
- [Cadenas](../../programming-guide/strings/index.md)
- <xref:System.Char?displayProperty=nameWithType>
