---
description: 'Más información acerca de: GROUPPARTITION (Entity SQL)'
title: GROUPPARTITION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: d0482e9b-086c-451c-9dfa-ccb024a9efb6
ms.openlocfilehash: 18fdb655f62f54d59c03c0a34f6f77c5ca26729e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696911"
---
# <a name="grouppartition-entity-sql"></a>GROUPPARTITION (Entity SQL)

Devuelve una colección de valores de argumento que se proyecta a partir de la partición de grupo actual con la que está relacionado el agregado. El agregado `GroupPartition` es un agregado basado en un grupo y no tiene ningún formulario basado en una colección.  
  
## <a name="syntax"></a>Sintaxis  
  
```sql  
GROUPPARTITION( [ALL|DISTINCT] expression )  
```  
  
## <a name="arguments"></a>Argumentos  

 `expression`  
 Cualquier expresión [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .  
  
## <a name="remarks"></a>Observaciones  

 La consulta siguiente genera una lista de productos y una colección de cantidades de la línea de pedidos por cada producto:  
  
```sql  
SELECT p, GroupPartition(ol.Quantity) FROM LOB.OrderLines AS ol
  GROUP BY ol.Product AS p
```  
  
 Las dos consultas siguientes son semánticamente iguales:  
  
```sql  
SELECT p, Sum(GroupPartition(ol.Quantity)) FROM LOB.OrderLines AS ol
  GROUP BY ol.Product AS p
SELET p, Sum(ol.Quantity) FROM LOB.OrderLines AS ol
  group by ol.Product as p  
```  
  
 El operador `GROUPPARTITION` se puede utilizar junto con funciones de agregado definidas por el usuario.  
  
`GROUPPARTITION` es un operador agregado especial que retiene una referencia al conjunto de entrada agrupado. Esta referencia se puede utilizar en cualquier parte de la consulta donde GROUP BY se encuentre dentro del ámbito. Por ejemplo:
  
```sql  
SELECT p, GroupPartition(ol.Quantity) FROM LOB.OrderLines AS ol GROUP BY ol.Product AS p
```  
  
 Con un normal `GROUP BY` , se ocultan los resultados de la agrupación. Los resultados solo pueden utilizarse en una función de agregado. Para ver los resultados de la agrupación, tiene que poner en correlación los resultados de la agrupación y el conjunto de entrada mediante una subconsulta. Las dos consultas siguientes son equivalentes:  
  
```sql  
SELET p, (SELECT q FROM GroupPartition(ol.Quantity) AS q) FROM LOB.OrderLines AS ol GROUP BY ol.Product AS p
SELECT p, (SELECT ol.Quantity AS q FROM LOB.OrderLines AS ol2 WHERE ol2.Product = p) FROM LOB.OrderLines AS ol GROUP BY ol.Product AS p
```  
  
 Tal y como se ve en el ejemplo, el operador agregado GROUPPARTITION facilita la obtención de una referencia al conjunto de entrada después de la agrupación.  
  
 El operador GROUPPARTITION puede especificar cualquier expresión [!INCLUDE[esql](../../../../../../includes/esql-md.md)] en la entrada del operador cuando se utiliza el parámetro `expression` .  
  
 Por ejemplo todas las expresiones de entrada siguientes a la partición de grupo son válidas:  
  
```sql  
SELECT groupkey, GroupPartition(b) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey
SELECT groupkey, GroupPartition(1) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey
SELECT groupkey, GroupPartition(a + b) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey
SELECT groupkey, GroupPartition({a + b}) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey  
SELECT groupkey, GroupPartition({42}) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey  
SELECT groupkey, GroupPartition(b > a) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey  
```  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra cómo utilizar la cláusula GROUPPARTITION con la cláusula GROUP BY. La cláusula GROUP BY agrupa las entidades `SalesOrderHeader` por `Contact`. A continuación, la cláusula GROUPPARTITION proyecta la propiedad `TotalDue` para cada grupo, produciendo una colección de decimales.  
  
 [!code-sql[DP EntityServices Concepts#Collection_GroupPartition](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#collection_grouppartition)]
