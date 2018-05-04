---
title: Funciones de agregado (Entity SQL)
ms.date: 03/30/2017
ms.assetid: acfd3149-f519-4c6e-8fe1-b21d243a0e58
ms.openlocfilehash: 63e366f323b38a24c4d067681b47d8a8b96125b2
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="aggregate-functions-entity-sql"></a>Funciones de agregado (Entity SQL)
Un agregado es una construcción de lenguaje que comprime una colección en una propiedad escalar como parte de una operación de grupo. Los agregados de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tienen dos formas:  
  
-   [!INCLUDE[esql](../../../../../../includes/esql-md.md)] funciones de colección que se pueden usar en cualquier parte en una expresión. Esto incluye el uso de funciones de agregado en proyecciones y predicados que actúan en colecciones. Las funciones de colección constituyen el modo preferido de especificar agregados en [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
-   Agregados basados en grupos en expresiones de consulta que tienen una cláusula GROUP BY. Como en [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], los agregados de grupo aceptan los modificadores DISTINCT y ALL como modificadores para la entrada agregada.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] primero intenta interpretar una expresión como una función de colección y, si la expresión es en el contexto de una expresión SELECT interpreta como un agregado de grupo.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] define un operador agregado especial denominado [GROUPPARTITION](../../../../../../docs/framework/data/adonet/ef/language-reference/grouppartition-entity-sql.md). Este operador permite obtener una referencia al conjunto de entrada agrupado. Esto permite más consultas de agrupación avanzadas, donde los resultados de la cláusula GROUP BY se pueden utilizar en lugares distintos de las funciones de colección o los agregados de grupo.  
  
## <a name="collection-functions"></a>Funciones de colección  
 Las funciones de colección operan en colecciones y devuelven un valor escalar. Por ejemplo, si `orders` es una colección de todos los pedidos (`orders`), puede calcular la fecha de entrega más reciente con la expresión siguiente:  
  
 `min(select value o.ShipDate from LOB.Orders as o)`  
  
## <a name="group-aggregates"></a>Agregados basados en grupo  
 Los agregados basados en un grupo se calculan sobre un resultado de grupo según define la cláusula GROUP BY. La cláusula GROUP BY divide los datos en grupos. Para cada grupo del resultado, se aplica la función de agregado y se calcula un agregado diferente utilizando los elementos de cada grupo como entradas del cálculo del agregado. Cuando se usa una cláusula GROUP BY en una expresión SELECT, solo pueden estar presentes en la cláusula ORDER BY, HAVING o de la proyección los nombres de la expresión de agrupamiento, los agregados o las expresiones constantes.  
  
 En el ejemplo siguiente se calcula la cantidad promedio pedida de cada producto.  
  
 `select p, avg(ol.Quantity) from LOB.OrderLines as ol`  
  
 `group by ol.Product as p`  
  
 Es posible tener un agregado basado en un grupo sin una cláusula GROUP BY explícita en la expresión SELECT. Todos los elementos se tratarán como un grupo único, como en el caso de especificar una agrupación basada en una constante.  
  
 `select avg(ol.Quantity) from LOB.OrderLines as ol`  
  
 `select avg(ol.Quantity) from LOB.OrderLines as ol group by 1`  
  
 Las expresiones usadas en la clausula GROUP BY se evalúan usando el mismo ámbito de resolución de nombres que sería visible para la expresión de la cláusula WHERE.  
  
## <a name="see-also"></a>Vea también  
 [Funciones](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)
