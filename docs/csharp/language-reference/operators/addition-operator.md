---
title: + Operadores + y += (referencia de C#)
ms.custom: seodec18
ms.date: 05/24/2019
f1_keywords:
- +_CSharpKeyword
- +=_CSharpKeyword
helpviewer_keywords:
- addition operator [C#]
- concatenation operator [C#]
- delegate combination [C#]
- + operator [C#]
- addition assignment operator [C#]
- event subscription [C#]
- += operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
ms.openlocfilehash: 14e62d53fca16212fae374b2627d1e96cbbca6ac
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025320"
---
# <a name="-and--operators-c-reference"></a><span data-ttu-id="b2955-102">Operadores + y += (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="b2955-102">+ and += operators (C# reference)</span></span>

<span data-ttu-id="b2955-103">El operador `+` es compatible con los tipos numéricos integrados, el tipo de [cadena](../keywords/string.md) y los tipos [delegados](../keywords/delegate.md).</span><span class="sxs-lookup"><span data-stu-id="b2955-103">The `+` operator is supported by the built-in numeric types, [string](../keywords/string.md) type, and [delegate](../keywords/delegate.md) types.</span></span>

<span data-ttu-id="b2955-104">Para obtener información acerca del operador aritmético `+`, consulte las secciones correspondientes a los [operadores unarios más y menos](arithmetic-operators.md#unary-plus-and-minus-operators) y al [operador de suma +](arithmetic-operators.md#addition-operator-) del artículo [Operadores aritméticos](arithmetic-operators.md).</span><span class="sxs-lookup"><span data-stu-id="b2955-104">For information about the arithmetic `+` operator, see the [Unary plus and minus operators](arithmetic-operators.md#unary-plus-and-minus-operators) and [Addition operator +](arithmetic-operators.md#addition-operator-) sections of the [Arithmetic operators](arithmetic-operators.md) article.</span></span>

## <a name="string-concatenation"></a><span data-ttu-id="b2955-105">Concatenación de cadenas</span><span class="sxs-lookup"><span data-stu-id="b2955-105">String concatenation</span></span>

<span data-ttu-id="b2955-106">Cuando uno o ambos operandos son de tipo [cadena](../keywords/string.md), el operador `+` concatena las representaciones de cadena de sus operandos:</span><span class="sxs-lookup"><span data-stu-id="b2955-106">When one or both operands are of type [string](../keywords/string.md), the `+` operator concatenates the string representations of its operands:</span></span>

[!code-csharp-interactive[string concatenation](~/samples/csharp/language-reference/operators/AdditionOperator.cs#AddStrings)]

<span data-ttu-id="b2955-107">A partir de C# 6, la [interpolación de cadenas](../tokens/interpolated.md) proporciona una manera más conveniente de dar formato a las cadenas:</span><span class="sxs-lookup"><span data-stu-id="b2955-107">Starting with C# 6, [string interpolation](../tokens/interpolated.md) provides a more convenient way to format strings:</span></span>

[!code-csharp-interactive[string interpolation](~/samples/csharp/language-reference/operators/AdditionOperator.cs#UseStringInterpolation)]

## <a name="delegate-combination"></a><span data-ttu-id="b2955-108">Combinación de delegados</span><span class="sxs-lookup"><span data-stu-id="b2955-108">Delegate combination</span></span>

<span data-ttu-id="b2955-109">Para los operandos del mismo tipo de [delegado](../keywords/delegate.md), el operador `+` devuelve una nueva instancia de delegado que, cuando se invoca, invoca el primer operando y luego invoca el segundo operando.</span><span class="sxs-lookup"><span data-stu-id="b2955-109">For operands of the same [delegate](../keywords/delegate.md) type, the `+` operator returns a new delegate instance that, when invoked, invokes the first operand and then invokes the second operand.</span></span> <span data-ttu-id="b2955-110">Si alguno de los operandos es `null`, el operador `+` devuelve el valor del otro operando (que también podría ser `null`).</span><span class="sxs-lookup"><span data-stu-id="b2955-110">If any of the operands is `null`, the `+` operator returns the value of another operand (which also might be `null`).</span></span> <span data-ttu-id="b2955-111">El ejemplo siguiente muestra cómo los delegados se pueden combinar con el operador `+`:</span><span class="sxs-lookup"><span data-stu-id="b2955-111">The following example shows how delegates can be combined with the `+` operator:</span></span>

[!code-csharp-interactive[delegate combination](~/samples/csharp/language-reference/operators/AdditionOperator.cs#AddDelegates)]

<span data-ttu-id="b2955-112">Para llevar a cabo la eliminación de delegados, utilice el [operador `-`](subtraction-operator.md#delegate-removal).</span><span class="sxs-lookup"><span data-stu-id="b2955-112">To perform delegate removal, use the [`-` operator](subtraction-operator.md#delegate-removal).</span></span>

<span data-ttu-id="b2955-113">Para más información sobre los tipos de delegado, vea [Delegados](../../programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="b2955-113">For more information about delegate types, see [Delegates](../../programming-guide/delegates/index.md).</span></span>

## <a name="addition-assignment-operator-"></a><span data-ttu-id="b2955-114">Operador de asignación y suma +=</span><span class="sxs-lookup"><span data-stu-id="b2955-114">Addition assignment operator +=</span></span>

<span data-ttu-id="b2955-115">Una expresión que usa el operador `+=`, como</span><span class="sxs-lookup"><span data-stu-id="b2955-115">An expression using the `+=` operator, such as</span></span>

```csharp
x += y
```

<span data-ttu-id="b2955-116">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="b2955-116">is equivalent to</span></span>

```csharp
x = x + y
```

<span data-ttu-id="b2955-117">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="b2955-117">except that `x` is only evaluated once.</span></span>
  
<span data-ttu-id="b2955-118">En el siguiente ejemplo se muestra el uso del operador `+=`:</span><span class="sxs-lookup"><span data-stu-id="b2955-118">The following example demonstrates the usage of the `+=` operator:</span></span>

[!code-csharp-interactive[+= examples](~/samples/csharp/language-reference/operators/AdditionOperator.cs#AddAndAssign)]

<span data-ttu-id="b2955-119">También usa el operador `+=` para especificar un método de controlador de eventos cuando se suscribe a un [evento](../keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="b2955-119">You also use the `+=` operator to specify an event handler method when you subscribe to an [event](../keywords/event.md).</span></span> <span data-ttu-id="b2955-120">Para obtener más información, vea [Procedimientos para suscribir y cancelar la suscripción a eventos](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="b2955-120">For more information, see [How to: subscribe to and unsubscribe from events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="b2955-121">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="b2955-121">Operator overloadability</span></span>

<span data-ttu-id="b2955-122">Un tipo definido por el usuario puede [sobrecargar](../keywords/operator.md) el operador `+`.</span><span class="sxs-lookup"><span data-stu-id="b2955-122">A user-defined type can [overload](../keywords/operator.md) the `+` operator.</span></span> <span data-ttu-id="b2955-123">Cuando se sobrecarga un operador `+` binario, el operador `+=` también se sobrecarga de modo implícito.</span><span class="sxs-lookup"><span data-stu-id="b2955-123">When a binary `+` operator is overloaded, the `+=` operator is also implicitly overloaded.</span></span> <span data-ttu-id="b2955-124">Un tipo definido por el usuario no puede sobrecargar de forma explícita el operador `+=`.</span><span class="sxs-lookup"><span data-stu-id="b2955-124">A user-defined type cannot explicitly overload the `+=` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="b2955-125">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="b2955-125">C# language specification</span></span>

<span data-ttu-id="b2955-126">Para más información, consulte las secciones [Operador unario más](~/_csharplang/spec/expressions.md#unary-plus-operator) y [Operador de suma](~/_csharplang/spec/expressions.md#addition-operator) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="b2955-126">For more information, see the [Unary plus operator](~/_csharplang/spec/expressions.md#unary-plus-operator) and [Addition operator](~/_csharplang/spec/expressions.md#addition-operator) sections of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b2955-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2955-127">See also</span></span>

- [<span data-ttu-id="b2955-128">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="b2955-128">C# reference</span></span>](../index.md)
- [<span data-ttu-id="b2955-129">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="b2955-129">C# operators</span></span>](index.md)
- [<span data-ttu-id="b2955-130">Interpolación de cadenas</span><span class="sxs-lookup"><span data-stu-id="b2955-130">String interpolation</span></span>](../tokens/interpolated.md)
- [<span data-ttu-id="b2955-131">Procedimiento para concatenar varias cadenas</span><span class="sxs-lookup"><span data-stu-id="b2955-131">How to: concatenate multiple strings</span></span>](../../how-to/concatenate-multiple-strings.md)
- [<span data-ttu-id="b2955-132">Delegados</span><span class="sxs-lookup"><span data-stu-id="b2955-132">Delegates</span></span>](../../programming-guide/delegates/index.md)
- [<span data-ttu-id="b2955-133">Eventos</span><span class="sxs-lookup"><span data-stu-id="b2955-133">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="b2955-134">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="b2955-134">Arithmetic operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="b2955-135">Operadores - y -=</span><span class="sxs-lookup"><span data-stu-id="b2955-135">- and -= operators</span></span>](subtraction-operator.md)
