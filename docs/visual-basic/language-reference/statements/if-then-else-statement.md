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
ms.openlocfilehash: d91a913d515f36a6b974850bc30079b000a919b4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58842699"
---
# <a name="ifthenelse-statement-visual-basic"></a><span data-ttu-id="5e5e3-102">Instrucción If...Then...Else (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5e5e3-102">If...Then...Else Statement (Visual Basic)</span></span>
<span data-ttu-id="5e5e3-103">Ejecuta condicionalmente un grupo de instrucciones en función del valor de una expresión.</span><span class="sxs-lookup"><span data-stu-id="5e5e3-103">Conditionally executes a group of statements, depending on the value of an expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e5e3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5e5e3-104">Syntax</span></span>  
  
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

## <a name="quick-links-to-example-code"></a><span data-ttu-id="5e5e3-105">Vínculos rápidos a código de ejemplo</span><span class="sxs-lookup"><span data-stu-id="5e5e3-105">Quick links to example code</span></span>

<span data-ttu-id="5e5e3-106">En este artículo incluye varios ejemplos que ilustran los usos de la `If`... `Then`... `Else` instrucción:</span><span class="sxs-lookup"><span data-stu-id="5e5e3-106">This article includes several examples that illustrate uses of the `If`...`Then`...`Else` statement:</span></span>

