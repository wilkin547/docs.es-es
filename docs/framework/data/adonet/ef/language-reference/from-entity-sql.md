---
title: FROM (Entity SQL)
ms.date: 03/30/2017
ms.assetid: ff3e3048-0d5d-4502-ae5c-9187fcbd0514
ms.openlocfilehash: 8affac82fb1813aa0282540b5dc2f47d42234a1b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148065"
---
# <a name="from-entity-sql"></a>FROM (Entity SQL)

Especifica la colección utilizada en las instrucciones [Select](select-entity-sql.md) .

## <a name="syntax"></a>Sintaxis

```sql
FROM expression [ ,...n ] AS C
```

## <a name="arguments"></a>Argumentos

`expression` \
Cualquier expresión de consulta válida que produce una colección que usar como origen en una instrucción `SELECT`.

## <a name="remarks"></a>Comentarios

Una cláusula `FROM` es una lista separada por comas de uno o varios elementos de la cláusula `FROM`. La cláusula `FROM` se puede utilizar para especificar uno o varios orígenes para una instrucción `SELECT`. La forma más sencilla de una cláusula `FROM` es una expresión de una única consulta que identifica una colección y un alias que se usa como origen en una instrucción `SELECT`, tal y como se muestra en el ejemplo siguiente:

`FROM C as c`

## <a name="from-clause-items"></a>Elementos de la cláusula FROM

Cada elemento de la cláusula `FROM` hace referencia a una colección de origen en la consulta [!INCLUDE[esql](../../../../../../includes/esql-md.md)]. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] admite las siguientes clases de elementos de la cláusula `FROM`: elementos de la cláusula `FROM` simples, elementos de la cláusula `JOIN FROM` y elementos de la cláusula `APPLY FROM`. En las siguientes secciones se describe con más detalle cada uno de estos elementos de la cláusula `FROM`.

### <a name="simple-from-clause-item"></a>Elemento de la cláusula FROM simple

El elemento de la cláusula `FROM` más simple es una expresión única que identifica una colección y un alias. La expresión puede ser simplemente un conjunto de entidades, una subconsulta o cualquier otra expresión que sea un tipo de colección. A continuación se muestra un ejemplo:

```sql
LOB.Customers as c
```

La especificación del alias es opcional. Una especificación alternativa del elemento de la cláusula FROM anterior podría ser la siguiente:

```sql
LOB.Customers
```

Si no se especifica un alias, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] intenta generar uno según la expresión de la colección.

### <a name="join-from-clause-item"></a>Elemento de la cláusula JOIN FROM

Un elemento de la cláusula `JOIN FROM` representa una unión entre dos elementos de la cláusula `FROM`. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] admite combinaciones cruzadas, combinaciones internas, combinaciones externas izquierda y derecha y combinaciones externas completas. Todas estas combinaciones se admiten de forma similar a como se admiten en Transact-SQL. Como en Transact-SQL, los dos `FROM` elementos de la cláusula implicados en `JOIN` deben ser independientes. Es decir, no pueden estar correlacionados. En estos casos se puede usar un elemento `CROSS APPLY` u `OUTER APPLY`.

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
> Para conservar la compatibilidad con SQL-92, en Transact-SQL la palabra clave OUTER es opcional. Por lo tanto, `LEFT JOIN`, `RIGHT JOIN` y `FULL JOIN` son sinónimos de `LEFT OUTER JOIN`, `RIGHT OUTER JOIN` y `FULL OUTER JOIN`.

### <a name="apply-clause-item"></a>Elemento de la cláusula APPLY

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] admite dos clases de `APPLY`: `CROSS APPLY` y `OUTER APPLY`.

`CROSS APPLY` genera un emparejamiento único de cada elemento de la colección de la izquierda con un elemento de la colección que se crea al evaluar la expresión de la derecha. Con una expresión `CROSS APPLY`, la expresión de la derecha es funcionalmente dependiente del elemento de la izquierda, tal y como se muestra en el ejemplo de colección asociada siguiente:

`SELECT c, f FROM C AS c CROSS APPLY c.Assoc AS f`

El comportamiento de `CROSS APPLY` es similar a la lista de combinaciones. Si la expresión de la derecha se evalúa como una colección vacía, `CROSS APPLY` no genera ningún emparejamiento para esa instancia del elemento de la izquierda.

