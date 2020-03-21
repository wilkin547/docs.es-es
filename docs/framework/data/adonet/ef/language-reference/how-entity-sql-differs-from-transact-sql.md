---
title: Diferencias entre Entity SQL y Transact-SQL
ms.date: 03/30/2017
ms.assetid: 9c9ee36d-f294-4c8b-a196-f0114c94f559
ms.openlocfilehash: 299cb9bbe90c72619cf809a8fc673fca456bd6fd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150236"
---
# <a name="how-entity-sql-differs-from-transact-sql"></a>Diferencias entre Entity SQL y Transact-SQL
En este tema se [!INCLUDE[esql](../../../../../../includes/esql-md.md)] describen las diferencias entre Y Transact-SQLTransact-SQL .  
  
## <a name="inheritance-and-relationships-support"></a>Compatibilidad con herencia y relaciones  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]funciona directamente con esquemas de entidad conceptual y admite características de modelo conceptual como herencia y relaciones.  
  
 Cuando se trabaja con la herencia, suele ser útil seleccionar instancias de un subtipo de una colección de instancias de supertipo. El operador [oftype](oftype-entity-sql.md) [!INCLUDE[esql](../../../../../../includes/esql-md.md)] in `oftype` (similar a en secuencias de C) proporciona esta capacidad.  
  
## <a name="support-for-collections"></a>Compatibilidad con colecciones  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]trata las colecciones como entidades de primera clase. Por ejemplo:  
  
- Las expresiones de colecciones son válidas en una cláusula `from`.  
  
- Las subconsultas `in` y `exists` se han generalizado para permitir cualquier tipo de colección.  
  
     Una subconsulta es un tipo de colección. `e1 in e2` y `exists(e)` son las construcciones de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] que permiten realizar estas operaciones.  
  
- Las operaciones Set, como `union`, `intersect` y `except`, funcionan ahora en colecciones.  
  
- Las combinaciones funcionan en colecciones.  
  
## <a name="support-for-expressions"></a>Compatibilidad con expresiones  
 Transact-SQLTransact-SQL tiene subconsultas (tablas) y expresiones (filas y columnas).  
  
 Para admitir colecciones [!INCLUDE[esql](../../../../../../includes/esql-md.md)] y colecciones anidadas, hace que todo sea una expresión. [!INCLUDE[esql](../../../../../../includes/esql-md.md)]es más componible que Transact-SQLTransact-SQL: cada expresión se puede usar en cualquier lugar. Las expresiones de consulta siempre producen colecciones de los tipos proyectados y se pueden utilizar en cualquier parte donde se permita una expresión de colección. Para obtener información acerca de las [!INCLUDE[esql](../../../../../../includes/esql-md.md)]expresiones transact-SQLTransact-SQL que no se admiten en , vea [Expresiones no admitidas](unsupported-expressions-entity-sql.md).  
  
 A continuación se muestran consultas válidas de [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:  
  
```sql  
1+2 *3  
"abc"  
row(1 as a, 2 as b)  
{ 1, 3, 5}
e1 union all e2  
set(e1)  
```  
  
## <a name="uniform-treatment-of-subqueries"></a>Tratamiento uniforme de subconsultas  
 Dado su énfasis en las tablas, Transact-SQLTransact-SQL realiza una interpretación contextual de las subconsultas. Por ejemplo, una subconsulta de la `from` cláusula se considera un conjunto múltiple (tabla). Pero la misma subconsulta utilizada en la cláusula `select` se considera una subconsulta escalar. De forma similar, una subconsulta `in` utilizada en el lado izquierdo de un operador se considera una subconsulta escalar, mientras que se espera que el lado derecho sea una subconsulta multiconjunto.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] elimina estas diferencias. Una expresión tiene una interpretación uniforme que no depende del contexto en el que se utiliza. [!INCLUDE[esql](../../../../../../includes/esql-md.md)]considera que todas las subconsultas son subconsultas multiconjunto. Si se desea un valor escalar de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] la `anyelement` subconsulta, proporciona el operador que opera en una colección (en este caso, la subconsulta) y extrae un valor singleton de la colección.  
  
### <a name="avoiding-implicit-coercions-for-subqueries"></a>Evitar conversiones implícitas en subconsultas  
 Un efecto secundario relacionado del tratamiento uniforme de las subconsultas es la conversión implícita de las subconsultas en valores escalares. En concreto, en Transact-SQLTransact-SQL, un conjunto múltiple de filas (con un solo campo) se convierte implícitamente en un valor escalar cuyo tipo de datos es el del campo.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] no admite esta conversión implícita. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] proporciona el operador ANYELEMENT para extraer un valor singleton de una colección y una cláusula `select value` para evitar crear un contenedor de filas durante una expresión de consulta.  
  
