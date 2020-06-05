---
title: Instrucción Do...Loop
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
ms.openlocfilehash: a9ec6caccbe161a39b592a642a938b81bae911a6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404789"
---
# <a name="doloop-statement-visual-basic"></a><span data-ttu-id="7bb7d-102">Instrucción Do...Loop (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7bb7d-102">Do...Loop Statement (Visual Basic)</span></span>
<span data-ttu-id="7bb7d-103">Repite un bloque de instrucciones mientras una `Boolean` condición es `True` o hasta que la condición se convierte en `True` .</span><span class="sxs-lookup"><span data-stu-id="7bb7d-103">Repeats a block of statements while a `Boolean` condition is `True` or until the condition becomes `True`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bb7d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7bb7d-104">Syntax</span></span>  
  
```vb  
Do { While | Until } condition  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop  
' -or-  
Do  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop { While | Until } condition  
```  
  
## <a name="parts"></a><span data-ttu-id="7bb7d-105">Partes</span><span class="sxs-lookup"><span data-stu-id="7bb7d-105">Parts</span></span>  
  
|<span data-ttu-id="7bb7d-106">Término</span><span class="sxs-lookup"><span data-stu-id="7bb7d-106">Term</span></span>|<span data-ttu-id="7bb7d-107">Definición</span><span class="sxs-lookup"><span data-stu-id="7bb7d-107">Definition</span></span>|  
|---|---|  
|`Do`|<span data-ttu-id="7bb7d-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="7bb7d-108">Required.</span></span> <span data-ttu-id="7bb7d-109">Inicia la definición del `Do` bucle.</span><span class="sxs-lookup"><span data-stu-id="7bb7d-109">Starts the definition of the `Do` loop.</span></span>|  
|`While`|<span data-ttu-id="7bb7d-110">Es necesario a menos que se use `Until`.</span><span class="sxs-lookup"><span data-stu-id="7bb7d-110">Required unless `Until` is used.</span></span> <span data-ttu-id="7bb7d-111">Repita el bucle hasta que `condition` sea `False` .</span><span class="sxs-lookup"><span data-stu-id="7bb7d-111">Repeat the loop until `condition` is `False`.</span></span>|  
|`Until`|<span data-ttu-id="7bb7d-112">Es necesario a menos que se use `While`.</span><span class="sxs-lookup"><span data-stu-id="7bb7d-112">Required unless `While` is used.</span></span> <span data-ttu-id="7bb7d-113">Repita el bucle hasta que `condition` sea `True` .</span><span class="sxs-lookup"><span data-stu-id="7bb7d-113">Repeat the loop until `condition` is `True`.</span></span>|  
|`condition`|<span data-ttu-id="7bb7d-114">Opcional.</span><span class="sxs-lookup"><span data-stu-id="7bb7d-114">Optional.</span></span> <span data-ttu-id="7bb7d-115">Expresión `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="7bb7d-115">`Boolean` expression.</span></span> <span data-ttu-id="7bb7d-116">Si `condition` es `Nothing` , Visual Basic lo trata como `False` .</span><span class="sxs-lookup"><span data-stu-id="7bb7d-116">If `condition` is `Nothing`, Visual Basic treats it as `False`.</span></span>|  
|`statements`|<span data-ttu-id="7bb7d-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="7bb7d-117">Optional.</span></span> <span data-ttu-id="7bb7d-118">Una o varias instrucciones que se repiten mientras, o hasta, `condition` es `True` .</span><span class="sxs-lookup"><span data-stu-id="7bb7d-118">One or more statements that are repeated while, or until, `condition` is `True`.</span></span>|  
|`Continue Do`|<span data-ttu-id="7bb7d-119">Opcional.</span><span class="sxs-lookup"><span data-stu-id="7bb7d-119">Optional.</span></span> <span data-ttu-id="7bb7d-120">Transfiere el control a la siguiente iteración del `Do` bucle.</span><span class="sxs-lookup"><span data-stu-id="7bb7d-120">Transfers control to the next iteration of the `Do` loop.</span></span>|  
|`Exit Do`|<span data-ttu-id="7bb7d-121">Opcional.</span><span class="sxs-lookup"><span data-stu-id="7bb7d-121">Optional.</span></span> <span data-ttu-id="7bb7d-122">Transfiere el control fuera del `Do` bucle.</span><span class="sxs-lookup"><span data-stu-id="7bb7d-122">Transfers control out of the `Do` loop.</span></span>|  
|`Loop`|<span data-ttu-id="7bb7d-123">Necesario.</span><span class="sxs-lookup"><span data-stu-id="7bb7d-123">Required.</span></span> <span data-ttu-id="7bb7d-124">Finaliza la definición del `Do` bucle.</span><span class="sxs-lookup"><span data-stu-id="7bb7d-124">Terminates the definition of the `Do` loop.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7bb7d-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7bb7d-125">Remarks</span></span>  
 <span data-ttu-id="7bb7d-126">Use una `Do...Loop` estructura cuando desee repetir un conjunto de instrucciones un número indefinido de veces, hasta que se satisfaga una condición.</span><span class="sxs-lookup"><span data-stu-id="7bb7d-126">Use a `Do...Loop` structure when you want to repeat a set of statements an indefinite number of times, until a condition is satisfied.</span></span> <span data-ttu-id="7bb7d-127">Si desea repetir las instrucciones un número establecido de veces, la instrucción [for... La siguiente instrucción](for-next-statement.md) suele ser una mejor opción.</span><span class="sxs-lookup"><span data-stu-id="7bb7d-127">If you want to repeat the statements a set number of times, the [For...Next Statement](for-next-statement.md) is usually a better choice.</span></span>  
  
 <span data-ttu-id="7bb7d-128">Puede usar `While` o `Until` para especificar `condition` , pero no ambos.</span><span class="sxs-lookup"><span data-stu-id="7bb7d-128">You can use either `While` or `Until` to specify `condition`, but not both.</span></span>  
  
 <span data-ttu-id="7bb7d-129">Solo puede probar `condition` una vez, al principio o al final del bucle.</span><span class="sxs-lookup"><span data-stu-id="7bb7d-129">You can test `condition` only one time, at either the start or the end of the loop.</span></span> <span data-ttu-id="7bb7d-130">Si realiza `condition` una prueba al principio del bucle (en la `Do` instrucción), el bucle podría no ejecutarse ni siquiera una vez.</span><span class="sxs-lookup"><span data-stu-id="7bb7d-130">If you test `condition` at the start of the loop (in the `Do` statement), the loop might not run even one time.</span></span> <span data-ttu-id="7bb7d-131">Si se prueba al final del bucle (en la `Loop` instrucción), el bucle siempre se ejecuta al menos una vez.</span><span class="sxs-lookup"><span data-stu-id="7bb7d-131">If you test at the end of the loop (in the `Loop` statement), the loop always runs at least one time.</span></span>  
  
 <span data-ttu-id="7bb7d-132">La condición suele ser el resultado de una comparación de dos valores, pero puede ser cualquier expresión que se evalúe como un valor de [tipo de datos booleano](../data-types/boolean-data-type.md) ( `True` o `False` ).</span><span class="sxs-lookup"><span data-stu-id="7bb7d-132">The condition usually results from a comparison of two values, but it can be any expression that evaluates to a [Boolean Data Type](../data-types/boolean-data-type.md) value (`True` or `False`).</span></span> <span data-ttu-id="7bb7d-133">Esto incluye los valores de otros tipos de datos, como los tipos numéricos, que se han convertido en `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="7bb7d-133">This includes values of other data types, such as numeric types, that have been converted to `Boolean`.</span></span>  
  
 <span data-ttu-id="7bb7d-134">Puede anidar `Do` bucles colocando un bucle dentro de otro.</span><span class="sxs-lookup"><span data-stu-id="7bb7d-134">You can nest `Do` loops by putting one loop within another.</span></span> <span data-ttu-id="7bb7d-135">También puede anidar distintos tipos de estructuras de control entre sí.</span><span class="sxs-lookup"><span data-stu-id="7bb7d-135">You can also nest different kinds of control structures within each other.</span></span> <span data-ttu-id="7bb7d-136">Para obtener más información, vea [estructuras de control anidadas](../../programming-guide/language-features/control-flow/nested-control-structures.md).</span><span class="sxs-lookup"><span data-stu-id="7bb7d-136">For more information, see [Nested Control Structures](../../programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7bb7d-137">La `Do...Loop` estructura proporciona más flexibilidad que el [tiempo... End while](while-end-while-statement.md) , ya que permite decidir si finalizar el bucle cuando se `condition` detiene `True` o cuando se convierte por primera vez `True` .</span><span class="sxs-lookup"><span data-stu-id="7bb7d-137">The `Do...Loop` structure gives you more flexibility than the [While...End While Statement](while-end-while-statement.md) because it enables you to decide whether to end the loop when `condition` stops being `True` or when it first becomes `True`.</span></span> <span data-ttu-id="7bb7d-138">También permite realizar pruebas `condition` en el inicio o el final del bucle.</span><span class="sxs-lookup"><span data-stu-id="7bb7d-138">It also enables you to test `condition` at either the start or the end of the loop.</span></span>  
  
## <a name="exit-do"></a><span data-ttu-id="7bb7d-139">Salir</span><span class="sxs-lookup"><span data-stu-id="7bb7d-139">Exit Do</span></span>  
 <span data-ttu-id="7bb7d-140">La instrucción [Exit do](exit-statement.md) puede proporcionar una manera alternativa de salir de un `Do…Loop` .</span><span class="sxs-lookup"><span data-stu-id="7bb7d-140">The [Exit Do](exit-statement.md) statement can provide an alternative way to exit a `Do…Loop`.</span></span> <span data-ttu-id="7bb7d-141">`Exit Do`transfiere el control inmediatamente a la instrucción que sigue a la `Loop` instrucción.</span><span class="sxs-lookup"><span data-stu-id="7bb7d-141">`Exit Do` transfers control immediately to the statement that follows the `Loop` statement.</span></span>  
  
 <span data-ttu-id="7bb7d-142">`Exit Do`se suele usar después de evaluar alguna condición, por ejemplo en una `If...Then...Else` estructura.</span><span class="sxs-lookup"><span data-stu-id="7bb7d-142">`Exit Do` is often used after some condition is evaluated, for example in an `If...Then...Else` structure.</span></span> <span data-ttu-id="7bb7d-143">Es posible que desee salir de un bucle si detecta una condición que hace que sea innecesario o imposible continuar la iteración, como un valor erróneo o una solicitud de finalización.</span><span class="sxs-lookup"><span data-stu-id="7bb7d-143">You might want to exit a loop if you detect a condition that makes it unnecessary or impossible to continue iterating, such as an erroneous value or a termination request.</span></span> <span data-ttu-id="7bb7d-144">Un uso de `Exit Do` es para probar una condición que podría provocar un *bucle interminable*, que es un bucle que podría ejecutar un número de veces grande o incluso infinito.</span><span class="sxs-lookup"><span data-stu-id="7bb7d-144">One use of `Exit Do` is to test for a condition that could cause an *endless loop*, which is a loop that could run a large or even infinite number of times.</span></span> <span data-ttu-id="7bb7d-145">Puede usar `Exit Do` para escapar el bucle.</span><span class="sxs-lookup"><span data-stu-id="7bb7d-145">You can use `Exit Do` to escape the loop.</span></span>  
  
 <span data-ttu-id="7bb7d-146">Puede incluir cualquier número de `Exit Do` instrucciones en cualquier parte de un `Do…Loop` .</span><span class="sxs-lookup"><span data-stu-id="7bb7d-146">You can include any number of `Exit Do` statements anywhere in a `Do…Loop`.</span></span>  
  
 <span data-ttu-id="7bb7d-147">Cuando se usa dentro de `Do` bucles anidados, `Exit Do` transfiere el control fuera del bucle más interno y en el siguiente nivel superior de anidamiento.</span><span class="sxs-lookup"><span data-stu-id="7bb7d-147">When used within nested `Do` loops, `Exit Do` transfers control out of the innermost loop and into the next higher level of nesting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7bb7d-148">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7bb7d-148">Example</span></span>  
 <span data-ttu-id="7bb7d-149">En el ejemplo siguiente, las instrucciones del bucle continúan ejecutándose hasta que la `index` variable es mayor que 10.</span><span class="sxs-lookup"><span data-stu-id="7bb7d-149">In the following example, the statements in the loop continue to run until the `index` variable is greater than 10.</span></span> <span data-ttu-id="7bb7d-150">La `Until` cláusula está al final del bucle.</span><span class="sxs-lookup"><span data-stu-id="7bb7d-150">The `Until` clause is at the end of the loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#131](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#131)]  
  
## <a name="example"></a><span data-ttu-id="7bb7d-151">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7bb7d-151">Example</span></span>  
 <span data-ttu-id="7bb7d-152">En el ejemplo siguiente se utiliza una `While` cláusula en lugar de una `Until` cláusula y `condition` se prueba al principio del bucle en lugar de al final.</span><span class="sxs-lookup"><span data-stu-id="7bb7d-152">The following example uses a `While` clause instead of an `Until` clause, and `condition` is tested at the start of the loop instead of at the end.</span></span>  
  
 [!code-vb[VbVbalrStatements#132](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#132)]  
  
## <a name="example"></a><span data-ttu-id="7bb7d-153">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7bb7d-153">Example</span></span>  
 <span data-ttu-id="7bb7d-154">En el ejemplo siguiente, `condition` detiene el bucle cuando la `index` variable es mayor que 100.</span><span class="sxs-lookup"><span data-stu-id="7bb7d-154">In the following example, `condition` stops the loop when the `index` variable is greater than 100.</span></span> <span data-ttu-id="7bb7d-155">La `If` instrucción del bucle, sin embargo, hace que la `Exit Do` instrucción detenga el bucle cuando la variable de índice es mayor que 10.</span><span class="sxs-lookup"><span data-stu-id="7bb7d-155">The `If` statement in the loop, however, causes the `Exit Do` statement to stop the loop when the index variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]  
  
## <a name="example"></a><span data-ttu-id="7bb7d-156">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7bb7d-156">Example</span></span>  
 <span data-ttu-id="7bb7d-157">En el ejemplo siguiente se leen todas las líneas de un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="7bb7d-157">The following example reads all lines in a text file.</span></span> <span data-ttu-id="7bb7d-158">El <xref:System.IO.File.OpenText%2A> método abre el archivo y devuelve un <xref:System.IO.StreamReader> que lee los caracteres.</span><span class="sxs-lookup"><span data-stu-id="7bb7d-158">The <xref:System.IO.File.OpenText%2A> method opens the file and returns a <xref:System.IO.StreamReader> that reads the characters.</span></span> <span data-ttu-id="7bb7d-159">En la `Do...Loop` condición, el <xref:System.IO.StreamReader.Peek%2A> método de `StreamReader` determina si hay caracteres adicionales.</span><span class="sxs-lookup"><span data-stu-id="7bb7d-159">In the `Do...Loop` condition, the <xref:System.IO.StreamReader.Peek%2A> method of the `StreamReader` determines whether there are any additional characters.</span></span>  
  
 [!code-vb[VbVbalrStatements#134](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#134)]  
  
## <a name="see-also"></a><span data-ttu-id="7bb7d-160">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7bb7d-160">See also</span></span>

- [<span data-ttu-id="7bb7d-161">Estructuras de bucle</span><span class="sxs-lookup"><span data-stu-id="7bb7d-161">Loop Structures</span></span>](../../programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="7bb7d-162">Instrucción For...Next</span><span class="sxs-lookup"><span data-stu-id="7bb7d-162">For...Next Statement</span></span>](for-next-statement.md)
- [<span data-ttu-id="7bb7d-163">Tipo de datos Boolean</span><span class="sxs-lookup"><span data-stu-id="7bb7d-163">Boolean Data Type</span></span>](../data-types/boolean-data-type.md)
- [<span data-ttu-id="7bb7d-164">Estructuras de control anidadas</span><span class="sxs-lookup"><span data-stu-id="7bb7d-164">Nested Control Structures</span></span>](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="7bb7d-165">Instrucción Exit</span><span class="sxs-lookup"><span data-stu-id="7bb7d-165">Exit Statement</span></span>](exit-statement.md)
- [<span data-ttu-id="7bb7d-166">Instrucción While...End While</span><span class="sxs-lookup"><span data-stu-id="7bb7d-166">While...End While Statement</span></span>](while-end-while-statement.md)
