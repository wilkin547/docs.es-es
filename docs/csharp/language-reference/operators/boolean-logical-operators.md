---
title: Operadores lógicos booleanos (referencia de C#)
description: Obtenga información sobre los operadores de C# que realizan operaciones lógicas de negación, conjunción (AND) y disyunción inclusiva y exclusiva (OR) con operandos booleanos.
ms.date: 09/27/2019
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
ms.openlocfilehash: 930329b922f585ac4763e6a66d3b192ae839f14f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398200"
---
# <a name="boolean-logical-operators-c-reference"></a><span data-ttu-id="18bd9-103">Operadores lógicos booleanos (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="18bd9-103">Boolean logical operators (C# reference)</span></span>

<span data-ttu-id="18bd9-104">Los operandos siguientes realizan operaciones lógicas con los operandos [bool](../builtin-types/bool.md):</span><span class="sxs-lookup"><span data-stu-id="18bd9-104">The following operators perform logical operations with [bool](../builtin-types/bool.md) operands:</span></span>

- <span data-ttu-id="18bd9-105">Operador unario [`!` (negación lógica)](#logical-negation-operator-).</span><span class="sxs-lookup"><span data-stu-id="18bd9-105">Unary [`!` (logical negation)](#logical-negation-operator-) operator.</span></span>
- <span data-ttu-id="18bd9-106">Operadores binarios [`&` (AND lógico)](#logical-and-operator-), [`|` (OR lógico)](#logical-or-operator-) y [`^` (OR exclusivo lógico)](#logical-exclusive-or-operator-).</span><span class="sxs-lookup"><span data-stu-id="18bd9-106">Binary [`&` (logical AND)](#logical-and-operator-), [`|` (logical OR)](#logical-or-operator-), and [`^` (logical exclusive OR)](#logical-exclusive-or-operator-) operators.</span></span> <span data-ttu-id="18bd9-107">Esos operadores siempre evalúan ambos operandos.</span><span class="sxs-lookup"><span data-stu-id="18bd9-107">Those operators always evaluate both operands.</span></span>
- <span data-ttu-id="18bd9-108">Operadores binarios [`&&` (AND lógico condicional)](#conditional-logical-and-operator-) y [`||` (OR lógico condicional)](#conditional-logical-or-operator-).</span><span class="sxs-lookup"><span data-stu-id="18bd9-108">Binary [`&&` (conditional logical AND)](#conditional-logical-and-operator-) and [`||` (conditional logical OR)](#conditional-logical-or-operator-) operators.</span></span> <span data-ttu-id="18bd9-109">Esos operadores evalúan el operando derecho solo si es necesario.</span><span class="sxs-lookup"><span data-stu-id="18bd9-109">Those operators evaluate the right-hand operand only if it's necessary.</span></span>

<span data-ttu-id="18bd9-110">En el caso de los operandos de los [tipos numéricos enteros](../builtin-types/integral-numeric-types.md), los operadores `&`, `|` y `^` realizan operaciones lógicas bit a bit.</span><span class="sxs-lookup"><span data-stu-id="18bd9-110">For operands of the [integral numeric types](../builtin-types/integral-numeric-types.md), the `&`, `|`, and `^` operators perform bitwise logical operations.</span></span> <span data-ttu-id="18bd9-111">Para obtener más información, vea [Operadores de desplazamiento y bit a bit](bitwise-and-shift-operators.md).</span><span class="sxs-lookup"><span data-stu-id="18bd9-111">For more information, see [Bitwise and shift operators](bitwise-and-shift-operators.md).</span></span>

## <a name="logical-negation-operator-"></a><span data-ttu-id="18bd9-112">Operador de negación lógico !</span><span class="sxs-lookup"><span data-stu-id="18bd9-112">Logical negation operator !</span></span>

<span data-ttu-id="18bd9-113">El operador `!` de prefijo unario calcula la negación lógica de su operando.</span><span class="sxs-lookup"><span data-stu-id="18bd9-113">The unary prefix `!` operator computes logical negation of its operand.</span></span> <span data-ttu-id="18bd9-114">Es decir, genera `true`, si el operando se evalúa como `false`, y `false`, si el operando se evalúa como `true`:</span><span class="sxs-lookup"><span data-stu-id="18bd9-114">That is, it produces `true`, if the operand evaluates to `false`, and `false`, if the operand evaluates to `true`:</span></span>

[!code-csharp-interactive[logical negation](snippets/BooleanLogicalOperators.cs#Negation)]

<span data-ttu-id="18bd9-115">A partir de C# 8.0, el operador `!` de postfijo unario es un [operador que permite un valor NULL](null-forgiving.md).</span><span class="sxs-lookup"><span data-stu-id="18bd9-115">Beginning with C# 8.0, the unary postfix `!` operator is the [null-forgiving operator](null-forgiving.md).</span></span>

## <a name="logical-and-operator-amp"></a><a name="logical-and-operator-"></a> <span data-ttu-id="18bd9-116">Operador AND lógico &amp;</span><span class="sxs-lookup"><span data-stu-id="18bd9-116">Logical AND operator &amp;</span></span>

<span data-ttu-id="18bd9-117">El operador `&` calcula el operador AND lógico de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="18bd9-117">The `&` operator computes the logical AND of its operands.</span></span> <span data-ttu-id="18bd9-118">El resultado de `x & y` es `true` si `x` y `y` se evalúan como `true`.</span><span class="sxs-lookup"><span data-stu-id="18bd9-118">The result of `x & y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="18bd9-119">De lo contrario, el resultado es `false`.</span><span class="sxs-lookup"><span data-stu-id="18bd9-119">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="18bd9-120">El operador `&` evalúa ambos operandos, incluso aunque el izquierdo se evalúe como `false`, para que el resultado de la operación sea `false` con independencia del valor del operando derecho.</span><span class="sxs-lookup"><span data-stu-id="18bd9-120">The `&` operator evaluates both operands even if the left-hand operand evaluates to `false`, so that the operation result is `false` regardless of the value of the right-hand operand.</span></span>

<span data-ttu-id="18bd9-121">En el ejemplo siguiente, el operando derecho del operador `&` es una llamada de método, que se realiza independientemente del valor del operando izquierdo:</span><span class="sxs-lookup"><span data-stu-id="18bd9-121">In the following example, the right-hand operand of the `&` operator is a method call, which is performed regardless of the value of the left-hand operand:</span></span>

[!code-csharp-interactive[logical AND](snippets/BooleanLogicalOperators.cs#And)]

<span data-ttu-id="18bd9-122">El [operador AND lógico condicional](#conditional-logical-and-operator-) `&&` también calcula el operador AND lógico de sus operandos, pero no evalúa el operando derecho si el izquierdo se evalúa como `false`.</span><span class="sxs-lookup"><span data-stu-id="18bd9-122">The [conditional logical AND operator](#conditional-logical-and-operator-) `&&` also computes the logical AND of its operands, but doesn't evaluate the right-hand operand if the left-hand operand evaluates to `false`.</span></span>

<span data-ttu-id="18bd9-123">En el caso de los operandos de los [tipos numéricos enteros](../builtin-types/integral-numeric-types.md), el operador `&` calcula el [AND lógico bit a bit](bitwise-and-shift-operators.md#logical-and-operator-) de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="18bd9-123">For operands of the [integral numeric types](../builtin-types/integral-numeric-types.md), the `&` operator computes the [bitwise logical AND](bitwise-and-shift-operators.md#logical-and-operator-) of its operands.</span></span> <span data-ttu-id="18bd9-124">El operador `&` unario es el [operador address-of](pointer-related-operators.md#address-of-operator-).</span><span class="sxs-lookup"><span data-stu-id="18bd9-124">The unary `&` operator is the [address-of operator](pointer-related-operators.md#address-of-operator-).</span></span>

## <a name="logical-exclusive-or-operator-"></a><span data-ttu-id="18bd9-125">Operador IR exclusivo lógico ^</span><span class="sxs-lookup"><span data-stu-id="18bd9-125">Logical exclusive OR operator ^</span></span>

<span data-ttu-id="18bd9-126">El operador `^` calcula el operador OR exclusivo lógica, también conocido como el operador XOR lógico, de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="18bd9-126">The `^` operator computes the logical exclusive OR, also known as the logical XOR, of its operands.</span></span> <span data-ttu-id="18bd9-127">El resultado de `x ^ y` es `true` si `x` se evalúa como `true` y `y` se evalúa como `false` o `x` se evalúa como `false` y `y` se evalúa como `true`.</span><span class="sxs-lookup"><span data-stu-id="18bd9-127">The result of `x ^ y` is `true` if `x` evaluates to `true` and `y` evaluates to `false`, or `x` evaluates to `false` and `y` evaluates to `true`.</span></span> <span data-ttu-id="18bd9-128">De lo contrario, el resultado es `false`.</span><span class="sxs-lookup"><span data-stu-id="18bd9-128">Otherwise, the result is `false`.</span></span> <span data-ttu-id="18bd9-129">Es decir, en los operandos `bool`, el operador `^` calcula el mismo resultado como el [operador de desigualdad](equality-operators.md#inequality-operator-) `!=`.</span><span class="sxs-lookup"><span data-stu-id="18bd9-129">That is, for the `bool` operands, the `^` operator computes the same result as the [inequality operator](equality-operators.md#inequality-operator-) `!=`.</span></span>

[!code-csharp-interactive[logical exclusive OR](snippets/BooleanLogicalOperators.cs#Xor)]

<span data-ttu-id="18bd9-130">En el caso de los operandos de los [tipos numéricos enteros](../builtin-types/integral-numeric-types.md), el operador `^` calcula el [AND lógico bit a bit](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="18bd9-130">For operands of the [integral numeric types](../builtin-types/integral-numeric-types.md), the `^` operator computes the [bitwise logical exclusive OR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) of its operands.</span></span>

## <a name="logical-or-operator-"></a><span data-ttu-id="18bd9-131">Operador lógico OR |</span><span class="sxs-lookup"><span data-stu-id="18bd9-131">Logical OR operator |</span></span>

<span data-ttu-id="18bd9-132">El operador `|` calcula el operador OR lógico de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="18bd9-132">The `|` operator computes the logical OR of its operands.</span></span> <span data-ttu-id="18bd9-133">El resultado de `x | y` es `true` si `x` o `y` se evalúan como `true`.</span><span class="sxs-lookup"><span data-stu-id="18bd9-133">The result of `x | y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="18bd9-134">De lo contrario, el resultado es `false`.</span><span class="sxs-lookup"><span data-stu-id="18bd9-134">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="18bd9-135">El operador `|` evalúa ambos operandos, incluso aunque el izquierdo se evalúe como `true`, para que el resultado de la operación sea `true` con independencia del valor del operando derecho.</span><span class="sxs-lookup"><span data-stu-id="18bd9-135">The `|` operator evaluates both operands even if the left-hand operand evaluates to `true`, so that the operation result is `true` regardless of the value of the right-hand operand.</span></span>

<span data-ttu-id="18bd9-136">En el ejemplo siguiente, el operando derecho del operador `|` es una llamada de método, que se realiza independientemente del valor del operando izquierdo:</span><span class="sxs-lookup"><span data-stu-id="18bd9-136">In the following example, the right-hand operand of the `|` operator is a method call, which is performed regardless of the value of the left-hand operand:</span></span>

[!code-csharp-interactive[logical OR](snippets/BooleanLogicalOperators.cs#Or)]

<span data-ttu-id="18bd9-137">El [operador OR lógico condicional](#conditional-logical-or-operator-) `||` también calcula el operador OR lógico de sus operandos, pero no evalúa el operando derecho si el izquierdo se evalúa como `true`.</span><span class="sxs-lookup"><span data-stu-id="18bd9-137">The [conditional logical OR operator](#conditional-logical-or-operator-) `||` also computes the logical OR of its operands, but doesn't evaluate the right-hand operand if the left-hand operand evaluates to `true`.</span></span>

<span data-ttu-id="18bd9-138">En el caso de los operandos de los [tipos numéricos enteros](../builtin-types/integral-numeric-types.md), el operador `|` calcula el [OR lógico bit a bit](bitwise-and-shift-operators.md#logical-or-operator-) de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="18bd9-138">For operands of the [integral numeric types](../builtin-types/integral-numeric-types.md), the `|` operator computes the [bitwise logical OR](bitwise-and-shift-operators.md#logical-or-operator-) of its operands.</span></span>

## <a name="conditional-logical-and-operator-ampamp"></a><a name="conditional-logical-and-operator-"></a> <span data-ttu-id="18bd9-139">Operador AND lógico condicional &amp;&amp;</span><span class="sxs-lookup"><span data-stu-id="18bd9-139">Conditional logical AND operator &amp;&amp;</span></span>

<span data-ttu-id="18bd9-140">El operador AND lógico condicional `&&`, también denominado operador AND lógico "de cortocircuito", calcula el operador AND lógico de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="18bd9-140">The conditional logical AND operator `&&`, also known as the "short-circuiting" logical AND operator, computes the logical AND of its operands.</span></span> <span data-ttu-id="18bd9-141">El resultado de `x && y` es `true` si `x` y `y` se evalúan como `true`.</span><span class="sxs-lookup"><span data-stu-id="18bd9-141">The result of `x && y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="18bd9-142">De lo contrario, el resultado es `false`.</span><span class="sxs-lookup"><span data-stu-id="18bd9-142">Otherwise, the result is `false`.</span></span> <span data-ttu-id="18bd9-143">Si `x` se evalúa como `false`, `y` no se evalúa.</span><span class="sxs-lookup"><span data-stu-id="18bd9-143">If `x` evaluates to `false`, `y` is not evaluated.</span></span>

<span data-ttu-id="18bd9-144">En el ejemplo siguiente, el operando derecho del operador `&&` es una llamada de método, que no se realiza si el operando izquierdo se evalúa como `false`:</span><span class="sxs-lookup"><span data-stu-id="18bd9-144">In the following example, the right-hand operand of the `&&` operator is a method call, which isn't performed if the left-hand operand evaluates to `false`:</span></span>

[!code-csharp-interactive[conditional logical AND](snippets/BooleanLogicalOperators.cs#ConditionalAnd)]

<span data-ttu-id="18bd9-145">El [operador AND lógico](#logical-and-operator-) `&` también calcula el operador AND lógico de sus operandos, pero siempre evalúa ambos operandos.</span><span class="sxs-lookup"><span data-stu-id="18bd9-145">The [logical AND operator](#logical-and-operator-) `&` also computes the logical AND of its operands, but always evaluates both operands.</span></span>

## <a name="conditional-logical-or-operator-"></a><span data-ttu-id="18bd9-146">Operador OR lógico condicional ||</span><span class="sxs-lookup"><span data-stu-id="18bd9-146">Conditional logical OR operator ||</span></span>

<span data-ttu-id="18bd9-147">El operador OR lógico condicional `||`, también denominado operador OR lógico "de cortocircuito", calcula el operador OR lógico de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="18bd9-147">The conditional logical OR operator `||`, also known as the "short-circuiting" logical OR operator, computes the logical OR of its operands.</span></span> <span data-ttu-id="18bd9-148">El resultado de `x || y` es `true` si `x` o `y` se evalúan como `true`.</span><span class="sxs-lookup"><span data-stu-id="18bd9-148">The result of `x || y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="18bd9-149">De lo contrario, el resultado es `false`.</span><span class="sxs-lookup"><span data-stu-id="18bd9-149">Otherwise, the result is `false`.</span></span> <span data-ttu-id="18bd9-150">Si `x` se evalúa como `true`, `y` no se evalúa.</span><span class="sxs-lookup"><span data-stu-id="18bd9-150">If `x` evaluates to `true`, `y` is not evaluated.</span></span>

<span data-ttu-id="18bd9-151">En el ejemplo siguiente, el operando derecho del operador `||` es una llamada de método, que no se realiza si el operando izquierdo se evalúa como `true`:</span><span class="sxs-lookup"><span data-stu-id="18bd9-151">In the following example, the right-hand operand of the `||` operator is a method call, which isn't performed if the left-hand operand evaluates to `true`:</span></span>

[!code-csharp-interactive[conditional logical OR](snippets/BooleanLogicalOperators.cs#ConditionalOr)]

<span data-ttu-id="18bd9-152">El [operador OR lógico](#logical-or-operator-) `|` también calcula el operador OR lógico de sus operandos, pero siempre evalúa ambos operandos.</span><span class="sxs-lookup"><span data-stu-id="18bd9-152">The [logical OR operator](#logical-or-operator-) `|` also computes the logical OR of its operands, but always evaluates both operands.</span></span>

## <a name="nullable-boolean-logical-operators"></a><span data-ttu-id="18bd9-153">Operadores lógicos booleanos que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="18bd9-153">Nullable Boolean logical operators</span></span>

<span data-ttu-id="18bd9-154">En el caso de los operandos `bool?`, los operadores `&` y `|` admiten la lógica de tres valores.</span><span class="sxs-lookup"><span data-stu-id="18bd9-154">For `bool?` operands, the `&` and `|` operators support the three-valued logic.</span></span> <span data-ttu-id="18bd9-155">La semántica de estos operadores se define en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="18bd9-155">The semantics of these operators is defined by the following table:</span></span>  
  
|<span data-ttu-id="18bd9-156">x</span><span class="sxs-lookup"><span data-stu-id="18bd9-156">x</span></span>|<span data-ttu-id="18bd9-157">y</span><span class="sxs-lookup"><span data-stu-id="18bd9-157">y</span></span>|<span data-ttu-id="18bd9-158">x e y</span><span class="sxs-lookup"><span data-stu-id="18bd9-158">x&y</span></span>|<span data-ttu-id="18bd9-159">x&#124;y</span><span class="sxs-lookup"><span data-stu-id="18bd9-159">x&#124;y</span></span>|  
|----|----|----|----|  
|<span data-ttu-id="18bd9-160">true</span><span class="sxs-lookup"><span data-stu-id="18bd9-160">true</span></span>|<span data-ttu-id="18bd9-161">true</span><span class="sxs-lookup"><span data-stu-id="18bd9-161">true</span></span>|<span data-ttu-id="18bd9-162">true</span><span class="sxs-lookup"><span data-stu-id="18bd9-162">true</span></span>|<span data-ttu-id="18bd9-163">true</span><span class="sxs-lookup"><span data-stu-id="18bd9-163">true</span></span>|  
|<span data-ttu-id="18bd9-164">true</span><span class="sxs-lookup"><span data-stu-id="18bd9-164">true</span></span>|<span data-ttu-id="18bd9-165">False</span><span class="sxs-lookup"><span data-stu-id="18bd9-165">false</span></span>|<span data-ttu-id="18bd9-166">false</span><span class="sxs-lookup"><span data-stu-id="18bd9-166">false</span></span>|<span data-ttu-id="18bd9-167">true</span><span class="sxs-lookup"><span data-stu-id="18bd9-167">true</span></span>|  
|<span data-ttu-id="18bd9-168">true</span><span class="sxs-lookup"><span data-stu-id="18bd9-168">true</span></span>|<span data-ttu-id="18bd9-169">null</span><span class="sxs-lookup"><span data-stu-id="18bd9-169">null</span></span>|<span data-ttu-id="18bd9-170">null</span><span class="sxs-lookup"><span data-stu-id="18bd9-170">null</span></span>|<span data-ttu-id="18bd9-171">true</span><span class="sxs-lookup"><span data-stu-id="18bd9-171">true</span></span>|  
|<span data-ttu-id="18bd9-172">False</span><span class="sxs-lookup"><span data-stu-id="18bd9-172">false</span></span>|<span data-ttu-id="18bd9-173">true</span><span class="sxs-lookup"><span data-stu-id="18bd9-173">true</span></span>|<span data-ttu-id="18bd9-174">False</span><span class="sxs-lookup"><span data-stu-id="18bd9-174">false</span></span>|<span data-ttu-id="18bd9-175">true</span><span class="sxs-lookup"><span data-stu-id="18bd9-175">true</span></span>|  
|<span data-ttu-id="18bd9-176">False</span><span class="sxs-lookup"><span data-stu-id="18bd9-176">false</span></span>|<span data-ttu-id="18bd9-177">False</span><span class="sxs-lookup"><span data-stu-id="18bd9-177">false</span></span>|<span data-ttu-id="18bd9-178">False</span><span class="sxs-lookup"><span data-stu-id="18bd9-178">false</span></span>|<span data-ttu-id="18bd9-179">False</span><span class="sxs-lookup"><span data-stu-id="18bd9-179">false</span></span>|  
|<span data-ttu-id="18bd9-180">False</span><span class="sxs-lookup"><span data-stu-id="18bd9-180">false</span></span>|<span data-ttu-id="18bd9-181">null</span><span class="sxs-lookup"><span data-stu-id="18bd9-181">null</span></span>|<span data-ttu-id="18bd9-182">False</span><span class="sxs-lookup"><span data-stu-id="18bd9-182">false</span></span>|<span data-ttu-id="18bd9-183">nulo</span><span class="sxs-lookup"><span data-stu-id="18bd9-183">null</span></span>|  
|<span data-ttu-id="18bd9-184">null</span><span class="sxs-lookup"><span data-stu-id="18bd9-184">null</span></span>|<span data-ttu-id="18bd9-185">true</span><span class="sxs-lookup"><span data-stu-id="18bd9-185">true</span></span>|<span data-ttu-id="18bd9-186">null</span><span class="sxs-lookup"><span data-stu-id="18bd9-186">null</span></span>|<span data-ttu-id="18bd9-187">true</span><span class="sxs-lookup"><span data-stu-id="18bd9-187">true</span></span>|  
|<span data-ttu-id="18bd9-188">null</span><span class="sxs-lookup"><span data-stu-id="18bd9-188">null</span></span>|<span data-ttu-id="18bd9-189">False</span><span class="sxs-lookup"><span data-stu-id="18bd9-189">false</span></span>|<span data-ttu-id="18bd9-190">False</span><span class="sxs-lookup"><span data-stu-id="18bd9-190">false</span></span>|<span data-ttu-id="18bd9-191">nulo</span><span class="sxs-lookup"><span data-stu-id="18bd9-191">null</span></span>|  
|<span data-ttu-id="18bd9-192">null</span><span class="sxs-lookup"><span data-stu-id="18bd9-192">null</span></span>|<span data-ttu-id="18bd9-193">null</span><span class="sxs-lookup"><span data-stu-id="18bd9-193">null</span></span>|<span data-ttu-id="18bd9-194">null</span><span class="sxs-lookup"><span data-stu-id="18bd9-194">null</span></span>|<span data-ttu-id="18bd9-195">null</span><span class="sxs-lookup"><span data-stu-id="18bd9-195">null</span></span>|  

<span data-ttu-id="18bd9-196">El comportamiento de esos operadores difiere del comportamiento típico del operador con tipos de valor que aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="18bd9-196">The behavior of those operators differs from the typical operator behavior with nullable value types.</span></span> <span data-ttu-id="18bd9-197">Por lo general, un operador que se define para los operandos de un tipo de valor también se puede usar con los operandos del tipo de valor que acepta valores NULL correspondientes.</span><span class="sxs-lookup"><span data-stu-id="18bd9-197">Typically, an operator which is defined for operands of a value type can be also used with operands of the corresponding nullable value type.</span></span> <span data-ttu-id="18bd9-198">Este tipo de operador genera `null` si alguno de sus operandos se evalúa como `null`.</span><span class="sxs-lookup"><span data-stu-id="18bd9-198">Such an operator produces `null` if any of its operands evaluates to `null`.</span></span> <span data-ttu-id="18bd9-199">Sin embargo, los operadores `&` y `|` pueden generar un valor no NULL incluso si uno de los operandos es `null`.</span><span class="sxs-lookup"><span data-stu-id="18bd9-199">However, the `&` and `|` operators can produce non-null even if one of the operands evaluates to `null`.</span></span> <span data-ttu-id="18bd9-200">Para más información sobre el comportamiento de los operadores con tipos de valor que aceptan valores NULL, consulte la sección [Operadores de elevación](../builtin-types/nullable-value-types.md#lifted-operators) del artículo [Tipos de valor que aceptan valores NULL](../builtin-types/nullable-value-types.md).</span><span class="sxs-lookup"><span data-stu-id="18bd9-200">For more information about the operator behavior with nullable value types, see the [Lifted operators](../builtin-types/nullable-value-types.md#lifted-operators) section of the [Nullable value types](../builtin-types/nullable-value-types.md) article.</span></span>

<span data-ttu-id="18bd9-201">También puede usar los operadores `!` y `^` con los operandos `bool?`, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="18bd9-201">You can also use the `!` and `^` operators with `bool?` operands, as the following example shows:</span></span>

[!code-csharp-interactive[lifted negation and xor](snippets/BooleanLogicalOperators.cs#WithNullableBoolean)]

<span data-ttu-id="18bd9-202">Los operadores lógicos condicionales `&&` y `||` no admiten los operandos `bool?`.</span><span class="sxs-lookup"><span data-stu-id="18bd9-202">The conditional logical operators `&&` and `||` don't support `bool?` operands.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="18bd9-203">Asignación compuesta</span><span class="sxs-lookup"><span data-stu-id="18bd9-203">Compound assignment</span></span>

<span data-ttu-id="18bd9-204">Para un operador binario `op`, una expresión de asignación compuesta con el formato</span><span class="sxs-lookup"><span data-stu-id="18bd9-204">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="18bd9-205">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="18bd9-205">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="18bd9-206">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="18bd9-206">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="18bd9-207">Los operadores `&`, `|` y `^` admiten la asignación compuesta, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="18bd9-207">The `&`, `|`, and `^` operators support compound assignment, as the following example shows:</span></span>

[!code-csharp-interactive[compound assignment](snippets/BooleanLogicalOperators.cs#CompoundAssignment)]

<span data-ttu-id="18bd9-208">Los operadores lógicos condicionales `&&` y `||` no admiten la asignación compuesta.</span><span class="sxs-lookup"><span data-stu-id="18bd9-208">The conditional logical operators `&&` and `||` don't support compound assignment.</span></span>

## <a name="operator-precedence"></a><span data-ttu-id="18bd9-209">Prioridad de operadores</span><span class="sxs-lookup"><span data-stu-id="18bd9-209">Operator precedence</span></span>

<span data-ttu-id="18bd9-210">En la lista siguiente se ordenan los operadores lógicos desde la prioridad más alta a la más baja:</span><span class="sxs-lookup"><span data-stu-id="18bd9-210">The following list orders logical operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="18bd9-211">Operador de negación lógico `!`</span><span class="sxs-lookup"><span data-stu-id="18bd9-211">Logical negation operator `!`</span></span>
- <span data-ttu-id="18bd9-212">Operador AND lógico `&`</span><span class="sxs-lookup"><span data-stu-id="18bd9-212">Logical AND operator `&`</span></span>
- <span data-ttu-id="18bd9-213">Operador OR exclusivo lógico `^`</span><span class="sxs-lookup"><span data-stu-id="18bd9-213">Logical exclusive OR operator `^`</span></span>
- <span data-ttu-id="18bd9-214">Operador OR lógico `|`</span><span class="sxs-lookup"><span data-stu-id="18bd9-214">Logical OR operator `|`</span></span>
- <span data-ttu-id="18bd9-215">Operador AND lógico condicional `&&`</span><span class="sxs-lookup"><span data-stu-id="18bd9-215">Conditional logical AND operator `&&`</span></span>
- <span data-ttu-id="18bd9-216">Operador OR lógico condicional `||`</span><span class="sxs-lookup"><span data-stu-id="18bd9-216">Conditional logical OR operator `||`</span></span>

<span data-ttu-id="18bd9-217">Use los paréntesis, `()`, para cambiar el orden de evaluación impuesto por la prioridad de los operadores:</span><span class="sxs-lookup"><span data-stu-id="18bd9-217">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence:</span></span>

[!code-csharp-interactive[operator precedence](snippets/BooleanLogicalOperators.cs#Precedence)]

<span data-ttu-id="18bd9-218">Para obtener la lista completa de los operadores de C# ordenados por nivel de prioridad, vea la sección [Prioridad de operadores](index.md#operator-precedence) del artículo [Operadores de C#](index.md).</span><span class="sxs-lookup"><span data-stu-id="18bd9-218">For the complete list of C# operators ordered by precedence level, see the [Operator precedence](index.md#operator-precedence) section of the [C# operators](index.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="18bd9-219">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="18bd9-219">Operator overloadability</span></span>

<span data-ttu-id="18bd9-220">Un tipo definido por el usuario puede [sobrecargar](operator-overloading.md) los operadores `!`, `&`, `|` y `^`.</span><span class="sxs-lookup"><span data-stu-id="18bd9-220">A user-defined type can [overload](operator-overloading.md) the `!`, `&`, `|`, and `^` operators.</span></span> <span data-ttu-id="18bd9-221">Cuando se sobrecarga un operador binario, también se sobrecarga de forma implícita el operador de asignación compuesta correspondiente.</span><span class="sxs-lookup"><span data-stu-id="18bd9-221">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="18bd9-222">Un tipo definido por el usuario no puede sobrecargar de forma explícita un operador de asignación compuesta.</span><span class="sxs-lookup"><span data-stu-id="18bd9-222">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

<span data-ttu-id="18bd9-223">Un tipo definido por el usuario no puede sobrecargar los operadores lógicos condicionales `&&` y `||`.</span><span class="sxs-lookup"><span data-stu-id="18bd9-223">A user-defined type cannot overload the conditional logical operators `&&` and `||`.</span></span> <span data-ttu-id="18bd9-224">Sin embargo, si un tipo definido por el usuario sobrecarga los [operadores true y false](true-false-operators.md) y el operador `&` o `|` de cierta manera, la operación `&&` o `||`, respectivamente, se puede evaluar para los operandos de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="18bd9-224">However, if a user-defined type overloads the [true and false operators](true-false-operators.md) and the `&` or `|` operator in a certain way, the `&&` or `||` operation, respectively, can be evaluated for the operands of that type.</span></span> <span data-ttu-id="18bd9-225">Para obtener más información, vea la sección [Operadores lógicos condicionales definidos por el usuario](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="18bd9-225">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="18bd9-226">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="18bd9-226">C# language specification</span></span>

<span data-ttu-id="18bd9-227">Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="18bd9-227">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="18bd9-228">Operador de negación lógico</span><span class="sxs-lookup"><span data-stu-id="18bd9-228">Logical negation operator</span></span>](~/_csharplang/spec/expressions.md#logical-negation-operator)
- [<span data-ttu-id="18bd9-229">Operadores lógicos</span><span class="sxs-lookup"><span data-stu-id="18bd9-229">Logical operators</span></span>](~/_csharplang/spec/expressions.md#logical-operators)
- [<span data-ttu-id="18bd9-230">Operadores lógicos condicionales</span><span class="sxs-lookup"><span data-stu-id="18bd9-230">Conditional logical operators</span></span>](~/_csharplang/spec/expressions.md#conditional-logical-operators)
- [<span data-ttu-id="18bd9-231">Asignación compuesta</span><span class="sxs-lookup"><span data-stu-id="18bd9-231">Compound assignment</span></span>](~/_csharplang/spec/expressions.md#compound-assignment)

## <a name="see-also"></a><span data-ttu-id="18bd9-232">Vea también</span><span class="sxs-lookup"><span data-stu-id="18bd9-232">See also</span></span>

- [<span data-ttu-id="18bd9-233">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="18bd9-233">C# reference</span></span>](../index.md)
- [<span data-ttu-id="18bd9-234">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="18bd9-234">C# operators</span></span>](index.md)
- [<span data-ttu-id="18bd9-235">Operadores de desplazamiento y bit a bit</span><span class="sxs-lookup"><span data-stu-id="18bd9-235">Bitwise and shift operators</span></span>](bitwise-and-shift-operators.md)
