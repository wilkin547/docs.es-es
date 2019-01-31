---
title: Procedimiento para ejecutar árboles de expresión (C#)
ms.date: 07/20/2015
ms.assetid: b8c40db5-2464-4bb9-9001-8c2bc7f006c5
ms.openlocfilehash: bed37d8d96837062831f4a3017df8a3633446bf0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54583277"
---
# <a name="how-to-execute-expression-trees-c"></a><span data-ttu-id="97f6f-102">Procedimiento para ejecutar árboles de expresión (C#)</span><span class="sxs-lookup"><span data-stu-id="97f6f-102">How to: Execute Expression Trees (C#)</span></span>
<span data-ttu-id="97f6f-103">En este tema se muestra cómo ejecutar un árbol de expresión.</span><span class="sxs-lookup"><span data-stu-id="97f6f-103">This topic shows you how to execute an expression tree.</span></span> <span data-ttu-id="97f6f-104">La ejecución de un árbol de expresión puede devolver un valor o simplemente realizar una acción, como llamar a un método.</span><span class="sxs-lookup"><span data-stu-id="97f6f-104">Executing an expression tree may return a value, or it may just perform an action such as calling a method.</span></span>  
  
 <span data-ttu-id="97f6f-105">Solo se pueden ejecutar los árboles de expresiones que representan expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="97f6f-105">Only expression trees that represent lambda expressions can be executed.</span></span> <span data-ttu-id="97f6f-106">Los árboles de expresiones que representan expresiones lambda son de tipo <xref:System.Linq.Expressions.LambdaExpression> o <xref:System.Linq.Expressions.Expression%601>.</span><span class="sxs-lookup"><span data-stu-id="97f6f-106">Expression trees that represent lambda expressions are of type <xref:System.Linq.Expressions.LambdaExpression> or <xref:System.Linq.Expressions.Expression%601>.</span></span> <span data-ttu-id="97f6f-107">Para ejecutar estos árboles de expresiones, llame al método <xref:System.Linq.Expressions.LambdaExpression.Compile%2A> para crear un delegado ejecutable y, después, invoque el delegado.</span><span class="sxs-lookup"><span data-stu-id="97f6f-107">To execute these expression trees, call the <xref:System.Linq.Expressions.LambdaExpression.Compile%2A> method to create an executable delegate, and then invoke the delegate.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="97f6f-108">Si el tipo del delegado es desconocido, es decir, la expresión lambda es de tipo <xref:System.Linq.Expressions.LambdaExpression> y no <xref:System.Linq.Expressions.Expression%601>, debe llamar al método <xref:System.Delegate.DynamicInvoke%2A> en el delegado en lugar de invocarlo directamente.</span><span class="sxs-lookup"><span data-stu-id="97f6f-108">If the type of the delegate is not known, that is, the lambda expression is of type <xref:System.Linq.Expressions.LambdaExpression> and not <xref:System.Linq.Expressions.Expression%601>, you must call the <xref:System.Delegate.DynamicInvoke%2A> method on the delegate instead of invoking it directly.</span></span>  
  
 <span data-ttu-id="97f6f-109">Si un árbol de expresión no representa una expresión lambda, puede crear una nueva expresión lambda que tenga el árbol de expresión original como su cuerpo llamando al método <xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29>.</span><span class="sxs-lookup"><span data-stu-id="97f6f-109">If an expression tree does not represent a lambda expression, you can create a new lambda expression that has the original expression tree as its body, by calling the <xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29> method.</span></span> <span data-ttu-id="97f6f-110">Luego puede ejecutar la expresión lambda tal y como se ha descrito anteriormente en esta sección.</span><span class="sxs-lookup"><span data-stu-id="97f6f-110">Then, you can execute the lambda expression as described earlier in this section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97f6f-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="97f6f-111">Example</span></span>  
 <span data-ttu-id="97f6f-112">En el ejemplo de código siguiente se muestra cómo ejecutar un árbol de expresión que representa la elevación de un número a una potencia mediante la creación de una expresión lambda y su posterior ejecución.</span><span class="sxs-lookup"><span data-stu-id="97f6f-112">The following code example demonstrates how to execute an expression tree that represents raising a number to a power by creating a lambda expression and executing it.</span></span> <span data-ttu-id="97f6f-113">Se muestra el resultado, que representa el número elevado a la potencia.</span><span class="sxs-lookup"><span data-stu-id="97f6f-113">The result, which represents the number raised to the power, is displayed.</span></span>  
  
```csharp  
// The expression tree to execute.  
BinaryExpression be = Expression.Power(Expression.Constant(2D), Expression.Constant(3D));  
  
// Create a lambda expression.  
Expression<Func<double>> le = Expression.Lambda<Func<double>>(be);  
  
// Compile the lambda expression.  
Func<double> compiledExpression = le.Compile();  
  
// Execute the lambda expression.  
double result = compiledExpression();  
  
// Display the result.  
Console.WriteLine(result);  
  
// This code produces the following output:  
// 8  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="97f6f-114">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="97f6f-114">Compiling the Code</span></span>  
  
-   <span data-ttu-id="97f6f-115">Agregue una referencia de proyecto a System.Core.dll si todavía no existe.</span><span class="sxs-lookup"><span data-stu-id="97f6f-115">Add a project reference to System.Core.dll if it is not already referenced.</span></span>  
  
-   <span data-ttu-id="97f6f-116">Incluya el espacio de nombres System.Linq.Expressions.</span><span class="sxs-lookup"><span data-stu-id="97f6f-116">Include the System.Linq.Expressions namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97f6f-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="97f6f-117">See also</span></span>

- [<span data-ttu-id="97f6f-118">Árboles de expresión (C#)</span><span class="sxs-lookup"><span data-stu-id="97f6f-118">Expression Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/expression-trees/index.md)
- [<span data-ttu-id="97f6f-119">Cómo: Modificar árboles de expresión (C#)</span><span class="sxs-lookup"><span data-stu-id="97f6f-119">How to: Modify Expression Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/expression-trees/how-to-modify-expression-trees.md)
