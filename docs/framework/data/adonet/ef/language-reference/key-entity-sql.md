---
title: KEY (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cbaa97a8-c89c-4460-8c74-00474695789f
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: aa18efd32998f881d49d7ebd71bad0cdf8122457
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="key-entity-sql"></a>KEY (Entity SQL)
Extrae la clave de una referencia o de una expresión de entidad.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
KEY(createref_expression)  
```  
  
## <a name="remarks"></a>Comentarios  
 Una clave de entidad contiene los valores de clave en el orden correcto de la entidad especificada o referencia a entidad. Dado que varios conjuntos de entidades pueden estar basados en el mismo tipo, la misma clave podría aparecer en cada conjunto de entidades. Para obtener una referencia única, utilice `REF`. El tipo de valor devuelto del operador KEY es un tipo de fila que incluye un campo para cada clave de la entidad, en el mismo orden.  
  
 En el ejemplo siguiente, al operador Key se le pasa una referencia a la entidad BadOrder y devuelve la parte de la clave de esa referencia. En este caso, un tipo de registro con exactamente un campo que corresponde a la propiedad `Id` .  
  
```  
select Key( CreateRef(LOB.BadOrders, row(o.Id)) )   
from LOB.Orders as o  
```  
  
## <a name="example"></a>Ejemplo  
 La consulta de Entity SQL siguiente utiliza el operador KEY para extraer la parte de la clave de una expresión con referencia de tipo. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#KEY](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#key)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)  
 [REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)  
 [DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)
