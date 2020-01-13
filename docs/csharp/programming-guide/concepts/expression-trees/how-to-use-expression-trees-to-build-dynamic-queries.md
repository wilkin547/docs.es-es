---
title: Procedimiento para usar árboles de expresión para crear consultas dinámicas (C#)
ms.date: 07/20/2015
ms.assetid: 52cd44dd-a3ec-441e-b93a-4eca388119c7
ms.openlocfilehash: 6114ec13dd43a7df146b87dda00fba06d6eb870c
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635904"
---
# <a name="how-to-use-expression-trees-to-build-dynamic-queries-c"></a>Procedimiento para usar árboles de expresión para crear consultas dinámicas (C#)
En LINQ, los árboles de expresión se usan para representar consultas estructuradas destinadas a orígenes de datos que implementan <xref:System.Linq.IQueryable%601>. Por ejemplo, el proveedor LINQ implementa la interfaz <xref:System.Linq.IQueryable%601> para realizar consultas en almacenes de datos relacionales. El compilador de C# compila las consultas dirigidas a estos orígenes de datos en el código que genera un árbol de expresión en tiempo de ejecución. El proveedor de consultas puede después recorrer la estructura de datos del árbol de expresión y convertirla en un lenguaje de consulta adecuado para el origen de datos.  
  
 Los arboles de expresión también se usan en LINQ para representar expresiones lambda que se asignan a variables de tipo <xref:System.Linq.Expressions.Expression%601>.  
  
 En este tema se describe cómo usar árboles de expresión para crear consultas LINQ dinámicas. Las consultas dinámicas son útiles cuando no se conocen los detalles de una consulta en tiempo de compilación. Por ejemplo, es posible que una aplicación proporcione una interfaz de usuario que permita al usuario final especificar uno o más predicados para filtrar los datos. Para poder usar LINQ para realizar consultas, este tipo de aplicación debe usar árboles de expresión para crear la consulta LINQ en tiempo de ejecución.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar árboles de expresión para crear una consulta en un origen de datos `IQueryable` y después ejecutarlo. El código crea un árbol de expresión para representar la consulta siguiente:  
  
 ```csharp
 companies.Where(company => (company.ToLower() == "coho winery" || company.Length > 16))
          .OrderBy(company => company)
 ```
  
 Los métodos de generador en el espacio de nombres <xref:System.Linq.Expressions> se usan para crear árboles de expresión que representan las expresiones que constituyen la consulta global. Las expresiones que representan llamadas a los métodos de operador de consulta estándar hacen referencia a las implementaciones <xref:System.Linq.Queryable> de estos métodos. El árbol de expresión final se pasa a la implementación <xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29> del proveedor del origen de datos `IQueryable` para crear una consulta ejecutable de tipo `IQueryable`. Los resultados se obtienen enumerando esa variable de consulta.  
  
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
  
 En este código se usa un número fijo de expresiones en el predicado que se pasa al método `Queryable.Where`. Pero se puede escribir una aplicación que combine un número variable de expresiones de predicado que dependa de la entrada del usuario. También se pueden variar los operadores de consulta estándar que se llaman en la consulta, dependiendo de la entrada del usuario.  
  
## <a name="compiling-the-code"></a>Compilar el código  
  
- Incluya el espacio de nombres System.Linq.Expressions.  
  
## <a name="see-also"></a>Vea también

- [Árboles de expresión (C#)](./index.md)
- [Procedimiento para ejecutar árboles de expresión (C#)](./how-to-execute-expression-trees.md)
- [Especificar dinámicamente filtros con predicado en tiempo de ejecución](../../../linq/dynamically-specify-predicate-filters-at-runtime.md)
