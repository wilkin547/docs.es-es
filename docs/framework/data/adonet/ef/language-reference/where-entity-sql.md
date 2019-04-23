---
title: WHERE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
ms.openlocfilehash: 02eeaeb8cfa335e5545b26d3d52b91c4e1614629
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59230712"
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

- [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [Expresiones de consulta](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
