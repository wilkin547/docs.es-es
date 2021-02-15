---
description: 'Más información sobre: Cómo: crear una expresión lambda (Visual Basic)'
title: Procedimiento para crear una expresión lambda
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
ms.openlocfilehash: 386d40c1e2021c9b02b2f785300c4e978b4da87d
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100472571"
---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a><span data-ttu-id="75c2f-103">Cómo: Crear una expresión lambda (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75c2f-103">How to: Create a Lambda Expression (Visual Basic)</span></span>

<span data-ttu-id="75c2f-104">Una *expresión lambda* es una función o subrutina que no tiene un nombre.</span><span class="sxs-lookup"><span data-stu-id="75c2f-104">A *lambda expression* is a function or subroutine that does not have a name.</span></span> <span data-ttu-id="75c2f-105">Se puede usar una expresión lambda siempre que un tipo de delegado sea válido.</span><span class="sxs-lookup"><span data-stu-id="75c2f-105">A lambda expression can be used wherever a delegate type is valid.</span></span>  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a><span data-ttu-id="75c2f-106">Para crear una función de expresión lambda de una sola línea</span><span class="sxs-lookup"><span data-stu-id="75c2f-106">To create a single-line lambda expression function</span></span>  
  
1. <span data-ttu-id="75c2f-107">En cualquier situación en la que se pueda usar un tipo de delegado, escriba la palabra clave `Function` , como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="75c2f-107">In any situation where a delegate type could be used, type the keyword `Function`, as in the following example:</span></span>  
  
     <span data-ttu-id="75c2f-108">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="75c2f-108">`Dim add1 =`   `Function`</span></span>  
  
2. <span data-ttu-id="75c2f-109">Entre paréntesis, directamente después de `Function` , escriba los parámetros de la función.</span><span class="sxs-lookup"><span data-stu-id="75c2f-109">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="75c2f-110">Tenga en cuenta que no especifica un nombre después de `Function` .</span><span class="sxs-lookup"><span data-stu-id="75c2f-110">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="75c2f-111">`Dim add1 = Function`   `(num As Integer)`</span><span class="sxs-lookup"><span data-stu-id="75c2f-111">`Dim add1 = Function`   `(num As Integer)`</span></span>  
  
3. <span data-ttu-id="75c2f-112">Después de la lista de parámetros, escriba una sola expresión como cuerpo de la función.</span><span class="sxs-lookup"><span data-stu-id="75c2f-112">Following the parameter list, type a single expression as the body of the function.</span></span> <span data-ttu-id="75c2f-113">El valor que la expresión evalúa como es el valor devuelto por la función.</span><span class="sxs-lookup"><span data-stu-id="75c2f-113">The value that the expression evaluates to is the value returned by the function.</span></span> <span data-ttu-id="75c2f-114">No se utiliza una `As` cláusula para especificar el tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="75c2f-114">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
     <span data-ttu-id="75c2f-115">Llame a la expresión lambda pasando un argumento entero.</span><span class="sxs-lookup"><span data-stu-id="75c2f-115">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
4. <span data-ttu-id="75c2f-116">Como alternativa, el mismo resultado se logra mediante el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="75c2f-116">Alternatively, the same result is accomplished by the following example:</span></span>  
  
     [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a><span data-ttu-id="75c2f-117">Para crear una subrutina de expresión lambda de una sola línea</span><span class="sxs-lookup"><span data-stu-id="75c2f-117">To create a single-line lambda expression subroutine</span></span>  
  
1. <span data-ttu-id="75c2f-118">En cualquier situación en la que se pueda usar un tipo de delegado, escriba la palabra clave `Sub` , tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="75c2f-118">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="75c2f-119">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="75c2f-119">`Dim add1 =`   `Sub`</span></span>  
  
2. <span data-ttu-id="75c2f-120">Entre paréntesis, directamente después de `Sub` , escriba los parámetros de la subrutina.</span><span class="sxs-lookup"><span data-stu-id="75c2f-120">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="75c2f-121">Tenga en cuenta que no especifica un nombre después de `Sub` .</span><span class="sxs-lookup"><span data-stu-id="75c2f-121">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="75c2f-122">`Dim add1 = Sub`   `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="75c2f-122">`Dim add1 = Sub`   `(msg As String)`</span></span>  
  
3. <span data-ttu-id="75c2f-123">Después de la lista de parámetros, escriba una sola instrucción como cuerpo de la subrutina.</span><span class="sxs-lookup"><span data-stu-id="75c2f-123">Following the parameter list, type a single statement as the body of the subroutine.</span></span>  
  
     [!code-vb[VbVbalrLambdas#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#17)]  
  
     <span data-ttu-id="75c2f-124">La expresión lambda se llama pasando un argumento de cadena.</span><span class="sxs-lookup"><span data-stu-id="75c2f-124">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#18)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a><span data-ttu-id="75c2f-125">Para crear una función de expresión lambda de varias líneas</span><span class="sxs-lookup"><span data-stu-id="75c2f-125">To create a multiline lambda expression function</span></span>  
  
1. <span data-ttu-id="75c2f-126">En cualquier situación en la que se pueda usar un tipo de delegado, escriba la palabra clave `Function` , tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="75c2f-126">In any situation where a delegate type could be used, type the keyword `Function`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="75c2f-127">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="75c2f-127">`Dim add1 =`   `Function`</span></span>  
  
2. <span data-ttu-id="75c2f-128">Entre paréntesis, directamente después de `Function` , escriba los parámetros de la función.</span><span class="sxs-lookup"><span data-stu-id="75c2f-128">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="75c2f-129">Tenga en cuenta que no especifica un nombre después de `Function` .</span><span class="sxs-lookup"><span data-stu-id="75c2f-129">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="75c2f-130">`Dim add1 = Function`   `(index As Integer)`</span><span class="sxs-lookup"><span data-stu-id="75c2f-130">`Dim add1 = Function`   `(index As Integer)`</span></span>  
  
3. <span data-ttu-id="75c2f-131">Presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="75c2f-131">Press ENTER.</span></span> <span data-ttu-id="75c2f-132">La `End Function` instrucción se agrega automáticamente.</span><span class="sxs-lookup"><span data-stu-id="75c2f-132">The `End Function` statement is automatically added.</span></span>  
  
4. <span data-ttu-id="75c2f-133">En el cuerpo de la función, agregue el código siguiente para crear una expresión y devolver el valor.</span><span class="sxs-lookup"><span data-stu-id="75c2f-133">Within the body of the function, add the following code to create an expression and return the value.</span></span> <span data-ttu-id="75c2f-134">No se utiliza una `As` cláusula para especificar el tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="75c2f-134">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#19)]  
  
     <span data-ttu-id="75c2f-135">Llame a la expresión lambda pasando un argumento entero.</span><span class="sxs-lookup"><span data-stu-id="75c2f-135">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#20)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a><span data-ttu-id="75c2f-136">Para crear una subrutina de expresión lambda de varias líneas</span><span class="sxs-lookup"><span data-stu-id="75c2f-136">To create a multiline lambda expression subroutine</span></span>  
  
1. <span data-ttu-id="75c2f-137">En cualquier situación en la que se pueda usar un tipo de delegado, escriba la palabra clave `Sub` , tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="75c2f-137">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example:</span></span>  
  
     <span data-ttu-id="75c2f-138">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="75c2f-138">`Dim add1 =`   `Sub`</span></span>  
  
2. <span data-ttu-id="75c2f-139">Entre paréntesis, directamente después de `Sub` , escriba los parámetros de la subrutina.</span><span class="sxs-lookup"><span data-stu-id="75c2f-139">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="75c2f-140">Tenga en cuenta que no especifica un nombre después de `Sub` .</span><span class="sxs-lookup"><span data-stu-id="75c2f-140">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="75c2f-141">`Dim add1 = Sub`  `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="75c2f-141">`Dim add1 = Sub`  `(msg As String)`</span></span>  
  
3. <span data-ttu-id="75c2f-142">Presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="75c2f-142">Press ENTER.</span></span> <span data-ttu-id="75c2f-143">La `End Sub` instrucción se agrega automáticamente.</span><span class="sxs-lookup"><span data-stu-id="75c2f-143">The `End Sub` statement is automatically added.</span></span>  
  
4. <span data-ttu-id="75c2f-144">En el cuerpo de la función, agregue el código siguiente para ejecutarlo cuando se invoque la subrutina.</span><span class="sxs-lookup"><span data-stu-id="75c2f-144">Within the body of the function, add the following code to execute when the subroutine is invoked.</span></span>  
  
     [!code-vb[VbVbalrLambdas#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#21)]  
  
     <span data-ttu-id="75c2f-145">La expresión lambda se llama pasando un argumento de cadena.</span><span class="sxs-lookup"><span data-stu-id="75c2f-145">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#22)]  
  
## <a name="example"></a><span data-ttu-id="75c2f-146">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="75c2f-146">Example</span></span>  

 <span data-ttu-id="75c2f-147">Un uso común de las expresiones lambda es definir una función que se puede pasar como argumento para un parámetro cuyo tipo es `Delegate` .</span><span class="sxs-lookup"><span data-stu-id="75c2f-147">A common use of lambda expressions is to define a function that can be passed in as the argument for a parameter whose type is `Delegate`.</span></span> <span data-ttu-id="75c2f-148">En el ejemplo siguiente, el <xref:System.Diagnostics.Process.GetProcesses%2A> método devuelve una matriz de los procesos que se ejecutan en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="75c2f-148">In the following example, the <xref:System.Diagnostics.Process.GetProcesses%2A> method returns an array of the processes running on the local computer.</span></span> <span data-ttu-id="75c2f-149">El <xref:System.Linq.Enumerable.Where%2A> método de la <xref:System.Linq.Enumerable> clase requiere un `Boolean` delegado como argumento.</span><span class="sxs-lookup"><span data-stu-id="75c2f-149">The <xref:System.Linq.Enumerable.Where%2A> method from the <xref:System.Linq.Enumerable> class requires a `Boolean` delegate as its argument.</span></span> <span data-ttu-id="75c2f-150">La expresión lambda en el ejemplo se usa para ese propósito.</span><span class="sxs-lookup"><span data-stu-id="75c2f-150">The lambda expression in the example is used for that purpose.</span></span> <span data-ttu-id="75c2f-151">Devuelve `True` para cada proceso que solo tiene un subproceso y que están seleccionados en `filteredList` .</span><span class="sxs-lookup"><span data-stu-id="75c2f-151">It returns `True` for each process that has only one thread, and those are selected in `filteredList`.</span></span>  
  
 [!code-vb[VbVbalrLambdas#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class4.vb#10)]  
  
 <span data-ttu-id="75c2f-152">El ejemplo anterior es equivalente al código siguiente, que se escribe en la sintaxis de Language-Integrated Query (LINQ):</span><span class="sxs-lookup"><span data-stu-id="75c2f-152">The previous example is equivalent to the following code, which is written in Language-Integrated Query (LINQ) syntax:</span></span>  
  
 [!code-vb[VbVbalrLambdas#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class5.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="75c2f-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="75c2f-153">See also</span></span>

- <xref:System.Linq.Enumerable>
- [<span data-ttu-id="75c2f-154">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="75c2f-154">Lambda Expressions</span></span>](./lambda-expressions.md)
- [<span data-ttu-id="75c2f-155">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="75c2f-155">Function Statement</span></span>](../../../language-reference/statements/function-statement.md)
- [<span data-ttu-id="75c2f-156">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="75c2f-156">Sub Statement</span></span>](../../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="75c2f-157">Delegados</span><span class="sxs-lookup"><span data-stu-id="75c2f-157">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="75c2f-158">Cómo: Pasar procedimientos a otro procedimiento en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="75c2f-158">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="75c2f-159">Delegate (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="75c2f-159">Delegate Statement</span></span>](../../../language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="75c2f-160">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="75c2f-160">Introduction to LINQ in Visual Basic</span></span>](../linq/introduction-to-linq.md)
