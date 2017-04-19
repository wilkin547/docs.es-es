---
title: "Cómo: Modificar árboles de expresión (Visual Basic) | Documentos de Microsoft"
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
ms.assetid: d1309fff-28bd-4d8e-a2cf-75725999e8f2
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
ms.openlocfilehash: fb4e818eed7d6547e091c914d40b3ce87af59512
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-modify-expression-trees-visual-basic"></a>Cómo: Modificar árboles de expresión (Visual Basic)
En este tema se muestra cómo modificar un árbol de expresión. Árboles de expresiones son inmutables, lo que significa no pueden modificarse directamente. Para cambiar un árbol de expresión, debe crear una copia de un árbol de expresión existente y cuando se crea la copia, realice los cambios necesarios. Puede usar el <xref:System.Linq.Expressions.ExpressionVisitor>clase para recorrer un árbol de expresión existente y copiar cada nodo que visita.</xref:System.Linq.Expressions.ExpressionVisitor>  
  
### <a name="to-modify-an-expression-tree"></a>Para modificar un árbol de expresión  
  
1.  Crear un nuevo **aplicación de consola** proyecto.  
  
2.  Agregar una `Imports` instrucción al archivo para el `System.Linq.Expressions` espacio de nombres.  
  
3.  Agregar la `AndAlsoModifier` clase al proyecto.  
  
    ```vb  
    Public Class AndAlsoModifier  
        Inherits ExpressionVisitor  
  
        Public Function Modify(ByVal expr As Expression) As Expression  
            Return Visit(expr)  
        End Function  
  
        Protected Overrides Function VisitBinary(ByVal b As BinaryExpression) As Expression  
            If b.NodeType = ExpressionType.AndAlso Then  
                Dim left = Me.Visit(b.Left)  
                Dim right = Me.Visit(b.Right)  
  
                ' Make this binary expression an OrElse operation instead   
                ' of an AndAlso operation.  
                Return Expression.MakeBinary(ExpressionType.OrElse, left, right, _  
                                             b.IsLiftedToNull, b.Method)  
            End If  
  
            Return MyBase.VisitBinary(b)  
        End Function  
    End Class  
    ```  
  
     Esta clase hereda la <xref:System.Linq.Expressions.ExpressionVisitor>clase y está especializado para modificar las expresiones que representan condicionales `AND` operations.</xref:System.Linq.Expressions.ExpressionVisitor> Cambia estas operaciones de una instrucción condicional `AND` en una instrucción condicional `OR`. Para ello, las invalidaciones de clase del <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A>método del tipo base, porque condicional `AND` expresiones se representan como expresiones binarias.</xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> En el `VisitBinary` método, si la expresión que se pasa representa una instrucción condicional `AND` operación, el código construye una nueva expresión que contiene el operador condicional `OR` operador en lugar del operador condicional `AND` operador. Si la expresión que se pasa a `VisitBinary` no representa una instrucción condicional `AND` operación, el método pasa a la implementación de la clase base. Los métodos de clase base nodos de construcción que son como los árboles de expresión que se pasan, pero los nodos tienen sus árboles sub reemplazados por los árboles de expresión que genera de forma recursiva por el visitante.  
  
4.  Agregar una `Imports` instrucción al archivo para el `System.Linq.Expressions` espacio de nombres.  
  
5.  Agregue código a la `Main` método en el archivo Module1.vb para crear un árbol de expresión y pasarlo al método que lo modificará.  
  
    ```vb  
    Dim expr As Expression(Of Func(Of String, Boolean)) = _  
        Function(name) name.Length > 10 AndAlso name.StartsWith("G")  
  
    Console.WriteLine(expr)  
  
    Dim modifier As New AndAlsoModifier()  
    Dim modifiedExpr = modifier.Modify(CType(expr, Expression))  
  
    Console.WriteLine(modifiedExpr)  
  
    ' This code produces the following output:  
    ' name => ((name.Length > 10) && name.StartsWith("G"))  
    ' name => ((name.Length > 10) || name.StartsWith("G"))  
    ```  
  
     El código crea una expresión que contiene una instrucción condicional `AND` operación. A continuación se crea una instancia de la `AndAlsoModifier` clase y pasa la expresión a la `Modify` método de esta clase. Tanto el original como el árbol de expresión modificado se genera para mostrar el cambio.  
  
6.  Compile y ejecute la aplicación.  
  
## <a name="see-also"></a>Vea también  
 [Cómo: Ejecutar árboles de expresión (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)   
 [Árboles de expresión (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
