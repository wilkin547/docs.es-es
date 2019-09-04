---
title: Comparaciones NULL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ef88af8c-8dfe-4556-8b56-81df960a900b
ms.openlocfilehash: 6aa0af812d44f5c63758dd47ea4271bb2d689837
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249832"
---
# <a name="null-comparisons"></a>Comparaciones NULL
Un valor `null` en el origen de datos indica que el valor es desconocido. En LINQ to Entities consultas, puede comprobar si hay valores NULL para que determinados cálculos o comparaciones solo se realicen en filas con datos válidos o no nulos. Sin embargo, la semántica de NULL de CLR puede diferir de la del origen de datos. La mayoría de las bases de datos utilizan una versión de lógica con tres valores para tratar las comparaciones de NULL. Es decir, una comparación con un valor NULL no se evalúa como `true` o `false`, se evalúa como `unknown`. A menudo ésta es una implementación de los valores NULL ANSI, pero este no es siempre el caso.  
  
 De forma predeterminada en SQL Server, al comparar si un valor NULL es igual a un valor NULL, se devuelve un valor NULL. En el ejemplo siguiente, las filas donde `ShipDate` es NULL se excluyen del conjunto de resultados y la instrucción de Transact-SQL devolvería 0 filas.  
  
```  
-- Find order details and orders with no ship date.  
SELECT h.SalesOrderID  
FROM Sales.SalesOrderHeader h  
JOIN Sales.SalesOrderDetail o ON o.SalesOrderID = h.SalesOrderID  
WHERE h.ShipDate IS Null  
```  
  
 Esto es muy diferente de la semántica de NULL de CLR, donde la comparación de igualdad entre valores NULL devuelve true.  
  
 La consulta de LINQ siguiente se expresa en el CLR, pero se ejecuta en el origen de datos. Dado que no hay ninguna garantía de que la semántica de CLR se vaya a cumplir en el origen de datos, el comportamiento esperado es indeterminado.  
  
 [!code-csharp[DP L2E Conceptual Examples#JoinOnNull](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#joinonnull)]
 [!code-vb[DP L2E Conceptual Examples#JoinOnNull](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#joinonnull)]  
  
## <a name="key-selectors"></a>Selectores de clave  
 Un *selector de claves* es una función que se usa en los operadores de consulta estándar para extraer una clave de un elemento. En la función de selector de clave, una expresión se puede comparar con una constante. La semántica de NULL del CLR se exhibe si una expresión se compara con una constante NULL o si se comparan dos constantes NULL. La semántica de NULL del almacén se exhibe si se comparan dos columnas con valores NULL del origen de datos. Los selectores de clave se encuentran en muchos de los operadores de consulta estándar de agrupamiento y ordenación, como <xref:System.Linq.Queryable.GroupBy%2A>, y se utilizan para seleccionar las claves por las que ordenar o agrupar los resultados de una consulta.  
  
## <a name="null-property-on-a-null-object"></a>Propiedad NULL en un objeto NULL  
 En el [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)], las propiedades de un objeto NULL son NULL. Al intentar hacer referencia a una propiedad de un objeto NULL en el CLR, recibirá <xref:System.NullReferenceException>. Cuando una consulta de LINQ implica una propiedad de un objeto NULL, puede provocarse un comportamiento incoherente.  
  
 Por ejemplo, en la consulta siguiente, la conversión a `NewProduct` se efectúa en el nivel de árbol de comandos, que podría hacer que la propiedad `Introduced` sea NULL. Si la base de datos definió las comparaciones de NULL de modo que la comparación de <xref:System.DateTime> se evalúe como true, la fila se incluirá.  
  
 [!code-csharp[DP L2E Conceptual Examples#CastResultsIsNull](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#castresultsisnull)]
 [!code-vb[DP L2E Conceptual Examples#CastResultsIsNull](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#castresultsisnull)]  
  
## <a name="passing-null-collections-to-aggregate-functions"></a>Pasar colecciones NULL a funciones de agregado  
 En LINQ to Entities, cuando se pasa una colección que admite `IQueryable` a una función de agregado, las operaciones de agregado se realizan en la base de datos. Puede haber diferencias en los resultados de una consulta realizada en memoria y en una consulta realizada en la base de datos. Con una consulta en memoria, si no hay ninguna coincidencia, la consulta devuelve cero. En la base de datos, la misma consulta devuelve `null`. Si se `null` pasa un valor a una función de agregado de LINQ, se producirá una excepción. Para aceptar los `null` valores posibles, convierta los tipos y las propiedades de los tipos que reciben los resultados de la consulta a tipos que aceptan valores NULL.  
  
## <a name="see-also"></a>Vea también

- [Expresiones en consultas de LINQ to Entities](expressions-in-linq-to-entities-queries.md)
