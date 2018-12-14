---
title: Instrucción foreach de C#
ms.date: 06/29/2018
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: 417a8cefbc9bc7544ae1156992e6e6c549fb828f
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53128627"
---
# <a name="foreach-in-c-reference"></a>foreach, in (Referencia de C#)

La instrucción `foreach` ejecuta una instrucción o un bloque de instrucciones para cada elemento en una instancia del tipo que implementa la interfaz <xref:System.Collections.IEnumerable?displayProperty=nameWithType> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>. La instrucción `foreach` no se limita a esos tipos y puede aplicarse a una instancia de cualquier tipo que satisfaga las siguientes condiciones:

- tiene el método público sin parámetros `GetEnumerator` cuyo tipo de valor devuelto es clase, estructura o tipo de interfaz,
- el tipo de valor devuelto del método `GetEnumerator` tiene la propiedad pública `Current` y el método público sin parámetros `MoveNext` cuyo tipo de valor devuelto es <xref:System.Boolean>.

A partir de C# 7.3, si la propiedad `Current` del enumerador devuelve un [valor devuelto de referencia](ref.md#reference-return-values) (`ref T` donde `T` es el tipo del elemento de colección), se puede declarar la variable de iteración con el modificador `ref` o `ref readonly`.

En cualquier punto del bloque de instrucciones `foreach`, se puede salir del bucle mediante la instrucción [break](break.md), o bien se puede ir a la siguiente iteración del bucle mediante la instrucción [continue](continue.md). También se puede salir de un bucle `foreach` mediante las instrucciones [goto](goto.md), [return](return.md) o [throw](throw.md).

## <a name="examples"></a>Ejemplos

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

El siguiente ejemplo muestra el uso de la instrucción `foreach` con una instancia del tipo <xref:System.Collections.Generic.List%601> que implementa la interfaz <xref:System.Collections.Generic.IEnumerable%601>:

[!code-csharp-interactive[list example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#1)]

El siguiente ejemplo utiliza la instrucción `foreach` con una instancia del tipo <xref:System.Span%601?displayProperty=nameWithType>, que no implementa ninguna interfaz:

[!code-csharp-interactive[span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#2)]

En el ejemplo siguiente se usa una variable de iteración `ref` para establecer el valor de cada elemento de una matriz stackalloc. La versión `ref readonly` recorre en iteración la colección para imprimir todos los valores. En la declaración de `readonly`, se usa una declaración de variable local implícita. Las declaraciones de variables implícitas se pueden usar con las declaraciones `ref` o `ref readonly`, al igual que las declaraciones de variables con tipo explícito.

[!code-csharp-interactive[ref span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#RefSpan)]

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, vea la sección sobre la [instrucción foreach](~/_csharplang/spec/statements.md#the-foreach-statement) de la [Especificación del lenguaje C#](../language-specification/index.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [Instrucciones de iteración](iteration-statements.md)
- [Utilizar foreach con matrices](../../programming-guide/arrays/using-foreach-with-arrays.md)
- [for (Instrucción)](for.md)
