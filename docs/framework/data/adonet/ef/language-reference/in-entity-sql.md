---
title: IN (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 51662950-ee01-4857-b7b9-311dd8515966
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: d32e5012b4acbf0ecd6830f549de5dccf79bb38b
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="in-entity-sql"></a>IN (Entity SQL)
Determina si un valor determinado coincide con algún valor de una colección.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
value [ NOT ] IN expression  
```  
  
## <a name="arguments"></a>Argumentos  
 `value`  
 Expresión válida que devuelve el valor que hay que buscar.  
  
 [ NOT ]  
 Especifica que el resultado `Boolean` de IN se niega.  
  
 `expression`  
 Expresión válida que devuelve la colección en la que hay que buscar una coincidencia. Todas las expresiones deben ser del mismo tipo que `value` o de un tipo base común o derivado.  
  
## <a name="return-value"></a>Valor devuelto  
 `true` si el valor se encuentra en la colección; Null si el valor o la colección son Null; `false`, en caso contrario. El uso de NOT IN niega el resultado de IN.  
  
## <a name="example"></a>Ejemplo  
 La siguiente consulta de Entity SQL usa el operador IN para determinar si un valor coincide con algún valor de una colección. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#IN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#in)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
