---
title: SET (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 28b4deac-c7e4-4f09-b428-4d352ef2dc94
ms.openlocfilehash: 9d4cdeac317509fd61741a19276a6764a1c2bfce
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319349"
---
# <a name="set-entity-sql"></a>SET (Entity SQL)
La expresión SET se usa para convertir una colección de objetos en un conjunto produciendo una colección nueva en la que se han quitado todos los elementos duplicados.  
  
## <a name="syntax"></a>Sintaxis  
  
```sql  
SET ( expression )  
```  
  
## <a name="arguments"></a>Argumentos  
 `expression`  
 Expresión de consulta válida que devuelve una colección.  
  
## <a name="remarks"></a>Comentarios  
 La expresión set `SET(c)` es lógicamente equivalente a la instrucción select siguiente:  
  
```sql  
SELECT VALUE DISTINCT c FROM c  
```  
  
 `SET` es uno de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] . Todos los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se evalúan de izquierda a derecha. Vea [excepto](except-entity-sql.md) para obtener información sobre la prioridad de los operadores de conjuntos [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
## <a name="example"></a>Ejemplo  
 La siguiente consulta de Entity SQL usa la expresión SET para convertir una colección de objetos en un conjunto. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento descrito en [Cómo: ejecutar una consulta que devuelve resultados PrimitiveType](../how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2. Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#SET](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#set)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
