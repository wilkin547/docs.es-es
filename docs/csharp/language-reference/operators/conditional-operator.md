---
description: 'Operador ?: (referencia de C#)'
title: 'Operador ?: (referencia de C#)'
ms.date: 03/06/2020
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: 0efa6de2b537fd3af76807938ac2b50a2716561f
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89122360"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="c895b-103">Operador ?: (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="c895b-103">?: operator (C# reference)</span></span>

<span data-ttu-id="c895b-104">El operador condicional `?:`, también conocido como operador condicional ternario, evalúa una expresión booleana y devuelve el resultado de una de las dos expresiones, en función de que la expresión booleana se evalúe como `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="c895b-104">The conditional operator `?:`, also known as the ternary conditional operator, evaluates a Boolean expression and returns the result of one of the two expressions, depending on whether the Boolean expression evaluates to `true` or `false`.</span></span>

<span data-ttu-id="c895b-105">La sintaxis del operador condicional es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="c895b-105">The syntax for the conditional operator is as follows:</span></span>

```csharp
condition ? consequent : alternative
```

<span data-ttu-id="c895b-106">La expresión `condition` debe evaluarse como `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="c895b-106">The `condition` expression must evaluate to `true` or `false`.</span></span> <span data-ttu-id="c895b-107">Si `condition` se evalúa como `true`, se evalúa la expresión `consequent` y su resultado se convierte en el resultado de la operación.</span><span class="sxs-lookup"><span data-stu-id="c895b-107">If `condition` evaluates to `true`, the `consequent` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="c895b-108">Si `condition` se evalúa como `false`, se evalúa la expresión `alternative` y su resultado se convierte en el resultado de la operación.</span><span class="sxs-lookup"><span data-stu-id="c895b-108">If `condition` evaluates to `false`, the `alternative` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="c895b-109">Solo se evalúan `consequent` o `alternative`.</span><span class="sxs-lookup"><span data-stu-id="c895b-109">Only `consequent` or `alternative` is evaluated.</span></span>

<span data-ttu-id="c895b-110">Los tipos de `consequent` y `alternative` deben coincidir o debe haber una conversión implícita de un tipo al otro.</span><span class="sxs-lookup"><span data-stu-id="c895b-110">The type of `consequent` and `alternative` must be the same, or there must be an implicit conversion from one type to the other.</span></span>

<span data-ttu-id="c895b-111">El operador condicional es asociativo a la derecha, es decir, una expresión de la forma</span><span class="sxs-lookup"><span data-stu-id="c895b-111">The conditional operator is right-associative, that is, an expression of the form</span></span>

```csharp
a ? b : c ? d : e
```

<span data-ttu-id="c895b-112">se evalúa como</span><span class="sxs-lookup"><span data-stu-id="c895b-112">is evaluated as</span></span>

```csharp
a ? b : (c ? d : e)
```

> [!TIP]
> <span data-ttu-id="c895b-113">Puede utilizar el siguiente recurso mnemotécnico para recordar cómo se evalúa el operador condicional:</span><span class="sxs-lookup"><span data-stu-id="c895b-113">You can use the following mnemonic device to remember how the conditional operator is evaluated:</span></span>
>
> ```text
> is this condition true ? yes : no
> ```

<span data-ttu-id="c895b-114">En el siguiente ejemplo se muestra el uso del operador condicional:</span><span class="sxs-lookup"><span data-stu-id="c895b-114">The following example demonstrates the usage of the conditional operator:</span></span>

