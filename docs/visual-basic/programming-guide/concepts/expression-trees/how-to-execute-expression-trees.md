---
description: 'Más información acerca de cómo: ejecutar árboles de expresión (Visual Basic)'
title: Procedimiento para ejecutar árboles de expresión
ms.date: 07/20/2015
ms.assetid: 9dfb5ab3-f48f-417e-975f-f8f6f1cdc18d
ms.openlocfilehash: debd850f35d8239c20d9b848a43dafd76ac19bbc
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100430708"
---
# <a name="how-to-execute-expression-trees-visual-basic"></a>How to: Execute Expression Trees (Visual Basic) (Cómo ejecutar árboles de expresión en Visual Basic)

En este tema se muestra cómo ejecutar un árbol de expresión. La ejecución de un árbol de expresión puede devolver un valor o simplemente realizar una acción, como llamar a un método.  
  
 Solo se pueden ejecutar los árboles de expresiones que representan expresiones lambda. Los árboles de expresiones que representan expresiones lambda son de tipo <xref:System.Linq.Expressions.LambdaExpression> o <xref:System.Linq.Expressions.Expression%601>. Para ejecutar estos árboles de expresiones, llame al método <xref:System.Linq.Expressions.LambdaExpression.Compile%2A> para crear un delegado ejecutable y, después, invoque el delegado.  
  
> [!NOTE]
> Si el tipo del delegado es desconocido, es decir, la expresión lambda es de tipo <xref:System.Linq.Expressions.LambdaExpression> y no <xref:System.Linq.Expressions.Expression%601>, debe llamar al método <xref:System.Delegate.DynamicInvoke%2A> en el delegado en lugar de invocarlo directamente.  
  
 Si un árbol de expresión no representa una expresión lambda, puede crear una nueva expresión lambda que tenga el árbol de expresión original como su cuerpo llamando al método <xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29>. Luego puede ejecutar la expresión lambda tal y como se ha descrito anteriormente en esta sección.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo de código siguiente se muestra cómo ejecutar un árbol de expresión que representa la elevación de un número a una potencia mediante la creación de una expresión lambda y su posterior ejecución. Se muestra el resultado, que representa el número elevado a la potencia.  
  
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
  
## <a name="compile-the-code"></a>Compilar el código  
  
- Incluya el espacio de nombres System.Linq.Expressions.  
  
## <a name="see-also"></a>Vea también

- [Árboles de expresión (Visual Basic)](index.md)
- [How to: Modify Expression Trees (Visual Basic)](how-to-modify-expression-trees.md) (Cómo modificar árboles de expresión en Visual Basic)
