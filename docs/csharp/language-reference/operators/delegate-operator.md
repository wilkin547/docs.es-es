---
title: 'Operador delegate: referencia de C#'
ms.date: 07/18/2019
helpviewer_keywords:
- delegate [C#]
- anonymous method [C#]
ms.openlocfilehash: 1fe281776bd75d8fa869065cd24e85f04fec849d
ms.sourcegitcommit: 09d699aca28ae9723399bbd9d3d44aa0cbd3848d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/19/2019
ms.locfileid: "68331834"
---
# <a name="delegate-operator-c-reference"></a>Operador delegate (referencia de C#)

El operador `delegate` crea un método anónimo que se puede convertir en un tipo delegado:

[!code-csharp-interactive[anonymous method](~/samples/csharp/language-reference/operators/DelegateOperator.cs#AnonymousMethod)]

A partir de C# 3, las [expresiones lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md) brindan una manera más concisa y expresiva para crear una función anónima. Use el [operador =>](lambda-operator.md) para construir una expresión lambda:

[!code-csharp-interactive[lambda expression](~/samples/csharp/language-reference/operators/DelegateOperator.cs#Lambda)]

Al usar el operador `delegate`, puede omitir la lista de parámetros. Si lo hace, el método anónimo creado se puede convertir en un tipo delegado con cualquier lista de parámetros, tal como se muestra en el ejemplo siguiente:

[!code-csharp-interactive[no parameter list](~/samples/csharp/language-reference/operators/DelegateOperator.cs#WithoutParameterList)]

Esta es la única funcionalidad de los métodos anónimos que las expresiones lambda no admiten. En todos los demás casos, una expresión lambda es una de las maneras preferidas de escribir código alineado. Para más información sobre las características de las expresiones lambda, como capturar las variables externas, consulte [Expresiones lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md).

También puede usar la palabra clave `delegate` para declarar un [tipo delegado](../builtin-types/reference-types.md#the-delegate-type).

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, vea la sección [Expresiones de función anónima](~/_csharplang/spec/expressions.md#anonymous-function-expressions) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Operadores de C#](index.md)
