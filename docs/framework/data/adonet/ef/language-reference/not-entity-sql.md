---
title: '! (NOT) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: a1447a34-df06-4393-93c3-0612ebd41abc
ms.openlocfilehash: 7755219c5238f78e59332c508643fe2ae1f5096f
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319518"
---
# <a name="-not-entity-sql"></a>! (NOT) (Entity SQL)
Niega una expresión `Boolean` .  
  
## <a name="syntax"></a>Sintaxis  
  
```sql  
NOT boolean_expression  
-- or  
! boolean_expression  
``` 
  
## <a name="arguments"></a>Argumentos  
 `boolean_expression`  
 Cualquier expresión válida que devuelve un valor booleano.  
  
## <a name="remarks"></a>Comentarios  
 El signo de admiración (!) tiene la misma funcionalidad que el operador NOT.  
  
## <a name="example"></a>Ejemplo  
 La siguiente consulta de Entity SQL usa el operador NOT para negar una expresión `Boolean` . La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#NOT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#not)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
