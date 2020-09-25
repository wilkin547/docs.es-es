---
title: Funciones de agregado (Entity SQL)
ms.date: 03/30/2017
ms.assetid: acfd3149-f519-4c6e-8fe1-b21d243a0e58
ms.openlocfilehash: 308670f04b9a04b1fff77ece08deb39c8c4081d1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198085"
---
# <a name="aggregate-functions-entity-sql"></a>Funciones de agregado (Entity SQL)

Un agregado es una construcción de lenguaje que comprime una colección en una propiedad escalar como parte de una operación de grupo. Los agregados de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tienen dos formas:  
  
- [!INCLUDE[esql](../../../../../../includes/esql-md.md)] funciones de colección que se pueden usar en cualquier parte de una expresión. Esto incluye el uso de funciones de agregado en proyecciones y predicados que actúan en colecciones. Las funciones de colección constituyen el modo preferido de especificar agregados en [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
- Agregados basados en grupos en expresiones de consulta que tienen una cláusula GROUP BY. Como en Transact-SQL, los agregados de grupo aceptan DISTINCt y ALL como modificadores para la entrada de agregado.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] primero intenta interpretar una expresión como una función de colección y si la expresión está en el contexto de una expresión SELECT, la interpreta como un agregado de grupo.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] define un operador agregado especial denominado [GROUPPARTITION](grouppartition-entity-sql.md). Este operador permite obtener una referencia al conjunto de entrada agrupado. Esto permite más consultas de agrupación avanzadas, donde los resultados de la cláusula GROUP BY se pueden utilizar en lugares distintos de las funciones de colección o los agregados de grupo.  
  
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

- [Funciones](functions-entity-sql.md)
