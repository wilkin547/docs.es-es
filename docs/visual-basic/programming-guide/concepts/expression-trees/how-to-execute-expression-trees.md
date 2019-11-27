---
title: 'Cómo: Ejecutar árboles de expresión'
ms.date: 07/20/2015
ms.assetid: 9dfb5ab3-f48f-417e-975f-f8f6f1cdc18d
ms.openlocfilehash: 82801728596449869e5124c3fc92c9c0673f5dd9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74332988"
---
# <a name="how-to-execute-expression-trees-visual-basic"></a><span data-ttu-id="99432-102">Cómo: ejecutar árboles de expresión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99432-102">How to: Execute Expression Trees (Visual Basic)</span></span>
<span data-ttu-id="99432-103">En este tema se muestra cómo ejecutar un árbol de expresión.</span><span class="sxs-lookup"><span data-stu-id="99432-103">This topic shows you how to execute an expression tree.</span></span> <span data-ttu-id="99432-104">La ejecución de un árbol de expresión puede devolver un valor o simplemente realizar una acción, como llamar a un método.</span><span class="sxs-lookup"><span data-stu-id="99432-104">Executing an expression tree may return a value, or it may just perform an action such as calling a method.</span></span>  
  
 <span data-ttu-id="99432-105">Solo se pueden ejecutar los árboles de expresiones que representan expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="99432-105">Only expression trees that represent lambda expressions can be executed.</span></span> <span data-ttu-id="99432-106">Los árboles de expresiones que representan expresiones lambda son de tipo <xref:System.Linq.Expressions.LambdaExpression> o <xref:System.Linq.Expressions.Expression%601>.</span><span class="sxs-lookup"><span data-stu-id="99432-106">Expression trees that represent lambda expressions are of type <xref:System.Linq.Expressions.LambdaExpression> or <xref:System.Linq.Expressions.Expression%601>.</span></span> <span data-ttu-id="99432-107">Para ejecutar estos árboles de expresiones, llame al método <xref:System.Linq.Expressions.LambdaExpression.Compile%2A> para crear un delegado ejecutable y, después, invoque el delegado.</span><span class="sxs-lookup"><span data-stu-id="99432-107">To execute these expression trees, call the <xref:System.Linq.Expressions.LambdaExpression.Compile%2A> method to create an executable delegate, and then invoke the delegate.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="99432-108">Si el tipo del delegado es desconocido, es decir, la expresión lambda es de tipo <xref:System.Linq.Expressions.LambdaExpression> y no <xref:System.Linq.Expressions.Expression%601>, debe llamar al método <xref:System.Delegate.DynamicInvoke%2A> en el delegado en lugar de invocarlo directamente.</span><span class="sxs-lookup"><span data-stu-id="99432-108">If the type of the delegate is not known, that is, the lambda expression is of type <xref:System.Linq.Expressions.LambdaExpression> and not <xref:System.Linq.Expressions.Expression%601>, you must call the <xref:System.Delegate.DynamicInvoke%2A> method on the delegate instead of invoking it directly.</span></span>  
  
 <span data-ttu-id="99432-109">Si un árbol de expresión no representa una expresión lambda, puede crear una nueva expresión lambda que tenga el árbol de expresión original como su cuerpo llamando al método <xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29>.</span><span class="sxs-lookup"><span data-stu-id="99432-109">If an expression tree does not represent a lambda expression, you can create a new lambda expression that has the original expression tree as its body, by calling the <xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29> method.</span></span> <span data-ttu-id="99432-110">Luego puede ejecutar la expresión lambda tal y como se ha descrito anteriormente en esta sección.</span><span class="sxs-lookup"><span data-stu-id="99432-110">Then, you can execute the lambda expression as described earlier in this section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99432-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="99432-111">Example</span></span>  
 <span data-ttu-id="99432-112">En el ejemplo de código siguiente se muestra cómo ejecutar un árbol de expresión que representa la elevación de un número a una potencia mediante la creación de una expresión lambda y su posterior ejecución.</span><span class="sxs-lookup"><span data-stu-id="99432-112">The following code example demonstrates how to execute an expression tree that represents raising a number to a power by creating a lambda expression and executing it.</span></span> <span data-ttu-id="99432-113">Se muestra el resultado, que representa el número elevado a la potencia.</span><span class="sxs-lookup"><span data-stu-id="99432-113">The result, which represents the number raised to the power, is displayed.</span></span>  
  
```vb  
' The expression tree to execute.  
Dim be As BinaryExpression = Expression.Power(Expression.Constant(2.0R), Expression.Constant(3.0R))  
  
' Create a lambda expression.  
Dim le As Expression(Of Func(Of Double)) = Expression.Lambda(Of Func(Of Double))(be)  
  
' Compile the lambda expression.  
Dim compiledExpression As Func(Of Double) = le.Compile()  
  
' Execute the lambda expression.  
Dim result As Double = compiledExpression()  
  
' Display the result.  
MsgBox(result)  
  
' This code produces the following output:  
' 8  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="99432-114">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="99432-114">Compiling the Code</span></span>  
  
- <span data-ttu-id="99432-115">Incluya el espacio de nombres System.Linq.Expressions.</span><span class="sxs-lookup"><span data-stu-id="99432-115">Include the System.Linq.Expressions namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99432-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="99432-116">See also</span></span>

- [<span data-ttu-id="99432-117">Árboles de expresión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99432-117">Expression Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
- [<span data-ttu-id="99432-118">Cómo: modificar árboles de expresiones (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99432-118">How to: Modify Expression Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-modify-expression-trees.md)
