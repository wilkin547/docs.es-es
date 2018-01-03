---
title: Variables (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: fff24c4572fab483c701a93167c0f229d5111d61
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
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
