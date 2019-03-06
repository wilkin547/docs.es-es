---
title: 'Operador []: Referencia de C#'
ms.custom: seodec18
ms.date: 01/10/2019
f1_keywords:
- '[]_CSharpKeyword'
helpviewer_keywords:
- subscript operator [C#]
- square brackets [ ] operator [C#]
- '[] operator [C#]'
- indexing operator [C#]
ms.assetid: 5c16bb45-88f7-45ff-b42c-1af1972b042c
ms.openlocfilehash: 9088393f61d300ee76e56e320bec17b4a79bfebb
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "56835595"
---
# <a name="-operator-c-reference"></a>Operador [] (Referencia de C#)

Los corchetes, `[]`, se suelen usar para el acceso a matriz, indizador o elemento de puntero.

Para obtener más información sobre el acceso a elemento de puntero, consulte [Cómo: Obtener acceso a un elemento de matriz con un puntero](../../programming-guide/unsafe-code-pointers/how-to-access-an-array-element-with-a-pointer.md).

También usa los corchetes para especificar [atributos](../../programming-guide/concepts/attributes/index.md):

```csharp
[System.Diagnostics.Conditional("DEBUG")]
void TraceMethod() {}
```

## <a name="array-access"></a>Acceso a matriz

En el ejemplo siguiente se muestra cómo se obtiene acceso a los elementos de matriz:

[!code-csharp-interactive[array access](~/samples/snippets/csharp/language-reference/operators/IndexOperatorExamples.cs#Arrays)]

Si un índice de matriz se encuentra fuera de los límites de la dimensión correspondiente de una matriz, se produce una excepción <xref:System.IndexOutOfRangeException>.

Tal como se muestra en el ejemplo anterior, también usa corchetes en declaración de un tipo de matriz y la creación de instancias de matriz.

Para obtener más información sobre las matrices, consulte [Matrices](../../programming-guide/arrays/index.md).

## <a name="indexer-access"></a>Acceso a indizador

En el siguiente ejemplo se usa el tipo <xref:System.Collections.Generic.Dictionary%602> de .NET para mostrar el acceso a indizador:

[!code-csharp-interactive[indexer access](~/samples/snippets/csharp/language-reference/operators/IndexOperatorExamples.cs#Indexers)]

Los indizadores le permiten indizar las instancias de un tipo definido por el usuario de un modo similar a la indización de matrices. A diferencia de los índices de matriz, que deben ser enteros, los argumentos de indizador se pueden declarar para ser de cualquier tipo.

Para más información sobre los indizadores, consulte [Indizadores](../../programming-guide/indexers/index.md).

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

El acceso a elemento `[]` no se considera un operador sobrecargable. Use [indizadores](../../programming-guide/indexers/index.md) para admitir la indización con tipos definidos por el usuario.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, consulte las secciones [Acceso a elemento](~/_csharplang/spec/expressions.md#element-access) y [Acceso a elemento de puntero](~/_csharplang/spec/unsafe-code.md#pointer-element-access) de la [Especificación de lenguaje C#](../language-specification/index.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Operadores de C#](index.md)
- [Matrices](../../programming-guide/arrays/index.md)
- [Indizadores](../../programming-guide/indexers/index.md)
- [Tipos de puntero](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [Atributos](../../programming-guide/concepts/attributes/index.md)
- [Operadores ?. y ?[]](null-conditional-operators.md)