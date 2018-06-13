---
title: Expresión de función (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
ms.openlocfilehash: 29bf95a336b6f6ed5c9c310c9ea7575a91089361
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604892"
---
# <a name="function-expression-visual-basic"></a><span data-ttu-id="dacc4-102">Expresión de función (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dacc4-102">Function Expression (Visual Basic)</span></span>
<span data-ttu-id="dacc4-103">Declara los parámetros y el código que definen una expresión lambda de función.</span><span class="sxs-lookup"><span data-stu-id="dacc4-103">Declares the parameters and code that define a function lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dacc4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dacc4-104">Syntax</span></span>  
  
```  
Function ( [ parameterlist ] ) expression  
- or -  
Function ( [ parameterlist ] )  
  [ statements ]  
End Function  
```  
  
## <a name="parts"></a><span data-ttu-id="dacc4-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="dacc4-105">Parts</span></span>  
  
|<span data-ttu-id="dacc4-106">Término</span><span class="sxs-lookup"><span data-stu-id="dacc4-106">Term</span></span>|<span data-ttu-id="dacc4-107">Definición</span><span class="sxs-lookup"><span data-stu-id="dacc4-107">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="dacc4-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="dacc4-108">Optional.</span></span> <span data-ttu-id="dacc4-109">Una lista de nombres de variables locales que representan los parámetros de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="dacc4-109">A list of local variable names that represent the parameters of this procedure.</span></span> <span data-ttu-id="dacc4-110">Los paréntesis deben estar presentes incluso cuando la lista está vacía.</span><span class="sxs-lookup"><span data-stu-id="dacc4-110">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="dacc4-111">Vea [lista de parámetros](../../../visual-basic/language-reference/statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="dacc4-111">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`expression`|<span data-ttu-id="dacc4-112">Requerido.</span><span class="sxs-lookup"><span data-stu-id="dacc4-112">Required.</span></span> <span data-ttu-id="dacc4-113">Una sola expresión.</span><span class="sxs-lookup"><span data-stu-id="dacc4-113">A single expression.</span></span> <span data-ttu-id="dacc4-114">El tipo de la expresión es el tipo de valor devuelto de la función.</span><span class="sxs-lookup"><span data-stu-id="dacc4-114">The type of the expression is the return type of the function.</span></span>|  
|`statements`|<span data-ttu-id="dacc4-115">Requerido.</span><span class="sxs-lookup"><span data-stu-id="dacc4-115">Required.</span></span> <span data-ttu-id="dacc4-116">Una lista de instrucciones que devuelve un valor mediante la `Return` instrucción.</span><span class="sxs-lookup"><span data-stu-id="dacc4-116">A list of statements that returns a value by using the `Return` statement.</span></span> <span data-ttu-id="dacc4-117">(Consulte [Return (instrucción)](../../../visual-basic/language-reference/statements/return-statement.md).) El tipo de valor devuelto es el tipo de valor devuelto de la función.</span><span class="sxs-lookup"><span data-stu-id="dacc4-117">(See [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).) The type of the value returned is the return type of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dacc4-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dacc4-118">Remarks</span></span>  
 <span data-ttu-id="dacc4-119">A *expresión lambda* es una función sin un nombre que calcule y devuelva un valor.</span><span class="sxs-lookup"><span data-stu-id="dacc4-119">A *lambda expression* is a function without a name that calculates and returns a value.</span></span> <span data-ttu-id="dacc4-120">Puede usar una expresión lambda en cualquier lugar puede utilizar un tipo de delegado, excepto como argumento a `RemoveHandler`.</span><span class="sxs-lookup"><span data-stu-id="dacc4-120">You can use a lambda expression anywhere you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="dacc4-121">Para obtener más información sobre los delegados y el uso de expresiones lambda con delegados, vea [instrucción Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md) y [conversión de delegado flexible](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="dacc4-121">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="dacc4-122">Sintaxis de la expresión lambda</span><span class="sxs-lookup"><span data-stu-id="dacc4-122">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="dacc4-123">La sintaxis de una expresión lambda es similar a la de una función estándar.</span><span class="sxs-lookup"><span data-stu-id="dacc4-123">The syntax of a lambda expression resembles that of a standard function.</span></span> <span data-ttu-id="dacc4-124">Las diferencias son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="dacc4-124">The differences are as follows:</span></span>  
  
-   <span data-ttu-id="dacc4-125">Una expresión lambda no tiene un nombre.</span><span class="sxs-lookup"><span data-stu-id="dacc4-125">A lambda expression does not have a name.</span></span>  
  
-   <span data-ttu-id="dacc4-126">Las expresiones lambda no pueden tener modificadores, como `Overloads` o `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="dacc4-126">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>  
  
-   <span data-ttu-id="dacc4-127">Las expresiones lambda no utilizan una `As` cláusula para designar el tipo de valor devuelto de la función.</span><span class="sxs-lookup"><span data-stu-id="dacc4-127">Lambda expressions do not use an `As` clause to designate the return type of the function.</span></span> <span data-ttu-id="dacc4-128">En su lugar, el tipo se deduce del valor que se evalúa como el cuerpo de una expresión lambda de línea o el valor devuelto de una expresión lambda de varias líneas.</span><span class="sxs-lookup"><span data-stu-id="dacc4-128">Instead, the type is inferred from the value that the body of a single-line lambda expression evaluates to, or the return value of a multiline lambda expression.</span></span> <span data-ttu-id="dacc4-129">Por ejemplo, si el cuerpo de una expresión lambda de línea `Where cust.City = "London"`, su tipo de valor devuelto es `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="dacc4-129">For example, if the body of a single-line lambda expression is `Where cust.City = "London"`, its return type is `Boolean`.</span></span>  
  
-   <span data-ttu-id="dacc4-130">El cuerpo de una expresión lambda de línea debe ser una expresión, no una instrucción.</span><span class="sxs-lookup"><span data-stu-id="dacc4-130">The body of a single-line lambda expression must be an expression, not a statement.</span></span> <span data-ttu-id="dacc4-131">El cuerpo puede constar de una llamada a un procedimiento de función, pero no es una llamada a un procedimiento sub.</span><span class="sxs-lookup"><span data-stu-id="dacc4-131">The body can consist of a call to a function procedure, but not a call to a sub procedure.</span></span>  
  
-   <span data-ttu-id="dacc4-132">Deben haber especificado todos los parámetros deben deducir los tipos de datos o todos.</span><span class="sxs-lookup"><span data-stu-id="dacc4-132">Either all parameters must have specified data types or all must be inferred.</span></span>  
  
-   <span data-ttu-id="dacc4-133">No se permiten parámetros Optional y Paramarray.</span><span class="sxs-lookup"><span data-stu-id="dacc4-133">Optional and Paramarray parameters are not permitted.</span></span>  
  
-   <span data-ttu-id="dacc4-134">No se permiten parámetros genéricos.</span><span class="sxs-lookup"><span data-stu-id="dacc4-134">Generic parameters are not permitted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dacc4-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dacc4-135">Example</span></span>  
 <span data-ttu-id="dacc4-136">Los ejemplos siguientes muestran dos maneras de crear expresiones lambda simples.</span><span class="sxs-lookup"><span data-stu-id="dacc4-136">The following examples show two ways to create simple lambda expressions.</span></span> <span data-ttu-id="dacc4-137">El primer ejemplo usa un `Dim` para proporcionar un nombre para la función.</span><span class="sxs-lookup"><span data-stu-id="dacc4-137">The first uses a `Dim` to provide a name for the function.</span></span> <span data-ttu-id="dacc4-138">Para llamar a la función, enviar un valor para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="dacc4-138">To call the function, you send in a value for the parameter.</span></span>  
  
 [!code-vb[VbVbalrLambdas#1](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_1.vb)]  
  
 [!code-vb[VbVbalrLambdas#2](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="dacc4-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dacc4-139">Example</span></span>  
 <span data-ttu-id="dacc4-140">Como alternativa, puede declarar y ejecutar la función a la vez.</span><span class="sxs-lookup"><span data-stu-id="dacc4-140">Alternatively, you can declare and run the function at the same time.</span></span>  
  
 [!code-vb[VbVbalrLambdas#3](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="dacc4-141">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dacc4-141">Example</span></span>  
 <span data-ttu-id="dacc4-142">Aquí te mostramos un ejemplo de una expresión lambda que incrementa su argumento y devuelve el valor.</span><span class="sxs-lookup"><span data-stu-id="dacc4-142">Following is an example of a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="dacc4-143">En el ejemplo se muestra la sintaxis de expresiones lambda de varias líneas y de línea para una función.</span><span class="sxs-lookup"><span data-stu-id="dacc4-143">The example shows both the single-line and multiline lambda expression syntax for a function.</span></span> <span data-ttu-id="dacc4-144">Para obtener más ejemplos, vea [expresiones Lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="dacc4-144">For more examples, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbVbalrLambdas#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_4.vb)]  
  
## <a name="example"></a><span data-ttu-id="dacc4-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dacc4-145">Example</span></span>  
 <span data-ttu-id="dacc4-146">Las expresiones lambda subyacen a muchos de los operadores de consulta en [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]y puede utilizarse de forma explícita en consultas basadas en métodos.</span><span class="sxs-lookup"><span data-stu-id="dacc4-146">Lambda expressions underlie many of the query operators in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)], and can be used explicitly in method-based queries.</span></span> <span data-ttu-id="dacc4-147">En el ejemplo siguiente se muestra una típica [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] consulta, seguido por la traducción de la consulta en formato de método.</span><span class="sxs-lookup"><span data-stu-id="dacc4-147">The following example shows a typical [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, followed by the translation of the query into method format.</span></span>  
  
```vb  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 <span data-ttu-id="dacc4-148">Para obtener más información acerca de los métodos de consulta, vea [consultas](../../../visual-basic/language-reference/queries/queries.md).</span><span class="sxs-lookup"><span data-stu-id="dacc4-148">For more information about query methods, see [Queries](../../../visual-basic/language-reference/queries/queries.md).</span></span> <span data-ttu-id="dacc4-149">Para obtener más información acerca de los operadores de consulta estándar, vea [información general sobre operadores de consulta estándar](../../programming-guide/concepts/linq/standard-query-operators-overview.md).</span><span class="sxs-lookup"><span data-stu-id="dacc4-149">For more information about standard query operators, see [Standard Query Operators Overview](../../programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dacc4-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="dacc4-150">See Also</span></span>  
 [<span data-ttu-id="dacc4-151">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="dacc4-151">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="dacc4-152">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="dacc4-152">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [<span data-ttu-id="dacc4-153">Operadores y expresiones</span><span class="sxs-lookup"><span data-stu-id="dacc4-153">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [<span data-ttu-id="dacc4-154">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="dacc4-154">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)  
 [<span data-ttu-id="dacc4-155">Comparaciones de valores</span><span class="sxs-lookup"><span data-stu-id="dacc4-155">Value Comparisons</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [<span data-ttu-id="dacc4-156">Expresiones booleanas</span><span class="sxs-lookup"><span data-stu-id="dacc4-156">Boolean Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [<span data-ttu-id="dacc4-157">If (operador)</span><span class="sxs-lookup"><span data-stu-id="dacc4-157">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)  
 [<span data-ttu-id="dacc4-158">Conversión de delegado flexible</span><span class="sxs-lookup"><span data-stu-id="dacc4-158">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
