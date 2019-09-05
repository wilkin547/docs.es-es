---
title: Variables (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: 5be9c80c2fce877f179d79f6b2c22f11e31e65a0
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248688"
---
# <a name="variables-entity-sql"></a><span data-ttu-id="d8142-102">Variables (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d8142-102">Variables (Entity SQL)</span></span>
## <a name="variable"></a><span data-ttu-id="d8142-103">Variable</span><span class="sxs-lookup"><span data-stu-id="d8142-103">Variable</span></span>  
 <span data-ttu-id="d8142-104">Una expresión de variable es una referencia a una expresión con nombre definida en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="d8142-104">A variable expression is a reference to a named expression defined in the current scope.</span></span> <span data-ttu-id="d8142-105">Una referencia de variable debe ser un [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identificador válido, tal y como se define en [Identifiers](identifiers-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="d8142-105">A variable reference must be a valid [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identifier, as defined in [Identifiers](identifiers-entity-sql.md).</span></span>  
  
 <span data-ttu-id="d8142-106">En el siguiente ejemplo se muestra el uso de una variable en la expresión.</span><span class="sxs-lookup"><span data-stu-id="d8142-106">The following example shows the use of a variable in the expression.</span></span> <span data-ttu-id="d8142-107">La `c` de la cláusula FROM es la definición de la variable.</span><span class="sxs-lookup"><span data-stu-id="d8142-107">The `c` in the FROM clause is the definition of the variable.</span></span> <span data-ttu-id="d8142-108">El uso de `c` en la cláusula SELECT representa la referencia a la variable.</span><span class="sxs-lookup"><span data-stu-id="d8142-108">The use of `c` in the SELECT clause represents the variable reference.</span></span>  
  
```  
select c   
from LOB.customers as c  
```  
  
## <a name="see-also"></a><span data-ttu-id="d8142-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="d8142-109">See also</span></span>

- [<span data-ttu-id="d8142-110">Identificadores</span><span class="sxs-lookup"><span data-stu-id="d8142-110">Identifiers</span></span>](identifiers-entity-sql.md)
- [<span data-ttu-id="d8142-111">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d8142-111">Parameters</span></span>](parameters-entity-sql.md)
- [<span data-ttu-id="d8142-112">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="d8142-112">Entity SQL Overview</span></span>](entity-sql-overview.md)