[!code-csharp-interactive[non ref conditional](snippets/shared/ConditionalOperator.cs#ConditionalValue)]

## <a name="conditional-ref-expression"></a><span data-ttu-id="c895b-115">Expresión condicional ref</span><span class="sxs-lookup"><span data-stu-id="c895b-115">Conditional ref expression</span></span>

<span data-ttu-id="c895b-116">A partir de C# 7.2, las variables locales de tipo [ref](../keywords/ref.md#ref-locals) o de tipo [ref readonly](../keywords/ref.md#ref-readonly-locals) se pueden asignar condicionalmente con la expresión condicional ref.</span><span class="sxs-lookup"><span data-stu-id="c895b-116">Beginning with C# 7.2, a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable can be assigned conditionally with the conditional ref expression.</span></span> <span data-ttu-id="c895b-117">La expresión condicional ref también se puede usar como un [valor devuelto de referencia](../keywords/ref.md#reference-return-values) o como un [método de argumento de `ref`](../keywords/ref.md#passing-an-argument-by-reference).</span><span class="sxs-lookup"><span data-stu-id="c895b-117">You can also use the conditional ref expression as a [reference return value](../keywords/ref.md#reference-return-values) or as a [`ref` method argument](../keywords/ref.md#passing-an-argument-by-reference).</span></span>

<span data-ttu-id="c895b-118">La sintaxis de la expresión condicional ref es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="c895b-118">The syntax for the conditional ref expression is as follows:</span></span>

```csharp
condition ? ref consequent : ref alternative
```

<span data-ttu-id="c895b-119">Al igual que el operador condicional original, la expresión condicional ref evalúa solo una de las dos expresiones: ya sea `consequent` o `alternative`.</span><span class="sxs-lookup"><span data-stu-id="c895b-119">Like the original conditional operator, the conditional ref expression evaluates only one of the two expressions: either `consequent` or `alternative`.</span></span>

<span data-ttu-id="c895b-120">En el caso de la expresión condicional ref, los tipos de `consequent` y `alternative` deben coincidir.</span><span class="sxs-lookup"><span data-stu-id="c895b-120">In the case of the conditional ref expression, the type of `consequent` and `alternative` must be the same.</span></span>

<span data-ttu-id="c895b-121">En el siguiente ejemplo se muestra el uso de la expresión condicional ref:</span><span class="sxs-lookup"><span data-stu-id="c895b-121">The following example demonstrates the usage of the conditional ref expression:</span></span>

[!code-csharp-interactive[conditional ref](snippets/shared/ConditionalOperator.cs#ConditionalRef)]

## <a name="conditional-operator-and-an-ifelse-statement"></a><span data-ttu-id="c895b-122">Operador condicional y una instrucción `if..else`</span><span class="sxs-lookup"><span data-stu-id="c895b-122">Conditional operator and an `if..else` statement</span></span>

<span data-ttu-id="c895b-123">Es posible que el uso del operador condicional en lugar de una instrucción [if-else](../keywords/if-else.md) genere código más conciso en aquellos casos en los que tenga que calcular un valor condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="c895b-123">Use of the conditional operator instead of an [if-else](../keywords/if-else.md) statement might result in more concise code in cases when you need conditionally to compute a value.</span></span> <span data-ttu-id="c895b-124">El ejemplo siguiente muestra dos maneras de clasificar un entero como negativo o no negativo:</span><span class="sxs-lookup"><span data-stu-id="c895b-124">The following example demonstrates two ways to classify an integer as negative or nonnegative:</span></span>

[!code-csharp[conditional and if-else](snippets/shared/ConditionalOperator.cs#CompareWithIf)]

## <a name="operator-overloadability"></a><span data-ttu-id="c895b-125">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="c895b-125">Operator overloadability</span></span>

<span data-ttu-id="c895b-126">Un tipo definido por el usuario no puede sobrecargar el operador condicional.</span><span class="sxs-lookup"><span data-stu-id="c895b-126">A user-defined type cannot overload the conditional operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c895b-127">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="c895b-127">C# language specification</span></span>

<span data-ttu-id="c895b-128">Para más información, vea la sección sobre [operadores condicionales](~/_csharplang/spec/expressions.md#conditional-operator) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="c895b-128">For more information, see the [Conditional operator](~/_csharplang/spec/expressions.md#conditional-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="c895b-129">Para más información sobre la expresión condicional ref, vea la [nota de propuesta de características](~/_csharplang/proposals/csharp-7.2/conditional-ref.md).</span><span class="sxs-lookup"><span data-stu-id="c895b-129">For more information about the conditional ref expression, see the [feature proposal note](~/_csharplang/proposals/csharp-7.2/conditional-ref.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c895b-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="c895b-130">See also</span></span>

- [<span data-ttu-id="c895b-131">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="c895b-131">C# reference</span></span>](../index.md)
- [<span data-ttu-id="c895b-132">Operadores y expresiones de C#</span><span class="sxs-lookup"><span data-stu-id="c895b-132">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="c895b-133">Instrucción if-else</span><span class="sxs-lookup"><span data-stu-id="c895b-133">if-else statement</span></span>](../keywords/if-else.md)
- <span data-ttu-id="c895b-134">[Operadores ?. y ?[]](member-access-operators.md#null-conditional-operators--and-)</span><span class="sxs-lookup"><span data-stu-id="c895b-134">[?. and ?[] operators](member-access-operators.md#null-conditional-operators--and-)</span></span>
- [<span data-ttu-id="c895b-135">Operadores ?? y ??=</span><span class="sxs-lookup"><span data-stu-id="c895b-135">?? and ??= operators</span></span>](null-coalescing-operator.md)
- [<span data-ttu-id="c895b-136">ref (palabra clave)</span><span class="sxs-lookup"><span data-stu-id="c895b-136">ref keyword</span></span>](../keywords/ref.md)
