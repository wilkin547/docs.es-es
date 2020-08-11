---
title: '- Operadores - y -= (referencia de C#)'
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
ms.openlocfilehash: a00957c8d36a96b5ee23b9e5a309b6139b33fd36
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916692"
---
# <a name="--and---operators-c-reference"></a><span data-ttu-id="f5135-102">Operadores - y -= (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="f5135-102">- and -= operators (C# reference)</span></span>

<span data-ttu-id="f5135-103">Los operadores `-` y `-=` son compatibles con los tipos numéricos [enteros](../builtin-types/integral-numeric-types.md) y de [punto flotante](../builtin-types/floating-point-numeric-types.md), y los tipos [delegados](../builtin-types/reference-types.md#the-delegate-type).</span><span class="sxs-lookup"><span data-stu-id="f5135-103">The `-` and `-=` operators are supported by the built-in [integral](../builtin-types/integral-numeric-types.md) and [floating-point](../builtin-types/floating-point-numeric-types.md) numeric types and [delegate](../builtin-types/reference-types.md#the-delegate-type) types.</span></span>

<span data-ttu-id="f5135-104">Para obtener información sobre el operador aritmético `-`, consulte las secciones correspondientes a los [operadores unarios más y menos](arithmetic-operators.md#unary-plus-and-minus-operators) y al [operador de resta (-)](arithmetic-operators.md#subtraction-operator--) del artículo [Operadores aritméticos](arithmetic-operators.md).</span><span class="sxs-lookup"><span data-stu-id="f5135-104">For information about the arithmetic `-` operator, see the [Unary plus and minus operators](arithmetic-operators.md#unary-plus-and-minus-operators) and [Subtraction operator -](arithmetic-operators.md#subtraction-operator--) sections of the [Arithmetic operators](arithmetic-operators.md) article.</span></span>

## <a name="delegate-removal"></a><span data-ttu-id="f5135-105">Eliminación de delegados</span><span class="sxs-lookup"><span data-stu-id="f5135-105">Delegate removal</span></span>

<span data-ttu-id="f5135-106">Para los operandos del mismo tipo [delegado](../builtin-types/reference-types.md#the-delegate-type), el operador `-` devuelve una instancia de delegado que se calcula de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="f5135-106">For operands of the same [delegate](../builtin-types/reference-types.md#the-delegate-type) type, the `-` operator returns a delegate instance that is calculated as follows:</span></span>

- <span data-ttu-id="f5135-107">Si ambos operandos no son nulos y la lista de invocación del operando derecho es una sublista apropiada contigua de la lista de invocación del operando izquierdo, el resultado de la operación es una nueva lista de invocación que se obtiene mediante la eliminación de las entradas del operando derecho de la lista de invocación del operando izquierdo.</span><span class="sxs-lookup"><span data-stu-id="f5135-107">If both operands are non-null and the invocation list of the right-hand operand is a proper contiguous sublist of the invocation list of the left-hand operand, the result of the operation is a new invocation list that is obtained by removing the right-hand operand's entries from the invocation list of the left-hand operand.</span></span> <span data-ttu-id="f5135-108">Si la lista del operando derecho coincide con varias sublistas contiguas en la lista del operando izquierdo, se quita solo la sublista coincidente más a la derecha.</span><span class="sxs-lookup"><span data-stu-id="f5135-108">If the right-hand operand's list matches multiple contiguous sublists in the left-hand operand's list, only the right-most matching sublist is removed.</span></span> <span data-ttu-id="f5135-109">Si la eliminación da como resultado una lista vacía, el resultado es `null`.</span><span class="sxs-lookup"><span data-stu-id="f5135-109">If removal results in an empty list, the result is `null`.</span></span>

  [!code-csharp-interactive[delegate removal](snippets/shared/SubtractionOperator.cs#DelegateRemoval)]

- <span data-ttu-id="f5135-110">Si la lista de invocación del operando derecho no es una sublista apropiada contigua de la lista de invocación del operando izquierdo, el resultado de la operación es el operando izquierdo.</span><span class="sxs-lookup"><span data-stu-id="f5135-110">If the invocation list of the right-hand operand is not a proper contiguous sublist of the invocation list of the left-hand operand, the result of the operation is the left-hand operand.</span></span> <span data-ttu-id="f5135-111">Por ejemplo, la eliminación de un delegado que no forma parte del delegado de multidifusión no surte ningún efecto y da como resultado que el delegado de multidifusión no cambie.</span><span class="sxs-lookup"><span data-stu-id="f5135-111">For example, removing a delegate that is not part of the multicast delegate does nothing and results in the unchanged multicast delegate.</span></span>

  [!code-csharp-interactive[delegate removal with no effect](snippets/shared/SubtractionOperator.cs#DelegateRemovalNoChange)]

  <span data-ttu-id="f5135-112">El ejemplo anterior también demuestra que, durante la eliminación de delegados, se comparan las instancias de delegados.</span><span class="sxs-lookup"><span data-stu-id="f5135-112">The preceding example also demonstrates that during delegate removal delegate instances are compared.</span></span> <span data-ttu-id="f5135-113">Por ejemplo, los delegados que se producen de la evaluación de [expresiones lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md) idénticas no son iguales.</span><span class="sxs-lookup"><span data-stu-id="f5135-113">For example, delegates that are produced from evaluation of identical [lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md) are not equal.</span></span> <span data-ttu-id="f5135-114">Para obtener más información acerca de la igualdad de delegados, consulte la sección [Operadores de igualdad de delegado](~/_csharplang/spec/expressions.md#delegate-equality-operators) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="f5135-114">For more information about delegate equality, see the [Delegate equality operators](~/_csharplang/spec/expressions.md#delegate-equality-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

- <span data-ttu-id="f5135-115">Si el operando izquierdo es `null`, el resultado de la operación es `null`.</span><span class="sxs-lookup"><span data-stu-id="f5135-115">If the left-hand operand is `null`, the result of the operation is `null`.</span></span> <span data-ttu-id="f5135-116">Si el operando derecho es `null`, el resultado de la operación es el operando izquierdo.</span><span class="sxs-lookup"><span data-stu-id="f5135-116">If the right-hand operand is `null`, the result of the operation is the left-hand operand.</span></span>

  [!code-csharp-interactive[delegate removal and null](snippets/shared/SubtractionOperator.cs#DelegateRemovalAndNull)]

<span data-ttu-id="f5135-117">Para combinar delegados, utilice el [operador `+`](addition-operator.md#delegate-combination).</span><span class="sxs-lookup"><span data-stu-id="f5135-117">To combine delegates, use the [`+` operator](addition-operator.md#delegate-combination).</span></span>

<span data-ttu-id="f5135-118">Para más información sobre los tipos de delegado, vea [Delegados](../../programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="f5135-118">For more information about delegate types, see [Delegates](../../programming-guide/delegates/index.md).</span></span>

## <a name="subtraction-assignment-operator--"></a><span data-ttu-id="f5135-119">Operador de resta y asignación (-=)</span><span class="sxs-lookup"><span data-stu-id="f5135-119">Subtraction assignment operator -=</span></span>

<span data-ttu-id="f5135-120">Una expresión que usa el operador `-=`, como</span><span class="sxs-lookup"><span data-stu-id="f5135-120">An expression using the `-=` operator, such as</span></span>

```csharp
x -= y
```

<span data-ttu-id="f5135-121">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="f5135-121">is equivalent to</span></span>

```csharp
x = x - y
```

<span data-ttu-id="f5135-122">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="f5135-122">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="f5135-123">En el siguiente ejemplo se muestra el uso del operador `-=`:</span><span class="sxs-lookup"><span data-stu-id="f5135-123">The following example demonstrates the usage of the `-=` operator:</span></span>

[!code-csharp-interactive[-= examples](snippets/shared/SubtractionOperator.cs#SubtractAndAssign)]

<span data-ttu-id="f5135-124">También se usa el operador `-=` con el fin de especificar un método de controlador de eventos para eliminar cuando se finaliza la suscripción a un [evento](../keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="f5135-124">You also use the `-=` operator to specify an event handler method to remove when you unsubscribe from an [event](../keywords/event.md).</span></span> <span data-ttu-id="f5135-125">Para obtener más información, vea [Procedimiento para suscribir y cancelar la suscripción a eventos](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="f5135-125">For more information, see [How to subscribe to and unsubscribe from events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="f5135-126">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="f5135-126">Operator overloadability</span></span>

<span data-ttu-id="f5135-127">Un tipo definido por el usuario puede [sobrecargar](operator-overloading.md) el operador `-`.</span><span class="sxs-lookup"><span data-stu-id="f5135-127">A user-defined type can [overload](operator-overloading.md) the `-` operator.</span></span> <span data-ttu-id="f5135-128">Cuando se sobrecarga un operador `-` binario, el operador `-=` también se sobrecarga de modo implícito.</span><span class="sxs-lookup"><span data-stu-id="f5135-128">When a binary `-` operator is overloaded, the `-=` operator is also implicitly overloaded.</span></span> <span data-ttu-id="f5135-129">Un tipo definido por el usuario no puede sobrecargar de forma explícita el operador `-=`.</span><span class="sxs-lookup"><span data-stu-id="f5135-129">A user-defined type cannot explicitly overload the `-=` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f5135-130">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="f5135-130">C# language specification</span></span>

<span data-ttu-id="f5135-131">Para más información, consulte las secciones correspondientes al [operador unario menos](~/_csharplang/spec/expressions.md#unary-minus-operator) y al [operador de resta](~/_csharplang/spec/expressions.md#subtraction-operator) de [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="f5135-131">For more information, see the [Unary minus operator](~/_csharplang/spec/expressions.md#unary-minus-operator) and [Subtraction operator](~/_csharplang/spec/expressions.md#subtraction-operator) sections of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f5135-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5135-132">See also</span></span>

- [<span data-ttu-id="f5135-133">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="f5135-133">C# reference</span></span>](../index.md)
- [<span data-ttu-id="f5135-134">Operadores y expresiones de C#</span><span class="sxs-lookup"><span data-stu-id="f5135-134">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="f5135-135">Eventos</span><span class="sxs-lookup"><span data-stu-id="f5135-135">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="f5135-136">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="f5135-136">Arithmetic operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="f5135-137">Operadores + y += </span><span class="sxs-lookup"><span data-stu-id="f5135-137">+ and += operators</span></span>](addition-operator.md)
