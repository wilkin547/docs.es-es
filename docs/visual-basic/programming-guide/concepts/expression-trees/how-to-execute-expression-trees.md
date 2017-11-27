---
title: "Cómo: Ejecutar árboles de expresión (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9dfb5ab3-f48f-417e-975f-f8f6f1cdc18d
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 45a13f13659472b7620b6df070815ace1d6fb0de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-execute-expression-trees-visual-basic"></a>Cómo: Ejecutar árboles de expresión (Visual Basic)
En este tema se muestra cómo ejecutar un árbol de expresión. La ejecución de un árbol de expresión puede devolver un valor o simplemente realizar una acción, como llamar a un método.  
  
 Solo se pueden ejecutar los árboles de expresiones que representan expresiones lambda. Los árboles de expresiones que representan expresiones lambda son de tipo <xref:System.Linq.Expressions.LambdaExpression> o <xref:System.Linq.Expressions.Expression%601>. Para ejecutar estos árboles de expresiones, llame al método <xref:System.Linq.Expressions.LambdaExpression.Compile%2A> para crear un delegado ejecutable y, después, invoque el delegado.  
  
> [!NOTE]
>  Si el tipo del delegado es desconocido, es decir, la expresión lambda es de tipo <xref:System.Linq.Expressions.LambdaExpression> y no <xref:System.Linq.Expressions.Expression%601>, debe llamar al método <xref:System.Delegate.DynamicInvoke%2A> en el delegado en lugar de invocarlo directamente.  
  
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
  
## <a name="compiling-the-code"></a>Compilar el código  
  
-   Agregue una referencia de proyecto a System.Core.dll si todavía no existe.  
  
-   Incluya el espacio de nombres System.Linq.Expressions.  
  
## <a name="see-also"></a>Vea también  
 [Árboles de expresión (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)  
 [Cómo: Modificar árboles de expresión (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-modify-expression-trees.md)
