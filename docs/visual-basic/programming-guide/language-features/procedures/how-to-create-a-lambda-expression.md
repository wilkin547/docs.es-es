---
title: Filtrar Crear una expresión Lambda (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
ms.openlocfilehash: fc2b7ed2004b842116d051b393f00506428def61
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59344551"
---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a><span data-ttu-id="f63e6-102">Filtrar Crear una expresión Lambda (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f63e6-102">How to: Create a Lambda Expression (Visual Basic)</span></span>
<span data-ttu-id="f63e6-103">Un *expresión lambda* es una función o subrutina que no tiene un nombre.</span><span class="sxs-lookup"><span data-stu-id="f63e6-103">A *lambda expression* is a function or subroutine that does not have a name.</span></span> <span data-ttu-id="f63e6-104">Una expresión lambda puede usarse siempre que sea un tipo de delegado es válido.</span><span class="sxs-lookup"><span data-stu-id="f63e6-104">A lambda expression can be used wherever a delegate type is valid.</span></span>  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a><span data-ttu-id="f63e6-105">Para crear una función de la expresión lambda de línea</span><span class="sxs-lookup"><span data-stu-id="f63e6-105">To create a single-line lambda expression function</span></span>  
  
1. <span data-ttu-id="f63e6-106">En cualquier situación donde se podría usar un tipo de delegado, escriba la palabra clave `Function`, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f63e6-106">In any situation where a delegate type could be used, type the keyword `Function`, as in the following example:</span></span>  
  
     `Dim add1 =`   `Function`  
  
2. <span data-ttu-id="f63e6-107">Entre paréntesis, directamente después `Function`, escriba los parámetros de la función.</span><span class="sxs-lookup"><span data-stu-id="f63e6-107">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="f63e6-108">Tenga en cuenta que no se especifica un nombre después de `Function`.</span><span class="sxs-lookup"><span data-stu-id="f63e6-108">Notice that you do not specify a name after `Function`.</span></span>  
  
     `Dim add1 = Function`   `(num As Integer)`  
  
3. <span data-ttu-id="f63e6-109">Después de la lista de parámetros, escriba una expresión única como el cuerpo de la función.</span><span class="sxs-lookup"><span data-stu-id="f63e6-109">Following the parameter list, type a single expression as the body of the function.</span></span> <span data-ttu-id="f63e6-110">El valor que se evalúa como la expresión es el valor devuelto por la función.</span><span class="sxs-lookup"><span data-stu-id="f63e6-110">The value that the expression evaluates to is the value returned by the function.</span></span> <span data-ttu-id="f63e6-111">No se usa un `As` cláusula para especificar el tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="f63e6-111">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
     <span data-ttu-id="f63e6-112">Se llama a la expresión lambda pasando un argumento entero.</span><span class="sxs-lookup"><span data-stu-id="f63e6-112">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
4. <span data-ttu-id="f63e6-113">Como alternativa, se consigue el mismo resultado en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f63e6-113">Alternatively, the same result is accomplished by the following example:</span></span>  
  
     [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a><span data-ttu-id="f63e6-114">Para crear una subrutina de expresión lambda de línea</span><span class="sxs-lookup"><span data-stu-id="f63e6-114">To create a single-line lambda expression subroutine</span></span>  
  
1. <span data-ttu-id="f63e6-115">En cualquier situación donde se podría usar un tipo de delegado, escriba la palabra clave `Sub`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f63e6-115">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example.</span></span>  
  
     `Dim add1 =`   `Sub`  
  
2. <span data-ttu-id="f63e6-116">Entre paréntesis, directamente después `Sub`, escriba los parámetros de la subrutina.</span><span class="sxs-lookup"><span data-stu-id="f63e6-116">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="f63e6-117">Tenga en cuenta que no se especifica un nombre después de `Sub`.</span><span class="sxs-lookup"><span data-stu-id="f63e6-117">Notice that you do not specify a name after `Sub`.</span></span>  
  
     `Dim add1 = Sub`   `(msg As String)`  
  
3. <span data-ttu-id="f63e6-118">Después de la lista de parámetros, escriba una sola instrucción como cuerpo de la subrutina.</span><span class="sxs-lookup"><span data-stu-id="f63e6-118">Following the parameter list, type a single statement as the body of the subroutine.</span></span>  
  
     [!code-vb[VbVbalrLambdas#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#17)]  
  
     <span data-ttu-id="f63e6-119">Se llama a la expresión lambda pasando un argumento de cadena.</span><span class="sxs-lookup"><span data-stu-id="f63e6-119">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#18)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a><span data-ttu-id="f63e6-120">Para crear una función de la expresión lambda de varias líneas</span><span class="sxs-lookup"><span data-stu-id="f63e6-120">To create a multiline lambda expression function</span></span>  
  
1. <span data-ttu-id="f63e6-121">En cualquier situación donde se podría usar un tipo de delegado, escriba la palabra clave `Function`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f63e6-121">In any situation where a delegate type could be used, type the keyword `Function`, as shown in the following example.</span></span>  
  
     `Dim add1 =`   `Function`  
  
2. <span data-ttu-id="f63e6-122">Entre paréntesis, directamente después `Function`, escriba los parámetros de la función.</span><span class="sxs-lookup"><span data-stu-id="f63e6-122">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="f63e6-123">Tenga en cuenta que no se especifica un nombre después de `Function`.</span><span class="sxs-lookup"><span data-stu-id="f63e6-123">Notice that you do not specify a name after `Function`.</span></span>  
  
     `Dim add1 = Function`   `(index As Integer)`  
  
3. <span data-ttu-id="f63e6-124">Presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="f63e6-124">Press ENTER.</span></span> <span data-ttu-id="f63e6-125">El `End Function` instrucción se agrega automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f63e6-125">The `End Function` statement is automatically added.</span></span>  
  
4. <span data-ttu-id="f63e6-126">Dentro del cuerpo de la función, agregue el código siguiente para crear una expresión y el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="f63e6-126">Within the body of the function, add the following code to create an expression and return the value.</span></span> <span data-ttu-id="f63e6-127">No se usa un `As` cláusula para especificar el tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="f63e6-127">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#19)]  
  
     <span data-ttu-id="f63e6-128">Se llama a la expresión lambda pasando un argumento entero.</span><span class="sxs-lookup"><span data-stu-id="f63e6-128">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#20)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a><span data-ttu-id="f63e6-129">Para crear una subrutina de expresión lambda de varias líneas</span><span class="sxs-lookup"><span data-stu-id="f63e6-129">To create a multiline lambda expression subroutine</span></span>  
  
1. <span data-ttu-id="f63e6-130">En cualquier situación donde se podría usar un tipo de delegado, escriba la palabra clave `Sub`, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f63e6-130">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example:</span></span>  
  
     `Dim add1 =`   `Sub`  
  
2. <span data-ttu-id="f63e6-131">Entre paréntesis, directamente después `Sub`, escriba los parámetros de la subrutina.</span><span class="sxs-lookup"><span data-stu-id="f63e6-131">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="f63e6-132">Tenga en cuenta que no se especifica un nombre después de `Sub`.</span><span class="sxs-lookup"><span data-stu-id="f63e6-132">Notice that you do not specify a name after `Sub`.</span></span>  
  
     `Dim add1 = Sub`  `(msg As String)`  
  
3. <span data-ttu-id="f63e6-133">Presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="f63e6-133">Press ENTER.</span></span> <span data-ttu-id="f63e6-134">El `End Sub` instrucción se agrega automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f63e6-134">The `End Sub` statement is automatically added.</span></span>  
  
4. <span data-ttu-id="f63e6-135">Dentro del cuerpo de la función, agregue el código siguiente para ejecutar cuando se invoca la subrutina.</span><span class="sxs-lookup"><span data-stu-id="f63e6-135">Within the body of the function, add the following code to execute when the subroutine is invoked.</span></span>  
  
     [!code-vb[VbVbalrLambdas#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#21)]  
  
     <span data-ttu-id="f63e6-136">Se llama a la expresión lambda pasando un argumento de cadena.</span><span class="sxs-lookup"><span data-stu-id="f63e6-136">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#22)]  
  
## <a name="example"></a><span data-ttu-id="f63e6-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f63e6-137">Example</span></span>  
 <span data-ttu-id="f63e6-138">Es un uso común de las expresiones lambda definir una función que puede pasarse como argumento para un parámetro cuyo tipo es `Delegate`.</span><span class="sxs-lookup"><span data-stu-id="f63e6-138">A common use of lambda expressions is to define a function that can be passed in as the argument for a parameter whose type is `Delegate`.</span></span> <span data-ttu-id="f63e6-139">En el ejemplo siguiente, la <xref:System.Diagnostics.Process.GetProcesses%2A> método devuelve una matriz de los procesos que se ejecutan en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="f63e6-139">In the following example, the <xref:System.Diagnostics.Process.GetProcesses%2A> method returns an array of the processes running on the local computer.</span></span> <span data-ttu-id="f63e6-140">El <xref:System.Linq.Enumerable.Where%2A> método desde el <xref:System.Linq.Enumerable> clase requiere un `Boolean` delegar como su argumento.</span><span class="sxs-lookup"><span data-stu-id="f63e6-140">The <xref:System.Linq.Enumerable.Where%2A> method from the <xref:System.Linq.Enumerable> class requires a `Boolean` delegate as its argument.</span></span> <span data-ttu-id="f63e6-141">La expresión lambda en el ejemplo se usa para ese propósito.</span><span class="sxs-lookup"><span data-stu-id="f63e6-141">The lambda expression in the example is used for that purpose.</span></span> <span data-ttu-id="f63e6-142">Devuelve `True` para cada proceso que tiene un solo subproceso, y que estén seleccionadas en `filteredList`.</span><span class="sxs-lookup"><span data-stu-id="f63e6-142">It returns `True` for each process that has only one thread, and those are selected in `filteredList`.</span></span>  
  
 [!code-vb[VbVbalrLambdas#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class4.vb#10)]  
  
 <span data-ttu-id="f63e6-143">El ejemplo anterior es equivalente al código siguiente, que está escrito en [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] sintaxis:</span><span class="sxs-lookup"><span data-stu-id="f63e6-143">The previous example is equivalent to the following code, which is written in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] syntax:</span></span>  
  
 [!code-vb[VbVbalrLambdas#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class5.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="f63e6-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="f63e6-144">See also</span></span>

- <xref:System.Linq.Enumerable>
- [<span data-ttu-id="f63e6-145">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="f63e6-145">Lambda Expressions</span></span>](./lambda-expressions.md)
- [<span data-ttu-id="f63e6-146">Function (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="f63e6-146">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="f63e6-147">Sub (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="f63e6-147">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="f63e6-148">Delegados</span><span class="sxs-lookup"><span data-stu-id="f63e6-148">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="f63e6-149">Filtrar Pasar procedimientos a otro procedimiento en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f63e6-149">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="f63e6-150">Delegate (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="f63e6-150">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="f63e6-151">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f63e6-151">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
