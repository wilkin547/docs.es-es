---
title: Instrucción While...End While (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.While
- vb.While...EndWhile
helpviewer_keywords:
- While statement [Visual Basic], While...End While
- While statement [Visual Basic]
- While...End While statements [Visual Basic]
ms.assetid: b931d1ce-e8ed-44d8-a13d-92a4f5458a1e
ms.openlocfilehash: 5da05835998b2e9ef9aeefe5b00faf9e1ecb9ce2
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582272"
---
# <a name="whileend-while-statement-visual-basic"></a><span data-ttu-id="147a7-102">Instrucción While...End While (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="147a7-102">While...End While Statement (Visual Basic)</span></span>
<span data-ttu-id="147a7-103">Ejecuta una serie de instrucciones siempre que se `True` una condición determinada.</span><span class="sxs-lookup"><span data-stu-id="147a7-103">Runs a series of statements as long as a given condition is `True`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="147a7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="147a7-104">Syntax</span></span>  
  
```vb  
While condition  
    [ statements ]  
    [ Continue While ]  
    [ statements ]  
    [ Exit While ]  
    [ statements ]  
End While  
```  
  
## <a name="parts"></a><span data-ttu-id="147a7-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="147a7-105">Parts</span></span>  
  
|<span data-ttu-id="147a7-106">Término</span><span class="sxs-lookup"><span data-stu-id="147a7-106">Term</span></span>|<span data-ttu-id="147a7-107">de esquema JSON</span><span class="sxs-lookup"><span data-stu-id="147a7-107">Definition</span></span>|  
|---|---|  
|`condition`|<span data-ttu-id="147a7-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="147a7-108">Required.</span></span> <span data-ttu-id="147a7-109">`Boolean` expresión.</span><span class="sxs-lookup"><span data-stu-id="147a7-109">`Boolean` expression.</span></span> <span data-ttu-id="147a7-110">Si `condition` es `Nothing`, Visual Basic lo trata como `False`.</span><span class="sxs-lookup"><span data-stu-id="147a7-110">If `condition` is `Nothing`, Visual Basic treats it as `False`.</span></span>|  
|`statements`|<span data-ttu-id="147a7-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="147a7-111">Optional.</span></span> <span data-ttu-id="147a7-112">Una o más instrucciones que siguen `While`, que se ejecutan cada vez que se `True` `condition`.</span><span class="sxs-lookup"><span data-stu-id="147a7-112">One or more statements following `While`, which run every time `condition` is `True`.</span></span>|  
|`Continue While`|<span data-ttu-id="147a7-113">Opcional.</span><span class="sxs-lookup"><span data-stu-id="147a7-113">Optional.</span></span> <span data-ttu-id="147a7-114">Transfiere el control a la siguiente iteración del bloque `While`.</span><span class="sxs-lookup"><span data-stu-id="147a7-114">Transfers control to the next iteration of the `While` block.</span></span>|  
|`Exit While`|<span data-ttu-id="147a7-115">Opcional.</span><span class="sxs-lookup"><span data-stu-id="147a7-115">Optional.</span></span> <span data-ttu-id="147a7-116">Transfiere el control fuera del bloque `While`.</span><span class="sxs-lookup"><span data-stu-id="147a7-116">Transfers control out of the `While` block.</span></span>|  
|`End While`|<span data-ttu-id="147a7-117">Requerido.</span><span class="sxs-lookup"><span data-stu-id="147a7-117">Required.</span></span> <span data-ttu-id="147a7-118">Termina la definición del bloque `While`.</span><span class="sxs-lookup"><span data-stu-id="147a7-118">Terminates the definition of the `While` block.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="147a7-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="147a7-119">Remarks</span></span>  
 <span data-ttu-id="147a7-120">Use una estructura de `While...End While` cuando desee repetir un conjunto de instrucciones un número indefinido de veces, siempre que una condición permanezca `True`.</span><span class="sxs-lookup"><span data-stu-id="147a7-120">Use a `While...End While` structure when you want to repeat a set of statements an indefinite number of times, as long as a condition remains `True`.</span></span> <span data-ttu-id="147a7-121">Si desea más flexibilidad con el punto de prueba de la condición o el resultado para probarlo, puede que prefiera la [acción... Instrucción Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="147a7-121">If you want more flexibility with where you test the condition or what result you test it for, you might prefer the [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span> <span data-ttu-id="147a7-122">Si desea repetir las instrucciones un número establecido de veces, la instrucción [for... La siguiente instrucción](../../../visual-basic/language-reference/statements/for-next-statement.md) suele ser una mejor opción.</span><span class="sxs-lookup"><span data-stu-id="147a7-122">If you want to repeat the statements a set number of times, the [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md) is usually a better choice.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="147a7-123">La palabra clave `While` también se usa en la. [.. Instrucción Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md), la [cláusula SKIP while](../../../visual-basic/language-reference/queries/skip-while-clause.md) y la [cláusula Take while](../../../visual-basic/language-reference/queries/take-while-clause.md).</span><span class="sxs-lookup"><span data-stu-id="147a7-123">The `While` keyword is also used in the [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md), the [Skip While Clause](../../../visual-basic/language-reference/queries/skip-while-clause.md) and the [Take While Clause](../../../visual-basic/language-reference/queries/take-while-clause.md).</span></span>  
  
 <span data-ttu-id="147a7-124">Si `condition` se `True`, todos los `statements` ejecutan hasta que se encuentre la instrucción `End While`.</span><span class="sxs-lookup"><span data-stu-id="147a7-124">If `condition` is `True`, all of the `statements` run until the `End While` statement is encountered.</span></span> <span data-ttu-id="147a7-125">A continuación, el control vuelve a la instrucción `While` y se comprueba de nuevo `condition`.</span><span class="sxs-lookup"><span data-stu-id="147a7-125">Control then returns to the `While` statement, and `condition` is again checked.</span></span> <span data-ttu-id="147a7-126">Si `condition` todavía está `True`, se repite el proceso.</span><span class="sxs-lookup"><span data-stu-id="147a7-126">If `condition` is still `True`, the process is repeated.</span></span> <span data-ttu-id="147a7-127">Si es `False`, el control pasa a la instrucción que sigue a la instrucción `End While`.</span><span class="sxs-lookup"><span data-stu-id="147a7-127">If it’s `False`, control passes to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="147a7-128">La instrucción `While` siempre comprueba la condición antes de iniciar el bucle.</span><span class="sxs-lookup"><span data-stu-id="147a7-128">The `While` statement always checks the condition before it starts the loop.</span></span> <span data-ttu-id="147a7-129">El bucle continúa mientras la condición permanece `True`.</span><span class="sxs-lookup"><span data-stu-id="147a7-129">Looping continues while the condition remains `True`.</span></span> <span data-ttu-id="147a7-130">Si `condition` se `False` la primera vez que se escribe el bucle, no se ejecuta ni siquiera una vez.</span><span class="sxs-lookup"><span data-stu-id="147a7-130">If `condition` is `False` when you first enter the loop, it doesn’t run even once.</span></span>  
  
 <span data-ttu-id="147a7-131">El `condition` suele ser el resultado de una comparación de dos valores, pero puede ser cualquier expresión que se evalúe como un valor de [tipo de datos booleano](../../../visual-basic/language-reference/data-types/boolean-data-type.md) (`True` o `False`).</span><span class="sxs-lookup"><span data-stu-id="147a7-131">The `condition` usually results from a comparison of two values, but it can be any expression that evaluates to a [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md) value (`True` or `False`).</span></span> <span data-ttu-id="147a7-132">Esta expresión puede incluir un valor de otro tipo de datos, como un tipo numérico, que se ha convertido en `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="147a7-132">This expression can include a value of another data type, such as a numeric type, that has been converted to `Boolean`.</span></span>  
  
 <span data-ttu-id="147a7-133">Puede anidar `While` bucles colocando un bucle dentro de otro.</span><span class="sxs-lookup"><span data-stu-id="147a7-133">You can nest `While` loops by placing one loop within another.</span></span> <span data-ttu-id="147a7-134">También puede anidar distintos tipos de estructuras de control entre sí.</span><span class="sxs-lookup"><span data-stu-id="147a7-134">You can also nest different kinds of control structures within one another.</span></span> <span data-ttu-id="147a7-135">Para obtener más información, vea [estructuras de control anidadas](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span><span class="sxs-lookup"><span data-stu-id="147a7-135">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
## <a name="exit-while"></a><span data-ttu-id="147a7-136">Salir</span><span class="sxs-lookup"><span data-stu-id="147a7-136">Exit While</span></span>  
 <span data-ttu-id="147a7-137">La instrucción [Exit while](../../../visual-basic/language-reference/statements/exit-statement.md) puede proporcionar otra manera de salir de un bucle `While`.</span><span class="sxs-lookup"><span data-stu-id="147a7-137">The [Exit While](../../../visual-basic/language-reference/statements/exit-statement.md) statement can provide another way to exit a `While` loop.</span></span> <span data-ttu-id="147a7-138">`Exit While` transfiere inmediatamente el control a la instrucción que sigue a la instrucción `End While`.</span><span class="sxs-lookup"><span data-stu-id="147a7-138">`Exit While` immediately transfers control to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="147a7-139">Normalmente se usa `Exit While` después de evaluar alguna condición (por ejemplo, en una estructura de `If...Then...Else`).</span><span class="sxs-lookup"><span data-stu-id="147a7-139">You typically use `Exit While` after some condition is evaluated (for example, in an `If...Then...Else` structure).</span></span> <span data-ttu-id="147a7-140">Es posible que desee salir de un bucle si detecta una condición que hace que sea innecesario o imposible continuar la iteración, como un valor erróneo o una solicitud de finalización.</span><span class="sxs-lookup"><span data-stu-id="147a7-140">You might want to exit a loop if you detect a condition that makes it unnecessary or impossible to continue iterating, such as an erroneous value or a termination request.</span></span> <span data-ttu-id="147a7-141">Puede utilizar `Exit While` al probar una condición que podría provocar un *bucle sin fin*, que es un bucle que podría ejecutar un número muy grande o incluso infinito de veces.</span><span class="sxs-lookup"><span data-stu-id="147a7-141">You can use `Exit While` when you test for a condition that could cause an *endless loop*, which is a loop that could run an extremely large or even infinite number of times.</span></span> <span data-ttu-id="147a7-142">Después, puede usar `Exit While` para escapar el bucle.</span><span class="sxs-lookup"><span data-stu-id="147a7-142">You can then use `Exit While` to escape the loop.</span></span>  
  
 <span data-ttu-id="147a7-143">Puede colocar cualquier número de instrucciones `Exit While` en cualquier parte del bucle `While`.</span><span class="sxs-lookup"><span data-stu-id="147a7-143">You can place any number of `Exit While` statements anywhere in the `While` loop.</span></span>  
  
 <span data-ttu-id="147a7-144">Cuando se utiliza en bucles `While` anidados, `Exit While` transfiere el control fuera del bucle más interno y en el siguiente nivel superior de anidamiento.</span><span class="sxs-lookup"><span data-stu-id="147a7-144">When used within nested `While` loops, `Exit While` transfers control out of the innermost loop and into the next higher level of nesting.</span></span>  
  
 <span data-ttu-id="147a7-145">La instrucción `Continue While` transfiere inmediatamente el control a la siguiente iteración del bucle.</span><span class="sxs-lookup"><span data-stu-id="147a7-145">The `Continue While` statement immediately transfers control to the next iteration of the loop.</span></span> <span data-ttu-id="147a7-146">Para obtener más información, vea [instrucción continue](../../../visual-basic/language-reference/statements/continue-statement.md).</span><span class="sxs-lookup"><span data-stu-id="147a7-146">For more information, see [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="147a7-147">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="147a7-147">Example</span></span>  
 <span data-ttu-id="147a7-148">En el ejemplo siguiente, las instrucciones del bucle continúan ejecutándose hasta que la variable de `index` sea mayor que 10.</span><span class="sxs-lookup"><span data-stu-id="147a7-148">In the following example, the statements in the loop continue to run until the `index` variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#171](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#171)]  
  
## <a name="example"></a><span data-ttu-id="147a7-149">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="147a7-149">Example</span></span>  
 <span data-ttu-id="147a7-150">En el ejemplo siguiente se muestra el uso de las instrucciones `Continue While` y `Exit While`.</span><span class="sxs-lookup"><span data-stu-id="147a7-150">The following example illustrates the use of the `Continue While` and `Exit While` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#172](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#172)]  
  
## <a name="example"></a><span data-ttu-id="147a7-151">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="147a7-151">Example</span></span>  
 <span data-ttu-id="147a7-152">En el ejemplo siguiente se leen todas las líneas de un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="147a7-152">The following example reads all lines in a text file.</span></span> <span data-ttu-id="147a7-153">El método <xref:System.IO.File.OpenText%2A> abre el archivo y devuelve un <xref:System.IO.StreamReader> que lee los caracteres.</span><span class="sxs-lookup"><span data-stu-id="147a7-153">The <xref:System.IO.File.OpenText%2A> method opens the file and returns a <xref:System.IO.StreamReader> that reads the characters.</span></span> <span data-ttu-id="147a7-154">En la condición `While`, el método <xref:System.IO.StreamReader.Peek%2A> de la `StreamReader` determina si el archivo contiene caracteres adicionales.</span><span class="sxs-lookup"><span data-stu-id="147a7-154">In the `While` condition, the <xref:System.IO.StreamReader.Peek%2A> method of the `StreamReader` determines whether the file contains additional characters.</span></span>  
  
 [!code-vb[VbVbalrStatements#173](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#173)]  
  
## <a name="see-also"></a><span data-ttu-id="147a7-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="147a7-155">See also</span></span>

- [<span data-ttu-id="147a7-156">Estructuras de bucle</span><span class="sxs-lookup"><span data-stu-id="147a7-156">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="147a7-157">Do...Loop (instrucción)</span><span class="sxs-lookup"><span data-stu-id="147a7-157">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="147a7-158">For...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="147a7-158">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="147a7-159">Boolean (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="147a7-159">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [<span data-ttu-id="147a7-160">Estructuras de control anidadas</span><span class="sxs-lookup"><span data-stu-id="147a7-160">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="147a7-161">Exit (instrucción)</span><span class="sxs-lookup"><span data-stu-id="147a7-161">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="147a7-162">Continue (instrucción)</span><span class="sxs-lookup"><span data-stu-id="147a7-162">Continue Statement</span></span>](../../../visual-basic/language-reference/statements/continue-statement.md)
