---
title: DEREF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4c78e833-b260-453d-9bf4-eb39857dd0fa
ms.openlocfilehash: 10c5ecb2b44c85dccd758cc1cf63a152da045cc1
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251081"
---
# <a name="deref-entity-sql"></a>DEREF (Entity SQL)
Desreferencia un valor de referencia y genera el resultado de dicha desreferenciación.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
SELECT DEREF ( o.expression ) from Table as o;  
```  
  
## <a name="arguments"></a>Argumentos  
 `expression`  
 Expresión de consulta válida que devuelve una colección.  
  
## <a name="return-value"></a>Valor devuelto  
 El valor de la entidad a la que se hace referencia.  
  
## <a name="remarks"></a>Comentarios  
 El operador DEREF desreferencia un valor de referencia y genera el resultado de dicha desreferenciación. Por ejemplo, si `r` es una referencia de tipo REF\<T >, `Deref(r)` es una expresión de tipo `T` que produce la entidad a `r`la que hace referencia. Si el valor de referencia es NULL, o está pendiente (es decir, el destino de la referencia no existe), el resultado del operador DEREF es NULL.  
  
## <a name="example"></a>Ejemplo  
 La consulta [!INCLUDE[esql](../../../../../../includes/esql-md.md)] utiliza el operador DEREF para desreferenciar un valor de referencia y generar el resultado de dicha desreferenciación. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento descrito [en cómo: Ejecuta una consulta que devuelve resultados](../how-to-execute-a-query-that-returns-primitivetype-results.md)PrimitiveType.  
  
2. Pase la consulta siguiente como argumento al método ExecutePrimitiveTypeQuery:  
  
 [!code-csharp[DP EntityServices Concepts 2#DEREF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#deref)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
- [REF](ref-entity-sql.md)
- [CREATEREF](createref-entity-sql.md)
- [KEY](key-entity-sql.md)
- [Tipos estructurados que aceptan valores NULL](nullable-structured-types-entity-sql.md)
