---
title: 'Operadores lógicos booleanos: referencia de C#'
description: Obtenga información sobre los operadores de C# que realizan operaciones lógicas de negación, conjunción (AND) y disyunción inclusiva y exclusiva (OR) con operandos booleanos.
ms.date: 04/08/2019
author: pkulikov
f1_keywords:
- '!_CSharpKeyword'
- '&_CSharpKeyword'
- ^_CSharpKeyword
- '|_CSharpKeyword'
- '&&_CSharpKeyword'
- '||_CSharpKeyword'
helpviewer_keywords:
- logical operators [C#]
- short-circuiting operators [C#]
- logical negation operator [C#]
- NOT operator [C#]
- '! operator [C#]'
- AND operator [C#]
- ampersand operator [C#]
- conjunction operator [C#]
- '& operator [C#]'
- exclusive OR operator [C#]
- XOR operator [C#]
- ^ operator [C#]
- OR operator [C#]
- disjunction operator [C#]
- '| operator [C#]'
- conditional AND operator [C#]
- short-circuiting AND operator [C#]
- '&& operator [C#]'
- conditional OR operator [C#]
- short-circuiting OR operator [C#]
- '|| operator [C#]'
ms.openlocfilehash: de621b26334bbc9679ba7e48a9d5a0cbaec67eab
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59427323"
---
# <a name="boolean-logical-operators-c-reference"></a><span data-ttu-id="73f1d-103">Operadores lógicos booleanos (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="73f1d-103">Boolean logical operators (C# Reference)</span></span>

<span data-ttu-id="73f1d-104">Los operandos siguientes realizan operaciones lógicas con los operandos [bool](../keywords/bool.md):</span><span class="sxs-lookup"><span data-stu-id="73f1d-104">The following operators perform logical operations with the [bool](../keywords/bool.md) operands:</span></span>

- <span data-ttu-id="73f1d-105">Operador unario [`!` (negación lógica)](#logical-negation-operator-).</span><span class="sxs-lookup"><span data-stu-id="73f1d-105">Unary [`!` (logical negation)](#logical-negation-operator-) operator.</span></span>
- <span data-ttu-id="73f1d-106">Operadores binarios [`&` (AND lógico)](#logical-and-operator-), [`|` (OR lógico)](#logical-or-operator-) y [`^` (OR exclusivo lógico)](#logical-exclusive-or-operator-).</span><span class="sxs-lookup"><span data-stu-id="73f1d-106">Binary [`&` (logical AND)](#logical-and-operator-), [`|` (logical OR)](#logical-or-operator-), and [`^` (logical exclusive OR)](#logical-exclusive-or-operator-) operators.</span></span> <span data-ttu-id="73f1d-107">Esos operadores siempre evalúan ambos operandos.</span><span class="sxs-lookup"><span data-stu-id="73f1d-107">Those operators always evaluate both operands.</span></span>
- <span data-ttu-id="73f1d-108">Operadores binarios [`&&` (AND lógico condicional)](#conditional-logical-and-operator-) y [`||` (OR lógico condicional)](#conditional-logical-or-operator-).</span><span class="sxs-lookup"><span data-stu-id="73f1d-108">Binary [`&&` (conditional logical AND)](#conditional-logical-and-operator-) and [`||` (conditional logical OR)](#conditional-logical-or-operator-) operators.</span></span> <span data-ttu-id="73f1d-109">Esos operadores evalúan el segundo operando solo si es necesario.</span><span class="sxs-lookup"><span data-stu-id="73f1d-109">Those operators evaluate the second operand only if it's necessary.</span></span>

<span data-ttu-id="73f1d-110">Para los operandos de tipos [de datos enteros](../keywords/integral-types-table.md), los operadores `&`, `|` y `^` realizan operaciones lógicas bit a bit.</span><span class="sxs-lookup"><span data-stu-id="73f1d-110">For the operands of [integral](../keywords/integral-types-table.md) types, the `&`, `|`, and `^` operators perform bitwise logical operations.</span></span>

## <a name="logical-negation-operator-"></a><span data-ttu-id="73f1d-111">Operador de negación lógico !</span><span class="sxs-lookup"><span data-stu-id="73f1d-111">Logical negation operator !</span></span>

<span data-ttu-id="73f1d-112">El operador `!` calcula la negación lógica de su operando.</span><span class="sxs-lookup"><span data-stu-id="73f1d-112">The `!` operator computes logical negation of its operand.</span></span> <span data-ttu-id="73f1d-113">Es decir, genera `true`, si el operando se evalúa como `false`, y `false`, si el operando se evalúa como `true`:</span><span class="sxs-lookup"><span data-stu-id="73f1d-113">That is, it produces `true`, if the operand evaluates to `false`, and `false`, if the operand evaluates to `true`:</span></span>

[!code-csharp-interactive[logical negation](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Negation)]

## <a name="logical-and-operator-amp"></a><span data-ttu-id="73f1d-114">Operador AND lógico &amp;</span><span class="sxs-lookup"><span data-stu-id="73f1d-114">Logical AND operator &amp;</span></span>

<span data-ttu-id="73f1d-115">El operador `&` calcula el operador AND lógico de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="73f1d-115">The `&` operator computes the logical AND of its operands.</span></span> <span data-ttu-id="73f1d-116">El resultado de `x & y` es `true` si `x` y `y` se evalúan como `true`.</span><span class="sxs-lookup"><span data-stu-id="73f1d-116">The result of `x & y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="73f1d-117">De lo contrario, el resultado es `false`.</span><span class="sxs-lookup"><span data-stu-id="73f1d-117">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="73f1d-118">El operador `&` evalúa ambos, incluso aunque el primero se evalúe como `false`, de modo que el resultado debe ser `false` con independencia del valor del segundo operando.</span><span class="sxs-lookup"><span data-stu-id="73f1d-118">The `&` operator evaluates both operands even if the first operand evaluates to `false`, so that the result must be `false` regardless of the value of the second operand.</span></span>

<span data-ttu-id="73f1d-119">En el ejemplo siguiente, el segundo operando del operador `&` es una llamada de método, que se realiza independientemente del valor del primer operando:</span><span class="sxs-lookup"><span data-stu-id="73f1d-119">In the following example, the second operand of the `&` operator is a method call, which is performed regardless of the value of the first operand:</span></span>

[!code-csharp-interactive[logical AND](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#And)]

<span data-ttu-id="73f1d-120">El [operador AND lógico condicional](#conditional-logical-and-operator-) `&&` también calcula el operador AND lógico de sus operandos, pero no evalúa el segundo operando si el primero se evalúa como `false`.</span><span class="sxs-lookup"><span data-stu-id="73f1d-120">The [conditional logical AND operator](#conditional-logical-and-operator-) `&&` also computes the logical AND of its operands, but doesn't evaluate the second operand if the first operand evaluates to `false`.</span></span>

<span data-ttu-id="73f1d-121">En el caso de los operandos de tipos de datos enteros, el operador `&` calcula el operador [AND lógico bit a bit](and-operator.md#integer-logical-bitwise-and-operator) de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="73f1d-121">For the operands of integral types, the `&` operator computes [bitwise logical AND](and-operator.md#integer-logical-bitwise-and-operator) of its operands.</span></span> <span data-ttu-id="73f1d-122">El operador `&` unario es el [operador address-of](and-operator.md#unary-address-of-operator).</span><span class="sxs-lookup"><span data-stu-id="73f1d-122">The unary `&` operator is the [address-of operator](and-operator.md#unary-address-of-operator).</span></span>

## <a name="logical-exclusive-or-operator-"></a><span data-ttu-id="73f1d-123">Operador IR exclusivo lógico ^</span><span class="sxs-lookup"><span data-stu-id="73f1d-123">Logical exclusive OR operator ^</span></span>

<span data-ttu-id="73f1d-124">El operador `^` calcula el operador OR exclusivo lógica, también conocido como el operador XOR lógico, de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="73f1d-124">The `^` operator computes the logical exclusive OR, also known as the logical XOR, of its operands.</span></span> <span data-ttu-id="73f1d-125">El resultado de `x ^ y` es `true` si `x` se evalúa como `true` y `y` se evalúa como `false` o `x` se evalúa como `false` y `y` se evalúa como `true`.</span><span class="sxs-lookup"><span data-stu-id="73f1d-125">The result of `x ^ y` is `true` if `x` evaluates to `true` and `y` evaluates to `false`, or `x` evaluates to `false` and `y` evaluates to `true`.</span></span> <span data-ttu-id="73f1d-126">De lo contrario, el resultado es `false`.</span><span class="sxs-lookup"><span data-stu-id="73f1d-126">Otherwise, the result is `false`.</span></span> <span data-ttu-id="73f1d-127">Es decir, para los operandos `bool`, el operador `^` calcula el mismo resultado como el [operador de desigualdad](equality-operators.md#inequality-operator-) `!=`.</span><span class="sxs-lookup"><span data-stu-id="73f1d-127">That is, for the `bool` operands, the `^` operator computes the same result as the [inequality operator](equality-operators.md#inequality-operator-) `!=`.</span></span>

[!code-csharp-interactive[logical exclusive OR](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Xor)]

<span data-ttu-id="73f1d-128">En el caso de los operandos de tipos de datos enteros, el operador `^` calcula el operador [OR exclusivo lógico bit a bit](xor-operator.md) de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="73f1d-128">For the operands of integral types, the `^` operator computes [bitwise logical exclusive OR](xor-operator.md) of its operands.</span></span>

## <a name="logical-or-operator-"></a><span data-ttu-id="73f1d-129">Operador lógico OR |</span><span class="sxs-lookup"><span data-stu-id="73f1d-129">Logical OR operator |</span></span>

<span data-ttu-id="73f1d-130">El operador `|` calcula el operador OR lógico de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="73f1d-130">The `|` operator computes the logical OR of its operands.</span></span> <span data-ttu-id="73f1d-131">El resultado de `x | y` es `true` si `x` o `y` se evalúan como `true`.</span><span class="sxs-lookup"><span data-stu-id="73f1d-131">The result of `x | y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="73f1d-132">De lo contrario, el resultado es `false`.</span><span class="sxs-lookup"><span data-stu-id="73f1d-132">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="73f1d-133">El operador `|` evalúa ambos, incluso aunque el primero se evalúe como `true`, de modo que el resultado debe ser `true` con independencia del valor del segundo operando.</span><span class="sxs-lookup"><span data-stu-id="73f1d-133">The `|` operator evaluates both operands even if the first operand evaluates to `true`, so that the result must be `true` regardless of the value of the second operand.</span></span>

<span data-ttu-id="73f1d-134">En el ejemplo siguiente, el segundo operando del operador `|` es una llamada de método, que se realiza independientemente del valor del primer operando:</span><span class="sxs-lookup"><span data-stu-id="73f1d-134">In the following example, the second operand of the `|` operator is a method call, which is performed regardless of the value of the first operand:</span></span>

[!code-csharp-interactive[logical OR](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Or)]

<span data-ttu-id="73f1d-135">El [operador OR lógico condicional](#conditional-logical-or-operator-) `||` también calcula el operador OR lógico de sus operandos, pero no evalúa el segundo operando si el primero se evalúa como `true`.</span><span class="sxs-lookup"><span data-stu-id="73f1d-135">The [conditional logical OR operator](#conditional-logical-or-operator-) `||` also computes the logical OR of its operands, but doesn't evaluate the second operand if the first operand evaluates to `true`.</span></span>

<span data-ttu-id="73f1d-136">En el caso de los operados de tipos de datos enteros, el operador `|` calcula el operador [OR lógico bit a bit](or-operator.md) de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="73f1d-136">For the operands of integral types, the `|` operator computes [bitwise logical OR](or-operator.md) of its operands.</span></span>

## <a name="conditional-logical-and-operator-ampamp"></a><span data-ttu-id="73f1d-137">Operador AND lógico condicional &amp;&amp;</span><span class="sxs-lookup"><span data-stu-id="73f1d-137">Conditional logical AND operator &amp;&amp;</span></span>

<span data-ttu-id="73f1d-138">El operador AND lógico condicional `&&`, también denominado operador AND lógico "de cortocircuito", calcula el operador AND lógico de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="73f1d-138">The conditional logical AND operator `&&`, also known as the "short-circuiting" logical AND operator, computes the logical AND of its operands.</span></span> <span data-ttu-id="73f1d-139">El resultado de `x && y` es `true` si `x` y `y` se evalúan como `true`.</span><span class="sxs-lookup"><span data-stu-id="73f1d-139">The result of `x && y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="73f1d-140">De lo contrario, el resultado es `false`.</span><span class="sxs-lookup"><span data-stu-id="73f1d-140">Otherwise, the result is `false`.</span></span> <span data-ttu-id="73f1d-141">Si el primer operando se evalúa como `false`, no se evalúa el segundo operando.</span><span class="sxs-lookup"><span data-stu-id="73f1d-141">If the first operand evaluates to `false`, the second operand is not evaluated.</span></span>

<span data-ttu-id="73f1d-142">En el ejemplo siguiente, el segundo operando del operador `&&` es una llamada de método, que no se realiza si el primer operando se evalúa como `false`:</span><span class="sxs-lookup"><span data-stu-id="73f1d-142">In the following example, the second operand of the `&&` operator is a method call, which isn't performed if the first operand evaluates to `false`:</span></span>

[!code-csharp-interactive[conditional logical AND](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#ConditionalAnd)]

<span data-ttu-id="73f1d-143">El [operador AND lógico](#logical-and-operator-) `&` también calcula el operador AND lógico de sus operandos, pero siempre evalúa ambos operandos.</span><span class="sxs-lookup"><span data-stu-id="73f1d-143">The [logical AND operator](#logical-and-operator-) `&` also computes the logical AND of its operands, but always evaluates both operands.</span></span>

## <a name="conditional-logical-or-operator-"></a><span data-ttu-id="73f1d-144">Operador OR lógico condicional ||</span><span class="sxs-lookup"><span data-stu-id="73f1d-144">Conditional logical OR operator ||</span></span>

<span data-ttu-id="73f1d-145">El operador OR lógico condicional `||`, también denominado operador OR lógico "de cortocircuito", calcula el operador OR lógico de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="73f1d-145">The conditional logical OR operator `||`, also known as the "short-circuiting" logical OR operator, computes the logical OR of its operands.</span></span> <span data-ttu-id="73f1d-146">El resultado de `x || y` es `true` si `x` o `y` se evalúan como `true`.</span><span class="sxs-lookup"><span data-stu-id="73f1d-146">The result of `x || y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="73f1d-147">De lo contrario, el resultado es `false`.</span><span class="sxs-lookup"><span data-stu-id="73f1d-147">Otherwise, the result is `false`.</span></span> <span data-ttu-id="73f1d-148">Si el primer operando se evalúa como `true`, no se evalúa el segundo operando.</span><span class="sxs-lookup"><span data-stu-id="73f1d-148">If the first operand evaluates to `true`, the second operand is not evaluated.</span></span>

<span data-ttu-id="73f1d-149">En el ejemplo siguiente, el segundo operando del operador `||` es una llamada de método, que no se realiza si el primer operando se evalúa como `true`:</span><span class="sxs-lookup"><span data-stu-id="73f1d-149">In the following example, the second operand of the `||` operator is a method call, which isn't performed if the first operand evaluates to `true`:</span></span>

[!code-csharp-interactive[conditional logical OR](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#ConditionalOr)]

<span data-ttu-id="73f1d-150">El [operador OR lógico](#logical-or-operator-) `|` también calcula el operador OR lógico de sus operandos, pero siempre evalúa ambos operandos.</span><span class="sxs-lookup"><span data-stu-id="73f1d-150">The [logical OR operator](#logical-or-operator-) `|` also computes the logical OR of its operands, but always evaluates both operands.</span></span>

## <a name="nullable-boolean-logical-operators"></a><span data-ttu-id="73f1d-151">Operadores lógicos booleanos que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="73f1d-151">Nullable Boolean logical operators</span></span>

<span data-ttu-id="73f1d-152">En el caso de los operandos `bool?`, los operadores `&` y `|` admiten la lógica de tres valores.</span><span class="sxs-lookup"><span data-stu-id="73f1d-152">For the `bool?` operands, the `&` and `|` operators support the three-valued logic.</span></span> <span data-ttu-id="73f1d-153">La semántica de estos operadores se define en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="73f1d-153">The semantics of these operators is defined by the following table:</span></span>  
  
|<span data-ttu-id="73f1d-154">x</span><span class="sxs-lookup"><span data-stu-id="73f1d-154">x</span></span>|<span data-ttu-id="73f1d-155">y</span><span class="sxs-lookup"><span data-stu-id="73f1d-155">y</span></span>|<span data-ttu-id="73f1d-156">x e y</span><span class="sxs-lookup"><span data-stu-id="73f1d-156">x&y</span></span>|<span data-ttu-id="73f1d-157">x&#124;y</span><span class="sxs-lookup"><span data-stu-id="73f1d-157">x&#124;y</span></span>|  
|----|----|----|----|  
|<span data-ttu-id="73f1d-158">true</span><span class="sxs-lookup"><span data-stu-id="73f1d-158">true</span></span>|<span data-ttu-id="73f1d-159">true</span><span class="sxs-lookup"><span data-stu-id="73f1d-159">true</span></span>|<span data-ttu-id="73f1d-160">true</span><span class="sxs-lookup"><span data-stu-id="73f1d-160">true</span></span>|<span data-ttu-id="73f1d-161">true</span><span class="sxs-lookup"><span data-stu-id="73f1d-161">true</span></span>|  
|<span data-ttu-id="73f1d-162">true</span><span class="sxs-lookup"><span data-stu-id="73f1d-162">true</span></span>|<span data-ttu-id="73f1d-163">False</span><span class="sxs-lookup"><span data-stu-id="73f1d-163">false</span></span>|<span data-ttu-id="73f1d-164">false</span><span class="sxs-lookup"><span data-stu-id="73f1d-164">false</span></span>|<span data-ttu-id="73f1d-165">true</span><span class="sxs-lookup"><span data-stu-id="73f1d-165">true</span></span>|  
|<span data-ttu-id="73f1d-166">true</span><span class="sxs-lookup"><span data-stu-id="73f1d-166">true</span></span>|<span data-ttu-id="73f1d-167">nulo</span><span class="sxs-lookup"><span data-stu-id="73f1d-167">null</span></span>|<span data-ttu-id="73f1d-168">nulo</span><span class="sxs-lookup"><span data-stu-id="73f1d-168">null</span></span>|<span data-ttu-id="73f1d-169">true</span><span class="sxs-lookup"><span data-stu-id="73f1d-169">true</span></span>|  
|<span data-ttu-id="73f1d-170">False</span><span class="sxs-lookup"><span data-stu-id="73f1d-170">false</span></span>|<span data-ttu-id="73f1d-171">true</span><span class="sxs-lookup"><span data-stu-id="73f1d-171">true</span></span>|<span data-ttu-id="73f1d-172">False</span><span class="sxs-lookup"><span data-stu-id="73f1d-172">false</span></span>|<span data-ttu-id="73f1d-173">true</span><span class="sxs-lookup"><span data-stu-id="73f1d-173">true</span></span>|  
|<span data-ttu-id="73f1d-174">False</span><span class="sxs-lookup"><span data-stu-id="73f1d-174">false</span></span>|<span data-ttu-id="73f1d-175">False</span><span class="sxs-lookup"><span data-stu-id="73f1d-175">false</span></span>|<span data-ttu-id="73f1d-176">False</span><span class="sxs-lookup"><span data-stu-id="73f1d-176">false</span></span>|<span data-ttu-id="73f1d-177">False</span><span class="sxs-lookup"><span data-stu-id="73f1d-177">false</span></span>|  
|<span data-ttu-id="73f1d-178">False</span><span class="sxs-lookup"><span data-stu-id="73f1d-178">false</span></span>|<span data-ttu-id="73f1d-179">nulo</span><span class="sxs-lookup"><span data-stu-id="73f1d-179">null</span></span>|<span data-ttu-id="73f1d-180">False</span><span class="sxs-lookup"><span data-stu-id="73f1d-180">false</span></span>|<span data-ttu-id="73f1d-181">nulo</span><span class="sxs-lookup"><span data-stu-id="73f1d-181">null</span></span>|  
|<span data-ttu-id="73f1d-182">nulo</span><span class="sxs-lookup"><span data-stu-id="73f1d-182">null</span></span>|<span data-ttu-id="73f1d-183">true</span><span class="sxs-lookup"><span data-stu-id="73f1d-183">true</span></span>|<span data-ttu-id="73f1d-184">nulo</span><span class="sxs-lookup"><span data-stu-id="73f1d-184">null</span></span>|<span data-ttu-id="73f1d-185">true</span><span class="sxs-lookup"><span data-stu-id="73f1d-185">true</span></span>|  
|<span data-ttu-id="73f1d-186">nulo</span><span class="sxs-lookup"><span data-stu-id="73f1d-186">null</span></span>|<span data-ttu-id="73f1d-187">False</span><span class="sxs-lookup"><span data-stu-id="73f1d-187">false</span></span>|<span data-ttu-id="73f1d-188">False</span><span class="sxs-lookup"><span data-stu-id="73f1d-188">false</span></span>|<span data-ttu-id="73f1d-189">nulo</span><span class="sxs-lookup"><span data-stu-id="73f1d-189">null</span></span>|  
|<span data-ttu-id="73f1d-190">nulo</span><span class="sxs-lookup"><span data-stu-id="73f1d-190">null</span></span>|<span data-ttu-id="73f1d-191">nulo</span><span class="sxs-lookup"><span data-stu-id="73f1d-191">null</span></span>|<span data-ttu-id="73f1d-192">nulo</span><span class="sxs-lookup"><span data-stu-id="73f1d-192">null</span></span>|<span data-ttu-id="73f1d-193">nulo</span><span class="sxs-lookup"><span data-stu-id="73f1d-193">null</span></span>|  

<span data-ttu-id="73f1d-194">El comportamiento de esos operadores difiere del comportamiento típico del operador con tipos de valor que aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="73f1d-194">The behavior of those operators differs from the typical operator behavior with nullable value types.</span></span> <span data-ttu-id="73f1d-195">Por lo general, un operador que se define para los operandos de un tipo de valor también se puede usar con los operandos del tipo de valor que acepta valores NULL correspondientes.</span><span class="sxs-lookup"><span data-stu-id="73f1d-195">Typically, an operator which is defined for operands of a value type can be also used with operands of the corresponding nullable value type.</span></span> <span data-ttu-id="73f1d-196">Este tipo de operador genera `null` si alguno de sus operandos es `null`.</span><span class="sxs-lookup"><span data-stu-id="73f1d-196">Such an operator produces `null` if any of its operands is `null`.</span></span> <span data-ttu-id="73f1d-197">Sin embargo, los operadores `&` y `|` pueden generar un valor no NULL incluso si uno de los operandos es `null`.</span><span class="sxs-lookup"><span data-stu-id="73f1d-197">However, the `&` and `|` operators can produce non-null even if one of the operands is `null`.</span></span> <span data-ttu-id="73f1d-198">Para más información sobre el comportamiento de los operandos con tipos de valor que aceptan valores NULL, consulte la sección [Operadores](../../programming-guide/nullable-types/using-nullable-types.md#operators) del artículo [Uso de tipos que aceptan valores NULL](../../programming-guide/nullable-types/using-nullable-types.md).</span><span class="sxs-lookup"><span data-stu-id="73f1d-198">For more information about the operator behavior with nullable value types, see the [Operators](../../programming-guide/nullable-types/using-nullable-types.md#operators) section of the [Using nullable types](../../programming-guide/nullable-types/using-nullable-types.md) article.</span></span>

<span data-ttu-id="73f1d-199">También puede usar los operadores `!` y `^` con los operandos `bool?`, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="73f1d-199">You can also use the `!` and `^` operators with the `bool?` operands, as the following example shows:</span></span>

[!code-csharp-interactive[lifted negation and xor](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#WithNullableBoolean)]

<span data-ttu-id="73f1d-200">Los operadores lógicos condicionales `&&` y `||` no admiten los operandos `bool?`.</span><span class="sxs-lookup"><span data-stu-id="73f1d-200">The conditional logical operators `&&` and `||` don't support the `bool?` operands.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="73f1d-201">Asignación compuesta</span><span class="sxs-lookup"><span data-stu-id="73f1d-201">Compound assignment</span></span>

<span data-ttu-id="73f1d-202">Para un operador binario `op`, una expresión de asignación compuesta con el formato</span><span class="sxs-lookup"><span data-stu-id="73f1d-202">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="73f1d-203">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="73f1d-203">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="73f1d-204">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="73f1d-204">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="73f1d-205">Los operadores `&`, `|` y `^` admiten la asignación compuesta, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="73f1d-205">The `&`, `|`, and `^` operators support compound assignment, as the following example shows:</span></span>

[!code-csharp-interactive[compound assignment](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#CompoundAssignment)]

<span data-ttu-id="73f1d-206">Los operadores lógicos condicionales `&&` y `||` no admiten la asignación compuesta.</span><span class="sxs-lookup"><span data-stu-id="73f1d-206">The conditional logical operators `&&` and `||` don't support compound assignment.</span></span>

## <a name="operator-precedence"></a><span data-ttu-id="73f1d-207">Prioridad de operadores</span><span class="sxs-lookup"><span data-stu-id="73f1d-207">Operator precedence</span></span>

<span data-ttu-id="73f1d-208">En la lista siguiente se ordenan los operadores lógicos desde la prioridad más alta a la más baja:</span><span class="sxs-lookup"><span data-stu-id="73f1d-208">The following list orders logical operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="73f1d-209">Operador de negación lógico `!`</span><span class="sxs-lookup"><span data-stu-id="73f1d-209">Logical negation operator `!`</span></span>
- <span data-ttu-id="73f1d-210">Operador AND lógico `&`</span><span class="sxs-lookup"><span data-stu-id="73f1d-210">Logical AND operator `&`</span></span>
- <span data-ttu-id="73f1d-211">Operador OR exclusivo lógico `^`</span><span class="sxs-lookup"><span data-stu-id="73f1d-211">Logical exclusive OR operator `^`</span></span>
- <span data-ttu-id="73f1d-212">Operador OR lógico `|`</span><span class="sxs-lookup"><span data-stu-id="73f1d-212">Logical OR operator `|`</span></span>
- <span data-ttu-id="73f1d-213">Operador AND lógico condicional `&&`</span><span class="sxs-lookup"><span data-stu-id="73f1d-213">Conditional logical AND operator `&&`</span></span>
- <span data-ttu-id="73f1d-214">Operador OR lógico condicional `||`</span><span class="sxs-lookup"><span data-stu-id="73f1d-214">Conditional logical OR operator `||`</span></span>

<span data-ttu-id="73f1d-215">Use los paréntesis, `()`, para cambiar el orden de evaluación impuesto por la prioridad de los operadores:</span><span class="sxs-lookup"><span data-stu-id="73f1d-215">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence:</span></span>

[!code-csharp-interactive[operator precedence](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Precedence)]

<span data-ttu-id="73f1d-216">Para obtener la lista completa de los operadores de C# ordenados por nivel de prioridad, vea [Operadores de C#](index.md).</span><span class="sxs-lookup"><span data-stu-id="73f1d-216">For the complete list of C# operators ordered by precedence level, see [C# operators](index.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="73f1d-217">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="73f1d-217">Operator overloadability</span></span>

<span data-ttu-id="73f1d-218">Un tipo definido por el usuario puede [sobrecargar](../keywords/operator.md) los operadores `!`, `&`, `|` y `^`.</span><span class="sxs-lookup"><span data-stu-id="73f1d-218">A user-defined type can [overload](../keywords/operator.md) the `!`, `&`, `|`, and `^` operators.</span></span> <span data-ttu-id="73f1d-219">Cuando se sobrecarga un operador binario, también se sobrecarga de forma implícita el operador de asignación compuesta correspondiente.</span><span class="sxs-lookup"><span data-stu-id="73f1d-219">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="73f1d-220">Un tipo definido por el usuario no puede sobrecargar de forma explícita un operador de asignación compuesta.</span><span class="sxs-lookup"><span data-stu-id="73f1d-220">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

<span data-ttu-id="73f1d-221">Un tipo definido por el usuario no puede sobrecargar los operadores lógicos condicionales `&&` y `||`.</span><span class="sxs-lookup"><span data-stu-id="73f1d-221">A user-defined type cannot overload the conditional logical operators `&&` and `||`.</span></span> <span data-ttu-id="73f1d-222">Sin embargo, si un tipo definido por el usuario sobrecarga los [operadores true y false](../keywords/true-false-operators.md) y el operador `&` o `|` de cierta manera, la operación `&&` o `||`, respectivamente, se puede evaluar para los operandos de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="73f1d-222">However, if a user-defined type overloads the [true and false operators](../keywords/true-false-operators.md) and the `&` or `|` operator in a certain way, the `&&` or `||` operation, respectively, can be evaluated for the operands of that type.</span></span> <span data-ttu-id="73f1d-223">Para obtener más información, vea la sección [Operadores lógicos condicionales definidos por el usuario](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="73f1d-223">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="73f1d-224">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="73f1d-224">C# language specification</span></span>

<span data-ttu-id="73f1d-225">Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="73f1d-225">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="73f1d-226">Operador de negación lógico</span><span class="sxs-lookup"><span data-stu-id="73f1d-226">Logical negation operator</span></span>](~/_csharplang/spec/expressions.md#logical-negation-operator)
- [<span data-ttu-id="73f1d-227">Operadores lógicos</span><span class="sxs-lookup"><span data-stu-id="73f1d-227">Logical operators</span></span>](~/_csharplang/spec/expressions.md#logical-operators)
- [<span data-ttu-id="73f1d-228">Operadores lógicos condicionales</span><span class="sxs-lookup"><span data-stu-id="73f1d-228">Conditional logical operators</span></span>](~/_csharplang/spec/expressions.md#conditional-logical-operators)

## <a name="see-also"></a><span data-ttu-id="73f1d-229">Vea también</span><span class="sxs-lookup"><span data-stu-id="73f1d-229">See also</span></span>

- [<span data-ttu-id="73f1d-230">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="73f1d-230">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="73f1d-231">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="73f1d-231">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="73f1d-232">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="73f1d-232">C# Operators</span></span>](index.md)
