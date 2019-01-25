---
title: Procedimiento Crear una expresión Lambda (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
ms.openlocfilehash: e7302304fe6c44b0143d7f12ec272d597b313fdd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54492428"
---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a><span data-ttu-id="a7d4c-102">Procedimiento Crear una expresión Lambda (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7d4c-102">How to: Create a Lambda Expression (Visual Basic)</span></span>
<span data-ttu-id="a7d4c-103">Un *expresión lambda* es una función o subrutina que no tiene un nombre.</span><span class="sxs-lookup"><span data-stu-id="a7d4c-103">A *lambda expression* is a function or subroutine that does not have a name.</span></span> <span data-ttu-id="a7d4c-104">Una expresión lambda puede usarse siempre que sea un tipo de delegado es válido.</span><span class="sxs-lookup"><span data-stu-id="a7d4c-104">A lambda expression can be used wherever a delegate type is valid.</span></span>  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a><span data-ttu-id="a7d4c-105">Para crear una función de la expresión lambda de línea</span><span class="sxs-lookup"><span data-stu-id="a7d4c-105">To create a single-line lambda expression function</span></span>  
  
1.  <span data-ttu-id="a7d4c-106">En cualquier situación donde se podría usar un tipo de delegado, escriba la palabra clave `Function`, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a7d4c-106">In any situation where a delegate type could be used, type the keyword `Function`, as in the following example:</span></span>  
  
     <span data-ttu-id="a7d4c-107">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="a7d4c-107">`Dim add1 =`   `Function`</span></span>  
  
2.  <span data-ttu-id="a7d4c-108">Entre paréntesis, directamente después `Function`, escriba los parámetros de la función.</span><span class="sxs-lookup"><span data-stu-id="a7d4c-108">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="a7d4c-109">Tenga en cuenta que no se especifica un nombre después de `Function`.</span><span class="sxs-lookup"><span data-stu-id="a7d4c-109">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="a7d4c-110">`Dim add1 = Function`   `(num As Integer)`</span><span class="sxs-lookup"><span data-stu-id="a7d4c-110">`Dim add1 = Function`   `(num As Integer)`</span></span>  
  
3.  <span data-ttu-id="a7d4c-111">Después de la lista de parámetros, escriba una expresión única como el cuerpo de la función.</span><span class="sxs-lookup"><span data-stu-id="a7d4c-111">Following the parameter list, type a single expression as the body of the function.</span></span> <span data-ttu-id="a7d4c-112">El valor que se evalúa como la expresión es el valor devuelto por la función.</span><span class="sxs-lookup"><span data-stu-id="a7d4c-112">The value that the expression evaluates to is the value returned by the function.</span></span> <span data-ttu-id="a7d4c-113">No se usa un `As` cláusula para especificar el tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="a7d4c-113">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_1.vb)]  
  
     <span data-ttu-id="a7d4c-114">Se llama a la expresión lambda pasando un argumento entero.</span><span class="sxs-lookup"><span data-stu-id="a7d4c-114">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_2.vb)]  
  
