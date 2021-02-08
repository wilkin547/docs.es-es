---
description: 'Más información sobre: superposiciones (Entity SQL)'
title: OVERLAPS (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 41743e89-79cb-4d7b-8a27-355b45024b61
ms.openlocfilehash: dd2f4a0925c57edcc3dd2d1264d00921b092525a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791912"
---
# <a name="overlaps-entity-sql"></a>OVERLAPS (Entity SQL)

Determina si dos colecciones tienen elementos comunes.  
  
## <a name="syntax"></a>Sintaxis  
  
```sql  
expression OVERLAPS expression  
```  
  
## <a name="arguments"></a>Argumentos  

 `expression`  
 Cualquier expresión de consulta válida que devuelva una colección para comparar con la colección que devuelve otra expresión de consulta. Todas las expresiones deben ser del mismo tipo que `expression`o de un tipo base común o derivado.  
  
## <a name="return-value"></a>Valor devuelto  

 `true` si las dos colecciones tienen elementos comunes; en caso contrario, `false`.  
  
## <a name="remarks"></a>Observaciones  

 Las superposiciones proporcionan funcionalmente equivalente a lo siguiente:  
  
 `EXISTS ( expression INTERSECT expression )`  
  
 OVERLAPS es uno de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] . Todos los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se evalúan de izquierda a derecha. Para obtener información sobre la prioridad de los [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operadores de conjuntos, vea [excepto](except-entity-sql.md).  
  
## <a name="example"></a>Ejemplo  

 La siguiente consulta de Entity SQL usa el operador OVERLAPS para determinar si dos colecciones tienen un valor común. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#OVERLAPS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#overlaps)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
