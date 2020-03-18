---
title: + Operadores + y += (referencia de C#)
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
ms.openlocfilehash: cafd07f4b4aefdcc4b43750d61c155fe3d65aa46
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398104"
---
# <a name="-and--operators-c-reference"></a><span data-ttu-id="ed155-102">Operadores + y += (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="ed155-102">+ and += operators (C# reference)</span></span>

<span data-ttu-id="ed155-103">Los operadores `+` y `+=` son compatibles con los tipos numéricos [enteros](../builtin-types/integral-numeric-types.md) y de [punto flotante](../builtin-types/floating-point-numeric-types.md), el tipo [string](../builtin-types/reference-types.md#the-string-type) y los tipos [delegados](../builtin-types/reference-types.md#the-delegate-type).</span><span class="sxs-lookup"><span data-stu-id="ed155-103">The `+` and `+=` operators are supported by the built-in [integral](../builtin-types/integral-numeric-types.md) and [floating-point](../builtin-types/floating-point-numeric-types.md) numeric types, the [string](../builtin-types/reference-types.md#the-string-type) type, and [delegate](../builtin-types/reference-types.md#the-delegate-type) types.</span></span>

<span data-ttu-id="ed155-104">Para obtener información acerca del operador aritmético `+`, consulte las secciones correspondientes a los [operadores unarios más y menos](arithmetic-operators.md#unary-plus-and-minus-operators) y al [operador de suma +](arithmetic-operators.md#addition-operator-) del artículo [Operadores aritméticos](arithmetic-operators.md).</span><span class="sxs-lookup"><span data-stu-id="ed155-104">For information about the arithmetic `+` operator, see the [Unary plus and minus operators](arithmetic-operators.md#unary-plus-and-minus-operators) and [Addition operator +](arithmetic-operators.md#addition-operator-) sections of the [Arithmetic operators](arithmetic-operators.md) article.</span></span>

## <a name="string-concatenation"></a><span data-ttu-id="ed155-105">Concatenación de cadenas</span><span class="sxs-lookup"><span data-stu-id="ed155-105">String concatenation</span></span>

<span data-ttu-id="ed155-106">Cuando uno o ambos operandos son de tipo [cadena](../builtin-types/reference-types.md#the-string-type), el operador `+` concatena las representaciones de cadena de sus operandos:</span><span class="sxs-lookup"><span data-stu-id="ed155-106">When one or both operands are of type [string](../builtin-types/reference-types.md#the-string-type), the `+` operator concatenates the string representations of its operands:</span></span>

[!code-csharp-interactive[string concatenation](snippets/AdditionOperator.cs#AddStrings)]

<span data-ttu-id="ed155-107">A partir de C# 6, la [interpolación de cadenas](../tokens/interpolated.md) proporciona una manera más conveniente de dar formato a las cadenas:</span><span class="sxs-lookup"><span data-stu-id="ed155-107">Beginning with C# 6, [string interpolation](../tokens/interpolated.md) provides a more convenient way to format strings:</span></span>

[!code-csharp-interactive[string interpolation](snippets/AdditionOperator.cs#UseStringInterpolation)]

## <a name="delegate-combination"></a><span data-ttu-id="ed155-108">Combinación de delegados</span><span class="sxs-lookup"><span data-stu-id="ed155-108">Delegate combination</span></span>

<span data-ttu-id="ed155-109">Para los operandos del mismo tipo de [delegado](../builtin-types/reference-types.md#the-delegate-type), el operador `+` devuelve una nueva instancia de delegado que, cuando se invoca, invoca el operando de la izquierda y luego invoca el operando de la derecha.</span><span class="sxs-lookup"><span data-stu-id="ed155-109">For operands of the same [delegate](../builtin-types/reference-types.md#the-delegate-type) type, the `+` operator returns a new delegate instance that, when invoked, invokes the left-hand operand and then invokes the right-hand operand.</span></span> <span data-ttu-id="ed155-110">Si alguno de los operandos es `null`, el operador `+` devuelve el valor del otro operando (que también podría ser `null`).</span><span class="sxs-lookup"><span data-stu-id="ed155-110">If any of the operands is `null`, the `+` operator returns the value of another operand (which also might be `null`).</span></span> <span data-ttu-id="ed155-111">El ejemplo siguiente muestra cómo los delegados se pueden combinar con el operador `+`:</span><span class="sxs-lookup"><span data-stu-id="ed155-111">The following example shows how delegates can be combined with the `+` operator:</span></span>

[!code-csharp-interactive[delegate combination](snippets/AdditionOperator.cs#AddDelegates)]

<span data-ttu-id="ed155-112">Para llevar a cabo la eliminación de delegados, utilice el [operador `-`](subtraction-operator.md#delegate-removal).</span><span class="sxs-lookup"><span data-stu-id="ed155-112">To perform delegate removal, use the [`-` operator](subtraction-operator.md#delegate-removal).</span></span>

<span data-ttu-id="ed155-113">Para más información sobre los tipos de delegado, vea [Delegados](../../programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="ed155-113">For more information about delegate types, see [Delegates](../../programming-guide/delegates/index.md).</span></span>

## <a name="addition-assignment-operator-"></a><span data-ttu-id="ed155-114">Operador de asignación y suma +=</span><span class="sxs-lookup"><span data-stu-id="ed155-114">Addition assignment operator +=</span></span>

<span data-ttu-id="ed155-115">Una expresión que usa el operador `+=`, como</span><span class="sxs-lookup"><span data-stu-id="ed155-115">An expression using the `+=` operator, such as</span></span>

```csharp
x += y
```

<span data-ttu-id="ed155-116">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="ed155-116">is equivalent to</span></span>

```csharp
x = x + y
```

<span data-ttu-id="ed155-117">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="ed155-117">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="ed155-118">En el siguiente ejemplo se muestra el uso del operador `+=`:</span><span class="sxs-lookup"><span data-stu-id="ed155-118">The following example demonstrates the usage of the `+=` operator:</span></span>

[!code-csharp-interactive[+= examples](snippets/AdditionOperator.cs#AddAndAssign)]

<span data-ttu-id="ed155-119">También usa el operador `+=` para especificar un método de controlador de eventos cuando se suscribe a un [evento](../keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="ed155-119">You also use the `+=` operator to specify an event handler method when you subscribe to an [event](../keywords/event.md).</span></span> <span data-ttu-id="ed155-120">Para obtener más información, vea [Procedimientos para suscribir y cancelar la suscripción a eventos](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="ed155-120">For more information, see [How to: subscribe to and unsubscribe from events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="ed155-121">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="ed155-121">Operator overloadability</span></span>

<span data-ttu-id="ed155-122">Un tipo definido por el usuario puede [sobrecargar](operator-overloading.md) el operador `+`.</span><span class="sxs-lookup"><span data-stu-id="ed155-122">A user-defined type can [overload](operator-overloading.md) the `+` operator.</span></span> <span data-ttu-id="ed155-123">Cuando se sobrecarga un operador `+` binario, el operador `+=` también se sobrecarga de modo implícito.</span><span class="sxs-lookup"><span data-stu-id="ed155-123">When a binary `+` operator is overloaded, the `+=` operator is also implicitly overloaded.</span></span> <span data-ttu-id="ed155-124">Un tipo definido por el usuario no puede sobrecargar de forma explícita el operador `+=`.</span><span class="sxs-lookup"><span data-stu-id="ed155-124">A user-defined type cannot explicitly overload the `+=` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="ed155-125">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="ed155-125">C# language specification</span></span>

<span data-ttu-id="ed155-126">Para más información, consulte las secciones [Operador unario más](~/_csharplang/spec/expressions.md#unary-plus-operator) y [Operador de suma](~/_csharplang/spec/expressions.md#addition-operator) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="ed155-126">For more information, see the [Unary plus operator](~/_csharplang/spec/expressions.md#unary-plus-operator) and [Addition operator](~/_csharplang/spec/expressions.md#addition-operator) sections of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ed155-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed155-127">See also</span></span>

- [<span data-ttu-id="ed155-128">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="ed155-128">C# reference</span></span>](../index.md)
- [<span data-ttu-id="ed155-129">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="ed155-129">C# operators</span></span>](index.md)
- [<span data-ttu-id="ed155-130">Concatenación de varias cadenas</span><span class="sxs-lookup"><span data-stu-id="ed155-130">How to concatenate multiple strings</span></span>](../../how-to/concatenate-multiple-strings.md)
- [<span data-ttu-id="ed155-131">Eventos</span><span class="sxs-lookup"><span data-stu-id="ed155-131">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="ed155-132">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="ed155-132">Arithmetic operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="ed155-133">Operadores - y -=</span><span class="sxs-lookup"><span data-stu-id="ed155-133">- and -= operators</span></span>](subtraction-operator.md)
