---
title: ISNULL (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dc7a0173-3664-4c90-a57b-5cbb0a8ed7ee
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 31e0b77e397bd4f190119a01719da185211f7715
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="isnull-entity-sql"></a>ISNULL (Entity SQL)
Determina si una expresión de consulta es nula.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
expression IS [ NOT ] NULL  
```  
  
## <a name="arguments"></a>Argumentos  
 `expression`  
 Cualquier expresión de consulta válida. No puede ser una colección, tener miembros de una colección, o un tipo de registro con propiedades de tipo de colección.  
  
 NOT  
 Niega el resultado EDM.Boolean de IS NULL.  
  
## <a name="return-value"></a>Valor devuelto  
 `true` si `expression` devuelve null; en caso contrario, `false`.  
  
## <a name="remarks"></a>Comentarios  
 Utilice `IS NULL` para determinar si el elemento de una combinación externa es nulo:  
  
```  
select c   
      from LOB.Customers as c left outer join LOB.Orders as o   
                              on c.ID = o.CustomerID    
      where o is not null and o.OrderQuantity = @x  
```  
  
 Utilice `IS NULL` para determinar si un miembro tiene un valor real:  
  
```  
select c from LOB.Customer as c where c.DOB is not null  
```  
  
 En la tabla siguiente se muestra el comportamiento de `IS NULL` en algunos patrones. Todas las excepciones se producen en el cliente antes de que se llame al proveedor:  
  
|Modelo|Comportamiento|  
|-------------|--------------|  
|null IS NULL|Devuelve `true`.|  
|TREAT (null AS EntityType) IS NULL|Devuelve `true`.|  
|TREAT (null AS ComplexType) IS NULL|Produce un error.|  
|TREAT (null AS RowType) IS NULL|Produce un error.|  
|EntityType IS NULL|Devuelve `true` o `false`.|  
|ComplexType IS NULL|Produce un error.|  
|RowType IS NULL|Produce un error.|  
  
## <a name="example"></a>Ejemplo  
 El siguiente [!INCLUDE[esql](../../../../../../includes/esql-md.md)] consulta utiliza el operador IS NOT NULL para determinar si una expresión de consulta no es null. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#ISNULL](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#isnull)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
