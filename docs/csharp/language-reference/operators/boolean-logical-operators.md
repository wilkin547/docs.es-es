---
title: Operadores lógicos booleanos (referencia de C#)
description: Obtenga información sobre los operadores de C# que realizan operaciones lógicas de negación, conjunción (AND) y disyunción inclusiva y exclusiva (OR) con operandos booleanos.
ms.date: 06/29/2020
author: pkulikov
f1_keywords:
- '!_CSharpKeyword'
- '&_CSharpKeyword'
- ^_CSharpKeyword
- '|_CSharpKeyword'
- '&&_CSharpKeyword'
- '||_CSharpKeyword'
- '|=_CSharpKeyword'
- ^=_CSharpKeyword
- '&=_CSharpKeyword'
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
ms.openlocfilehash: 00b1523029ed6562fda6947415029cd3b7a9b405
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916890"
---
# <a name="boolean-logical-operators-c-reference"></a><span data-ttu-id="80709-103">Operadores lógicos booleanos (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="80709-103">Boolean logical operators (C# reference)</span></span>

<span data-ttu-id="80709-104">Los operandos siguientes realizan operaciones lógicas con los operandos [bool](../builtin-types/bool.md):</span><span class="sxs-lookup"><span data-stu-id="80709-104">The following operators perform logical operations with [bool](../builtin-types/bool.md) operands:</span></span>

- <span data-ttu-id="80709-105">Operador unario [`!` (negación lógica)](#logical-negation-operator-).</span><span class="sxs-lookup"><span data-stu-id="80709-105">Unary [`!` (logical negation)](#logical-negation-operator-) operator.</span></span>
- <span data-ttu-id="80709-106">Operadores binarios [`&` (AND lógico)](#logical-and-operator-), [`|` (OR lógico)](#logical-or-operator-) y [`^` (OR exclusivo lógico)](#logical-exclusive-or-operator-).</span><span class="sxs-lookup"><span data-stu-id="80709-106">Binary [`&` (logical AND)](#logical-and-operator-), [`|` (logical OR)](#logical-or-operator-), and [`^` (logical exclusive OR)](#logical-exclusive-or-operator-) operators.</span></span> <span data-ttu-id="80709-107">Esos operadores siempre evalúan ambos operandos.</span><span class="sxs-lookup"><span data-stu-id="80709-107">Those operators always evaluate both operands.</span></span>
- <span data-ttu-id="80709-108">Operadores binarios [`&&` (AND lógico condicional)](#conditional-logical-and-operator-) y [`||` (OR lógico condicional)](#conditional-logical-or-operator-).</span><span class="sxs-lookup"><span data-stu-id="80709-108">Binary [`&&` (conditional logical AND)](#conditional-logical-and-operator-) and [`||` (conditional logical OR)](#conditional-logical-or-operator-) operators.</span></span> <span data-ttu-id="80709-109">Esos operadores evalúan el operando derecho solo si es necesario.</span><span class="sxs-lookup"><span data-stu-id="80709-109">Those operators evaluate the right-hand operand only if it's necessary.</span></span>

<span data-ttu-id="80709-110">En el caso de los operandos de los [tipos numéricos enteros](../builtin-types/integral-numeric-types.md), los operadores `&`, `|` y `^` realizan operaciones lógicas bit a bit.</span><span class="sxs-lookup"><span data-stu-id="80709-110">For operands of the [integral numeric types](../builtin-types/integral-numeric-types.md), the `&`, `|`, and `^` operators perform bitwise logical operations.</span></span> <span data-ttu-id="80709-111">Para obtener más información, vea [Operadores de desplazamiento y bit a bit](bitwise-and-shift-operators.md).</span><span class="sxs-lookup"><span data-stu-id="80709-111">For more information, see [Bitwise and shift operators](bitwise-and-shift-operators.md).</span></span>

## <a name="logical-negation-operator-"></a><span data-ttu-id="80709-112">Operador de negación lógico !</span><span class="sxs-lookup"><span data-stu-id="80709-112">Logical negation operator !</span></span>

<span data-ttu-id="80709-113">El operador `!` de prefijo unario calcula la negación lógica de su operando.</span><span class="sxs-lookup"><span data-stu-id="80709-113">The unary prefix `!` operator computes logical negation of its operand.</span></span> <span data-ttu-id="80709-114">Es decir, genera `true`, si el operando se evalúa como `false`, y `false`, si el operando se evalúa como `true`:</span><span class="sxs-lookup"><span data-stu-id="80709-114">That is, it produces `true`, if the operand evaluates to `false`, and `false`, if the operand evaluates to `true`:</span></span>

[!code-csharp-interactive[logical negation](snippets/shared/BooleanLogicalOperators.cs#Negation)]

<span data-ttu-id="80709-115">A partir de C# 8.0, el operador `!` de postfijo unario es un [operador que permite un valor NULL](null-forgiving.md).</span><span class="sxs-lookup"><span data-stu-id="80709-115">Beginning with C# 8.0, the unary postfix `!` operator is the [null-forgiving operator](null-forgiving.md).</span></span>

## <a name="logical-and-operator-amp"></a><a name="logical-and-operator-"></a> <span data-ttu-id="80709-116">Operador AND lógico &amp;</span><span class="sxs-lookup"><span data-stu-id="80709-116">Logical AND operator &amp;</span></span>

<span data-ttu-id="80709-117">El operador `&` calcula el operador AND lógico de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="80709-117">The `&` operator computes the logical AND of its operands.</span></span> <span data-ttu-id="80709-118">El resultado de `x & y` es `true` si `x` y `y` se evalúan como `true`.</span><span class="sxs-lookup"><span data-stu-id="80709-118">The result of `x & y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="80709-119">De lo contrario, el resultado es `false`.</span><span class="sxs-lookup"><span data-stu-id="80709-119">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="80709-120">El operador `&` evalúa ambos operandos, incluso aunque el izquierdo se evalúe como `false`, para que el resultado de la operación sea `false` con independencia del valor del operando derecho.</span><span class="sxs-lookup"><span data-stu-id="80709-120">The `&` operator evaluates both operands even if the left-hand operand evaluates to `false`, so that the operation result is `false` regardless of the value of the right-hand operand.</span></span>

<span data-ttu-id="80709-121">En el ejemplo siguiente, el operando derecho del operador `&` es una llamada de método, que se realiza independientemente del valor del operando izquierdo:</span><span class="sxs-lookup"><span data-stu-id="80709-121">In the following example, the right-hand operand of the `&` operator is a method call, which is performed regardless of the value of the left-hand operand:</span></span>

[!code-csharp-interactive[logical AND](snippets/shared/BooleanLogicalOperators.cs#And)]

<span data-ttu-id="80709-122">El [operador AND lógico condicional](#conditional-logical-and-operator-) `&&` también calcula el operador AND lógico de sus operandos, pero no evalúa el operando derecho si el izquierdo se evalúa como `false`.</span><span class="sxs-lookup"><span data-stu-id="80709-122">The [conditional logical AND operator](#conditional-logical-and-operator-) `&&` also computes the logical AND of its operands, but doesn't evaluate the right-hand operand if the left-hand operand evaluates to `false`.</span></span>

<span data-ttu-id="80709-123">En el caso de los operandos de los [tipos numéricos enteros](../builtin-types/integral-numeric-types.md), el operador `&` calcula el [AND lógico bit a bit](bitwise-and-shift-operators.md#logical-and-operator-) de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="80709-123">For operands of the [integral numeric types](../builtin-types/integral-numeric-types.md), the `&` operator computes the [bitwise logical AND](bitwise-and-shift-operators.md#logical-and-operator-) of its operands.</span></span> <span data-ttu-id="80709-124">El operador `&` unario es el [operador address-of](pointer-related-operators.md#address-of-operator-).</span><span class="sxs-lookup"><span data-stu-id="80709-124">The unary `&` operator is the [address-of operator](pointer-related-operators.md#address-of-operator-).</span></span>

## <a name="logical-exclusive-or-operator-"></a><span data-ttu-id="80709-125">Operador IR exclusivo lógico ^</span><span class="sxs-lookup"><span data-stu-id="80709-125">Logical exclusive OR operator ^</span></span>

<span data-ttu-id="80709-126">El operador `^` calcula el operador OR exclusivo lógica, también conocido como el operador XOR lógico, de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="80709-126">The `^` operator computes the logical exclusive OR, also known as the logical XOR, of its operands.</span></span> <span data-ttu-id="80709-127">El resultado de `x ^ y` es `true` si `x` se evalúa como `true` y `y` se evalúa como `false` o `x` se evalúa como `false` y `y` se evalúa como `true`.</span><span class="sxs-lookup"><span data-stu-id="80709-127">The result of `x ^ y` is `true` if `x` evaluates to `true` and `y` evaluates to `false`, or `x` evaluates to `false` and `y` evaluates to `true`.</span></span> <span data-ttu-id="80709-128">De lo contrario, el resultado es `false`.</span><span class="sxs-lookup"><span data-stu-id="80709-128">Otherwise, the result is `false`.</span></span> <span data-ttu-id="80709-129">Es decir, en los operandos `bool`, el operador `^` calcula el mismo resultado como el [operador de desigualdad](equality-operators.md#inequality-operator-) `!=`.</span><span class="sxs-lookup"><span data-stu-id="80709-129">That is, for the `bool` operands, the `^` operator computes the same result as the [inequality operator](equality-operators.md#inequality-operator-) `!=`.</span></span>

[!code-csharp-interactive[logical exclusive OR](snippets/shared/BooleanLogicalOperators.cs#Xor)]

<span data-ttu-id="80709-130">En el caso de los operandos de los [tipos numéricos enteros](../builtin-types/integral-numeric-types.md), el operador `^` calcula el [AND lógico bit a bit](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="80709-130">For operands of the [integral numeric types](../builtin-types/integral-numeric-types.md), the `^` operator computes the [bitwise logical exclusive OR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) of its operands.</span></span>

## <a name="logical-or-operator-"></a><span data-ttu-id="80709-131">Operador lógico OR |</span><span class="sxs-lookup"><span data-stu-id="80709-131">Logical OR operator |</span></span>

<span data-ttu-id="80709-132">El operador `|` calcula el operador OR lógico de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="80709-132">The `|` operator computes the logical OR of its operands.</span></span> <span data-ttu-id="80709-133">El resultado de `x | y` es `true` si `x` o `y` se evalúan como `true`.</span><span class="sxs-lookup"><span data-stu-id="80709-133">The result of `x | y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="80709-134">De lo contrario, el resultado es `false`.</span><span class="sxs-lookup"><span data-stu-id="80709-134">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="80709-135">El operador `|` evalúa ambos operandos, incluso aunque el izquierdo se evalúe como `true`, para que el resultado de la operación sea `true` con independencia del valor del operando derecho.</span><span class="sxs-lookup"><span data-stu-id="80709-135">The `|` operator evaluates both operands even if the left-hand operand evaluates to `true`, so that the operation result is `true` regardless of the value of the right-hand operand.</span></span>

<span data-ttu-id="80709-136">En el ejemplo siguiente, el operando derecho del operador `|` es una llamada de método, que se realiza independientemente del valor del operando izquierdo:</span><span class="sxs-lookup"><span data-stu-id="80709-136">In the following example, the right-hand operand of the `|` operator is a method call, which is performed regardless of the value of the left-hand operand:</span></span>

[!code-csharp-interactive[logical OR](snippets/shared/BooleanLogicalOperators.cs#Or)]

<span data-ttu-id="80709-137">El [operador OR lógico condicional](#conditional-logical-or-operator-) `||` también calcula el operador OR lógico de sus operandos, pero no evalúa el operando derecho si el izquierdo se evalúa como `true`.</span><span class="sxs-lookup"><span data-stu-id="80709-137">The [conditional logical OR operator](#conditional-logical-or-operator-) `||` also computes the logical OR of its operands, but doesn't evaluate the right-hand operand if the left-hand operand evaluates to `true`.</span></span>

<span data-ttu-id="80709-138">En el caso de los operandos de los [tipos numéricos enteros](../builtin-types/integral-numeric-types.md), el operador `|` calcula el [OR lógico bit a bit](bitwise-and-shift-operators.md#logical-or-operator-) de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="80709-138">For operands of the [integral numeric types](../builtin-types/integral-numeric-types.md), the `|` operator computes the [bitwise logical OR](bitwise-and-shift-operators.md#logical-or-operator-) of its operands.</span></span>

## <a name="conditional-logical-and-operator-ampamp"></a><a name="conditional-logical-and-operator-"></a> <span data-ttu-id="80709-139">Operador AND lógico condicional &amp;&amp;</span><span class="sxs-lookup"><span data-stu-id="80709-139">Conditional logical AND operator &amp;&amp;</span></span>

<span data-ttu-id="80709-140">El operador AND lógico condicional `&&`, también denominado operador AND lógico "de cortocircuito", calcula el operador AND lógico de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="80709-140">The conditional logical AND operator `&&`, also known as the "short-circuiting" logical AND operator, computes the logical AND of its operands.</span></span> <span data-ttu-id="80709-141">El resultado de `x && y` es `true` si `x` y `y` se evalúan como `true`.</span><span class="sxs-lookup"><span data-stu-id="80709-141">The result of `x && y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="80709-142">De lo contrario, el resultado es `false`.</span><span class="sxs-lookup"><span data-stu-id="80709-142">Otherwise, the result is `false`.</span></span> <span data-ttu-id="80709-143">Si `x` se evalúa como `false`, `y` no se evalúa.</span><span class="sxs-lookup"><span data-stu-id="80709-143">If `x` evaluates to `false`, `y` is not evaluated.</span></span>

<span data-ttu-id="80709-144">En el ejemplo siguiente, el operando derecho del operador `&&` es una llamada de método, que no se realiza si el operando izquierdo se evalúa como `false`:</span><span class="sxs-lookup"><span data-stu-id="80709-144">In the following example, the right-hand operand of the `&&` operator is a method call, which isn't performed if the left-hand operand evaluates to `false`:</span></span>

[!code-csharp-interactive[conditional logical AND](snippets/shared/BooleanLogicalOperators.cs#ConditionalAnd)]

<span data-ttu-id="80709-145">El [operador AND lógico](#logical-and-operator-) `&` también calcula el operador AND lógico de sus operandos, pero siempre evalúa ambos operandos.</span><span class="sxs-lookup"><span data-stu-id="80709-145">The [logical AND operator](#logical-and-operator-) `&` also computes the logical AND of its operands, but always evaluates both operands.</span></span>

## <a name="conditional-logical-or-operator-"></a><span data-ttu-id="80709-146">Operador OR lógico condicional ||</span><span class="sxs-lookup"><span data-stu-id="80709-146">Conditional logical OR operator ||</span></span>

<span data-ttu-id="80709-147">El operador OR lógico condicional `||`, también denominado operador OR lógico "de cortocircuito", calcula el operador OR lógico de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="80709-147">The conditional logical OR operator `||`, also known as the "short-circuiting" logical OR operator, computes the logical OR of its operands.</span></span> <span data-ttu-id="80709-148">El resultado de `x || y` es `true` si `x` o `y` se evalúan como `true`.</span><span class="sxs-lookup"><span data-stu-id="80709-148">The result of `x || y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="80709-149">De lo contrario, el resultado es `false`.</span><span class="sxs-lookup"><span data-stu-id="80709-149">Otherwise, the result is `false`.</span></span> <span data-ttu-id="80709-150">Si `x` se evalúa como `true`, `y` no se evalúa.</span><span class="sxs-lookup"><span data-stu-id="80709-150">If `x` evaluates to `true`, `y` is not evaluated.</span></span>

<span data-ttu-id="80709-151">En el ejemplo siguiente, el operando derecho del operador `||` es una llamada de método, que no se realiza si el operando izquierdo se evalúa como `true`:</span><span class="sxs-lookup"><span data-stu-id="80709-151">In the following example, the right-hand operand of the `||` operator is a method call, which isn't performed if the left-hand operand evaluates to `true`:</span></span>

[!code-csharp-interactive[conditional logical OR](snippets/shared/BooleanLogicalOperators.cs#ConditionalOr)]

<span data-ttu-id="80709-152">El [operador OR lógico](#logical-or-operator-) `|` también calcula el operador OR lógico de sus operandos, pero siempre evalúa ambos operandos.</span><span class="sxs-lookup"><span data-stu-id="80709-152">The [logical OR operator](#logical-or-operator-) `|` also computes the logical OR of its operands, but always evaluates both operands.</span></span>

## <a name="nullable-boolean-logical-operators"></a><span data-ttu-id="80709-153">Operadores lógicos booleanos que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="80709-153">Nullable Boolean logical operators</span></span>

<span data-ttu-id="80709-154">En el caso de los operandos `bool?`, los operadores [`&` (AND lógico)](#logical-and-operator-) y [`|` (OR lógico)](#logical-or-operator-) admiten la lógica de tres valores tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="80709-154">For `bool?` operands, the [`&` (logical AND)](#logical-and-operator-) and [`|` (logical OR)](#logical-or-operator-) operators support the three-valued logic as follows:</span></span>

- <span data-ttu-id="80709-155">El operador `&` produce `true` solo si sus dos operandos se evalúan como `true`.</span><span class="sxs-lookup"><span data-stu-id="80709-155">The `&` operator produces `true` only if both its operands evaluate to `true`.</span></span> <span data-ttu-id="80709-156">Si `x` o `y` se evalúan como `false`, `x & y` produce `false` (aunque otro operando se evalúe como `null`).</span><span class="sxs-lookup"><span data-stu-id="80709-156">If either `x` or `y` evaluates to `false`, `x & y` produces `false` (even if another operand evaluates to `null`).</span></span> <span data-ttu-id="80709-157">De lo contrario, el resultado de `x & y` es `null`.</span><span class="sxs-lookup"><span data-stu-id="80709-157">Otherwise, the result of `x & y` is `null`.</span></span>

- <span data-ttu-id="80709-158">El operador `|` produce `false` solo si sus dos operandos se evalúan como `false`.</span><span class="sxs-lookup"><span data-stu-id="80709-158">The `|` operator produces `false` only if both its operands evaluate to `false`.</span></span> <span data-ttu-id="80709-159">Si `x` o `y` se evalúan como `true`, `x | y` produce `true` (aunque otro operando se evalúe como `null`).</span><span class="sxs-lookup"><span data-stu-id="80709-159">If either `x` or `y` evaluates to `true`, `x | y` produces `true` (even if another operand evaluates to `null`).</span></span> <span data-ttu-id="80709-160">De lo contrario, el resultado de `x | y` es `null`.</span><span class="sxs-lookup"><span data-stu-id="80709-160">Otherwise, the result of `x | y` is `null`.</span></span>

<span data-ttu-id="80709-161">En la tabla siguiente se presenta esta semántica:</span><span class="sxs-lookup"><span data-stu-id="80709-161">The following table presents that semantics:</span></span>

|<span data-ttu-id="80709-162">x</span><span class="sxs-lookup"><span data-stu-id="80709-162">x</span></span>|<span data-ttu-id="80709-163">y</span><span class="sxs-lookup"><span data-stu-id="80709-163">y</span></span>|<span data-ttu-id="80709-164">x e y</span><span class="sxs-lookup"><span data-stu-id="80709-164">x&y</span></span>|<span data-ttu-id="80709-165">x&#124;y</span><span class="sxs-lookup"><span data-stu-id="80709-165">x&#124;y</span></span>|  
|----|----|----|----|  
|<span data-ttu-id="80709-166">true</span><span class="sxs-lookup"><span data-stu-id="80709-166">true</span></span>|<span data-ttu-id="80709-167">true</span><span class="sxs-lookup"><span data-stu-id="80709-167">true</span></span>|<span data-ttu-id="80709-168">true</span><span class="sxs-lookup"><span data-stu-id="80709-168">true</span></span>|<span data-ttu-id="80709-169">true</span><span class="sxs-lookup"><span data-stu-id="80709-169">true</span></span>|  
|<span data-ttu-id="80709-170">true</span><span class="sxs-lookup"><span data-stu-id="80709-170">true</span></span>|<span data-ttu-id="80709-171">False</span><span class="sxs-lookup"><span data-stu-id="80709-171">false</span></span>|<span data-ttu-id="80709-172">false</span><span class="sxs-lookup"><span data-stu-id="80709-172">false</span></span>|<span data-ttu-id="80709-173">true</span><span class="sxs-lookup"><span data-stu-id="80709-173">true</span></span>|  
|<span data-ttu-id="80709-174">true</span><span class="sxs-lookup"><span data-stu-id="80709-174">true</span></span>|<span data-ttu-id="80709-175">null</span><span class="sxs-lookup"><span data-stu-id="80709-175">null</span></span>|<span data-ttu-id="80709-176">null</span><span class="sxs-lookup"><span data-stu-id="80709-176">null</span></span>|<span data-ttu-id="80709-177">true</span><span class="sxs-lookup"><span data-stu-id="80709-177">true</span></span>|  
|<span data-ttu-id="80709-178">False</span><span class="sxs-lookup"><span data-stu-id="80709-178">false</span></span>|<span data-ttu-id="80709-179">true</span><span class="sxs-lookup"><span data-stu-id="80709-179">true</span></span>|<span data-ttu-id="80709-180">False</span><span class="sxs-lookup"><span data-stu-id="80709-180">false</span></span>|<span data-ttu-id="80709-181">true</span><span class="sxs-lookup"><span data-stu-id="80709-181">true</span></span>|  
|<span data-ttu-id="80709-182">False</span><span class="sxs-lookup"><span data-stu-id="80709-182">false</span></span>|<span data-ttu-id="80709-183">False</span><span class="sxs-lookup"><span data-stu-id="80709-183">false</span></span>|<span data-ttu-id="80709-184">False</span><span class="sxs-lookup"><span data-stu-id="80709-184">false</span></span>|<span data-ttu-id="80709-185">False</span><span class="sxs-lookup"><span data-stu-id="80709-185">false</span></span>|  
|<span data-ttu-id="80709-186">False</span><span class="sxs-lookup"><span data-stu-id="80709-186">false</span></span>|<span data-ttu-id="80709-187">null</span><span class="sxs-lookup"><span data-stu-id="80709-187">null</span></span>|<span data-ttu-id="80709-188">False</span><span class="sxs-lookup"><span data-stu-id="80709-188">false</span></span>|<span data-ttu-id="80709-189">nulo</span><span class="sxs-lookup"><span data-stu-id="80709-189">null</span></span>|  
|<span data-ttu-id="80709-190">null</span><span class="sxs-lookup"><span data-stu-id="80709-190">null</span></span>|<span data-ttu-id="80709-191">true</span><span class="sxs-lookup"><span data-stu-id="80709-191">true</span></span>|<span data-ttu-id="80709-192">null</span><span class="sxs-lookup"><span data-stu-id="80709-192">null</span></span>|<span data-ttu-id="80709-193">true</span><span class="sxs-lookup"><span data-stu-id="80709-193">true</span></span>|  
|<span data-ttu-id="80709-194">null</span><span class="sxs-lookup"><span data-stu-id="80709-194">null</span></span>|<span data-ttu-id="80709-195">False</span><span class="sxs-lookup"><span data-stu-id="80709-195">false</span></span>|<span data-ttu-id="80709-196">False</span><span class="sxs-lookup"><span data-stu-id="80709-196">false</span></span>|<span data-ttu-id="80709-197">nulo</span><span class="sxs-lookup"><span data-stu-id="80709-197">null</span></span>|  
|<span data-ttu-id="80709-198">null</span><span class="sxs-lookup"><span data-stu-id="80709-198">null</span></span>|<span data-ttu-id="80709-199">null</span><span class="sxs-lookup"><span data-stu-id="80709-199">null</span></span>|<span data-ttu-id="80709-200">null</span><span class="sxs-lookup"><span data-stu-id="80709-200">null</span></span>|<span data-ttu-id="80709-201">null</span><span class="sxs-lookup"><span data-stu-id="80709-201">null</span></span>|  

<span data-ttu-id="80709-202">El comportamiento de esos operadores difiere del comportamiento típico del operador con tipos de valor que aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="80709-202">The behavior of those operators differs from the typical operator behavior with nullable value types.</span></span> <span data-ttu-id="80709-203">Por lo general, un operador que se define para los operandos de un tipo de valor también se puede usar con los operandos del tipo de valor que acepta valores NULL correspondientes.</span><span class="sxs-lookup"><span data-stu-id="80709-203">Typically, an operator which is defined for operands of a value type can be also used with operands of the corresponding nullable value type.</span></span> <span data-ttu-id="80709-204">Este tipo de operador genera `null` si alguno de sus operandos se evalúa como `null`.</span><span class="sxs-lookup"><span data-stu-id="80709-204">Such an operator produces `null` if any of its operands evaluates to `null`.</span></span> <span data-ttu-id="80709-205">Sin embargo, los operadores `&` y `|` pueden generar un valor no NULL incluso si uno de los operandos es `null`.</span><span class="sxs-lookup"><span data-stu-id="80709-205">However, the `&` and `|` operators can produce non-null even if one of the operands evaluates to `null`.</span></span> <span data-ttu-id="80709-206">Para más información sobre el comportamiento de los operadores con tipos de valor que aceptan valores NULL, consulte la sección [Operadores de elevación](../builtin-types/nullable-value-types.md#lifted-operators) del artículo [Tipos de valor que aceptan valores NULL](../builtin-types/nullable-value-types.md).</span><span class="sxs-lookup"><span data-stu-id="80709-206">For more information about the operator behavior with nullable value types, see the [Lifted operators](../builtin-types/nullable-value-types.md#lifted-operators) section of the [Nullable value types](../builtin-types/nullable-value-types.md) article.</span></span>

<span data-ttu-id="80709-207">También puede usar los operadores `!` y `^` con los operandos `bool?`, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="80709-207">You can also use the `!` and `^` operators with `bool?` operands, as the following example shows:</span></span>

[!code-csharp-interactive[lifted negation and xor](snippets/shared/BooleanLogicalOperators.cs#WithNullableBoolean)]

<span data-ttu-id="80709-208">Los operadores lógicos condicionales `&&` y `||` no admiten los operandos `bool?`.</span><span class="sxs-lookup"><span data-stu-id="80709-208">The conditional logical operators `&&` and `||` don't support `bool?` operands.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="80709-209">Asignación compuesta</span><span class="sxs-lookup"><span data-stu-id="80709-209">Compound assignment</span></span>

<span data-ttu-id="80709-210">Para un operador binario `op`, una expresión de asignación compuesta con el formato</span><span class="sxs-lookup"><span data-stu-id="80709-210">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="80709-211">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="80709-211">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="80709-212">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="80709-212">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="80709-213">Los operadores `&`, `|` y `^` admiten la asignación compuesta, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="80709-213">The `&`, `|`, and `^` operators support compound assignment, as the following example shows:</span></span>

[!code-csharp-interactive[compound assignment](snippets/shared/BooleanLogicalOperators.cs#CompoundAssignment)]

> [!NOTE]
> <span data-ttu-id="80709-214">Los operadores lógicos condicionales `&&` y `||` no admiten la asignación compuesta.</span><span class="sxs-lookup"><span data-stu-id="80709-214">The conditional logical operators `&&` and `||` don't support compound assignment.</span></span>

## <a name="operator-precedence"></a><span data-ttu-id="80709-215">Prioridad de operadores</span><span class="sxs-lookup"><span data-stu-id="80709-215">Operator precedence</span></span>

<span data-ttu-id="80709-216">En la lista siguiente se ordenan los operadores lógicos desde la prioridad más alta a la más baja:</span><span class="sxs-lookup"><span data-stu-id="80709-216">The following list orders logical operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="80709-217">Operador de negación lógico `!`</span><span class="sxs-lookup"><span data-stu-id="80709-217">Logical negation operator `!`</span></span>
- <span data-ttu-id="80709-218">Operador AND lógico `&`</span><span class="sxs-lookup"><span data-stu-id="80709-218">Logical AND operator `&`</span></span>
- <span data-ttu-id="80709-219">Operador OR exclusivo lógico `^`</span><span class="sxs-lookup"><span data-stu-id="80709-219">Logical exclusive OR operator `^`</span></span>
- <span data-ttu-id="80709-220">Operador OR lógico `|`</span><span class="sxs-lookup"><span data-stu-id="80709-220">Logical OR operator `|`</span></span>
- <span data-ttu-id="80709-221">Operador AND lógico condicional `&&`</span><span class="sxs-lookup"><span data-stu-id="80709-221">Conditional logical AND operator `&&`</span></span>
- <span data-ttu-id="80709-222">Operador OR lógico condicional `||`</span><span class="sxs-lookup"><span data-stu-id="80709-222">Conditional logical OR operator `||`</span></span>

<span data-ttu-id="80709-223">Use los paréntesis, `()`, para cambiar el orden de evaluación impuesto por la prioridad de los operadores:</span><span class="sxs-lookup"><span data-stu-id="80709-223">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence:</span></span>

[!code-csharp-interactive[operator precedence](snippets/shared/BooleanLogicalOperators.cs#Precedence)]

<span data-ttu-id="80709-224">Para obtener la lista completa de los operadores de C# ordenados por nivel de prioridad, vea la sección [Prioridad de operadores](index.md#operator-precedence) del artículo [Operadores de C#](index.md).</span><span class="sxs-lookup"><span data-stu-id="80709-224">For the complete list of C# operators ordered by precedence level, see the [Operator precedence](index.md#operator-precedence) section of the [C# operators](index.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="80709-225">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="80709-225">Operator overloadability</span></span>

<span data-ttu-id="80709-226">Un tipo definido por el usuario puede [sobrecargar](operator-overloading.md) los operadores `!`, `&`, `|` y `^`.</span><span class="sxs-lookup"><span data-stu-id="80709-226">A user-defined type can [overload](operator-overloading.md) the `!`, `&`, `|`, and `^` operators.</span></span> <span data-ttu-id="80709-227">Cuando se sobrecarga un operador binario, también se sobrecarga de forma implícita el operador de asignación compuesta correspondiente.</span><span class="sxs-lookup"><span data-stu-id="80709-227">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="80709-228">Un tipo definido por el usuario no puede sobrecargar de forma explícita un operador de asignación compuesta.</span><span class="sxs-lookup"><span data-stu-id="80709-228">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

<span data-ttu-id="80709-229">Un tipo definido por el usuario no puede sobrecargar los operadores lógicos condicionales `&&` y `||`.</span><span class="sxs-lookup"><span data-stu-id="80709-229">A user-defined type cannot overload the conditional logical operators `&&` and `||`.</span></span> <span data-ttu-id="80709-230">Sin embargo, si un tipo definido por el usuario sobrecarga los [operadores true y false](true-false-operators.md) y el operador `&` o `|` de cierta manera, la operación `&&` o `||`, respectivamente, se puede evaluar para los operandos de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="80709-230">However, if a user-defined type overloads the [true and false operators](true-false-operators.md) and the `&` or `|` operator in a certain way, the `&&` or `||` operation, respectively, can be evaluated for the operands of that type.</span></span> <span data-ttu-id="80709-231">Para obtener más información, vea la sección [Operadores lógicos condicionales definidos por el usuario](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="80709-231">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="80709-232">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="80709-232">C# language specification</span></span>

<span data-ttu-id="80709-233">Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="80709-233">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="80709-234">Operador de negación lógico</span><span class="sxs-lookup"><span data-stu-id="80709-234">Logical negation operator</span></span>](~/_csharplang/spec/expressions.md#logical-negation-operator)
- [<span data-ttu-id="80709-235">Operadores lógicos</span><span class="sxs-lookup"><span data-stu-id="80709-235">Logical operators</span></span>](~/_csharplang/spec/expressions.md#logical-operators)
- [<span data-ttu-id="80709-236">Operadores lógicos condicionales</span><span class="sxs-lookup"><span data-stu-id="80709-236">Conditional logical operators</span></span>](~/_csharplang/spec/expressions.md#conditional-logical-operators)
- [<span data-ttu-id="80709-237">Asignación compuesta</span><span class="sxs-lookup"><span data-stu-id="80709-237">Compound assignment</span></span>](~/_csharplang/spec/expressions.md#compound-assignment)

## <a name="see-also"></a><span data-ttu-id="80709-238">Vea también</span><span class="sxs-lookup"><span data-stu-id="80709-238">See also</span></span>

- [<span data-ttu-id="80709-239">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="80709-239">C# reference</span></span>](../index.md)
- [<span data-ttu-id="80709-240">Operadores y expresiones de C#</span><span class="sxs-lookup"><span data-stu-id="80709-240">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="80709-241">Operadores de desplazamiento y bit a bit</span><span class="sxs-lookup"><span data-stu-id="80709-241">Bitwise and shift operators</span></span>](bitwise-and-shift-operators.md)
