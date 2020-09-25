---
title: Variables (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: af6d586a22f14a04bfc7ec339d0aa8e9ba7c66c7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181003"
---
# <a name="variables-entity-sql"></a>Variables (Entity SQL)

## <a name="variable"></a>Variable  

 Una expresión de variable es una referencia a una expresión con nombre definida en el ámbito actual. Una referencia de variable debe ser un [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identificador válido, tal y como se define en [Identifiers](identifiers-entity-sql.md).  
  
 En el siguiente ejemplo se muestra el uso de una variable en la expresión. La `c` de la cláusula FROM es la definición de la variable. El uso de `c` en la cláusula SELECT representa la referencia a la variable.  
  
```sql  
select c
from LOB.customers as c  
```  
  
## <a name="see-also"></a>Consulte también

- [Identificadores](identifiers-entity-sql.md)
- [Parámetros](parameters-entity-sql.md)
- [Información general sobre Entity SQL](entity-sql-overview.md)
