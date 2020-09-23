---
description: 'Operador ?: (referencia de C#)'
title: 'Operador ?: (referencia de C#)'
ms.date: 09/17/2020
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: b6add045983619169bed0cd9f32eb27dba0a0338
ms.sourcegitcommit: a8730298170b8d96b4272e0c3dfc9819c606947b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "90738884"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="29ab2-103">Operador ?: (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="29ab2-103">?: operator (C# reference)</span></span>

<span data-ttu-id="29ab2-104">El operador condicional `?:`, también conocido como operador condicional ternario, evalúa una expresión booleana y devuelve el resultado de una de las dos expresiones, en función de que la expresión booleana se evalúe como `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="29ab2-104">The conditional operator `?:`, also known as the ternary conditional operator, evaluates a Boolean expression and returns the result of one of the two expressions, depending on whether the Boolean expression evaluates to `true` or `false`.</span></span>

<span data-ttu-id="29ab2-105">La sintaxis del operador condicional es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="29ab2-105">The syntax for the conditional operator is as follows:</span></span>

```csharp
condition ? consequent : alternative
```

<span data-ttu-id="29ab2-106">La expresión `condition` debe evaluarse como `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="29ab2-106">The `condition` expression must evaluate to `true` or `false`.</span></span> <span data-ttu-id="29ab2-107">Si `condition` se evalúa como `true`, se evalúa la expresión `consequent` y su resultado se convierte en el resultado de la operación.</span><span class="sxs-lookup"><span data-stu-id="29ab2-107">If `condition` evaluates to `true`, the `consequent` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="29ab2-108">Si `condition` se evalúa como `false`, se evalúa la expresión `alternative` y su resultado se convierte en el resultado de la operación.</span><span class="sxs-lookup"><span data-stu-id="29ab2-108">If `condition` evaluates to `false`, the `alternative` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="29ab2-109">Solo se evalúan `consequent` o `alternative`.</span><span class="sxs-lookup"><span data-stu-id="29ab2-109">Only `consequent` or `alternative` is evaluated.</span></span>

<span data-ttu-id="29ab2-110">A partir de C# 9.0, las expresiones condicionales tienen tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="29ab2-110">Beginning with C# 9.0, conditional expressions are target-typed.</span></span> <span data-ttu-id="29ab2-111">Es decir, si se conoce el tipo de destino de una expresión condicional, los tipos de `consequent` y `alternative` se deben poder convertir implícitamente al tipo de destino, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="29ab2-111">That is, if a target type of a conditional expression is known, the types of `consequent` and `alternative` must be implicitly convertible to the target type, as the following example shows:</span></span>

[!code-csharp[target-typed conditional](snippets/shared/ConditionalOperator.cs#TargetTyped)]

<span data-ttu-id="29ab2-112">Si se desconoce el tipo de destino de una expresión condicional (por ejemplo, al usar la palabra clave [`var`](../keywords/var.md)) o en C# 8.0 y versiones anteriores, el tipo de `consequent` y `alternative` debe ser el mismo, o bien debe haber una conversión implícita de un tipo a otro:</span><span class="sxs-lookup"><span data-stu-id="29ab2-112">If a target type of a conditional expression is unknown (for example, when you use the [`var`](../keywords/var.md) keyword) or in C# 8.0 and earlier, the type of `consequent` and `alternative` must be the same or there must be an implicit conversion from one type to the other:</span></span>

[!code-csharp[not target-typed conditional](snippets/shared/ConditionalOperator.cs#NotTargetTyped)]

<span data-ttu-id="29ab2-113">El operador condicional es asociativo a la derecha, es decir, una expresión de la forma</span><span class="sxs-lookup"><span data-stu-id="29ab2-113">The conditional operator is right-associative, that is, an expression of the form</span></span>

```csharp
a ? b : c ? d : e
```

<span data-ttu-id="29ab2-114">se evalúa como</span><span class="sxs-lookup"><span data-stu-id="29ab2-114">is evaluated as</span></span>

```csharp
a ? b : (c ? d : e)
```

> [!TIP]
> <span data-ttu-id="29ab2-115">Puede utilizar el siguiente recurso mnemotécnico para recordar cómo se evalúa el operador condicional:</span><span class="sxs-lookup"><span data-stu-id="29ab2-115">You can use the following mnemonic device to remember how the conditional operator is evaluated:</span></span>
>
> ```text
> is this condition true ? yes : no
> ```

<span data-ttu-id="29ab2-116">En el siguiente ejemplo se muestra el uso del operador condicional:</span><span class="sxs-lookup"><span data-stu-id="29ab2-116">The following example demonstrates the usage of the conditional operator:</span></span>

[!code-csharp-interactive[non ref conditional](snippets/shared/ConditionalOperator.cs#ConditionalValue)]

## <a name="conditional-ref-expression"></a><span data-ttu-id="29ab2-117">Expresión condicional ref</span><span class="sxs-lookup"><span data-stu-id="29ab2-117">Conditional ref expression</span></span>

<span data-ttu-id="29ab2-118">A partir de C# 7.2, las variables locales de tipo [ref](../keywords/ref.md#ref-locals) o [ref readonly](../keywords/ref.md#ref-readonly-locals) se pueden asignar condicionalmente con una expresión condicional ref.</span><span class="sxs-lookup"><span data-stu-id="29ab2-118">Beginning with C# 7.2, a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable can be assigned conditionally with a conditional ref expression.</span></span> <span data-ttu-id="29ab2-119">También puede usar una expresión condicional ref como un [valor devuelto de referencia](../keywords/ref.md#reference-return-values) o como un [método de argumento de `ref`](../keywords/ref.md#passing-an-argument-by-reference).</span><span class="sxs-lookup"><span data-stu-id="29ab2-119">You can also use a conditional ref expression as a [reference return value](../keywords/ref.md#reference-return-values) or as a [`ref` method argument](../keywords/ref.md#passing-an-argument-by-reference).</span></span>

<span data-ttu-id="29ab2-120">La sintaxis de una expresión condicional ref es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="29ab2-120">The syntax for a conditional ref expression is as follows:</span></span>

```csharp
condition ? ref consequent : ref alternative
```

<span data-ttu-id="29ab2-121">Como sucede con el operador condicional original, una expresión condicional ref evalúa solo una de las dos expresiones, ya sea `consequent` o `alternative`.</span><span class="sxs-lookup"><span data-stu-id="29ab2-121">Like the original conditional operator, a conditional ref expression evaluates only one of the two expressions: either `consequent` or `alternative`.</span></span>

<span data-ttu-id="29ab2-122">En el caso de una expresión condicional ref, los tipos de `consequent` y `alternative` deben coincidir.</span><span class="sxs-lookup"><span data-stu-id="29ab2-122">In the case of a conditional ref expression, the type of `consequent` and `alternative` must be the same.</span></span> <span data-ttu-id="29ab2-123">Las expresiones condicionales ref no tienen tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="29ab2-123">Conditional ref expressions are not target-typed.</span></span>

<span data-ttu-id="29ab2-124">En el ejemplo siguiente se muestra el uso de una expresión condicional ref:</span><span class="sxs-lookup"><span data-stu-id="29ab2-124">The following example demonstrates the usage of a conditional ref expression:</span></span>

[!code-csharp-interactive[conditional ref](snippets/shared/ConditionalOperator.cs#ConditionalRef)]

## <a name="conditional-operator-and-an-ifelse-statement"></a><span data-ttu-id="29ab2-125">Operador condicional y una instrucción `if..else`</span><span class="sxs-lookup"><span data-stu-id="29ab2-125">Conditional operator and an `if..else` statement</span></span>

<span data-ttu-id="29ab2-126">Es posible que el uso del operador condicional en lugar de una instrucción [if-else](../keywords/if-else.md) genere código más conciso en aquellos casos en los que tenga que calcular un valor condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="29ab2-126">Use of the conditional operator instead of an [if-else](../keywords/if-else.md) statement might result in more concise code in cases when you need conditionally to compute a value.</span></span> <span data-ttu-id="29ab2-127">El ejemplo siguiente muestra dos maneras de clasificar un entero como negativo o no negativo:</span><span class="sxs-lookup"><span data-stu-id="29ab2-127">The following example demonstrates two ways to classify an integer as negative or nonnegative:</span></span>

[!code-csharp[conditional and if-else](snippets/shared/ConditionalOperator.cs#CompareWithIf)]

## <a name="operator-overloadability"></a><span data-ttu-id="29ab2-128">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="29ab2-128">Operator overloadability</span></span>

<span data-ttu-id="29ab2-129">Un tipo definido por el usuario no puede sobrecargar el operador condicional.</span><span class="sxs-lookup"><span data-stu-id="29ab2-129">A user-defined type cannot overload the conditional operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="29ab2-130">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="29ab2-130">C# language specification</span></span>

<span data-ttu-id="29ab2-131">Para más información, vea la sección sobre [operadores condicionales](~/_csharplang/spec/expressions.md#conditional-operator) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="29ab2-131">For more information, see the [Conditional operator](~/_csharplang/spec/expressions.md#conditional-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="29ab2-132">Para obtener más información sobre de las características agregadas en C# 7.2 y versiones posteriores, vea las siguientes notas de propuesta de características:</span><span class="sxs-lookup"><span data-stu-id="29ab2-132">For more information about features added in C# 7.2 and later, see the following feature proposal notes:</span></span>

- [<span data-ttu-id="29ab2-133">Expresiones condicionales ref (C# 7.2)</span><span class="sxs-lookup"><span data-stu-id="29ab2-133">Conditional ref expressions (C# 7.2)</span></span>](~/_csharplang/proposals/csharp-7.2/conditional-ref.md)
- [<span data-ttu-id="29ab2-134">Expresión condicional con tipo de destino (C# 9.0)</span><span class="sxs-lookup"><span data-stu-id="29ab2-134">Target-typed conditional expression (C# 9.0)</span></span>](~/_csharplang/proposals/csharp-9.0/target-typed-conditional-expression.md)

## <a name="see-also"></a><span data-ttu-id="29ab2-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="29ab2-135">See also</span></span>

- [<span data-ttu-id="29ab2-136">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="29ab2-136">C# reference</span></span>](../index.md)
- [<span data-ttu-id="29ab2-137">Operadores y expresiones de C#</span><span class="sxs-lookup"><span data-stu-id="29ab2-137">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="29ab2-138">Instrucción if-else</span><span class="sxs-lookup"><span data-stu-id="29ab2-138">if-else statement</span></span>](../keywords/if-else.md)
- <span data-ttu-id="29ab2-139">[Operadores ?. y ?[]](member-access-operators.md#null-conditional-operators--and-)</span><span class="sxs-lookup"><span data-stu-id="29ab2-139">[?. and ?[] operators](member-access-operators.md#null-conditional-operators--and-)</span></span>
- [<span data-ttu-id="29ab2-140">Operadores ?? y ??=</span><span class="sxs-lookup"><span data-stu-id="29ab2-140">?? and ??= operators</span></span>](null-coalescing-operator.md)
- [<span data-ttu-id="29ab2-141">ref (palabra clave)</span><span class="sxs-lookup"><span data-stu-id="29ab2-141">ref keyword</span></span>](../keywords/ref.md)
