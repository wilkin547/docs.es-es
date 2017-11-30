---
title: "Instrucción Select...Case (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Select
- vb.Case
helpviewer_keywords:
- Select statement [Visual Basic]
- Case statement [Visual Basic]
- Select...Case statements
- conditional statements [Visual Basic], Select Case
- control flow [Visual Basic], branching
- Else keyword [Visual Basic], in Select...Case statements
- execution [Visual Basic], conditional
- To keyword [Visual Basic], in Select...Case statements
- Select Case statement [Visual Basic], Select...Case
- Select statement [Visual Basic], Select...Case
- Is operator [Visual Basic], in Select...Case statements
- branching [Visual Basic], conditional
- Case Else statement [Visual Basic], Select...Case
- End keyword [Visual Basic], Select Case statements
- Case statement [Visual Basic], Select...Case
ms.assetid: 68877b65-5419-4bf0-a465-20cd0e4c7d44
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a7527763a05ec32af88c6ba66ef717d839c33154
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="selectcase-statement-visual-basic"></a><span data-ttu-id="2eda7-102">Instrucción Select...Case (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2eda7-102">Select...Case Statement (Visual Basic)</span></span>
<span data-ttu-id="2eda7-103">Ejecuta uno de varios grupos de instrucciones, dependiendo del valor de una expresión.</span><span class="sxs-lookup"><span data-stu-id="2eda7-103">Runs one of several groups of statements, depending on the value of an expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2eda7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2eda7-104">Syntax</span></span>  
  
```  
Select [ Case ] testexpression  
    [ Case expressionlist  
        [ statements ] ]  
    [ Case Else  
        [ elsestatements ] ]  
End Select  
```  
  
## <a name="parts"></a><span data-ttu-id="2eda7-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="2eda7-105">Parts</span></span>  
  
|<span data-ttu-id="2eda7-106">Término</span><span class="sxs-lookup"><span data-stu-id="2eda7-106">Term</span></span>|<span data-ttu-id="2eda7-107">Definición</span><span class="sxs-lookup"><span data-stu-id="2eda7-107">Definition</span></span>|  
|---|---|  
|`testexpression`|<span data-ttu-id="2eda7-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="2eda7-108">Required.</span></span> <span data-ttu-id="2eda7-109">Expresión.</span><span class="sxs-lookup"><span data-stu-id="2eda7-109">Expression.</span></span> <span data-ttu-id="2eda7-110">Se debe evaluar como uno de los tipos de datos básicos (`Boolean`, `Byte`, `Char`, `Date`, `Double`, `Decimal`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, y `UShort`).</span><span class="sxs-lookup"><span data-stu-id="2eda7-110">Must evaluate to one of the elementary data types (`Boolean`, `Byte`, `Char`, `Date`, `Double`, `Decimal`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, and `UShort`).</span></span>|  
|`expressionlist`|<span data-ttu-id="2eda7-111">Necesario en un `Case` instrucción.</span><span class="sxs-lookup"><span data-stu-id="2eda7-111">Required in a `Case` statement.</span></span> <span data-ttu-id="2eda7-112">Lista de cláusulas de expresiones que representan valores que coinciden para `testexpression`.</span><span class="sxs-lookup"><span data-stu-id="2eda7-112">List of expression clauses representing match values for `testexpression`.</span></span> <span data-ttu-id="2eda7-113">Cláusulas de varias expresiones se separan mediante comas.</span><span class="sxs-lookup"><span data-stu-id="2eda7-113">Multiple expression clauses are separated by commas.</span></span> <span data-ttu-id="2eda7-114">Cada cláusula puede realizar una de las siguientes formas:</span><span class="sxs-lookup"><span data-stu-id="2eda7-114">Each clause can take one of the following forms:</span></span><br /><br /> <span data-ttu-id="2eda7-115">-   *expression1* `To` *expression2*</span><span class="sxs-lookup"><span data-stu-id="2eda7-115">-   *expression1* `To` *expression2*</span></span><br /><span data-ttu-id="2eda7-116">-[ `Is` ] *comparisonoperator* *expresión*</span><span class="sxs-lookup"><span data-stu-id="2eda7-116">-   [ `Is` ] *comparisonoperator* *expression*</span></span><br /><span data-ttu-id="2eda7-117">-   *expresión*</span><span class="sxs-lookup"><span data-stu-id="2eda7-117">-   *expression*</span></span><br /><br /> <span data-ttu-id="2eda7-118">Use la `To` palabra clave para especificar los límites de un intervalo de coincidencia de los valores de `testexpression`.</span><span class="sxs-lookup"><span data-stu-id="2eda7-118">Use the `To` keyword to specify the boundaries of a range of match values for `testexpression`.</span></span> <span data-ttu-id="2eda7-119">El valor de `expression1` debe ser menor o igual que el valor de `expression2`.</span><span class="sxs-lookup"><span data-stu-id="2eda7-119">The value of `expression1` must be less than or equal to the value of `expression2`.</span></span><br /><br /> <span data-ttu-id="2eda7-120">Use la `Is` palabra clave con un operador de comparación (`=`, `<>`, `<`, `<=`, `>`, o `>=`) para especificar una restricción en los valores coincidentes para `testexpression`.</span><span class="sxs-lookup"><span data-stu-id="2eda7-120">Use the `Is` keyword with a comparison operator (`=`, `<>`, `<`, `<=`, `>`, or `>=`) to specify a restriction on the match values for `testexpression`.</span></span> <span data-ttu-id="2eda7-121">Si el `Is` palabra clave no se proporciona, se inserta automáticamente antes de *comparisonoperator*.</span><span class="sxs-lookup"><span data-stu-id="2eda7-121">If the `Is` keyword is not supplied, it is automatically inserted before *comparisonoperator*.</span></span><br /><br /> <span data-ttu-id="2eda7-122">La forma de especificar sólo `expression` se trata como un caso especial de la `Is` forman where *comparisonoperator* es el signo igual (`=`).</span><span class="sxs-lookup"><span data-stu-id="2eda7-122">The form specifying only `expression` is treated as a special case of the `Is` form where *comparisonoperator* is the equal sign (`=`).</span></span> <span data-ttu-id="2eda7-123">Este formulario se evalúa como `testexpression`  =  `expression`.</span><span class="sxs-lookup"><span data-stu-id="2eda7-123">This form is evaluated as `testexpression` = `expression`.</span></span><br /><br /> <span data-ttu-id="2eda7-124">Las expresiones de `expressionlist` pueden ser de cualquier tipo de datos, siempre que se pueden convertir implícitamente al tipo de `testexpression` y la correspondiente `comparisonoperator` es válido para usarlo con los tipos de dos.</span><span class="sxs-lookup"><span data-stu-id="2eda7-124">The expressions in `expressionlist` can be of any data type, provided they are implicitly convertible to the type of `testexpression` and the appropriate `comparisonoperator` is valid for the two types it is being used with.</span></span>|  
|`statements`|<span data-ttu-id="2eda7-125">Opcional.</span><span class="sxs-lookup"><span data-stu-id="2eda7-125">Optional.</span></span> <span data-ttu-id="2eda7-126">Uno o más instrucciones que siguen `Case` que se ejecutarán si `testexpression` coincide con cualquier cláusula en `expressionlist`.</span><span class="sxs-lookup"><span data-stu-id="2eda7-126">One or more statements following `Case` that run if `testexpression` matches any clause in `expressionlist`.</span></span>|  
|`elsestatements`|<span data-ttu-id="2eda7-127">Opcional.</span><span class="sxs-lookup"><span data-stu-id="2eda7-127">Optional.</span></span> <span data-ttu-id="2eda7-128">Uno o más instrucciones que siguen `Case Else` que se ejecutarán si `testexpression` no coincide con cualquier cláusula en la `expressionlist` de cualquiera de los `Case` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="2eda7-128">One or more statements following `Case Else` that run if `testexpression` does not match any clause in the `expressionlist` of any of the `Case` statements.</span></span>|  
|`End Select`|<span data-ttu-id="2eda7-129">Termina la definición de la `Select`... `Case` construcción.</span><span class="sxs-lookup"><span data-stu-id="2eda7-129">Terminates the definition of the `Select`...`Case` construction.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2eda7-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2eda7-130">Remarks</span></span>  
 <span data-ttu-id="2eda7-131">Si `testexpression` coincide con cualquier `Case` `expressionlist` cláusula, las instrucciones siguientes que `Case` ejecuta instrucción a la siguiente `Case`, `Case Else`, o `End Select` instrucción.</span><span class="sxs-lookup"><span data-stu-id="2eda7-131">If `testexpression` matches any `Case` `expressionlist` clause, the statements following that `Case` statement run up to the next `Case`, `Case Else`, or `End Select` statement.</span></span> <span data-ttu-id="2eda7-132">Después, el control pasa a la siguiente instrucción `End Select`.</span><span class="sxs-lookup"><span data-stu-id="2eda7-132">Control then passes to the statement following `End Select`.</span></span> <span data-ttu-id="2eda7-133">Si `testexpression` coincide con un `expressionlist` cláusula en más de una `Case` ejecutan de cláusula, solo las instrucciones que siguen a la primera coincidencia.</span><span class="sxs-lookup"><span data-stu-id="2eda7-133">If `testexpression` matches an `expressionlist` clause in more than one `Case` clause, only the statements following the first match run.</span></span>  
  
 <span data-ttu-id="2eda7-134">El `Case Else` instrucción se utiliza para introducir el `elsestatements` ejecutándose si se encuentra ninguna coincidencia entre el `testexpression` y un `expressionlist` cláusula en cualquiera de los demás `Case` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="2eda7-134">The `Case Else` statement is used to introduce the `elsestatements` to run if no match is found between the `testexpression` and an `expressionlist` clause in any of the other `Case` statements.</span></span> <span data-ttu-id="2eda7-135">Aunque no es necesario, es una buena idea tener un `Case Else` instrucción en su `Select Case` construcción controlen imprevistos `testexpression` valores.</span><span class="sxs-lookup"><span data-stu-id="2eda7-135">Although not required, it is a good idea to have a `Case Else` statement in your `Select Case` construction to handle unforeseen `testexpression` values.</span></span> <span data-ttu-id="2eda7-136">Si no hay ningún `Case` `expressionlist` coincide con la cláusula `testexpression` y no hay ningún `Case Else` instrucción, el control pasa a la siguiente instrucción `End Select`.</span><span class="sxs-lookup"><span data-stu-id="2eda7-136">If no `Case` `expressionlist` clause matches `testexpression` and there is no `Case Else` statement, control passes to the statement following `End Select`.</span></span>  
  
 <span data-ttu-id="2eda7-137">Se pueden utilizar varias expresiones o intervalos en cada `Case` cláusula.</span><span class="sxs-lookup"><span data-stu-id="2eda7-137">You can use multiple expressions or ranges in each `Case` clause.</span></span> <span data-ttu-id="2eda7-138">Por ejemplo, la siguiente línea es válida.</span><span class="sxs-lookup"><span data-stu-id="2eda7-138">For example, the following line is valid.</span></span>  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
>  <span data-ttu-id="2eda7-139">El `Is` palabra clave utilizada en el `Case` y `Case Else` instrucciones no es el mismo que el [operador Is](../../../visual-basic/language-reference/operators/is-operator.md), que se usa para la comparación de referencia de objeto.</span><span class="sxs-lookup"><span data-stu-id="2eda7-139">The `Is` keyword used in the `Case` and `Case Else` statements is not the same as the [Is Operator](../../../visual-basic/language-reference/operators/is-operator.md), which is used for object reference comparison.</span></span>  
  
 <span data-ttu-id="2eda7-140">Puede especificar intervalos y varias expresiones para cadenas de caracteres.</span><span class="sxs-lookup"><span data-stu-id="2eda7-140">You can specify ranges and multiple expressions for character strings.</span></span> <span data-ttu-id="2eda7-141">En el ejemplo siguiente, `Case` coincide con cualquier cadena que es exactamente igual a "apples", tiene un valor entre "otros frutos" y "sopa" en orden alfabético o contiene el mismo valor exacto que el valor actual de `testItem`.</span><span class="sxs-lookup"><span data-stu-id="2eda7-141">In the following example, `Case` matches any string that is exactly equal to "apples", has a value between "nuts" and "soup" in alphabetical order, or contains the exact same value as the current value of `testItem`.</span></span>  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 <span data-ttu-id="2eda7-142">La configuración de `Option Compare` puede afectar a las comparaciones de cadenas.</span><span class="sxs-lookup"><span data-stu-id="2eda7-142">The setting of `Option Compare` can affect string comparisons.</span></span> <span data-ttu-id="2eda7-143">En `Option Compare Text`, las cadenas "Apples" y "apples" se consideran iguales, pero en `Option Compare Binary`, no lo hace.</span><span class="sxs-lookup"><span data-stu-id="2eda7-143">Under `Option Compare Text`, the strings "Apples" and "apples" compare as equal, but under `Option Compare Binary`, they do not.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2eda7-144">A `Case` instrucción con varias cláusulas puede exhibir el comportamiento conocido como *evaluación "cortocircuitada"*.</span><span class="sxs-lookup"><span data-stu-id="2eda7-144">A `Case` statement with multiple clauses can exhibit behavior known as *short-circuiting*.</span></span> <span data-ttu-id="2eda7-145">Visual Basic evalúa las cláusulas de izquierda a derecha y, si uno produce una coincidencia con `testexpression`, no se evalúan las cláusulas restantes.</span><span class="sxs-lookup"><span data-stu-id="2eda7-145">Visual Basic evaluates the clauses from left to right, and if one produces a match with `testexpression`, the remaining clauses are not evaluated.</span></span> <span data-ttu-id="2eda7-146">Evaluación "cortocircuitada" puede mejorar el rendimiento, pero pueden producir resultados inesperados si se espera que todas las expresiones en `expressionlist` que se debe evaluar.</span><span class="sxs-lookup"><span data-stu-id="2eda7-146">Short-circuiting can improve performance, but it can produce unexpected results if you are expecting every expression in `expressionlist` to be evaluated.</span></span> <span data-ttu-id="2eda7-147">Para obtener más información sobre evaluación "cortocircuitada", consulte [expresiones booleanas](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="2eda7-147">For more information on short-circuiting, see [Boolean Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md).</span></span>  
  
 <span data-ttu-id="2eda7-148">Si el código dentro de un `Case` o `Case Else` no es necesario ejecutar más de las instrucciones en el bloque de bloque de instrucciones, puede salir del bloque mediante el uso de la `Exit Select` instrucción.</span><span class="sxs-lookup"><span data-stu-id="2eda7-148">If the code within a `Case` or `Case Else` statement block does not need to run any more of the statements in the block, it can exit the block by using the `Exit Select` statement.</span></span> <span data-ttu-id="2eda7-149">Esto transfiere el control inmediatamente a la siguiente instrucción `End Select`.</span><span class="sxs-lookup"><span data-stu-id="2eda7-149">This transfers control immediately to the statement following `End Select`.</span></span>  
  
 <span data-ttu-id="2eda7-150">`Select Case`construcciones se pueden anidar.</span><span class="sxs-lookup"><span data-stu-id="2eda7-150">`Select Case` constructions can be nested.</span></span> <span data-ttu-id="2eda7-151">Cada uno anidado `Select Case` construcción debe tener su correspondiente `End Select` instrucción y deben estar contenidos completamente dentro de una única `Case` o `Case Else` bloque de instrucciones de la externa `Select Case` construcción en el que está anidada.</span><span class="sxs-lookup"><span data-stu-id="2eda7-151">Each nested `Select Case` construction must have a matching `End Select` statement and must be completely contained within a single `Case` or `Case Else` statement block of the outer `Select Case` construction within which it is nested.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2eda7-152">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2eda7-152">Example</span></span>  
 <span data-ttu-id="2eda7-153">En el ejemplo siguiente se usa un `Select Case` construcción para escribir una línea correspondiente al valor de la variable `number`.</span><span class="sxs-lookup"><span data-stu-id="2eda7-153">The following example uses a `Select Case` construction to write a line corresponding to the value of the variable `number`.</span></span> <span data-ttu-id="2eda7-154">El segundo `Case` instrucción contiene el valor que coincide con el valor actual de `number`, por lo que la instrucción que escribe "entre 6 y 8, inclusive" se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="2eda7-154">The second `Case` statement contains the value that matches the current value of `number`, so the statement that writes "Between 6 and 8, inclusive" runs.</span></span>  
  
 [!code-vb[VbVbalrStatements#54](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/select-case-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="2eda7-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="2eda7-155">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Interaction.Choose%2A>  
 [<span data-ttu-id="2eda7-156">End (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2eda7-156">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)  
 [<span data-ttu-id="2eda7-157">If...Then...Else (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2eda7-157">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [<span data-ttu-id="2eda7-158">Option Compare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2eda7-158">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [<span data-ttu-id="2eda7-159">Exit (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2eda7-159">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
