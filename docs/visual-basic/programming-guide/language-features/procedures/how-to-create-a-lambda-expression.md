---
title: 'Cómo: Crear una expresión lambda'
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
ms.openlocfilehash: 1c65841e4c124252cfa41bcd4d0c305a426687ee
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2020
ms.locfileid: "75632355"
---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a><span data-ttu-id="6cd98-102">Cómo: Crear una expresión lambda (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6cd98-102">How to: Create a Lambda Expression (Visual Basic)</span></span>
<span data-ttu-id="6cd98-103">Una *expresión lambda* es una función o subrutina que no tiene un nombre.</span><span class="sxs-lookup"><span data-stu-id="6cd98-103">A *lambda expression* is a function or subroutine that does not have a name.</span></span> <span data-ttu-id="6cd98-104">Se puede usar una expresión lambda siempre que un tipo de delegado sea válido.</span><span class="sxs-lookup"><span data-stu-id="6cd98-104">A lambda expression can be used wherever a delegate type is valid.</span></span>  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a><span data-ttu-id="6cd98-105">Para crear una función de expresión lambda de una sola línea</span><span class="sxs-lookup"><span data-stu-id="6cd98-105">To create a single-line lambda expression function</span></span>  
  
1. <span data-ttu-id="6cd98-106">En cualquier situación en la que se pueda usar un tipo de delegado, escriba la palabra clave `Function`, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6cd98-106">In any situation where a delegate type could be used, type the keyword `Function`, as in the following example:</span></span>  
  
     <span data-ttu-id="6cd98-107">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="6cd98-107">`Dim add1 =`   `Function`</span></span>  
  
2. <span data-ttu-id="6cd98-108">Entre paréntesis, directamente después de `Function`, escriba los parámetros de la función.</span><span class="sxs-lookup"><span data-stu-id="6cd98-108">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="6cd98-109">Tenga en cuenta que no especifica un nombre después de `Function`.</span><span class="sxs-lookup"><span data-stu-id="6cd98-109">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="6cd98-110">`Dim add1 = Function`   `(num As Integer)`</span><span class="sxs-lookup"><span data-stu-id="6cd98-110">`Dim add1 = Function`   `(num As Integer)`</span></span>  
  
3. <span data-ttu-id="6cd98-111">Después de la lista de parámetros, escriba una sola expresión como cuerpo de la función.</span><span class="sxs-lookup"><span data-stu-id="6cd98-111">Following the parameter list, type a single expression as the body of the function.</span></span> <span data-ttu-id="6cd98-112">El valor que la expresión evalúa como es el valor devuelto por la función.</span><span class="sxs-lookup"><span data-stu-id="6cd98-112">The value that the expression evaluates to is the value returned by the function.</span></span> <span data-ttu-id="6cd98-113">No use una cláusula `As` para especificar el tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="6cd98-113">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
     <span data-ttu-id="6cd98-114">Llame a la expresión lambda pasando un argumento entero.</span><span class="sxs-lookup"><span data-stu-id="6cd98-114">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
4. <span data-ttu-id="6cd98-115">Como alternativa, el mismo resultado se logra mediante el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6cd98-115">Alternatively, the same result is accomplished by the following example:</span></span>  
  
     [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a><span data-ttu-id="6cd98-116">Para crear una subrutina de expresión lambda de una sola línea</span><span class="sxs-lookup"><span data-stu-id="6cd98-116">To create a single-line lambda expression subroutine</span></span>  
  
1. <span data-ttu-id="6cd98-117">En cualquier situación en la que se pueda usar un tipo de delegado, escriba la palabra clave `Sub`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="6cd98-117">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="6cd98-118">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="6cd98-118">`Dim add1 =`   `Sub`</span></span>  
  
2. <span data-ttu-id="6cd98-119">Entre paréntesis, directamente después de `Sub`, escriba los parámetros de la subrutina.</span><span class="sxs-lookup"><span data-stu-id="6cd98-119">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="6cd98-120">Tenga en cuenta que no especifica un nombre después de `Sub`.</span><span class="sxs-lookup"><span data-stu-id="6cd98-120">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="6cd98-121">`Dim add1 = Sub`   `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="6cd98-121">`Dim add1 = Sub`   `(msg As String)`</span></span>  
  
3. <span data-ttu-id="6cd98-122">Después de la lista de parámetros, escriba una sola instrucción como cuerpo de la subrutina.</span><span class="sxs-lookup"><span data-stu-id="6cd98-122">Following the parameter list, type a single statement as the body of the subroutine.</span></span>  
  
     [!code-vb[VbVbalrLambdas#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#17)]  
  
     <span data-ttu-id="6cd98-123">La expresión lambda se llama pasando un argumento de cadena.</span><span class="sxs-lookup"><span data-stu-id="6cd98-123">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#18)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a><span data-ttu-id="6cd98-124">Para crear una función de expresión lambda de varias líneas</span><span class="sxs-lookup"><span data-stu-id="6cd98-124">To create a multiline lambda expression function</span></span>  
  
1. <span data-ttu-id="6cd98-125">En cualquier situación en la que se pueda usar un tipo de delegado, escriba la palabra clave `Function`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="6cd98-125">In any situation where a delegate type could be used, type the keyword `Function`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="6cd98-126">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="6cd98-126">`Dim add1 =`   `Function`</span></span>  
  
2. <span data-ttu-id="6cd98-127">Entre paréntesis, directamente después de `Function`, escriba los parámetros de la función.</span><span class="sxs-lookup"><span data-stu-id="6cd98-127">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="6cd98-128">Tenga en cuenta que no especifica un nombre después de `Function`.</span><span class="sxs-lookup"><span data-stu-id="6cd98-128">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="6cd98-129">`Dim add1 = Function`   `(index As Integer)`</span><span class="sxs-lookup"><span data-stu-id="6cd98-129">`Dim add1 = Function`   `(index As Integer)`</span></span>  
  
3. <span data-ttu-id="6cd98-130">Presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="6cd98-130">Press ENTER.</span></span> <span data-ttu-id="6cd98-131">La instrucción `End Function` se agrega automáticamente.</span><span class="sxs-lookup"><span data-stu-id="6cd98-131">The `End Function` statement is automatically added.</span></span>  
  
4. <span data-ttu-id="6cd98-132">En el cuerpo de la función, agregue el código siguiente para crear una expresión y devolver el valor.</span><span class="sxs-lookup"><span data-stu-id="6cd98-132">Within the body of the function, add the following code to create an expression and return the value.</span></span> <span data-ttu-id="6cd98-133">No use una cláusula `As` para especificar el tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="6cd98-133">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#19)]  
  
     <span data-ttu-id="6cd98-134">Llame a la expresión lambda pasando un argumento entero.</span><span class="sxs-lookup"><span data-stu-id="6cd98-134">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#20)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a><span data-ttu-id="6cd98-135">Para crear una subrutina de expresión lambda de varias líneas</span><span class="sxs-lookup"><span data-stu-id="6cd98-135">To create a multiline lambda expression subroutine</span></span>  
  
1. <span data-ttu-id="6cd98-136">En cualquier situación en la que se pueda usar un tipo de delegado, escriba la palabra clave `Sub`, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6cd98-136">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example:</span></span>  
  
     <span data-ttu-id="6cd98-137">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="6cd98-137">`Dim add1 =`   `Sub`</span></span>  
  
2. <span data-ttu-id="6cd98-138">Entre paréntesis, directamente después de `Sub`, escriba los parámetros de la subrutina.</span><span class="sxs-lookup"><span data-stu-id="6cd98-138">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="6cd98-139">Tenga en cuenta que no especifica un nombre después de `Sub`.</span><span class="sxs-lookup"><span data-stu-id="6cd98-139">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="6cd98-140">`Dim add1 = Sub`  `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="6cd98-140">`Dim add1 = Sub`  `(msg As String)`</span></span>  
  
3. <span data-ttu-id="6cd98-141">Presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="6cd98-141">Press ENTER.</span></span> <span data-ttu-id="6cd98-142">La instrucción `End Sub` se agrega automáticamente.</span><span class="sxs-lookup"><span data-stu-id="6cd98-142">The `End Sub` statement is automatically added.</span></span>  
  
4. <span data-ttu-id="6cd98-143">En el cuerpo de la función, agregue el código siguiente para ejecutarlo cuando se invoque la subrutina.</span><span class="sxs-lookup"><span data-stu-id="6cd98-143">Within the body of the function, add the following code to execute when the subroutine is invoked.</span></span>  
  
     [!code-vb[VbVbalrLambdas#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#21)]  
  
     <span data-ttu-id="6cd98-144">La expresión lambda se llama pasando un argumento de cadena.</span><span class="sxs-lookup"><span data-stu-id="6cd98-144">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#22)]  
  
## <a name="example"></a><span data-ttu-id="6cd98-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6cd98-145">Example</span></span>  
 <span data-ttu-id="6cd98-146">Un uso común de las expresiones lambda es definir una función que se puede pasar como argumento para un parámetro cuyo tipo es `Delegate`.</span><span class="sxs-lookup"><span data-stu-id="6cd98-146">A common use of lambda expressions is to define a function that can be passed in as the argument for a parameter whose type is `Delegate`.</span></span> <span data-ttu-id="6cd98-147">En el ejemplo siguiente, el método <xref:System.Diagnostics.Process.GetProcesses%2A> devuelve una matriz de los procesos que se ejecutan en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="6cd98-147">In the following example, the <xref:System.Diagnostics.Process.GetProcesses%2A> method returns an array of the processes running on the local computer.</span></span> <span data-ttu-id="6cd98-148">El método <xref:System.Linq.Enumerable.Where%2A> de la clase <xref:System.Linq.Enumerable> requiere un delegado `Boolean` como argumento.</span><span class="sxs-lookup"><span data-stu-id="6cd98-148">The <xref:System.Linq.Enumerable.Where%2A> method from the <xref:System.Linq.Enumerable> class requires a `Boolean` delegate as its argument.</span></span> <span data-ttu-id="6cd98-149">La expresión lambda en el ejemplo se usa para ese propósito.</span><span class="sxs-lookup"><span data-stu-id="6cd98-149">The lambda expression in the example is used for that purpose.</span></span> <span data-ttu-id="6cd98-150">Devuelve `True` para cada proceso que solo tiene un subproceso y que se seleccionan en `filteredList`.</span><span class="sxs-lookup"><span data-stu-id="6cd98-150">It returns `True` for each process that has only one thread, and those are selected in `filteredList`.</span></span>  
  
 [!code-vb[VbVbalrLambdas#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class4.vb#10)]  
  
 <span data-ttu-id="6cd98-151">El ejemplo anterior es equivalente al código siguiente, que está escrito en la sintaxis Language-Integrated Query (LINQ):</span><span class="sxs-lookup"><span data-stu-id="6cd98-151">The previous example is equivalent to the following code, which is written in Language-Integrated Query (LINQ) syntax:</span></span>  
  
 [!code-vb[VbVbalrLambdas#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class5.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="6cd98-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="6cd98-152">See also</span></span>

- <xref:System.Linq.Enumerable>
- [<span data-ttu-id="6cd98-153">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="6cd98-153">Lambda Expressions</span></span>](./lambda-expressions.md)
- [<span data-ttu-id="6cd98-154">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="6cd98-154">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="6cd98-155">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="6cd98-155">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="6cd98-156">Delegados</span><span class="sxs-lookup"><span data-stu-id="6cd98-156">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="6cd98-157">Paso de procedimientos a otro procedimiento en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6cd98-157">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="6cd98-158">Delegate (instrucción)</span><span class="sxs-lookup"><span data-stu-id="6cd98-158">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="6cd98-159">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6cd98-159">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
