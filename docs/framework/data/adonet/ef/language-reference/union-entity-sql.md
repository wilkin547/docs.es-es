---
description: 'Más información acerca de: UNION (Entity SQL)'
title: UNION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: df98a4db-b00d-4c8b-bd74-0d285f27e1df
ms.openlocfilehash: f02b3d76d8c21848b7a1b7ef5e7bbf749aea5c0f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99673315"
---
# <a name="union-entity-sql"></a>UNION (Entity SQL)

Combina los resultados de dos o más consultas en una sola colección.  
  
## <a name="syntax"></a>Sintaxis  
  
```sql  
expression  
UNION [ ALL ]  
expression  
```  
  
## <a name="arguments"></a>Argumentos  

 `expression`  
 Cualquier expresión de consulta válida que devuelva una colección que combine con la colección. Todas las expresiones deben ser del mismo tipo que `expression`o de un tipo base común o derivado.  
  
 UNION  
 Especifica que se van a combinar varias colecciones y se van a devolver como una sola.  
  
 ALL  
 Especifica que se van a combinar varias colecciones y se van a devolver como una sola, que incluye duplicados. Si no se especifica, los duplicados se quitan de la colección resultado.  
  
## <a name="return-value"></a>Valor devuelto  

 Colección del mismo tipo que `expression`o de un tipo base común o derivado.  
  
## <a name="remarks"></a>Observaciones  

 UNION es uno de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] . Todos los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se evalúan de izquierda a derecha. Para obtener información sobre la prioridad de los [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operadores de conjuntos, vea [excepto](except-entity-sql.md).  
  
## <a name="example"></a>Ejemplo  

 La siguiente consulta de Entity SQL usa el operador UNION ALL para combinar los resultados de dos consultas en una sola colección. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#UNION](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#union)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
