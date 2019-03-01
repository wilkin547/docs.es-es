---
title: Exit (Instrucción, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Exit
helpviewer_keywords:
- execution [Visual Basic], ending
- files [Visual Basic], closing
- programs [Visual Basic], quitting
- code, exiting
- Exit statement [Visual Basic]
- program termination
- execution [Visual Basic], stopping
ms.assetid: 760bfb32-5c3f-4bdb-a432-9a6001c92db7
ms.openlocfilehash: e08d436686876a0a3d63f15167d35383e32221e7
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967807"
---
# <a name="exit-statement-visual-basic"></a><span data-ttu-id="5562f-102">Exit (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5562f-102">Exit Statement (Visual Basic)</span></span>
<span data-ttu-id="5562f-103">Se cierra un procedimiento o bloque y transfiere el control inmediatamente a la instrucción siguiente a la llamada al procedimiento o la definición del bloque.</span><span class="sxs-lookup"><span data-stu-id="5562f-103">Exits a procedure or block and transfers control immediately to the statement following the procedure call or the block definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5562f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5562f-104">Syntax</span></span>  
  
```  
Exit { Do | For | Function | Property | Select | Sub | Try | While }  
```  
  
## <a name="statements"></a><span data-ttu-id="5562f-105">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="5562f-105">Statements</span></span>  
 `Exit Do`  
 <span data-ttu-id="5562f-106">Inmediatamente después cierra el `Do` bucle en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="5562f-106">Immediately exits the `Do` loop in which it appears.</span></span> <span data-ttu-id="5562f-107">La ejecución continúa con la instrucción que sigue la `Loop` instrucción.</span><span class="sxs-lookup"><span data-stu-id="5562f-107">Execution continues with the statement following the `Loop` statement.</span></span> <span data-ttu-id="5562f-108">`Exit Do` se puede usar solo dentro de un `Do` bucle.</span><span class="sxs-lookup"><span data-stu-id="5562f-108">`Exit Do` can be used only inside a `Do` loop.</span></span> <span data-ttu-id="5562f-109">Cuando se usa en anidados `Do` bucles, `Exit Do` sale del bucle más interno y transfiere el control al siguiente nivel más alto de anidamiento.</span><span class="sxs-lookup"><span data-stu-id="5562f-109">When used within nested `Do` loops, `Exit Do` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>  
  
 `Exit For`  
 <span data-ttu-id="5562f-110">Inmediatamente después cierra el `For` bucle en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="5562f-110">Immediately exits the `For` loop in which it appears.</span></span> <span data-ttu-id="5562f-111">La ejecución continúa con la instrucción que sigue la `Next` instrucción.</span><span class="sxs-lookup"><span data-stu-id="5562f-111">Execution continues with the statement following the `Next` statement.</span></span> <span data-ttu-id="5562f-112">`Exit For` se puede usar solo dentro de un `For`... `Next` o `For Each`... `Next` bucle.</span><span class="sxs-lookup"><span data-stu-id="5562f-112">`Exit For` can be used only inside a `For`...`Next` or `For Each`...`Next` loop.</span></span> <span data-ttu-id="5562f-113">Cuando se usa en anidados `For` bucles, `Exit For` sale del bucle más interno y transfiere el control al siguiente nivel más alto de anidamiento.</span><span class="sxs-lookup"><span data-stu-id="5562f-113">When used within nested `For` loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>  
  
 `Exit Function`  
 <span data-ttu-id="5562f-114">Inmediatamente después cierra el `Function` procedimiento en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="5562f-114">Immediately exits the `Function` procedure in which it appears.</span></span> <span data-ttu-id="5562f-115">La ejecución continúa con la instrucción que sigue a la instrucción que llama el `Function` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="5562f-115">Execution continues with the statement following the statement that called the `Function` procedure.</span></span> <span data-ttu-id="5562f-116">`Exit Function` se puede usar solo dentro de un `Function` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="5562f-116">`Exit Function` can be used only inside a `Function` procedure.</span></span>  
  
 <span data-ttu-id="5562f-117">Para especificar un valor devuelto, puede asignar el valor al nombre de función en una línea antes de la `Exit Function` instrucción.</span><span class="sxs-lookup"><span data-stu-id="5562f-117">To specify a return value, you can assign the value to the function name on a line before the `Exit Function` statement.</span></span> <span data-ttu-id="5562f-118">Para asignar el valor devuelto y salir de la función en una sola instrucción, puede usar en su lugar el [instrucción Return](../../../visual-basic/language-reference/statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="5562f-118">To assign the return value and exit the function in one statement, you can instead use the [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
 `Exit Property`  
 <span data-ttu-id="5562f-119">Inmediatamente después cierra el `Property` procedimiento en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="5562f-119">Immediately exits the `Property` procedure in which it appears.</span></span> <span data-ttu-id="5562f-120">La ejecución continúa con la instrucción que llama el `Property` procedimiento, es decir, con la instrucción que solicita o establece el valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="5562f-120">Execution continues with the statement that called the `Property` procedure, that is, with the statement requesting or setting the property's value.</span></span> <span data-ttu-id="5562f-121">`Exit Property` se puede usar solo dentro de una propiedad `Get` o `Set` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="5562f-121">`Exit Property` can be used only inside a property's `Get` or `Set` procedure.</span></span>  
  
 <span data-ttu-id="5562f-122">Para especificar un valor devuelto en un `Get` procedimiento, puede asignar el valor al nombre de función en una línea antes de la `Exit Property` instrucción.</span><span class="sxs-lookup"><span data-stu-id="5562f-122">To specify a return value in a `Get` procedure, you can assign the value to the function name on a line before the `Exit Property` statement.</span></span> <span data-ttu-id="5562f-123">Para asignar el valor devuelto y salir del `Get` procedimiento en una sola instrucción, puede usar en su lugar el `Return` instrucción.</span><span class="sxs-lookup"><span data-stu-id="5562f-123">To assign the return value and exit the `Get` procedure in one statement, you can instead use the `Return` statement.</span></span>  
  
 <span data-ttu-id="5562f-124">En un `Set` procedimiento, el `Exit Property` instrucción es equivalente a la `Return` instrucción.</span><span class="sxs-lookup"><span data-stu-id="5562f-124">In a `Set` procedure, the `Exit Property` statement is equivalent to the `Return` statement.</span></span>  
  
 `Exit Select`  
 <span data-ttu-id="5562f-125">Inmediatamente después cierra el `Select Case` bloque en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="5562f-125">Immediately exits the `Select Case` block in which it appears.</span></span> <span data-ttu-id="5562f-126">La ejecución continúa con la instrucción que sigue la `End Select` instrucción.</span><span class="sxs-lookup"><span data-stu-id="5562f-126">Execution continues with the statement following the `End Select` statement.</span></span> <span data-ttu-id="5562f-127">`Exit Select` se puede usar solo dentro de un `Select Case` instrucción.</span><span class="sxs-lookup"><span data-stu-id="5562f-127">`Exit Select` can be used only inside a `Select Case` statement.</span></span>  
  
 `Exit Sub`  
 <span data-ttu-id="5562f-128">Inmediatamente después cierra el `Sub` procedimiento en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="5562f-128">Immediately exits the `Sub` procedure in which it appears.</span></span> <span data-ttu-id="5562f-129">La ejecución continúa con la instrucción que sigue a la instrucción que llama el `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="5562f-129">Execution continues with the statement following the statement that called the `Sub` procedure.</span></span> <span data-ttu-id="5562f-130">`Exit Sub` se puede usar solo dentro de un `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="5562f-130">`Exit Sub` can be used only inside a `Sub` procedure.</span></span>  
  
 <span data-ttu-id="5562f-131">En un `Sub` procedimiento, el `Exit Sub` instrucción es equivalente a la `Return` instrucción.</span><span class="sxs-lookup"><span data-stu-id="5562f-131">In a `Sub` procedure, the `Exit Sub` statement is equivalent to the `Return` statement.</span></span>  
  
 `Exit Try`  
 <span data-ttu-id="5562f-132">Inmediatamente después cierra el `Try` o `Catch` bloque en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="5562f-132">Immediately exits the `Try` or `Catch` block in which it appears.</span></span> <span data-ttu-id="5562f-133">La ejecución continúa con la `Finally` bloquear si hay alguno, o con la instrucción que sigue la `End Try` instrucción en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="5562f-133">Execution continues with the `Finally` block if there is one, or with the statement following the `End Try` statement otherwise.</span></span> <span data-ttu-id="5562f-134">`Exit Try` se puede usar solo dentro de un `Try` o `Catch` bloque y no dentro un `Finally` bloque.</span><span class="sxs-lookup"><span data-stu-id="5562f-134">`Exit Try` can be used only inside a `Try` or `Catch` block, and not inside a `Finally` block.</span></span>  
  
 `Exit While`  
 <span data-ttu-id="5562f-135">Inmediatamente después cierra el `While` bucle en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="5562f-135">Immediately exits the `While` loop in which it appears.</span></span> <span data-ttu-id="5562f-136">La ejecución continúa con la instrucción que sigue la `End While` instrucción.</span><span class="sxs-lookup"><span data-stu-id="5562f-136">Execution continues with the statement following the `End While` statement.</span></span> <span data-ttu-id="5562f-137">`Exit While` se puede usar solo dentro de un `While` bucle.</span><span class="sxs-lookup"><span data-stu-id="5562f-137">`Exit While` can be used only inside a `While` loop.</span></span> <span data-ttu-id="5562f-138">Cuando se usa dentro de anidar `While` bucles, `Exit While` transfiere el control al bucle que está anidado y un nivel por encima del bucle donde `Exit While` se produce.</span><span class="sxs-lookup"><span data-stu-id="5562f-138">When used within nested `While` loops, `Exit While` transfers control to the loop that is one nested level above the loop where `Exit While` occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5562f-139">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5562f-139">Remarks</span></span>  
 <span data-ttu-id="5562f-140">No confunda `Exit` instrucciones con `End` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="5562f-140">Do not confuse `Exit` statements with `End` statements.</span></span> <span data-ttu-id="5562f-141">`Exit` no se define el final de una instrucción.</span><span class="sxs-lookup"><span data-stu-id="5562f-141">`Exit` does not define the end of a statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5562f-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5562f-142">Example</span></span>  
 <span data-ttu-id="5562f-143">En el ejemplo siguiente, la condición del bucle detiene el bucle cuando la `index` variable es mayor que 100.</span><span class="sxs-lookup"><span data-stu-id="5562f-143">In the following example, the loop condition stops the loop when the `index` variable is greater than 100.</span></span> <span data-ttu-id="5562f-144">El `If` instrucción del bucle, sin embargo, hace que el `Exit Do` instrucción para detener el bucle cuando la variable de índice es mayor que 10.</span><span class="sxs-lookup"><span data-stu-id="5562f-144">The `If` statement in the loop, however, causes the `Exit Do` statement to stop the loop when the index variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]  
  
## <a name="example"></a><span data-ttu-id="5562f-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5562f-145">Example</span></span>  
 <span data-ttu-id="5562f-146">En el ejemplo siguiente se asigna el valor devuelto para el nombre de función `myFunction`y, a continuación, usa `Exit Function` para devolver de la función.</span><span class="sxs-lookup"><span data-stu-id="5562f-146">The following example assigns the return value to the function name `myFunction`, and then uses `Exit Function` to return from the function.</span></span>  
  
 [!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]  
  
## <a name="example"></a><span data-ttu-id="5562f-147">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5562f-147">Example</span></span>  
 <span data-ttu-id="5562f-148">En el ejemplo siguiente se usa el [instrucción Return](../../../visual-basic/language-reference/statements/return-statement.md) para asignar el valor devuelto y salir de la función.</span><span class="sxs-lookup"><span data-stu-id="5562f-148">The following example uses the [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) to assign the return value and exit the function.</span></span>  
  
 [!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]  
  
## <a name="see-also"></a><span data-ttu-id="5562f-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="5562f-149">See also</span></span>
- [<span data-ttu-id="5562f-150">Continue (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5562f-150">Continue Statement</span></span>](../../../visual-basic/language-reference/statements/continue-statement.md)
- [<span data-ttu-id="5562f-151">Do...Loop (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5562f-151">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="5562f-152">End (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5562f-152">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
- [<span data-ttu-id="5562f-153">For Each...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5562f-153">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="5562f-154">For...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5562f-154">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="5562f-155">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5562f-155">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="5562f-156">Return (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5562f-156">Return Statement</span></span>](../../../visual-basic/language-reference/statements/return-statement.md)
- [<span data-ttu-id="5562f-157">Stop (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5562f-157">Stop Statement</span></span>](../../../visual-basic/language-reference/statements/stop-statement.md)
- [<span data-ttu-id="5562f-158">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5562f-158">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="5562f-159">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5562f-159">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
