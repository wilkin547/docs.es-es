---
title: Expresión de función (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
ms.openlocfilehash: 0ab4a77395b478df06f34240212438f3e6e18f6e
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592203"
---
# <a name="function-expression-visual-basic"></a><span data-ttu-id="8dda8-102">Expresión de función (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8dda8-102">Function Expression (Visual Basic)</span></span>
<span data-ttu-id="8dda8-103">Declara los parámetros y el código que definen una expresión lambda de función.</span><span class="sxs-lookup"><span data-stu-id="8dda8-103">Declares the parameters and code that define a function lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8dda8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8dda8-104">Syntax</span></span>  
  
```vb  
Function ( [ parameterlist ] ) expression  
- or -  
Function ( [ parameterlist ] )  
  [ statements ]  
End Function  
```  
  
## <a name="parts"></a><span data-ttu-id="8dda8-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="8dda8-105">Parts</span></span>  
  
|<span data-ttu-id="8dda8-106">Término</span><span class="sxs-lookup"><span data-stu-id="8dda8-106">Term</span></span>|<span data-ttu-id="8dda8-107">Definición</span><span class="sxs-lookup"><span data-stu-id="8dda8-107">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="8dda8-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="8dda8-108">Optional.</span></span> <span data-ttu-id="8dda8-109">Una lista de nombres de variables locales que representan los parámetros de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="8dda8-109">A list of local variable names that represent the parameters of this procedure.</span></span> <span data-ttu-id="8dda8-110">Los paréntesis deben estar presentes incluso cuando la lista esté vacía.</span><span class="sxs-lookup"><span data-stu-id="8dda8-110">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="8dda8-111">Vea [lista de parámetros](../../../visual-basic/language-reference/statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="8dda8-111">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`expression`|<span data-ttu-id="8dda8-112">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="8dda8-112">Required.</span></span> <span data-ttu-id="8dda8-113">Expresión única.</span><span class="sxs-lookup"><span data-stu-id="8dda8-113">A single expression.</span></span> <span data-ttu-id="8dda8-114">El tipo de la expresión es el tipo de valor devuelto de la función.</span><span class="sxs-lookup"><span data-stu-id="8dda8-114">The type of the expression is the return type of the function.</span></span>|  
|`statements`|<span data-ttu-id="8dda8-115">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="8dda8-115">Required.</span></span> <span data-ttu-id="8dda8-116">Una lista de instrucciones que devuelven un valor mediante la instrucción `Return`.</span><span class="sxs-lookup"><span data-stu-id="8dda8-116">A list of statements that returns a value by using the `Return` statement.</span></span> <span data-ttu-id="8dda8-117">(Consulte la [instrucción return](../../../visual-basic/language-reference/statements/return-statement.md)). El tipo del valor devuelto es el tipo de valor devuelto de la función.</span><span class="sxs-lookup"><span data-stu-id="8dda8-117">(See [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).) The type of the value returned is the return type of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8dda8-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8dda8-118">Remarks</span></span>  
 <span data-ttu-id="8dda8-119">Una *expresión lambda* es una función sin un nombre que calcula y devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="8dda8-119">A *lambda expression* is a function without a name that calculates and returns a value.</span></span> <span data-ttu-id="8dda8-120">Puede usar una expresión lambda en cualquier lugar en el que pueda usar un tipo de delegado, excepto como argumento para `RemoveHandler`.</span><span class="sxs-lookup"><span data-stu-id="8dda8-120">You can use a lambda expression anywhere you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="8dda8-121">Para obtener más información sobre los delegados y el uso de expresiones lambda con delegados, vea [instrucción Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md) y [conversión de delegado relajado](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="8dda8-121">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="8dda8-122">Sintaxis de la expresión lambda</span><span class="sxs-lookup"><span data-stu-id="8dda8-122">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="8dda8-123">La sintaxis de una expresión lambda es similar a la de una función estándar.</span><span class="sxs-lookup"><span data-stu-id="8dda8-123">The syntax of a lambda expression resembles that of a standard function.</span></span> <span data-ttu-id="8dda8-124">Las diferencias son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="8dda8-124">The differences are as follows:</span></span>  
  
- <span data-ttu-id="8dda8-125">Una expresión lambda no tiene un nombre.</span><span class="sxs-lookup"><span data-stu-id="8dda8-125">A lambda expression does not have a name.</span></span>  
  
- <span data-ttu-id="8dda8-126">Las expresiones lambda no pueden tener modificadores, como `Overloads` o `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="8dda8-126">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>  
  
- <span data-ttu-id="8dda8-127">Las expresiones lambda no usan una cláusula `As` para designar el tipo de valor devuelto de la función.</span><span class="sxs-lookup"><span data-stu-id="8dda8-127">Lambda expressions do not use an `As` clause to designate the return type of the function.</span></span> <span data-ttu-id="8dda8-128">En su lugar, el tipo se deduce del valor que el cuerpo de una expresión lambda de una sola línea evalúa como, o el valor devuelto de una expresión lambda de varias líneas.</span><span class="sxs-lookup"><span data-stu-id="8dda8-128">Instead, the type is inferred from the value that the body of a single-line lambda expression evaluates to, or the return value of a multiline lambda expression.</span></span> <span data-ttu-id="8dda8-129">Por ejemplo, si el cuerpo de una expresión lambda de una sola línea es `Where cust.City = "London"`, su tipo de valor devuelto es `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="8dda8-129">For example, if the body of a single-line lambda expression is `Where cust.City = "London"`, its return type is `Boolean`.</span></span>  
  
- <span data-ttu-id="8dda8-130">El cuerpo de una expresión lambda de una sola línea debe ser una expresión, no una instrucción.</span><span class="sxs-lookup"><span data-stu-id="8dda8-130">The body of a single-line lambda expression must be an expression, not a statement.</span></span> <span data-ttu-id="8dda8-131">El cuerpo puede constar de una llamada a un procedimiento de función, pero no una llamada a un procedimiento Sub.</span><span class="sxs-lookup"><span data-stu-id="8dda8-131">The body can consist of a call to a function procedure, but not a call to a sub procedure.</span></span>  
  
- <span data-ttu-id="8dda8-132">Todos los parámetros deben tener tipos de datos especificados o todos deben ser inferidos.</span><span class="sxs-lookup"><span data-stu-id="8dda8-132">Either all parameters must have specified data types or all must be inferred.</span></span>  
  
- <span data-ttu-id="8dda8-133">No se permiten parámetros opcionales y ParamArray.</span><span class="sxs-lookup"><span data-stu-id="8dda8-133">Optional and Paramarray parameters are not permitted.</span></span>  
  
- <span data-ttu-id="8dda8-134">No se permiten parámetros genéricos.</span><span class="sxs-lookup"><span data-stu-id="8dda8-134">Generic parameters are not permitted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8dda8-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8dda8-135">Example</span></span>  
 <span data-ttu-id="8dda8-136">En los ejemplos siguientes se muestran dos maneras de crear expresiones lambda simples.</span><span class="sxs-lookup"><span data-stu-id="8dda8-136">The following examples show two ways to create simple lambda expressions.</span></span> <span data-ttu-id="8dda8-137">El primero usa un `Dim` para proporcionar un nombre para la función.</span><span class="sxs-lookup"><span data-stu-id="8dda8-137">The first uses a `Dim` to provide a name for the function.</span></span> <span data-ttu-id="8dda8-138">Para llamar a la función, envíe un valor para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="8dda8-138">To call the function, you send in a value for the parameter.</span></span>  
  
 [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
 [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="8dda8-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8dda8-139">Example</span></span>  
 <span data-ttu-id="8dda8-140">Como alternativa, puede declarar y ejecutar la función al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="8dda8-140">Alternatively, you can declare and run the function at the same time.</span></span>  
  
 [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="8dda8-141">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8dda8-141">Example</span></span>  
 <span data-ttu-id="8dda8-142">A continuación se muestra un ejemplo de una expresión lambda que incrementa su argumento y devuelve el valor.</span><span class="sxs-lookup"><span data-stu-id="8dda8-142">Following is an example of a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="8dda8-143">En el ejemplo se muestra la sintaxis de la expresión lambda de una sola línea y de varias líneas para una función.</span><span class="sxs-lookup"><span data-stu-id="8dda8-143">The example shows both the single-line and multiline lambda expression syntax for a function.</span></span> <span data-ttu-id="8dda8-144">Para obtener más ejemplos, consulte [expresiones lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="8dda8-144">For more examples, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]  
  
## <a name="example"></a><span data-ttu-id="8dda8-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8dda8-145">Example</span></span>  
 <span data-ttu-id="8dda8-146">Las expresiones lambda subyacen a muchos de los operadores de consulta de [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] y se pueden usar explícitamente en las consultas basadas en métodos.</span><span class="sxs-lookup"><span data-stu-id="8dda8-146">Lambda expressions underlie many of the query operators in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)], and can be used explicitly in method-based queries.</span></span> <span data-ttu-id="8dda8-147">En el ejemplo siguiente se muestra una consulta [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] típica, seguida de la conversión de la consulta en formato de método.</span><span class="sxs-lookup"><span data-stu-id="8dda8-147">The following example shows a typical [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, followed by the translation of the query into method format.</span></span>  
  
```vb  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 <span data-ttu-id="8dda8-148">Para obtener más información sobre los métodos de consulta, vea [consultas](../../../visual-basic/language-reference/queries/index.md).</span><span class="sxs-lookup"><span data-stu-id="8dda8-148">For more information about query methods, see [Queries](../../../visual-basic/language-reference/queries/index.md).</span></span> <span data-ttu-id="8dda8-149">Para obtener más información acerca de los operadores de consulta estándar, vea [información general sobre operadores de consulta estándar](../../programming-guide/concepts/linq/standard-query-operators-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8dda8-149">For more information about standard query operators, see [Standard Query Operators Overview](../../programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dda8-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="8dda8-150">See also</span></span>

- [<span data-ttu-id="8dda8-151">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8dda8-151">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="8dda8-152">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="8dda8-152">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="8dda8-153">Operadores y expresiones</span><span class="sxs-lookup"><span data-stu-id="8dda8-153">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="8dda8-154">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="8dda8-154">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="8dda8-155">Comparaciones de valores</span><span class="sxs-lookup"><span data-stu-id="8dda8-155">Value Comparisons</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [<span data-ttu-id="8dda8-156">Expresiones booleanas</span><span class="sxs-lookup"><span data-stu-id="8dda8-156">Boolean Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [<span data-ttu-id="8dda8-157">If (operador)</span><span class="sxs-lookup"><span data-stu-id="8dda8-157">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
- [<span data-ttu-id="8dda8-158">Conversión de delegado flexible</span><span class="sxs-lookup"><span data-stu-id="8dda8-158">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
