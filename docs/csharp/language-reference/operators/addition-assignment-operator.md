---
title: Operador += (Referencia de C#)
ms.date: 10/22/2018
f1_keywords:
- +=_CSharpKeyword
helpviewer_keywords:
- += operator [C#]
- addition assignment operator (+=) [C#]
- event subscription [C#]
ms.assetid: 9cdf97e6-331d-492b-85e1-3ec3171484e9
ms.openlocfilehash: ee335e3e2e7d352d4e26b802bad2b08a05c666ab
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
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

Si un tipo definido por el usuario [sobrecarga](../keywords/operator.md) el [operador de suma](addition-operator.md) `+`, el operador de asignación de suma `+=` se sobrecarga implícitamente.

También usa el operador `+=` para especificar un método de controlador de eventos cuando se suscribe a un [evento](../keywords/event.md). Para obtener más información, vea [How to: Subscribe to and Unsubscribe from Events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md) (Cómo: Suscribir y cancelar la suscripción a eventos [Guía de programación de C#]).

En el siguiente ejemplo se muestra el uso del operador `+=`:

[!code-csharp-interactive[+= examples](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddAndAssign)]
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Operadores de C#](index.md)
- [Eventos](../../programming-guide/events/index.md)
- [Delegados](../../programming-guide/delegates/index.md)
