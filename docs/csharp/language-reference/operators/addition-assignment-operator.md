---
title: Operador += (Referencia de C#)
ms.date: 10/29/2018
f1_keywords:
- +=_CSharpKeyword
helpviewer_keywords:
- += operator [C#]
- addition assignment operator (+=) [C#]
- event subscription [C#]
ms.assetid: 9cdf97e6-331d-492b-85e1-3ec3171484e9
ms.openlocfilehash: ac9330e283cb58ae4e0ee7b644aa2c22bdf64c46
ms.sourcegitcommit: 3b1cb8467bd73dee854b604e306c0e7e3882d91a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2018
ms.locfileid: "50192036"
---
# <a name="-operator-c-reference"></a>Operador += (Referencia de C#)

El operador de asignación y suma.

Una expresión que usa el operador `+=`, como

```csharp
x += y
```

es equivalente a

```csharp
x = x + y
```

salvo que `x` solo se evalúa una vez.
  
Para tipos numéricos, el [operador de suma](addition-operator.md) `+` calcula la suma de sus operandos. Si uno o ambos operandos son de tipo [cadena](../keywords/string.md), concatena las representaciones de cadena de sus operandos. Para los tipos de delegado, el operador `+` devuelve una nueva instancia de delegado que es la combinación de sus operandos.

También usa el operador `+=` para especificar un método de controlador de eventos cuando se suscribe a un [evento](../keywords/event.md). Para obtener más información, vea [How to: Subscribe to and Unsubscribe from Events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md) (Cómo: Suscribir y cancelar la suscripción a eventos [Guía de programación de C#]).

En el siguiente ejemplo se muestra el uso del operador `+=`:

[!code-csharp-interactive[+= examples](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddAndAssign)]

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

Si un tipo definido por el usuario [sobrecarga](../keywords/operator.md) el [operador de suma](addition-operator.md) `+`, el operador de asignación de suma `+=` se sobrecarga implícitamente. Un tipo definido por el usuario no puede sobrecargar de forma implícita el operador de asignación de suma.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, vea las secciones [Asignación compuesta](~/_csharplang/spec/expressions.md#compound-assignment) y [Asignación de eventos](~/_csharplang/spec/expressions.md#event-assignment) de la [Especificación del lenguaje C#](../language-specification/index.md).
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Operadores de C#](index.md)
- [Eventos](../../programming-guide/events/index.md)
- [Delegados](../../programming-guide/delegates/index.md)
