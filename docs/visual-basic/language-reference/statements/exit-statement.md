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
ms.openlocfilehash: 9c25653809c51662ea5b606ab97be6a9b50d5986
ms.sourcegitcommit: 7bfe1682d9368cf88d43e895d1e80ba2d88c3a99
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2019
ms.locfileid: "71956944"
---
# <a name="exit-statement-visual-basic"></a><span data-ttu-id="91cfb-102">Exit (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="91cfb-102">Exit Statement (Visual Basic)</span></span>

<span data-ttu-id="91cfb-103">Sale de un procedimiento o un bloque y transfiere el control inmediatamente a la instrucción que sigue a la llamada al procedimiento o la definición del bloque.</span><span class="sxs-lookup"><span data-stu-id="91cfb-103">Exits a procedure or block and transfers control immediately to the statement following the procedure call or the block definition.</span></span>

## <a name="syntax"></a><span data-ttu-id="91cfb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="91cfb-104">Syntax</span></span>

```vb
Exit { Do | For | Function | Property | Select | Sub | Try | While }
```

## <a name="statements"></a><span data-ttu-id="91cfb-105">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="91cfb-105">Statements</span></span>

 `Exit Do`  
 <span data-ttu-id="91cfb-106">Sale inmediatamente del bucle `Do` en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="91cfb-106">Immediately exits the `Do` loop in which it appears.</span></span> <span data-ttu-id="91cfb-107">La ejecución continúa con la instrucción que sigue a la instrucción `Loop`.</span><span class="sxs-lookup"><span data-stu-id="91cfb-107">Execution continues with the statement following the `Loop` statement.</span></span> <span data-ttu-id="91cfb-108">`Exit Do` solo se puede usar dentro de un bucle `Do`.</span><span class="sxs-lookup"><span data-stu-id="91cfb-108">`Exit Do` can be used only inside a `Do` loop.</span></span> <span data-ttu-id="91cfb-109">Cuando se usa dentro de bucles `Do` anidados, `Exit Do` sale del bucle más interno y transfiere el control al siguiente nivel superior de anidamiento.</span><span class="sxs-lookup"><span data-stu-id="91cfb-109">When used within nested `Do` loops, `Exit Do` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>

 `Exit For`  
 <span data-ttu-id="91cfb-110">Sale inmediatamente del bucle `For` en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="91cfb-110">Immediately exits the `For` loop in which it appears.</span></span> <span data-ttu-id="91cfb-111">La ejecución continúa con la instrucción que sigue a la instrucción `Next`.</span><span class="sxs-lookup"><span data-stu-id="91cfb-111">Execution continues with the statement following the `Next` statement.</span></span> <span data-ttu-id="91cfb-112">`Exit For` solo se puede usar dentro de un bucle `For`... `Next` o `For Each`... `Next`.</span><span class="sxs-lookup"><span data-stu-id="91cfb-112">`Exit For` can be used only inside a `For`...`Next` or `For Each`...`Next` loop.</span></span> <span data-ttu-id="91cfb-113">Cuando se usa dentro de bucles `For` anidados, `Exit For` sale del bucle más interno y transfiere el control al siguiente nivel superior de anidamiento.</span><span class="sxs-lookup"><span data-stu-id="91cfb-113">When used within nested `For` loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>

 `Exit Function`  
 <span data-ttu-id="91cfb-114">Sale inmediatamente del procedimiento `Function` en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="91cfb-114">Immediately exits the `Function` procedure in which it appears.</span></span> <span data-ttu-id="91cfb-115">La ejecución continúa con la instrucción que sigue a la instrucción que llamó al procedimiento `Function`.</span><span class="sxs-lookup"><span data-stu-id="91cfb-115">Execution continues with the statement following the statement that called the `Function` procedure.</span></span> <span data-ttu-id="91cfb-116">`Exit Function` solo se puede usar dentro de un procedimiento `Function`.</span><span class="sxs-lookup"><span data-stu-id="91cfb-116">`Exit Function` can be used only inside a `Function` procedure.</span></span>

 <span data-ttu-id="91cfb-117">Para especificar un valor devuelto, puede asignar el valor al nombre de la función en una línea antes de la instrucción `Exit Function`.</span><span class="sxs-lookup"><span data-stu-id="91cfb-117">To specify a return value, you can assign the value to the function name on a line before the `Exit Function` statement.</span></span> <span data-ttu-id="91cfb-118">Para asignar el valor devuelto y salir de la función en una instrucción, en su lugar puede usar la [instrucción return](return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="91cfb-118">To assign the return value and exit the function in one statement, you can instead use the [Return Statement](return-statement.md).</span></span>

 `Exit Property`  
 <span data-ttu-id="91cfb-119">Sale inmediatamente del procedimiento `Property` en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="91cfb-119">Immediately exits the `Property` procedure in which it appears.</span></span> <span data-ttu-id="91cfb-120">La ejecución continúa con la instrucción que llamó al procedimiento `Property`, es decir, con la instrucción que solicita o establece el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="91cfb-120">Execution continues with the statement that called the `Property` procedure, that is, with the statement requesting or setting the property's value.</span></span> <span data-ttu-id="91cfb-121">`Exit Property` solo se puede usar dentro del procedimiento `Get` o `Set` de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="91cfb-121">`Exit Property` can be used only inside a property's `Get` or `Set` procedure.</span></span>

 <span data-ttu-id="91cfb-122">Para especificar un valor devuelto en un procedimiento `Get`, puede asignar el valor al nombre de la función en una línea antes de la instrucción `Exit Property`.</span><span class="sxs-lookup"><span data-stu-id="91cfb-122">To specify a return value in a `Get` procedure, you can assign the value to the function name on a line before the `Exit Property` statement.</span></span> <span data-ttu-id="91cfb-123">Para asignar el valor devuelto y salir del procedimiento `Get` en una instrucción, puede usar en su lugar la instrucción `Return`.</span><span class="sxs-lookup"><span data-stu-id="91cfb-123">To assign the return value and exit the `Get` procedure in one statement, you can instead use the `Return` statement.</span></span>

 <span data-ttu-id="91cfb-124">En un procedimiento `Set`, la instrucción `Exit Property` es equivalente a la instrucción `Return`.</span><span class="sxs-lookup"><span data-stu-id="91cfb-124">In a `Set` procedure, the `Exit Property` statement is equivalent to the `Return` statement.</span></span>

 `Exit Select`  
 <span data-ttu-id="91cfb-125">Sale inmediatamente del bloque `Select Case` en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="91cfb-125">Immediately exits the `Select Case` block in which it appears.</span></span> <span data-ttu-id="91cfb-126">La ejecución continúa con la instrucción que sigue a la instrucción `End Select`.</span><span class="sxs-lookup"><span data-stu-id="91cfb-126">Execution continues with the statement following the `End Select` statement.</span></span> <span data-ttu-id="91cfb-127">`Exit Select` solo se puede usar dentro de una instrucción `Select Case`.</span><span class="sxs-lookup"><span data-stu-id="91cfb-127">`Exit Select` can be used only inside a `Select Case` statement.</span></span>

 `Exit Sub`  
 <span data-ttu-id="91cfb-128">Sale inmediatamente del procedimiento `Sub` en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="91cfb-128">Immediately exits the `Sub` procedure in which it appears.</span></span> <span data-ttu-id="91cfb-129">La ejecución continúa con la instrucción que sigue a la instrucción que llamó al procedimiento `Sub`.</span><span class="sxs-lookup"><span data-stu-id="91cfb-129">Execution continues with the statement following the statement that called the `Sub` procedure.</span></span> <span data-ttu-id="91cfb-130">`Exit Sub` solo se puede usar dentro de un procedimiento `Sub`.</span><span class="sxs-lookup"><span data-stu-id="91cfb-130">`Exit Sub` can be used only inside a `Sub` procedure.</span></span>

 <span data-ttu-id="91cfb-131">En un procedimiento `Sub`, la instrucción `Exit Sub` es equivalente a la instrucción `Return`.</span><span class="sxs-lookup"><span data-stu-id="91cfb-131">In a `Sub` procedure, the `Exit Sub` statement is equivalent to the `Return` statement.</span></span>

 `Exit Try`  
 <span data-ttu-id="91cfb-132">Sale inmediatamente del bloque `Try` o `Catch` en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="91cfb-132">Immediately exits the `Try` or `Catch` block in which it appears.</span></span> <span data-ttu-id="91cfb-133">La ejecución continúa con el bloque `Finally`, si hay alguno, o con la instrucción que sigue a la instrucción `End Try` en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="91cfb-133">Execution continues with the `Finally` block if there is one, or with the statement following the `End Try` statement otherwise.</span></span> <span data-ttu-id="91cfb-134">`Exit Try` solo se puede usar dentro de un bloque `Try` o `Catch` y no dentro de un bloque `Finally`.</span><span class="sxs-lookup"><span data-stu-id="91cfb-134">`Exit Try` can be used only inside a `Try` or `Catch` block, and not inside a `Finally` block.</span></span>

 `Exit While`  
 <span data-ttu-id="91cfb-135">Sale inmediatamente del bucle `While` en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="91cfb-135">Immediately exits the `While` loop in which it appears.</span></span> <span data-ttu-id="91cfb-136">La ejecución continúa con la instrucción que sigue a la instrucción `End While`.</span><span class="sxs-lookup"><span data-stu-id="91cfb-136">Execution continues with the statement following the `End While` statement.</span></span> <span data-ttu-id="91cfb-137">`Exit While` solo se puede usar dentro de un bucle `While`.</span><span class="sxs-lookup"><span data-stu-id="91cfb-137">`Exit While` can be used only inside a `While` loop.</span></span> <span data-ttu-id="91cfb-138">Cuando se usa en bucles `While` anidados, `Exit While` transfiere el control al bucle que está un nivel anidado por encima del bucle donde se produce `Exit While`.</span><span class="sxs-lookup"><span data-stu-id="91cfb-138">When used within nested `While` loops, `Exit While` transfers control to the loop that is one nested level above the loop where `Exit While` occurs.</span></span>

## <a name="remarks"></a><span data-ttu-id="91cfb-139">Comentarios</span><span class="sxs-lookup"><span data-stu-id="91cfb-139">Remarks</span></span>

<span data-ttu-id="91cfb-140">No confunda las instrucciones `Exit` con las instrucciones `End`.</span><span class="sxs-lookup"><span data-stu-id="91cfb-140">Do not confuse `Exit` statements with `End` statements.</span></span> <span data-ttu-id="91cfb-141">`Exit` no define el final de una instrucción.</span><span class="sxs-lookup"><span data-stu-id="91cfb-141">`Exit` does not define the end of a statement.</span></span>

## <a name="example"></a><span data-ttu-id="91cfb-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="91cfb-142">Example</span></span>

<span data-ttu-id="91cfb-143">En el ejemplo siguiente, la condición de bucle detiene el bucle cuando la variable `index` es mayor que 100.</span><span class="sxs-lookup"><span data-stu-id="91cfb-143">In the following example, the loop condition stops the loop when the `index` variable is greater than 100.</span></span> <span data-ttu-id="91cfb-144">La instrucción `If` del bucle, sin embargo, hace que la instrucción `Exit Do` detenga el bucle cuando la variable de índice sea mayor que 10.</span><span class="sxs-lookup"><span data-stu-id="91cfb-144">The `If` statement in the loop, however, causes the `Exit Do` statement to stop the loop when the index variable is greater than 10.</span></span>

[!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]

## <a name="example"></a><span data-ttu-id="91cfb-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="91cfb-145">Example</span></span>

<span data-ttu-id="91cfb-146">En el ejemplo siguiente se asigna el valor devuelto al nombre de la función `myFunction` y, a continuación, se usa `Exit Function` para volver de la función:</span><span class="sxs-lookup"><span data-stu-id="91cfb-146">The following example assigns the return value to the function name `myFunction`, and then uses `Exit Function` to return from the function:</span></span>

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

## <a name="example"></a><span data-ttu-id="91cfb-147">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="91cfb-147">Example</span></span>

<span data-ttu-id="91cfb-148">En el ejemplo siguiente se usa la [instrucción return](return-statement.md) para asignar el valor devuelto y salir de la función:</span><span class="sxs-lookup"><span data-stu-id="91cfb-148">The following example uses the [Return Statement](return-statement.md) to assign the return value and exit the function:</span></span>

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

## <a name="see-also"></a><span data-ttu-id="91cfb-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="91cfb-149">See also</span></span>

- [<span data-ttu-id="91cfb-150">Continue (instrucción)</span><span class="sxs-lookup"><span data-stu-id="91cfb-150">Continue Statement</span></span>](continue-statement.md)
- [<span data-ttu-id="91cfb-151">Do...Loop (instrucción)</span><span class="sxs-lookup"><span data-stu-id="91cfb-151">Do...Loop Statement</span></span>](do-loop-statement.md)
- [<span data-ttu-id="91cfb-152">End (instrucción)</span><span class="sxs-lookup"><span data-stu-id="91cfb-152">End Statement</span></span>](end-statement.md)
- [<span data-ttu-id="91cfb-153">For Each...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="91cfb-153">For Each...Next Statement</span></span>](for-each-next-statement.md)
- [<span data-ttu-id="91cfb-154">For...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="91cfb-154">For...Next Statement</span></span>](for-next-statement.md)
- [<span data-ttu-id="91cfb-155">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="91cfb-155">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="91cfb-156">Return (instrucción)</span><span class="sxs-lookup"><span data-stu-id="91cfb-156">Return Statement</span></span>](return-statement.md)
- [<span data-ttu-id="91cfb-157">Stop (instrucción)</span><span class="sxs-lookup"><span data-stu-id="91cfb-157">Stop Statement</span></span>](stop-statement.md)
- [<span data-ttu-id="91cfb-158">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="91cfb-158">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="91cfb-159">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="91cfb-159">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
