---
description: 'Más información sobre: Exit Statement (Visual Basic)'
title: Instrucción Exit
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
ms.openlocfilehash: 54af7fbf908dbad829cf6f08bf442dfe85e35610
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99769134"
---
# <a name="exit-statement-visual-basic"></a><span data-ttu-id="bb772-103">Exit (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bb772-103">Exit Statement (Visual Basic)</span></span>

<span data-ttu-id="bb772-104">Sale de un procedimiento o un bloque y transfiere el control inmediatamente a la instrucción que sigue a la llamada al procedimiento o la definición del bloque.</span><span class="sxs-lookup"><span data-stu-id="bb772-104">Exits a procedure or block and transfers control immediately to the statement following the procedure call or the block definition.</span></span>

## <a name="syntax"></a><span data-ttu-id="bb772-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bb772-105">Syntax</span></span>

```vb
Exit { Do | For | Function | Property | Select | Sub | Try | While }
```

## <a name="statements"></a><span data-ttu-id="bb772-106">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="bb772-106">Statements</span></span>

 `Exit Do`  
 <span data-ttu-id="bb772-107">Sale inmediatamente del `Do` bucle en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="bb772-107">Immediately exits the `Do` loop in which it appears.</span></span> <span data-ttu-id="bb772-108">La ejecución continúa con la instrucción que sigue a la `Loop` instrucción.</span><span class="sxs-lookup"><span data-stu-id="bb772-108">Execution continues with the statement following the `Loop` statement.</span></span> <span data-ttu-id="bb772-109">`Exit Do` solo se puede usar dentro de un `Do` bucle.</span><span class="sxs-lookup"><span data-stu-id="bb772-109">`Exit Do` can be used only inside a `Do` loop.</span></span> <span data-ttu-id="bb772-110">Cuando se usa dentro de `Do` bucles anidados, `Exit Do` sale del bucle más interno y transfiere el control al siguiente nivel superior de anidamiento.</span><span class="sxs-lookup"><span data-stu-id="bb772-110">When used within nested `Do` loops, `Exit Do` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>

 `Exit For`  
 <span data-ttu-id="bb772-111">Sale inmediatamente del `For` bucle en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="bb772-111">Immediately exits the `For` loop in which it appears.</span></span> <span data-ttu-id="bb772-112">La ejecución continúa con la instrucción que sigue a la `Next` instrucción.</span><span class="sxs-lookup"><span data-stu-id="bb772-112">Execution continues with the statement following the `Next` statement.</span></span> <span data-ttu-id="bb772-113">`Exit For` solo se puede usar dentro de un `For` bucle... `Next` o `For Each` ... `Next` .</span><span class="sxs-lookup"><span data-stu-id="bb772-113">`Exit For` can be used only inside a `For`...`Next` or `For Each`...`Next` loop.</span></span> <span data-ttu-id="bb772-114">Cuando se usa dentro de `For` bucles anidados, `Exit For` sale del bucle más interno y transfiere el control al siguiente nivel superior de anidamiento.</span><span class="sxs-lookup"><span data-stu-id="bb772-114">When used within nested `For` loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>

 `Exit Function`  
 <span data-ttu-id="bb772-115">Sale inmediatamente del `Function` procedimiento en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="bb772-115">Immediately exits the `Function` procedure in which it appears.</span></span> <span data-ttu-id="bb772-116">La ejecución continúa con la instrucción que sigue a la instrucción que llamó al `Function` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="bb772-116">Execution continues with the statement following the statement that called the `Function` procedure.</span></span> <span data-ttu-id="bb772-117">`Exit Function` solo se puede usar dentro de un `Function` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="bb772-117">`Exit Function` can be used only inside a `Function` procedure.</span></span>

 <span data-ttu-id="bb772-118">Para especificar un valor devuelto, puede asignar el valor al nombre de la función en una línea antes de la `Exit Function` instrucción.</span><span class="sxs-lookup"><span data-stu-id="bb772-118">To specify a return value, you can assign the value to the function name on a line before the `Exit Function` statement.</span></span> <span data-ttu-id="bb772-119">Para asignar el valor devuelto y salir de la función en una instrucción, en su lugar puede usar la [instrucción return](return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="bb772-119">To assign the return value and exit the function in one statement, you can instead use the [Return Statement](return-statement.md).</span></span>

 `Exit Property`  
 <span data-ttu-id="bb772-120">Sale inmediatamente del `Property` procedimiento en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="bb772-120">Immediately exits the `Property` procedure in which it appears.</span></span> <span data-ttu-id="bb772-121">La ejecución continúa con la instrucción que llamó al `Property` procedimiento, es decir, con la instrucción que solicita o establece el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="bb772-121">Execution continues with the statement that called the `Property` procedure, that is, with the statement requesting or setting the property's value.</span></span> <span data-ttu-id="bb772-122">`Exit Property` solo se puede usar dentro del procedimiento o de una propiedad `Get` `Set` .</span><span class="sxs-lookup"><span data-stu-id="bb772-122">`Exit Property` can be used only inside a property's `Get` or `Set` procedure.</span></span>

 <span data-ttu-id="bb772-123">Para especificar un valor devuelto en un `Get` procedimiento, puede asignar el valor al nombre de la función en una línea antes de la `Exit Property` instrucción.</span><span class="sxs-lookup"><span data-stu-id="bb772-123">To specify a return value in a `Get` procedure, you can assign the value to the function name on a line before the `Exit Property` statement.</span></span> <span data-ttu-id="bb772-124">Para asignar el valor devuelto y salir del `Get` procedimiento en una instrucción, en su lugar puede usar la `Return` instrucción.</span><span class="sxs-lookup"><span data-stu-id="bb772-124">To assign the return value and exit the `Get` procedure in one statement, you can instead use the `Return` statement.</span></span>

 <span data-ttu-id="bb772-125">En un `Set` procedimiento, la `Exit Property` instrucción es equivalente a la `Return` instrucción.</span><span class="sxs-lookup"><span data-stu-id="bb772-125">In a `Set` procedure, the `Exit Property` statement is equivalent to the `Return` statement.</span></span>

 `Exit Select`  
 <span data-ttu-id="bb772-126">Sale inmediatamente del `Select Case` bloque en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="bb772-126">Immediately exits the `Select Case` block in which it appears.</span></span> <span data-ttu-id="bb772-127">La ejecución continúa con la instrucción que sigue a la `End Select` instrucción.</span><span class="sxs-lookup"><span data-stu-id="bb772-127">Execution continues with the statement following the `End Select` statement.</span></span> <span data-ttu-id="bb772-128">`Exit Select` solo se puede utilizar dentro de una `Select Case` instrucción.</span><span class="sxs-lookup"><span data-stu-id="bb772-128">`Exit Select` can be used only inside a `Select Case` statement.</span></span>

 `Exit Sub`  
 <span data-ttu-id="bb772-129">Sale inmediatamente del `Sub` procedimiento en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="bb772-129">Immediately exits the `Sub` procedure in which it appears.</span></span> <span data-ttu-id="bb772-130">La ejecución continúa con la instrucción que sigue a la instrucción que llamó al `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="bb772-130">Execution continues with the statement following the statement that called the `Sub` procedure.</span></span> <span data-ttu-id="bb772-131">`Exit Sub` solo se puede usar dentro de un `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="bb772-131">`Exit Sub` can be used only inside a `Sub` procedure.</span></span>

 <span data-ttu-id="bb772-132">En un `Sub` procedimiento, la `Exit Sub` instrucción es equivalente a la `Return` instrucción.</span><span class="sxs-lookup"><span data-stu-id="bb772-132">In a `Sub` procedure, the `Exit Sub` statement is equivalent to the `Return` statement.</span></span>

 `Exit Try`  
 <span data-ttu-id="bb772-133">Sale inmediatamente del `Try` bloque o `Catch` en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="bb772-133">Immediately exits the `Try` or `Catch` block in which it appears.</span></span> <span data-ttu-id="bb772-134">La ejecución continúa con el `Finally` bloque, si hay alguno, o con la instrucción que sigue a la `End Try` instrucción de lo contrario.</span><span class="sxs-lookup"><span data-stu-id="bb772-134">Execution continues with the `Finally` block if there is one, or with the statement following the `End Try` statement otherwise.</span></span> <span data-ttu-id="bb772-135">`Exit Try` solo se puede usar dentro de `Try` un `Catch` bloque o, y no dentro de un `Finally` bloque.</span><span class="sxs-lookup"><span data-stu-id="bb772-135">`Exit Try` can be used only inside a `Try` or `Catch` block, and not inside a `Finally` block.</span></span>

 `Exit While`  
 <span data-ttu-id="bb772-136">Sale inmediatamente del `While` bucle en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="bb772-136">Immediately exits the `While` loop in which it appears.</span></span> <span data-ttu-id="bb772-137">La ejecución continúa con la instrucción que sigue a la `End While` instrucción.</span><span class="sxs-lookup"><span data-stu-id="bb772-137">Execution continues with the statement following the `End While` statement.</span></span> <span data-ttu-id="bb772-138">`Exit While` solo se puede usar dentro de un `While` bucle.</span><span class="sxs-lookup"><span data-stu-id="bb772-138">`Exit While` can be used only inside a `While` loop.</span></span> <span data-ttu-id="bb772-139">Cuando se usa dentro de `While` bucles anidados, `Exit While` transfiere el control al bucle que está un nivel anidado por encima del bucle en el que `Exit While` se produce.</span><span class="sxs-lookup"><span data-stu-id="bb772-139">When used within nested `While` loops, `Exit While` transfers control to the loop that is one nested level above the loop where `Exit While` occurs.</span></span>

## <a name="remarks"></a><span data-ttu-id="bb772-140">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bb772-140">Remarks</span></span>

<span data-ttu-id="bb772-141">No confunda `Exit` instrucciones con `End` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="bb772-141">Do not confuse `Exit` statements with `End` statements.</span></span> <span data-ttu-id="bb772-142">`Exit` no define el final de una instrucción.</span><span class="sxs-lookup"><span data-stu-id="bb772-142">`Exit` does not define the end of a statement.</span></span>

## <a name="example"></a><span data-ttu-id="bb772-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bb772-143">Example</span></span>

<span data-ttu-id="bb772-144">En el ejemplo siguiente, la condición de bucle detiene el bucle cuando la `index` variable es mayor que 100.</span><span class="sxs-lookup"><span data-stu-id="bb772-144">In the following example, the loop condition stops the loop when the `index` variable is greater than 100.</span></span> <span data-ttu-id="bb772-145">La `If` instrucción del bucle, sin embargo, hace que la `Exit Do` instrucción detenga el bucle cuando la variable de índice es mayor que 10.</span><span class="sxs-lookup"><span data-stu-id="bb772-145">The `If` statement in the loop, however, causes the `Exit Do` statement to stop the loop when the index variable is greater than 10.</span></span>

[!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]

## <a name="example"></a><span data-ttu-id="bb772-146">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bb772-146">Example</span></span>

<span data-ttu-id="bb772-147">En el ejemplo siguiente se asigna el valor devuelto al nombre de la función `myFunction` y, a continuación, `Exit Function` se usa para devolver de la función:</span><span class="sxs-lookup"><span data-stu-id="bb772-147">The following example assigns the return value to the function name `myFunction`, and then uses `Exit Function` to return from the function:</span></span>

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

## <a name="example"></a><span data-ttu-id="bb772-148">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bb772-148">Example</span></span>

<span data-ttu-id="bb772-149">En el ejemplo siguiente se usa la [instrucción return](return-statement.md) para asignar el valor devuelto y salir de la función:</span><span class="sxs-lookup"><span data-stu-id="bb772-149">The following example uses the [Return Statement](return-statement.md) to assign the return value and exit the function:</span></span>

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

## <a name="see-also"></a><span data-ttu-id="bb772-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb772-150">See also</span></span>

- [<span data-ttu-id="bb772-151">Continue (instrucción)</span><span class="sxs-lookup"><span data-stu-id="bb772-151">Continue Statement</span></span>](continue-statement.md)
- [<span data-ttu-id="bb772-152">Instrucción Do...Loop</span><span class="sxs-lookup"><span data-stu-id="bb772-152">Do...Loop Statement</span></span>](do-loop-statement.md)
- [<span data-ttu-id="bb772-153">End (instrucción)</span><span class="sxs-lookup"><span data-stu-id="bb772-153">End Statement</span></span>](end-statement.md)
- [<span data-ttu-id="bb772-154">Instrucción For Each...Next</span><span class="sxs-lookup"><span data-stu-id="bb772-154">For Each...Next Statement</span></span>](for-each-next-statement.md)
- [<span data-ttu-id="bb772-155">Instrucción For...Next</span><span class="sxs-lookup"><span data-stu-id="bb772-155">For...Next Statement</span></span>](for-next-statement.md)
- [<span data-ttu-id="bb772-156">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="bb772-156">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="bb772-157">Instrucción Return</span><span class="sxs-lookup"><span data-stu-id="bb772-157">Return Statement</span></span>](return-statement.md)
- [<span data-ttu-id="bb772-158">Instrucción Stop</span><span class="sxs-lookup"><span data-stu-id="bb772-158">Stop Statement</span></span>](stop-statement.md)
- [<span data-ttu-id="bb772-159">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="bb772-159">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="bb772-160">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="bb772-160">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
