---
title: Instrucción If...Then...Else (Visual Basic)
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
ms.openlocfilehash: 97ac8c82df14eb5ddc5e26fdaddf61cc774a0476
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046569"
---
# <a name="ifthenelse-statement-visual-basic"></a><span data-ttu-id="85125-102">Instrucción If...Then...Else (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="85125-102">If...Then...Else Statement (Visual Basic)</span></span>

<span data-ttu-id="85125-103">Ejecuta condicionalmente un grupo de instrucciones en función del valor de una expresión.</span><span class="sxs-lookup"><span data-stu-id="85125-103">Conditionally executes a group of statements, depending on the value of an expression.</span></span>

## <a name="syntax"></a><span data-ttu-id="85125-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="85125-104">Syntax</span></span>

```
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

## <a name="quick-links-to-example-code"></a><span data-ttu-id="85125-105">Vínculos rápidos a código de ejemplo</span><span class="sxs-lookup"><span data-stu-id="85125-105">Quick links to example code</span></span>

<span data-ttu-id="85125-106">En este artículo se incluyen varios ejemplos que muestran los `If`usos de... `Then`... `Else` instrucción:</span><span class="sxs-lookup"><span data-stu-id="85125-106">This article includes several examples that illustrate uses of the `If`...`Then`...`Else` statement:</span></span>

* [<span data-ttu-id="85125-107">Ejemplo de sintaxis de varias líneas</span><span class="sxs-lookup"><span data-stu-id="85125-107">Multiline syntax example</span></span>](#multi-line)
* [<span data-ttu-id="85125-108">Ejemplo de sintaxis anidada</span><span class="sxs-lookup"><span data-stu-id="85125-108">Nested syntax example</span></span>](#nested)
* [<span data-ttu-id="85125-109">Ejemplo de sintaxis de una sola línea</span><span class="sxs-lookup"><span data-stu-id="85125-109">Single-line syntax example</span></span>](#single-line)

## <a name="parts"></a><span data-ttu-id="85125-110">Elementos</span><span class="sxs-lookup"><span data-stu-id="85125-110">Parts</span></span>

`condition` \
<span data-ttu-id="85125-111">Necesario.</span><span class="sxs-lookup"><span data-stu-id="85125-111">Required.</span></span> <span data-ttu-id="85125-112">Expresiones.</span><span class="sxs-lookup"><span data-stu-id="85125-112">Expression.</span></span> <span data-ttu-id="85125-113">Debe evaluarse `True` como `False`o, o en un tipo de datos que se pueda convertir `Boolean`implícitamente en.</span><span class="sxs-lookup"><span data-stu-id="85125-113">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>

<span data-ttu-id="85125-114">Si la expresión es una `Boolean` variable que [acepta valores NULL](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `False` y que se evalúa como [Nothing](../../../visual-basic/language-reference/nothing.md), la condición se trata como si la expresión fuese y se ejecuta el `Else` bloque.</span><span class="sxs-lookup"><span data-stu-id="85125-114">If the expression is a [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` variable that evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the condition is treated as if the expression is `False` and the `Else` block is executed.</span></span>

`Then` \
<span data-ttu-id="85125-115">Requerido en la sintaxis de una sola línea; opcional en la sintaxis de varias líneas.</span><span class="sxs-lookup"><span data-stu-id="85125-115">Required in the single-line syntax; optional in the multiline syntax.</span></span>

`statements` \
<span data-ttu-id="85125-116">Opcional.</span><span class="sxs-lookup"><span data-stu-id="85125-116">Optional.</span></span> <span data-ttu-id="85125-117">Una o más instrucciones que `If`siguen a... que se ejecutan `condition` si se evalúa `True`como. `Then`</span><span class="sxs-lookup"><span data-stu-id="85125-117">One or more statements following `If`...`Then` that are executed if `condition` evaluates to `True`.</span></span>

`elseifcondition` \
<span data-ttu-id="85125-118">Obligatorio si `ElseIf` está presente.</span><span class="sxs-lookup"><span data-stu-id="85125-118">Required if `ElseIf` is present.</span></span> <span data-ttu-id="85125-119">Expresiones.</span><span class="sxs-lookup"><span data-stu-id="85125-119">Expression.</span></span> <span data-ttu-id="85125-120">Debe evaluarse `True` como `False`o, o en un tipo de datos que se pueda convertir `Boolean`implícitamente en.</span><span class="sxs-lookup"><span data-stu-id="85125-120">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>

`elseifstatements` \
<span data-ttu-id="85125-121">Opcional.</span><span class="sxs-lookup"><span data-stu-id="85125-121">Optional.</span></span> <span data-ttu-id="85125-122">Una o más instrucciones que `ElseIf`siguen a... que se ejecutan `elseifcondition` si se evalúa `True`como. `Then`</span><span class="sxs-lookup"><span data-stu-id="85125-122">One or more statements following `ElseIf`...`Then` that are executed if `elseifcondition` evaluates to `True`.</span></span>

