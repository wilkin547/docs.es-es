---
title: "Cómo: Modificar árboles de expresión (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d1309fff-28bd-4d8e-a2cf-75725999e8f2
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 28a79a2dc8817a3fc6c7f3e2e01c1270d2981334
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-modify-expression-trees-visual-basic"></a><span data-ttu-id="ac195-102">Cómo: Modificar árboles de expresión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ac195-102">How to: Modify Expression Trees (Visual Basic)</span></span>
<span data-ttu-id="ac195-103">En este tema se muestra cómo modificar un árbol de expresión.</span><span class="sxs-lookup"><span data-stu-id="ac195-103">This topic shows you how to modify an expression tree.</span></span> <span data-ttu-id="ac195-104">Los árboles de expresiones son inmutables, lo que significa que no pueden modificarse directamente.</span><span class="sxs-lookup"><span data-stu-id="ac195-104">Expression trees are immutable, which means that they cannot be modified directly.</span></span> <span data-ttu-id="ac195-105">Para cambiar un árbol de expresión, debe crear una copia de un árbol de expresión existente y, una vez creada la copia, realizar los cambios necesarios.</span><span class="sxs-lookup"><span data-stu-id="ac195-105">To change an expression tree, you must create a copy of an existing expression tree and when you create the copy, make the required changes.</span></span> <span data-ttu-id="ac195-106">Puede usar la clase <xref:System.Linq.Expressions.ExpressionVisitor> para recorrer un árbol de expresión existente y copiar cada nodo que visita.</span><span class="sxs-lookup"><span data-stu-id="ac195-106">You can use the <xref:System.Linq.Expressions.ExpressionVisitor> class to traverse an existing expression tree and to copy each node that it visits.</span></span>  
  
### <a name="to-modify-an-expression-tree"></a><span data-ttu-id="ac195-107">Para modificar un árbol de expresión</span><span class="sxs-lookup"><span data-stu-id="ac195-107">To modify an expression tree</span></span>  
  
1.  <span data-ttu-id="ac195-108">Cree un nuevo proyecto de **Aplicación de consola**.</span><span class="sxs-lookup"><span data-stu-id="ac195-108">Create a new **Console Application** project.</span></span>  
  
2.  <span data-ttu-id="ac195-109">Agregar un `Imports` instrucción en el archivo para el `System.Linq.Expressions` espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="ac195-109">Add an `Imports` statement to the file for the `System.Linq.Expressions` namespace.</span></span>  
  
3.  <span data-ttu-id="ac195-110">Agregue la clase `AndAlsoModifier` al proyecto.</span><span class="sxs-lookup"><span data-stu-id="ac195-110">Add the `AndAlsoModifier` class to your project.</span></span>  
  
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
  
     <span data-ttu-id="ac195-111">Esta clase hereda la clase <xref:System.Linq.Expressions.ExpressionVisitor> y está especializada en la modificación de expresiones que representan operaciones `AND` condicionales.</span><span class="sxs-lookup"><span data-stu-id="ac195-111">This class inherits the <xref:System.Linq.Expressions.ExpressionVisitor> class and is specialized to modify expressions that represent conditional `AND` operations.</span></span> <span data-ttu-id="ac195-112">Cambia estas operaciones de una expresión `AND` condicional a una expresión `OR` condicional.</span><span class="sxs-lookup"><span data-stu-id="ac195-112">It changes these operations from a conditional `AND` to a conditional `OR`.</span></span> <span data-ttu-id="ac195-113">Para ello, la clase invalida el método <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> del tipo base, porque las expresiones `AND` condicionales se representan como expresiones binarias.</span><span class="sxs-lookup"><span data-stu-id="ac195-113">To do this, the class overrides the <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> method of the base type, because conditional `AND` expressions are represented as binary expressions.</span></span> <span data-ttu-id="ac195-114">En el método `VisitBinary`, si la expresión que se pasa representa una operación `AND` condicional, el código construye una nueva expresión que contiene el operador `OR` condicional en lugar del operador `AND` condicional.</span><span class="sxs-lookup"><span data-stu-id="ac195-114">In the `VisitBinary` method, if the expression that is passed to it represents a conditional `AND` operation, the code constructs a new expression that contains the conditional `OR` operator instead of the conditional `AND` operator.</span></span> <span data-ttu-id="ac195-115">Si la expresión que se pasa a `VisitBinary` no representa una operación `AND` condicional, el método defiere a la implementación de la case base.</span><span class="sxs-lookup"><span data-stu-id="ac195-115">If the expression that is passed to `VisitBinary` does not represent a conditional `AND` operation, the method defers to the base class implementation.</span></span> <span data-ttu-id="ac195-116">Los métodos de clase base construyen nodos que son como los árboles de expresiones que se pasan, pero los subárboles de los nodos se reemplazan por los árboles de expresiones que genera de forma recursiva el visitante.</span><span class="sxs-lookup"><span data-stu-id="ac195-116">The base class methods construct nodes that are like the expression trees that are passed in, but the nodes have their sub trees replaced with the expression trees that are produced recursively by the visitor.</span></span>  
  
4.  <span data-ttu-id="ac195-117">Agregar un `Imports` instrucción en el archivo para el `System.Linq.Expressions` espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="ac195-117">Add an `Imports` statement to the file for the `System.Linq.Expressions` namespace.</span></span>  
  
5.  <span data-ttu-id="ac195-118">Agregue código a la `Main` método en el archivo Module1.vb para crear un árbol de expresión y pasarlo al método que la modifique.</span><span class="sxs-lookup"><span data-stu-id="ac195-118">Add code to the `Main` method in the Module1.vb file to create an expression tree and pass it to the method that will modify it.</span></span>  
  
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
  
     <span data-ttu-id="ac195-119">El código crea una expresión que contiene una operación `AND` condicional.</span><span class="sxs-lookup"><span data-stu-id="ac195-119">The code creates an expression that contains a conditional `AND` operation.</span></span> <span data-ttu-id="ac195-120">Luego crea una instancia de la clase `AndAlsoModifier` y pasa la expresión al método `Modify` de esta clase.</span><span class="sxs-lookup"><span data-stu-id="ac195-120">It then creates an instance of the `AndAlsoModifier` class and passes the expression to the `Modify` method of this class.</span></span> <span data-ttu-id="ac195-121">Se generan los árboles de expresiones tanto originales como modificados para mostrar el cambio.</span><span class="sxs-lookup"><span data-stu-id="ac195-121">Both the original and the modified expression trees are outputted to show the change.</span></span>  
  
6.  <span data-ttu-id="ac195-122">Compile y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ac195-122">Compile and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac195-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac195-123">See Also</span></span>  
 [<span data-ttu-id="ac195-124">Cómo: Ejecutar árboles de expresión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ac195-124">How to: Execute Expression Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)  
 [<span data-ttu-id="ac195-125">Árboles de expresión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ac195-125">Expression Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
