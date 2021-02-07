---
description: 'Más información sobre: if... Después... Else (instrucción) (Visual Basic)'
title: Instrucción If...Then...Else
ms.date: 04/16/2018
f1_keywords:
- vb.ElseIf
- vb.Then
- vb.If
- vb.EndIf
helpviewer_keywords:
- ElseIf statement [Visual Basic], If...Then...Else
- Then statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], branching
- execution [Visual Basic], conditional
- TypeOf...Is expression, and If...Then...Else statements
- If...Then...Else statements
- If statement [Visual Basic], If...Then...Else
- If statement [Visual Basic]
- Is operator [Visual Basic], in If...Then...Else statements
- If Operator [Visual Basic]
- branching [Visual Basic], conditional
- If function [Visual Basic], and If...Then...Else statements
- Else statement [Visual Basic]
ms.assetid: 790068a2-1307-4e28-8a72-be5ebda099e9
ms.openlocfilehash: 83850771354b95f0e2d9c1bf1360a61d5264fe2e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99769018"
---
# <a name="ifthenelse-statement-visual-basic"></a><span data-ttu-id="766f4-103">Instrucción If...Then...Else (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="766f4-103">If...Then...Else Statement (Visual Basic)</span></span>

<span data-ttu-id="766f4-104">Ejecuta condicionalmente un grupo de instrucciones en función del valor de una expresión.</span><span class="sxs-lookup"><span data-stu-id="766f4-104">Conditionally executes a group of statements, depending on the value of an expression.</span></span>

## <a name="syntax"></a><span data-ttu-id="766f4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="766f4-105">Syntax</span></span>

```vb
' Multiline syntax:
If condition [ Then ]
    [ statements ]
[ ElseIf elseifcondition [ Then ]
    [ elseifstatements ] ]
[ Else
    [ elsestatements ] ]
End If

' Single-line syntax:
If condition Then [ statements ] [ Else [ elsestatements ] ]
```

## <a name="quick-links-to-example-code"></a><span data-ttu-id="766f4-106">Vínculos rápidos a código de ejemplo</span><span class="sxs-lookup"><span data-stu-id="766f4-106">Quick links to example code</span></span>

<span data-ttu-id="766f4-107">En este artículo se incluyen varios ejemplos que muestran los usos de `If` ... `Then` ...`Else` privacidad</span><span class="sxs-lookup"><span data-stu-id="766f4-107">This article includes several examples that illustrate uses of the `If`...`Then`...`Else` statement:</span></span>