`elsestatements` \
<span data-ttu-id="85125-123">Opcional.</span><span class="sxs-lookup"><span data-stu-id="85125-123">Optional.</span></span> <span data-ttu-id="85125-124">Una o varias instrucciones que se ejecutan si ninguna `condition` expresión `elseifcondition` or anterior se evalúa `True`como.</span><span class="sxs-lookup"><span data-stu-id="85125-124">One or more statements that are executed if no previous `condition` or `elseifcondition` expression evaluates to `True`.</span></span>

`End If` \
<span data-ttu-id="85125-125">Finaliza la versión multilínea de `If`... `Then`... `Else` bloque.</span><span class="sxs-lookup"><span data-stu-id="85125-125">Terminates the multiline version of `If`...`Then`...`Else` block.</span></span>

## <a name="remarks"></a><span data-ttu-id="85125-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="85125-126">Remarks</span></span>

### <a name="multiline-syntax"></a><span data-ttu-id="85125-127">Sintaxis de varias líneas</span><span class="sxs-lookup"><span data-stu-id="85125-127">Multiline syntax</span></span>

<span data-ttu-id="85125-128">`If`Cuando... `Then`... la instrucción se ha `condition` encontrado, se ha probado. `Else`</span><span class="sxs-lookup"><span data-stu-id="85125-128">When an `If`...`Then`...`Else` statement is encountered, `condition` is tested.</span></span> <span data-ttu-id="85125-129">Si `condition` `Then` es `True`, se ejecutan las instrucciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="85125-129">If `condition` is `True`, the statements following `Then` are executed.</span></span> <span data-ttu-id="85125-130">Si `condition` es `False`, cada`ElseIf` instrucción (si hay alguna) se evalúa en orden.</span><span class="sxs-lookup"><span data-stu-id="85125-130">If `condition` is `False`, each `ElseIf` statement (if there are any) is evaluated in order.</span></span> <span data-ttu-id="85125-131">Cuando se `True` encuentra un `elseifcondition` objeto, se ejecutan las instrucciones `ElseIf` inmediatamente después del objeto asociado.</span><span class="sxs-lookup"><span data-stu-id="85125-131">When a `True` `elseifcondition` is found, the statements immediately following the associated `ElseIf` are executed.</span></span> <span data-ttu-id="85125-132">Si no `elseifcondition` se evalúa `True`como, o si no hay ninguna `ElseIf` instrucción, se ejecutan `Else` las instrucciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="85125-132">If no `elseifcondition` evaluates to `True`, or if there are no `ElseIf` statements, the statements following `Else` are executed.</span></span> <span data-ttu-id="85125-133">Después de ejecutar las instrucciones que `Then`siguen `ElseIf`a, `Else`o, la ejecución continúa con la `End If`instrucción que sigue a.</span><span class="sxs-lookup"><span data-stu-id="85125-133">After executing the statements following `Then`, `ElseIf`, or `Else`, execution continues with the statement following `End If`.</span></span>

<span data-ttu-id="85125-134">Las `ElseIf` cláusulas y `Else` son opcionales.</span><span class="sxs-lookup"><span data-stu-id="85125-134">The `ElseIf` and `Else` clauses are both optional.</span></span> <span data-ttu-id="85125-135">Puede tener tantas `ElseIf` cláusulas como desee `If`en... `Then`... , pero no `ElseIf` puede aparecer una cláusula después de `Else` una cláusula. `Else`</span><span class="sxs-lookup"><span data-stu-id="85125-135">You can have as many `ElseIf` clauses as you want in an `If`...`Then`...`Else` statement, but no `ElseIf` clause can appear after an `Else` clause.</span></span> <span data-ttu-id="85125-136">`If`... `Then`... `Else` las instrucciones se pueden anidar unas dentro de otras.</span><span class="sxs-lookup"><span data-stu-id="85125-136">`If`...`Then`...`Else` statements can be nested within each other.</span></span>

<span data-ttu-id="85125-137">En la sintaxis de varias líneas `If` , la instrucción debe ser la única instrucción en la primera línea.</span><span class="sxs-lookup"><span data-stu-id="85125-137">In the multiline syntax, the `If` statement must be the only statement on the first line.</span></span> <span data-ttu-id="85125-138">Las `ElseIf`instrucciones `Else`, y`End If` solo pueden ir precedidas de una etiqueta de línea.</span><span class="sxs-lookup"><span data-stu-id="85125-138">The `ElseIf`, `Else`, and `End If` statements can be preceded only by a line label.</span></span> <span data-ttu-id="85125-139">`If`... `Then`... el bloque debe terminar con `End If` una instrucción. `Else`</span><span class="sxs-lookup"><span data-stu-id="85125-139">The `If`...`Then`...`Else` block must end with an `End If` statement.</span></span>

> [!TIP]
> <span data-ttu-id="85125-140">La [selección... La instrucción Case](../../../visual-basic/language-reference/statements/select-case-statement.md) podría ser más útil cuando se evalúa una expresión única que tiene varios valores posibles.</span><span class="sxs-lookup"><span data-stu-id="85125-140">The [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) might be more useful when you evaluate a single expression that has several possible values.</span></span>

