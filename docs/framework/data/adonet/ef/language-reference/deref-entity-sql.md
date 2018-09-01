---
title: DEREF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4c78e833-b260-453d-9bf4-eb39857dd0fa
ms.openlocfilehash: abe47f8c72abe13bd5c27fe10a412ff94ab861cf
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43384972"
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
 El operador DEREF desreferencia un valor de referencia y genera el resultado de dicha desreferenciación. Por ejemplo, si `r` es una referencia de tipo ref\<T >, `Deref(r)` es una expresión de tipo `T` que obtiene la entidad al que hace referencia `r`. Si el valor de referencia es NULL, o está pendiente (es decir, el destino de la referencia no existe), el resultado del operador DEREF es NULL.  
  
## <a name="example"></a>Ejemplo  
 La consulta [!INCLUDE[esql](../../../../../../includes/esql-md.md)] utiliza el operador DEREF para desreferenciar un valor de referencia y generar el resultado de dicha desreferenciación. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [Cómo: ejecutar una consulta que muestra los resultados PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método ExecutePrimitiveTypeQuery:  
  
 [!code-csharp[DP EntityServices Concepts 2#DEREF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#deref)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)  
 [CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)  
 [KEY](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)  
 [Tipos estructurados que aceptan valores NULL](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)
