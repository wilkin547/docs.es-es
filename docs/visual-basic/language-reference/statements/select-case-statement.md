---
description: 'Más información acerca de: seleccionar... Instrucción Case (Visual Basic)'
title: Instrucción Select...Case
ms.date: 07/20/2015
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
ms.openlocfilehash: 4f8edecd0a0b1afd59e182a372e308c3829a9b93
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99741138"
---
# <a name="selectcase-statement-visual-basic"></a><span data-ttu-id="0b04c-103">Instrucción Select...Case (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0b04c-103">Select...Case Statement (Visual Basic)</span></span>

<span data-ttu-id="0b04c-104">Ejecuta uno de varios grupos de instrucciones, dependiendo del valor de una expresión.</span><span class="sxs-lookup"><span data-stu-id="0b04c-104">Runs one of several groups of statements, depending on the value of an expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b04c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0b04c-105">Syntax</span></span>  
  
```vb  
Select [ Case ] testexpression  
    [ Case expressionlist  
        [ statements ] ]  
    [ Case Else  
        [ elsestatements ] ]  
End Select  
```  
  
## <a name="parts"></a><span data-ttu-id="0b04c-106">Partes</span><span class="sxs-lookup"><span data-stu-id="0b04c-106">Parts</span></span>  
  
|<span data-ttu-id="0b04c-107">Término</span><span class="sxs-lookup"><span data-stu-id="0b04c-107">Term</span></span>|<span data-ttu-id="0b04c-108">Definición</span><span class="sxs-lookup"><span data-stu-id="0b04c-108">Definition</span></span>|  
|---|---|  
|`testexpression`|<span data-ttu-id="0b04c-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="0b04c-109">Required.</span></span> <span data-ttu-id="0b04c-110">Expresión.</span><span class="sxs-lookup"><span data-stu-id="0b04c-110">Expression.</span></span> <span data-ttu-id="0b04c-111">Debe evaluarse como uno de los tipos de datos básicos ( `Boolean` , `Byte` , `Char` , `Date` , `Double` , `Decimal` , `Integer` , `Long` , `Object` , `SByte` , `Short` ,,,, `Single` `String` `UInteger` `ULong` y `UShort` ).</span><span class="sxs-lookup"><span data-stu-id="0b04c-111">Must evaluate to one of the elementary data types (`Boolean`, `Byte`, `Char`, `Date`, `Double`, `Decimal`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, and `UShort`).</span></span>|  
|`expressionlist`|<span data-ttu-id="0b04c-112">Obligatorio en una `Case` instrucción.</span><span class="sxs-lookup"><span data-stu-id="0b04c-112">Required in a `Case` statement.</span></span> <span data-ttu-id="0b04c-113">Lista de cláusulas de expresión que representan los valores de coincidencia para `testexpression` .</span><span class="sxs-lookup"><span data-stu-id="0b04c-113">List of expression clauses representing match values for `testexpression`.</span></span> <span data-ttu-id="0b04c-114">Las cláusulas de varias expresiones se separan mediante comas.</span><span class="sxs-lookup"><span data-stu-id="0b04c-114">Multiple expression clauses are separated by commas.</span></span> <span data-ttu-id="0b04c-115">Cada cláusula puede adoptar uno de los siguientes formatos:</span><span class="sxs-lookup"><span data-stu-id="0b04c-115">Each clause can take one of the following forms:</span></span><br /><br /> <span data-ttu-id="0b04c-116">-   *expression1* `To` *expresión2*</span><span class="sxs-lookup"><span data-stu-id="0b04c-116">-   *expression1* `To` *expression2*</span></span><br /><span data-ttu-id="0b04c-117">-[ `Is` ]  *expresión* de comparisonoperator</span><span class="sxs-lookup"><span data-stu-id="0b04c-117">-   [ `Is` ] *comparisonoperator* *expression*</span></span><br /><span data-ttu-id="0b04c-118">-   *Expresiones*</span><span class="sxs-lookup"><span data-stu-id="0b04c-118">-   *expression*</span></span><br /><br /> <span data-ttu-id="0b04c-119">Use la `To` palabra clave para especificar los límites de un intervalo de valores de coincidencia para `testexpression` .</span><span class="sxs-lookup"><span data-stu-id="0b04c-119">Use the `To` keyword to specify the boundaries of a range of match values for `testexpression`.</span></span> <span data-ttu-id="0b04c-120">El valor de `expression1` debe ser menor o igual que el valor de `expression2` .</span><span class="sxs-lookup"><span data-stu-id="0b04c-120">The value of `expression1` must be less than or equal to the value of `expression2`.</span></span><br /><br /> <span data-ttu-id="0b04c-121">Use la `Is` palabra clave con un operador de comparación ( `=` , `<>` , `<` , `<=` , `>` o `>=` ) para especificar una restricción en los valores de coincidencia para `testexpression` .</span><span class="sxs-lookup"><span data-stu-id="0b04c-121">Use the `Is` keyword with a comparison operator (`=`, `<>`, `<`, `<=`, `>`, or `>=`) to specify a restriction on the match values for `testexpression`.</span></span> <span data-ttu-id="0b04c-122">Si `Is` no se proporciona la palabra clave, se inserta automáticamente antes de *comparisonoperator*.</span><span class="sxs-lookup"><span data-stu-id="0b04c-122">If the `Is` keyword is not supplied, it is automatically inserted before *comparisonoperator*.</span></span><br /><br /> <span data-ttu-id="0b04c-123">La forma que especifica solo `expression` se trata como un caso especial del `Is` formulario donde *comparisonoperator* es el signo igual ( `=` ).</span><span class="sxs-lookup"><span data-stu-id="0b04c-123">The form specifying only `expression` is treated as a special case of the `Is` form where *comparisonoperator* is the equal sign (`=`).</span></span> <span data-ttu-id="0b04c-124">Este formulario se evalúa como `testexpression`  =  `expression` .</span><span class="sxs-lookup"><span data-stu-id="0b04c-124">This form is evaluated as `testexpression` = `expression`.</span></span><br /><br /> <span data-ttu-id="0b04c-125">Las expresiones de `expressionlist` pueden ser de cualquier tipo de datos, siempre que se puedan convertir implícitamente al tipo de `testexpression` y el adecuado `comparisonoperator` sea válido para los dos tipos con los que se usa.</span><span class="sxs-lookup"><span data-stu-id="0b04c-125">The expressions in `expressionlist` can be of any data type, provided they are implicitly convertible to the type of `testexpression` and the appropriate `comparisonoperator` is valid for the two types it is being used with.</span></span>|  
|`statements`|<span data-ttu-id="0b04c-126">Opcional.</span><span class="sxs-lookup"><span data-stu-id="0b04c-126">Optional.</span></span> <span data-ttu-id="0b04c-127">Una o más instrucciones que siguen a `Case` que se ejecutan si `testexpression` coincide con cualquier cláusula de `expressionlist` .</span><span class="sxs-lookup"><span data-stu-id="0b04c-127">One or more statements following `Case` that run if `testexpression` matches any clause in `expressionlist`.</span></span>|  
|`elsestatements`|<span data-ttu-id="0b04c-128">Opcional.</span><span class="sxs-lookup"><span data-stu-id="0b04c-128">Optional.</span></span> <span data-ttu-id="0b04c-129">Una o varias instrucciones que siguen a `Case Else` que se ejecutan si no `testexpression` coinciden con ninguna cláusula en `expressionlist` de cualquiera de las `Case` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="0b04c-129">One or more statements following `Case Else` that run if `testexpression` does not match any clause in the `expressionlist` of any of the `Case` statements.</span></span>|  
|`End Select`|<span data-ttu-id="0b04c-130">Finaliza la definición de la `Select` construcción... `Case` .</span><span class="sxs-lookup"><span data-stu-id="0b04c-130">Terminates the definition of the `Select`...`Case` construction.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b04c-131">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0b04c-131">Remarks</span></span>  

 <span data-ttu-id="0b04c-132">Si `testexpression` coincide con cualquier `Case` `expressionlist` cláusula, las instrucciones que siguen `Case` a esa instrucción se ejecutan hasta la siguiente `Case` `Case Else` instrucción, o `End Select` .</span><span class="sxs-lookup"><span data-stu-id="0b04c-132">If `testexpression` matches any `Case` `expressionlist` clause, the statements following that `Case` statement run up to the next `Case`, `Case Else`, or `End Select` statement.</span></span> <span data-ttu-id="0b04c-133">A continuación, el control pasa a la instrucción que sigue a `End Select` .</span><span class="sxs-lookup"><span data-stu-id="0b04c-133">Control then passes to the statement following `End Select`.</span></span> <span data-ttu-id="0b04c-134">Si `testexpression` coincide con una `expressionlist` cláusula en más de una `Case` cláusula, solo se ejecutan las instrucciones que siguen a la primera coincidencia.</span><span class="sxs-lookup"><span data-stu-id="0b04c-134">If `testexpression` matches an `expressionlist` clause in more than one `Case` clause, only the statements following the first match run.</span></span>  
  
 <span data-ttu-id="0b04c-135">La `Case Else` instrucción se utiliza para introducir `elsestatements` para que se ejecute si no se encuentra ninguna coincidencia entre las `testexpression` `expressionlist` cláusulas y en cualquiera de las demás `Case` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="0b04c-135">The `Case Else` statement is used to introduce the `elsestatements` to run if no match is found between the `testexpression` and an `expressionlist` clause in any of the other `Case` statements.</span></span> <span data-ttu-id="0b04c-136">Aunque no es necesario, es una buena idea tener una `Case Else` instrucción en la `Select Case` construcción para administrar los valores imprevistos `testexpression` .</span><span class="sxs-lookup"><span data-stu-id="0b04c-136">Although not required, it is a good idea to have a `Case Else` statement in your `Select Case` construction to handle unforeseen `testexpression` values.</span></span> <span data-ttu-id="0b04c-137">Si ninguna `Case` `expressionlist` cláusula coincide `testexpression` y no hay ninguna `Case Else` instrucción, el control pasa a la instrucción que sigue a `End Select` .</span><span class="sxs-lookup"><span data-stu-id="0b04c-137">If no `Case` `expressionlist` clause matches `testexpression` and there is no `Case Else` statement, control passes to the statement following `End Select`.</span></span>  
  
 <span data-ttu-id="0b04c-138">Puede usar varias expresiones o intervalos en cada `Case` cláusula.</span><span class="sxs-lookup"><span data-stu-id="0b04c-138">You can use multiple expressions or ranges in each `Case` clause.</span></span> <span data-ttu-id="0b04c-139">Por ejemplo, la siguiente línea es válida.</span><span class="sxs-lookup"><span data-stu-id="0b04c-139">For example, the following line is valid.</span></span>  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
