---
description: 'Más información acerca de: AGRUPAr por (Entity SQL)'
title: GROUP BY (Entity SQL)
ms.date: 03/30/2017
ms.assetid: cf4f4972-4724-4945-ba44-943a08549139
ms.openlocfilehash: 16328b46a59a2a07622cda43dce30d8b4f1d3dde
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696937"
---
# <a name="group-by-entity-sql"></a>GROUP BY (Entity SQL)

Especifica los grupos en los que se van a colocar los objetos devueltos por una expresión de consulta ([SELECT](select-entity-sql.md)).  
  
## <a name="syntax"></a>Sintaxis  
  
```sql  
[ GROUP BY aliasedExpression [ ,...n ] ]  
```  
  
## <a name="arguments"></a>Argumentos  

 `aliasedExpression`  
 Cualquier expresión de consulta válida en la que se realice una agrupación. `expression` puede ser una propiedad o una expresión no agregada que haga referencia a una propiedad devuelta por la cláusula FROM. Cada expresión de una cláusula GROUP BY se debe evaluar como un tipo en el que se pueda comparar la igualdad. Estos tipos son generalmente primitivos escalares, como números, cadenas y fechas. No se puede agrupar por una colección.  
  
## <a name="remarks"></a>Observaciones  

 Si se incluyen funciones de agregado en la cláusula SELECT \<select list> , Group by calcula un valor de resumen para cada grupo. Cuando se especifica GROUP BY, cada nombre de propiedad que esté en una expresión no agregada de la lista de selección se debe incluir en la lista de GROUP BY, o la expresión GROUP BY debe coincidir exactamente con la expresión de la lista de selección.  
  
> [!NOTE]
> Si no se especifica la cláusula ORDER BY, los grupos devueltos por la cláusula GROUP BY no estarán en un orden concreto. Se recomienda utilizar siempre la cláusula ORDER BY para especificar un orden concreto de los datos.  
  
 Cuando se especifica una cláusula GROUP BY, ya sea explícita o implícitamente (por ejemplo, mediante una cláusula HAVING en la consulta), se oculta el ámbito actual y se introduce un nuevo ámbito.  
  
 Las cláusulas SELECT, HAVING y ORDER BY ya no podrán hacer referencia a los nombres de elementos especificados en la cláusula FROM. solo se puede hacer referencia a las propias expresiones de agrupación. Para ello, puede asignar un nuevo nombre (alias) a cada expresión de agrupación. Si no se especifica ningún alias para una expresión de agrupación, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] intentará generar uno utilizando las reglas de generación de alias, como se muestra en el ejemplo siguiente.  
  
 `SELECT g1, g2, ...gn FROM c as c1`  
  
 `GROUP BY e1 as g1, e2 as g2, ...en as gn`  
  
 Las expresiones de la cláusula GROUP BY no pueden hacer referencia a nombres definidos anteriormente en la misma cláusula GROUP BY.  
  
 Además de los nombres de agrupación, también se pueden especificar agregados en las cláusulas SELECT, HAVING y ORDER BY. Un agregado contiene una expresión que se evalúa para cada elemento del grupo. El operador agregado reduce los valores de todas estas expresiones (normalmente, pero no siempre, en un valor único). La expresión agregada puede realizar referencias a los nombres de elemento originales visibles en el ámbito primario, o a cualquiera de los nuevos nombres introducido por la propia cláusula GROUP BY. Aunque los agregados aparecen en las cláusulas SELECT, HAVING y ORDER BY, se evalúan realmente en el mismo ámbito que las expresiones de agrupación, como se muestra en el ejemplo siguiente.  
  
 `SELECT name, sum(o.Price * o.Quantity) as total`  
  
 `FROM orderLines as o`  
  
 `GROUP BY o.Product as name`  
  
 Esta consulta utiliza la cláusula GROUP BY para generar un informe del costo de todos los productos pedidos, desglosado por producto. Asigna el nombre `name` al producto como parte de la expresión de agrupación y, a continuación, hace referencia a ese nombre en la lista SELECT. También especifica el valor `sum` agregado en la lista SELECT que hace referencia internamente al precio y la cantidad de la línea de pedidos.  
  
 Cada expresión de clave GROUP BY debe tener como mínimo una referencia al ámbito de entrada:  
  
```sql  
SELECT FROM Persons as P  
GROUP BY Q + P   -- GOOD  
GROUP BY Q   -- BAD  
GROUP BY 1   -- BAD, a constant is not allowed  
```  
  
 Para obtener un ejemplo de cómo se usa GROUP BY, vea [HAVING](having-entity-sql.md).  
  
## <a name="example"></a>Ejemplo  

 La consulta de Entity SQL siguiente utiliza el operador GROUP BY para especificar los grupos en los que una consulta devuelve los objetos. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento descrito en [Cómo: ejecutar una consulta que devuelve resultados PrimitiveType](../how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2. Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#GROUPBY](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#groupby)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
- [Expresiones de consulta](query-expressions-entity-sql.md)
