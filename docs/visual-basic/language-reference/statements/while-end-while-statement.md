---
description: 'Más información acerca de: while... End while (instrucción Visual Basic)'
title: Instrucción While...End While
ms.date: 07/20/2015
f1_keywords:
- vb.While
- vb.While...EndWhile
helpviewer_keywords:
- While statement [Visual Basic], While...End While
- While statement [Visual Basic]
- While...End While statements [Visual Basic]
ms.assetid: b931d1ce-e8ed-44d8-a13d-92a4f5458a1e
ms.openlocfilehash: ab452e2d9446c9c44b952c6ebf026f7a6f9080cd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787583"
---
# <a name="whileend-while-statement-visual-basic"></a><span data-ttu-id="389a8-103">Instrucción While...End While (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="389a8-103">While...End While Statement (Visual Basic)</span></span>

<span data-ttu-id="389a8-104">Ejecuta una serie de instrucciones siempre que una condición determinada sea `True` .</span><span class="sxs-lookup"><span data-stu-id="389a8-104">Runs a series of statements as long as a given condition is `True`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="389a8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="389a8-105">Syntax</span></span>  
  
```vb  
While condition  
    [ statements ]  
    [ Continue While ]  
    [ statements ]  
    [ Exit While ]  
    [ statements ]  
End While  
```  
  
## <a name="parts"></a><span data-ttu-id="389a8-106">Partes</span><span class="sxs-lookup"><span data-stu-id="389a8-106">Parts</span></span>  
  
