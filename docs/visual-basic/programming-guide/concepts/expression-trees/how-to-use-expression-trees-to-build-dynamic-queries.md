---
title: Procedimiento para usar árboles de expresión para crear consultas dinámicas
ms.date: 07/20/2015
ms.assetid: 16278787-7532-4b65-98b2-7a412406c4ee
ms.openlocfilehash: 1f686c37b5d04263ac5ae0dd6883aa8a519ed19e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410984"
---
# <a name="how-to-use-expression-trees-to-build-dynamic-queries-visual-basic"></a>Cómo: usar árboles de expresión para generar consultas dinámicas (Visual Basic)

En LINQ, los árboles de expresión se usan para representar consultas estructuradas destinadas a orígenes de datos que implementan <xref:System.Linq.IQueryable%601>. Por ejemplo, el proveedor LINQ implementa la interfaz <xref:System.Linq.IQueryable%601> para realizar consultas en almacenes de datos relacionales. El compilador de Visual Basic compila las consultas que tienen como destino estos orígenes de datos en el código que crea un árbol de expresión en tiempo de ejecución. El proveedor de consultas puede después recorrer la estructura de datos del árbol de expresión y convertirla en un lenguaje de consulta adecuado para el origen de datos.

Los arboles de expresión también se usan en LINQ para representar expresiones lambda que se asignan a variables de tipo <xref:System.Linq.Expressions.Expression%601>.

En este tema se describe cómo usar árboles de expresión para crear consultas LINQ dinámicas. Las consultas dinámicas son útiles cuando no se conocen los detalles de una consulta en tiempo de compilación. Por ejemplo, es posible que una aplicación proporcione una interfaz de usuario que permita al usuario final especificar uno o más predicados para filtrar los datos. Para poder usar LINQ para realizar consultas, este tipo de aplicación debe usar árboles de expresión para crear la consulta LINQ en tiempo de ejecución.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo usar árboles de expresión para crear una consulta en un origen de datos `IQueryable` y después ejecutarlo. El código crea un árbol de expresión para representar la consulta siguiente:

`companies.Where(Function(company) company.ToLower() = "coho winery" OrElse company.Length > 16).OrderBy(Function(company) company)`

Los métodos de generador en el espacio de nombres <xref:System.Linq.Expressions> se usan para crear árboles de expresión que representan las expresiones que constituyen la consulta global. Las expresiones que representan llamadas a los métodos de operador de consulta estándar hacen referencia a las implementaciones <xref:System.Linq.Queryable> de estos métodos. El árbol de expresión final se pasa a la implementación <xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29> del proveedor del origen de datos `IQueryable` para crear una consulta ejecutable de tipo `IQueryable`. Los resultados se obtienen enumerando esa variable de consulta.

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

En este código se usa un número fijo de expresiones en el predicado que se pasa al método `Queryable.Where`. Pero se puede escribir una aplicación que combine un número variable de expresiones de predicado que dependa de la entrada del usuario. También se pueden variar los operadores de consulta estándar que se llaman en la consulta, dependiendo de la entrada del usuario.

## <a name="compile-the-code"></a>Compilar el código

- Cree un nuevo proyecto de **aplicación de consola** .

- Incluya el espacio de nombres System.Linq.Expressions.

- Copie el código del ejemplo y péguelo en el `Main` `Sub` procedimiento.

## <a name="see-also"></a>Consulte también

- [Árboles de expresión (Visual Basic)](index.md)
- [How to: Execute Expression Trees (Visual Basic)](how-to-execute-expression-trees.md) (Cómo ejecutar árboles de expresión en Visual Basic)
