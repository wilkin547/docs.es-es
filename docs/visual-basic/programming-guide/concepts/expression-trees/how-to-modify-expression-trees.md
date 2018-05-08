---
title: 'Cómo: Modificar árboles de expresión (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: d1309fff-28bd-4d8e-a2cf-75725999e8f2
ms.openlocfilehash: 92a0fb37e2a383c68beb2e4a56deb16f89a9bd28
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-modify-expression-trees-visual-basic"></a>Cómo: Modificar árboles de expresión (Visual Basic)
En este tema se muestra cómo modificar un árbol de expresión. Los árboles de expresiones son inmutables, lo que significa que no pueden modificarse directamente. Para cambiar un árbol de expresión, debe crear una copia de un árbol de expresión existente y, una vez creada la copia, realizar los cambios necesarios. Puede usar la clase <xref:System.Linq.Expressions.ExpressionVisitor> para recorrer un árbol de expresión existente y copiar cada nodo que visita.  
  
### <a name="to-modify-an-expression-tree"></a>Para modificar un árbol de expresión  
  
1.  Cree un nuevo proyecto de **Aplicación de consola**.  
  
2.  Agregar un `Imports` instrucción en el archivo para el `System.Linq.Expressions` espacio de nombres.  
  
3.  Agregue la clase `AndAlsoModifier` al proyecto.  
  
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
  
     Esta clase hereda la clase <xref:System.Linq.Expressions.ExpressionVisitor> y está especializada en la modificación de expresiones que representan operaciones `AND` condicionales. Cambia estas operaciones de una expresión `AND` condicional a una expresión `OR` condicional. Para ello, la clase invalida el método <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> del tipo base, porque las expresiones `AND` condicionales se representan como expresiones binarias. En el método `VisitBinary`, si la expresión que se pasa representa una operación `AND` condicional, el código construye una nueva expresión que contiene el operador `OR` condicional en lugar del operador `AND` condicional. Si la expresión que se pasa a `VisitBinary` no representa una operación `AND` condicional, el método defiere a la implementación de la case base. Los métodos de clase base construyen nodos que son como los árboles de expresiones que se pasan, pero los subárboles de los nodos se reemplazan por los árboles de expresiones que genera de forma recursiva el visitante.  
  
4.  Agregar un `Imports` instrucción en el archivo para el `System.Linq.Expressions` espacio de nombres.  
  
5.  Agregue código a la `Main` método en el archivo Module1.vb para crear un árbol de expresión y pasarlo al método que la modifique.  
  
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
  
     El código crea una expresión que contiene una operación `AND` condicional. Luego crea una instancia de la clase `AndAlsoModifier` y pasa la expresión al método `Modify` de esta clase. Se generan los árboles de expresiones tanto originales como modificados para mostrar el cambio.  
  
6.  Compile y ejecute la aplicación.  
  
## <a name="see-also"></a>Vea también  
 [Cómo: Ejecutar árboles de expresión (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)  
 [Árboles de expresión (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