Una expresión `OUTER APPLY` se parece a `CROSS APPLY`, excepto en que se sigue produciendo un emparejamiento incluso cuando la expresión de la derecha se evalúa como una colección vacía. El siguiente es un ejemplo de `OUTER APPLY`:

`SELECT c, f FROM C AS c OUTER APPLY c.Assoc AS f`

> [!NOTE]
> A diferencia de Transact-SQL, no es necesario un paso explícito UNNEST en [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .

> [!NOTE]
> `CROSS` los `OUTER APPLY` operadores y se introdujeron en SQL Server 2005. En algunos casos, la canalización de la consulta podría generar código de Transact-SQL que contiene los operadores `CROSS APPLY` y `OUTER APPLY`. Dado que algunos proveedores de back-end, incluidas las versiones de SQL Server anteriores a SQL Server 2005, no admiten estos operadores, tales consultas no se pueden ejecutar en estos proveedores de back-end.
>
> Algunos escenarios típicos que podrían conducir  a la presencia de los operadores `CROSS APPLY``OUTER APPLY` en la consulta de salida son las siguientes: una subconsulta correlacionada con la paginación; AnyElement sobre una subconsulta correlacionada o sobre una colección generada mediante navegación; consultas LINQ que utilizan métodos de agrupación que aceptan un selector de elemento; una consulta en la que se especifica explícitamente `CROSS APPLY` u `OUTER APPLY`; una consulta que tiene una construcción `DEREF` sobre una construcción `REF`.

## <a name="multiple-collections-in-the-from-clause"></a>Varias colecciones en la cláusula FROM

La cláusula `FROM` puede contener más de una colección separada por comas. En estos casos, se supone que las colecciones están combinadas. Considérelas como una operación CROSS JOIN de n direcciones.

En el ejemplo siguiente, `C` y `D` son colecciones independientes, pero `c.Names` depende de `C` .

```sql
FROM C AS c, D AS d, c.Names AS e
```

El ejemplo anterior es lógicamente equivalente al ejemplo siguiente:

`FROM (C AS c JOIN D AS d) CROSS APPLY c.Names AS e`

## <a name="left-correlation"></a>Correlación izquierda

 Los elementos de la cláusula `FROM` pueden hacer referencia a los elementos especificados en las cláusulas anteriores. En el ejemplo siguiente, `C` y `D` son colecciones independientes, pero `c.Names` depende de `C`:

```sql
from C as c, D as d, c.Names as e
```

Esto es lógicamente equivalente a:

```sql
from (C as c join D as d) cross apply c.Names as e
```

## <a name="semantics"></a>Semántica

Lógicamente, se supone que las colecciones de la cláusula `FROM` forman parte de la combinación cruzada de `n` direcciones (excepto en el caso de una combinación cruzada unidireccional). Los alias de la cláusula `FROM` se procesan de izquierda a derecha y se agregan al ámbito actual como referencia. Se supone que la cláusula `FROM` genera un multiconjunto de filas. Habrá un campo para cada elemento de la cláusula `FROM` que representa un elemento único de esa colección.

La cláusula `FROM` genera lógicamente un multiconjunto de filas de tipo Row(c, d, e), donde los campos c, d y e se supone que son del tipo de elemento de `C`, `D` y `c.Names`.

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] introduce un alias para cada elemento de la cláusula `FROM` simple en el ámbito. Por ejemplo, en el fragmento de código de la cláusula FROM siguiente, los nombres introducidos en el ámbito son c, d y e.

```sql
from (C as c join D as d) cross apply c.Names as e
```

En [!INCLUDE[esql](../../../../../../includes/esql-md.md)] (a diferencia de Transact-SQL), la `FROM` cláusula solo introduce los alias en el ámbito. Cualquier referencia a las columnas (propiedades) de estas colecciones se debe certificar con el alias.

## <a name="pulling-up-keys-from-nested-queries"></a>Extraer claves de las consultas anidadas

No se admiten ciertos tipos de consultas que requieren la extracción de las claves de una consulta anidada. Por ejemplo, la consulta siguiente es válida:

```sql
select c.Orders from Customers as c
```

Sin embargo, la consulta siguiente no es válida, porque la consulta anidada no tiene ninguna clave:

```sql
select {1} from {2, 3}
```

## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
- [Expresiones de consulta](query-expressions-entity-sql.md)
- [Tipos estructurados que aceptan valores NULL](nullable-structured-types-entity-sql.md)
