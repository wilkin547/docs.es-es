---
title: WHERE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
ms.openlocfilehash: 939d4c0ec2c30bc71b22fb65ab36644e063f97de
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489846"
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
 La cláusula WHERE tiene la misma semántica que se describen para Transact-SQL. Restringe los objetos generados por la expresión de consulta limitando los elementos de las colecciones de origen a los que cumplen la condición.  
  
```  
select c from cs as c where e  
```  
  
 La expresión `e` debe tener el tipo Boolean.  
  
 La cláusula WHERE se aplica directamente después de la cláusula FROM y antes de que tenga lugar cualquier agrupación, ordenación o proyección. Todos los nombres de elemento definidos en la cláusula FROM son visibles para la expresión de la cláusula WHERE.  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [Expresiones de consulta](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
