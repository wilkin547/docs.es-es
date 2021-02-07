---
description: 'Más información acerca de: Dónde (Entity SQL)'
title: WHERE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
ms.openlocfilehash: e094a93927f6ac77aef772654f1d8d4fcf999cbd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712875"
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
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
- [Expresiones de consulta](query-expressions-entity-sql.md)