## <a name="select-value-avoiding-the-implicit-row-wrapper"></a>Seleccionar el valor: evitar el contenedor de filas implícitas  
 La cláusula select de una subconsulta de Transact-SQLTransact-SQL crea implícitamente un contenedor de filas alrededor de los elementos de la cláusula. Esto implica que no podemos crear colecciones de valores escalares o de objetos. Transact-SQLTransact-SQL permite una coerción implícita entre un tipo de fila con un campo y un valor singleton del mismo tipo de datos.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] proporciona la cláusula `select value` para omitir la creación de filas implícitas. Solo se puede especificar un elemento en una cláusula `select value`. Cuando se utiliza este tipo de cláusula, no se crea ningún contenedor de filas en torno a los elementos de la cláusula `select` y se puede generar una colección de la forma deseada, por ejemplo: `select value a`.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] también proporciona el constructor de filas para crear filas arbitrarias. La cláusula `select` toma uno o más elementos en la proyección y devuelve un registro de datos con campos, de la siguiente forma:  
  
 `select a, b, c`  
  
## <a name="left-correlation-and-aliasing"></a>Correlación izquierda y uso de alias  
 En Transact-SQLTransact-SQL, las expresiones `select` de `from`un ámbito determinado (una sola cláusula como o ) no pueden hacer referencia a expresiones definidas anteriormente en el mismo ámbito. Algunos dialectos de SQL (incluido Transact-SQLTransact-SQL) admiten formas limitadas de estos en la `from` cláusula.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]generaliza las correlaciones `from` izquierdas en la cláusula y las trata uniformemente. Las expresiones de la cláusula `from` pueden hacer referencia a definiciones anteriores (a la izquierda) en la misma cláusula sin necesidad de una sintaxis adicional.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] también impone restricciones adicionales en consultas que afectan a cláusulas `group by`. Las expresiones de la `select` cláusula y `having` cláusula `group by` de dichas consultas solo pueden hacer referencia a las claves a través de sus alias. La siguiente construcción es válida en Transact-SQLTransact-SQL, pero no está en: [!INCLUDE[esql](../../../../../../includes/esql-md.md)]  
  
```sql  
SELECT t.x + t.y FROM T AS t group BY t.x + t.y
```  
  
 Para hacer esto en [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:  
  
```sql  
SELET k FROM T AS t GROUP BY (t.x + t.y) AS k
```  
  
## <a name="referencing-columns-properties-of-tables-collections"></a>Hacer referencia a columnas (propiedades) de tablas (colecciones)  
 Todas las referencias de columna de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se deben calificar con el alias de la tabla. La siguiente construcción (suponiendo que `a` es `T`una columna válida de tabla [!INCLUDE[esql](../../../../../../includes/esql-md.md)]) es válida en Transact-SQLTransact-SQL pero no en .  
  
```sql  
SELECT a FROM T
```  
  
 El formato de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] es:  
  
```sql  
SELECT t.a AS A FROM T AS t
```  
  
 Los alias de tabla son opcionales en la cláusula `from`. El nombre de la tabla se utiliza como alias implícito. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] también permite el formato siguiente:  
  
```sql  
SELET Tab.a FROM Tab
```  
  
## <a name="navigation-through-objects"></a>Navegación a través de objetos  
 Transact-SQLTransact-SQL usa la notación "." para hacer referencia a columnas de (una fila de) una tabla. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] amplía esta notación (que toma prestada de los lenguajes de programación) para admitir la navegación a través de las propiedades de un objeto.  
  
 Por ejemplo, si `p` es una expresión de tipo Persona, lo siguiente es la sintaxis de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] para hacer referencia a la ciudad de la dirección de esta persona.  
  
```sql  
p.Address.City
```  
  
## <a name="no-support-for-"></a>No hay compatibilidad con *  
 Transact-SQLTransact-SQL admite la sintaxis * no calificada \* como alias\*para toda la fila y la sintaxis calificada (t. ) como método abreviado para los campos de esa tabla. Además, Transact-SQLTransact-SQL\*permite un agregado count( ) especial, que incluye valores NULL.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] no admite la construcción *. Consultas de Transact-SQLTransact-SQL del [!INCLUDE[esql](../../../../../../includes/esql-md.md)] `select value t from T as t` formulario `select value t1 from T1 as t1, T2 as t2...` `select * from T` y `select T1.* from T1, T2...` se pueden expresar en como y , respectivamente. Además, estas construcciones administran la herencia (capacidad de sustitución de valores), mientras que las variantes de `select *` se restringen a las propiedades de nivel superior del tipo declarado.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] no admite el agregado `count(*)`. En su lugar, use `count(0)`.  
  
