---
title: WHERE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
ms.openlocfilehash: b551d15d7de2cf07afc7455b7fd0a0faf6436ccf
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319184"
---
# <a name="where-entity-sql"></a>WHERE (Entity SQL)
La cláusula WHERE se aplica directamente después de la cláusula [from](from-entity-sql.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```sql  
[ WHERE expression ]  
```  
  
## <a name="arguments"></a>Argumentos  
 `expression`  
 Tipo Boolean.  
  
## <a name="remarks"></a>Comentarios  
 La cláusula WHERE tiene la misma semántica que se describe en Transact-SQL. Restringe los objetos generados por la expresión de consulta limitando los elementos de las colecciones de origen a los que cumplen la condición.  
  
```sql  
select c from cs as c where e  
```  
  
 La expresión `e` debe tener el tipo Boolean.  
  
 La cláusula WHERE se aplica directamente después de la cláusula FROM y antes de que tenga lugar cualquier agrupación, ordenación o proyección. Todos los nombres de elemento definidos en la cláusula FROM son visibles para la expresión de la cláusula WHERE.  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
- [Expresiones de consulta](query-expressions-entity-sql.md)
