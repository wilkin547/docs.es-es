---
title: WHERE (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 11687b1218c61acde7a68bb8fc112e287e5e1c38
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="where-entity-sql"></a>WHERE (Entity SQL)
La cláusula WHERE se aplica directamente después del [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md) cláusula.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
[ WHERE expression ]  
```  
  
## <a name="arguments"></a>Argumentos  
 `expression`  
 Tipo Boolean.  
  
## <a name="remarks"></a>Comentarios  
 La cláusula WHERE tiene la misma semántica que la descrita para [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]. Restringe los objetos generados por la expresión de consulta limitando los elementos de las colecciones de origen a los que cumplen la condición.  
  
```  
select c from cs as c where e  
```  
  
 La expresión `e` debe tener el tipo Boolean.  
  
 La cláusula WHERE se aplica directamente después de la cláusula FROM y antes de que tenga lugar cualquier agrupación, ordenación o proyección. Todos los nombres de elemento definidos en la cláusula FROM son visibles para la expresión de la cláusula WHERE.  
  
## <a name="see-also"></a>Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Expresiones de consulta](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
