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
ms.openlocfilehash: b666c915506872930b16c1c5890de24e9cbe4f7a
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880579"
---
# <a name="boolean-logical-operators-c-reference"></a><span data-ttu-id="64a5c-103">Operadores lógicos booleanos (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="64a5c-103">Boolean logical operators (C# Reference)</span></span>

<span data-ttu-id="64a5c-104">Los operandos siguientes realizan operaciones lógicas con los operandos [bool](../keywords/bool.md):</span><span class="sxs-lookup"><span data-stu-id="64a5c-104">The following operators perform logical operations with the [bool](../keywords/bool.md) operands:</span></span>

- <span data-ttu-id="64a5c-105">Operador unario [`!` (negación lógica)](#logical-negation-operator-).</span><span class="sxs-lookup"><span data-stu-id="64a5c-105">Unary [`!` (logical negation)](#logical-negation-operator-) operator.</span></span>
- <span data-ttu-id="64a5c-106">Operadores binarios [`&` (AND lógico)](#logical-and-operator-), [`|` (OR lógico)](#logical-or-operator-) y [`^` (OR exclusivo lógico)](#logical-exclusive-or-operator-).</span><span class="sxs-lookup"><span data-stu-id="64a5c-106">Binary [`&` (logical AND)](#logical-and-operator-), [`|` (logical OR)](#logical-or-operator-), and [`^` (logical exclusive OR)](#logical-exclusive-or-operator-) operators.</span></span> <span data-ttu-id="64a5c-107">Esos operadores siempre evalúan ambos operandos.</span><span class="sxs-lookup"><span data-stu-id="64a5c-107">Those operators always evaluate both operands.</span></span>
- <span data-ttu-id="64a5c-108">Operadores binarios [`&&` (AND lógico condicional)](#conditional-logical-and-operator-) y [`||` (OR lógico condicional)](#conditional-logical-or-operator-).</span><span class="sxs-lookup"><span data-stu-id="64a5c-108">Binary [`&&` (conditional logical AND)](#conditional-logical-and-operator-) and [`||` (conditional logical OR)](#conditional-logical-or-operator-) operators.</span></span> <span data-ttu-id="64a5c-109">Esos operadores evalúan el segundo operando solo si es necesario.</span><span class="sxs-lookup"><span data-stu-id="64a5c-109">Those operators evaluate the second operand only if it's necessary.</span></span>

<span data-ttu-id="64a5c-110">En el caso de los operandos de tipo [entero](../keywords/integral-types-table.md), los operadores `&`, `|` y `^` realizan operaciones lógicas bit a bit.</span><span class="sxs-lookup"><span data-stu-id="64a5c-110">For the operands of the [integral](../keywords/integral-types-table.md) types, the `&`, `|`, and `^` operators perform bitwise logical operations.</span></span> <span data-ttu-id="64a5c-111">Para obtener más información, vea [Operadores de desplazamiento y bit a bit](bitwise-and-shift-operators.md).</span><span class="sxs-lookup"><span data-stu-id="64a5c-111">For more information, see [Bitwise and shift operators](bitwise-and-shift-operators.md).</span></span>

## <a name="logical-negation-operator-"></a><span data-ttu-id="64a5c-112">Operador de negación lógico !</span><span class="sxs-lookup"><span data-stu-id="64a5c-112">Logical negation operator !</span></span>

<span data-ttu-id="64a5c-113">El operador `!` calcula la negación lógica de su operando.</span><span class="sxs-lookup"><span data-stu-id="64a5c-113">The `!` operator computes logical negation of its operand.</span></span> <span data-ttu-id="64a5c-114">Es decir, genera `true`, si el operando se evalúa como `false`, y `false`, si el operando se evalúa como `true`:</span><span class="sxs-lookup"><span data-stu-id="64a5c-114">That is, it produces `true`, if the operand evaluates to `false`, and `false`, if the operand evaluates to `true`:</span></span>

[!code-csharp-interactive[logical negation](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Negation)]

## <a name="logical-and-operator-amp"></a><span data-ttu-id="64a5c-115">Operador AND lógico &amp;</span><span class="sxs-lookup"><span data-stu-id="64a5c-115">Logical AND operator &amp;</span></span>

<span data-ttu-id="64a5c-116">El operador `&` calcula el operador AND lógico de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="64a5c-116">The `&` operator computes the logical AND of its operands.</span></span> <span data-ttu-id="64a5c-117">El resultado de `x & y` es `true` si `x` y `y` se evalúan como `true`.</span><span class="sxs-lookup"><span data-stu-id="64a5c-117">The result of `x & y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="64a5c-118">De lo contrario, el resultado es `false`.</span><span class="sxs-lookup"><span data-stu-id="64a5c-118">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="64a5c-119">El operador `&` evalúa ambos, incluso aunque el primero se evalúe como `false`, de modo que el resultado debe ser `false` con independencia del valor del segundo operando.</span><span class="sxs-lookup"><span data-stu-id="64a5c-119">The `&` operator evaluates both operands even if the first operand evaluates to `false`, so that the result must be `false` regardless of the value of the second operand.</span></span>

<span data-ttu-id="64a5c-120">En el ejemplo siguiente, el segundo operando del operador `&` es una llamada de método, que se realiza independientemente del valor del primer operando:</span><span class="sxs-lookup"><span data-stu-id="64a5c-120">In the following example, the second operand of the `&` operator is a method call, which is performed regardless of the value of the first operand:</span></span>

[!code-csharp-interactive[logical AND](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#And)]

<span data-ttu-id="64a5c-121">El [operador AND lógico condicional](#conditional-logical-and-operator-) `&&` también calcula el operador AND lógico de sus operandos, pero no evalúa el segundo operando si el primero se evalúa como `false`.</span><span class="sxs-lookup"><span data-stu-id="64a5c-121">The [conditional logical AND operator](#conditional-logical-and-operator-) `&&` also computes the logical AND of its operands, but doesn't evaluate the second operand if the first operand evaluates to `false`.</span></span>

<span data-ttu-id="64a5c-122">En el caso de los operandos de tipo entero, el operador `&` calcula el [AND lógico bit a bit](bitwise-and-shift-operators.md#logical-and-operator-) de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="64a5c-122">For the operands of the integral types, the `&` operator computes the [bitwise logical AND](bitwise-and-shift-operators.md#logical-and-operator-) of its operands.</span></span> <span data-ttu-id="64a5c-123">El operador `&` unario es el [operador address-of](pointer-related-operators.md#address-of-operator-).</span><span class="sxs-lookup"><span data-stu-id="64a5c-123">The unary `&` operator is the [address-of operator](pointer-related-operators.md#address-of-operator-).</span></span>

## <a name="logical-exclusive-or-operator-"></a><span data-ttu-id="64a5c-124">Operador IR exclusivo lógico ^</span><span class="sxs-lookup"><span data-stu-id="64a5c-124">Logical exclusive OR operator ^</span></span>

<span data-ttu-id="64a5c-125">El operador `^` calcula el operador OR exclusivo lógica, también conocido como el operador XOR lógico, de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="64a5c-125">The `^` operator computes the logical exclusive OR, also known as the logical XOR, of its operands.</span></span> <span data-ttu-id="64a5c-126">El resultado de `x ^ y` es `true` si `x` se evalúa como `true` y `y` se evalúa como `false` o `x` se evalúa como `false` y `y` se evalúa como `true`.</span><span class="sxs-lookup"><span data-stu-id="64a5c-126">The result of `x ^ y` is `true` if `x` evaluates to `true` and `y` evaluates to `false`, or `x` evaluates to `false` and `y` evaluates to `true`.</span></span> <span data-ttu-id="64a5c-127">De lo contrario, el resultado es `false`.</span><span class="sxs-lookup"><span data-stu-id="64a5c-127">Otherwise, the result is `false`.</span></span> <span data-ttu-id="64a5c-128">Es decir, para los operandos `bool`, el operador `^` calcula el mismo resultado como el [operador de desigualdad](equality-operators.md#inequality-operator-) `!=`.</span><span class="sxs-lookup"><span data-stu-id="64a5c-128">That is, for the `bool` operands, the `^` operator computes the same result as the [inequality operator](equality-operators.md#inequality-operator-) `!=`.</span></span>

[!code-csharp-interactive[logical exclusive OR](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Xor)]

<span data-ttu-id="64a5c-129">En el caso de los operandos de tipo entero, el operador `^` calcula el [OR exclusivo lógico bit a bit](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="64a5c-129">For the operands of the integral types, the `^` operator computes the [bitwise logical exclusive OR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) of its operands.</span></span>

## <a name="logical-or-operator-"></a><span data-ttu-id="64a5c-130">Operador lógico OR |</span><span class="sxs-lookup"><span data-stu-id="64a5c-130">Logical OR operator |</span></span>

<span data-ttu-id="64a5c-131">El operador `|` calcula el operador OR lógico de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="64a5c-131">The `|` operator computes the logical OR of its operands.</span></span> <span data-ttu-id="64a5c-132">El resultado de `x | y` es `true` si `x` o `y` se evalúan como `true`.</span><span class="sxs-lookup"><span data-stu-id="64a5c-132">The result of `x | y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="64a5c-133">De lo contrario, el resultado es `false`.</span><span class="sxs-lookup"><span data-stu-id="64a5c-133">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="64a5c-134">El operador `|` evalúa ambos, incluso aunque el primero se evalúe como `true`, de modo que el resultado debe ser `true` con independencia del valor del segundo operando.</span><span class="sxs-lookup"><span data-stu-id="64a5c-134">The `|` operator evaluates both operands even if the first operand evaluates to `true`, so that the result must be `true` regardless of the value of the second operand.</span></span>

<span data-ttu-id="64a5c-135">En el ejemplo siguiente, el segundo operando del operador `|` es una llamada de método, que se realiza independientemente del valor del primer operando:</span><span class="sxs-lookup"><span data-stu-id="64a5c-135">In the following example, the second operand of the `|` operator is a method call, which is performed regardless of the value of the first operand:</span></span>

[!code-csharp-interactive[logical OR](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Or)]

<span data-ttu-id="64a5c-136">El [operador OR lógico condicional](#conditional-logical-or-operator-) `||` también calcula el operador OR lógico de sus operandos, pero no evalúa el segundo operando si el primero se evalúa como `true`.</span><span class="sxs-lookup"><span data-stu-id="64a5c-136">The [conditional logical OR operator](#conditional-logical-or-operator-) `||` also computes the logical OR of its operands, but doesn't evaluate the second operand if the first operand evaluates to `true`.</span></span>

<span data-ttu-id="64a5c-137">En el caso de los operandos de tipo entero, el operador `|` calcula el [OR lógico bit a bit](bitwise-and-shift-operators.md#logical-or-operator-) de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="64a5c-137">For the operands of the integral types, the `|` operator computes the [bitwise logical OR](bitwise-and-shift-operators.md#logical-or-operator-) of its operands.</span></span>

## <a name="conditional-logical-and-operator-ampamp"></a><span data-ttu-id="64a5c-138">Operador AND lógico condicional &amp;&amp;</span><span class="sxs-lookup"><span data-stu-id="64a5c-138">Conditional logical AND operator &amp;&amp;</span></span>

<span data-ttu-id="64a5c-139">El operador AND lógico condicional `&&`, también denominado operador AND lógico "de cortocircuito", calcula el operador AND lógico de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="64a5c-139">The conditional logical AND operator `&&`, also known as the "short-circuiting" logical AND operator, computes the logical AND of its operands.</span></span> <span data-ttu-id="64a5c-140">El resultado de `x && y` es `true` si `x` y `y` se evalúan como `true`.</span><span class="sxs-lookup"><span data-stu-id="64a5c-140">The result of `x && y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="64a5c-141">De lo contrario, el resultado es `false`.</span><span class="sxs-lookup"><span data-stu-id="64a5c-141">Otherwise, the result is `false`.</span></span> <span data-ttu-id="64a5c-142">Si el primer operando se evalúa como `false`, no se evalúa el segundo operando.</span><span class="sxs-lookup"><span data-stu-id="64a5c-142">If the first operand evaluates to `false`, the second operand is not evaluated.</span></span>

<span data-ttu-id="64a5c-143">En el ejemplo siguiente, el segundo operando del operador `&&` es una llamada de método, que no se realiza si el primer operando se evalúa como `false`:</span><span class="sxs-lookup"><span data-stu-id="64a5c-143">In the following example, the second operand of the `&&` operator is a method call, which isn't performed if the first operand evaluates to `false`:</span></span>

[!code-csharp-interactive[conditional logical AND](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#ConditionalAnd)]

<span data-ttu-id="64a5c-144">El [operador AND lógico](#logical-and-operator-) `&` también calcula el operador AND lógico de sus operandos, pero siempre evalúa ambos operandos.</span><span class="sxs-lookup"><span data-stu-id="64a5c-144">The [logical AND operator](#logical-and-operator-) `&` also computes the logical AND of its operands, but always evaluates both operands.</span></span>

## <a name="conditional-logical-or-operator-"></a><span data-ttu-id="64a5c-145">Operador OR lógico condicional ||</span><span class="sxs-lookup"><span data-stu-id="64a5c-145">Conditional logical OR operator ||</span></span>

<span data-ttu-id="64a5c-146">El operador OR lógico condicional `||`, también denominado operador OR lógico "de cortocircuito", calcula el operador OR lógico de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="64a5c-146">The conditional logical OR operator `||`, also known as the "short-circuiting" logical OR operator, computes the logical OR of its operands.</span></span> <span data-ttu-id="64a5c-147">El resultado de `x || y` es `true` si `x` o `y` se evalúan como `true`.</span><span class="sxs-lookup"><span data-stu-id="64a5c-147">The result of `x || y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="64a5c-148">De lo contrario, el resultado es `false`.</span><span class="sxs-lookup"><span data-stu-id="64a5c-148">Otherwise, the result is `false`.</span></span> <span data-ttu-id="64a5c-149">Si el primer operando se evalúa como `true`, no se evalúa el segundo operando.</span><span class="sxs-lookup"><span data-stu-id="64a5c-149">If the first operand evaluates to `true`, the second operand is not evaluated.</span></span>

<span data-ttu-id="64a5c-150">En el ejemplo siguiente, el segundo operando del operador `||` es una llamada de método, que no se realiza si el primer operando se evalúa como `true`:</span><span class="sxs-lookup"><span data-stu-id="64a5c-150">In the following example, the second operand of the `||` operator is a method call, which isn't performed if the first operand evaluates to `true`:</span></span>

[!code-csharp-interactive[conditional logical OR](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#ConditionalOr)]

<span data-ttu-id="64a5c-151">El [operador OR lógico](#logical-or-operator-) `|` también calcula el operador OR lógico de sus operandos, pero siempre evalúa ambos operandos.</span><span class="sxs-lookup"><span data-stu-id="64a5c-151">The [logical OR operator](#logical-or-operator-) `|` also computes the logical OR of its operands, but always evaluates both operands.</span></span>

## <a name="nullable-boolean-logical-operators"></a><span data-ttu-id="64a5c-152">Operadores lógicos booleanos que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="64a5c-152">Nullable Boolean logical operators</span></span>

<span data-ttu-id="64a5c-153">En el caso de los operandos `bool?`, los operadores `&` y `|` admiten la lógica de tres valores.</span><span class="sxs-lookup"><span data-stu-id="64a5c-153">For the `bool?` operands, the `&` and `|` operators support the three-valued logic.</span></span> <span data-ttu-id="64a5c-154">La semántica de estos operadores se define en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="64a5c-154">The semantics of these operators is defined by the following table:</span></span>  
  
|<span data-ttu-id="64a5c-155">x</span><span class="sxs-lookup"><span data-stu-id="64a5c-155">x</span></span>|<span data-ttu-id="64a5c-156">y</span><span class="sxs-lookup"><span data-stu-id="64a5c-156">y</span></span>|<span data-ttu-id="64a5c-157">x e y</span><span class="sxs-lookup"><span data-stu-id="64a5c-157">x&y</span></span>|<span data-ttu-id="64a5c-158">x&#124;y</span><span class="sxs-lookup"><span data-stu-id="64a5c-158">x&#124;y</span></span>|  
|----|----|----|----|  
|<span data-ttu-id="64a5c-159">true</span><span class="sxs-lookup"><span data-stu-id="64a5c-159">true</span></span>|<span data-ttu-id="64a5c-160">true</span><span class="sxs-lookup"><span data-stu-id="64a5c-160">true</span></span>|<span data-ttu-id="64a5c-161">true</span><span class="sxs-lookup"><span data-stu-id="64a5c-161">true</span></span>|<span data-ttu-id="64a5c-162">true</span><span class="sxs-lookup"><span data-stu-id="64a5c-162">true</span></span>|  
|<span data-ttu-id="64a5c-163">true</span><span class="sxs-lookup"><span data-stu-id="64a5c-163">true</span></span>|<span data-ttu-id="64a5c-164">False</span><span class="sxs-lookup"><span data-stu-id="64a5c-164">false</span></span>|<span data-ttu-id="64a5c-165">false</span><span class="sxs-lookup"><span data-stu-id="64a5c-165">false</span></span>|<span data-ttu-id="64a5c-166">true</span><span class="sxs-lookup"><span data-stu-id="64a5c-166">true</span></span>|  
|<span data-ttu-id="64a5c-167">true</span><span class="sxs-lookup"><span data-stu-id="64a5c-167">true</span></span>|<span data-ttu-id="64a5c-168">nulo</span><span class="sxs-lookup"><span data-stu-id="64a5c-168">null</span></span>|<span data-ttu-id="64a5c-169">nulo</span><span class="sxs-lookup"><span data-stu-id="64a5c-169">null</span></span>|<span data-ttu-id="64a5c-170">true</span><span class="sxs-lookup"><span data-stu-id="64a5c-170">true</span></span>|  
|<span data-ttu-id="64a5c-171">False</span><span class="sxs-lookup"><span data-stu-id="64a5c-171">false</span></span>|<span data-ttu-id="64a5c-172">true</span><span class="sxs-lookup"><span data-stu-id="64a5c-172">true</span></span>|<span data-ttu-id="64a5c-173">False</span><span class="sxs-lookup"><span data-stu-id="64a5c-173">false</span></span>|<span data-ttu-id="64a5c-174">true</span><span class="sxs-lookup"><span data-stu-id="64a5c-174">true</span></span>|  
|<span data-ttu-id="64a5c-175">False</span><span class="sxs-lookup"><span data-stu-id="64a5c-175">false</span></span>|<span data-ttu-id="64a5c-176">False</span><span class="sxs-lookup"><span data-stu-id="64a5c-176">false</span></span>|<span data-ttu-id="64a5c-177">False</span><span class="sxs-lookup"><span data-stu-id="64a5c-177">false</span></span>|<span data-ttu-id="64a5c-178">False</span><span class="sxs-lookup"><span data-stu-id="64a5c-178">false</span></span>|  
|<span data-ttu-id="64a5c-179">False</span><span class="sxs-lookup"><span data-stu-id="64a5c-179">false</span></span>|<span data-ttu-id="64a5c-180">nulo</span><span class="sxs-lookup"><span data-stu-id="64a5c-180">null</span></span>|<span data-ttu-id="64a5c-181">False</span><span class="sxs-lookup"><span data-stu-id="64a5c-181">false</span></span>|<span data-ttu-id="64a5c-182">nulo</span><span class="sxs-lookup"><span data-stu-id="64a5c-182">null</span></span>|  
|<span data-ttu-id="64a5c-183">nulo</span><span class="sxs-lookup"><span data-stu-id="64a5c-183">null</span></span>|<span data-ttu-id="64a5c-184">true</span><span class="sxs-lookup"><span data-stu-id="64a5c-184">true</span></span>|<span data-ttu-id="64a5c-185">nulo</span><span class="sxs-lookup"><span data-stu-id="64a5c-185">null</span></span>|<span data-ttu-id="64a5c-186">true</span><span class="sxs-lookup"><span data-stu-id="64a5c-186">true</span></span>|  
|<span data-ttu-id="64a5c-187">nulo</span><span class="sxs-lookup"><span data-stu-id="64a5c-187">null</span></span>|<span data-ttu-id="64a5c-188">False</span><span class="sxs-lookup"><span data-stu-id="64a5c-188">false</span></span>|<span data-ttu-id="64a5c-189">False</span><span class="sxs-lookup"><span data-stu-id="64a5c-189">false</span></span>|<span data-ttu-id="64a5c-190">nulo</span><span class="sxs-lookup"><span data-stu-id="64a5c-190">null</span></span>|  
|<span data-ttu-id="64a5c-191">nulo</span><span class="sxs-lookup"><span data-stu-id="64a5c-191">null</span></span>|<span data-ttu-id="64a5c-192">nulo</span><span class="sxs-lookup"><span data-stu-id="64a5c-192">null</span></span>|<span data-ttu-id="64a5c-193">nulo</span><span class="sxs-lookup"><span data-stu-id="64a5c-193">null</span></span>|<span data-ttu-id="64a5c-194">nulo</span><span class="sxs-lookup"><span data-stu-id="64a5c-194">null</span></span>|  

<span data-ttu-id="64a5c-195">El comportamiento de esos operadores difiere del comportamiento típico del operador con tipos de valor que aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="64a5c-195">The behavior of those operators differs from the typical operator behavior with nullable value types.</span></span> <span data-ttu-id="64a5c-196">Por lo general, un operador que se define para los operandos de un tipo de valor también se puede usar con los operandos del tipo de valor que acepta valores NULL correspondientes.</span><span class="sxs-lookup"><span data-stu-id="64a5c-196">Typically, an operator which is defined for operands of a value type can be also used with operands of the corresponding nullable value type.</span></span> <span data-ttu-id="64a5c-197">Este tipo de operador genera `null` si alguno de sus operandos es `null`.</span><span class="sxs-lookup"><span data-stu-id="64a5c-197">Such an operator produces `null` if any of its operands is `null`.</span></span> <span data-ttu-id="64a5c-198">Sin embargo, los operadores `&` y `|` pueden generar un valor no NULL incluso si uno de los operandos es `null`.</span><span class="sxs-lookup"><span data-stu-id="64a5c-198">However, the `&` and `|` operators can produce non-null even if one of the operands is `null`.</span></span> <span data-ttu-id="64a5c-199">Para más información sobre el comportamiento de los operandos con tipos de valor que aceptan valores NULL, consulte la sección [Operadores](../../programming-guide/nullable-types/using-nullable-types.md#operators) del artículo [Uso de tipos que aceptan valores NULL](../../programming-guide/nullable-types/using-nullable-types.md).</span><span class="sxs-lookup"><span data-stu-id="64a5c-199">For more information about the operator behavior with nullable value types, see the [Operators](../../programming-guide/nullable-types/using-nullable-types.md#operators) section of the [Using nullable types](../../programming-guide/nullable-types/using-nullable-types.md) article.</span></span>

<span data-ttu-id="64a5c-200">También puede usar los operadores `!` y `^` con los operandos `bool?`, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="64a5c-200">You can also use the `!` and `^` operators with the `bool?` operands, as the following example shows:</span></span>

[!code-csharp-interactive[lifted negation and xor](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#WithNullableBoolean)]

<span data-ttu-id="64a5c-201">Los operadores lógicos condicionales `&&` y `||` no admiten los operandos `bool?`.</span><span class="sxs-lookup"><span data-stu-id="64a5c-201">The conditional logical operators `&&` and `||` don't support the `bool?` operands.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="64a5c-202">Asignación compuesta</span><span class="sxs-lookup"><span data-stu-id="64a5c-202">Compound assignment</span></span>

<span data-ttu-id="64a5c-203">Para un operador binario `op`, una expresión de asignación compuesta con el formato</span><span class="sxs-lookup"><span data-stu-id="64a5c-203">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="64a5c-204">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="64a5c-204">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="64a5c-205">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="64a5c-205">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="64a5c-206">Los operadores `&`, `|` y `^` admiten la asignación compuesta, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="64a5c-206">The `&`, `|`, and `^` operators support compound assignment, as the following example shows:</span></span>

[!code-csharp-interactive[compound assignment](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#CompoundAssignment)]

<span data-ttu-id="64a5c-207">Los operadores lógicos condicionales `&&` y `||` no admiten la asignación compuesta.</span><span class="sxs-lookup"><span data-stu-id="64a5c-207">The conditional logical operators `&&` and `||` don't support compound assignment.</span></span>

## <a name="operator-precedence"></a><span data-ttu-id="64a5c-208">Prioridad de operadores</span><span class="sxs-lookup"><span data-stu-id="64a5c-208">Operator precedence</span></span>

<span data-ttu-id="64a5c-209">En la lista siguiente se ordenan los operadores lógicos desde la prioridad más alta a la más baja:</span><span class="sxs-lookup"><span data-stu-id="64a5c-209">The following list orders logical operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="64a5c-210">Operador de negación lógico `!`</span><span class="sxs-lookup"><span data-stu-id="64a5c-210">Logical negation operator `!`</span></span>
- <span data-ttu-id="64a5c-211">Operador AND lógico `&`</span><span class="sxs-lookup"><span data-stu-id="64a5c-211">Logical AND operator `&`</span></span>
- <span data-ttu-id="64a5c-212">Operador OR exclusivo lógico `^`</span><span class="sxs-lookup"><span data-stu-id="64a5c-212">Logical exclusive OR operator `^`</span></span>
- <span data-ttu-id="64a5c-213">Operador OR lógico `|`</span><span class="sxs-lookup"><span data-stu-id="64a5c-213">Logical OR operator `|`</span></span>
- <span data-ttu-id="64a5c-214">Operador AND lógico condicional `&&`</span><span class="sxs-lookup"><span data-stu-id="64a5c-214">Conditional logical AND operator `&&`</span></span>
- <span data-ttu-id="64a5c-215">Operador OR lógico condicional `||`</span><span class="sxs-lookup"><span data-stu-id="64a5c-215">Conditional logical OR operator `||`</span></span>

<span data-ttu-id="64a5c-216">Use los paréntesis, `()`, para cambiar el orden de evaluación impuesto por la prioridad de los operadores:</span><span class="sxs-lookup"><span data-stu-id="64a5c-216">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence:</span></span>

[!code-csharp-interactive[operator precedence](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Precedence)]

<span data-ttu-id="64a5c-217">Para obtener la lista completa de los operadores de C# ordenados por nivel de prioridad, vea [Operadores de C#](index.md).</span><span class="sxs-lookup"><span data-stu-id="64a5c-217">For the complete list of C# operators ordered by precedence level, see [C# operators](index.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="64a5c-218">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="64a5c-218">Operator overloadability</span></span>

<span data-ttu-id="64a5c-219">Un tipo definido por el usuario puede [sobrecargar](../keywords/operator.md) los operadores `!`, `&`, `|` y `^`.</span><span class="sxs-lookup"><span data-stu-id="64a5c-219">A user-defined type can [overload](../keywords/operator.md) the `!`, `&`, `|`, and `^` operators.</span></span> <span data-ttu-id="64a5c-220">Cuando se sobrecarga un operador binario, también se sobrecarga de forma implícita el operador de asignación compuesta correspondiente.</span><span class="sxs-lookup"><span data-stu-id="64a5c-220">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="64a5c-221">Un tipo definido por el usuario no puede sobrecargar de forma explícita un operador de asignación compuesta.</span><span class="sxs-lookup"><span data-stu-id="64a5c-221">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

<span data-ttu-id="64a5c-222">Un tipo definido por el usuario no puede sobrecargar los operadores lógicos condicionales `&&` y `||`.</span><span class="sxs-lookup"><span data-stu-id="64a5c-222">A user-defined type cannot overload the conditional logical operators `&&` and `||`.</span></span> <span data-ttu-id="64a5c-223">Sin embargo, si un tipo definido por el usuario sobrecarga los [operadores true y false](../keywords/true-false-operators.md) y el operador `&` o `|` de cierta manera, la operación `&&` o `||`, respectivamente, se puede evaluar para los operandos de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="64a5c-223">However, if a user-defined type overloads the [true and false operators](../keywords/true-false-operators.md) and the `&` or `|` operator in a certain way, the `&&` or `||` operation, respectively, can be evaluated for the operands of that type.</span></span> <span data-ttu-id="64a5c-224">Para obtener más información, vea la sección [Operadores lógicos condicionales definidos por el usuario](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="64a5c-224">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="64a5c-225">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="64a5c-225">C# language specification</span></span>

<span data-ttu-id="64a5c-226">Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="64a5c-226">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="64a5c-227">Operador de negación lógico</span><span class="sxs-lookup"><span data-stu-id="64a5c-227">Logical negation operator</span></span>](~/_csharplang/spec/expressions.md#logical-negation-operator)
- [<span data-ttu-id="64a5c-228">Operadores lógicos</span><span class="sxs-lookup"><span data-stu-id="64a5c-228">Logical operators</span></span>](~/_csharplang/spec/expressions.md#logical-operators)
- [<span data-ttu-id="64a5c-229">Operadores lógicos condicionales</span><span class="sxs-lookup"><span data-stu-id="64a5c-229">Conditional logical operators</span></span>](~/_csharplang/spec/expressions.md#conditional-logical-operators)
- [<span data-ttu-id="64a5c-230">Asignación compuesta</span><span class="sxs-lookup"><span data-stu-id="64a5c-230">Compound assignment</span></span>](~/_csharplang/spec/expressions.md#compound-assignment)

## <a name="see-also"></a><span data-ttu-id="64a5c-231">Vea también</span><span class="sxs-lookup"><span data-stu-id="64a5c-231">See also</span></span>

- [<span data-ttu-id="64a5c-232">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="64a5c-232">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="64a5c-233">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="64a5c-233">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="64a5c-234">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="64a5c-234">C# Operators</span></span>](index.md)
- [<span data-ttu-id="64a5c-235">Operadores de desplazamiento y bit a bit</span><span class="sxs-lookup"><span data-stu-id="64a5c-235">Bitwise and shift operators</span></span>](bitwise-and-shift-operators.md)
