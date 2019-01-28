---
title: 'delegado: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- delegate_CSharpKeyword
- delegate
- CS0123
helpviewer_keywords:
- delegate keyword [C#]
- function pointers [C#]
ms.assetid: 0bb8cb6d-2f87-47c7-9d1f-d65c1cd01e9f
ms.openlocfilehash: f9df40c3ca721ca97b575a05377bbac29a29aec9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54560612"
---
# <a name="delegate-c-reference"></a>delegado (Referencia de C#)

La declaración de un tipo delegado es similar a una firma de método. Tiene un valor devuelto y un número cualquiera de parámetros de cualquier tipo:

```csharp
public delegate void TestDelegate(string message);
public delegate int TestDelegate(MyType m, long num);
```

Un `delegate` es un tipo de referencia que puede usarse para encapsular un método con nombre o anónimo. Los delegados son similares a los punteros de función en C++; pero son más seguros y proporcionan mayor seguridad de tipos. Para las aplicaciones de delegados, vea [Delegados](../../../csharp/programming-guide/delegates/index.md) y [Delegados genéricos](../../../csharp/programming-guide/generics/generic-delegates.md).

## <a name="remarks"></a>Comentarios

Los delegados son la base de los [eventos](../../../csharp/programming-guide/events/index.md).

Se pueden crear instancias de un delegado asociándolo a un método con nombre o anónimo. Para obtener más información, vea [Métodos con nombre](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) y [Métodos anónimos](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).

Para crear instancias del delegado debe usarse un método o una expresión lambda que tenga un tipo de valor devuelto y parámetros de entrada compatibles. Para obtener más información sobre el grado de variación permitida en la firma de método, vea [Varianza en delegados](../../programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md). Para el uso con métodos anónimos, el delegado y el código que se van a asociar se declaran juntos. En esta sección se describen las dos maneras de crear instancias de delegados.

## <a name="example"></a>Ejemplo

[!code-csharp[csrefKeywordsTypes#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#8)]

## <a name="c-language-specification"></a>Especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)
- [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)
- [Tipos de referencia](../../../csharp/language-reference/keywords/reference-types.md)
- [Delegados](../../../csharp/programming-guide/delegates/index.md)
- [Eventos](../../../csharp/programming-guide/events/index.md)
- [Delegados con métodos con nombre y delegados con métodos anónimos](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)
- [Métodos anónimos](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)
- [Expresiones lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)
