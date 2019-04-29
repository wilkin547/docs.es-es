---
title: Procedimiento Crear una expresión Lambda (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
ms.openlocfilehash: fc2b7ed2004b842116d051b393f00506428def61
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61665941"
---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a><span data-ttu-id="ba34b-102">Procedimiento Crear una expresión Lambda (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ba34b-102">How to: Create a Lambda Expression (Visual Basic)</span></span>
<span data-ttu-id="ba34b-103">Un *expresión lambda* es una función o subrutina que no tiene un nombre.</span><span class="sxs-lookup"><span data-stu-id="ba34b-103">A *lambda expression* is a function or subroutine that does not have a name.</span></span> <span data-ttu-id="ba34b-104">Una expresión lambda puede usarse siempre que sea un tipo de delegado es válido.</span><span class="sxs-lookup"><span data-stu-id="ba34b-104">A lambda expression can be used wherever a delegate type is valid.</span></span>  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a><span data-ttu-id="ba34b-105">Para crear una función de la expresión lambda de línea</span><span class="sxs-lookup"><span data-stu-id="ba34b-105">To create a single-line lambda expression function</span></span>  
  
1. <span data-ttu-id="ba34b-106">En cualquier situación donde se podría usar un tipo de delegado, escriba la palabra clave `Function`, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ba34b-106">In any situation where a delegate type could be used, type the keyword `Function`, as in the following example:</span></span>  
  
     <span data-ttu-id="ba34b-107">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="ba34b-107">`Dim add1 =`   `Function`</span></span>  
  
2. <span data-ttu-id="ba34b-108">Entre paréntesis, directamente después `Function`, escriba los parámetros de la función.</span><span class="sxs-lookup"><span data-stu-id="ba34b-108">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="ba34b-109">Tenga en cuenta que no se especifica un nombre después de `Function`.</span><span class="sxs-lookup"><span data-stu-id="ba34b-109">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="ba34b-110">`Dim add1 = Function`   `(num As Integer)`</span><span class="sxs-lookup"><span data-stu-id="ba34b-110">`Dim add1 = Function`   `(num As Integer)`</span></span>  
  
3. <span data-ttu-id="ba34b-111">Después de la lista de parámetros, escriba una expresión única como el cuerpo de la función.</span><span class="sxs-lookup"><span data-stu-id="ba34b-111">Following the parameter list, type a single expression as the body of the function.</span></span> <span data-ttu-id="ba34b-112">El valor que se evalúa como la expresión es el valor devuelto por la función.</span><span class="sxs-lookup"><span data-stu-id="ba34b-112">The value that the expression evaluates to is the value returned by the function.</span></span> <span data-ttu-id="ba34b-113">No se usa un `As` cláusula para especificar el tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="ba34b-113">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
     <span data-ttu-id="ba34b-114">Se llama a la expresión lambda pasando un argumento entero.</span><span class="sxs-lookup"><span data-stu-id="ba34b-114">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
4. <span data-ttu-id="ba34b-115">Como alternativa, se consigue el mismo resultado en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ba34b-115">Alternatively, the same result is accomplished by the following example:</span></span>  
  
     [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a><span data-ttu-id="ba34b-116">Para crear una subrutina de expresión lambda de línea</span><span class="sxs-lookup"><span data-stu-id="ba34b-116">To create a single-line lambda expression subroutine</span></span>  
  
1. <span data-ttu-id="ba34b-117">En cualquier situación donde se podría usar un tipo de delegado, escriba la palabra clave `Sub`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ba34b-117">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="ba34b-118">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="ba34b-118">`Dim add1 =`   `Sub`</span></span>  
  
2. <span data-ttu-id="ba34b-119">Entre paréntesis, directamente después `Sub`, escriba los parámetros de la subrutina.</span><span class="sxs-lookup"><span data-stu-id="ba34b-119">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="ba34b-120">Tenga en cuenta que no se especifica un nombre después de `Sub`.</span><span class="sxs-lookup"><span data-stu-id="ba34b-120">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="ba34b-121">`Dim add1 = Sub`   `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="ba34b-121">`Dim add1 = Sub`   `(msg As String)`</span></span>  
  
3. <span data-ttu-id="ba34b-122">Después de la lista de parámetros, escriba una sola instrucción como cuerpo de la subrutina.</span><span class="sxs-lookup"><span data-stu-id="ba34b-122">Following the parameter list, type a single statement as the body of the subroutine.</span></span>  
  
     [!code-vb[VbVbalrLambdas#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#17)]  
  
     <span data-ttu-id="ba34b-123">Se llama a la expresión lambda pasando un argumento de cadena.</span><span class="sxs-lookup"><span data-stu-id="ba34b-123">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#18)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a><span data-ttu-id="ba34b-124">Para crear una función de la expresión lambda de varias líneas</span><span class="sxs-lookup"><span data-stu-id="ba34b-124">To create a multiline lambda expression function</span></span>  
  
1. <span data-ttu-id="ba34b-125">En cualquier situación donde se podría usar un tipo de delegado, escriba la palabra clave `Function`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ba34b-125">In any situation where a delegate type could be used, type the keyword `Function`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="ba34b-126">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="ba34b-126">`Dim add1 =`   `Function`</span></span>  
  
2. <span data-ttu-id="ba34b-127">Entre paréntesis, directamente después `Function`, escriba los parámetros de la función.</span><span class="sxs-lookup"><span data-stu-id="ba34b-127">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="ba34b-128">Tenga en cuenta que no se especifica un nombre después de `Function`.</span><span class="sxs-lookup"><span data-stu-id="ba34b-128">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="ba34b-129">`Dim add1 = Function`   `(index As Integer)`</span><span class="sxs-lookup"><span data-stu-id="ba34b-129">`Dim add1 = Function`   `(index As Integer)`</span></span>  
  
3. <span data-ttu-id="ba34b-130">Presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="ba34b-130">Press ENTER.</span></span> <span data-ttu-id="ba34b-131">El `End Function` instrucción se agrega automáticamente.</span><span class="sxs-lookup"><span data-stu-id="ba34b-131">The `End Function` statement is automatically added.</span></span>  
  
4. <span data-ttu-id="ba34b-132">Dentro del cuerpo de la función, agregue el código siguiente para crear una expresión y el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="ba34b-132">Within the body of the function, add the following code to create an expression and return the value.</span></span> <span data-ttu-id="ba34b-133">No se usa un `As` cláusula para especificar el tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="ba34b-133">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#19)]  
  
     <span data-ttu-id="ba34b-134">Se llama a la expresión lambda pasando un argumento entero.</span><span class="sxs-lookup"><span data-stu-id="ba34b-134">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#20)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a><span data-ttu-id="ba34b-135">Para crear una subrutina de expresión lambda de varias líneas</span><span class="sxs-lookup"><span data-stu-id="ba34b-135">To create a multiline lambda expression subroutine</span></span>  
  
1. <span data-ttu-id="ba34b-136">En cualquier situación donde se podría usar un tipo de delegado, escriba la palabra clave `Sub`, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ba34b-136">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example:</span></span>  
  
     <span data-ttu-id="ba34b-137">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="ba34b-137">`Dim add1 =`   `Sub`</span></span>  
  
2. <span data-ttu-id="ba34b-138">Entre paréntesis, directamente después `Sub`, escriba los parámetros de la subrutina.</span><span class="sxs-lookup"><span data-stu-id="ba34b-138">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="ba34b-139">Tenga en cuenta que no se especifica un nombre después de `Sub`.</span><span class="sxs-lookup"><span data-stu-id="ba34b-139">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="ba34b-140">`Dim add1 = Sub`  `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="ba34b-140">`Dim add1 = Sub`  `(msg As String)`</span></span>  
  
3. <span data-ttu-id="ba34b-141">Presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="ba34b-141">Press ENTER.</span></span> <span data-ttu-id="ba34b-142">El `End Sub` instrucción se agrega automáticamente.</span><span class="sxs-lookup"><span data-stu-id="ba34b-142">The `End Sub` statement is automatically added.</span></span>  
  
4. <span data-ttu-id="ba34b-143">Dentro del cuerpo de la función, agregue el código siguiente para ejecutar cuando se invoca la subrutina.</span><span class="sxs-lookup"><span data-stu-id="ba34b-143">Within the body of the function, add the following code to execute when the subroutine is invoked.</span></span>  
  
     [!code-vb[VbVbalrLambdas#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#21)]  
  
     <span data-ttu-id="ba34b-144">Se llama a la expresión lambda pasando un argumento de cadena.</span><span class="sxs-lookup"><span data-stu-id="ba34b-144">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#22)]  
  
## <a name="example"></a><span data-ttu-id="ba34b-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ba34b-145">Example</span></span>  
 <span data-ttu-id="ba34b-146">Es un uso común de las expresiones lambda definir una función que puede pasarse como argumento para un parámetro cuyo tipo es `Delegate`.</span><span class="sxs-lookup"><span data-stu-id="ba34b-146">A common use of lambda expressions is to define a function that can be passed in as the argument for a parameter whose type is `Delegate`.</span></span> <span data-ttu-id="ba34b-147">En el ejemplo siguiente, la <xref:System.Diagnostics.Process.GetProcesses%2A> método devuelve una matriz de los procesos que se ejecutan en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="ba34b-147">In the following example, the <xref:System.Diagnostics.Process.GetProcesses%2A> method returns an array of the processes running on the local computer.</span></span> <span data-ttu-id="ba34b-148">El <xref:System.Linq.Enumerable.Where%2A> método desde el <xref:System.Linq.Enumerable> clase requiere un `Boolean` delegar como su argumento.</span><span class="sxs-lookup"><span data-stu-id="ba34b-148">The <xref:System.Linq.Enumerable.Where%2A> method from the <xref:System.Linq.Enumerable> class requires a `Boolean` delegate as its argument.</span></span> <span data-ttu-id="ba34b-149">La expresión lambda en el ejemplo se usa para ese propósito.</span><span class="sxs-lookup"><span data-stu-id="ba34b-149">The lambda expression in the example is used for that purpose.</span></span> <span data-ttu-id="ba34b-150">Devuelve `True` para cada proceso que tiene un solo subproceso, y que estén seleccionadas en `filteredList`.</span><span class="sxs-lookup"><span data-stu-id="ba34b-150">It returns `True` for each process that has only one thread, and those are selected in `filteredList`.</span></span>  
  
 [!code-vb[VbVbalrLambdas#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class4.vb#10)]  
  
 <span data-ttu-id="ba34b-151">El ejemplo anterior es equivalente al código siguiente, que está escrito en [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] sintaxis:</span><span class="sxs-lookup"><span data-stu-id="ba34b-151">The previous example is equivalent to the following code, which is written in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] syntax:</span></span>  
  
 [!code-vb[VbVbalrLambdas#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class5.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="ba34b-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba34b-152">See also</span></span>

- <xref:System.Linq.Enumerable>
- [<span data-ttu-id="ba34b-153">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="ba34b-153">Lambda Expressions</span></span>](./lambda-expressions.md)
- [<span data-ttu-id="ba34b-154">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ba34b-154">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="ba34b-155">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ba34b-155">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="ba34b-156">Delegados</span><span class="sxs-lookup"><span data-stu-id="ba34b-156">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="ba34b-157">Cómo: Pasar procedimientos a otro procedimiento en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ba34b-157">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="ba34b-158">Delegate (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ba34b-158">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="ba34b-159">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ba34b-159">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
