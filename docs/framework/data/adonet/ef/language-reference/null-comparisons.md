---
title: Comparaciones NULL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ef88af8c-8dfe-4556-8b56-81df960a900b
ms.openlocfilehash: 697c933daeb3c68fb4ea89a957b639a79a9407f8
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249661"
---
# <a name="null-comparisons"></a>Comparaciones NULL
Un valor `null` en el origen de datos indica que el valor es desconocido. En las consultas LINQ to Entities, puede comprobar los valores nulos para que determinados cálculos o comparaciones solo se realicen en filas que tengan datos válidos o no nulos. Sin embargo, la semántica de NULL de CLR puede diferir de la del origen de datos. La mayoría de las bases de datos utilizan una versión de lógica con tres valores para tratar las comparaciones de NULL. Es decir, una comparación con un `true` `false`valor nulo no `unknown`se evalúa como o , se evalúa como . A menudo ésta es una implementación de los valores NULL ANSI, pero este no es siempre el caso.  
  
 De forma predeterminada en SQL Server, al comparar si un valor NULL es igual a un valor NULL, se devuelve un valor NULL. En el ejemplo siguiente, `ShipDate` las filas donde es null se excluyen del conjunto de resultados y la instrucción Transact-SQLTransact-SQL devolvería 0 filas.  
  
```sql  
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
 Un selector de *teclas* es una función utilizada en los operadores de consulta estándar para extraer una clave de un elemento. En la función de selector de clave, una expresión se puede comparar con una constante. La semántica de NULL del CLR se exhibe si una expresión se compara con una constante NULL o si se comparan dos constantes NULL. La semántica de NULL del almacén se exhibe si se comparan dos columnas con valores NULL del origen de datos. Los selectores de clave se encuentran en muchos de los operadores de consulta estándar de agrupamiento y ordenación, como <xref:System.Linq.Queryable.GroupBy%2A>, y se utilizan para seleccionar las claves por las que ordenar o agrupar los resultados de una consulta.  
  
## <a name="null-property-on-a-null-object"></a>Propiedad NULL en un objeto NULL  
 En Entity Framework, las propiedades de un objeto null son null. Al intentar hacer referencia a una propiedad de un objeto NULL en el CLR, recibirá <xref:System.NullReferenceException>. Cuando una consulta de LINQ implica una propiedad de un objeto NULL, puede provocarse un comportamiento incoherente.  
  
 Por ejemplo, en la consulta siguiente, la conversión a `NewProduct` se efectúa en el nivel de árbol de comandos, que podría hacer que la propiedad `Introduced` sea NULL. Si la base de datos definió las comparaciones de NULL de modo que la comparación de <xref:System.DateTime> se evalúe como true, la fila se incluirá.  
  
 [!code-csharp[DP L2E Conceptual Examples#CastResultsIsNull](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#castresultsisnull)]
 [!code-vb[DP L2E Conceptual Examples#CastResultsIsNull](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#castresultsisnull)]  
  
## <a name="passing-null-collections-to-aggregate-functions"></a>Pasar colecciones NULL a funciones de agregado  
 En LINQ to Entities, cuando se `IQueryable` pasa una colección que admite una función de agregado, las operaciones de agregado se realizan en la base de datos. Podría haber diferencias entre los resultados de una consulta que se realizó en memoria y una consulta que se realizó en la base de datos. En una consulta en memoria, si no hay ninguna coincidencia, la consulta devuelve el cero. En la base de datos, la misma consulta devuelve `null`. Si `null` se pasa un valor a una función de agregado LINQ, se producirá una excepción. Para aceptar `null` valores posibles, convierta los tipos y las propiedades de los tipos que reciben los resultados de la consulta en tipos de valor que aceptan valores NULL.  
  
## <a name="see-also"></a>Vea también

- [Expresiones en consultas de LINQ to Entities](expressions-in-linq-to-entities-queries.md)
