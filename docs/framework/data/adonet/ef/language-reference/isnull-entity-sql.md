---
title: ISNULL (Entity SQL)
ms.date: 03/30/2017
ms.assetid: dc7a0173-3664-4c90-a57b-5cbb0a8ed7ee
ms.openlocfilehash: b3fc2484e80b637ed5841375985f7bae476bbbf7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150205"
---
# <a name="isnull-entity-sql"></a>ISNULL (Entity SQL)
Determina si una expresión de consulta es nula.  
  
## <a name="syntax"></a>Sintaxis  
  
```sql  
expression IS [ NOT ] NULL  
```  
  
## <a name="arguments"></a>Argumentos  
 `expression`  
 Cualquier expresión de consulta válida. No puede ser una colección, tener miembros de una colección, o un tipo de registro con propiedades de tipo de colección.  
  
 NOT  
 Niega el resultado EDM.Boolean de IS NULL.  
  
## <a name="return-value"></a>Valor devuelto  
 `true` si `expression` devuelve null; en caso contrario, `false`.  
  
## <a name="remarks"></a>Observaciones  
 Utilice `IS NULL` para determinar si el elemento de una combinación externa es nulo:  
  
```sql  
select c
      from LOB.Customers as c left outer join LOB.Orders as o
                              on c.ID = o.CustomerID
      where o is not null and o.OrderQuantity = @x  
```  
  
 Utilice `IS NULL` para determinar si un miembro tiene un valor real:  
  
```sql  
select c from LOB.Customer as c where c.DOB is not null  
```  
  
 En la tabla siguiente se muestra el comportamiento de `IS NULL` en algunos patrones. Todas las excepciones se producen en el cliente antes de que se llame al proveedor:  
  
|Patrón|Comportamiento|  
|-------------|--------------|  
|null IS NULL|Devuelve `true`.|  
|TREAT (null AS EntityType) IS NULL|Devuelve `true`.|  
|TREAT (null AS ComplexType) IS NULL|Produce un error.|  
|TREAT (null AS RowType) IS NULL|Produce un error.|  
|EntityType IS NULL|Devuelve `true` o `false`.|  
|ComplexType IS NULL|Produce un error.|  
|RowType IS NULL|Produce un error.|  
  
## <a name="example"></a>Ejemplo  
 La [!INCLUDE[esql](../../../../../../includes/esql-md.md)] siguiente consulta utiliza el operador IS NOT NULL para determinar si una expresión de consulta no es null. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#ISNULL](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#isnull)]  
  
## <a name="see-also"></a>Consulte también

- [Referencia de Entity SQL](entity-sql-reference.md)
