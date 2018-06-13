---
title: ANYELEMENT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 475a9ad6-8c8d-4f49-9970-af273e5360f1
ms.openlocfilehash: 11d1dd4b09ff07519f3435d313de72c5b9a3edf4
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32761849"
---
# <a name="anyelement-entity-sql"></a>ANYELEMENT (Entity SQL)
Extrae un elemento de una colección de varios valores.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
ANYELEMENT ( expression )  
```  
  
## <a name="arguments"></a>Argumentos  
 `expression`  
 Expresión de consulta válida que devuelve una colección de la que extraer un elemento.  
  
## <a name="return-value"></a>Valor devuelto  
 Un único elemento de la colección o un elemento arbitrario si la colección tiene más de uno; si la colección está vacía, devuelve `null`. Si `collection` es una colección de tipo `Collection<T>`, a continuación, `ANYELEMENT(collection)` es una expresión válida que produzca una instancia de tipo `T`.  
  
## <a name="remarks"></a>Comentarios  
 ANYELEMENT extrae un elemento arbitrario de una colección de varios valores. Por ejemplo, a continuación se intenta extraer un elemento singleton del conjunto `Customers`.  
  
```  
ANYELEMENT(Customers)  
```  
  
## <a name="example"></a>Ejemplo  
 La siguiente consulta de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] usa el operador ANYELEMENT para extraer un elemento de una colección de varios valores. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#ANYELEMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#anyelement)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Tipos estructurados que aceptan valores NULL](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)
