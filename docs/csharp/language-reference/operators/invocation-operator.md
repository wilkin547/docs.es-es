---
title: 'Operador (): Referencia de C#'
ms.custom: seodec18
ms.date: 01/15/2019
f1_keywords:
- ()_CSharpKeyword
helpviewer_keywords:
- type conversion [C#], () operator
- cast operator [C#]
- () operator [C#]
ms.assetid: 846e1f94-8a8c-42fc-a42c-fbd38e70d8cc
ms.openlocfilehash: 8f7382a49c81b6fd8e104b864ffc2f70db7fe4a6
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758113"
---
# <a name="-operator-c-reference"></a>Operador () (Referencia de C#)

Los paréntesis, `()`, se suelen usar para la invocación de método o delegado, o en expresiones Cast.

También usa los paréntesis para especificar el orden en el que se van a evaluar operaciones en una expresión. Para más información, consulte la sección [Agregar paréntesis](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses) del artículo [Operadores](../../programming-guide/statements-expressions-operators/operators.md). Para ver la lista de operadores ordenados por nivel de precedencia, consulte [Operadores de C#](index.md).

## <a name="method-invocation"></a>Invocación del método.

En el ejemplo siguiente se muestra cómo invocar un método, con o sin argumentos, y un delegado:

[!code-csharp-interactive[use for invocation](~/samples/csharp/language-reference/operators/InvocationOperatorExamples.cs#Invocation)]

También usa paréntesis al invocar un [constructor](../../programming-guide/classes-and-structs/constructors.md) con un operador [`new`](../keywords/new-operator.md).

Para obtener más información sobre los métodos, consulte [Métodos](../../programming-guide/classes-and-structs/methods.md). Para obtener más información sobre los delegados, consulte [Delegados](../../programming-guide/delegates/index.md).

## <a name="cast-expression"></a>Expresión Cast

Una expresión Cast con el formato `(T)E` invoca un operador de conversión para convertir el valor de la expresión `E` en el tipo `T`. Si no existe ninguna conversión explícita del tipo de `E` al tipo `T`, se producirá un error en tiempo de compilación. Para obtener información sobre cómo definir un operador de conversión, consulte los artículos sobre las palabras clave [explicit](../keywords/explicit.md) e [implicit](../keywords/implicit.md).

En el siguiente ejemplo se muestra la conversión de tipos entre los tipos numéricos:

[!code-csharp-interactive[use for cast](~/samples/csharp/language-reference/operators/InvocationOperatorExamples.cs#Cast)]

Para obtener más información sobre las conversiones explícitas predefinidas entre tipos numéricos, consulte [Tabla de conversiones numéricas explícitas](../keywords/explicit-numeric-conversions-table.md).

Para obtener más información, consulte [Conversiones de tipos](../../programming-guide/types/casting-and-type-conversions.md) y [Operadores de conversión](../../programming-guide/statements-expressions-operators/conversion-operators.md).

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

El operador `()` no se puede sobrecargar.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, consulte las secciones [Expresiones de invocación](~/_csharplang/spec/expressions.md#invocation-expressions) y [Expresiones Cast](~/_csharplang/spec/expressions.md#cast-expressions) de la [especificación del lenguaje C#](../language-specification/index.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Operadores de C#](index.md)