> <span data-ttu-id="0b04c-140">La `Is` palabra clave usada en `Case` las `Case Else` instrucciones y no es igual que el [operador is](../operators/is-operator.md), que se usa para la comparación de referencia de objeto.</span><span class="sxs-lookup"><span data-stu-id="0b04c-140">The `Is` keyword used in the `Case` and `Case Else` statements is not the same as the [Is Operator](../operators/is-operator.md), which is used for object reference comparison.</span></span>  
  
 <span data-ttu-id="0b04c-141">Puede especificar intervalos y varias expresiones para las cadenas de caracteres.</span><span class="sxs-lookup"><span data-stu-id="0b04c-141">You can specify ranges and multiple expressions for character strings.</span></span> <span data-ttu-id="0b04c-142">En el ejemplo siguiente, `Case` coincide con cualquier cadena que sea exactamente igual a "manzanas", tiene un valor entre "NUTS" y "sopa" en orden alfabético, o contiene el mismo valor exacto que el valor actual de `testItem` .</span><span class="sxs-lookup"><span data-stu-id="0b04c-142">In the following example, `Case` matches any string that is exactly equal to "apples", has a value between "nuts" and "soup" in alphabetical order, or contains the exact same value as the current value of `testItem`.</span></span>  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 <span data-ttu-id="0b04c-143">La configuración de `Option Compare` puede afectar a las comparaciones de cadenas.</span><span class="sxs-lookup"><span data-stu-id="0b04c-143">The setting of `Option Compare` can affect string comparisons.</span></span> <span data-ttu-id="0b04c-144">En `Option Compare Text` , las cadenas "manzanas" y "manzanas" se comparan como iguales, pero en `Option Compare Binary` , no.</span><span class="sxs-lookup"><span data-stu-id="0b04c-144">Under `Option Compare Text`, the strings "Apples" and "apples" compare as equal, but under `Option Compare Binary`, they do not.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0b04c-145">Una `Case` instrucción con varias cláusulas puede presentar un comportamiento conocido como *cortocircuito*.</span><span class="sxs-lookup"><span data-stu-id="0b04c-145">A `Case` statement with multiple clauses can exhibit behavior known as *short-circuiting*.</span></span> <span data-ttu-id="0b04c-146">Visual Basic evalúa las cláusulas de izquierda a derecha y, si una genera una coincidencia con `testexpression` , no se evalúan las cláusulas restantes.</span><span class="sxs-lookup"><span data-stu-id="0b04c-146">Visual Basic evaluates the clauses from left to right, and if one produces a match with `testexpression`, the remaining clauses are not evaluated.</span></span> <span data-ttu-id="0b04c-147">El cortocircuito puede mejorar el rendimiento, pero puede producir resultados inesperados si espera que se evalúen todas las expresiones de `expressionlist` .</span><span class="sxs-lookup"><span data-stu-id="0b04c-147">Short-circuiting can improve performance, but it can produce unexpected results if you are expecting every expression in `expressionlist` to be evaluated.</span></span> <span data-ttu-id="0b04c-148">Para obtener más información sobre el cortocircuito, vea [Expresiones booleanas](../../programming-guide/language-features/operators-and-expressions/boolean-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="0b04c-148">For more information on short-circuiting, see [Boolean Expressions](../../programming-guide/language-features/operators-and-expressions/boolean-expressions.md).</span></span>  
  
 <span data-ttu-id="0b04c-149">Si el código dentro de `Case` un `Case Else` bloque de instrucciones o no necesita ejecutar más instrucciones en el bloque, puede salir del bloque mediante la `Exit Select` instrucción.</span><span class="sxs-lookup"><span data-stu-id="0b04c-149">If the code within a `Case` or `Case Else` statement block does not need to run any more of the statements in the block, it can exit the block by using the `Exit Select` statement.</span></span> <span data-ttu-id="0b04c-150">Esto transfiere el control inmediatamente a la instrucción que sigue a `End Select` .</span><span class="sxs-lookup"><span data-stu-id="0b04c-150">This transfers control immediately to the statement following `End Select`.</span></span>  
  
 <span data-ttu-id="0b04c-151">`Select Case` las construcciones se pueden anidar.</span><span class="sxs-lookup"><span data-stu-id="0b04c-151">`Select Case` constructions can be nested.</span></span> <span data-ttu-id="0b04c-152">Cada construcción anidada `Select Case` debe tener una `End Select` instrucción coincidente y debe estar contenida completamente dentro de un único `Case` `Case Else` bloque de instrucciones o de la `Select Case` construcción externa en la que está anidada.</span><span class="sxs-lookup"><span data-stu-id="0b04c-152">Each nested `Select Case` construction must have a matching `End Select` statement and must be completely contained within a single `Case` or `Case Else` statement block of the outer `Select Case` construction within which it is nested.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b04c-153">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0b04c-153">Example</span></span>  

 <span data-ttu-id="0b04c-154">En el ejemplo siguiente se usa una `Select Case` construcción para escribir una línea que se corresponde con el valor de la variable `number` .</span><span class="sxs-lookup"><span data-stu-id="0b04c-154">The following example uses a `Select Case` construction to write a line corresponding to the value of the variable `number`.</span></span> <span data-ttu-id="0b04c-155">La segunda `Case` instrucción contiene el valor que coincide con el valor actual de `number` , por lo que se ejecuta la instrucción que escribe "between 6 and 8, inclusive".</span><span class="sxs-lookup"><span data-stu-id="0b04c-155">The second `Case` statement contains the value that matches the current value of `number`, so the statement that writes "Between 6 and 8, inclusive" runs.</span></span>  
  
 [!code-vb[VbVbalrStatements#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#54)]  
  
## <a name="see-also"></a><span data-ttu-id="0b04c-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b04c-156">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- [<span data-ttu-id="0b04c-157">End (instrucción)</span><span class="sxs-lookup"><span data-stu-id="0b04c-157">End Statement</span></span>](end-statement.md)
- [<span data-ttu-id="0b04c-158">Instrucción If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="0b04c-158">If...Then...Else Statement</span></span>](if-then-else-statement.md)
- [<span data-ttu-id="0b04c-159">Option Compare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="0b04c-159">Option Compare Statement</span></span>](option-compare-statement.md)
- [<span data-ttu-id="0b04c-160">Instrucción Exit</span><span class="sxs-lookup"><span data-stu-id="0b04c-160">Exit Statement</span></span>](exit-statement.md)