## <a name="changes-to-group-by"></a>Cambios de Group By  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] admite el uso de alias de las claves `group by`. Las expresiones de la cláusula `select` y de la cláusula `having` deben hacer referencia a las claves `group by` a través de estos alias. Por ejemplo, considere esta sintaxis de [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:  
  
```sql  
SELECT k1, count(t.a), sum(t.a)
FROM T AS t
GROUP BY t.b + t.c AS k1
```  
  
 ... es equivalente al siguiente Transact-SQLTransact-SQL:  
  
```sql  
SELECT b + c, count(*), sum(a)
FROM T
GROUP BY b + c
```  
  
## <a name="collection-based-aggregates"></a>Agregados basados en colecciones  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] admite dos tipos de agregados.  
  
 Los agregados basados en colecciones operan en colecciones y generan el resultado agregado. Estos pueden aparecer en cualquier parte de la consulta y no requieren una cláusula `group by`. Por ejemplo:  
  
```sql  
SELECT t.a AS a, count({1,2,3}) AS b FROM T AS t
```  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] también admite agregados del estilo de SQL. Por ejemplo:  
  
```sql  
SELECT a, sum(t.b) FROM T AS t GROUP BY t.a AS a
```  
  
## <a name="order-by-clause-usage"></a>Uso de la cláusula ORDER BY  
Transact-SQLTransact-SQL permite `ORDER BY` especificar cláusulas solo `SELECT .. FROM .. WHERE` en el bloque superior. En [!INCLUDE[esql](../../../../../../includes/esql-md.md)] usted puede `ORDER BY` usar una expresión anidada y se puede colocar en cualquier lugar de la consulta, pero el orden en una consulta anidada no se conserva.  
  
```sql  
-- The following query will order the results by the last name  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact AS C1
        ORDER BY C1.LastName  
```  
  
```sql  
-- In the following query ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="identifiers"></a>Identificadores  
 En Transact-SQLTransact-SQL, la comparación de identificadores se basa en la intercalación de la base de datos actual. En [!INCLUDE[esql](../../../../../../includes/esql-md.md)], los identificadores son siempre sin distinción entre mayúsculas y minúsculas, pero tienen en cuenta los acentos (es decir, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] distingue entre caracteres con y sin acento; por ejemplo, 'e' no es igual a 'é'). [!INCLUDE[esql](../../../../../../includes/esql-md.md)] trata las versiones de letras que parecen iguales pero proceden de páginas de códigos diferentes como caracteres distintos. Para obtener más información, consulte Conjunto de [caracteres](input-character-set-entity-sql.md)de entrada .  
  
## <a name="transact-sql-functionality-not-available-in-entity-sql"></a>Funcionalidad de Transact-SQL no disponible en Entity SQL  
 La siguiente funcionalidad de Transact-SQLTransact-SQL no está disponible en [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
 DML  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]actualmente no proporciona compatibilidad con instrucciones DML (insertar, actualizar, eliminar).  
  
 DDL  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] no proporciona compatibilidad con DDL en la versión actual.  
  
 Programación imperativa  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]no proporciona compatibilidad para la programación imperativa, a diferencia de Transact-SQLTransact-SQL. Utilice un lenguaje de programación en su lugar.  
  
 Funciones de agrupamiento  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] no proporciona aún compatibilidad con las funciones de agrupamiento (por ejemplo, CUBE, ROLLUP y GROUPING_SET).  
  
 Funciones analíticas  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] no proporciona aún compatibilidad con las funciones analíticas.  
  
 Funciones y operadores integrados  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]admite un subconjunto de funciones y operadores integrados de Transact-SQLTransact-SQL . Es probable que estos operadores y funciones sean admitidos por los principales proveedores de almacenamiento. [!INCLUDE[esql](../../../../../../includes/esql-md.md)]utiliza las funciones específicas del almacén declaradas en un manifiesto de proveedor. Además, Entity Framework permite declarar funciones de almacén existentes [!INCLUDE[esql](../../../../../../includes/esql-md.md)] integradas y definidas por el usuario, para su uso.  
  
 Sugerencias  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] no proporciona mecanismos para sugerencias de consulta.  
  
 Resultados de un consulta por lotes  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] no admite resultados de una consulta por lotes. Por ejemplo, lo siguiente es Transact-SQLTransact-SQL válido (envío como lote):  
  
```sql  
SELECT * FROM products;
SELECT * FROM catagories;
```  
  
 Sin embargo, no se admite el código [!INCLUDE[esql](../../../../../../includes/esql-md.md)] equivalente:  
  
```sql  
SELECT value p FROM Products AS p;
SELECT value c FROM Categories AS c;
```  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] admite únicamente una instrucción de consulta que genera un solo resultado por comando.  
  
## <a name="see-also"></a>Consulte también

- [Información general sobre Entity SQL](entity-sql-overview.md)
- [Expresiones no admitidas](unsupported-expressions-entity-sql.md)
