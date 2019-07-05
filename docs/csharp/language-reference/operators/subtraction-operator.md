---
title: '- Operadores - y -= (referencia de C#)'
ms.custom: seodec18
ms.date: 05/27/2019
f1_keywords:
- -_CSharpKeyword
- -=_CSharpKeyword
helpviewer_keywords:
- subtraction operator [C#]
- delegate removal [C#]
- '- operator [C#]'
- subtraction assignment operator [C#]
- event unsubscription [C#]
- -= operator [C#]
ms.assetid: 4de7a4fa-c69d-48e6-aff1-3130af970b2d
ms.openlocfilehash: 7c9863134cb2a12072954bb283c7828abece3adb
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2019
ms.locfileid: "67347907"
---
# <a name="--and---operators-c-reference"></a>Operadores - y -= (referencia de C#)

El operador `-` es compatible con los tipos numéricos integrados y los tipos [delegados](../keywords/delegate.md).

Para obtener información sobre el operador aritmético `-`, consulte las secciones correspondientes a los [operadores unarios más y menos](arithmetic-operators.md#unary-plus-and-minus-operators) y al [operador de resta (-)](arithmetic-operators.md#subtraction-operator--) del artículo [Operadores aritméticos](arithmetic-operators.md).

## <a name="delegate-removal"></a>Eliminación de delegados

Para los operandos del mismo tipo [delegado](../keywords/delegate.md), el operador `-` devuelve una instancia de delegado que se calcula de la siguiente manera:

- Si ambos operandos no son nulos y la lista de invocación del operando derecho es una sublista apropiada contigua de la lista de invocación del operando izquierdo, el resultado de la operación es una nueva lista de invocación que se obtiene mediante la eliminación de las entradas del operando derecho de la lista de invocación del operando izquierdo. Si la lista del operando derecho coincide con varias sublistas contiguas en la lista del operando izquierdo, se quita solo la sublista coincidente más a la derecha. Si la eliminación da como resultado una lista vacía, el resultado es `null`.

  [!code-csharp-interactive[delegate removal](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#DelegateRemoval)]

- Si la lista de invocación del operando derecho no es una sublista apropiada contigua de la lista de invocación del operando izquierdo, el resultado de la operación es el operando izquierdo. Por ejemplo, la eliminación de un delegado que no forma parte del delegado de multidifusión no surte ningún efecto y da como resultado que el delegado de multidifusión no cambie.

  [!code-csharp-interactive[delegate removal with no effect](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#DelegateRemovalNoChange)]

  El ejemplo anterior también demuestra que, durante la eliminación de delegados, se comparan las instancias de delegados. Por ejemplo, los delegados que se producen de la evaluación de [expresiones lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md) idénticas no son iguales. Para obtener más información acerca de la igualdad de delegados, consulte la sección [Operadores de igualdad de delegado](~/_csharplang/spec/expressions.md#delegate-equality-operators) de la [especificación del lenguaje C#](../language-specification/index.md).

- Si el operando izquierdo es `null`, el resultado de la operación es `null`. Si el operando derecho es `null`, el resultado de la operación es el operando izquierdo.

  [!code-csharp-interactive[delegate removal and null](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#DelegateRemovalAndNull)]

Para combinar delegados, utilice el [operador `+`](addition-operator.md#delegate-combination).

Para más información sobre los tipos de delegado, vea [Delegados](../../programming-guide/delegates/index.md).

## <a name="subtraction-assignment-operator--"></a>Operador de resta y asignación (-=)

Una expresión que usa el operador `-=`, como

```csharp
x -= y
```

es equivalente a

```csharp
x = x - y
```

salvo que `x` solo se evalúa una vez.
  
En el siguiente ejemplo se muestra el uso del operador `-=`:

[!code-csharp-interactive[-= examples](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#SubtractAndAssign)]

También se usa el operador `-=` con el fin de especificar un método de controlador de eventos para eliminar cuando se finaliza la suscripción a un [evento](../keywords/event.md). Para obtener más información, vea [Procedimientos para suscribir y cancelar la suscripción a eventos](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

Un tipo definido por el usuario puede [sobrecargar](../keywords/operator.md) el operador `-`. Cuando se sobrecarga un operador `-` binario, el operador `-=` también se sobrecarga de modo implícito. Un tipo definido por el usuario no puede sobrecargar de forma explícita el operador `-=`.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, consulte las secciones correspondientes al [operador unario menos](~/_csharplang/spec/expressions.md#unary-minus-operator) y al [operador de resta](~/_csharplang/spec/expressions.md#subtraction-operator) de [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Operadores de C#](index.md)
- [Delegados](../../programming-guide/delegates/index.md)
- [Eventos](../../programming-guide/events/index.md)
- [Operadores aritméticos](arithmetic-operators.md)
- [Operadores + y += ](addition-operator.md)
