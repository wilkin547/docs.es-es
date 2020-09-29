---
title: Procedimiento para modificar árboles de expresión (C#)
description: Aprenda a modificar un árbol de expresión mediante la creación de una copia de un árbol de expresión existente y la realización de los cambios necesarios.
ms.date: 07/20/2015
ms.assetid: 9b0cd8c2-457e-4833-9e36-31e79545f442
ms.openlocfilehash: 01176f489794a0f4ca29d229d29507fdba0fd5a8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167696"
---
# <a name="how-to-modify-expression-trees-c"></a>Procedimiento para modificar árboles de expresión (C#)

En este tema se muestra cómo modificar un árbol de expresión. Los árboles de expresiones son inmutables, lo que significa que no pueden modificarse directamente. Para cambiar un árbol de expresión, debe crear una copia de un árbol de expresión existente y, una vez creada la copia, realizar los cambios necesarios. Puede usar la clase <xref:System.Linq.Expressions.ExpressionVisitor> para recorrer un árbol de expresión existente y copiar cada nodo que visita.  
  
### <a name="to-modify-an-expression-tree"></a>Para modificar un árbol de expresión  
  
1. Cree un nuevo proyecto de **aplicación de consola**.  
  
2. Agregue una directiva `using` al archivo para el espacio de nombres `System.Linq.Expressions`.  
  
3. Agregue la clase `AndAlsoModifier` al proyecto.  
  
    ```csharp  
    public class AndAlsoModifier : ExpressionVisitor  
    {  
        public Expression Modify(Expression expression)  
        {  
            return Visit(expression);  
        }  
  
        protected override Expression VisitBinary(BinaryExpression b)  
        {  
            if (b.NodeType == ExpressionType.AndAlso)  
            {  
                Expression left = this.Visit(b.Left);  
                Expression right = this.Visit(b.Right);  
  
                // Make this binary expression an OrElse operation instead of an AndAlso operation.  
                return Expression.MakeBinary(ExpressionType.OrElse, left, right, b.IsLiftedToNull, b.Method);  
            }  
  
            return base.VisitBinary(b);  
        }  
    }  
    ```  
  
     Esta clase hereda la clase <xref:System.Linq.Expressions.ExpressionVisitor> y está especializada en la modificación de expresiones que representan operaciones `AND` condicionales. Cambia estas operaciones de una expresión `AND` condicional a una expresión `OR` condicional. Para ello, la clase invalida el método <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> del tipo base, porque las expresiones `AND` condicionales se representan como expresiones binarias. En el método `VisitBinary`, si la expresión que se pasa representa una operación `AND` condicional, el código construye una nueva expresión que contiene el operador `OR` condicional en lugar del operador `AND` condicional. Si la expresión que se pasa a `VisitBinary` no representa una operación `AND` condicional, el método defiere a la implementación de la case base. Los métodos de clase base construyen nodos que son como los árboles de expresiones que se pasan, pero los subárboles de los nodos se reemplazan por los árboles de expresiones que genera de forma recursiva el visitante.  
  
4. Agregue una directiva `using` al archivo para el espacio de nombres `System.Linq.Expressions`.  
  
5. Agregue código al método `Main` en el archivo Program.cs para crear un árbol de expresión y pasarlo al método que lo modificará.  
  
    ```csharp  
    Expression<Func<string, bool>> expr = name => name.Length > 10 && name.StartsWith("G");  
    Console.WriteLine(expr);  
  
    AndAlsoModifier treeModifier = new AndAlsoModifier();  
    Expression modifiedExpr = treeModifier.Modify((Expression) expr);  
  
    Console.WriteLine(modifiedExpr);  
  
    /*  This code produces the following output:  
  
        name => ((name.Length > 10) && name.StartsWith("G"))  
        name => ((name.Length > 10) || name.StartsWith("G"))  
    */  
    ```  
  
     El código crea una expresión que contiene una operación `AND` condicional. Luego crea una instancia de la clase `AndAlsoModifier` y pasa la expresión al método `Modify` de esta clase. Se generan los árboles de expresiones tanto originales como modificados para mostrar el cambio.  
  
6. Compile y ejecute la aplicación.  
  
## <a name="see-also"></a>Vea también

- [Procedimiento para ejecutar árboles de expresión (C#)](./how-to-execute-expression-trees.md)
- [Árboles de expresión (C#)](./index.md)
