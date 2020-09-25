---
title: USING (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
ms.openlocfilehash: bdab81ed8acae5e757de0a669922dc79d0303ee4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203597"
---
# <a name="using-entity-sql"></a>USING (Entity SQL)

Especifica espacios de nombres que se usan en una expresión de consulta.  
  
## <a name="syntax"></a>Sintaxis  
  
```sql  
USING [ alias = ] namespace  
```  
  
## <a name="arguments"></a>Argumentos  

 `alias`  
 Especifica un alias más breve con el que calificar un espacio de nombres.  
  
 `namespace`  
 Cualquier espacio de nombres válido.  
  
## <a name="example"></a>Ejemplo  

 En la consulta de Entity SQL siguiente se usa el operador USING para especificar los espacios de nombres que se usan en la expresión de consulta. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento descrito en [Cómo: ejecutar una consulta que devuelve resultados PrimitiveType](../how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2. Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :  
  
```csharp
using SqlServer; RAND()  
```  
  
## <a name="see-also"></a>Consulte también

- [Espacios de nombres](namespaces-entity-sql.md)
- [Referencia de Entity SQL](entity-sql-reference.md)
