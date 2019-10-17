---
title: Variables (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: bb8e6ebe81dacc7ec0f45fdde65b9c18cfd76789
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319201"
---
# <a name="variables-entity-sql"></a><span data-ttu-id="bbb55-102">Variables (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="bbb55-102">Variables (Entity SQL)</span></span>
## <a name="variable"></a><span data-ttu-id="bbb55-103">Variable</span><span class="sxs-lookup"><span data-stu-id="bbb55-103">Variable</span></span>  
 <span data-ttu-id="bbb55-104">Una expresión de variable es una referencia a una expresión con nombre definida en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="bbb55-104">A variable expression is a reference to a named expression defined in the current scope.</span></span> <span data-ttu-id="bbb55-105">Una referencia de variable debe ser un identificador [!INCLUDE[esql](../../../../../../includes/esql-md.md)] válido, tal y como se define en [Identifiers](identifiers-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="bbb55-105">A variable reference must be a valid [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identifier, as defined in [Identifiers](identifiers-entity-sql.md).</span></span>  
  
 <span data-ttu-id="bbb55-106">En el siguiente ejemplo se muestra el uso de una variable en la expresión.</span><span class="sxs-lookup"><span data-stu-id="bbb55-106">The following example shows the use of a variable in the expression.</span></span> <span data-ttu-id="bbb55-107">La `c` de la cláusula FROM es la definición de la variable.</span><span class="sxs-lookup"><span data-stu-id="bbb55-107">The `c` in the FROM clause is the definition of the variable.</span></span> <span data-ttu-id="bbb55-108">El uso de `c` en la cláusula SELECT representa la referencia a la variable.</span><span class="sxs-lookup"><span data-stu-id="bbb55-108">The use of `c` in the SELECT clause represents the variable reference.</span></span>  
  
```sql  
select c   
from LOB.customers as c  
```  
  
## <a name="see-also"></a><span data-ttu-id="bbb55-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="bbb55-109">See also</span></span>

- [<span data-ttu-id="bbb55-110">Identificadores</span><span class="sxs-lookup"><span data-stu-id="bbb55-110">Identifiers</span></span>](identifiers-entity-sql.md)
- [<span data-ttu-id="bbb55-111">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bbb55-111">Parameters</span></span>](parameters-entity-sql.md)
- [<span data-ttu-id="bbb55-112">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="bbb55-112">Entity SQL Overview</span></span>](entity-sql-overview.md)