- [<span data-ttu-id="766f4-108">Ejemplo de sintaxis de varias líneas</span><span class="sxs-lookup"><span data-stu-id="766f4-108">Multiline syntax example</span></span>](#multi-line)
- [<span data-ttu-id="766f4-109">Ejemplo de sintaxis anidada</span><span class="sxs-lookup"><span data-stu-id="766f4-109">Nested syntax example</span></span>](#nested)
- [<span data-ttu-id="766f4-110">Ejemplo de sintaxis de una sola línea</span><span class="sxs-lookup"><span data-stu-id="766f4-110">Single-line syntax example</span></span>](#single-line)

## <a name="parts"></a><span data-ttu-id="766f4-111">Partes</span><span class="sxs-lookup"><span data-stu-id="766f4-111">Parts</span></span>

`condition` \
<span data-ttu-id="766f4-112">Necesario.</span><span class="sxs-lookup"><span data-stu-id="766f4-112">Required.</span></span> <span data-ttu-id="766f4-113">Expresión.</span><span class="sxs-lookup"><span data-stu-id="766f4-113">Expression.</span></span> <span data-ttu-id="766f4-114">Debe evaluarse como `True` o `False` , o en un tipo de datos que se pueda convertir implícitamente en `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="766f4-114">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>

<span data-ttu-id="766f4-115">Si la expresión es una variable que [acepta valores NULL](../../programming-guide/language-features/data-types/nullable-value-types.md) y `Boolean` que se evalúa como [Nothing](../nothing.md), la condición se trata como si la expresión fuese `False` , y los `ElseIf` bloques se evalúan si existen, o el `Else` bloque se ejecuta si existe.</span><span class="sxs-lookup"><span data-stu-id="766f4-115">If the expression is a [Nullable](../../programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` variable that evaluates to [Nothing](../nothing.md), the condition is treated as if the expression is `False`, and the `ElseIf` blocks are evaluated if they exist, or the `Else` block is executed if it exists.</span></span>

`Then` \
<span data-ttu-id="766f4-116">Requerido en la sintaxis de una sola línea; opcional en la sintaxis de varias líneas.</span><span class="sxs-lookup"><span data-stu-id="766f4-116">Required in the single-line syntax; optional in the multiline syntax.</span></span>

`statements` \
<span data-ttu-id="766f4-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="766f4-117">Optional.</span></span> <span data-ttu-id="766f4-118">Una o más instrucciones `If` que siguen a... `Then` que se ejecutan si se `condition` evalúa como `True` .</span><span class="sxs-lookup"><span data-stu-id="766f4-118">One or more statements following `If`...`Then` that are executed if `condition` evaluates to `True`.</span></span>

`elseifcondition` \
<span data-ttu-id="766f4-119">Obligatorio si `ElseIf` está presente.</span><span class="sxs-lookup"><span data-stu-id="766f4-119">Required if `ElseIf` is present.</span></span> <span data-ttu-id="766f4-120">Expresión.</span><span class="sxs-lookup"><span data-stu-id="766f4-120">Expression.</span></span> <span data-ttu-id="766f4-121">Debe evaluarse como `True` o `False` , o en un tipo de datos que se pueda convertir implícitamente en `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="766f4-121">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>

`elseifstatements` \
<span data-ttu-id="766f4-122">Opcional.</span><span class="sxs-lookup"><span data-stu-id="766f4-122">Optional.</span></span> <span data-ttu-id="766f4-123">Una o más instrucciones `ElseIf` que siguen a... `Then` que se ejecutan si se `elseifcondition` evalúa como `True` .</span><span class="sxs-lookup"><span data-stu-id="766f4-123">One or more statements following `ElseIf`...`Then` that are executed if `elseifcondition` evaluates to `True`.</span></span>

`elsestatements` \
<span data-ttu-id="766f4-124">Opcional.</span><span class="sxs-lookup"><span data-stu-id="766f4-124">Optional.</span></span> <span data-ttu-id="766f4-125">Una o varias instrucciones que se ejecutan si ninguna `condition` expresión or anterior se `elseifcondition` evalúa como `True` .</span><span class="sxs-lookup"><span data-stu-id="766f4-125">One or more statements that are executed if no previous `condition` or `elseifcondition` expression evaluates to `True`.</span></span>

`End If` \
<span data-ttu-id="766f4-126">Finaliza la versión multilínea de `If` ... `Then` ...`Else` sin.</span><span class="sxs-lookup"><span data-stu-id="766f4-126">Terminates the multiline version of `If`...`Then`...`Else` block.</span></span>

## <a name="remarks"></a><span data-ttu-id="766f4-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="766f4-127">Remarks</span></span>

### <a name="multiline-syntax"></a><span data-ttu-id="766f4-128">Sintaxis de varias líneas</span><span class="sxs-lookup"><span data-stu-id="766f4-128">Multiline syntax</span></span>

<span data-ttu-id="766f4-129">Cuando `If` ... `Then` ...`Else` la instrucción se ha encontrado, `condition` se ha probado.</span><span class="sxs-lookup"><span data-stu-id="766f4-129">When an `If`...`Then`...`Else` statement is encountered, `condition` is tested.</span></span> <span data-ttu-id="766f4-130">Si `condition` es `True` , `Then` se ejecutan las instrucciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="766f4-130">If `condition` is `True`, the statements following `Then` are executed.</span></span> <span data-ttu-id="766f4-131">Si `condition` es `False` , cada `ElseIf` instrucción (si hay alguna) se evalúa en orden.</span><span class="sxs-lookup"><span data-stu-id="766f4-131">If `condition` is `False`, each `ElseIf` statement (if there are any) is evaluated in order.</span></span> <span data-ttu-id="766f4-132">Cuando `True` `elseifcondition` se encuentra un objeto, se ejecutan las instrucciones inmediatamente después del objeto asociado `ElseIf` .</span><span class="sxs-lookup"><span data-stu-id="766f4-132">When a `True` `elseifcondition` is found, the statements immediately following the associated `ElseIf` are executed.</span></span> <span data-ttu-id="766f4-133">Si no `elseifcondition` se evalúa como `True` , o si no hay ninguna `ElseIf` instrucción, `Else` se ejecutan las instrucciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="766f4-133">If no `elseifcondition` evaluates to `True`, or if there are no `ElseIf` statements, the statements following `Else` are executed.</span></span> <span data-ttu-id="766f4-134">Después de ejecutar las instrucciones que `Then` siguen `ElseIf` a, o `Else` , la ejecución continúa con la instrucción que sigue a `End If` .</span><span class="sxs-lookup"><span data-stu-id="766f4-134">After executing the statements following `Then`, `ElseIf`, or `Else`, execution continues with the statement following `End If`.</span></span>

<span data-ttu-id="766f4-135">Las `ElseIf` `Else` cláusulas y son opcionales.</span><span class="sxs-lookup"><span data-stu-id="766f4-135">The `ElseIf` and `Else` clauses are both optional.</span></span> <span data-ttu-id="766f4-136">Puede tener tantas `ElseIf` cláusulas como desee en `If` ... `Then` ...`Else` , pero no `ElseIf` puede aparecer una cláusula después de una `Else` cláusula.</span><span class="sxs-lookup"><span data-stu-id="766f4-136">You can have as many `ElseIf` clauses as you want in an `If`...`Then`...`Else` statement, but no `ElseIf` clause can appear after an `Else` clause.</span></span> <span data-ttu-id="766f4-137">`If`...`Then` ...`Else` las instrucciones se pueden anidar unas dentro de otras.</span><span class="sxs-lookup"><span data-stu-id="766f4-137">`If`...`Then`...`Else` statements can be nested within each other.</span></span>

<span data-ttu-id="766f4-138">En la sintaxis de varias líneas, la `If` instrucción debe ser la única instrucción en la primera línea.</span><span class="sxs-lookup"><span data-stu-id="766f4-138">In the multiline syntax, the `If` statement must be the only statement on the first line.</span></span> <span data-ttu-id="766f4-139">Las `ElseIf` `Else` instrucciones, y `End If` solo pueden ir precedidas de una etiqueta de línea.</span><span class="sxs-lookup"><span data-stu-id="766f4-139">The `ElseIf`, `Else`, and `End If` statements can be preceded only by a line label.</span></span> <span data-ttu-id="766f4-140">`If`... `Then` ...`Else` el bloque debe terminar con una `End If` instrucción.</span><span class="sxs-lookup"><span data-stu-id="766f4-140">The `If`...`Then`...`Else` block must end with an `End If` statement.</span></span>

> [!TIP]
> <span data-ttu-id="766f4-141">La [selección... La instrucción Case](select-case-statement.md) podría ser más útil cuando se evalúa una expresión única que tiene varios valores posibles.</span><span class="sxs-lookup"><span data-stu-id="766f4-141">The [Select...Case Statement](select-case-statement.md) might be more useful when you evaluate a single expression that has several possible values.</span></span>

### <a name="single-line-syntax"></a><span data-ttu-id="766f4-142">Sintaxis de Single-Line</span><span class="sxs-lookup"><span data-stu-id="766f4-142">Single-Line syntax</span></span>

<span data-ttu-id="766f4-143">Puede usar la sintaxis de una sola línea para una única condición con el código que se ejecutará si es true.</span><span class="sxs-lookup"><span data-stu-id="766f4-143">You can use the single-line syntax for a single condition with code to execute if it's true.</span></span> <span data-ttu-id="766f4-144">Sin embargo, la sintaxis de varias líneas proporciona más estructura y flexibilidad y es más fácil de leer, mantener y depurar.</span><span class="sxs-lookup"><span data-stu-id="766f4-144">However, the multiple-line syntax provides more structure and flexibility and is easier to read, maintain, and debug.</span></span>

<span data-ttu-id="766f4-145">Lo que sigue `Then` a la palabra clave se examina para determinar si una instrucción es una sola línea `If` .</span><span class="sxs-lookup"><span data-stu-id="766f4-145">What follows the `Then` keyword is examined to determine whether a statement is a single-line `If`.</span></span> <span data-ttu-id="766f4-146">Si aparece cualquier cosa que no sea un comentario después `Then` de en la misma línea, la instrucción se trata como una instrucción de una sola línea `If` .</span><span class="sxs-lookup"><span data-stu-id="766f4-146">If anything other than a comment appears after `Then` on the same line, the statement is treated as a single-line `If` statement.</span></span> <span data-ttu-id="766f4-147">Si `Then` no está presente, debe ser el inicio de una `If` ... `Then` ...`Else`.</span><span class="sxs-lookup"><span data-stu-id="766f4-147">If `Then` is absent, it must be the start of a multiple-line `If`...`Then`...`Else`.</span></span>

<span data-ttu-id="766f4-148">En la sintaxis de una sola línea, se pueden ejecutar varias instrucciones como resultado de una `If` decisión... `Then` .</span><span class="sxs-lookup"><span data-stu-id="766f4-148">In the single-line syntax, you can have multiple statements executed as the result of an `If`...`Then` decision.</span></span> <span data-ttu-id="766f4-149">Todas las instrucciones deben estar en la misma línea y deben estar separadas por dos puntos.</span><span class="sxs-lookup"><span data-stu-id="766f4-149">All statements must be on the same line and be separated by colons.</span></span>

## <a name="multiline-syntax-example"></a><span data-ttu-id="766f4-150">Ejemplo de sintaxis de varias líneas</span><span class="sxs-lookup"><span data-stu-id="766f4-150">Multiline syntax example</span></span>

<a name="multi-line"></a>

<span data-ttu-id="766f4-151">En el ejemplo siguiente se muestra el uso de la sintaxis de varias líneas de `If` ... `Then` ...`Else` privacidad.</span><span class="sxs-lookup"><span data-stu-id="766f4-151">The following example illustrates the use of the multiline syntax of the `If`...`Then`...`Else` statement.</span></span>

[!code-vb[VbVbalrStatements#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#101)]

## <a name="nested-syntax-example"></a><span data-ttu-id="766f4-152">Ejemplo de sintaxis anidada</span><span class="sxs-lookup"><span data-stu-id="766f4-152">Nested syntax example</span></span>

<a name="nested"></a>

<span data-ttu-id="766f4-153">El ejemplo siguiente contiene anidado `If` ... `Then` ...`Else` afirma.</span><span class="sxs-lookup"><span data-stu-id="766f4-153">The following example contains nested `If`...`Then`...`Else` statements.</span></span>

[!code-vb[VbVbalrStatements#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#102)]

## <a name="single-line-syntax-example"></a><span data-ttu-id="766f4-154">Ejemplo de sintaxis de Single-Line</span><span class="sxs-lookup"><span data-stu-id="766f4-154">Single-Line syntax example</span></span>

<a name="single-line"></a> <span data-ttu-id="766f4-155">En el ejemplo siguiente se muestra el uso de la sintaxis de una sola línea.</span><span class="sxs-lookup"><span data-stu-id="766f4-155">The following example illustrates the use of the single-line syntax.</span></span>

[!code-vb[VbVbalrStatements#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#103)]

## <a name="see-also"></a><span data-ttu-id="766f4-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="766f4-156">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- <xref:Microsoft.VisualBasic.Interaction.Switch%2A>
- [<span data-ttu-id="766f4-157">#If...Then...#Else (directivas)</span><span class="sxs-lookup"><span data-stu-id="766f4-157">#If...Then...#Else Directives</span></span>](../directives/if-then-else-directives.md)
- [<span data-ttu-id="766f4-158">Instrucción Select...Case</span><span class="sxs-lookup"><span data-stu-id="766f4-158">Select...Case Statement</span></span>](select-case-statement.md)
- [<span data-ttu-id="766f4-159">Estructuras de control anidadas</span><span class="sxs-lookup"><span data-stu-id="766f4-159">Nested Control Structures</span></span>](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="766f4-160">Estructuras de decisión</span><span class="sxs-lookup"><span data-stu-id="766f4-160">Decision Structures</span></span>](../../programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="766f4-161">Operadores lógicos y bit a bit en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="766f4-161">Logical and Bitwise Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [<span data-ttu-id="766f4-162">Operador If</span><span class="sxs-lookup"><span data-stu-id="766f4-162">If Operator</span></span>](../operators/if-operator.md)
