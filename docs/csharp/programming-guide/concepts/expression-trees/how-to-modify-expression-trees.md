---
title: Procedimiento para modificar árboles de expresión (C#)
description: Aprenda a modificar un árbol de expresión mediante la creación de una copia de un árbol de expresión existente y la realización de los cambios necesarios.
ms.date: 07/20/2015
ms.assetid: 9b0cd8c2-457e-4833-9e36-31e79545f442
ms.openlocfilehash: 45aea18e253811d4e5c60f23f7f8496d4358f64c
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105605"
---
# <a name="how-to-modify-expression-trees-c"></a><span data-ttu-id="03e8b-103">Procedimiento para modificar árboles de expresión (C#)</span><span class="sxs-lookup"><span data-stu-id="03e8b-103">How to modify expression trees (C#)</span></span>
<span data-ttu-id="03e8b-104">En este tema se muestra cómo modificar un árbol de expresión.</span><span class="sxs-lookup"><span data-stu-id="03e8b-104">This topic shows you how to modify an expression tree.</span></span> <span data-ttu-id="03e8b-105">Los árboles de expresiones son inmutables, lo que significa que no pueden modificarse directamente.</span><span class="sxs-lookup"><span data-stu-id="03e8b-105">Expression trees are immutable, which means that they cannot be modified directly.</span></span> <span data-ttu-id="03e8b-106">Para cambiar un árbol de expresión, debe crear una copia de un árbol de expresión existente y, una vez creada la copia, realizar los cambios necesarios.</span><span class="sxs-lookup"><span data-stu-id="03e8b-106">To change an expression tree, you must create a copy of an existing expression tree and when you create the copy, make the required changes.</span></span> <span data-ttu-id="03e8b-107">Puede usar la clase <xref:System.Linq.Expressions.ExpressionVisitor> para recorrer un árbol de expresión existente y copiar cada nodo que visita.</span><span class="sxs-lookup"><span data-stu-id="03e8b-107">You can use the <xref:System.Linq.Expressions.ExpressionVisitor> class to traverse an existing expression tree and to copy each node that it visits.</span></span>  
  
### <a name="to-modify-an-expression-tree"></a><span data-ttu-id="03e8b-108">Para modificar un árbol de expresión</span><span class="sxs-lookup"><span data-stu-id="03e8b-108">To modify an expression tree</span></span>  
  
1. <span data-ttu-id="03e8b-109">Cree un nuevo proyecto de **aplicación de consola**.</span><span class="sxs-lookup"><span data-stu-id="03e8b-109">Create a new **Console Application** project.</span></span>  
  
2. <span data-ttu-id="03e8b-110">Agregue una directiva `using` al archivo para el espacio de nombres `System.Linq.Expressions`.</span><span class="sxs-lookup"><span data-stu-id="03e8b-110">Add a `using` directive to the file for the `System.Linq.Expressions` namespace.</span></span>  
  
3. <span data-ttu-id="03e8b-111">Agregue la clase `AndAlsoModifier` al proyecto.</span><span class="sxs-lookup"><span data-stu-id="03e8b-111">Add the `AndAlsoModifier` class to your project.</span></span>  
  
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
  
     <span data-ttu-id="03e8b-112">Esta clase hereda la clase <xref:System.Linq.Expressions.ExpressionVisitor> y está especializada en la modificación de expresiones que representan operaciones `AND` condicionales.</span><span class="sxs-lookup"><span data-stu-id="03e8b-112">This class inherits the <xref:System.Linq.Expressions.ExpressionVisitor> class and is specialized to modify expressions that represent conditional `AND` operations.</span></span> <span data-ttu-id="03e8b-113">Cambia estas operaciones de una expresión `AND` condicional a una expresión `OR` condicional.</span><span class="sxs-lookup"><span data-stu-id="03e8b-113">It changes these operations from a conditional `AND` to a conditional `OR`.</span></span> <span data-ttu-id="03e8b-114">Para ello, la clase invalida el método <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> del tipo base, porque las expresiones `AND` condicionales se representan como expresiones binarias.</span><span class="sxs-lookup"><span data-stu-id="03e8b-114">To do this, the class overrides the <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> method of the base type, because conditional `AND` expressions are represented as binary expressions.</span></span> <span data-ttu-id="03e8b-115">En el método `VisitBinary`, si la expresión que se pasa representa una operación `AND` condicional, el código construye una nueva expresión que contiene el operador `OR` condicional en lugar del operador `AND` condicional.</span><span class="sxs-lookup"><span data-stu-id="03e8b-115">In the `VisitBinary` method, if the expression that is passed to it represents a conditional `AND` operation, the code constructs a new expression that contains the conditional `OR` operator instead of the conditional `AND` operator.</span></span> <span data-ttu-id="03e8b-116">Si la expresión que se pasa a `VisitBinary` no representa una operación `AND` condicional, el método defiere a la implementación de la case base.</span><span class="sxs-lookup"><span data-stu-id="03e8b-116">If the expression that is passed to `VisitBinary` does not represent a conditional `AND` operation, the method defers to the base class implementation.</span></span> <span data-ttu-id="03e8b-117">Los métodos de clase base construyen nodos que son como los árboles de expresiones que se pasan, pero los subárboles de los nodos se reemplazan por los árboles de expresiones que genera de forma recursiva el visitante.</span><span class="sxs-lookup"><span data-stu-id="03e8b-117">The base class methods construct nodes that are like the expression trees that are passed in, but the nodes have their sub trees replaced with the expression trees that are produced recursively by the visitor.</span></span>  
  
4. <span data-ttu-id="03e8b-118">Agregue una directiva `using` al archivo para el espacio de nombres `System.Linq.Expressions`.</span><span class="sxs-lookup"><span data-stu-id="03e8b-118">Add a `using` directive to the file for the `System.Linq.Expressions` namespace.</span></span>  
  
5. <span data-ttu-id="03e8b-119">Agregue código al método `Main` en el archivo Program.cs para crear un árbol de expresión y pasarlo al método que lo modificará.</span><span class="sxs-lookup"><span data-stu-id="03e8b-119">Add code to the `Main` method in the Program.cs file to create an expression tree and pass it to the method that will modify it.</span></span>  
  
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
  
     <span data-ttu-id="03e8b-120">El código crea una expresión que contiene una operación `AND` condicional.</span><span class="sxs-lookup"><span data-stu-id="03e8b-120">The code creates an expression that contains a conditional `AND` operation.</span></span> <span data-ttu-id="03e8b-121">Luego crea una instancia de la clase `AndAlsoModifier` y pasa la expresión al método `Modify` de esta clase.</span><span class="sxs-lookup"><span data-stu-id="03e8b-121">It then creates an instance of the `AndAlsoModifier` class and passes the expression to the `Modify` method of this class.</span></span> <span data-ttu-id="03e8b-122">Se generan los árboles de expresiones tanto originales como modificados para mostrar el cambio.</span><span class="sxs-lookup"><span data-stu-id="03e8b-122">Both the original and the modified expression trees are outputted to show the change.</span></span>  
  
6. <span data-ttu-id="03e8b-123">Compile y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="03e8b-123">Compile and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03e8b-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="03e8b-124">See also</span></span>

- [<span data-ttu-id="03e8b-125">Procedimiento para ejecutar árboles de expresión (C#)</span><span class="sxs-lookup"><span data-stu-id="03e8b-125">How to execute expression trees (C#)</span></span>](./how-to-execute-expression-trees.md)
- [<span data-ttu-id="03e8b-126">Árboles de expresión (C#)</span><span class="sxs-lookup"><span data-stu-id="03e8b-126">Expression Trees (C#)</span></span>](./index.md)
