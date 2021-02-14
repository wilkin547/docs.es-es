---
description: 'Más información acerca de cómo: usar árboles de expresión para generar consultas dinámicas (Visual Basic)'
title: Procedimiento para usar árboles de expresión para crear consultas dinámicas
ms.date: 07/20/2015
ms.assetid: 16278787-7532-4b65-98b2-7a412406c4ee
ms.openlocfilehash: bb8abb22749cbf7c15b72632f60a5bd08287378d
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100423100"
---
# <a name="how-to-use-expression-trees-to-build-dynamic-queries-visual-basic"></a><span data-ttu-id="63389-103">Cómo: usar árboles de expresión para generar consultas dinámicas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63389-103">How to: Use Expression Trees to Build Dynamic Queries (Visual Basic)</span></span>

<span data-ttu-id="63389-104">En LINQ, los árboles de expresión se usan para representar consultas estructuradas destinadas a orígenes de datos que implementan <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="63389-104">In LINQ, expression trees are used to represent structured queries that target sources of data that implement <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="63389-105">Por ejemplo, el proveedor LINQ implementa la interfaz <xref:System.Linq.IQueryable%601> para realizar consultas en almacenes de datos relacionales.</span><span class="sxs-lookup"><span data-stu-id="63389-105">For example, the LINQ provider implements the <xref:System.Linq.IQueryable%601> interface for querying relational data stores.</span></span> <span data-ttu-id="63389-106">El compilador de Visual Basic compila las consultas que tienen como destino estos orígenes de datos en el código que crea un árbol de expresión en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="63389-106">The Visual Basic compiler compiles queries that target such data sources into code that builds an expression tree at runtime.</span></span> <span data-ttu-id="63389-107">El proveedor de consultas puede después recorrer la estructura de datos del árbol de expresión y convertirla en un lenguaje de consulta adecuado para el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="63389-107">The query provider can then traverse the expression tree data structure and translate it into a query language appropriate for the data source.</span></span>

<span data-ttu-id="63389-108">Los arboles de expresión también se usan en LINQ para representar expresiones lambda que se asignan a variables de tipo <xref:System.Linq.Expressions.Expression%601>.</span><span class="sxs-lookup"><span data-stu-id="63389-108">Expression trees are also used in LINQ to represent lambda expressions that are assigned to variables of type <xref:System.Linq.Expressions.Expression%601>.</span></span>

<span data-ttu-id="63389-109">En este tema se describe cómo usar árboles de expresión para crear consultas LINQ dinámicas.</span><span class="sxs-lookup"><span data-stu-id="63389-109">This topic describes how to use expression trees to create dynamic LINQ queries.</span></span> <span data-ttu-id="63389-110">Las consultas dinámicas son útiles cuando no se conocen los detalles de una consulta en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="63389-110">Dynamic queries are useful when the specifics of a query are not known at compile time.</span></span> <span data-ttu-id="63389-111">Por ejemplo, es posible que una aplicación proporcione una interfaz de usuario que permita al usuario final especificar uno o más predicados para filtrar los datos.</span><span class="sxs-lookup"><span data-stu-id="63389-111">For example, an application might provide a user interface that enables the end user to specify one or more predicates to filter the data.</span></span> <span data-ttu-id="63389-112">Para poder usar LINQ para realizar consultas, este tipo de aplicación debe usar árboles de expresión para crear la consulta LINQ en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="63389-112">In order to use LINQ for querying, this kind of application must use expression trees to create the LINQ query at runtime.</span></span>

## <a name="example"></a><span data-ttu-id="63389-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="63389-113">Example</span></span>

<span data-ttu-id="63389-114">En el ejemplo siguiente se muestra cómo usar árboles de expresión para crear una consulta en un origen de datos `IQueryable` y después ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="63389-114">The following example shows you how to use expression trees to construct a query against an `IQueryable` data source and then execute it.</span></span> <span data-ttu-id="63389-115">El código crea un árbol de expresión para representar la consulta siguiente:</span><span class="sxs-lookup"><span data-stu-id="63389-115">The code builds an expression tree to represent the following query:</span></span>

`companies.Where(Function(company) company.ToLower() = "coho winery" OrElse company.Length > 16).OrderBy(Function(company) company)`

<span data-ttu-id="63389-116">Los métodos de generador en el espacio de nombres <xref:System.Linq.Expressions> se usan para crear árboles de expresión que representan las expresiones que constituyen la consulta global.</span><span class="sxs-lookup"><span data-stu-id="63389-116">The factory methods in the <xref:System.Linq.Expressions> namespace are used to create expression trees that represent the expressions that make up the overall query.</span></span> <span data-ttu-id="63389-117">Las expresiones que representan llamadas a los métodos de operador de consulta estándar hacen referencia a las implementaciones <xref:System.Linq.Queryable> de estos métodos.</span><span class="sxs-lookup"><span data-stu-id="63389-117">The expressions that represent calls to the standard query operator methods refer to the <xref:System.Linq.Queryable> implementations of these methods.</span></span> <span data-ttu-id="63389-118">El árbol de expresión final se pasa a la implementación <xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29> del proveedor del origen de datos `IQueryable` para crear una consulta ejecutable de tipo `IQueryable`.</span><span class="sxs-lookup"><span data-stu-id="63389-118">The final expression tree is passed to the <xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29> implementation of the provider of the `IQueryable` data source to create an executable query of type `IQueryable`.</span></span> <span data-ttu-id="63389-119">Los resultados se obtienen enumerando esa variable de consulta.</span><span class="sxs-lookup"><span data-stu-id="63389-119">The results are obtained by enumerating that query variable.</span></span>

