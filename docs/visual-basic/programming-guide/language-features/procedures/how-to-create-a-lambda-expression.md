---
title: Procedimiento para crear una expresión lambda
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
ms.openlocfilehash: cc2de38f7375848d104edff6f419656d9caa9cb2
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071929"
---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a><span data-ttu-id="ddebb-102">Cómo: Crear una expresión lambda (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ddebb-102">How to: Create a Lambda Expression (Visual Basic)</span></span>

<span data-ttu-id="ddebb-103">Una *expresión lambda* es una función o subrutina que no tiene un nombre.</span><span class="sxs-lookup"><span data-stu-id="ddebb-103">A *lambda expression* is a function or subroutine that does not have a name.</span></span> <span data-ttu-id="ddebb-104">Se puede usar una expresión lambda siempre que un tipo de delegado sea válido.</span><span class="sxs-lookup"><span data-stu-id="ddebb-104">A lambda expression can be used wherever a delegate type is valid.</span></span>  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a><span data-ttu-id="ddebb-105">Para crear una función de expresión lambda de una sola línea</span><span class="sxs-lookup"><span data-stu-id="ddebb-105">To create a single-line lambda expression function</span></span>  
  
1. <span data-ttu-id="ddebb-106">En cualquier situación en la que se pueda usar un tipo de delegado, escriba la palabra clave `Function` , como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ddebb-106">In any situation where a delegate type could be used, type the keyword `Function`, as in the following example:</span></span>  
  
     <span data-ttu-id="ddebb-107">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="ddebb-107">`Dim add1 =`   `Function`</span></span>  
  
2. <span data-ttu-id="ddebb-108">Entre paréntesis, directamente después de `Function` , escriba los parámetros de la función.</span><span class="sxs-lookup"><span data-stu-id="ddebb-108">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="ddebb-109">Tenga en cuenta que no especifica un nombre después de `Function` .</span><span class="sxs-lookup"><span data-stu-id="ddebb-109">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="ddebb-110">`Dim add1 = Function`   `(num As Integer)`</span><span class="sxs-lookup"><span data-stu-id="ddebb-110">`Dim add1 = Function`   `(num As Integer)`</span></span>  
  
3. <span data-ttu-id="ddebb-111">Después de la lista de parámetros, escriba una sola expresión como cuerpo de la función.</span><span class="sxs-lookup"><span data-stu-id="ddebb-111">Following the parameter list, type a single expression as the body of the function.</span></span> <span data-ttu-id="ddebb-112">El valor que la expresión evalúa como es el valor devuelto por la función.</span><span class="sxs-lookup"><span data-stu-id="ddebb-112">The value that the expression evaluates to is the value returned by the function.</span></span> <span data-ttu-id="ddebb-113">No se utiliza una `As` cláusula para especificar el tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="ddebb-113">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
     <span data-ttu-id="ddebb-114">Llame a la expresión lambda pasando un argumento entero.</span><span class="sxs-lookup"><span data-stu-id="ddebb-114">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
4. <span data-ttu-id="ddebb-115">Como alternativa, el mismo resultado se logra mediante el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ddebb-115">Alternatively, the same result is accomplished by the following example:</span></span>  
  
     [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a><span data-ttu-id="ddebb-116">Para crear una subrutina de expresión lambda de una sola línea</span><span class="sxs-lookup"><span data-stu-id="ddebb-116">To create a single-line lambda expression subroutine</span></span>  
  
1. <span data-ttu-id="ddebb-117">En cualquier situación en la que se pueda usar un tipo de delegado, escriba la palabra clave `Sub` , tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ddebb-117">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="ddebb-118">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="ddebb-118">`Dim add1 =`   `Sub`</span></span>  
  
2. <span data-ttu-id="ddebb-119">Entre paréntesis, directamente después de `Sub` , escriba los parámetros de la subrutina.</span><span class="sxs-lookup"><span data-stu-id="ddebb-119">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="ddebb-120">Tenga en cuenta que no especifica un nombre después de `Sub` .</span><span class="sxs-lookup"><span data-stu-id="ddebb-120">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="ddebb-121">`Dim add1 = Sub`   `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="ddebb-121">`Dim add1 = Sub`   `(msg As String)`</span></span>  
  
3. <span data-ttu-id="ddebb-122">Después de la lista de parámetros, escriba una sola instrucción como cuerpo de la subrutina.</span><span class="sxs-lookup"><span data-stu-id="ddebb-122">Following the parameter list, type a single statement as the body of the subroutine.</span></span>  
  
     [!code-vb[VbVbalrLambdas#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#17)]  
  
     <span data-ttu-id="ddebb-123">La expresión lambda se llama pasando un argumento de cadena.</span><span class="sxs-lookup"><span data-stu-id="ddebb-123">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#18)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a><span data-ttu-id="ddebb-124">Para crear una función de expresión lambda de varias líneas</span><span class="sxs-lookup"><span data-stu-id="ddebb-124">To create a multiline lambda expression function</span></span>  
  
1. <span data-ttu-id="ddebb-125">En cualquier situación en la que se pueda usar un tipo de delegado, escriba la palabra clave `Function` , tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ddebb-125">In any situation where a delegate type could be used, type the keyword `Function`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="ddebb-126">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="ddebb-126">`Dim add1 =`   `Function`</span></span>  
  
2. <span data-ttu-id="ddebb-127">Entre paréntesis, directamente después de `Function` , escriba los parámetros de la función.</span><span class="sxs-lookup"><span data-stu-id="ddebb-127">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="ddebb-128">Tenga en cuenta que no especifica un nombre después de `Function` .</span><span class="sxs-lookup"><span data-stu-id="ddebb-128">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="ddebb-129">`Dim add1 = Function`   `(index As Integer)`</span><span class="sxs-lookup"><span data-stu-id="ddebb-129">`Dim add1 = Function`   `(index As Integer)`</span></span>  
  
3. <span data-ttu-id="ddebb-130">Presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="ddebb-130">Press ENTER.</span></span> <span data-ttu-id="ddebb-131">La `End Function` instrucción se agrega automáticamente.</span><span class="sxs-lookup"><span data-stu-id="ddebb-131">The `End Function` statement is automatically added.</span></span>  
  
4. <span data-ttu-id="ddebb-132">En el cuerpo de la función, agregue el código siguiente para crear una expresión y devolver el valor.</span><span class="sxs-lookup"><span data-stu-id="ddebb-132">Within the body of the function, add the following code to create an expression and return the value.</span></span> <span data-ttu-id="ddebb-133">No se utiliza una `As` cláusula para especificar el tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="ddebb-133">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#19)]  
  
     <span data-ttu-id="ddebb-134">Llame a la expresión lambda pasando un argumento entero.</span><span class="sxs-lookup"><span data-stu-id="ddebb-134">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#20)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a><span data-ttu-id="ddebb-135">Para crear una subrutina de expresión lambda de varias líneas</span><span class="sxs-lookup"><span data-stu-id="ddebb-135">To create a multiline lambda expression subroutine</span></span>  
  
1. <span data-ttu-id="ddebb-136">En cualquier situación en la que se pueda usar un tipo de delegado, escriba la palabra clave `Sub` , tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ddebb-136">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example:</span></span>  
  
     <span data-ttu-id="ddebb-137">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="ddebb-137">`Dim add1 =`   `Sub`</span></span>  
  
2. <span data-ttu-id="ddebb-138">Entre paréntesis, directamente después de `Sub` , escriba los parámetros de la subrutina.</span><span class="sxs-lookup"><span data-stu-id="ddebb-138">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="ddebb-139">Tenga en cuenta que no especifica un nombre después de `Sub` .</span><span class="sxs-lookup"><span data-stu-id="ddebb-139">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="ddebb-140">`Dim add1 = Sub`  `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="ddebb-140">`Dim add1 = Sub`  `(msg As String)`</span></span>  
  
3. <span data-ttu-id="ddebb-141">Presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="ddebb-141">Press ENTER.</span></span> <span data-ttu-id="ddebb-142">La `End Sub` instrucción se agrega automáticamente.</span><span class="sxs-lookup"><span data-stu-id="ddebb-142">The `End Sub` statement is automatically added.</span></span>  
  
4. <span data-ttu-id="ddebb-143">En el cuerpo de la función, agregue el código siguiente para ejecutarlo cuando se invoque la subrutina.</span><span class="sxs-lookup"><span data-stu-id="ddebb-143">Within the body of the function, add the following code to execute when the subroutine is invoked.</span></span>  
  
     [!code-vb[VbVbalrLambdas#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#21)]  
  
     <span data-ttu-id="ddebb-144">La expresión lambda se llama pasando un argumento de cadena.</span><span class="sxs-lookup"><span data-stu-id="ddebb-144">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#22)]  
  
## <a name="example"></a><span data-ttu-id="ddebb-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ddebb-145">Example</span></span>  

 <span data-ttu-id="ddebb-146">Un uso común de las expresiones lambda es definir una función que se puede pasar como argumento para un parámetro cuyo tipo es `Delegate` .</span><span class="sxs-lookup"><span data-stu-id="ddebb-146">A common use of lambda expressions is to define a function that can be passed in as the argument for a parameter whose type is `Delegate`.</span></span> <span data-ttu-id="ddebb-147">En el ejemplo siguiente, el <xref:System.Diagnostics.Process.GetProcesses%2A> método devuelve una matriz de los procesos que se ejecutan en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="ddebb-147">In the following example, the <xref:System.Diagnostics.Process.GetProcesses%2A> method returns an array of the processes running on the local computer.</span></span> <span data-ttu-id="ddebb-148">El <xref:System.Linq.Enumerable.Where%2A> método de la <xref:System.Linq.Enumerable> clase requiere un `Boolean` delegado como argumento.</span><span class="sxs-lookup"><span data-stu-id="ddebb-148">The <xref:System.Linq.Enumerable.Where%2A> method from the <xref:System.Linq.Enumerable> class requires a `Boolean` delegate as its argument.</span></span> <span data-ttu-id="ddebb-149">La expresión lambda en el ejemplo se usa para ese propósito.</span><span class="sxs-lookup"><span data-stu-id="ddebb-149">The lambda expression in the example is used for that purpose.</span></span> <span data-ttu-id="ddebb-150">Devuelve `True` para cada proceso que solo tiene un subproceso y que están seleccionados en `filteredList` .</span><span class="sxs-lookup"><span data-stu-id="ddebb-150">It returns `True` for each process that has only one thread, and those are selected in `filteredList`.</span></span>  
  
 [!code-vb[VbVbalrLambdas#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class4.vb#10)]  
  
 <span data-ttu-id="ddebb-151">El ejemplo anterior es equivalente al código siguiente, que está escrito en la sintaxis Language-Integrated Query (LINQ):</span><span class="sxs-lookup"><span data-stu-id="ddebb-151">The previous example is equivalent to the following code, which is written in Language-Integrated Query (LINQ) syntax:</span></span>  
  
 [!code-vb[VbVbalrLambdas#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class5.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="ddebb-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ddebb-152">See also</span></span>

- <xref:System.Linq.Enumerable>
- [<span data-ttu-id="ddebb-153">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="ddebb-153">Lambda Expressions</span></span>](./lambda-expressions.md)
- [<span data-ttu-id="ddebb-154">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="ddebb-154">Function Statement</span></span>](../../../language-reference/statements/function-statement.md)
- [<span data-ttu-id="ddebb-155">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="ddebb-155">Sub Statement</span></span>](../../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="ddebb-156">Delegados</span><span class="sxs-lookup"><span data-stu-id="ddebb-156">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="ddebb-157">Cómo: Pasar procedimientos a otro procedimiento en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ddebb-157">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="ddebb-158">Delegate (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="ddebb-158">Delegate Statement</span></span>](../../../language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="ddebb-159">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ddebb-159">Introduction to LINQ in Visual Basic</span></span>](../linq/introduction-to-linq.md)
