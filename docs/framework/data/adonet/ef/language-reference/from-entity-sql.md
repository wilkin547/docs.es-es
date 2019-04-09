---
title: FROM (Entity SQL)
ms.date: 03/30/2017
ms.assetid: ff3e3048-0d5d-4502-ae5c-9187fcbd0514
ms.openlocfilehash: 3cc02b4c51b32d0faace4d89d0c6c1f6923dd138
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119839"
---
# <a name="from-entity-sql"></a>FROM (Entity SQL)
Especifica la colección que se usa en [seleccione](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md) instrucciones.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
FROM expression [ ,...n ] as C  
```  
  
## <a name="arguments"></a>Argumentos  
 `expression`  
 Cualquier expresión de consulta válida que produce una colección que usar como origen en una instrucción `SELECT`.  
  
## <a name="remarks"></a>Comentarios  
 Una cláusula `FROM` es una lista separada por comas de uno o varios elementos de la cláusula `FROM`. La cláusula `FROM` se puede utilizar para especificar uno o varios orígenes para una instrucción `SELECT`. La forma más sencilla de una cláusula `FROM` es una expresión de una única consulta que identifica una colección y un alias que se usa como origen en una instrucción `SELECT`, tal y como se muestra en el ejemplo siguiente:  
  
 `FROM C as c`  
  
## <a name="from-clause-items"></a>Elementos de la cláusula FROM  
 Cada elemento de la cláusula `FROM` hace referencia a una colección de origen en la consulta [!INCLUDE[esql](../../../../../../includes/esql-md.md)]. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] admite las siguientes clases de `FROM` elementos de la cláusula: simple `FROM` elementos de la cláusula `JOIN FROM` elementos de la cláusula y `APPLY FROM` elementos de la cláusula. En las siguientes secciones se describe con más detalle cada uno de estos elementos de la cláusula `FROM`.  
  
### <a name="simple-from-clause-item"></a>Elemento de la cláusula FROM simple  
 El elemento de la cláusula `FROM` más simple es una expresión única que identifica una colección y un alias. La expresión puede ser simplemente un conjunto de entidades, una subconsulta o cualquier otra expresión que sea un tipo de colección. A continuación se muestra un ejemplo:  
  
```  
LOB.Customers as c  
```  
  
 La especificación del alias es opcional. Una especificación alternativa del elemento de la cláusula FROM anterior podría ser la siguiente:  
  
```  
LOB.Customers  
```  
  
 Si no se especifica un alias, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] intenta generar uno según la expresión de la colección.  
  
### <a name="join-from-clause-item"></a>Elemento de la cláusula JOIN FROM  
 Un elemento de la cláusula `JOIN FROM` representa una unión entre dos elementos de la cláusula `FROM`. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] admite cruzadas combinaciones, las combinaciones internas, combinaciones externas izquierdas y derecha y combinaciones externas completas. Todas estas combinaciones se admiten de forma similar a como se admiten en [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]. Como en [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], los dos elementos de la cláusula `FROM` implicados en la `JOIN` deben ser independientes. Es decir, no pueden estar correlacionados. En estos casos se puede usar un elemento `CROSS APPLY` u `OUTER APPLY`.  
  
#### <a name="cross-joins"></a>Combinaciones cruzadas  
 Una expresión de consulta `CROSS JOIN` genera el producto cartesiano de las dos colecciones, tal y como se muestra en el ejemplo siguiente:  
  
 `FROM C AS c CROSS JOIN D as d`  
  
#### <a name="inner-joins"></a>Combinaciones internas  
 Una expresión de consulta `INNER JOIN` genera un producto cartesiano restringido de las dos colecciones, tal y como se muestra en el ejemplo siguiente:  
  
 `FROM C AS c [INNER] JOIN D AS d ON e`  
  
 La expresión de consulta anterior procesa una combinación de cada elemento de la colección de la izquierda emparejada con cada elemento de la colección de la derecha, donde la condición `ON` es verdad. Si no se especifica ninguna condición `ON`, una expresión `INNER JOIN` degenera en `CROSS JOIN`.  
  
#### <a name="left-outer-joins-and-right-outer-joins"></a>Combinación externa izquierda y combinación externa derecha  
 Una expresión de consulta `OUTER JOIN` genera el producto cartesiano restringido de las dos colecciones, tal y como se muestra en el ejemplo siguiente:  
  
 `FROM C AS c LEFT OUTER JOIN D AS d ON e`  
  
 La expresión de consulta anterior procesa una combinación de cada elemento de la colección de la izquierda emparejada con cada elemento de la colección de la derecha, donde la condición `ON` es verdad. Si la condición `ON` es falsa, la expresión todavía procesa una única instancia del elemento de la izquierda emparejado con el elemento de la derecha, con el valor NULL.  
  
 Una expresión `RIGHT OUTER JOIN` se puede expresar de una manera similar.  
  
#### <a name="full-outer-joins"></a>Combinación externa completa  
 Una expresión de consulta `FULL OUTER JOIN` explícita genera un producto cartesiano restringido de las dos colecciones, tal y como se muestra en el ejemplo siguiente:  
  
 `FROM C AS c FULL OUTER JOIN D AS d ON e`  
  
 La expresión de consulta anterior procesa una combinación de cada elemento de la colección de la izquierda emparejada con cada elemento de la colección de la derecha, donde la condición `ON` es verdad. Si la condición `ON` es falsa, la expresión aún procesa una instancia del elemento de la izquierda emparejada con el elemento de la derecha, con el valor NULL. También procesa una instancia del elemento de la derecha emparejado con el elemento de la izquierda, con el valor NULL.  
  
> [!NOTE]
>  Para conservar la compatibilidad con SQL-92, en [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], la palabra clave OUTER es opcional. Por lo tanto, `LEFT JOIN`, `RIGHT JOIN` y `FULL JOIN` son sinónimos de `LEFT OUTER JOIN`, `RIGHT OUTER JOIN` y `FULL OUTER JOIN`.  
  
### <a name="apply-clause-item"></a>Elemento de la cláusula APPLY  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] admite dos tipos de `APPLY`: `CROSS APPLY` y `OUTER APPLY`.  
  
 `CROSS APPLY` genera un emparejamiento único de cada elemento de la colección de la izquierda con un elemento de la colección que se crea al evaluar la expresión de la derecha. Con una expresión `CROSS APPLY`, la expresión de la derecha es funcionalmente dependiente del elemento de la izquierda, tal y como se muestra en el ejemplo de colección asociada siguiente:  
  
 `SELECT c, f FROM C AS c CROSS APPLY c.Assoc AS f`  
  
 El comportamiento de `CROSS APPLY` es similar a la lista de combinaciones. Si la expresión de la derecha se evalúa como una colección vacía, `CROSS APPLY` no genera ningún emparejamiento para esa instancia del elemento de la izquierda.  
  
 Una expresión `OUTER APPLY` se parece a `CROSS APPLY`, excepto en que se sigue produciendo un emparejamiento incluso cuando la expresión de la derecha se evalúa como una colección vacía. El siguiente es un ejemplo de `OUTER APPLY`:  
  
 `SELECT c, f FROM C AS c OUTER APPLY c.Assoc AS f`  
  
> [!NOTE]
>  A diferencia de lo que ocurre en [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], no hay necesidad de seguir un paso UNNEST explícito en [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
> [!NOTE]
>  `CROSS` y `OUTER APPLY` operadores se introdujeron en [!INCLUDE[ssVersion2005](../../../../../../includes/ssversion2005-md.md)]. En algunos casos, la canalización de la consulta podría generar código de Transact-SQL que contiene los operadores `CROSS APPLY` y `OUTER APPLY`. Dado que algunos proveedores back-end, incluidas las versiones de SQL Server anteriores a [!INCLUDE[ssVersion2005](../../../../../../includes/ssversion2005-md.md)], no admiten estos operadores, tales consultas no se pueden ejecutar en estos proveedores back-end.  
>   
>  Algunos escenarios típicos que podrían conducir  a la presencia de los operadores `CROSS APPLY``OUTER APPLY` en la consulta de salida son las siguientes: una subconsulta correlacionada con la paginación; AnyElement sobre una subconsulta correlacionada o sobre una colección generada mediante navegación; consultas LINQ que utilizan métodos de agrupación que aceptan un selector de elemento; una consulta en la que se especifica explícitamente `CROSS APPLY` u `OUTER APPLY`; una consulta que tiene una construcción `DEREF` sobre una construcción `REF`.  
  
## <a name="multiple-collections-in-the-from-clause"></a>Varias colecciones en la cláusula FROM  
 La cláusula `FROM` puede contener más de una colección separada por comas. En estos casos, se supone que las colecciones están combinadas. Considérelas como una operación CROSS JOIN de n direcciones.  
  
 En el ejemplo siguiente, `C` y `D` son colecciones independientes, pero `c.Names` depende de `C`.  
  
```  
FROM C AS c, D AS d, c.Names AS e  
```  
  
 El ejemplo anterior es lógicamente equivalente al ejemplo siguiente:  
  
 `FROM (C AS c JOIN D AS d) CROSS APPLY c.Names AS e`  
  
## <a name="left-correlation"></a>Correlación izquierda  
 Los elementos de la cláusula `FROM` pueden hacer referencia a los elementos especificados en las cláusulas anteriores. En el ejemplo siguiente, `C` y `D` son colecciones independientes, pero `c.Names` depende de `C`:  
  
```  
from C as c, D as d, c.Names as e  
```  
  
 Esto es lógicamente equivalente a:  
  
```  
from (C as c join D as d) cross apply c.Names as e  
```  
  
## <a name="semantics"></a>Semántica  
 Lógicamente, se supone que las colecciones de la cláusula `FROM` forman parte de la combinación cruzada de `n` direcciones (excepto en el caso de una combinación cruzada unidireccional). Los alias de la cláusula `FROM` se procesan de izquierda a derecha y se agregan al ámbito actual como referencia. Se supone que la cláusula `FROM` genera un multiconjunto de filas. Habrá un campo para cada elemento de la cláusula `FROM` que representa un elemento único de esa colección.  
  
 La cláusula `FROM` genera lógicamente un multiconjunto de filas de tipo Row(c, d, e), donde los campos c, d y e se supone que son del tipo de elemento de `C`, `D` y `c.Names`.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Introduce un alias para cada simple `FROM` elemento en el ámbito de la cláusula. Por ejemplo, en el fragmento de código de la cláusula FROM siguiente, los nombres introducidos en el ámbito son c, d y e.  
  
```  
from (C as c join D as d) cross apply c.Names as e  
```  
  
 En [!INCLUDE[esql](../../../../../../includes/esql-md.md)] (a diferencia de [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]), la cláusula `FROM` solo introduce los alias en el ámbito. Cualquier referencia a las columnas (propiedades) de estas colecciones se debe certificar con el alias.  
  
## <a name="pulling-up-keys-from-nested-queries"></a>Extraer claves de las consultas anidadas  
 No se admiten ciertos tipos de consultas que requieren la extracción de las claves de una consulta anidada. Por ejemplo, la consulta siguiente es válida:  
  
```  
select c.Orders from Customers as c   
```  
  
 Sin embargo, la consulta siguiente no es válida, porque la consulta anidada no tiene ninguna clave:  
  
```  
select {1} from {2, 3}  
```  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [Expresiones de consulta](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
- [Tipos estructurados que aceptan valores NULL](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)
