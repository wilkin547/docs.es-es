---
description: 'Más información acerca de: variables (Entity SQL)'
title: Variables (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: 134fee8f61c8e87a18520e6622f6a6a5cceb0076
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795045"
---
# <a name="variables-entity-sql"></a>Variables (Entity SQL)

## <a name="variable"></a>Variable  

 Una expresión de variable es una referencia a una expresión con nombre definida en el ámbito actual. Una referencia de variable debe ser un [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identificador válido, tal y como se define en [Identifiers](identifiers-entity-sql.md).  
  
 En el siguiente ejemplo se muestra el uso de una variable en la expresión. La `c` de la cláusula FROM es la definición de la variable. El uso de `c` en la cláusula SELECT representa la referencia a la variable.  
  
```sql  
select c
from LOB.customers as c  
```  
  
## <a name="see-also"></a>Vea también

- [Identificadores](identifiers-entity-sql.md)
- [Parámetros](parameters-entity-sql.md)
- [Información general sobre Entity SQL](entity-sql-overview.md)
