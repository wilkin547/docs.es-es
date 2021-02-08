---
description: 'Más información acerca de: FLATTEN (Entity SQL)'
title: FLATTEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 1a670c63-0a29-4738-80e6-101f66af05c3
ms.openlocfilehash: 3701fbdf481024c799b4cdc6f109bae9fc226609
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786360"
---
# <a name="flatten-entity-sql"></a>FLATTEN (Entity SQL)

Convierte una colección de colecciones en una colección plana. La nueva colección contiene los mismos elementos que la colección anterior, pero sin una estructura anidada.  
  
## <a name="syntax"></a>Sintaxis  
  
```sql  
FLATTEN ( collection )  
```  
  
## <a name="arguments"></a>Argumentos  

 `collection`  
 Cualquier expresión válida que devuelva una colección de colecciones de valores para convertir en una sola colección.  
  
## <a name="remarks"></a>Observaciones  

 `FLATTEN` es uno de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] . Todos los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se evalúan de izquierda a derecha. Vea [excepto](except-entity-sql.md) para obtener información sobre la prioridad de los [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operadores de conjuntos.  
  
## <a name="example"></a>Ejemplo  

 La siguiente consulta de Entity SQL usa el operador `FLATTEN` para convertir una colección de colecciones en una colección plana. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#FLATTEN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#flatten)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
