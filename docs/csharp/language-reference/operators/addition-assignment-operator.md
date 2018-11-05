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
# <a name="-operator-c-reference"></a><span data-ttu-id="fc416-102">Operador += (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="fc416-102">+= Operator (C# Reference)</span></span>

<span data-ttu-id="fc416-103">El operador de asignación y suma.</span><span class="sxs-lookup"><span data-stu-id="fc416-103">The addition assignment operator.</span></span>

<span data-ttu-id="fc416-104">Una expresión que usa el operador `+=`, como</span><span class="sxs-lookup"><span data-stu-id="fc416-104">An expression using the `+=` operator, such as</span></span>  

```csharp
x += y
```  

<span data-ttu-id="fc416-105">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="fc416-105">is equivalent to</span></span>  

```csharp
x = x + y
```  

<span data-ttu-id="fc416-106">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="fc416-106">except that `x` is only evaluated once.</span></span>
  
<span data-ttu-id="fc416-107">Para tipos numéricos, el [operador de suma](addition-operator.md) `+` calcula la suma de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="fc416-107">For numeric types, the [addition operator](addition-operator.md) `+` computes the sum of its operands.</span></span> <span data-ttu-id="fc416-108">Si uno o ambos operandos son de tipo [cadena](../keywords/string.md), concatena las representaciones de cadena de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="fc416-108">If one or both operands is of type [string](../keywords/string.md), it concatenates the string representations of its operands.</span></span> <span data-ttu-id="fc416-109">Para los tipos de delegado, el operador `+` devuelve una nueva instancia de delegado que es la combinación de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="fc416-109">For delegate types, the `+` operator returns a new delegate instance that is combination of its operands.</span></span>

<span data-ttu-id="fc416-110">Si un tipo definido por el usuario [sobrecarga](../keywords/operator.md) el [operador de suma](addition-operator.md) `+`, el operador de asignación de suma `+=` se sobrecarga implícitamente.</span><span class="sxs-lookup"><span data-stu-id="fc416-110">If a user-defined type [overloads](../keywords/operator.md) the [addition operator](addition-operator.md) `+`, the addition assignment operator `+=` is implicitly overloaded.</span></span>

<span data-ttu-id="fc416-111">También usa el operador `+=` para especificar un método de controlador de eventos cuando se suscribe a un [evento](../keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="fc416-111">You also use the `+=` operator to specify an event handler method when you subscribe to an [event](../keywords/event.md).</span></span> <span data-ttu-id="fc416-112">Para obtener más información, vea [How to: Subscribe to and Unsubscribe from Events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md) (Cómo: Suscribir y cancelar la suscripción a eventos [Guía de programación de C#]).</span><span class="sxs-lookup"><span data-stu-id="fc416-112">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

<span data-ttu-id="fc416-113">En el siguiente ejemplo se muestra el uso del operador `+=`:</span><span class="sxs-lookup"><span data-stu-id="fc416-113">The following example demonstrates the usage of the `+=` operator:</span></span>

[!code-csharp-interactive[+= examples](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddAndAssign)]
  
## <a name="see-also"></a><span data-ttu-id="fc416-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc416-114">See also</span></span>

- [<span data-ttu-id="fc416-115">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="fc416-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="fc416-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="fc416-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="fc416-117">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="fc416-117">C# Operators</span></span>](index.md)
- [<span data-ttu-id="fc416-118">Eventos</span><span class="sxs-lookup"><span data-stu-id="fc416-118">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="fc416-119">Delegados</span><span class="sxs-lookup"><span data-stu-id="fc416-119">Delegates</span></span>](../../programming-guide/delegates/index.md)
