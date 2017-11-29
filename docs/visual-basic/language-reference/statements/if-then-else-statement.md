---
title: "Instrucción If...Then...Else (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "29"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 898b72055345e88ca35f805de211c0c57cd74200
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ifthenelse-statement-visual-basic"></a><span data-ttu-id="5300b-102">Instrucción If...Then...Else (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5300b-102">If...Then...Else Statement (Visual Basic)</span></span>
<span data-ttu-id="5300b-103">Ejecuta condicionalmente un grupo de instrucciones en función del valor de una expresión.</span><span class="sxs-lookup"><span data-stu-id="5300b-103">Conditionally executes a group of statements, depending on the value of an expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5300b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5300b-104">Syntax</span></span>  
  
```  
' Multiple-line syntax:  
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
  
## <a name="parts"></a><span data-ttu-id="5300b-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="5300b-105">Parts</span></span>  
 `condition`  
 <span data-ttu-id="5300b-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="5300b-106">Required.</span></span> <span data-ttu-id="5300b-107">Expresión.</span><span class="sxs-lookup"><span data-stu-id="5300b-107">Expression.</span></span> <span data-ttu-id="5300b-108">Se debe evaluar como `True` o `False`, o a un tipo de datos que es implícitamente convertible a `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="5300b-108">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>  
  
 <span data-ttu-id="5300b-109">Si la expresión es un [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` variable que se evalúa como [nada](../../../visual-basic/language-reference/nothing.md), la condición se trata como si la expresión no es `True`y el `Else` bloque es ejecutar.</span><span class="sxs-lookup"><span data-stu-id="5300b-109">If the expression is a [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)`Boolean` variable that evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the condition is treated as if the expression is not `True`, and the `Else` block is executed.</span></span>  
  
 `Then`  
 <span data-ttu-id="5300b-110">Requerido en la sintaxis de línea; opcional en la sintaxis de varias líneas.</span><span class="sxs-lookup"><span data-stu-id="5300b-110">Required in the single-line syntax; optional in the multiple-line syntax.</span></span>  
  
 `statements`  
 <span data-ttu-id="5300b-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="5300b-111">Optional.</span></span> <span data-ttu-id="5300b-112">Uno o más instrucciones que siguen `If`... `Then` que se ejecutan si `condition` se evalúa como `True`.</span><span class="sxs-lookup"><span data-stu-id="5300b-112">One or more statements following `If`...`Then` that are executed if `condition` evaluates to `True`.</span></span>  
  
 `elseifcondition`  
 <span data-ttu-id="5300b-113">Obligatorio si `ElseIf` está presente.</span><span class="sxs-lookup"><span data-stu-id="5300b-113">Required if `ElseIf` is present.</span></span> <span data-ttu-id="5300b-114">Expresión.</span><span class="sxs-lookup"><span data-stu-id="5300b-114">Expression.</span></span> <span data-ttu-id="5300b-115">Se debe evaluar como `True` o `False`, o a un tipo de datos que es implícitamente convertible a `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="5300b-115">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>  
  
 `elseifstatements`  
 <span data-ttu-id="5300b-116">Opcional.</span><span class="sxs-lookup"><span data-stu-id="5300b-116">Optional.</span></span> <span data-ttu-id="5300b-117">Uno o más instrucciones que siguen `ElseIf`... `Then` que se ejecutan si `elseifcondition` se evalúa como `True`.</span><span class="sxs-lookup"><span data-stu-id="5300b-117">One or more statements following `ElseIf`...`Then` that are executed if `elseifcondition` evaluates to `True`.</span></span>  
  
 `elsestatements`  
 <span data-ttu-id="5300b-118">Opcional.</span><span class="sxs-lookup"><span data-stu-id="5300b-118">Optional.</span></span> <span data-ttu-id="5300b-119">Una o más instrucciones que se ejecutan si anterior ya no `condition` o `elseifcondition` expresión se evalúa como `True`.</span><span class="sxs-lookup"><span data-stu-id="5300b-119">One or more statements that are executed if no previous `condition` or `elseifcondition` expression evaluates to `True`.</span></span>  
  
 `End If`  
 <span data-ttu-id="5300b-120">Finaliza el `If`... `Then`... `Else` bloque.</span><span class="sxs-lookup"><span data-stu-id="5300b-120">Terminates the `If`...`Then`...`Else` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5300b-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5300b-121">Remarks</span></span>  
  
## <a name="multiple-line-syntax"></a><span data-ttu-id="5300b-122">Sintaxis de varias líneas</span><span class="sxs-lookup"><span data-stu-id="5300b-122">Multiple-Line Syntax</span></span>  
 <span data-ttu-id="5300b-123">Cuando un `If`... `Then`... `Else` se encuentra la instrucción, `condition` se ha probado.</span><span class="sxs-lookup"><span data-stu-id="5300b-123">When an `If`...`Then`...`Else` statement is encountered, `condition` is tested.</span></span> <span data-ttu-id="5300b-124">Si `condition` es `True`, las instrucciones que siguen `Then` se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="5300b-124">If `condition` is `True`, the statements following `Then` are executed.</span></span> <span data-ttu-id="5300b-125">Si `condition` es `False`, cada `ElseIf` instrucción (si hay alguno) se evalúa en orden.</span><span class="sxs-lookup"><span data-stu-id="5300b-125">If `condition` is `False`, each `ElseIf` statement (if there are any) is evaluated in order.</span></span> <span data-ttu-id="5300b-126">Cuando un `True``elseifcondition` se encuentra, las instrucciones que siguen inmediatamente asociado `ElseIf` se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="5300b-126">When a `True``elseifcondition` is found, the statements immediately following the associated `ElseIf` are executed.</span></span> <span data-ttu-id="5300b-127">Si no hay ningún `elseifcondition` se evalúa como `True`, o si no hay ningún `ElseIf` las instrucciones que siguen, instrucciones `Else` se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="5300b-127">If no `elseifcondition` evaluates to `True`, or if there are no `ElseIf` statements, the statements following `Else` are executed.</span></span> <span data-ttu-id="5300b-128">Después de ejecutar las instrucciones que siguen `Then`, `ElseIf`, o `Else`, la ejecución continúa con la siguiente instrucción `End If`.</span><span class="sxs-lookup"><span data-stu-id="5300b-128">After executing the statements following `Then`, `ElseIf`, or `Else`, execution continues with the statement following `End If`.</span></span>  
  
 <span data-ttu-id="5300b-129">El `ElseIf` y `Else` cláusulas son opcionales.</span><span class="sxs-lookup"><span data-stu-id="5300b-129">The `ElseIf` and `Else` clauses are both optional.</span></span> <span data-ttu-id="5300b-130">Puede tener tantos `ElseIf` cláusulas como desee en un `If`... `Then`... `Else` instrucción, pero no `ElseIf` cláusula puede aparecer después de un `Else` cláusula.</span><span class="sxs-lookup"><span data-stu-id="5300b-130">You can have as many `ElseIf` clauses as you want in an `If`...`Then`...`Else` statement, but no `ElseIf` clause can appear after an `Else` clause.</span></span> <span data-ttu-id="5300b-131">`If`... `Then`... `Else` instrucciones pueden anidarse dentro de otros.</span><span class="sxs-lookup"><span data-stu-id="5300b-131">`If`...`Then`...`Else` statements can be nested within each other.</span></span>  
  
 <span data-ttu-id="5300b-132">En la sintaxis de varias líneas, el `If` instrucción debe ser la única instrucción en la primera línea.</span><span class="sxs-lookup"><span data-stu-id="5300b-132">In the multiple-line syntax, the `If` statement must be the only statement on the first line.</span></span> <span data-ttu-id="5300b-133">El `ElseIf`, `Else`, y `End If` instrucciones pueden ir precedidas solamente por una etiqueta de línea.</span><span class="sxs-lookup"><span data-stu-id="5300b-133">The `ElseIf`, `Else`, and `End If` statements can be preceded only by a line label.</span></span> <span data-ttu-id="5300b-134">El `If`... `Then`... `Else` bloque debe terminar con un `End If` instrucción.</span><span class="sxs-lookup"><span data-stu-id="5300b-134">The `If`...`Then`...`Else` block must end with an `End If` statement.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="5300b-135">El [seleccione... Caso instrucción](../../../visual-basic/language-reference/statements/select-case-statement.md) podrían ser más útiles cuando se evalúa una expresión única que tiene varios valores posibles.</span><span class="sxs-lookup"><span data-stu-id="5300b-135">The [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) might be more useful when you evaluate a single expression that has several possible values.</span></span>  
  
## <a name="single-line-syntax"></a><span data-ttu-id="5300b-136">Sintaxis de línea</span><span class="sxs-lookup"><span data-stu-id="5300b-136">Single-Line Syntax</span></span>  
 <span data-ttu-id="5300b-137">Puede utilizar la sintaxis de línea para pruebas cortas y sencillas.</span><span class="sxs-lookup"><span data-stu-id="5300b-137">You can use the single-line syntax for short, simple tests.</span></span> <span data-ttu-id="5300b-138">Sin embargo, la sintaxis de varias líneas proporciona más estructura y flexibilidad y normalmente es más fácil leer, mantener y depurar.</span><span class="sxs-lookup"><span data-stu-id="5300b-138">However, the multiple-line syntax provides more structure and flexibility and is usually easier to read, maintain, and debug.</span></span>  
  
 <span data-ttu-id="5300b-139">A continuación el `Then` palabra clave se examina para determinar si la instrucción es una sola línea `If`.</span><span class="sxs-lookup"><span data-stu-id="5300b-139">What follows the `Then` keyword is examined to determine whether a statement is a single-line `If`.</span></span> <span data-ttu-id="5300b-140">Si algo distinto de un comentario aparece después de `Then` en la misma línea, la instrucción se trata como una sola línea `If` instrucción.</span><span class="sxs-lookup"><span data-stu-id="5300b-140">If anything other than a comment appears after `Then` on the same line, the statement is treated as a single-line `If` statement.</span></span> <span data-ttu-id="5300b-141">Si `Then` no está presente, debe ser el inicio de varias líneas `If`... `Then`... `Else`.</span><span class="sxs-lookup"><span data-stu-id="5300b-141">If `Then` is absent, it must be the start of a multiple-line `If`...`Then`...`Else`.</span></span>  
  
 <span data-ttu-id="5300b-142">En la sintaxis de línea, puede tener varias instrucciones que se ejecuta como resultado de un `If`... `Then` decisión.</span><span class="sxs-lookup"><span data-stu-id="5300b-142">In the single-line syntax, you can have multiple statements executed as the result of an `If`...`Then` decision.</span></span> <span data-ttu-id="5300b-143">Todas las instrucciones deben estar en la misma línea y estar separadas por signos de dos puntos.</span><span class="sxs-lookup"><span data-stu-id="5300b-143">All statements must be on the same line and be separated by colons.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5300b-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5300b-144">Example</span></span>  
 <span data-ttu-id="5300b-145">En el ejemplo siguiente se muestra el uso de la sintaxis de varias líneas de la `If`... `Then`... `Else` instrucción.</span><span class="sxs-lookup"><span data-stu-id="5300b-145">The following example illustrates the use of the multiple-line syntax of the `If`...`Then`...`Else` statement.</span></span>  
  
 [!code-vb[VbVbalrStatements#101](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="5300b-146">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5300b-146">Example</span></span>  
 <span data-ttu-id="5300b-147">El ejemplo siguiente contiene anidada `If`... `Then`... `Else` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="5300b-147">The following example contains nested `If`...`Then`...`Else` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#102](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="5300b-148">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5300b-148">Example</span></span>  
 <span data-ttu-id="5300b-149">En el ejemplo siguiente se muestra el uso de la sintaxis de línea.</span><span class="sxs-lookup"><span data-stu-id="5300b-149">The following example illustrates the use of the single-line syntax.</span></span>  
  
 [!code-vb[VbVbalrStatements#103](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="5300b-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="5300b-150">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Interaction.Choose%2A>  
 <xref:Microsoft.VisualBasic.Interaction.Switch%2A>  
 [<span data-ttu-id="5300b-151">#If...Then...#Else (directivas)</span><span class="sxs-lookup"><span data-stu-id="5300b-151">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [<span data-ttu-id="5300b-152">Select...Case (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5300b-152">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)  
 [<span data-ttu-id="5300b-153">Estructuras de control anidadas</span><span class="sxs-lookup"><span data-stu-id="5300b-153">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="5300b-154">Estructuras de decisión</span><span class="sxs-lookup"><span data-stu-id="5300b-154">Decision Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [<span data-ttu-id="5300b-155">Operadores lógicos y bit a bit en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5300b-155">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)  
 [<span data-ttu-id="5300b-156">If (operador)</span><span class="sxs-lookup"><span data-stu-id="5300b-156">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
