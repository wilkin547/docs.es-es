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
# <a name="--and---operators-c-reference"></a><span data-ttu-id="6bfb1-102">Operadores - y -= (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="6bfb1-102">- and -= operators (C# Reference)</span></span>

<span data-ttu-id="6bfb1-103">El operador `-` es compatible con los tipos numéricos integrados y los tipos [delegados](../keywords/delegate.md).</span><span class="sxs-lookup"><span data-stu-id="6bfb1-103">The `-` operator is supported by the built-in numeric types and [delegate](../keywords/delegate.md) types.</span></span>

<span data-ttu-id="6bfb1-104">Para obtener información sobre el operador aritmético `-`, consulte las secciones correspondientes a los [operadores unarios más y menos](arithmetic-operators.md#unary-plus-and-minus-operators) y al [operador de resta (-)](arithmetic-operators.md#subtraction-operator--) del artículo [Operadores aritméticos](arithmetic-operators.md).</span><span class="sxs-lookup"><span data-stu-id="6bfb1-104">For information about the arithmetic `-` operator, see the [Unary plus and minus operators](arithmetic-operators.md#unary-plus-and-minus-operators) and [Subtraction operator -](arithmetic-operators.md#subtraction-operator--) sections of the [Arithmetic operators](arithmetic-operators.md) article.</span></span>

## <a name="delegate-removal"></a><span data-ttu-id="6bfb1-105">Eliminación de delegados</span><span class="sxs-lookup"><span data-stu-id="6bfb1-105">Delegate removal</span></span>

<span data-ttu-id="6bfb1-106">Para los operandos del mismo tipo [delegado](../keywords/delegate.md), el operador `-` devuelve una instancia de delegado que se calcula de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="6bfb1-106">For operands of the same [delegate](../keywords/delegate.md) type, the `-` operator returns a delegate instance that is calculated as follows:</span></span>

- <span data-ttu-id="6bfb1-107">Si ambos operandos no son nulos y la lista de invocación del segundo operando es una sublista apropiada contigua de la lista de invocación del primer operando, el resultado de la operación es una nueva lista de invocación que se obtiene mediante la eliminación de las entradas del segundo operando de la lista de invocación del primer operando.</span><span class="sxs-lookup"><span data-stu-id="6bfb1-107">If both operands are non-null and the invocation list of the second operand is a proper contiguous sublist of the invocation list of the first operand, the result of the operation is a new invocation list that is obtained by removing the second operand's entries from the invocation list of the first operand.</span></span> <span data-ttu-id="6bfb1-108">Si la lista del segundo operando coincide con varias sublistas contiguas en la lista del primer operando, se quita solo la sublista coincidente más a la derecha.</span><span class="sxs-lookup"><span data-stu-id="6bfb1-108">If the second operand's list matches multiple contiguous sublists in the first operand's list, only the right-most matching sublist is removed.</span></span> <span data-ttu-id="6bfb1-109">Si la eliminación da como resultado una lista vacía, el resultado es `null`.</span><span class="sxs-lookup"><span data-stu-id="6bfb1-109">If removal results in an empty list, the result is `null`.</span></span>
- <span data-ttu-id="6bfb1-110">Si la lista de invocación del segundo operando no es una sublista apropiada contigua de la lista de invocación del primer operando, el resultado de la operación es el primer operando.</span><span class="sxs-lookup"><span data-stu-id="6bfb1-110">If the invocation list of the second operand is not a proper contiguous sublist of the invocation list of the first operand, the result of the operation is the first operand.</span></span>
- <span data-ttu-id="6bfb1-111">Si el primer operando es `null`, el resultado de la operación es `null`.</span><span class="sxs-lookup"><span data-stu-id="6bfb1-111">If the first operand is `null`, the result of the operation is `null`.</span></span> <span data-ttu-id="6bfb1-112">Si el segundo operando es `null`, el resultado de la operación es el primer operando.</span><span class="sxs-lookup"><span data-stu-id="6bfb1-112">If the second operand is `null`, the result of the operation is the first operand.</span></span>

<span data-ttu-id="6bfb1-113">En el ejemplo siguiente se muestra cómo la operación `-` realiza la eliminación de delegados:</span><span class="sxs-lookup"><span data-stu-id="6bfb1-113">The following example shows how the `-` operation performs delegate removal:</span></span>

[!code-csharp-interactive[delegate removal](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#DelegateRemoval)]

## <a name="subtraction-assignment-operator--"></a><span data-ttu-id="6bfb1-114">Operador de resta y asignación (-=)</span><span class="sxs-lookup"><span data-stu-id="6bfb1-114">Subtraction assignment operator -=</span></span>

<span data-ttu-id="6bfb1-115">Una expresión que usa el operador `-=`, como</span><span class="sxs-lookup"><span data-stu-id="6bfb1-115">An expression using the `-=` operator, such as</span></span>

```csharp
x -= y
```

<span data-ttu-id="6bfb1-116">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="6bfb1-116">is equivalent to</span></span>

```csharp
x = x - y
```

<span data-ttu-id="6bfb1-117">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="6bfb1-117">except that `x` is only evaluated once.</span></span>
  
<span data-ttu-id="6bfb1-118">En el siguiente ejemplo se muestra el uso del operador `-=`:</span><span class="sxs-lookup"><span data-stu-id="6bfb1-118">The following example demonstrates the usage of the `-=` operator:</span></span>

[!code-csharp-interactive[-= examples](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#SubtractAndAssign)]

<span data-ttu-id="6bfb1-119">También se usa el operador `-=` con el fin de especificar un método de controlador de eventos para eliminar cuando se finaliza la suscripción a un [evento](../keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="6bfb1-119">You also use the `-=` operator to specify an event handler method to remove when you unsubscribe from an [event](../keywords/event.md).</span></span> <span data-ttu-id="6bfb1-120">Para obtener más información, vea [Procedimientos para suscribir y cancelar la suscripción a eventos](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="6bfb1-120">For more information, see [How to: subscribe to and unsubscribe from events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="6bfb1-121">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="6bfb1-121">Operator overloadability</span></span>

<span data-ttu-id="6bfb1-122">Un tipo definido por el usuario puede [sobrecargar](../keywords/operator.md) el operador `-`.</span><span class="sxs-lookup"><span data-stu-id="6bfb1-122">A user-defined type can [overload](../keywords/operator.md) the `-` operator.</span></span> <span data-ttu-id="6bfb1-123">Cuando se sobrecarga un operador `-` binario, el operador `-=` también se sobrecarga de modo implícito.</span><span class="sxs-lookup"><span data-stu-id="6bfb1-123">When a binary `-` operator is overloaded, the `-=` operator is also implicitly overloaded.</span></span> <span data-ttu-id="6bfb1-124">Un tipo definido por el usuario no puede sobrecargar de forma explícita el operador `-=`.</span><span class="sxs-lookup"><span data-stu-id="6bfb1-124">A user-defined type cannot explicitly overload the `-=` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="6bfb1-125">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="6bfb1-125">C# language specification</span></span>

<span data-ttu-id="6bfb1-126">Para más información, consulte las secciones correspondientes al [operador unario menos](~/_csharplang/spec/expressions.md#unary-minus-operator) y al [operador de resta](~/_csharplang/spec/expressions.md#subtraction-operator) de [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="6bfb1-126">For more information, see the [Unary minus operator](~/_csharplang/spec/expressions.md#unary-minus-operator) and [Subtraction operator](~/_csharplang/spec/expressions.md#subtraction-operator) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6bfb1-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="6bfb1-127">See also</span></span>

- [<span data-ttu-id="6bfb1-128">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="6bfb1-128">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="6bfb1-129">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="6bfb1-129">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="6bfb1-130">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="6bfb1-130">C# Operators</span></span>](index.md)
- [<span data-ttu-id="6bfb1-131">Delegados</span><span class="sxs-lookup"><span data-stu-id="6bfb1-131">Delegates</span></span>](../../programming-guide/delegates/index.md)
- [<span data-ttu-id="6bfb1-132">Eventos</span><span class="sxs-lookup"><span data-stu-id="6bfb1-132">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="6bfb1-133">Checked y unchecked</span><span class="sxs-lookup"><span data-stu-id="6bfb1-133">Checked and unchecked</span></span>](../keywords/checked-and-unchecked.md)
- [<span data-ttu-id="6bfb1-134">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="6bfb1-134">Arithmetic operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="6bfb1-135">Operadores + y += </span><span class="sxs-lookup"><span data-stu-id="6bfb1-135">+ and += operators</span></span>](addition-operator.md)