```vb
' Add an Imports statement for System.Linq.Expressions.

Dim companies =
    {"Consolidated Messenger", "Alpine Ski House", "Southridge Video", "City Power & Light",
     "Coho Winery", "Wide World Importers", "Graphic Design Institute", "Adventure Works",
     "Humongous Insurance", "Woodgrove Bank", "Margie's Travel", "Northwind Traders",
     "Blue Yonder Airlines", "Trey Research", "The Phone Company",
     "Wingtip Toys", "Lucerne Publishing", "Fourth Coffee"}

' The IQueryable data to query.
Dim queryableData As IQueryable(Of String) = companies.AsQueryable()

' Compose the expression tree that represents the parameter to the predicate.
Dim pe As ParameterExpression = Expression.Parameter(GetType(String), "company")

' ***** Where(Function(company) company.ToLower() = "coho winery" OrElse company.Length > 16) *****
' Create an expression tree that represents the expression: company.ToLower() = "coho winery".
Dim left As Expression = Expression.Call(pe, GetType(String).GetMethod("ToLower", System.Type.EmptyTypes))
Dim right As Expression = Expression.Constant("coho winery")
Dim e1 As Expression = Expression.Equal(left, right)

' Create an expression tree that represents the expression: company.Length > 16.
left = Expression.Property(pe, GetType(String).GetProperty("Length"))
right = Expression.Constant(16, GetType(Integer))
Dim e2 As Expression = Expression.GreaterThan(left, right)

' Combine the expressions to create an expression tree that represents the
' expression: company.ToLower() = "coho winery" OrElse company.Length > 16).
Dim predicateBody As Expression = Expression.OrElse(e1, e2)

' Create an expression tree that represents the expression:
' queryableData.Where(Function(company) company.ToLower() = "coho winery" OrElse company.Length > 16)
Dim whereCallExpression As MethodCallExpression = Expression.Call(
        GetType(Queryable),
        "Where",
        New Type() {queryableData.ElementType},
        queryableData.Expression,
        Expression.Lambda(Of Func(Of String, Boolean))(predicateBody, New ParameterExpression() {pe}))
' ***** End Where *****

' ***** OrderBy(Function(company) company) *****
' Create an expression tree that represents the expression:
' whereCallExpression.OrderBy(Function(company) company)
Dim orderByCallExpression As MethodCallExpression = Expression.Call(
        GetType(Queryable),
        "OrderBy",
        New Type() {queryableData.ElementType, queryableData.ElementType},
        whereCallExpression,
        Expression.Lambda(Of Func(Of String, String))(pe, New ParameterExpression() {pe}))
' ***** End OrderBy *****

' Create an executable query from the expression tree.
Dim results As IQueryable(Of String) = queryableData.Provider.CreateQuery(Of String)(orderByCallExpression)

' Enumerate the results.
For Each company As String In results
    Console.WriteLine(company)
Next

' This code produces the following output:
'
' Blue Yonder Airlines
' City Power & Light
' Coho Winery
' Consolidated Messenger
' Graphic Design Institute
' Humongous Insurance
' Lucerne Publishing
' Northwind Traders
' The Phone Company
' Wide World Importers
```

<span data-ttu-id="63389-120">En este código se usa un número fijo de expresiones en el predicado que se pasa al método `Queryable.Where`.</span><span class="sxs-lookup"><span data-stu-id="63389-120">This code uses a fixed number of expressions in the predicate that is passed to the `Queryable.Where` method.</span></span> <span data-ttu-id="63389-121">Pero se puede escribir una aplicación que combine un número variable de expresiones de predicado que dependa de la entrada del usuario.</span><span class="sxs-lookup"><span data-stu-id="63389-121">However, you can write an application that combines a variable number of predicate expressions that depends on the user input.</span></span> <span data-ttu-id="63389-122">También se pueden variar los operadores de consulta estándar que se llaman en la consulta, dependiendo de la entrada del usuario.</span><span class="sxs-lookup"><span data-stu-id="63389-122">You can also vary the standard query operators that are called in the query, depending on the input from the user.</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="63389-123">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="63389-123">Compile the code</span></span>

- <span data-ttu-id="63389-124">Cree un nuevo proyecto de **aplicación de consola**.</span><span class="sxs-lookup"><span data-stu-id="63389-124">Create a new **Console Application** project.</span></span>

- <span data-ttu-id="63389-125">Incluya el espacio de nombres System.Linq.Expressions.</span><span class="sxs-lookup"><span data-stu-id="63389-125">Include the System.Linq.Expressions namespace.</span></span>

- <span data-ttu-id="63389-126">Copie el código del ejemplo y péguelo en el `Main` `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="63389-126">Copy the code from the example and paste it into the `Main` `Sub` procedure.</span></span>

## <a name="see-also"></a><span data-ttu-id="63389-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="63389-127">See also</span></span>

- [<span data-ttu-id="63389-128">Árboles de expresión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63389-128">Expression Trees (Visual Basic)</span></span>](index.md)
- <span data-ttu-id="63389-129">[How to: Execute Expression Trees (Visual Basic)](how-to-execute-expression-trees.md) (Cómo ejecutar árboles de expresión en Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63389-129">[How to: Execute Expression Trees (Visual Basic)](how-to-execute-expression-trees.md)</span></span>
