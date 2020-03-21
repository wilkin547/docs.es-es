---
title: SELECT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 9a33bd0d-ded1-41e7-ba3c-305502755e3b
ms.openlocfilehash: de6c497e7d781d705c68092e4a13ee07b727b2b7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149914"
---
# <a name="select-entity-sql"></a>SELECT (Entity SQL)
Especifica los elementos devueltos por una consulta.  
  
## <a name="syntax"></a>Sintaxis  
  
```sql  
SELECT [ ALL | DISTINCT ] [ topSubclause ] aliasedExpr
      [{ , aliasedExpr }] FROM fromClause [ WHERE whereClause ] [ GROUP BY groupByClause [ HAVING havingClause ] ] [ ORDER BY orderByClause ]  
-- or  
SELECT VALUE [ ALL | DISTINCT ] [ topSubclause ] expr FROM fromClause [ WHERE whereClause ] [ GROUP BY groupByClause [ HAVING havingClause ] ] [ ORDER BY orderByClause  
```  
  
## <a name="arguments"></a>Argumentos  
 ALL  
 Especifica que el conjunto de resultados puede incluir resultados duplicados. ALL es el valor predeterminado.  
  
 DISTINCT  
 Especifica que el conjunto de resultados solo puede incluir resultados únicos.  
  
 VALOR  
 Solo permite que se especifique un elemento y no agrega un contenedor de filas.  
  
 `topSubclause`  
 Cualquier expresión válida que indique el número de primeros resultados que ha de devolver la consulta, del tipo `top(expr)`.  
  
 El parámetro LIMIT del operador [ORDER BY](order-by-entity-sql.md) también permite seleccionar los primeros n elementos del conjunto de resultados.  
  
 `aliasedExpr`  
 Expresión del tipo:  
  
 `expr`como `identifier` &#124;`expr`  
  
 `expr`  
 Literal o expresión.  
  
## <a name="remarks"></a>Observaciones  
 La cláusula SELECT se evalúa después de que se hayan evaluado las cláusulas [FROM](from-entity-sql.md), [GROUP BY](group-by-entity-sql.md)y [HAVING.](having-entity-sql.md) La cláusula SELECT solo puede hacer referencia a elementos que están actualmente en el ámbito (de la cláusula FROM o de ámbitos externos). Si se ha especificado una cláusula GROUP BY, la cláusula SELECT solo se permite para hacer referencia a los alias para las claves GROUP BY. La referencia a los elementos de la cláusula de FROM solo se permite en funciones de agregado.  
  
 La lista de una o más expresiones de consulta que siguen a la palabra clave SELECT se conoce como lista de selección o más formalmente como proyección. La forma más general de proyección es una expresión de consulta única. Si selecciona un miembro `member1` de una colección `collection1`, generará una nueva colección de todos los valores de `member1` para cada objeto de `collection1`, como se muestra en el ejemplo siguiente.  
  
```sql  
SELECT collection1.member1 FROM collection1  
```  
  
 Por ejemplo, si `customers` es una colección de tipo `Customer` que tiene una propiedad `Name` que es de tipo `string`, la acción de seleccionar `Name` de `customers` producirá una colección de cadenas, como se muestra en el ejemplo siguiente.  
  
```sql  
SELECT customers.Name FROM customers AS c  
```  
  
 También es posible utilizar la sintaxis de JOIN (FULL, INNER, LEFT, OUTER, ON y RIGHT). ON se requiere para combinaciones internas y no se permite para combinaciones cruzadas.  
  
## <a name="row-and-value-select-clauses"></a>Cláusulas de selección de fila y valor  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] admite dos variantes de la cláusula SELECT. La primera variante, selección de fila, se identifica mediante la palabra clave SELECT y se puede utilizar para especificar uno o varios valores que se deben proyectar. Dado que un contenedor de filas se agrega implícitamente alrededor de los valores devueltos, el resultado de la expresión de consulta siempre es un conjunto múltiple de filas.  
  
 Cada expresión de consulta en una selección de filas debe especificar un alias. Si no se especifica un alias,[!INCLUDE[esql](../../../../../../includes/esql-md.md)] intenta generar uno usando las reglas de generación de alias.  
  
 La otra variante de la cláusula SELECT, selección de valor, se identifica mediante la palabra clave SELECT VALUE. Solo permite que se especifique un valor y no agrega un contenedor de filas.  
  
 Una selección de fila siempre se puede expresar en términos de VALUE SELECT, como se muestra en el ejemplo siguiente.  
  
```sql  
SELECT 1 AS a, "abc" AS b FROM C  
SELECT VALUE ROW(1 AS a, "abc" AS b) FROM C
```  
  
## <a name="all-and-distinct-modifiers"></a>Modificadores All y Distinct  
 Las dos variantes de SELECT en [!INCLUDE[esql](../../../../../../includes/esql-md.md)] permiten la especificación de un modificador ALL o DISTINCT. Si se especifica el modificador DISTINCT, los resultados duplicados se eliminan de la colección producida por la expresión de consulta (hasta la cláusula SELECT e incluida dicha cláusula). Si se especifica el modificador ALL, no se lleva a cabo la eliminación de resultados duplicados; ALL es el valor predeterminado.  
  
## <a name="differences-from-transact-sql"></a>Diferencias respecto de Transact-SQL  
 A diferencia de Transact-SQL, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] no admite el uso del argumento * en la cláusula SELECT.  En su lugar, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] permite que las consultas proyecten externamente registros completos haciendo referencia a los alias para la colección de la cláusula FROM, como se muestra en el ejemplo siguiente.  
  
```sql  
SELECT * FROM T1, T2  
```  
  
 La expresión de consulta Transact-SQLTransact-SQL anterior se expresa [!INCLUDE[esql](../../../../../../includes/esql-md.md)] de la siguiente manera.  
  
```sql  
SELECT a1, a2 FROM T1 AS a1, T2 AS a2  
```  
  
## <a name="example"></a>Ejemplo  
 La consulta de Entity SQL siguiente utiliza el operador SELECT para especificar los elementos que ha de devolver una consulta. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#LESS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#less)]  
  
## <a name="see-also"></a>Consulte también

- [Expresiones de consulta](query-expressions-entity-sql.md)
- [Referencia de Entity SQL](entity-sql-reference.md)
- [Arriba](top-entity-sql.md)
