---
title: Diferencias entre Entity SQL y Transact-SQL
ms.date: 03/30/2017
ms.assetid: 9c9ee36d-f294-4c8b-a196-f0114c94f559
ms.openlocfilehash: 96e2283074b6c69e51bb7fee4d4f257cdb58d615
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615636"
---
# <a name="how-entity-sql-differs-from-transact-sql"></a>Cómo difiere Entity SQL de Transact-SQL

En este artículo se describen las diferencias entre Entity SQL y Transact-SQL.  
  
## <a name="inheritance-and-relationships-support"></a>Compatibilidad con herencia y relaciones  
 Entity SQL trabaja directamente con esquemas de entidades conceptuales y admite características del modelo conceptual como la herencia y las relaciones.  
  
 Cuando se trabaja con la herencia, suele ser útil seleccionar instancias de un subtipo de una colección de instancias de supertipo. El operador [untype](oftype-entity-sql.md) en Entity SQL (similar a `oftype` en secuencias de C#) proporciona esta capacidad.  
  
## <a name="support-for-collections"></a>Compatibilidad con colecciones  
 Entity SQL trata las colecciones como entidades de primera clase. Por ejemplo:  
  
- Las expresiones de colecciones son válidas en una cláusula `from`.  
  
- Las subconsultas `in` y `exists` se han generalizado para permitir cualquier tipo de colección.  
  
     Una subconsulta es un tipo de colección. `e1 in e2`y `exists(e)` son las construcciones de Entity SQL para realizar estas operaciones.  
  
- Las operaciones Set, como `union`, `intersect` y `except`, funcionan ahora en colecciones.  
  
- Las combinaciones funcionan en colecciones.  
  
## <a name="support-for-expressions"></a>Compatibilidad con expresiones  
 Transact-SQL tiene subconsultas (tablas) y expresiones (filas y columnas).  
  
 Para admitir colecciones y colecciones anidadas, Entity SQL convierte todo en una expresión. Entity SQL es más ajustable que Transact-SQL; todas las expresiones se pueden usar en cualquier lugar. Las expresiones de consulta siempre producen colecciones de los tipos proyectados y se pueden utilizar en cualquier parte donde se permita una expresión de colección. Para obtener información sobre las expresiones de Transact-SQL que no se admiten en Entity SQL, vea [expresiones no admitidas](unsupported-expressions-entity-sql.md).  
  
 A continuación se muestran todas las consultas de Entity SQL válidas:  
  
```sql  
1+2 *3  
"abc"  
row(1 as a, 2 as b)  
{ 1, 3, 5}
e1 union all e2  
set(e1)  
```  
  
## <a name="uniform-treatment-of-subqueries"></a>Tratamiento uniforme de subconsultas  
 A partir de su énfasis en las tablas, Transact-SQL realiza la interpretación contextual de las subconsultas. Por ejemplo, se considera que una subconsulta de la `from` cláusula es un conjunto múltiple (tabla). Pero la misma subconsulta utilizada en la cláusula `select` se considera una subconsulta escalar. Del mismo modo, se considera que una subconsulta utilizada en el lado izquierdo de un `in` operador es una subconsulta escalar, mientras que se espera que el lado derecho sea una subconsulta MultiSet.  
  
 Entity SQL elimina estas diferencias. Una expresión tiene una interpretación uniforme que no depende del contexto en el que se utiliza. Entity SQL considera que todas las subconsultas son subconsultas de MultiSet. Si se desea un valor escalar de la subconsulta, Entity SQL proporciona el `anyelement` operador que opera en una colección (en este caso, la subconsulta) y extrae un valor singleton de la colección.  
  
### <a name="avoiding-implicit-coercions-for-subqueries"></a>Evitar conversiones implícitas en subconsultas  
 Un efecto secundario relacionado del tratamiento uniforme de las subconsultas es la conversión implícita de las subconsultas en valores escalares. En concreto, en Transact-SQL, un conjunto múltiple de filas (con un campo único) se convierte implícitamente en un valor escalar cuyo tipo de datos es el del campo.  
  
 Entity SQL no admite esta coerción implícita. Entity SQL proporciona el `ANYELEMENT` operador para extraer un valor singleton de una colección y una `select value` cláusula para evitar la creación de un contenedor de filas durante una expresión de consulta.  
  
## <a name="select-value-avoiding-the-implicit-row-wrapper"></a>Seleccionar el valor: evitar el contenedor de filas implícitas  
 La cláusula SELECT de una subconsulta Transact-SQL crea implícitamente un contenedor de filas alrededor de los elementos de la cláusula. Esto implica que no podemos crear colecciones de valores escalares o de objetos. Transact-SQL permite una conversión implícita entre un `rowtype` con un campo y un valor singleton del mismo tipo de datos.  
  
 Entity SQL proporciona la `select value` cláusula para omitir la construcción de filas implícita. Solo se puede especificar un elemento en una cláusula `select value`. Cuando se utiliza este tipo de cláusula, no se crea ningún contenedor de filas en torno a los elementos de la `select` cláusula y se puede generar una colección de la forma deseada, por ejemplo, `select value a` .  
  
 Entity SQL también proporciona el constructor de filas para construir filas arbitrarias. `select`toma uno o más elementos en la proyección y da como resultado un registro de datos con campos:  
  
 `select a, b, c`  
  
## <a name="left-correlation-and-aliasing"></a>Correlación izquierda y uso de alias  
 En Transact-SQL, las expresiones de un ámbito determinado (una sola cláusula como `select` o `from` ) no pueden hacer referencia a expresiones definidas anteriormente en el mismo ámbito. Algunos dialectos de SQL (incluido Transact-SQL) admiten formas limitadas en la `from` cláusula.  
  
 Entity SQL generaliza las correlaciones de la izquierda en la `from` cláusula y las trata de forma uniforme. Las expresiones de la cláusula `from` pueden hacer referencia a definiciones anteriores (a la izquierda) en la misma cláusula sin necesidad de una sintaxis adicional.  
  
 Entity SQL también impone restricciones adicionales en las consultas que implican `group by` cláusulas. Las expresiones de la `select` cláusula y `having` de estas consultas solo pueden hacer referencia a las `group by` claves a través de sus alias. La siguiente construcción es válida en Transact-SQL, pero no en Entity SQL:  
  
```sql  
SELECT t.x + t.y FROM T AS t group BY t.x + t.y
```  
  
 Para hacer esto en Entity SQL:  
  
```sql  
SELET k FROM T AS t GROUP BY (t.x + t.y) AS k
```  
  
## <a name="referencing-columns-properties-of-tables-collections"></a>Hacer referencia a columnas (propiedades) de tablas (colecciones)  
 Todas las referencias de columna en Entity SQL deben estar calificadas con el alias de tabla. La construcción siguiente (suponiendo que `a` es una columna válida de la tabla `T` ) es válida en TRANSACT-SQL, pero no en Entity SQL.  
  
```sql  
SELECT a FROM T
```  
  
 El formulario Entity SQL es  
  
```sql  
SELECT t.a AS A FROM T AS t
```  
  
 Los alias de tabla son opcionales en la cláusula `from`. El nombre de la tabla se utiliza como alias implícito. Entity SQL también permite el siguiente formato:  
  
```sql  
SELET Tab.a FROM Tab
```  
  
## <a name="navigation-through-objects"></a>Navegación a través de objetos  
 Transact-SQL usa la notación "." para hacer referencia a las columnas de una tabla (una fila de). Entity SQL extiende esta notación (prestada de lenguajes de programación) para admitir la navegación a través de las propiedades de un objeto.  
  
 Por ejemplo, si `p` es una expresión de tipo Person, la siguiente es la sintaxis de Entity SQL para hacer referencia a la ciudad de la dirección de esta persona.  
  
```sql  
p.Address.City
```  
  
## <a name="no-support-for-"></a>No se admite\*  
 Transact-SQL admite la sintaxis sin calificar \* como alias para toda la fila y la sintaxis completa \* (t. \* ) como un acceso directo para los campos de esa tabla. Además, Transact-SQL permite un agregado Count () especial \* , que incluye valores NULL.  
  
 Entity SQL no admite la construcción *. Las consultas de Transact-SQL del formulario `select * from T` y `select T1.* from T1, T2...` se pueden expresar en Entity SQL como `select value t from T as t` y `select value t1 from T1 as t1, T2 as t2...` , respectivamente. Además, estas construcciones administran la herencia (capacidad de sustitución de valores), mientras que las variantes de `select *` se restringen a las propiedades de nivel superior del tipo declarado.  
  
 Entity SQL no admite el `count(*)` agregado. Utilice `count(0)` en su lugar.  
  
## <a name="changes-to-group-by"></a>Cambios de Group By  
 Entity SQL admite el alias de `group by` claves. Las expresiones de la cláusula `select` y de la cláusula `having` deben hacer referencia a las claves `group by` a través de estos alias. Por ejemplo, esta sintaxis de Entity SQL:  
  
```sql  
SELECT k1, count(t.a), sum(t.a)
FROM T AS t
GROUP BY t.b + t.c AS k1
```  
  
 ... es equivalente a la siguiente instrucción Transact-SQL:  
  
```sql  
SELECT b + c, count(*), sum(a)
FROM T
GROUP BY b + c
```  
  
## <a name="collection-based-aggregates"></a>Agregados basados en colecciones  
 Entity SQL admite dos tipos de agregados.  
  
 Los agregados basados en colecciones operan en colecciones y generan el resultado agregado. Estos pueden aparecer en cualquier parte de la consulta y no requieren una cláusula `group by`. Por ejemplo:  
  
```sql  
SELECT t.a AS a, count({1,2,3}) AS b FROM T AS t
```  
  
 Entity SQL también admite agregados de estilo SQL. Por ejemplo:  
  
```sql  
SELECT a, sum(t.b) FROM T AS t GROUP BY t.a AS a
```  
  
## <a name="order-by-clause-usage"></a>Uso de la cláusula ORDER BY  
Transact-SQL permite `ORDER BY` que las cláusulas se especifiquen solo en el bloque de nivel superior `SELECT .. FROM .. WHERE` . En Entity SQL, puede usar una expresión anidada `ORDER BY` y se puede colocar en cualquier parte de la consulta, pero no se conserva la ordenación en una consulta anidada.  
  
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
 En Transact-SQL, la comparación de identificadores se basa en la intercalación de la base de datos actual. En Entity SQL, los identificadores siempre distinguen mayúsculas de minúsculas y distinguen acentos (es decir, Entity SQL distingue entre caracteres acentuados y no acentuados; por ejemplo, ' a ' no es igual a ' é '). Entity SQL trata las versiones de letras que parecen iguales pero proceden de páginas de códigos diferentes como caracteres distintos. Para obtener más información, vea [juego de caracteres de entrada](input-character-set-entity-sql.md).  
  
## <a name="transact-sql-functionality-not-available-in-entity-sql"></a>Funcionalidad de Transact-SQL no disponible en Entity SQL  
 La siguiente funcionalidad de Transact-SQL no está disponible en Entity SQL.  
  
 DML  
 Actualmente, Entity SQL no proporciona compatibilidad con instrucciones DML (Insert, Update y Delete).  
  
 DDL  
 Entity SQL no proporciona compatibilidad con DDL en la versión actual.  
  
 Programación imperativa  
 Entity SQL no proporciona compatibilidad con la programación imperativa, a diferencia de Transact-SQL. Utilice un lenguaje de programación en su lugar.  
  
 Funciones de agrupamiento  
 Entity SQL aún no proporciona compatibilidad con las funciones de agrupación (por ejemplo, CUBE, ROLLUP y GROUPING_SET).  
  
 Funciones analíticas  
 Entity SQL no proporciona compatibilidad con las funciones analíticas.  
  
 Funciones y operadores integrados  
 Entity SQL admite un subconjunto de funciones y operadores integrados de Transact-SQL. Es probable que estos operadores y funciones sean admitidos por los principales proveedores de almacenamiento. Entity SQL usa las funciones específicas del almacén declaradas en un manifiesto del proveedor. Además, el Entity Framework permite declarar funciones de almacenamiento existentes integradas y definidas por el usuario, para que Entity SQL las use.  
  
 Sugerencias  
 Entity SQL no proporciona mecanismos para las sugerencias de consulta.  
  
 Resultados de un consulta por lotes  
 Entity SQL no admite el procesamiento por lotes de los resultados de la consulta. Por ejemplo, el siguiente código de Transact-SQL es válido (se envía como un lote):  
  
```sql  
SELECT * FROM products;
SELECT * FROM catagories;
```  
  
 Sin embargo, no se admite el Entity SQL equivalente:  
  
```sql  
SELECT value p FROM Products AS p;
SELECT value c FROM Categories AS c;
```  
  
 Entity SQL solo admite una instrucción de consulta de generación de resultados por comando.  
  
## <a name="see-also"></a>Consulta también

- [Información general sobre Entity SQL](entity-sql-overview.md)
- [Expresiones no admitidas](unsupported-expressions-entity-sql.md)
