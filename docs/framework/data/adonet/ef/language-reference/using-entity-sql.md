---
title: USING (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
ms.openlocfilehash: 89306c8b4c317ebaba0d964869c4fe9e1028631a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="using-entity-sql"></a>USING (Entity SQL)
Especifica espacios de nombres que se usan en una expresión de consulta.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
USING [ alias = ] namespace  
```  
  
## <a name="arguments"></a>Argumentos  
 `alias`  
 Especifica un alias más breve con el que calificar un espacio de nombres.  
  
 `namespace`  
 Cualquier espacio de nombres válido.  
  
## <a name="example"></a>Ejemplo  
 En la consulta de Entity SQL siguiente se usa el operador USING para especificar los espacios de nombres que se usan en la expresión de consulta. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [Cómo: ejecutar una consulta que muestra los resultados PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :  
  
```  
using SqlServer; RAND()  
```  
  
## <a name="see-also"></a>Vea también  
 [Espacios de nombres](../../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md)  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
