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
# <a name="variables-entity-sql"></a><span data-ttu-id="1bc2d-103">Variables (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="1bc2d-103">Variables (Entity SQL)</span></span>

## <a name="variable"></a><span data-ttu-id="1bc2d-104">Variable</span><span class="sxs-lookup"><span data-stu-id="1bc2d-104">Variable</span></span>  

 <span data-ttu-id="1bc2d-105">Una expresión de variable es una referencia a una expresión con nombre definida en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="1bc2d-105">A variable expression is a reference to a named expression defined in the current scope.</span></span> <span data-ttu-id="1bc2d-106">Una referencia de variable debe ser un [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identificador válido, tal y como se define en [Identifiers](identifiers-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="1bc2d-106">A variable reference must be a valid [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identifier, as defined in [Identifiers](identifiers-entity-sql.md).</span></span>  
  
 <span data-ttu-id="1bc2d-107">En el siguiente ejemplo se muestra el uso de una variable en la expresión.</span><span class="sxs-lookup"><span data-stu-id="1bc2d-107">The following example shows the use of a variable in the expression.</span></span> <span data-ttu-id="1bc2d-108">La `c` de la cláusula FROM es la definición de la variable.</span><span class="sxs-lookup"><span data-stu-id="1bc2d-108">The `c` in the FROM clause is the definition of the variable.</span></span> <span data-ttu-id="1bc2d-109">El uso de `c` en la cláusula SELECT representa la referencia a la variable.</span><span class="sxs-lookup"><span data-stu-id="1bc2d-109">The use of `c` in the SELECT clause represents the variable reference.</span></span>  
  
```sql  
select c
from LOB.customers as c  
```  
  
## <a name="see-also"></a><span data-ttu-id="1bc2d-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="1bc2d-110">See also</span></span>

- [<span data-ttu-id="1bc2d-111">Identificadores</span><span class="sxs-lookup"><span data-stu-id="1bc2d-111">Identifiers</span></span>](identifiers-entity-sql.md)
- [<span data-ttu-id="1bc2d-112">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1bc2d-112">Parameters</span></span>](parameters-entity-sql.md)
- [<span data-ttu-id="1bc2d-113">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="1bc2d-113">Entity SQL Overview</span></span>](entity-sql-overview.md)
