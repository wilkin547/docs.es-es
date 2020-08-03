---
title: Procedimiento para usar árboles de expresión para crear consultas dinámicas (C#)
description: Obtenga información sobre cómo usar árboles de expresión para crear consultas LINQ dinámicas. Estas consultas son útiles cuando no se conocen los detalles de una consulta en tiempo de compilación.
ms.date: 07/20/2015
ms.assetid: 52cd44dd-a3ec-441e-b93a-4eca388119c7
ms.openlocfilehash: edcef4068c19ba8e789683cf6ba4d5ef2477e0d8
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105592"
---
# <a name="how-to-use-expression-trees-to-build-dynamic-queries-c"></a><span data-ttu-id="c6334-104">Procedimiento para usar árboles de expresión para crear consultas dinámicas (C#)</span><span class="sxs-lookup"><span data-stu-id="c6334-104">How to use expression trees to build dynamic queries (C#)</span></span>
<span data-ttu-id="c6334-105">En LINQ, los árboles de expresión se usan para representar consultas estructuradas destinadas a orígenes de datos que implementan <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="c6334-105">In LINQ, expression trees are used to represent structured queries that target sources of data that implement <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="c6334-106">Por ejemplo, el proveedor LINQ implementa la interfaz <xref:System.Linq.IQueryable%601> para realizar consultas en almacenes de datos relacionales.</span><span class="sxs-lookup"><span data-stu-id="c6334-106">For example, the LINQ provider implements the <xref:System.Linq.IQueryable%601> interface for querying relational data stores.</span></span> <span data-ttu-id="c6334-107">El compilador de C# compila las consultas dirigidas a estos orígenes de datos en el código que genera un árbol de expresión en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c6334-107">The C# compiler compiles queries that target such data sources into code that builds an expression tree at runtime.</span></span> <span data-ttu-id="c6334-108">El proveedor de consultas puede después recorrer la estructura de datos del árbol de expresión y convertirla en un lenguaje de consulta adecuado para el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="c6334-108">The query provider can then traverse the expression tree data structure and translate it into a query language appropriate for the data source.</span></span>  
  
 <span data-ttu-id="c6334-109">Los arboles de expresión también se usan en LINQ para representar expresiones lambda que se asignan a variables de tipo <xref:System.Linq.Expressions.Expression%601>.</span><span class="sxs-lookup"><span data-stu-id="c6334-109">Expression trees are also used in LINQ to represent lambda expressions that are assigned to variables of type <xref:System.Linq.Expressions.Expression%601>.</span></span>  
  
 <span data-ttu-id="c6334-110">En este tema se describe cómo usar árboles de expresión para crear consultas LINQ dinámicas.</span><span class="sxs-lookup"><span data-stu-id="c6334-110">This topic describes how to use expression trees to create dynamic LINQ queries.</span></span> <span data-ttu-id="c6334-111">Las consultas dinámicas son útiles cuando no se conocen los detalles de una consulta en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="c6334-111">Dynamic queries are useful when the specifics of a query are not known at compile time.</span></span> <span data-ttu-id="c6334-112">Por ejemplo, es posible que una aplicación proporcione una interfaz de usuario que permita al usuario final especificar uno o más predicados para filtrar los datos.</span><span class="sxs-lookup"><span data-stu-id="c6334-112">For example, an application might provide a user interface that enables the end user to specify one or more predicates to filter the data.</span></span> <span data-ttu-id="c6334-113">Para poder usar LINQ para realizar consultas, este tipo de aplicación debe usar árboles de expresión para crear la consulta LINQ en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c6334-113">In order to use LINQ for querying, this kind of application must use expression trees to create the LINQ query at runtime.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6334-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c6334-114">Example</span></span>  
 <span data-ttu-id="c6334-115">En el ejemplo siguiente se muestra cómo usar árboles de expresión para crear una consulta en un origen de datos `IQueryable` y después ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="c6334-115">The following example shows you how to use expression trees to construct a query against an `IQueryable` data source and then execute it.</span></span> <span data-ttu-id="c6334-116">El código crea un árbol de expresión para representar la consulta siguiente:</span><span class="sxs-lookup"><span data-stu-id="c6334-116">The code builds an expression tree to represent the following query:</span></span>  
  
 ```csharp
 companies.Where(company => (company.ToLower() == "coho winery" || company.Length > 16))
          .OrderBy(company => company)
 ```
  
 <span data-ttu-id="c6334-117">Los métodos de generador en el espacio de nombres <xref:System.Linq.Expressions> se usan para crear árboles de expresión que representan las expresiones que constituyen la consulta global.</span><span class="sxs-lookup"><span data-stu-id="c6334-117">The factory methods in the <xref:System.Linq.Expressions> namespace are used to create expression trees that represent the expressions that make up the overall query.</span></span> <span data-ttu-id="c6334-118">Las expresiones que representan llamadas a los métodos de operador de consulta estándar hacen referencia a las implementaciones <xref:System.Linq.Queryable> de estos métodos.</span><span class="sxs-lookup"><span data-stu-id="c6334-118">The expressions that represent calls to the standard query operator methods refer to the <xref:System.Linq.Queryable> implementations of these methods.</span></span> <span data-ttu-id="c6334-119">El árbol de expresión final se pasa a la implementación <xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29> del proveedor del origen de datos `IQueryable` para crear una consulta ejecutable de tipo `IQueryable`.</span><span class="sxs-lookup"><span data-stu-id="c6334-119">The final expression tree is passed to the <xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29> implementation of the provider of the `IQueryable` data source to create an executable query of type `IQueryable`.</span></span> <span data-ttu-id="c6334-120">Los resultados se obtienen enumerando esa variable de consulta.</span><span class="sxs-lookup"><span data-stu-id="c6334-120">The results are obtained by enumerating that query variable.</span></span>  
  
```csharp  
// Add a using directive for System.Linq.Expressions.  
  
string[] companies = { "Consolidated Messenger", "Alpine Ski House", "Southridge Video", "City Power & Light",  
                   "Coho Winery", "Wide World Importers", "Graphic Design Institute", "Adventure Works",  
                   "Humongous Insurance", "Woodgrove Bank", "Margie's Travel", "Northwind Traders",  
                   "Blue Yonder Airlines", "Trey Research", "The Phone Company",  
                   "Wingtip Toys", "Lucerne Publishing", "Fourth Coffee" };  
  
// The IQueryable data to query.  
IQueryable<String> queryableData = companies.AsQueryable<string>();  
  
// Compose the expression tree that represents the parameter to the predicate.  
ParameterExpression pe = Expression.Parameter(typeof(string), "company");  
  
// ***** Where(company => (company.ToLower() == "coho winery" || company.Length > 16)) *****  
// Create an expression tree that represents the expression 'company.ToLower() == "coho winery"'.  
Expression left = Expression.Call(pe, typeof(string).GetMethod("ToLower", System.Type.EmptyTypes));  
Expression right = Expression.Constant("coho winery");  
Expression e1 = Expression.Equal(left, right);  
  
// Create an expression tree that represents the expression 'company.Length > 16'.  
left = Expression.Property(pe, typeof(string).GetProperty("Length"));  
right = Expression.Constant(16, typeof(int));  
Expression e2 = Expression.GreaterThan(left, right);  
  
// Combine the expression trees to create an expression tree that represents the  
// expression '(company.ToLower() == "coho winery" || company.Length > 16)'.  
Expression predicateBody = Expression.OrElse(e1, e2);  
  
// Create an expression tree that represents the expression  
// 'queryableData.Where(company => (company.ToLower() == "coho winery" || company.Length > 16))'  
MethodCallExpression whereCallExpression = Expression.Call(  
    typeof(Queryable),  
    "Where",  
    new Type[] { queryableData.ElementType },  
    queryableData.Expression,  
    Expression.Lambda<Func<string, bool>>(predicateBody, new ParameterExpression[] { pe }));  
// ***** End Where *****  
  
// ***** OrderBy(company => company) *****  
// Create an expression tree that represents the expression  
// 'whereCallExpression.OrderBy(company => company)'  
MethodCallExpression orderByCallExpression = Expression.Call(  
    typeof(Queryable),  
    "OrderBy",  
    new Type[] { queryableData.ElementType, queryableData.ElementType },  
    whereCallExpression,  
    Expression.Lambda<Func<string, string>>(pe, new ParameterExpression[] { pe }));  
// ***** End OrderBy *****  
  
// Create an executable query from the expression tree.  
IQueryable<string> results = queryableData.Provider.CreateQuery<string>(orderByCallExpression);  
  
// Enumerate the results.  
foreach (string company in results)  
    Console.WriteLine(company);  
  
/*  This code produces the following output:  
  
    Blue Yonder Airlines  
    City Power & Light  
    Coho Winery  
    Consolidated Messenger  
    Graphic Design Institute  
    Humongous Insurance  
    Lucerne Publishing  
    Northwind Traders  
    The Phone Company  
    Wide World Importers  
*/  
```  
  
 <span data-ttu-id="c6334-121">En este código se usa un número fijo de expresiones en el predicado que se pasa al método `Queryable.Where`.</span><span class="sxs-lookup"><span data-stu-id="c6334-121">This code uses a fixed number of expressions in the predicate that is passed to the `Queryable.Where` method.</span></span> <span data-ttu-id="c6334-122">Pero se puede escribir una aplicación que combine un número variable de expresiones de predicado que dependa de la entrada del usuario.</span><span class="sxs-lookup"><span data-stu-id="c6334-122">However, you can write an application that combines a variable number of predicate expressions that depends on the user input.</span></span> <span data-ttu-id="c6334-123">También se pueden variar los operadores de consulta estándar que se llaman en la consulta, dependiendo de la entrada del usuario.</span><span class="sxs-lookup"><span data-stu-id="c6334-123">You can also vary the standard query operators that are called in the query, depending on the input from the user.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c6334-124">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="c6334-124">Compiling the Code</span></span>  
  
- <span data-ttu-id="c6334-125">Incluya el espacio de nombres System.Linq.Expressions.</span><span class="sxs-lookup"><span data-stu-id="c6334-125">Include the System.Linq.Expressions namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6334-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6334-126">See also</span></span>

- [<span data-ttu-id="c6334-127">Árboles de expresión (C#)</span><span class="sxs-lookup"><span data-stu-id="c6334-127">Expression Trees (C#)</span></span>](./index.md)
- [<span data-ttu-id="c6334-128">Procedimiento para ejecutar árboles de expresión (C#)</span><span class="sxs-lookup"><span data-stu-id="c6334-128">How to execute expression trees (C#)</span></span>](./how-to-execute-expression-trees.md)
- [<span data-ttu-id="c6334-129">Especificar dinámicamente filtros con predicado en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="c6334-129">Dynamically specify predicate filters at runtime</span></span>](../../../linq/dynamically-specify-predicate-filters-at-runtime.md)
