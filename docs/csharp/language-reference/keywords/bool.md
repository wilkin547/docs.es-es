---
title: bool (palabra clave) - Referencia de C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- bool_CSharpKeyword
- bool
helpviewer_keywords:
- bool keyword [C#]
ms.assetid: 551cfe35-2632-4343-af49-33ad12da08e2
ms.openlocfilehash: d87da29872582e9c0d47a6c999312ce88252a5cc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59334177"
---
# <a name="bool-c-reference"></a>bool (Referencia de C#)

La palabra clave `bool` es un alias de <xref:System.Boolean?displayProperty=nameWithType>. Se usa para declarar variables que almacenan los valores booleanos [true](true-literal.md) y [false](false-literal.md).

> [!NOTE]
> Use el tipo `bool?`, si tiene que admitir la lógica de tres valores, por ejemplo, cuando trabaja con bases de datos que admiten un tipo booleano de tres valores. En el caso de los operandos `bool?`, los operadores predefinidos `&` y `|` admiten la lógica de tres valores. Para más información, consulte la sección [Operadores lógicos booleanos que aceptan valores NULL](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) del artículo [Operadores lógicos booleanos](../operators/boolean-logical-operators.md).

## <a name="literals"></a>Literales

Se puede asignar un valor booleano a una variable `bool`. También se puede asignar una expresión que se evalúe como `bool` a una variable `bool`.

[!code-csharp[csrefKeywordsTypes#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#1)]

El valor predeterminado de una variable `bool` es `false`. El valor predeterminado de una variable `bool?` es `null`.

## <a name="conversions"></a>Conversiones

En C++, un valor de tipo `bool` se puede convertir en un valor de tipo `int`, es decir, `false` equivale a cero y `true` equivale a valores distintos de cero. En C#, no hay ninguna conversión entre el tipo `bool` y otros tipos. Por ejemplo, la siguiente instrucción `if` no es válida en C#:

[!code-csharp[csrefKeywordsTypes#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#2)]

Para probar una variable del tipo `int`, tendrá que compararla explícitamente con un valor, como cero, del modo siguiente:

[!code-csharp[csrefKeywordsTypes#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#3)]

## <a name="example"></a>Ejemplo

En este ejemplo, se escribe un carácter desde el teclado y el programa comprueba si el carácter de entrada es una letra. Si es una letra, comprueba si está en mayúsculas o minúsculas. Estas comprobaciones se realizan con <xref:System.Char.IsLetter%2A> y <xref:System.Char.IsLower%2A>; ambos devuelven el tipo `bool`:

[!code-csharp[csrefKeywordsTypes#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#4)]

## <a name="c-language-specification"></a>Especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)
- [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)
- [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md)
- [Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md)
- [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
- [Tabla de conversiones numéricas explícitas](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
