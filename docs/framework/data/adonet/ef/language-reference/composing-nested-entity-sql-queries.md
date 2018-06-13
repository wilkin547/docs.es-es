---
title: Crear consultas anidadas de Entity SQL
ms.date: 03/30/2017
ms.assetid: 685d4cd3-2c1f-419f-bb46-c9d97a351eeb
ms.openlocfilehash: 92e3153350787ef75c48ee52f1b6c68e09e15b4b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32760861"
---
# <a name="composing-nested-entity-sql-queries"></a>Crear consultas anidadas de Entity SQL
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] es un lenguaje funcional enriquecido. El bloque de creación de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] es una expresión. A diferencia del SQL convencional, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] no se limita a un conjunto de resultados tabular: [!INCLUDE[esql](../../../../../../includes/esql-md.md)] permite crear expresiones complejas que pueden tener literales, parámetros o expresiones anidadas. Un valor de la expresión se puede parametrizar o formado por alguna otra expresión.  
  
## <a name="nested-expressions"></a>Expresiones anidadas  
 Una expresión anidada se puede colocar en cualquier parte donde se acepte un valor del tipo que devuelve. Por ejemplo:  
  
```  
-- Returns a hierarchical collection of three elements at top-level.   
-- x must be passed in the parameter collection.  
ROW(@x, {@x}, {@x, 4, 5}, {@x, 7, 8, 9})  
  
-- Returns a hierarchical collection of one element at top-level.  
-- x must be passed in the parameter collection.  
{{{@x}}};  
```  
  
 Una consulta anidada se puede colocar en una cláusula de proyección. Por ejemplo:  
  
```  
-- Returns a collection of rows where each row contains an Address entity.  
-- and a collection of references to its corresponding SalesOrderHeader entities.  
SELECT address, (SELECT DEREF(soh)   
                    FROM NAVIGATE(address, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS soh)   
                    AS salesOrderHeader FROM AdventureWorksEntities.Address AS address  
```  
  
 En [!INCLUDE[esql](../../../../../../includes/esql-md.md)], las consultas anidadas siempre deben ir entre paréntesis:  
  
```  
-- Pseudo-Entity SQL  
( SELECT …  
FROM … )  
UNION ALL  
( SELECT …  
FROM … );  
```  
  
 En el ejemplo siguiente se muestra cómo anidar apropiadamente las expresiones en [!INCLUDE[esql](../../../../../../includes/esql-md.md)]: [Cómo: ordenar la unión de dos consultas](http://msdn.microsoft.com/library/853c583a-eaba-4400-830d-be974e735313).  
  
## <a name="nested-queries-in-projection"></a>Consultas anidadas en proyección  
 Las consultas anidadas en la cláusula del proyecto se podrían traducir en consultas de producto cartesiano en el servidor. Esto puede hacer que la tabla TempDB aumente, lo que puede afectar adversamente al rendimiento del servidor en algunos servidores de servicios backend, incluido SLQ Server.  
  
 A continuación se muestra un ejemplo de dicha consulta:  
  
```  
SELECT c, (SELECT c, (SELECT c FROM AdventureWorksModel.Vendor AS c  ) As Inner2 FROM AdventureWorksModel.JobCandidate AS c  ) As Inner1 FROM AdventureWorksModel.EmployeeDepartmentHistory AS c  
```  
  
## <a name="ordering-nested-queries"></a>Ordenar las consultas anidadas  
 En el Entity Framework, una expresión anidada se puede colocar en cualquier parte de la consulta. Dado que Entity SQL permite gran flexibilidad al escribir las consultas, es posible escribir una consulta que contenga una ordenación de las consultas anidadas. Sin embargo, el orden de una consulta anidada no se conserva.  
  
```  
-- The following query will order the results by last name.  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorksModel.Contact as C1  
        ORDER BY C1.LastName  
```  
  
```  
-- In the following query, ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorksModel.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
