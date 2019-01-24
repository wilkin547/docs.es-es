---
title: SET (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 28b4deac-c7e4-4f09-b428-4d352ef2dc94
ms.openlocfilehash: b6adce314e5d4fb1e4077b0efef758d07444e496
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54744445"
---
# <a name="set-entity-sql"></a>SET (Entity SQL)
La expresión SET se usa para convertir una colección de objetos en un conjunto produciendo una colección nueva en la que se han quitado todos los elementos duplicados.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
SET ( expression )  
```  
  
## <a name="arguments"></a>Argumentos  
 `expression`  
 Expresión de consulta válida que devuelve una colección.  
  
## <a name="remarks"></a>Comentarios  
 La expresión set `SET(c)` es lógicamente equivalente a la instrucción select siguiente:  
  
```  
SELECT VALUE DISTINCT c FROM c  
```  
  
 `SET` es uno de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] . Todos los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se evalúan de izquierda a derecha. Consulte [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md) para obtener información de prioridad para la [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operadores de conjuntos.  
  
## <a name="example"></a>Ejemplo  
 La siguiente consulta de Entity SQL usa la expresión SET para convertir una colección de objetos en un conjunto. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#SET](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#set)]  
  
## <a name="see-also"></a>Vea también
- [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
