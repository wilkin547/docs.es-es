---
title: Variables (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: f271ffc31875e7d94a27f4752b71bfe508fcb620
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="variables-entity-sql"></a>Variables (Entity SQL)
## <a name="variable"></a>Variable  
 Una expresión de variable es una referencia a una expresión con nombre definida en el ámbito actual. Una referencia de variable debe ser válido [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identificador, como se define en [identificadores](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md).  
  
 En el siguiente ejemplo se muestra el uso de una variable en la expresión. La `c` de la cláusula FROM es la definición de la variable. El uso de `c` en la cláusula SELECT representa la referencia a la variable.  
  
```  
select c   
from LOB.customers as c  
```  
  
## <a name="see-also"></a>Vea también  
 [Identificadores](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)  
 [Parámetros](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md)  
 [Información general sobre Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
