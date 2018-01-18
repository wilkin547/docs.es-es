---
title: OVERLAPS (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 41743e89-79cb-4d7b-8a27-355b45024b61
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 22593af3f79e78621764ba293e65505a72b194f8
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="overlaps-entity-sql"></a>OVERLAPS (Entity SQL)
Determina si dos colecciones tienen elementos comunes.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
expression OVERLAPS expression  
```  
  
## <a name="arguments"></a>Argumentos  
 `expression`  
 Cualquier expresión de consulta válida que devuelva una colección para comparar con la colección que devuelve otra expresión de consulta. Todas las expresiones deben ser del mismo tipo que `expression`o de un tipo base común o derivado.  
  
## <a name="return-value"></a>Valor devuelto  
 `true` si las dos colecciones tienen elementos comunes; en caso contrario, `false`.  
  
## <a name="remarks"></a>Comentarios  
 OVERLAPS es funcionalmente equivalente a la siguiente:  
  
 `EXISTS ( expression INTERSECT expression )`  
  
 OVERLAPS es uno de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] . Todos los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se evalúan de izquierda a derecha. Para obtener información de prioridad para la [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operadores de conjuntos, vea [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).  
  
## <a name="example"></a>Ejemplo  
 La siguiente consulta de Entity SQL usa el operador OVERLAPS para determinar si dos colecciones tienen un valor común. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#OVERLAPS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#overlaps)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
