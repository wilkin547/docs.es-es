---
description: 'Más información acerca de cómo: modificar árboles de expresión (Visual Basic)'
title: Procedimiento para modificar árboles de expresión
ms.date: 07/20/2015
ms.assetid: d1309fff-28bd-4d8e-a2cf-75725999e8f2
ms.openlocfilehash: 13098f5588fe44be8e57c9be52a9cfe5f7cd661f
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100455904"
---
# <a name="how-to-modify-expression-trees-visual-basic"></a>How to: Modify Expression Trees (Visual Basic) (Cómo modificar árboles de expresión en Visual Basic)

En este tema se muestra cómo modificar un árbol de expresión. Los árboles de expresiones son inmutables, lo que significa que no pueden modificarse directamente. Para cambiar un árbol de expresión, debe crear una copia de un árbol de expresión existente y, una vez creada la copia, realizar los cambios necesarios. Puede usar la clase <xref:System.Linq.Expressions.ExpressionVisitor> para recorrer un árbol de expresión existente y copiar cada nodo que visita.

## <a name="to-modify-an-expression-tree"></a>Para modificar un árbol de expresión

1. Cree un nuevo proyecto de **aplicación de consola**.

2. Agregue una `Imports` instrucción al archivo para el `System.Linq.Expressions` espacio de nombres.

3. Agregue la clase `AndAlsoModifier` al proyecto.

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

4. Agregue una `Imports` instrucción al archivo para el `System.Linq.Expressions` espacio de nombres.

5. Agregue código al `Main` método en el archivo Module1. VB para crear un árbol de expresión y pasarlo al método que lo modificará.

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

6. Compile y ejecute la aplicación.

## <a name="see-also"></a>Vea también

- [How to: Execute Expression Trees (Visual Basic)](how-to-execute-expression-trees.md) (Cómo ejecutar árboles de expresión en Visual Basic)
- [Árboles de expresión (Visual Basic)](index.md)
