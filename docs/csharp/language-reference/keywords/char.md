---
title: 'Palabra clave char: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: 754c04bfc3b4090906420d55d55e51606b72f187
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69605953"
---
# <a name="char-c-reference"></a>char (Referencia de C#)

La palabra clave `char` se usa para declarar una instancia de la estructura <xref:System.Char?displayProperty=nameWithType> que .NET Framework usa para representar un carácter Unicode. El valor de un objeto `Char` es un valor numérico de 16 bits (ordinal).

 Los caracteres Unicode se usan para representar la mayoría de los idiomas escritos del mundo.

|Tipo|Intervalo|Tamaño|Tipo de .NET|
|----------|-----------|----------|-------------------------|
|`char`|U+0000 a U+FFFF|Carácter Unicode de 16 bits|<xref:System.Char?displayProperty=nameWithType>|

## <a name="literals"></a>Literales

Las constantes de tipo `char` pueden escribirse como literales de caracteres, secuencias de escape hexadecimal o representaciones Unicode. También se pueden convertir los códigos de caracteres enteros. En el siguiente ejemplo se inicializan cuatro variables `char` con el mismo carácter `X`:

[!code-csharp[csrefKeywordsTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#19)]

## <a name="conversions"></a>Conversiones

Un `char` se puede convertir implícitamente a [ushort](../builtin-types/integral-numeric-types.md), [int](../builtin-types/integral-numeric-types.md), [uint](../builtin-types/integral-numeric-types.md), [double](../builtin-types/floating-point-numeric-types.md) o [decimal](../builtin-types/floating-point-numeric-types.md). En cambio, no hay ninguna conversión implícita de otros tipos al tipo `char`.

El tipo <xref:System.Char?displayProperty=nameWithType> proporciona varios métodos estáticos para trabajar con valores `char`.

## <a name="c-language-specification"></a>Especificación del lenguaje C#  

Para obtener más información, vea la sección [Tipos enteros](~/_csharplang/spec/types.md#integral-types) de la [Especificación del lenguaje C#](../language-specification/index.md). La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.

## <a name="see-also"></a>Vea también

- <xref:System.Char>
- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](./index.md)
- [Tipos enteros](../builtin-types/integral-numeric-types.md)
- [Tabla de tipos integrados](./built-in-types-table.md)
- [Tabla de conversiones numéricas implícitas](./implicit-numeric-conversions-table.md)
- [Tabla de conversiones numéricas explícitas](./explicit-numeric-conversions-table.md)
- [Tipos que aceptan valores NULL](../../programming-guide/nullable-types/index.md)
- [Cadenas](../../programming-guide/strings/index.md)
