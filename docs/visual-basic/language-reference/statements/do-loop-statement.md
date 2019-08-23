---
title: Instrucción Do...Loop (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Do
- vb.Loop
- vb.Until
helpviewer_keywords:
- conditional statements [Visual Basic], Do�Loop
- while statement [Visual Basic], Do...Loop
- execution [Visual Basic], conditional
- Do loops
- Until keyword [Visual Basic], Do...Loop statement
- Do...Loop statement
- instructions, repeating
- Do statement [Visual Basic]
- Exit statement [Visual Basic], in Do...Loop statements
- loop structures [Visual Basic], Do�Loop statements
- do-while statements [Visual Basic]
- loops, exiting
- Loop keyword [Visual Basic], Do...Loop statement
ms.assetid: 892f9096-b3e2-4aee-834d-83bc4e2c379d
ms.openlocfilehash: 75a2129a9f332024831d97021e381f1b3d4fa048
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942997"
---
# <a name="doloop-statement-visual-basic"></a><span data-ttu-id="4f133-102">Instrucción Do...Loop (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4f133-102">Do...Loop Statement (Visual Basic)</span></span>
<span data-ttu-id="4f133-103">Repite un bloque de instrucciones mientras una `Boolean` condición es `True` o hasta que la condición `True`se convierte en.</span><span class="sxs-lookup"><span data-stu-id="4f133-103">Repeats a block of statements while a `Boolean` condition is `True` or until the condition becomes `True`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f133-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4f133-104">Syntax</span></span>  
  
```  
Do { While | Until } condition  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop  
-or-  
Do  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop { While | Until } condition  
```  
  
## <a name="parts"></a><span data-ttu-id="4f133-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="4f133-105">Parts</span></span>  
  
|<span data-ttu-id="4f133-106">Término</span><span class="sxs-lookup"><span data-stu-id="4f133-106">Term</span></span>|<span data-ttu-id="4f133-107">Definición</span><span class="sxs-lookup"><span data-stu-id="4f133-107">Definition</span></span>|  
|---|---|  
|`Do`|<span data-ttu-id="4f133-108">Necesario.</span><span class="sxs-lookup"><span data-stu-id="4f133-108">Required.</span></span> <span data-ttu-id="4f133-109">Inicia la definición del `Do` bucle.</span><span class="sxs-lookup"><span data-stu-id="4f133-109">Starts the definition of the `Do` loop.</span></span>|  
|`While`|<span data-ttu-id="4f133-110">Es necesario a menos que se use `Until`.</span><span class="sxs-lookup"><span data-stu-id="4f133-110">Required unless `Until` is used.</span></span> <span data-ttu-id="4f133-111">Repita el bucle hasta `condition` que `False`sea.</span><span class="sxs-lookup"><span data-stu-id="4f133-111">Repeat the loop until `condition` is `False`.</span></span>|  
|`Until`|<span data-ttu-id="4f133-112">Es necesario a menos que se use `While`.</span><span class="sxs-lookup"><span data-stu-id="4f133-112">Required unless `While` is used.</span></span> <span data-ttu-id="4f133-113">Repita el bucle hasta `condition` que `True`sea.</span><span class="sxs-lookup"><span data-stu-id="4f133-113">Repeat the loop until `condition` is `True`.</span></span>|  
|`condition`|<span data-ttu-id="4f133-114">Opcional.</span><span class="sxs-lookup"><span data-stu-id="4f133-114">Optional.</span></span> <span data-ttu-id="4f133-115">`Boolean`Expresiones.</span><span class="sxs-lookup"><span data-stu-id="4f133-115">`Boolean` expression.</span></span> <span data-ttu-id="4f133-116">Si `condition` `False`es `Nothing`, Visual Basic lo trata como.</span><span class="sxs-lookup"><span data-stu-id="4f133-116">If `condition` is `Nothing`, Visual Basic treats it as `False`.</span></span>|  
|`statements`|<span data-ttu-id="4f133-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="4f133-117">Optional.</span></span> <span data-ttu-id="4f133-118">Una o varias instrucciones que se repiten mientras, o `condition` hasta `True`, es.</span><span class="sxs-lookup"><span data-stu-id="4f133-118">One or more statements that are repeated while, or until, `condition` is `True`.</span></span>|  
|`Continue Do`|<span data-ttu-id="4f133-119">Opcional.</span><span class="sxs-lookup"><span data-stu-id="4f133-119">Optional.</span></span> <span data-ttu-id="4f133-120">Transfiere el control a la siguiente iteración `Do` del bucle.</span><span class="sxs-lookup"><span data-stu-id="4f133-120">Transfers control to the next iteration of the `Do` loop.</span></span>|  
|`Exit Do`|<span data-ttu-id="4f133-121">Opcional.</span><span class="sxs-lookup"><span data-stu-id="4f133-121">Optional.</span></span> <span data-ttu-id="4f133-122">Transfiere el `Do` control fuera del bucle.</span><span class="sxs-lookup"><span data-stu-id="4f133-122">Transfers control out of the `Do` loop.</span></span>|  
|`Loop`|<span data-ttu-id="4f133-123">Necesario.</span><span class="sxs-lookup"><span data-stu-id="4f133-123">Required.</span></span> <span data-ttu-id="4f133-124">Finaliza la definición del `Do` bucle.</span><span class="sxs-lookup"><span data-stu-id="4f133-124">Terminates the definition of the `Do` loop.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f133-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4f133-125">Remarks</span></span>  
 <span data-ttu-id="4f133-126">Use una `Do...Loop` estructura cuando desee repetir un conjunto de instrucciones un número indefinido de veces, hasta que se satisfaga una condición.</span><span class="sxs-lookup"><span data-stu-id="4f133-126">Use a `Do...Loop` structure when you want to repeat a set of statements an indefinite number of times, until a condition is satisfied.</span></span> <span data-ttu-id="4f133-127">Si desea repetir las instrucciones un número establecido de veces, la instrucción [for... La siguiente instrucción](../../../visual-basic/language-reference/statements/for-next-statement.md) suele ser una mejor opción.</span><span class="sxs-lookup"><span data-stu-id="4f133-127">If you want to repeat the statements a set number of times, the [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md) is usually a better choice.</span></span>  
  
 <span data-ttu-id="4f133-128">Puede usar `While` o `Until` para especificar `condition`, pero no ambos.</span><span class="sxs-lookup"><span data-stu-id="4f133-128">You can use either `While` or `Until` to specify `condition`, but not both.</span></span>  
  
 <span data-ttu-id="4f133-129">Solo puede probar `condition` una vez, al principio o al final del bucle.</span><span class="sxs-lookup"><span data-stu-id="4f133-129">You can test `condition` only one time, at either the start or the end of the loop.</span></span> <span data-ttu-id="4f133-130">Si realiza una `condition` prueba al principio del bucle (en la `Do` instrucción), el bucle podría no ejecutarse ni siquiera una vez.</span><span class="sxs-lookup"><span data-stu-id="4f133-130">If you test `condition` at the start of the loop (in the `Do` statement), the loop might not run even one time.</span></span> <span data-ttu-id="4f133-131">Si se prueba al final del bucle (en la `Loop` instrucción), el bucle siempre se ejecuta al menos una vez.</span><span class="sxs-lookup"><span data-stu-id="4f133-131">If you test at the end of the loop (in the `Loop` statement), the loop always runs at least one time.</span></span>  
  
 <span data-ttu-id="4f133-132">La condición suele ser el resultado de una comparación de dos valores, pero puede ser cualquier expresión que se evalúe como un valor de tipo de`True` [datos booleano](../../../visual-basic/language-reference/data-types/boolean-data-type.md) (o `False`).</span><span class="sxs-lookup"><span data-stu-id="4f133-132">The condition usually results from a comparison of two values, but it can be any expression that evaluates to a [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md) value (`True` or `False`).</span></span> <span data-ttu-id="4f133-133">Esto incluye los valores de otros tipos de datos, como los tipos numéricos, que se `Boolean`han convertido en.</span><span class="sxs-lookup"><span data-stu-id="4f133-133">This includes values of other data types, such as numeric types, that have been converted to `Boolean`.</span></span>  
  
 <span data-ttu-id="4f133-134">Puede anidar `Do` bucles colocando un bucle dentro de otro.</span><span class="sxs-lookup"><span data-stu-id="4f133-134">You can nest `Do` loops by putting one loop within another.</span></span> <span data-ttu-id="4f133-135">También puede anidar distintos tipos de estructuras de control entre sí.</span><span class="sxs-lookup"><span data-stu-id="4f133-135">You can also nest different kinds of control structures within each other.</span></span> <span data-ttu-id="4f133-136">Para obtener más información, vea [estructuras de control anidadas](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span><span class="sxs-lookup"><span data-stu-id="4f133-136">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4f133-137">La `Do...Loop` estructura proporciona más flexibilidad que el [tiempo... End while](../../../visual-basic/language-reference/statements/while-end-while-statement.md) , ya que permite decidir si finalizar el bucle cuando `condition` se detiene `True` o cuando se convierte `True`por primera vez.</span><span class="sxs-lookup"><span data-stu-id="4f133-137">The `Do...Loop` structure gives you more flexibility than the [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md) because it enables you to decide whether to end the loop when `condition` stops being `True` or when it first becomes `True`.</span></span> <span data-ttu-id="4f133-138">También permite realizar pruebas `condition` en el inicio o el final del bucle.</span><span class="sxs-lookup"><span data-stu-id="4f133-138">It also enables you to test `condition` at either the start or the end of the loop.</span></span>  
  
## <a name="exit-do"></a><span data-ttu-id="4f133-139">Salir</span><span class="sxs-lookup"><span data-stu-id="4f133-139">Exit Do</span></span>  
 <span data-ttu-id="4f133-140">La instrucción [Exit do](../../../visual-basic/language-reference/statements/exit-statement.md) puede proporcionar una manera alternativa de salir de `Do…Loop`un.</span><span class="sxs-lookup"><span data-stu-id="4f133-140">The [Exit Do](../../../visual-basic/language-reference/statements/exit-statement.md) statement can provide an alternative way to exit a `Do…Loop`.</span></span> <span data-ttu-id="4f133-141">`Exit Do`transfiere el control inmediatamente a la instrucción que sigue `Loop` a la instrucción.</span><span class="sxs-lookup"><span data-stu-id="4f133-141">`Exit Do` transfers control immediately to the statement that follows the `Loop` statement.</span></span>  
  
 <span data-ttu-id="4f133-142">`Exit Do`se suele usar después de evaluar alguna condición, por ejemplo en una `If...Then...Else` estructura.</span><span class="sxs-lookup"><span data-stu-id="4f133-142">`Exit Do` is often used after some condition is evaluated, for example in an `If...Then...Else` structure.</span></span> <span data-ttu-id="4f133-143">Es posible que desee salir de un bucle si detecta una condición que hace que sea innecesario o imposible continuar la iteración, como un valor erróneo o una solicitud de finalización.</span><span class="sxs-lookup"><span data-stu-id="4f133-143">You might want to exit a loop if you detect a condition that makes it unnecessary or impossible to continue iterating, such as an erroneous value or a termination request.</span></span> <span data-ttu-id="4f133-144">Un uso de `Exit Do` es para probar una condición que podría provocar un *bucle interminable*, que es un bucle que podría ejecutar un número de veces grande o incluso infinito.</span><span class="sxs-lookup"><span data-stu-id="4f133-144">One use of `Exit Do` is to test for a condition that could cause an *endless loop*, which is a loop that could run a large or even infinite number of times.</span></span> <span data-ttu-id="4f133-145">Puede usar `Exit Do` para escapar el bucle.</span><span class="sxs-lookup"><span data-stu-id="4f133-145">You can use `Exit Do` to escape the loop.</span></span>  
  
 <span data-ttu-id="4f133-146">Puede incluir cualquier número de `Exit Do` instrucciones en cualquier parte de un. `Do…Loop`</span><span class="sxs-lookup"><span data-stu-id="4f133-146">You can include any number of `Exit Do` statements anywhere in a `Do…Loop`.</span></span>  
  
 <span data-ttu-id="4f133-147">Cuando se usa dentro de `Do` bucles anidados, `Exit Do` transfiere el control fuera del bucle más interno y en el siguiente nivel superior de anidamiento.</span><span class="sxs-lookup"><span data-stu-id="4f133-147">When used within nested `Do` loops, `Exit Do` transfers control out of the innermost loop and into the next higher level of nesting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f133-148">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4f133-148">Example</span></span>  
 <span data-ttu-id="4f133-149">En el ejemplo siguiente, las instrucciones del bucle continúan ejecutándose hasta que la `index` variable es mayor que 10.</span><span class="sxs-lookup"><span data-stu-id="4f133-149">In the following example, the statements in the loop continue to run until the `index` variable is greater than 10.</span></span> <span data-ttu-id="4f133-150">La `Until` cláusula está al final del bucle.</span><span class="sxs-lookup"><span data-stu-id="4f133-150">The `Until` clause is at the end of the loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#131](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#131)]  
  
## <a name="example"></a><span data-ttu-id="4f133-151">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4f133-151">Example</span></span>  
 <span data-ttu-id="4f133-152">En el ejemplo siguiente se `While` utiliza una cláusula en lugar `Until` de una cláusula `condition` y se prueba al principio del bucle en lugar de al final.</span><span class="sxs-lookup"><span data-stu-id="4f133-152">The following example uses a `While` clause instead of an `Until` clause, and `condition` is tested at the start of the loop instead of at the end.</span></span>  
  
 [!code-vb[VbVbalrStatements#132](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#132)]  
  
## <a name="example"></a><span data-ttu-id="4f133-153">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4f133-153">Example</span></span>  
 <span data-ttu-id="4f133-154">En el ejemplo siguiente, `condition` detiene el bucle cuando la `index` variable es mayor que 100.</span><span class="sxs-lookup"><span data-stu-id="4f133-154">In the following example, `condition` stops the loop when the `index` variable is greater than 100.</span></span> <span data-ttu-id="4f133-155">La `If` instrucción del bucle, sin embargo, hace que `Exit Do` la instrucción detenga el bucle cuando la variable de índice es mayor que 10.</span><span class="sxs-lookup"><span data-stu-id="4f133-155">The `If` statement in the loop, however, causes the `Exit Do` statement to stop the loop when the index variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]  
  
## <a name="example"></a><span data-ttu-id="4f133-156">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4f133-156">Example</span></span>  
 <span data-ttu-id="4f133-157">En el ejemplo siguiente se leen todas las líneas de un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="4f133-157">The following example reads all lines in a text file.</span></span> <span data-ttu-id="4f133-158">El <xref:System.IO.File.OpenText%2A> método abre el archivo y devuelve un <xref:System.IO.StreamReader> que lee los caracteres.</span><span class="sxs-lookup"><span data-stu-id="4f133-158">The <xref:System.IO.File.OpenText%2A> method opens the file and returns a <xref:System.IO.StreamReader> that reads the characters.</span></span> <span data-ttu-id="4f133-159">En la `Do...Loop` condición, el <xref:System.IO.StreamReader.Peek%2A> método de `StreamReader` determina si hay caracteres adicionales.</span><span class="sxs-lookup"><span data-stu-id="4f133-159">In the `Do...Loop` condition, the <xref:System.IO.StreamReader.Peek%2A> method of the `StreamReader` determines whether there are any additional characters.</span></span>  
  
 [!code-vb[VbVbalrStatements#134](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#134)]  
  
## <a name="see-also"></a><span data-ttu-id="4f133-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f133-160">See also</span></span>

- [<span data-ttu-id="4f133-161">Estructuras de bucle</span><span class="sxs-lookup"><span data-stu-id="4f133-161">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="4f133-162">For...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="4f133-162">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="4f133-163">Boolean (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="4f133-163">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [<span data-ttu-id="4f133-164">Estructuras de control anidadas</span><span class="sxs-lookup"><span data-stu-id="4f133-164">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="4f133-165">Exit (instrucción)</span><span class="sxs-lookup"><span data-stu-id="4f133-165">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="4f133-166">While...End While (instrucción)</span><span class="sxs-lookup"><span data-stu-id="4f133-166">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
