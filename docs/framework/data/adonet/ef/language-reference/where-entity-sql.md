---
title: WHERE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
ms.openlocfilehash: 1907b8786622d3c8019c75916f997c830cc07cfb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91180964"
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
  
## <a name="remarks"></a>Observaciones  

 La cláusula WHERE tiene la misma semántica que se describe en Transact-SQL. Restringe los objetos generados por la expresión de consulta limitando los elementos de las colecciones de origen a los que cumplen la condición.  
  
```sql  
select c from cs as c where e  
```  
  
 La expresión `e` debe tener el tipo Boolean.  
  
 La cláusula WHERE se aplica directamente después de la cláusula FROM y antes de que tenga lugar cualquier agrupación, ordenación o proyección. Todos los nombres de elemento definidos en la cláusula FROM son visibles para la expresión de la cláusula WHERE.  
  
## <a name="see-also"></a>Consulte también

- [Referencia de Entity SQL](entity-sql-reference.md)
- [Expresiones de consulta](query-expressions-entity-sql.md)