### <a name="single-line-syntax"></a><span data-ttu-id="85125-141">Sintaxis de una sola línea</span><span class="sxs-lookup"><span data-stu-id="85125-141">Single-Line syntax</span></span>

<span data-ttu-id="85125-142">Puede usar la sintaxis de una sola línea para una única condición con el código que se ejecutará si es true.</span><span class="sxs-lookup"><span data-stu-id="85125-142">You can use the single-line syntax for a single condition with code to execute if it's true.</span></span> <span data-ttu-id="85125-143">Sin embargo, la sintaxis de varias líneas proporciona más estructura y flexibilidad y es más fácil de leer, mantener y depurar.</span><span class="sxs-lookup"><span data-stu-id="85125-143">However, the multiple-line syntax provides more structure and flexibility and is easier to read, maintain, and debug.</span></span>

<span data-ttu-id="85125-144">Lo que sigue `Then` a la palabra clave se examina para determinar si una instrucción es una `If`sola línea.</span><span class="sxs-lookup"><span data-stu-id="85125-144">What follows the `Then` keyword is examined to determine whether a statement is a single-line `If`.</span></span> <span data-ttu-id="85125-145">Si aparece cualquier cosa que no sea un `Then` comentario después de en la misma línea, la instrucción se trata como una `If` instrucción de una sola línea.</span><span class="sxs-lookup"><span data-stu-id="85125-145">If anything other than a comment appears after `Then` on the same line, the statement is treated as a single-line `If` statement.</span></span> <span data-ttu-id="85125-146">Si `Then` no está presente, debe ser el inicio de una `If`... `Then`... `Else`.</span><span class="sxs-lookup"><span data-stu-id="85125-146">If `Then` is absent, it must be the start of a multiple-line `If`...`Then`...`Else`.</span></span>

<span data-ttu-id="85125-147">En la sintaxis de una sola línea, se pueden ejecutar varias instrucciones como resultado de `If`... `Then` decisión.</span><span class="sxs-lookup"><span data-stu-id="85125-147">In the single-line syntax, you can have multiple statements executed as the result of an `If`...`Then` decision.</span></span> <span data-ttu-id="85125-148">Todas las instrucciones deben estar en la misma línea y deben estar separadas por dos puntos.</span><span class="sxs-lookup"><span data-stu-id="85125-148">All statements must be on the same line and be separated by colons.</span></span>

## <a name="multiline-syntax-example"></a><span data-ttu-id="85125-149">Ejemplo de sintaxis de varias líneas</span><span class="sxs-lookup"><span data-stu-id="85125-149">Multiline syntax example</span></span>

<a name="multi-line"></a>

<span data-ttu-id="85125-150">En el ejemplo siguiente se muestra el uso de la sintaxis de varias `If`líneas de... `Then`... `Else` instrucción.</span><span class="sxs-lookup"><span data-stu-id="85125-150">The following example illustrates the use of the multiline syntax of the `If`...`Then`...`Else` statement.</span></span>

[!code-vb[VbVbalrStatements#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#101)]

## <a name="nested-syntax-example"></a><span data-ttu-id="85125-151">Ejemplo de sintaxis anidada</span><span class="sxs-lookup"><span data-stu-id="85125-151">Nested syntax example</span></span>

<a name="nested"></a>

<span data-ttu-id="85125-152">El ejemplo siguiente contiene anidado `If`... `Then`... `Else` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="85125-152">The following example contains nested `If`...`Then`...`Else` statements.</span></span>

[!code-vb[VbVbalrStatements#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#102)]

## <a name="single-line-syntax-example"></a><span data-ttu-id="85125-153">Ejemplo de sintaxis de una sola línea</span><span class="sxs-lookup"><span data-stu-id="85125-153">Single-Line syntax example</span></span>

<a name="single-line"></a><span data-ttu-id="85125-154">En el ejemplo siguiente se muestra el uso de la sintaxis de una sola línea.</span><span class="sxs-lookup"><span data-stu-id="85125-154">The following example illustrates the use of the single-line syntax.</span></span>

[!code-vb[VbVbalrStatements#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#103)]

## <a name="see-also"></a><span data-ttu-id="85125-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="85125-155">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- <xref:Microsoft.VisualBasic.Interaction.Switch%2A>
- [<span data-ttu-id="85125-156">#If...Then...#Else (directivas)</span><span class="sxs-lookup"><span data-stu-id="85125-156">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="85125-157">Select...Case (instrucción)</span><span class="sxs-lookup"><span data-stu-id="85125-157">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [<span data-ttu-id="85125-158">Estructuras de control anidadas</span><span class="sxs-lookup"><span data-stu-id="85125-158">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="85125-159">Estructuras de decisión</span><span class="sxs-lookup"><span data-stu-id="85125-159">Decision Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="85125-160">Operadores lógicos y bit a bit en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="85125-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [<span data-ttu-id="85125-161">If (operador)</span><span class="sxs-lookup"><span data-stu-id="85125-161">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
