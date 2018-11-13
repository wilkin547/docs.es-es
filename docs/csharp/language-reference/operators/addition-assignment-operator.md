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
# <a name="-operator-c-reference"></a><span data-ttu-id="d6426-102">Operador += (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="d6426-102">+= Operator (C# Reference)</span></span>

<span data-ttu-id="d6426-103">El operador de asignación y suma.</span><span class="sxs-lookup"><span data-stu-id="d6426-103">The addition assignment operator.</span></span>

<span data-ttu-id="d6426-104">Una expresión que usa el operador `+=`, como</span><span class="sxs-lookup"><span data-stu-id="d6426-104">An expression using the `+=` operator, such as</span></span>

```csharp
x += y
```

<span data-ttu-id="d6426-105">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="d6426-105">is equivalent to</span></span>

```csharp
x = x + y
```

<span data-ttu-id="d6426-106">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="d6426-106">except that `x` is only evaluated once.</span></span>
  
<span data-ttu-id="d6426-107">Para tipos numéricos, el [operador de suma](addition-operator.md) `+` calcula la suma de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="d6426-107">For numeric types, the [addition operator](addition-operator.md) `+` computes the sum of its operands.</span></span> <span data-ttu-id="d6426-108">Si uno o ambos operandos son de tipo [cadena](../keywords/string.md), concatena las representaciones de cadena de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="d6426-108">If one or both operands is of type [string](../keywords/string.md), it concatenates the string representations of its operands.</span></span> <span data-ttu-id="d6426-109">Para los tipos de delegado, el operador `+` devuelve una nueva instancia de delegado que es la combinación de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="d6426-109">For delegate types, the `+` operator returns a new delegate instance that is combination of its operands.</span></span>

<span data-ttu-id="d6426-110">También usa el operador `+=` para especificar un método de controlador de eventos cuando se suscribe a un [evento](../keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="d6426-110">You also use the `+=` operator to specify an event handler method when you subscribe to an [event](../keywords/event.md).</span></span> <span data-ttu-id="d6426-111">Para obtener más información, vea [How to: Subscribe to and Unsubscribe from Events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md) (Cómo: Suscribir y cancelar la suscripción a eventos [Guía de programación de C#]).</span><span class="sxs-lookup"><span data-stu-id="d6426-111">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

<span data-ttu-id="d6426-112">En el siguiente ejemplo se muestra el uso del operador `+=`:</span><span class="sxs-lookup"><span data-stu-id="d6426-112">The following example demonstrates the usage of the `+=` operator:</span></span>

[!code-csharp-interactive[+= examples](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddAndAssign)]

## <a name="operator-overloadability"></a><span data-ttu-id="d6426-113">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="d6426-113">Operator overloadability</span></span>

<span data-ttu-id="d6426-114">Si un tipo definido por el usuario [sobrecarga](../keywords/operator.md) el [operador de suma](addition-operator.md) `+`, el operador de asignación de suma `+=` se sobrecarga implícitamente.</span><span class="sxs-lookup"><span data-stu-id="d6426-114">If a user-defined type [overloads](../keywords/operator.md) the [addition operator](addition-operator.md) `+`, the addition assignment operator `+=` is implicitly overloaded.</span></span> <span data-ttu-id="d6426-115">Un tipo definido por el usuario no puede sobrecargar de forma implícita el operador de asignación de suma.</span><span class="sxs-lookup"><span data-stu-id="d6426-115">A user-defined type cannot explicitly overload the addition assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="d6426-116">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="d6426-116">C# language specification</span></span>

<span data-ttu-id="d6426-117">Para obtener más información, vea las secciones [Asignación compuesta](~/_csharplang/spec/expressions.md#compound-assignment) y [Asignación de eventos](~/_csharplang/spec/expressions.md#event-assignment) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="d6426-117">For more information, see the [Compound assignment](~/_csharplang/spec/expressions.md#compound-assignment) and [Event assignment](~/_csharplang/spec/expressions.md#event-assignment) sections of the [C# language specification](../language-specification/index.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d6426-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6426-118">See also</span></span>

- [<span data-ttu-id="d6426-119">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="d6426-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d6426-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="d6426-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d6426-121">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="d6426-121">C# Operators</span></span>](index.md)
- [<span data-ttu-id="d6426-122">Eventos</span><span class="sxs-lookup"><span data-stu-id="d6426-122">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="d6426-123">Delegados</span><span class="sxs-lookup"><span data-stu-id="d6426-123">Delegates</span></span>](../../programming-guide/delegates/index.md)
