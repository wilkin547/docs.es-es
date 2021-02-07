---
description: 'Más información acerca de: expresión de función (Visual Basic)'
title: Expresión Function
ms.date: 07/20/2015
helpviewer_keywords:
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
ms.openlocfilehash: bef5db7f167b615c2a0c20539521c186683da985
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99666022"
---
# <a name="function-expression-visual-basic"></a><span data-ttu-id="67c18-103">Expresión de función (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67c18-103">Function Expression (Visual Basic)</span></span>

<span data-ttu-id="67c18-104">Declara los parámetros y el código que definen una expresión lambda de función.</span><span class="sxs-lookup"><span data-stu-id="67c18-104">Declares the parameters and code that define a function lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67c18-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="67c18-105">Syntax</span></span>  
  
```vb  
Function ( [ parameterlist ] ) expression  
- or -  
Function ( [ parameterlist ] )  
  [ statements ]  
End Function  
```  
  
## <a name="parts"></a><span data-ttu-id="67c18-106">Partes</span><span class="sxs-lookup"><span data-stu-id="67c18-106">Parts</span></span>  
  
|<span data-ttu-id="67c18-107">Término</span><span class="sxs-lookup"><span data-stu-id="67c18-107">Term</span></span>|<span data-ttu-id="67c18-108">Definición</span><span class="sxs-lookup"><span data-stu-id="67c18-108">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="67c18-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="67c18-109">Optional.</span></span> <span data-ttu-id="67c18-110">Una lista de nombres de variables locales que representan los parámetros de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="67c18-110">A list of local variable names that represent the parameters of this procedure.</span></span> <span data-ttu-id="67c18-111">Los paréntesis deben estar presentes incluso cuando la lista esté vacía.</span><span class="sxs-lookup"><span data-stu-id="67c18-111">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="67c18-112">Vea [lista de parámetros](../statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="67c18-112">See [Parameter List](../statements/parameter-list.md).</span></span>|  
|`expression`|<span data-ttu-id="67c18-113">Necesario.</span><span class="sxs-lookup"><span data-stu-id="67c18-113">Required.</span></span> <span data-ttu-id="67c18-114">Expresión única.</span><span class="sxs-lookup"><span data-stu-id="67c18-114">A single expression.</span></span> <span data-ttu-id="67c18-115">El tipo de la expresión es el tipo de valor devuelto de la función.</span><span class="sxs-lookup"><span data-stu-id="67c18-115">The type of the expression is the return type of the function.</span></span>|  
|`statements`|<span data-ttu-id="67c18-116">Necesario.</span><span class="sxs-lookup"><span data-stu-id="67c18-116">Required.</span></span> <span data-ttu-id="67c18-117">Una lista de instrucciones que devuelven un valor mediante la `Return` instrucción.</span><span class="sxs-lookup"><span data-stu-id="67c18-117">A list of statements that returns a value by using the `Return` statement.</span></span> <span data-ttu-id="67c18-118">(Consulte la [instrucción return](../statements/return-statement.md)). El tipo del valor devuelto es el tipo de valor devuelto de la función.</span><span class="sxs-lookup"><span data-stu-id="67c18-118">(See [Return Statement](../statements/return-statement.md).) The type of the value returned is the return type of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67c18-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="67c18-119">Remarks</span></span>  

 <span data-ttu-id="67c18-120">Una *expresión lambda* es una función sin un nombre que calcula y devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="67c18-120">A *lambda expression* is a function without a name that calculates and returns a value.</span></span> <span data-ttu-id="67c18-121">Puede usar una expresión lambda en cualquier lugar en el que pueda usar un tipo de delegado, excepto como argumento para `RemoveHandler` .</span><span class="sxs-lookup"><span data-stu-id="67c18-121">You can use a lambda expression anywhere you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="67c18-122">Para obtener más información sobre los delegados y el uso de expresiones lambda con delegados, vea [instrucción Delegate](../statements/delegate-statement.md) y [conversión de delegado relajado](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="67c18-122">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="67c18-123">Sintaxis de la expresión lambda</span><span class="sxs-lookup"><span data-stu-id="67c18-123">Lambda Expression Syntax</span></span>  

 <span data-ttu-id="67c18-124">La sintaxis de una expresión lambda es similar a la de una función estándar.</span><span class="sxs-lookup"><span data-stu-id="67c18-124">The syntax of a lambda expression resembles that of a standard function.</span></span> <span data-ttu-id="67c18-125">Las diferencias son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="67c18-125">The differences are as follows:</span></span>  
  
- <span data-ttu-id="67c18-126">Una expresión lambda no tiene un nombre.</span><span class="sxs-lookup"><span data-stu-id="67c18-126">A lambda expression does not have a name.</span></span>  
  
- <span data-ttu-id="67c18-127">Las expresiones lambda no pueden tener modificadores, como `Overloads` o `Overrides` .</span><span class="sxs-lookup"><span data-stu-id="67c18-127">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>  
  
- <span data-ttu-id="67c18-128">Las expresiones lambda no usan una `As` cláusula para designar el tipo de valor devuelto de la función.</span><span class="sxs-lookup"><span data-stu-id="67c18-128">Lambda expressions do not use an `As` clause to designate the return type of the function.</span></span> <span data-ttu-id="67c18-129">En su lugar, el tipo se deduce del valor que el cuerpo de una expresión lambda de una sola línea evalúa como, o el valor devuelto de una expresión lambda de varias líneas.</span><span class="sxs-lookup"><span data-stu-id="67c18-129">Instead, the type is inferred from the value that the body of a single-line lambda expression evaluates to, or the return value of a multiline lambda expression.</span></span> <span data-ttu-id="67c18-130">Por ejemplo, si el cuerpo de una expresión lambda de una sola línea es `Where cust.City = "London"` , su tipo de valor devuelto es `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="67c18-130">For example, if the body of a single-line lambda expression is `Where cust.City = "London"`, its return type is `Boolean`.</span></span>  
  
- <span data-ttu-id="67c18-131">El cuerpo de una expresión lambda de una sola línea debe ser una expresión, no una instrucción.</span><span class="sxs-lookup"><span data-stu-id="67c18-131">The body of a single-line lambda expression must be an expression, not a statement.</span></span> <span data-ttu-id="67c18-132">El cuerpo puede constar de una llamada a un procedimiento de función, pero no una llamada a un procedimiento Sub.</span><span class="sxs-lookup"><span data-stu-id="67c18-132">The body can consist of a call to a function procedure, but not a call to a sub procedure.</span></span>  
  
- <span data-ttu-id="67c18-133">Todos los parámetros deben tener tipos de datos especificados o todos deben ser inferidos.</span><span class="sxs-lookup"><span data-stu-id="67c18-133">Either all parameters must have specified data types or all must be inferred.</span></span>  
  
- <span data-ttu-id="67c18-134">No se permiten parámetros opcionales y ParamArray.</span><span class="sxs-lookup"><span data-stu-id="67c18-134">Optional and Paramarray parameters are not permitted.</span></span>  
  
- <span data-ttu-id="67c18-135">No se permiten parámetros genéricos.</span><span class="sxs-lookup"><span data-stu-id="67c18-135">Generic parameters are not permitted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67c18-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="67c18-136">Example</span></span>  

 <span data-ttu-id="67c18-137">En los ejemplos siguientes se muestran dos maneras de crear expresiones lambda simples.</span><span class="sxs-lookup"><span data-stu-id="67c18-137">The following examples show two ways to create simple lambda expressions.</span></span> <span data-ttu-id="67c18-138">El primero usa `Dim` para proporcionar un nombre para la función.</span><span class="sxs-lookup"><span data-stu-id="67c18-138">The first uses a `Dim` to provide a name for the function.</span></span> <span data-ttu-id="67c18-139">Para llamar a la función, envíe un valor para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="67c18-139">To call the function, you send in a value for the parameter.</span></span>  
  
 [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
 [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="67c18-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="67c18-140">Example</span></span>  

 <span data-ttu-id="67c18-141">Como alternativa, puede declarar y ejecutar la función al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="67c18-141">Alternatively, you can declare and run the function at the same time.</span></span>  
  
 [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="67c18-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="67c18-142">Example</span></span>  

 <span data-ttu-id="67c18-143">A continuación se muestra un ejemplo de una expresión lambda que incrementa su argumento y devuelve el valor.</span><span class="sxs-lookup"><span data-stu-id="67c18-143">Following is an example of a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="67c18-144">En el ejemplo se muestra la sintaxis de la expresión lambda de una sola línea y de varias líneas para una función.</span><span class="sxs-lookup"><span data-stu-id="67c18-144">The example shows both the single-line and multiline lambda expression syntax for a function.</span></span> <span data-ttu-id="67c18-145">Para obtener más ejemplos, consulte [expresiones lambda](../../programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="67c18-145">For more examples, see [Lambda Expressions](../../programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]  
  
## <a name="example"></a><span data-ttu-id="67c18-146">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="67c18-146">Example</span></span>  

 <span data-ttu-id="67c18-147">Las expresiones lambda subyacen a muchos de los operadores de consulta en Language-Integrated Query (LINQ) y se pueden usar explícitamente en las consultas basadas en métodos.</span><span class="sxs-lookup"><span data-stu-id="67c18-147">Lambda expressions underlie many of the query operators in Language-Integrated Query (LINQ), and can be used explicitly in method-based queries.</span></span> <span data-ttu-id="67c18-148">En el ejemplo siguiente se muestra una consulta LINQ típica, seguida de la conversión de la consulta en formato de método.</span><span class="sxs-lookup"><span data-stu-id="67c18-148">The following example shows a typical LINQ query, followed by the translation of the query into method format.</span></span>  
  
```vb  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 <span data-ttu-id="67c18-149">Para obtener más información sobre los métodos de consulta, vea [consultas](../queries/index.md).</span><span class="sxs-lookup"><span data-stu-id="67c18-149">For more information about query methods, see [Queries](../queries/index.md).</span></span> <span data-ttu-id="67c18-150">Para obtener más información acerca de los operadores de consulta estándar, vea [información general sobre operadores de consulta estándar](../../programming-guide/concepts/linq/standard-query-operators-overview.md).</span><span class="sxs-lookup"><span data-stu-id="67c18-150">For more information about standard query operators, see [Standard Query Operators Overview](../../programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67c18-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="67c18-151">See also</span></span>

- [<span data-ttu-id="67c18-152">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="67c18-152">Function Statement</span></span>](../statements/function-statement.md)
- [<span data-ttu-id="67c18-153">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="67c18-153">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="67c18-154">Operadores y expresiones</span><span class="sxs-lookup"><span data-stu-id="67c18-154">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="67c18-155">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="67c18-155">Statements</span></span>](../../programming-guide/language-features/statements.md)
- [<span data-ttu-id="67c18-156">Comparaciones de valores</span><span class="sxs-lookup"><span data-stu-id="67c18-156">Value Comparisons</span></span>](../../programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [<span data-ttu-id="67c18-157">Expresiones booleanas</span><span class="sxs-lookup"><span data-stu-id="67c18-157">Boolean Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [<span data-ttu-id="67c18-158">Operador If</span><span class="sxs-lookup"><span data-stu-id="67c18-158">If Operator</span></span>](if-operator.md)
- [<span data-ttu-id="67c18-159">Conversión de delegado flexible</span><span class="sxs-lookup"><span data-stu-id="67c18-159">Relaxed Delegate Conversion</span></span>](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
