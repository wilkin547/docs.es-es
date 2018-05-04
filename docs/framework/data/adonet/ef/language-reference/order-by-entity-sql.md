---
title: ORDER BY (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c0b61572-ecee-41eb-9d7f-74132ec8a26c
ms.openlocfilehash: 5cffd7a696496f92ae83822faff2f08e325eea93
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="order-by-entity-sql"></a>ORDER BY (Entity SQL)
Especifica el criterio de ordenación utilizado en los objetos devueltos en una instrucción SELECT.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
[ ORDER BY   
   {  
      order_by_expression [SKIP n] [LIMIT n]  
      [ COLLATE collation_name ]  
      [ ASC | DESC ]  
   }  
   [ ,…n ]   
]  
```  
  
## <a name="arguments"></a>Argumentos  
 `order_by_expression`  
 Cualquier expresión de consulta válida que especifique una propiedad por la que se va a ordenar. Se pueden especificar varias expresiones de ordenación. La secuencia de las expresiones de ordenación de la cláusula ORDER BY define la organización del conjunto de resultados ordenado.  
  
 COLLATE {collation_name}  
 Especifica que la operación ORDER BY se debe realizar de acuerdo con la intercalación especificada en `collation_name`. COLLATE solo es aplicable para las expresiones de cadena.  
  
 ASC  
 Especifica que los valores de la propiedad indicada se deben ordenar de forma ascendente, del valor más bajo al más alto. Este es el valor predeterminado.  
  
 DESC  
 Especifica que los valores de la propiedad indicada se deben ordenar de forma descendente, del valor más alto al más bajo.  
  
 LIMIT `n`  
 Solo se seleccionarán los `n` primeros elementos.  
  
 SKIP `n`  
 Omite los `n` primeros elementos.  
  
## <a name="remarks"></a>Comentarios  
 La cláusula ORDER BY se aplica lógicamente al resultado de la cláusula SELECT. La cláusula ORDER BY puede hacer referencia a los elementos de la lista de selección utilizando sus alias. La cláusula ORDER BY también puede hacer referencia a otras variables que estén actualmente en el ámbito. Sin embargo, si la cláusula SELECT se ha especificado con un modificador DISTINCT, la cláusula ORDER BY solo puede hacer referencia a los alias de la cláusula SELECT.  
  
 `SELECT c AS c1 FROM cs AS c ORDER BY c1.e1, c.e2`  
  
 Cada expresión en la cláusula ORDER BY se debe evaluar como un tipo que se puede comparar a efectos de desigualdad ordenada (menor que o mayor que, etc.). Estos tipos son generalmente primitivos escalares, como números, cadenas y fechas. Los tipos de fila de tipos comparables también se pueden comparar según el orden.  
  
 Si el código recorre en iteración un conjunto ordenado, que no sea para una proyección de nivel superior, no se garantiza que los resultados mantengan su orden.  
  
```  
-- In the following sample, order is guaranteed to be preserved:  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName  
```  
  
```  
-- In the following query ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
 Para tener una operación UNION, UNION ALL, EXCEPT o INTERSECT ordenada, utilice el modelo siguiente:  
  
```  
SELECT ...  
FROM ( UNION/EXCEPT/INTERSECT operation )  
ORDER BY ...  
```  
  
## <a name="restricted-keywords"></a>Palabras clave restringidas  
 Las palabras clave siguientes debe ir entre comillas cuando se utilizan en una cláusula `ORDER BY` :  
  
-   CROSS  
  
-   FULL  
  
-   KEY  
  
-   IZQUIERDA  
  
-   ORDER  
  
-   OUTER  
  
-   DERECHA  
  
-   ROW  
  
-   VALUE  
  
## <a name="ordering-nested-queries"></a>Ordenar las consultas anidadas  
 En Entity Framework, una expresión anidada se puede colocar en cualquier parte de la consulta; el orden de una consulta anidada no se conserva.  
  
```  
-- The following query will order the results by the last name.  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName  
```  
  
```  
-- In the following query, ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="example"></a>Ejemplo  
 La consulta de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] siguiente usa el operador ORDER BY para especificar el criterio de ordenación utilizado en los objetos devueltos en una instrucción SELECT. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#ORDERBY](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#orderby)]  
  
## <a name="see-also"></a>Vea también  
 [Expresiones de consulta](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md)  
 [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md)  
 [TOP](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