* [<span data-ttu-id="5e5e3-107">Ejemplo de sintaxis de varias líneas</span><span class="sxs-lookup"><span data-stu-id="5e5e3-107">Multiline syntax example</span></span>](#multi-line)
* [<span data-ttu-id="5e5e3-108">Ejemplo de sintaxis anidados</span><span class="sxs-lookup"><span data-stu-id="5e5e3-108">Nested syntax example</span></span>](#nested)
* [<span data-ttu-id="5e5e3-109">Ejemplo de sintaxis de línea</span><span class="sxs-lookup"><span data-stu-id="5e5e3-109">Single-line syntax example</span></span>](#single-line)

## <a name="parts"></a><span data-ttu-id="5e5e3-110">Elementos</span><span class="sxs-lookup"><span data-stu-id="5e5e3-110">Parts</span></span>  
 `condition`  
 <span data-ttu-id="5e5e3-111">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="5e5e3-111">Required.</span></span> <span data-ttu-id="5e5e3-112">expresión.</span><span class="sxs-lookup"><span data-stu-id="5e5e3-112">Expression.</span></span> <span data-ttu-id="5e5e3-113">Se debe evaluar como `True` o `False`, o a un tipo de datos que es implícitamente convertible a `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="5e5e3-113">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>  
  
 <span data-ttu-id="5e5e3-114">Si la expresión es un [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` variable que se evalúa como [nada](../../../visual-basic/language-reference/nothing.md), la condición se trata como si la expresión es `False` y `Else` bloque se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="5e5e3-114">If the expression is a [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` variable that evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the condition is treated as if the expression is `False` and the `Else` block is executed.</span></span>  
  
 `Then`  
 <span data-ttu-id="5e5e3-115">Necesario en la sintaxis de línea; opcional en la sintaxis de varias líneas.</span><span class="sxs-lookup"><span data-stu-id="5e5e3-115">Required in the single-line syntax; optional in the multiline syntax.</span></span>  
  
 `statements`  
 <span data-ttu-id="5e5e3-116">Opcional.</span><span class="sxs-lookup"><span data-stu-id="5e5e3-116">Optional.</span></span> <span data-ttu-id="5e5e3-117">Uno o más instrucciones que siguen `If`... `Then` que se ejecutan si `condition` se evalúa como `True`.</span><span class="sxs-lookup"><span data-stu-id="5e5e3-117">One or more statements following `If`...`Then` that are executed if `condition` evaluates to `True`.</span></span>  
  
 `elseifcondition`  
 <span data-ttu-id="5e5e3-118">Es necesario si `ElseIf` está presente.</span><span class="sxs-lookup"><span data-stu-id="5e5e3-118">Required if `ElseIf` is present.</span></span> <span data-ttu-id="5e5e3-119">expresión.</span><span class="sxs-lookup"><span data-stu-id="5e5e3-119">Expression.</span></span> <span data-ttu-id="5e5e3-120">Se debe evaluar como `True` o `False`, o a un tipo de datos que es implícitamente convertible a `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="5e5e3-120">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>  
  
 `elseifstatements`  
 <span data-ttu-id="5e5e3-121">Opcional.</span><span class="sxs-lookup"><span data-stu-id="5e5e3-121">Optional.</span></span> <span data-ttu-id="5e5e3-122">Uno o más instrucciones que siguen `ElseIf`... `Then` que se ejecutan si `elseifcondition` se evalúa como `True`.</span><span class="sxs-lookup"><span data-stu-id="5e5e3-122">One or more statements following `ElseIf`...`Then` that are executed if `elseifcondition` evaluates to `True`.</span></span>  
  
 `elsestatements`  
 <span data-ttu-id="5e5e3-123">Opcional.</span><span class="sxs-lookup"><span data-stu-id="5e5e3-123">Optional.</span></span> <span data-ttu-id="5e5e3-124">Una o varias instrucciones que se ejecutan si anterior no `condition` o `elseifcondition` expresión se evalúa como `True`.</span><span class="sxs-lookup"><span data-stu-id="5e5e3-124">One or more statements that are executed if no previous `condition` or `elseifcondition` expression evaluates to `True`.</span></span>  
  
 `End If`  
 <span data-ttu-id="5e5e3-125">Finaliza la versión multilínea del `If`... `Then`... `Else` bloque.</span><span class="sxs-lookup"><span data-stu-id="5e5e3-125">Terminates the multiline version of `If`...`Then`...`Else` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e5e3-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5e5e3-126">Remarks</span></span>  
  
### <a name="multiline-syntax"></a><span data-ttu-id="5e5e3-127">Sintaxis de varias líneas</span><span class="sxs-lookup"><span data-stu-id="5e5e3-127">Multiline syntax</span></span>  
 <span data-ttu-id="5e5e3-128">Cuando un `If`... `Then`... `Else` se encuentra la instrucción, `condition` está probando.</span><span class="sxs-lookup"><span data-stu-id="5e5e3-128">When an `If`...`Then`...`Else` statement is encountered, `condition` is tested.</span></span> <span data-ttu-id="5e5e3-129">Si `condition` es `True`, las instrucciones que siguen `Then` se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="5e5e3-129">If `condition` is `True`, the statements following `Then` are executed.</span></span> <span data-ttu-id="5e5e3-130">Si `condition` es `False`, cada `ElseIf` instrucción (si hay alguno) se evalúa en orden.</span><span class="sxs-lookup"><span data-stu-id="5e5e3-130">If `condition` is `False`, each `ElseIf` statement (if there are any) is evaluated in order.</span></span> <span data-ttu-id="5e5e3-131">Cuando un `True` `elseifcondition` se encuentra, las instrucciones que siguen inmediatamente asociado `ElseIf` se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="5e5e3-131">When a `True` `elseifcondition` is found, the statements immediately following the associated `ElseIf` are executed.</span></span> <span data-ttu-id="5e5e3-132">Si no hay ningún `elseifcondition` se evalúa como `True`, o si no hay ningún `ElseIf` instrucciones, las instrucciones que siguen `Else` se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="5e5e3-132">If no `elseifcondition` evaluates to `True`, or if there are no `ElseIf` statements, the statements following `Else` are executed.</span></span> <span data-ttu-id="5e5e3-133">Después de ejecutar las instrucciones que siguen `Then`, `ElseIf`, o `Else`, la ejecución continúa con la instrucción que sigue `End If`.</span><span class="sxs-lookup"><span data-stu-id="5e5e3-133">After executing the statements following `Then`, `ElseIf`, or `Else`, execution continues with the statement following `End If`.</span></span>  
  
 <span data-ttu-id="5e5e3-134">El `ElseIf` y `Else` cláusulas son opcionales.</span><span class="sxs-lookup"><span data-stu-id="5e5e3-134">The `ElseIf` and `Else` clauses are both optional.</span></span> <span data-ttu-id="5e5e3-135">Puede tener tantos `ElseIf` cláusulas como desean en un `If`... `Then`... `Else` instrucción, pero no `ElseIf` puede aparecer una cláusula después de un `Else` cláusula.</span><span class="sxs-lookup"><span data-stu-id="5e5e3-135">You can have as many `ElseIf` clauses as you want in an `If`...`Then`...`Else` statement, but no `ElseIf` clause can appear after an `Else` clause.</span></span> <span data-ttu-id="5e5e3-136">`If`... `Then`... `Else` instrucciones pueden anidarse dentro de otros.</span><span class="sxs-lookup"><span data-stu-id="5e5e3-136">`If`...`Then`...`Else` statements can be nested within each other.</span></span>  
  
 <span data-ttu-id="5e5e3-137">En la sintaxis de varias líneas, el `If` instrucción debe ser la única instrucción en la primera línea.</span><span class="sxs-lookup"><span data-stu-id="5e5e3-137">In the multiline syntax, the `If` statement must be the only statement on the first line.</span></span> <span data-ttu-id="5e5e3-138">El `ElseIf`, `Else`, y `End If` instrucciones pueden ir precedidas solamente por una etiqueta de línea.</span><span class="sxs-lookup"><span data-stu-id="5e5e3-138">The `ElseIf`, `Else`, and `End If` statements can be preceded only by a line label.</span></span> <span data-ttu-id="5e5e3-139">El `If`... `Then`... `Else` bloque debe terminar con un `End If` instrucción.</span><span class="sxs-lookup"><span data-stu-id="5e5e3-139">The `If`...`Then`...`Else` block must end with an `End If` statement.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="5e5e3-140">El [seleccione... Instrucción de caso](../../../visual-basic/language-reference/statements/select-case-statement.md) podría ser más útil al evaluar una expresión única que tiene varios valores posibles.</span><span class="sxs-lookup"><span data-stu-id="5e5e3-140">The [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) might be more useful when you evaluate a single expression that has several possible values.</span></span>  
  
### <a name="single-line-syntax"></a><span data-ttu-id="5e5e3-141">Sintaxis de línea</span><span class="sxs-lookup"><span data-stu-id="5e5e3-141">Single-Line syntax</span></span>  
 <span data-ttu-id="5e5e3-142">Puede usar la sintaxis de línea para una única condición con el código que se ejecutarán si es true.</span><span class="sxs-lookup"><span data-stu-id="5e5e3-142">You can use the single-line syntax for a single condition with code to execute if it's true.</span></span> <span data-ttu-id="5e5e3-143">Sin embargo, la sintaxis de varias líneas proporciona más estructura y la flexibilidad y es más fácil de leer, mantener y depurar.</span><span class="sxs-lookup"><span data-stu-id="5e5e3-143">However, the multiple-line syntax provides more structure and flexibility and is easier to read, maintain, and debug.</span></span>  
  
 <span data-ttu-id="5e5e3-144">A continuación se la `Then` palabra clave se examina para determinar si la instrucción es una sola línea `If`.</span><span class="sxs-lookup"><span data-stu-id="5e5e3-144">What follows the `Then` keyword is examined to determine whether a statement is a single-line `If`.</span></span> <span data-ttu-id="5e5e3-145">Si algo distinto de un comentario aparece después `Then` en la misma línea, la instrucción se trata como una sola línea `If` instrucción.</span><span class="sxs-lookup"><span data-stu-id="5e5e3-145">If anything other than a comment appears after `Then` on the same line, the statement is treated as a single-line `If` statement.</span></span> <span data-ttu-id="5e5e3-146">Si `Then` no está presente, debe ser el inicio de varias líneas `If`... `Then`... `Else`.</span><span class="sxs-lookup"><span data-stu-id="5e5e3-146">If `Then` is absent, it must be the start of a multiple-line `If`...`Then`...`Else`.</span></span>  
  
 <span data-ttu-id="5e5e3-147">En la sintaxis de línea única, puede tener varias instrucciones ejecutadas como resultado de un `If`... `Then` decisión.</span><span class="sxs-lookup"><span data-stu-id="5e5e3-147">In the single-line syntax, you can have multiple statements executed as the result of an `If`...`Then` decision.</span></span> <span data-ttu-id="5e5e3-148">Todas las instrucciones deben estar en la misma línea y estar separadas por signos de dos puntos.</span><span class="sxs-lookup"><span data-stu-id="5e5e3-148">All statements must be on the same line and be separated by colons.</span></span>  

## <a name="multiline-syntax-example"></a><span data-ttu-id="5e5e3-149">Ejemplo de sintaxis de varias líneas</span><span class="sxs-lookup"><span data-stu-id="5e5e3-149">Multiline syntax example</span></span>

<a name="multi-line"></a>
 
 <span data-ttu-id="5e5e3-150">El ejemplo siguiente muestra el uso de la sintaxis de varias líneas de la `If`... `Then`... `Else` instrucción.</span><span class="sxs-lookup"><span data-stu-id="5e5e3-150">The following example illustrates the use of the multiline syntax of the `If`...`Then`...`Else` statement.</span></span>  
  
 [!code-vb[VbVbalrStatements#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#101)]

## <a name="nested-syntax-example"></a><span data-ttu-id="5e5e3-151">Ejemplo de sintaxis anidados</span><span class="sxs-lookup"><span data-stu-id="5e5e3-151">Nested syntax example</span></span>

<a name="nested"></a>

 <span data-ttu-id="5e5e3-152">El ejemplo siguiente contiene anidada `If`... `Then`... `Else` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="5e5e3-152">The following example contains nested `If`...`Then`...`Else` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#102)]

## <a name="single-line-syntax-example"></a><span data-ttu-id="5e5e3-153">Ejemplo de sintaxis de línea</span><span class="sxs-lookup"><span data-stu-id="5e5e3-153">Single-Line syntax example</span></span>
  
<a name="single-line"></a> <span data-ttu-id="5e5e3-154">El ejemplo siguiente muestra el uso de la sintaxis de línea.</span><span class="sxs-lookup"><span data-stu-id="5e5e3-154">The following example illustrates the use of the single-line syntax.</span></span>  
  
 [!code-vb[VbVbalrStatements#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#103)]
  
## <a name="see-also"></a><span data-ttu-id="5e5e3-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e5e3-155">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- <xref:Microsoft.VisualBasic.Interaction.Switch%2A>
- [<span data-ttu-id="5e5e3-156">#If...Then...#Else (directivas)</span><span class="sxs-lookup"><span data-stu-id="5e5e3-156">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="5e5e3-157">Select...Case (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5e5e3-157">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [<span data-ttu-id="5e5e3-158">Estructuras de control anidadas</span><span class="sxs-lookup"><span data-stu-id="5e5e3-158">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="5e5e3-159">Estructuras de decisión</span><span class="sxs-lookup"><span data-stu-id="5e5e3-159">Decision Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="5e5e3-160">Operadores lógicos y bit a bit en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5e5e3-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [<span data-ttu-id="5e5e3-161">If (operador)</span><span class="sxs-lookup"><span data-stu-id="5e5e3-161">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
