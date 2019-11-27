---
title: Exit (Instrucción)
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
ms.openlocfilehash: 1bfe81428fd3c50663fd8978e05c6a945cd47df8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345936"
---
# <a name="exit-statement-visual-basic"></a><span data-ttu-id="c3387-102">Exit (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c3387-102">Exit Statement (Visual Basic)</span></span>

<span data-ttu-id="c3387-103">Sale de un procedimiento o un bloque y transfiere el control inmediatamente a la instrucción que sigue a la llamada al procedimiento o la definición del bloque.</span><span class="sxs-lookup"><span data-stu-id="c3387-103">Exits a procedure or block and transfers control immediately to the statement following the procedure call or the block definition.</span></span>

## <a name="syntax"></a><span data-ttu-id="c3387-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c3387-104">Syntax</span></span>

```vb
Exit { Do | For | Function | Property | Select | Sub | Try | While }
```

## <a name="statements"></a><span data-ttu-id="c3387-105">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="c3387-105">Statements</span></span>

 `Exit Do`  
 <span data-ttu-id="c3387-106">Sale inmediatamente del bucle `Do` en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="c3387-106">Immediately exits the `Do` loop in which it appears.</span></span> <span data-ttu-id="c3387-107">La ejecución continúa con la instrucción que sigue a la instrucción `Loop`.</span><span class="sxs-lookup"><span data-stu-id="c3387-107">Execution continues with the statement following the `Loop` statement.</span></span> <span data-ttu-id="c3387-108">`Exit Do` solo se puede usar dentro de un bucle de `Do`.</span><span class="sxs-lookup"><span data-stu-id="c3387-108">`Exit Do` can be used only inside a `Do` loop.</span></span> <span data-ttu-id="c3387-109">Cuando se usa dentro de bucles `Do` anidados, `Exit Do` sale del bucle más interno y transfiere el control al siguiente nivel superior de anidamiento.</span><span class="sxs-lookup"><span data-stu-id="c3387-109">When used within nested `Do` loops, `Exit Do` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>

 `Exit For`  
 <span data-ttu-id="c3387-110">Sale inmediatamente del bucle `For` en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="c3387-110">Immediately exits the `For` loop in which it appears.</span></span> <span data-ttu-id="c3387-111">La ejecución continúa con la instrucción que sigue a la instrucción `Next`.</span><span class="sxs-lookup"><span data-stu-id="c3387-111">Execution continues with the statement following the `Next` statement.</span></span> <span data-ttu-id="c3387-112">`Exit For` solo se puede usar dentro de un bucle `For`...`Next` o `For Each`...`Next`.</span><span class="sxs-lookup"><span data-stu-id="c3387-112">`Exit For` can be used only inside a `For`...`Next` or `For Each`...`Next` loop.</span></span> <span data-ttu-id="c3387-113">Cuando se usa dentro de bucles `For` anidados, `Exit For` sale del bucle más interno y transfiere el control al siguiente nivel superior de anidamiento.</span><span class="sxs-lookup"><span data-stu-id="c3387-113">When used within nested `For` loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>

 `Exit Function`  
 <span data-ttu-id="c3387-114">Sale inmediatamente del procedimiento de `Function` en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="c3387-114">Immediately exits the `Function` procedure in which it appears.</span></span> <span data-ttu-id="c3387-115">La ejecución continúa con la instrucción que sigue a la instrucción que llamó al procedimiento `Function`.</span><span class="sxs-lookup"><span data-stu-id="c3387-115">Execution continues with the statement following the statement that called the `Function` procedure.</span></span> <span data-ttu-id="c3387-116">`Exit Function` solo se puede usar dentro de un procedimiento `Function`.</span><span class="sxs-lookup"><span data-stu-id="c3387-116">`Exit Function` can be used only inside a `Function` procedure.</span></span>

 <span data-ttu-id="c3387-117">Para especificar un valor devuelto, puede asignar el valor al nombre de la función en una línea antes de la instrucción `Exit Function`.</span><span class="sxs-lookup"><span data-stu-id="c3387-117">To specify a return value, you can assign the value to the function name on a line before the `Exit Function` statement.</span></span> <span data-ttu-id="c3387-118">Para asignar el valor devuelto y salir de la función en una instrucción, en su lugar puede usar la [instrucción return](return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c3387-118">To assign the return value and exit the function in one statement, you can instead use the [Return Statement](return-statement.md).</span></span>

 `Exit Property`  
 <span data-ttu-id="c3387-119">Sale inmediatamente del procedimiento de `Property` en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="c3387-119">Immediately exits the `Property` procedure in which it appears.</span></span> <span data-ttu-id="c3387-120">La ejecución continúa con la instrucción que llamó al procedimiento `Property`, es decir, con la instrucción que solicita o establece el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="c3387-120">Execution continues with the statement that called the `Property` procedure, that is, with the statement requesting or setting the property's value.</span></span> <span data-ttu-id="c3387-121">`Exit Property` solo se puede usar dentro del procedimiento de `Get` o `Set` de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="c3387-121">`Exit Property` can be used only inside a property's `Get` or `Set` procedure.</span></span>

 <span data-ttu-id="c3387-122">Para especificar un valor devuelto en un procedimiento `Get`, puede asignar el valor al nombre de la función en una línea antes de la instrucción `Exit Property`.</span><span class="sxs-lookup"><span data-stu-id="c3387-122">To specify a return value in a `Get` procedure, you can assign the value to the function name on a line before the `Exit Property` statement.</span></span> <span data-ttu-id="c3387-123">Para asignar el valor devuelto y salir del procedimiento `Get` en una instrucción, en su lugar puede usar la instrucción `Return`.</span><span class="sxs-lookup"><span data-stu-id="c3387-123">To assign the return value and exit the `Get` procedure in one statement, you can instead use the `Return` statement.</span></span>

 <span data-ttu-id="c3387-124">En un procedimiento de `Set`, la instrucción `Exit Property` es equivalente a la instrucción `Return`.</span><span class="sxs-lookup"><span data-stu-id="c3387-124">In a `Set` procedure, the `Exit Property` statement is equivalent to the `Return` statement.</span></span>

 `Exit Select`  
 <span data-ttu-id="c3387-125">Sale inmediatamente del bloque `Select Case` en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="c3387-125">Immediately exits the `Select Case` block in which it appears.</span></span> <span data-ttu-id="c3387-126">La ejecución continúa con la instrucción que sigue a la instrucción `End Select`.</span><span class="sxs-lookup"><span data-stu-id="c3387-126">Execution continues with the statement following the `End Select` statement.</span></span> <span data-ttu-id="c3387-127">`Exit Select` solo se puede usar dentro de una instrucción de `Select Case`.</span><span class="sxs-lookup"><span data-stu-id="c3387-127">`Exit Select` can be used only inside a `Select Case` statement.</span></span>

 `Exit Sub`  
 <span data-ttu-id="c3387-128">Sale inmediatamente del procedimiento de `Sub` en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="c3387-128">Immediately exits the `Sub` procedure in which it appears.</span></span> <span data-ttu-id="c3387-129">La ejecución continúa con la instrucción que sigue a la instrucción que llamó al procedimiento `Sub`.</span><span class="sxs-lookup"><span data-stu-id="c3387-129">Execution continues with the statement following the statement that called the `Sub` procedure.</span></span> <span data-ttu-id="c3387-130">`Exit Sub` solo se puede usar dentro de un procedimiento `Sub`.</span><span class="sxs-lookup"><span data-stu-id="c3387-130">`Exit Sub` can be used only inside a `Sub` procedure.</span></span>

 <span data-ttu-id="c3387-131">En un procedimiento de `Sub`, la instrucción `Exit Sub` es equivalente a la instrucción `Return`.</span><span class="sxs-lookup"><span data-stu-id="c3387-131">In a `Sub` procedure, the `Exit Sub` statement is equivalent to the `Return` statement.</span></span>

 `Exit Try`  
 <span data-ttu-id="c3387-132">Sale inmediatamente del bloque `Try` o `Catch` en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="c3387-132">Immediately exits the `Try` or `Catch` block in which it appears.</span></span> <span data-ttu-id="c3387-133">La ejecución continúa con el bloque `Finally` si hay alguno, o con la instrucción que sigue a la instrucción `End Try` de lo contrario.</span><span class="sxs-lookup"><span data-stu-id="c3387-133">Execution continues with the `Finally` block if there is one, or with the statement following the `End Try` statement otherwise.</span></span> <span data-ttu-id="c3387-134">`Exit Try` solo se puede usar dentro de un bloque de `Try` o `Catch` y no dentro de un bloque de `Finally`.</span><span class="sxs-lookup"><span data-stu-id="c3387-134">`Exit Try` can be used only inside a `Try` or `Catch` block, and not inside a `Finally` block.</span></span>

 `Exit While`  
 <span data-ttu-id="c3387-135">Sale inmediatamente del bucle `While` en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="c3387-135">Immediately exits the `While` loop in which it appears.</span></span> <span data-ttu-id="c3387-136">La ejecución continúa con la instrucción que sigue a la instrucción `End While`.</span><span class="sxs-lookup"><span data-stu-id="c3387-136">Execution continues with the statement following the `End While` statement.</span></span> <span data-ttu-id="c3387-137">`Exit While` solo se puede usar dentro de un bucle de `While`.</span><span class="sxs-lookup"><span data-stu-id="c3387-137">`Exit While` can be used only inside a `While` loop.</span></span> <span data-ttu-id="c3387-138">Cuando se usa dentro de bucles `While` anidados, `Exit While` transfiere el control al bucle que está un nivel anidado por encima del bucle donde se produce `Exit While`.</span><span class="sxs-lookup"><span data-stu-id="c3387-138">When used within nested `While` loops, `Exit While` transfers control to the loop that is one nested level above the loop where `Exit While` occurs.</span></span>

## <a name="remarks"></a><span data-ttu-id="c3387-139">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c3387-139">Remarks</span></span>

<span data-ttu-id="c3387-140">No confunda `Exit` instrucciones con instrucciones de `End`.</span><span class="sxs-lookup"><span data-stu-id="c3387-140">Do not confuse `Exit` statements with `End` statements.</span></span> <span data-ttu-id="c3387-141">`Exit` no define el final de una instrucción.</span><span class="sxs-lookup"><span data-stu-id="c3387-141">`Exit` does not define the end of a statement.</span></span>

## <a name="example"></a><span data-ttu-id="c3387-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c3387-142">Example</span></span>

<span data-ttu-id="c3387-143">En el ejemplo siguiente, la condición de bucle detiene el bucle cuando la variable de `index` es mayor que 100.</span><span class="sxs-lookup"><span data-stu-id="c3387-143">In the following example, the loop condition stops the loop when the `index` variable is greater than 100.</span></span> <span data-ttu-id="c3387-144">Sin embargo, la instrucción `If` del bucle hace que la instrucción `Exit Do` detenga el bucle cuando la variable de índice sea mayor que 10.</span><span class="sxs-lookup"><span data-stu-id="c3387-144">The `If` statement in the loop, however, causes the `Exit Do` statement to stop the loop when the index variable is greater than 10.</span></span>

[!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]

## <a name="example"></a><span data-ttu-id="c3387-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c3387-145">Example</span></span>

<span data-ttu-id="c3387-146">En el ejemplo siguiente se asigna el valor devuelto al nombre de función `myFunction`y, a continuación, se usa `Exit Function` para devolver de la función:</span><span class="sxs-lookup"><span data-stu-id="c3387-146">The following example assigns the return value to the function name `myFunction`, and then uses `Exit Function` to return from the function:</span></span>

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

## <a name="example"></a><span data-ttu-id="c3387-147">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c3387-147">Example</span></span>

<span data-ttu-id="c3387-148">En el ejemplo siguiente se usa la [instrucción return](return-statement.md) para asignar el valor devuelto y salir de la función:</span><span class="sxs-lookup"><span data-stu-id="c3387-148">The following example uses the [Return Statement](return-statement.md) to assign the return value and exit the function:</span></span>

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

## <a name="see-also"></a><span data-ttu-id="c3387-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3387-149">See also</span></span>

- [<span data-ttu-id="c3387-150">Continue (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c3387-150">Continue Statement</span></span>](continue-statement.md)
- [<span data-ttu-id="c3387-151">Do...Loop (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c3387-151">Do...Loop Statement</span></span>](do-loop-statement.md)
- [<span data-ttu-id="c3387-152">End (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c3387-152">End Statement</span></span>](end-statement.md)
- [<span data-ttu-id="c3387-153">For Each...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c3387-153">For Each...Next Statement</span></span>](for-each-next-statement.md)
- [<span data-ttu-id="c3387-154">For...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c3387-154">For...Next Statement</span></span>](for-next-statement.md)
- [<span data-ttu-id="c3387-155">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c3387-155">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="c3387-156">Return (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c3387-156">Return Statement</span></span>](return-statement.md)
- [<span data-ttu-id="c3387-157">Stop (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c3387-157">Stop Statement</span></span>](stop-statement.md)
- [<span data-ttu-id="c3387-158">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c3387-158">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="c3387-159">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c3387-159">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
