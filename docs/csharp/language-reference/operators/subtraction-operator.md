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
ms.openlocfilehash: 9f43a863de69122e251204668af2ea989fcc993c
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300086"
---
# <a name="--and---operators-c-reference"></a>Operadores - y -= (referencia de C#)

El operador `-` es compatible con los tipos numéricos integrados y los tipos [delegados](../keywords/delegate.md).

Para obtener información sobre el operador aritmético `-`, consulte las secciones correspondientes a los [operadores unarios más y menos](arithmetic-operators.md#unary-plus-and-minus-operators) y al [operador de resta (-)](arithmetic-operators.md#subtraction-operator--) del artículo [Operadores aritméticos](arithmetic-operators.md).

## <a name="delegate-removal"></a>Eliminación de delegados

Para los operandos del mismo tipo [delegado](../keywords/delegate.md), el operador `-` devuelve una instancia de delegado que se calcula de la siguiente manera:

- Si ambos operandos no son nulos y la lista de invocación del segundo operando es una sublista apropiada contigua de la lista de invocación del primer operando, el resultado de la operación es una nueva lista de invocación que se obtiene mediante la eliminación de las entradas del segundo operando de la lista de invocación del primer operando. Si la lista del segundo operando coincide con varias sublistas contiguas en la lista del primer operando, se quita solo la sublista coincidente más a la derecha. Si la eliminación da como resultado una lista vacía, el resultado es `null`.
- Si la lista de invocación del segundo operando no es una sublista apropiada contigua de la lista de invocación del primer operando, el resultado de la operación es el primer operando.
- Si el primer operando es `null`, el resultado de la operación es `null`. Si el segundo operando es `null`, el resultado de la operación es el primer operando.

En el ejemplo siguiente se muestra cómo la operación `-` realiza la eliminación de delegados:

[!code-csharp-interactive[delegate removal](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#DelegateRemoval)]

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

Para más información, consulte las secciones correspondientes al [operador unario menos](~/_csharplang/spec/expressions.md#unary-minus-operator) y al [operador de resta](~/_csharplang/spec/expressions.md#subtraction-operator) de [Especificación del lenguaje C#](../language-specification/index.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Operadores de C#](index.md)
- [Delegados](../../programming-guide/delegates/index.md)
- [Eventos](../../programming-guide/events/index.md)
- [Checked y unchecked](../keywords/checked-and-unchecked.md)
- [Operadores aritméticos](arithmetic-operators.md)
- [Operadores + y += ](addition-operator.md)
