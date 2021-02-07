---
description: 'Más información acerca de: ANYELEMENT (Entity SQL)'
title: ANYELEMENT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 475a9ad6-8c8d-4f49-9970-af273e5360f1
ms.openlocfilehash: 3330c1b0bed69084bc83c5a689762ff529539d54
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697158"
---
# <a name="anyelement-entity-sql"></a>ANYELEMENT (Entity SQL)

Extrae un elemento de una colección de varios valores.  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp
ANYELEMENT ( expression )  
```  
  
## <a name="arguments"></a>Argumentos  

 `expression`  
 Expresión de consulta válida que devuelve una colección de la que extraer un elemento.  
  
## <a name="return-value"></a>Valor devuelto  

 Un único elemento de la colección o un elemento arbitrario si la colección tiene más de uno; si la colección está vacía, devuelve `null`. Si `collection` es una colección de tipo `Collection<T>` , entonces `ANYELEMENT(collection)` es una expresión válida que da como resultado una instancia de tipo `T` .  
  
## <a name="remarks"></a>Observaciones  

 ANYELEMENT extrae un elemento arbitrario de una colección de varios valores. Por ejemplo, a continuación se intenta extraer un elemento singleton del conjunto `Customers`.  
  
```csharp
ANYELEMENT(Customers)  
```  
  
## <a name="example"></a>Ejemplo  

 La siguiente consulta de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] usa el operador ANYELEMENT para extraer un elemento de una colección de varios valores. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#ANYELEMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#anyelement)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
- [Tipos estructurados que aceptan valores NULL](nullable-structured-types-entity-sql.md)