4.  <span data-ttu-id="a7d4c-115">Como alternativa, se consigue el mismo resultado en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a7d4c-115">Alternatively, the same result is accomplished by the following example:</span></span>  
  
     [!code-vb[VbVbalrLambdas#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_3.vb)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a><span data-ttu-id="a7d4c-116">Para crear una subrutina de expresión lambda de línea</span><span class="sxs-lookup"><span data-stu-id="a7d4c-116">To create a single-line lambda expression subroutine</span></span>  
  
1.  <span data-ttu-id="a7d4c-117">En cualquier situación donde se podría usar un tipo de delegado, escriba la palabra clave `Sub`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="a7d4c-117">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="a7d4c-118">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="a7d4c-118">`Dim add1 =`   `Sub`</span></span>  
  
2.  <span data-ttu-id="a7d4c-119">Entre paréntesis, directamente después `Sub`, escriba los parámetros de la subrutina.</span><span class="sxs-lookup"><span data-stu-id="a7d4c-119">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="a7d4c-120">Tenga en cuenta que no se especifica un nombre después de `Sub`.</span><span class="sxs-lookup"><span data-stu-id="a7d4c-120">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="a7d4c-121">`Dim add1 = Sub`   `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="a7d4c-121">`Dim add1 = Sub`   `(msg As String)`</span></span>  
  
3.  <span data-ttu-id="a7d4c-122">Después de la lista de parámetros, escriba una sola instrucción como cuerpo de la subrutina.</span><span class="sxs-lookup"><span data-stu-id="a7d4c-122">Following the parameter list, type a single statement as the body of the subroutine.</span></span>  
  
     [!code-vb[VbVbalrLambdas#17](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_4.vb)]  
  
     <span data-ttu-id="a7d4c-123">Se llama a la expresión lambda pasando un argumento de cadena.</span><span class="sxs-lookup"><span data-stu-id="a7d4c-123">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#18](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_5.vb)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a><span data-ttu-id="a7d4c-124">Para crear una función de la expresión lambda de varias líneas</span><span class="sxs-lookup"><span data-stu-id="a7d4c-124">To create a multiline lambda expression function</span></span>  
  
1.  <span data-ttu-id="a7d4c-125">En cualquier situación donde se podría usar un tipo de delegado, escriba la palabra clave `Function`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="a7d4c-125">In any situation where a delegate type could be used, type the keyword `Function`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="a7d4c-126">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="a7d4c-126">`Dim add1 =`   `Function`</span></span>  
  
2.  <span data-ttu-id="a7d4c-127">Entre paréntesis, directamente después `Function`, escriba los parámetros de la función.</span><span class="sxs-lookup"><span data-stu-id="a7d4c-127">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="a7d4c-128">Tenga en cuenta que no se especifica un nombre después de `Function`.</span><span class="sxs-lookup"><span data-stu-id="a7d4c-128">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="a7d4c-129">`Dim add1 = Function`   `(index As Integer)`</span><span class="sxs-lookup"><span data-stu-id="a7d4c-129">`Dim add1 = Function`   `(index As Integer)`</span></span>  
  
3.  <span data-ttu-id="a7d4c-130">Presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="a7d4c-130">Press ENTER.</span></span> <span data-ttu-id="a7d4c-131">El `End Function` instrucción se agrega automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a7d4c-131">The `End Function` statement is automatically added.</span></span>  
  
4.  <span data-ttu-id="a7d4c-132">Dentro del cuerpo de la función, agregue el código siguiente para crear una expresión y el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="a7d4c-132">Within the body of the function, add the following code to create an expression and return the value.</span></span> <span data-ttu-id="a7d4c-133">No se usa un `As` cláusula para especificar el tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="a7d4c-133">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#19](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_6.vb)]  
  
     <span data-ttu-id="a7d4c-134">Se llama a la expresión lambda pasando un argumento entero.</span><span class="sxs-lookup"><span data-stu-id="a7d4c-134">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#20](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_7.vb)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a><span data-ttu-id="a7d4c-135">Para crear una subrutina de expresión lambda de varias líneas</span><span class="sxs-lookup"><span data-stu-id="a7d4c-135">To create a multiline lambda expression subroutine</span></span>  
  
1.  <span data-ttu-id="a7d4c-136">En cualquier situación donde se podría usar un tipo de delegado, escriba la palabra clave `Sub`, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a7d4c-136">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example:</span></span>  
  
     <span data-ttu-id="a7d4c-137">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="a7d4c-137">`Dim add1 =`   `Sub`</span></span>  
  
2.  <span data-ttu-id="a7d4c-138">Entre paréntesis, directamente después `Sub`, escriba los parámetros de la subrutina.</span><span class="sxs-lookup"><span data-stu-id="a7d4c-138">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="a7d4c-139">Tenga en cuenta que no se especifica un nombre después de `Sub`.</span><span class="sxs-lookup"><span data-stu-id="a7d4c-139">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="a7d4c-140">`Dim add1 = Sub`  `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="a7d4c-140">`Dim add1 = Sub`  `(msg As String)`</span></span>  
  
3.  <span data-ttu-id="a7d4c-141">Presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="a7d4c-141">Press ENTER.</span></span> <span data-ttu-id="a7d4c-142">El `End Sub` instrucción se agrega automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a7d4c-142">The `End Sub` statement is automatically added.</span></span>  
  
4.  <span data-ttu-id="a7d4c-143">Dentro del cuerpo de la función, agregue el código siguiente para ejecutar cuando se invoca la subrutina.</span><span class="sxs-lookup"><span data-stu-id="a7d4c-143">Within the body of the function, add the following code to execute when the subroutine is invoked.</span></span>  
  
     [!code-vb[VbVbalrLambdas#21](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_8.vb)]  
  
     <span data-ttu-id="a7d4c-144">Se llama a la expresión lambda pasando un argumento de cadena.</span><span class="sxs-lookup"><span data-stu-id="a7d4c-144">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#22](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_9.vb)]  
  
## <a name="example"></a><span data-ttu-id="a7d4c-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a7d4c-145">Example</span></span>  
 <span data-ttu-id="a7d4c-146">Es un uso común de las expresiones lambda definir una función que puede pasarse como argumento para un parámetro cuyo tipo es `Delegate`.</span><span class="sxs-lookup"><span data-stu-id="a7d4c-146">A common use of lambda expressions is to define a function that can be passed in as the argument for a parameter whose type is `Delegate`.</span></span> <span data-ttu-id="a7d4c-147">En el ejemplo siguiente, la <xref:System.Diagnostics.Process.GetProcesses%2A> método devuelve una matriz de los procesos que se ejecutan en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="a7d4c-147">In the following example, the <xref:System.Diagnostics.Process.GetProcesses%2A> method returns an array of the processes running on the local computer.</span></span> <span data-ttu-id="a7d4c-148">El <xref:System.Linq.Enumerable.Where%2A> método desde el <xref:System.Linq.Enumerable> clase requiere un `Boolean` delegar como su argumento.</span><span class="sxs-lookup"><span data-stu-id="a7d4c-148">The <xref:System.Linq.Enumerable.Where%2A> method from the <xref:System.Linq.Enumerable> class requires a `Boolean` delegate as its argument.</span></span> <span data-ttu-id="a7d4c-149">La expresión lambda en el ejemplo se usa para ese propósito.</span><span class="sxs-lookup"><span data-stu-id="a7d4c-149">The lambda expression in the example is used for that purpose.</span></span> <span data-ttu-id="a7d4c-150">Devuelve `True` para cada proceso que tiene un solo subproceso, y que estén seleccionadas en `filteredList`.</span><span class="sxs-lookup"><span data-stu-id="a7d4c-150">It returns `True` for each process that has only one thread, and those are selected in `filteredList`.</span></span>  
  
 [!code-vb[VbVbalrLambdas#10](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_10.vb)]  
  
 <span data-ttu-id="a7d4c-151">El ejemplo anterior es equivalente al código siguiente, que está escrito en [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] sintaxis:</span><span class="sxs-lookup"><span data-stu-id="a7d4c-151">The previous example is equivalent to the following code, which is written in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] syntax:</span></span>  
  
 [!code-vb[VbVbalrLambdas#11](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_11.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="a7d4c-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7d4c-152">See also</span></span>
- <xref:System.Linq.Enumerable>
- [<span data-ttu-id="a7d4c-153">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="a7d4c-153">Lambda Expressions</span></span>](./lambda-expressions.md)
- [<span data-ttu-id="a7d4c-154">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="a7d4c-154">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="a7d4c-155">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="a7d4c-155">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="a7d4c-156">Delegados</span><span class="sxs-lookup"><span data-stu-id="a7d4c-156">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="a7d4c-157">Cómo: Pasar procedimientos a otro procedimiento en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a7d4c-157">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="a7d4c-158">Delegate (instrucción)</span><span class="sxs-lookup"><span data-stu-id="a7d4c-158">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="a7d4c-159">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a7d4c-159">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
