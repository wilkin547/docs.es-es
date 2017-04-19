---
title: "Cómo: Ejecutar árboles de expresión (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 9dfb5ab3-f48f-417e-975f-f8f6f1cdc18d
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e12c45b417310f097d597561b2652ee793a4b2c0
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-execute-expression-trees-visual-basic"></a>Cómo: Ejecutar árboles de expresión (Visual Basic)
En este tema se muestra cómo ejecutar un árbol de expresión. Ejecutar un árbol de expresión puede devolver un valor o simplemente puede realizarse una acción, como llamar a un método.  
  
 Se pueden ejecutar los árboles de expresiones que representan expresiones lambda. Árboles de expresiones que representan expresiones lambda son de tipo <xref:System.Linq.Expressions.LambdaExpression>o <xref:System.Linq.Expressions.Expression%601>.</xref:System.Linq.Expressions.Expression%601> </xref:System.Linq.Expressions.LambdaExpression> Para ejecutar estos árboles de expresiones, llame a la <xref:System.Linq.Expressions.LambdaExpression.Compile%2A>método para crear un delegado ejecutable y, a continuación, invoque el delegado.</xref:System.Linq.Expressions.LambdaExpression.Compile%2A>  
  
> [!NOTE]
>  Si no se conoce el tipo del delegado, es decir, la expresión lambda es de tipo <xref:System.Linq.Expressions.LambdaExpression>y no <xref:System.Linq.Expressions.Expression%601>, se debe llamar a la <xref:System.Delegate.DynamicInvoke%2A>método del delegado en lugar de invocarlo directamente.</xref:System.Delegate.DynamicInvoke%2A> </xref:System.Linq.Expressions.Expression%601> </xref:System.Linq.Expressions.LambdaExpression>  
  
 Si un árbol de expresión representa una expresión lambda, puede crear una nueva expresión lambda que tiene el árbol de expresión original como su cuerpo llamando el <xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29>método.</xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29> A continuación, puede ejecutar la expresión lambda como se describió anteriormente en esta sección.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se muestra cómo ejecutar un árbol de expresión que representa la elevación de un número a una potencia mediante la creación de una expresión lambda y ejecutarlo. Se muestra el resultado, que representa el número elevado a la potencia.  
  
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
  
-   Agregue una referencia a System.Core.dll del proyecto si no se hace referencia.  
  
-   Incluir el espacio de nombres System.Linq.Expressions.  
  
## <a name="see-also"></a>Vea también  
 [Árboles de expresión (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)   
 [Cómo: Modificar árboles de expresión (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-modify-expression-trees.md)
