---
title: "Cómo: Modificar árboles de expresiones (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 9b0cd8c2-457e-4833-9e36-31e79545f442
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b665f3bfa1228e2e8834241f010792e9d5975c96
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-modify-expression-trees-c"></a><span data-ttu-id="5e826-102">Cómo: Modificar árboles de expresiones (C#)</span><span class="sxs-lookup"><span data-stu-id="5e826-102">How to: Modify Expression Trees (C#)</span></span>
<span data-ttu-id="5e826-103">En este tema se muestra cómo modificar un árbol de expresión.</span><span class="sxs-lookup"><span data-stu-id="5e826-103">This topic shows you how to modify an expression tree.</span></span> <span data-ttu-id="5e826-104">Los árboles de expresiones son inmutables, lo que significa que no pueden modificarse directamente.</span><span class="sxs-lookup"><span data-stu-id="5e826-104">Expression trees are immutable, which means that they cannot be modified directly.</span></span> <span data-ttu-id="5e826-105">Para cambiar un árbol de expresión, debe crear una copia de un árbol de expresión existente y, una vez creada la copia, realizar los cambios necesarios.</span><span class="sxs-lookup"><span data-stu-id="5e826-105">To change an expression tree, you must create a copy of an existing expression tree and when you create the copy, make the required changes.</span></span> <span data-ttu-id="5e826-106">Puede usar la clase <xref:System.Linq.Expressions.ExpressionVisitor> para recorrer un árbol de expresión existente y copiar cada nodo que visita.</span><span class="sxs-lookup"><span data-stu-id="5e826-106">You can use the <xref:System.Linq.Expressions.ExpressionVisitor> class to traverse an existing expression tree and to copy each node that it visits.</span></span>  
  
### <a name="to-modify-an-expression-tree"></a><span data-ttu-id="5e826-107">Para modificar un árbol de expresión</span><span class="sxs-lookup"><span data-stu-id="5e826-107">To modify an expression tree</span></span>  
  
1.  <span data-ttu-id="5e826-108">Cree un nuevo proyecto de **aplicación de consola**.</span><span class="sxs-lookup"><span data-stu-id="5e826-108">Create a new **Console Application** project.</span></span>  
  
2.  <span data-ttu-id="5e826-109">Agregue una directiva `using` al archivo para el espacio de nombres `System.Linq.Expressions`.</span><span class="sxs-lookup"><span data-stu-id="5e826-109">Add a `using` directive to the file for the `System.Linq.Expressions` namespace.</span></span>  
  
3.  <span data-ttu-id="5e826-110">Agregue la clase `AndAlsoModifier` al proyecto.</span><span class="sxs-lookup"><span data-stu-id="5e826-110">Add the `AndAlsoModifier` class to your project.</span></span>  
  
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
  
     <span data-ttu-id="5e826-111">Esta clase hereda la clase <xref:System.Linq.Expressions.ExpressionVisitor> y está especializada en la modificación de expresiones que representan operaciones `AND` condicionales.</span><span class="sxs-lookup"><span data-stu-id="5e826-111">This class inherits the <xref:System.Linq.Expressions.ExpressionVisitor> class and is specialized to modify expressions that represent conditional `AND` operations.</span></span> <span data-ttu-id="5e826-112">Cambia estas operaciones de una expresión `AND` condicional a una expresión `OR` condicional.</span><span class="sxs-lookup"><span data-stu-id="5e826-112">It changes these operations from a conditional `AND` to a conditional `OR`.</span></span> <span data-ttu-id="5e826-113">Para ello, la clase invalida el método <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> del tipo base, porque las expresiones `AND` condicionales se representan como expresiones binarias.</span><span class="sxs-lookup"><span data-stu-id="5e826-113">To do this, the class overrides the <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> method of the base type, because conditional `AND` expressions are represented as binary expressions.</span></span> <span data-ttu-id="5e826-114">En el método `VisitBinary`, si la expresión que se pasa representa una operación `AND` condicional, el código construye una nueva expresión que contiene el operador `OR` condicional en lugar del operador `AND` condicional.</span><span class="sxs-lookup"><span data-stu-id="5e826-114">In the `VisitBinary` method, if the expression that is passed to it represents a conditional `AND` operation, the code constructs a new expression that contains the conditional `OR` operator instead of the conditional `AND` operator.</span></span> <span data-ttu-id="5e826-115">Si la expresión que se pasa a `VisitBinary` no representa una operación `AND` condicional, el método defiere a la implementación de la case base.</span><span class="sxs-lookup"><span data-stu-id="5e826-115">If the expression that is passed to `VisitBinary` does not represent a conditional `AND` operation, the method defers to the base class implementation.</span></span> <span data-ttu-id="5e826-116">Los métodos de clase base construyen nodos que son como los árboles de expresiones que se pasan, pero los subárboles de los nodos se reemplazan por los árboles de expresiones que genera de forma recursiva el visitante.</span><span class="sxs-lookup"><span data-stu-id="5e826-116">The base class methods construct nodes that are like the expression trees that are passed in, but the nodes have their sub trees replaced with the expression trees that are produced recursively by the visitor.</span></span>  
  
4.  <span data-ttu-id="5e826-117">Agregue una directiva `using` al archivo para el espacio de nombres `System.Linq.Expressions`.</span><span class="sxs-lookup"><span data-stu-id="5e826-117">Add a `using` directive to the file for the `System.Linq.Expressions` namespace.</span></span>  
  
5.  <span data-ttu-id="5e826-118">Agregue código al método `Main` en el archivo Program.cs para crear un árbol de expresión y pasarlo al método que lo modificará.</span><span class="sxs-lookup"><span data-stu-id="5e826-118">Add code to the `Main` method in the Program.cs file to create an expression tree and pass it to the method that will modify it.</span></span>  
  
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
  
     <span data-ttu-id="5e826-119">El código crea una expresión que contiene una operación `AND` condicional.</span><span class="sxs-lookup"><span data-stu-id="5e826-119">The code creates an expression that contains a conditional `AND` operation.</span></span> <span data-ttu-id="5e826-120">Luego crea una instancia de la clase `AndAlsoModifier` y pasa la expresión al método `Modify` de esta clase.</span><span class="sxs-lookup"><span data-stu-id="5e826-120">It then creates an instance of the `AndAlsoModifier` class and passes the expression to the `Modify` method of this class.</span></span> <span data-ttu-id="5e826-121">Se generan los árboles de expresiones tanto originales como modificados para mostrar el cambio.</span><span class="sxs-lookup"><span data-stu-id="5e826-121">Both the original and the modified expression trees are outputted to show the change.</span></span>  
  
6.  <span data-ttu-id="5e826-122">Compile y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5e826-122">Compile and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e826-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e826-123">See Also</span></span>  
 <span data-ttu-id="5e826-124">[Cómo: Ejecutar árboles de expresiones (C#)](../../../../csharp/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md) </span><span class="sxs-lookup"><span data-stu-id="5e826-124">[How to: Execute Expression Trees (C#)](../../../../csharp/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md) </span></span>  
 [<span data-ttu-id="5e826-125">Árboles de expresión (C#)</span><span class="sxs-lookup"><span data-stu-id="5e826-125">Expression Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/expression-trees/index.md)

