---
title: GROUPPARTITION (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d0482e9b-086c-451c-9dfa-ccb024a9efb6
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 8807564cb9acf8c50aed43ee11441ebdfbbcea78
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="grouppartition-entity-sql"></a>GROUPPARTITION (Entity SQL)
Devuelve una colección de valores de argumento que se proyecta a partir de la partición de grupo actual con la que está relacionado el agregado. El agregado `GroupPartition` es un agregado basado en un grupo y no tiene ningún formulario basado en una colección.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
GROUPPARTITION( [ALL|DISTINCT] expression )  
```  
  
## <a name="arguments"></a>Argumentos  
 `expression`  
 Cualquier expresión [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .  
  
## <a name="remarks"></a>Comentarios  
 La consulta siguiente genera una lista de productos y una colección de cantidades de la línea de pedidos por cada producto:  
  
```  
select p, GroupPartition(ol.Quantity) from LOB.OrderLines as ol  
  group by ol.Product as p  
```  
  
 Las dos consultas siguientes son semánticamente iguales:  
  
```  
select p, Sum(GroupPartition(ol.Quantity)) from LOB.OrderLines as ol  
  group by ol.Product as p  
select p, Sum(ol.Quantity) from LOB.OrderLines as ol  
  group by ol.Product as p  
```  
  
 El operador `GROUPPARTITION` se puede utilizar junto con funciones de agregado definidas por el usuario.  
  
 `GROUPPARTITION` es un operador agregado especial que retiene una referencia al conjunto de entrada agrupado. Esta referencia se puede utilizar en cualquier parte de la consulta donde GROUP BY se encuentre dentro del ámbito. Por ejemplo,  
  
```  
select p, GroupPartition(ol.Quantity) from LOB.OrderLines as ol group by ol.Product as p  
```  
  
 Con un GROUP BY normal, se ocultan los resultados de la agrupación. Los resultados solo pueden utilizarse en una función de agregado. Para ver los resultados de la agrupación, tiene que poner en correlación los resultados de la agrupación y el conjunto de entrada mediante una subconsulta. Las dos consultas siguientes son equivalentes:  
  
```  
select p, (select q from GroupPartition(ol.Quantity) as q) from LOB.OrderLines as ol group by ol.Product as p  
select p, (select ol.Quantity as q from LOB.OrderLines as ol2 where ol2.Product = p) from LOB.OrderLines as ol group by ol.Product as p  
```  
  
 Tal y como se ve en el ejemplo, el operador agregado GROUPPARTITION facilita la obtención de una referencia al conjunto de entrada después de la agrupación.  
  
 El operador GROUPPARTITION puede especificar cualquier expresión [!INCLUDE[esql](../../../../../../includes/esql-md.md)] en la entrada del operador cuando se utiliza el parámetro `expression` .  
  
 Por ejemplo todas las expresiones de entrada siguientes a la partición de grupo son válidas:  
  
```  
select groupkey, GroupPartition(b) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition(1) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition(a + b) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition({a + b}) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition({42}) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition(b > a) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
```  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar la cláusula GROUPPARTITION con la cláusula GROUP BY. La cláusula GROUP BY agrupa las entidades `SalesOrderHeader` por `Contact`. A continuación, la cláusula GROUPPARTITION proyecta la propiedad `TotalDue` para cada grupo, produciendo una colección de decimales.  
  
 [!code-csharp[DP EntityServices Concepts 2#Collection_GroupPartition](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#collection_grouppartition)]
