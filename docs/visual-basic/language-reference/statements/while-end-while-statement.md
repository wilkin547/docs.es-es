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
ms.openlocfilehash: 00ca0ad24231128b25a988921386d6bd3265e9a0
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58843718"
---
# <a name="whileend-while-statement-visual-basic"></a><span data-ttu-id="73a5e-102">Instrucción While...End While (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="73a5e-102">While...End While Statement (Visual Basic)</span></span>
<span data-ttu-id="73a5e-103">Ejecuta una serie de instrucciones mientras una condición dada sea `True`.</span><span class="sxs-lookup"><span data-stu-id="73a5e-103">Runs a series of statements as long as a given condition is `True`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73a5e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="73a5e-104">Syntax</span></span>  
  
```  
While condition  
    [ statements ]  
    [ Continue While ]  
    [ statements ]  
    [ Exit While ]  
    [ statements ]  
End While  
```  
  
## <a name="parts"></a><span data-ttu-id="73a5e-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="73a5e-105">Parts</span></span>  
  
|<span data-ttu-id="73a5e-106">Término</span><span class="sxs-lookup"><span data-stu-id="73a5e-106">Term</span></span>|<span data-ttu-id="73a5e-107">de esquema JSON</span><span class="sxs-lookup"><span data-stu-id="73a5e-107">Definition</span></span>|  
|---|---|  
|`condition`|<span data-ttu-id="73a5e-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="73a5e-108">Required.</span></span> <span data-ttu-id="73a5e-109">`Boolean` expresión.</span><span class="sxs-lookup"><span data-stu-id="73a5e-109">`Boolean` expression.</span></span> <span data-ttu-id="73a5e-110">Si `condition` es `Nothing`, Visual Basic lo trata como `False`.</span><span class="sxs-lookup"><span data-stu-id="73a5e-110">If `condition` is `Nothing`, Visual Basic treats it as `False`.</span></span>|  
|`statements`|<span data-ttu-id="73a5e-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="73a5e-111">Optional.</span></span> <span data-ttu-id="73a5e-112">Uno o más instrucciones que siguen `While`, que ejecutará cada vez `condition` es `True`.</span><span class="sxs-lookup"><span data-stu-id="73a5e-112">One or more statements following `While`, which run every time `condition` is `True`.</span></span>|  
|`Continue While`|<span data-ttu-id="73a5e-113">Opcional.</span><span class="sxs-lookup"><span data-stu-id="73a5e-113">Optional.</span></span> <span data-ttu-id="73a5e-114">Transfiere el control a la siguiente iteración de la `While` bloque.</span><span class="sxs-lookup"><span data-stu-id="73a5e-114">Transfers control to the next iteration of the `While` block.</span></span>|  
|`Exit While`|<span data-ttu-id="73a5e-115">Opcional.</span><span class="sxs-lookup"><span data-stu-id="73a5e-115">Optional.</span></span> <span data-ttu-id="73a5e-116">Transfiere el control fuera de la `While` bloque.</span><span class="sxs-lookup"><span data-stu-id="73a5e-116">Transfers control out of the `While` block.</span></span>|  
|`End While`|<span data-ttu-id="73a5e-117">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="73a5e-117">Required.</span></span> <span data-ttu-id="73a5e-118">Termina la definición del bloque `While`.</span><span class="sxs-lookup"><span data-stu-id="73a5e-118">Terminates the definition of the `While` block.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73a5e-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="73a5e-119">Remarks</span></span>  
 <span data-ttu-id="73a5e-120">Use un `While...End While` estructura cuando desea repetir un conjunto de instrucciones un número indefinido de veces, mientras una condición permanezca `True`.</span><span class="sxs-lookup"><span data-stu-id="73a5e-120">Use a `While...End While` structure when you want to repeat a set of statements an indefinite number of times, as long as a condition remains `True`.</span></span> <span data-ttu-id="73a5e-121">Si desea más flexibilidad con en el que probar la condición o resultado para el que la prueba, es posible que prefiera el [hacer... Instrucción de bucle](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="73a5e-121">If you want more flexibility with where you test the condition or what result you test it for, you might prefer the [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span> <span data-ttu-id="73a5e-122">Si desea repetir las instrucciones de un número determinado de veces, el [para... Instrucción Next](../../../visual-basic/language-reference/statements/for-next-statement.md) suele ser una opción mejor.</span><span class="sxs-lookup"><span data-stu-id="73a5e-122">If you want to repeat the statements a set number of times, the [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md) is usually a better choice.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="73a5e-123">El `While` también se utiliza la palabra clave en el [hacer... Instrucción de bucle](../../../visual-basic/language-reference/statements/do-loop-statement.md), el [cláusula Skip While](../../../visual-basic/language-reference/queries/skip-while-clause.md) y [Take While cláusula](../../../visual-basic/language-reference/queries/take-while-clause.md).</span><span class="sxs-lookup"><span data-stu-id="73a5e-123">The `While` keyword is also used in the [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md), the [Skip While Clause](../../../visual-basic/language-reference/queries/skip-while-clause.md) and the [Take While Clause](../../../visual-basic/language-reference/queries/take-while-clause.md).</span></span>  
  
 <span data-ttu-id="73a5e-124">Si `condition` es `True`, todos los de la `statements` ejecución hasta que el `End While` se encuentra la instrucción.</span><span class="sxs-lookup"><span data-stu-id="73a5e-124">If `condition` is `True`, all of the `statements` run until the `End While` statement is encountered.</span></span> <span data-ttu-id="73a5e-125">Controlar, a continuación, vuelve a la `While` instrucción, y `condition` se comprueba de nuevo.</span><span class="sxs-lookup"><span data-stu-id="73a5e-125">Control then returns to the `While` statement, and `condition` is again checked.</span></span> <span data-ttu-id="73a5e-126">Si `condition` sigue siendo `True`, el proceso se repite.</span><span class="sxs-lookup"><span data-stu-id="73a5e-126">If `condition` is still `True`, the process is repeated.</span></span> <span data-ttu-id="73a5e-127">Si tiene `False`, el control pasa a la instrucción que sigue la `End While` instrucción.</span><span class="sxs-lookup"><span data-stu-id="73a5e-127">If it’s `False`, control passes to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="73a5e-128">El `While` instrucción siempre comprueba la condición antes de iniciar el bucle.</span><span class="sxs-lookup"><span data-stu-id="73a5e-128">The `While` statement always checks the condition before it starts the loop.</span></span> <span data-ttu-id="73a5e-129">Ejecución en bucle continúa mientras la condición permanezca `True`.</span><span class="sxs-lookup"><span data-stu-id="73a5e-129">Looping continues while the condition remains `True`.</span></span> <span data-ttu-id="73a5e-130">Si `condition` es `False` cuando se escribe por primera vez el bucle, no se ejecuta ni siquiera una vez.</span><span class="sxs-lookup"><span data-stu-id="73a5e-130">If `condition` is `False` when you first enter the loop, it doesn’t run even once.</span></span>  
  
 <span data-ttu-id="73a5e-131">El `condition` normalmente los resultados de una comparación de dos valores, pero pueden ser cualquier expresión que se evalúa como un [tipo de datos Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md) valor (`True` o `False`).</span><span class="sxs-lookup"><span data-stu-id="73a5e-131">The `condition` usually results from a comparison of two values, but it can be any expression that evaluates to a [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md) value (`True` or `False`).</span></span> <span data-ttu-id="73a5e-132">Esta expresión puede incluir un valor de otro tipo de datos, como un tipo numérico, que se ha convertido en `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="73a5e-132">This expression can include a value of another data type, such as a numeric type, that has been converted to `Boolean`.</span></span>  
  
 <span data-ttu-id="73a5e-133">Puede anidar `While` bucles colocando un bucle dentro de otra.</span><span class="sxs-lookup"><span data-stu-id="73a5e-133">You can nest `While` loops by placing one loop within another.</span></span> <span data-ttu-id="73a5e-134">También puede anidar diferentes tipos de estructuras de control entre sí.</span><span class="sxs-lookup"><span data-stu-id="73a5e-134">You can also nest different kinds of control structures within one another.</span></span> <span data-ttu-id="73a5e-135">Para obtener más información, consulte [estructuras de Control anidadas](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span><span class="sxs-lookup"><span data-stu-id="73a5e-135">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
## <a name="exit-while"></a><span data-ttu-id="73a5e-136">Salida al</span><span class="sxs-lookup"><span data-stu-id="73a5e-136">Exit While</span></span>  
 <span data-ttu-id="73a5e-137">El [salir mientras](../../../visual-basic/language-reference/statements/exit-statement.md) instrucción puede proporcionar otra manera de salir de un `While` bucle.</span><span class="sxs-lookup"><span data-stu-id="73a5e-137">The [Exit While](../../../visual-basic/language-reference/statements/exit-statement.md) statement can provide another way to exit a `While` loop.</span></span> <span data-ttu-id="73a5e-138">`Exit While` transfiere el control a la instrucción que sigue inmediatamente el `End While` instrucción.</span><span class="sxs-lookup"><span data-stu-id="73a5e-138">`Exit While` immediately transfers control to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="73a5e-139">Se suele usar `Exit While` después de que se evalúa alguna condición (por ejemplo, en un `If...Then...Else` estructura).</span><span class="sxs-lookup"><span data-stu-id="73a5e-139">You typically use `Exit While` after some condition is evaluated (for example, in an `If...Then...Else` structure).</span></span> <span data-ttu-id="73a5e-140">Es posible que desee salir de un bucle si detecta una condición que hace innecesario o imposible continuar la iteración, por ejemplo, un valor erróneo o una solicitud de finalización.</span><span class="sxs-lookup"><span data-stu-id="73a5e-140">You might want to exit a loop if you detect a condition that makes it unnecessary or impossible to continue iterating, such as an erroneous value or a termination request.</span></span> <span data-ttu-id="73a5e-141">Puede usar `Exit While` cuando se prueba una condición que podría provocar un *bucle sin fin*, que es un bucle que podría ejecutar un número muy grande o incluso infinito de veces.</span><span class="sxs-lookup"><span data-stu-id="73a5e-141">You can use `Exit While` when you test for a condition that could cause an *endless loop*, which is a loop that could run an extremely large or even infinite number of times.</span></span> <span data-ttu-id="73a5e-142">A continuación, puede usar `Exit While` para salir del bucle.</span><span class="sxs-lookup"><span data-stu-id="73a5e-142">You can then use `Exit While` to escape the loop.</span></span>  
  
 <span data-ttu-id="73a5e-143">Puede colocar cualquier número de `Exit While` instrucciones en cualquier lugar en el `While` bucle.</span><span class="sxs-lookup"><span data-stu-id="73a5e-143">You can place any number of `Exit While` statements anywhere in the `While` loop.</span></span>  
  
 <span data-ttu-id="73a5e-144">Cuando se usan anidados dentro `While` bucles, `Exit While` transfiere el control fuera del bucle más interno y en el siguiente nivel más alto de anidamiento.</span><span class="sxs-lookup"><span data-stu-id="73a5e-144">When used within nested `While` loops, `Exit While` transfers control out of the innermost loop and into the next higher level of nesting.</span></span>  
  
 <span data-ttu-id="73a5e-145">El `Continue While` instrucción transfiere el control inmediatamente a la siguiente iteración del bucle.</span><span class="sxs-lookup"><span data-stu-id="73a5e-145">The `Continue While` statement immediately transfers control to the next iteration of the loop.</span></span> <span data-ttu-id="73a5e-146">Para obtener más información, consulte [instrucción Continue](../../../visual-basic/language-reference/statements/continue-statement.md).</span><span class="sxs-lookup"><span data-stu-id="73a5e-146">For more information, see [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="73a5e-147">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="73a5e-147">Example</span></span>  
 <span data-ttu-id="73a5e-148">En el ejemplo siguiente, las instrucciones en el bucle continúen ejecutándose hasta el `index` variable es mayor que 10.</span><span class="sxs-lookup"><span data-stu-id="73a5e-148">In the following example, the statements in the loop continue to run until the `index` variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#171](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#171)]  
  
## <a name="example"></a><span data-ttu-id="73a5e-149">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="73a5e-149">Example</span></span>  
 <span data-ttu-id="73a5e-150">El ejemplo siguiente muestra el uso de la `Continue While` y `Exit While` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="73a5e-150">The following example illustrates the use of the `Continue While` and `Exit While` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#172](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#172)]  
  
## <a name="example"></a><span data-ttu-id="73a5e-151">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="73a5e-151">Example</span></span>  
 <span data-ttu-id="73a5e-152">El ejemplo siguiente lee todas las líneas en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="73a5e-152">The following example reads all lines in a text file.</span></span> <span data-ttu-id="73a5e-153">El <xref:System.IO.File.OpenText%2A> método abre el archivo y devuelve un <xref:System.IO.StreamReader> que lee los caracteres.</span><span class="sxs-lookup"><span data-stu-id="73a5e-153">The <xref:System.IO.File.OpenText%2A> method opens the file and returns a <xref:System.IO.StreamReader> that reads the characters.</span></span> <span data-ttu-id="73a5e-154">En el `While` condición, el <xref:System.IO.StreamReader.Peek%2A> método de la `StreamReader` determina si el archivo contiene caracteres adicionales.</span><span class="sxs-lookup"><span data-stu-id="73a5e-154">In the `While` condition, the <xref:System.IO.StreamReader.Peek%2A> method of the `StreamReader` determines whether the file contains additional characters.</span></span>  
  
 [!code-vb[VbVbalrStatements#173](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#173)]  
  
## <a name="see-also"></a><span data-ttu-id="73a5e-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="73a5e-155">See also</span></span>

- [<span data-ttu-id="73a5e-156">Estructuras de bucle</span><span class="sxs-lookup"><span data-stu-id="73a5e-156">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="73a5e-157">Do...Loop (instrucción)</span><span class="sxs-lookup"><span data-stu-id="73a5e-157">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="73a5e-158">For...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="73a5e-158">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="73a5e-159">Boolean (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="73a5e-159">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [<span data-ttu-id="73a5e-160">Estructuras de control anidadas</span><span class="sxs-lookup"><span data-stu-id="73a5e-160">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="73a5e-161">Exit (instrucción)</span><span class="sxs-lookup"><span data-stu-id="73a5e-161">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="73a5e-162">Continue (instrucción)</span><span class="sxs-lookup"><span data-stu-id="73a5e-162">Continue Statement</span></span>](../../../visual-basic/language-reference/statements/continue-statement.md)
