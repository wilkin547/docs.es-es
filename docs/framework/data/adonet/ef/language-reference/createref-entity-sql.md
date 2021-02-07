---
description: 'Más información acerca de: CREATEREF (Entity SQL)'
title: CREATEREF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 489828cf-a335-4449-9360-b0d92eec5481
ms.openlocfilehash: c4e96f97bd3587e50b34f6cbd63c5ae9ed8d94ba
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724783"
---
# <a name="createref-entity-sql"></a>CREATEREF (Entity SQL)

Crea referencias a una entidad en un elemento entityset.  
  
## <a name="syntax"></a>Sintaxis  
  
```sql  
CreateRef(entityset_identifier, row_typed_expression)  
```  
  
## <a name="arguments"></a>Argumentos  

 `entityset_identifier`  
 Identificador de entityset, no un literal de cadena.  
  
 `row_typed_expression`  
 Expresión escrita por fila que corresponde a las propiedades de clave del tipo de entidad.  
  
## <a name="remarks"></a>Observaciones  

 `row_typed_expression` debe ser estructuralmente equivalentes al tipo de clave de la entidad. Es decir, debe tener el mismo número y los mismos tipos de campos en el mismo orden que las claves de entidad.  
  
 En el ejemplo siguiente, Orders y BadOrders son ambos elementos entityset de tipo Order y se supone que Id es la propiedad de clave única de Order. El ejemplo muestra cómo se puede generar una referencia a una entidad en BadOrders. Observe que la referencia puede estar pendiente.  Es decir, la referencia puede no identificar realmente una entidad concreta. En esos casos, una operación `DEREF` en esa referencia devuelve un valor NULL.  
  
```sql  
SELECT CreateRef(LOB.BadOrders, row(o.Id))
FROM LOB.Orders AS o
```  
  
## <a name="example"></a>Ejemplo  

 La consulta de Entity SQL siguiente utiliza el operador CREATEREF para crear las referencias a una entidad en un conjunto de entidades. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#CREATEREF](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#createref)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
- [DEREF](deref-entity-sql.md)
- [KEY](key-entity-sql.md)
- [CLI](ref-entity-sql.md)
