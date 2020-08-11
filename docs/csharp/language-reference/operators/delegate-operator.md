---
title: 'Operador delegate: referencia de C#'
ms.date: 07/18/2019
helpviewer_keywords:
- delegate [C#]
- anonymous method [C#]
ms.openlocfilehash: f7cd7caf11d9f076a5d6e82aae696c914bd60e44
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916845"
---
# <a name="delegate-operator-c-reference"></a>Operador delegate (referencia de C#)

El operador `delegate` crea un método anónimo que se puede convertir en un tipo delegado:

[!code-csharp-interactive[anonymous method](snippets/shared/DelegateOperator.cs#AnonymousMethod)]

> [!NOTE]
> A partir de C# 3, las expresiones lambda proporcionan una manera más concisa y expresiva de crear una función anónima. Use el [operador =>](lambda-operator.md) para construir una expresión lambda:
>
> [!code-csharp-interactive[lambda expression](snippets/shared/DelegateOperator.cs#Lambda)]
>
> Para más información sobre las características de las expresiones lambda, como capturar las variables externas, consulte [Expresiones lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md).

Al usar el operador `delegate`, puede omitir la lista de parámetros. Si lo hace, el método anónimo creado se puede convertir en un tipo delegado con cualquier lista de parámetros, tal como se muestra en el ejemplo siguiente:

[!code-csharp-interactive[no parameter list](snippets/shared/DelegateOperator.cs#WithoutParameterList)]

Esta es la única funcionalidad de los métodos anónimos que las expresiones lambda no admiten. En todos los demás casos, una expresión lambda es una de las maneras preferidas de escribir código alineado.

También puede usar la palabra clave `delegate` para declarar un [tipo delegado](../builtin-types/reference-types.md#the-delegate-type).

## <a name="c-language-specification"></a>especificación del lenguaje C#

Para obtener más información, vea la sección [Expresiones de función anónima](~/_csharplang/spec/expressions.md#anonymous-function-expressions) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Operadores y expresiones de C#](index.md)
- [Operador =>](lambda-operator.md)