|<span data-ttu-id="389a8-107">Término</span><span class="sxs-lookup"><span data-stu-id="389a8-107">Term</span></span>|<span data-ttu-id="389a8-108">Definición</span><span class="sxs-lookup"><span data-stu-id="389a8-108">Definition</span></span>|  
|---|---|  
|`condition`|<span data-ttu-id="389a8-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="389a8-109">Required.</span></span> <span data-ttu-id="389a8-110">Expresión `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="389a8-110">`Boolean` expression.</span></span> <span data-ttu-id="389a8-111">Si `condition` es `Nothing` , Visual Basic lo trata como `False` .</span><span class="sxs-lookup"><span data-stu-id="389a8-111">If `condition` is `Nothing`, Visual Basic treats it as `False`.</span></span>|  
|`statements`|<span data-ttu-id="389a8-112">Opcional.</span><span class="sxs-lookup"><span data-stu-id="389a8-112">Optional.</span></span> <span data-ttu-id="389a8-113">Una o varias instrucciones siguientes `While` , que se ejecutan cada vez `condition` `True` .</span><span class="sxs-lookup"><span data-stu-id="389a8-113">One or more statements following `While`, which run every time `condition` is `True`.</span></span>|  
|`Continue While`|<span data-ttu-id="389a8-114">Opcional.</span><span class="sxs-lookup"><span data-stu-id="389a8-114">Optional.</span></span> <span data-ttu-id="389a8-115">Transfiere el control a la siguiente iteración del `While` bloque.</span><span class="sxs-lookup"><span data-stu-id="389a8-115">Transfers control to the next iteration of the `While` block.</span></span>|  
|`Exit While`|<span data-ttu-id="389a8-116">Opcional.</span><span class="sxs-lookup"><span data-stu-id="389a8-116">Optional.</span></span> <span data-ttu-id="389a8-117">Transfiere el control fuera del `While` bloque.</span><span class="sxs-lookup"><span data-stu-id="389a8-117">Transfers control out of the `While` block.</span></span>|  
|`End While`|<span data-ttu-id="389a8-118">Necesario.</span><span class="sxs-lookup"><span data-stu-id="389a8-118">Required.</span></span> <span data-ttu-id="389a8-119">Termina la definición del bloque `While`.</span><span class="sxs-lookup"><span data-stu-id="389a8-119">Terminates the definition of the `While` block.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="389a8-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="389a8-120">Remarks</span></span>  

 <span data-ttu-id="389a8-121">Use una `While...End While` estructura cuando desee repetir un conjunto de instrucciones un número indefinido de veces, siempre y cuando se mantenga una condición `True` .</span><span class="sxs-lookup"><span data-stu-id="389a8-121">Use a `While...End While` structure when you want to repeat a set of statements an indefinite number of times, as long as a condition remains `True`.</span></span> <span data-ttu-id="389a8-122">Si desea más flexibilidad con el punto de prueba de la condición o el resultado para probarlo, puede que prefiera la [acción... Instrucción Loop](do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="389a8-122">If you want more flexibility with where you test the condition or what result you test it for, you might prefer the [Do...Loop Statement](do-loop-statement.md).</span></span> <span data-ttu-id="389a8-123">Si desea repetir las instrucciones un número establecido de veces, la instrucción [for... La siguiente instrucción](for-next-statement.md) suele ser una mejor opción.</span><span class="sxs-lookup"><span data-stu-id="389a8-123">If you want to repeat the statements a set number of times, the [For...Next Statement](for-next-statement.md) is usually a better choice.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="389a8-124">La `While` palabra clave también se usa en la. [.. Instrucción Loop](do-loop-statement.md), la [cláusula SKIP while](../queries/skip-while-clause.md) y la [cláusula Take while](../queries/take-while-clause.md).</span><span class="sxs-lookup"><span data-stu-id="389a8-124">The `While` keyword is also used in the [Do...Loop Statement](do-loop-statement.md), the [Skip While Clause](../queries/skip-while-clause.md) and the [Take While Clause](../queries/take-while-clause.md).</span></span>  
  
 <span data-ttu-id="389a8-125">Si `condition` es `True` , todos los se `statements` ejecutan hasta que `End While` se encuentra la instrucción.</span><span class="sxs-lookup"><span data-stu-id="389a8-125">If `condition` is `True`, all of the `statements` run until the `End While` statement is encountered.</span></span> <span data-ttu-id="389a8-126">A continuación, el control vuelve a la `While` instrucción y `condition` se comprueba de nuevo.</span><span class="sxs-lookup"><span data-stu-id="389a8-126">Control then returns to the `While` statement, and `condition` is again checked.</span></span> <span data-ttu-id="389a8-127">Si `condition` todavía está `True` , el proceso se repite.</span><span class="sxs-lookup"><span data-stu-id="389a8-127">If `condition` is still `True`, the process is repeated.</span></span> <span data-ttu-id="389a8-128">Si es `False` , el control pasa a la instrucción que sigue a la `End While` instrucción.</span><span class="sxs-lookup"><span data-stu-id="389a8-128">If it’s `False`, control passes to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="389a8-129">La `While` instrucción siempre comprueba la condición antes de iniciar el bucle.</span><span class="sxs-lookup"><span data-stu-id="389a8-129">The `While` statement always checks the condition before it starts the loop.</span></span> <span data-ttu-id="389a8-130">El bucle continúa mientras se mantiene la condición `True` .</span><span class="sxs-lookup"><span data-stu-id="389a8-130">Looping continues while the condition remains `True`.</span></span> <span data-ttu-id="389a8-131">Si `condition` es `False` la primera vez que se escribe el bucle, no se ejecuta ni siquiera una vez.</span><span class="sxs-lookup"><span data-stu-id="389a8-131">If `condition` is `False` when you first enter the loop, it doesn’t run even once.</span></span>  
  
 <span data-ttu-id="389a8-132">Normalmente es el `condition` resultado de una comparación de dos valores, pero puede ser cualquier expresión que se evalúe como un valor de [tipo de datos booleano](../data-types/boolean-data-type.md) ( `True` o `False` ).</span><span class="sxs-lookup"><span data-stu-id="389a8-132">The `condition` usually results from a comparison of two values, but it can be any expression that evaluates to a [Boolean Data Type](../data-types/boolean-data-type.md) value (`True` or `False`).</span></span> <span data-ttu-id="389a8-133">Esta expresión puede incluir un valor de otro tipo de datos, como un tipo numérico, que se ha convertido en `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="389a8-133">This expression can include a value of another data type, such as a numeric type, that has been converted to `Boolean`.</span></span>  
  
 <span data-ttu-id="389a8-134">Puede anidar `While` bucles colocando un bucle dentro de otro.</span><span class="sxs-lookup"><span data-stu-id="389a8-134">You can nest `While` loops by placing one loop within another.</span></span> <span data-ttu-id="389a8-135">También puede anidar distintos tipos de estructuras de control entre sí.</span><span class="sxs-lookup"><span data-stu-id="389a8-135">You can also nest different kinds of control structures within one another.</span></span> <span data-ttu-id="389a8-136">Para obtener más información, vea [estructuras de control anidadas](../../programming-guide/language-features/control-flow/nested-control-structures.md).</span><span class="sxs-lookup"><span data-stu-id="389a8-136">For more information, see [Nested Control Structures](../../programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
## <a name="exit-while"></a><span data-ttu-id="389a8-137">Salir</span><span class="sxs-lookup"><span data-stu-id="389a8-137">Exit While</span></span>  

 <span data-ttu-id="389a8-138">La instrucción [Exit while](exit-statement.md) puede proporcionar otra manera de salir de un `While` bucle.</span><span class="sxs-lookup"><span data-stu-id="389a8-138">The [Exit While](exit-statement.md) statement can provide another way to exit a `While` loop.</span></span> <span data-ttu-id="389a8-139">`Exit While` transfiere inmediatamente el control a la instrucción que sigue a la `End While` instrucción.</span><span class="sxs-lookup"><span data-stu-id="389a8-139">`Exit While` immediately transfers control to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="389a8-140">Normalmente se utiliza `Exit While` después de evaluar alguna condición (por ejemplo, en una `If...Then...Else` estructura).</span><span class="sxs-lookup"><span data-stu-id="389a8-140">You typically use `Exit While` after some condition is evaluated (for example, in an `If...Then...Else` structure).</span></span> <span data-ttu-id="389a8-141">Es posible que desee salir de un bucle si detecta una condición que hace que sea innecesario o imposible continuar la iteración, como un valor erróneo o una solicitud de finalización.</span><span class="sxs-lookup"><span data-stu-id="389a8-141">You might want to exit a loop if you detect a condition that makes it unnecessary or impossible to continue iterating, such as an erroneous value or a termination request.</span></span> <span data-ttu-id="389a8-142">Puede usar `Exit While` al probar una condición que podría provocar un *bucle interminable*, que es un bucle que podría ejecutar un número muy grande o incluso infinito de veces.</span><span class="sxs-lookup"><span data-stu-id="389a8-142">You can use `Exit While` when you test for a condition that could cause an *endless loop*, which is a loop that could run an extremely large or even infinite number of times.</span></span> <span data-ttu-id="389a8-143">Después, puede usar `Exit While` para escapar el bucle.</span><span class="sxs-lookup"><span data-stu-id="389a8-143">You can then use `Exit While` to escape the loop.</span></span>  
  
 <span data-ttu-id="389a8-144">Puede colocar cualquier número de `Exit While` instrucciones en cualquier parte del `While` bucle.</span><span class="sxs-lookup"><span data-stu-id="389a8-144">You can place any number of `Exit While` statements anywhere in the `While` loop.</span></span>  
  
 <span data-ttu-id="389a8-145">Cuando se usa dentro de `While` bucles anidados, `Exit While` transfiere el control fuera del bucle más interno y en el siguiente nivel superior de anidamiento.</span><span class="sxs-lookup"><span data-stu-id="389a8-145">When used within nested `While` loops, `Exit While` transfers control out of the innermost loop and into the next higher level of nesting.</span></span>  
  
 <span data-ttu-id="389a8-146">La `Continue While` instrucción transfiere inmediatamente el control a la siguiente iteración del bucle.</span><span class="sxs-lookup"><span data-stu-id="389a8-146">The `Continue While` statement immediately transfers control to the next iteration of the loop.</span></span> <span data-ttu-id="389a8-147">Para obtener más información, vea [instrucción continue](continue-statement.md).</span><span class="sxs-lookup"><span data-stu-id="389a8-147">For more information, see [Continue Statement](continue-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="389a8-148">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="389a8-148">Example</span></span>  

 <span data-ttu-id="389a8-149">En el ejemplo siguiente, las instrucciones del bucle continúan ejecutándose hasta que la `index` variable es mayor que 10.</span><span class="sxs-lookup"><span data-stu-id="389a8-149">In the following example, the statements in the loop continue to run until the `index` variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#171](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#171)]  
  
## <a name="example"></a><span data-ttu-id="389a8-150">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="389a8-150">Example</span></span>  

 <span data-ttu-id="389a8-151">En el ejemplo siguiente se muestra el uso de `Continue While` las `Exit While` instrucciones y.</span><span class="sxs-lookup"><span data-stu-id="389a8-151">The following example illustrates the use of the `Continue While` and `Exit While` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#172](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#172)]  
  
## <a name="example"></a><span data-ttu-id="389a8-152">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="389a8-152">Example</span></span>  

 <span data-ttu-id="389a8-153">En el ejemplo siguiente se leen todas las líneas de un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="389a8-153">The following example reads all lines in a text file.</span></span> <span data-ttu-id="389a8-154">El <xref:System.IO.File.OpenText%2A> método abre el archivo y devuelve un <xref:System.IO.StreamReader> que lee los caracteres.</span><span class="sxs-lookup"><span data-stu-id="389a8-154">The <xref:System.IO.File.OpenText%2A> method opens the file and returns a <xref:System.IO.StreamReader> that reads the characters.</span></span> <span data-ttu-id="389a8-155">En la `While` condición, el <xref:System.IO.StreamReader.Peek%2A> método de `StreamReader` determina si el archivo contiene caracteres adicionales.</span><span class="sxs-lookup"><span data-stu-id="389a8-155">In the `While` condition, the <xref:System.IO.StreamReader.Peek%2A> method of the `StreamReader` determines whether the file contains additional characters.</span></span>  
  
 [!code-vb[VbVbalrStatements#173](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#173)]  
  
## <a name="see-also"></a><span data-ttu-id="389a8-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="389a8-156">See also</span></span>

- [<span data-ttu-id="389a8-157">Estructuras de bucle</span><span class="sxs-lookup"><span data-stu-id="389a8-157">Loop Structures</span></span>](../../programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="389a8-158">Instrucción Do...Loop</span><span class="sxs-lookup"><span data-stu-id="389a8-158">Do...Loop Statement</span></span>](do-loop-statement.md)
- [<span data-ttu-id="389a8-159">Instrucción For...Next</span><span class="sxs-lookup"><span data-stu-id="389a8-159">For...Next Statement</span></span>](for-next-statement.md)
- [<span data-ttu-id="389a8-160">Tipo de datos Boolean</span><span class="sxs-lookup"><span data-stu-id="389a8-160">Boolean Data Type</span></span>](../data-types/boolean-data-type.md)
- [<span data-ttu-id="389a8-161">Estructuras de control anidadas</span><span class="sxs-lookup"><span data-stu-id="389a8-161">Nested Control Structures</span></span>](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="389a8-162">Instrucción Exit</span><span class="sxs-lookup"><span data-stu-id="389a8-162">Exit Statement</span></span>](exit-statement.md)
- [<span data-ttu-id="389a8-163">Continue (instrucción)</span><span class="sxs-lookup"><span data-stu-id="389a8-163">Continue Statement</span></span>](continue-statement.md)
