---
description: 'Más información acerca de: DEREF (Entity SQL)'
title: DEREF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4c78e833-b260-453d-9bf4-eb39857dd0fa
ms.openlocfilehash: 9d0f29123c1459c6eab21ea9cd860b5c9e77f591
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724731"
---
# <a name="deref-entity-sql"></a>DEREF (Entity SQL)

Desreferencia un valor de referencia y genera el resultado de dicha desreferenciación.  
  
## <a name="syntax"></a>Sintaxis  
  
```sql  
SELECT DEREF ( o.expression ) FROM Table AS o;
```  
  
## <a name="arguments"></a>Argumentos  

 `expression`  
 Expresión de consulta válida que devuelve una colección.  
  
## <a name="return-value"></a>Valor devuelto  

 El valor de la entidad a la que se hace referencia.  
  
## <a name="remarks"></a>Observaciones  

 El operador DEREF desreferencia un valor de referencia y genera el resultado de dicha desreferenciación. Por ejemplo, si `r` es una referencia de tipo REF \<T> , `Deref(r)` es una expresión de tipo `T` que produce la entidad a la que hace referencia `r` . Si el valor de referencia es NULL, o está pendiente (es decir, el destino de la referencia no existe), el resultado del operador DEREF es NULL.  
  
## <a name="example"></a>Ejemplo  

 La consulta [!INCLUDE[esql](../../../../../../includes/esql-md.md)] utiliza el operador DEREF para desreferenciar un valor de referencia y generar el resultado de dicha desreferenciación. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento descrito en [Cómo: ejecutar una consulta que devuelve resultados PrimitiveType](../how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2. Pase la consulta siguiente como argumento al método ExecutePrimitiveTypeQuery:  
  
 [!code-sql[DP EntityServices Concepts#DEREF](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#deref)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
- [CLI](ref-entity-sql.md)
- [CREATEREF](createref-entity-sql.md)
- [KEY](key-entity-sql.md)
- [Tipos estructurados que aceptan valores NULL](nullable-structured-types-entity-sql.md)
