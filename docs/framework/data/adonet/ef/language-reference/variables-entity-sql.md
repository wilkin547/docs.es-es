---
title: Variables (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: bf6fa95e38d1eb5817fd67165b6993cbb0755fd1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61879780"
---
# <a name="variables-entity-sql"></a><span data-ttu-id="0f0b8-102">Variables (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="0f0b8-102">Variables (Entity SQL)</span></span>
## <a name="variable"></a><span data-ttu-id="0f0b8-103">Variable</span><span class="sxs-lookup"><span data-stu-id="0f0b8-103">Variable</span></span>  
 <span data-ttu-id="0f0b8-104">Una expresión de variable es una referencia a una expresión con nombre definida en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="0f0b8-104">A variable expression is a reference to a named expression defined in the current scope.</span></span> <span data-ttu-id="0f0b8-105">Una referencia de variable debe ser válido [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identificador, tal como se define en [identificadores](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="0f0b8-105">A variable reference must be a valid [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identifier, as defined in [Identifiers](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md).</span></span>  
  
 <span data-ttu-id="0f0b8-106">En el siguiente ejemplo se muestra el uso de una variable en la expresión.</span><span class="sxs-lookup"><span data-stu-id="0f0b8-106">The following example shows the use of a variable in the expression.</span></span> <span data-ttu-id="0f0b8-107">La `c` de la cláusula FROM es la definición de la variable.</span><span class="sxs-lookup"><span data-stu-id="0f0b8-107">The `c` in the FROM clause is the definition of the variable.</span></span> <span data-ttu-id="0f0b8-108">El uso de `c` en la cláusula SELECT representa la referencia a la variable.</span><span class="sxs-lookup"><span data-stu-id="0f0b8-108">The use of `c` in the SELECT clause represents the variable reference.</span></span>  
  
```  
select c   
from LOB.customers as c  
```  
  
## <a name="see-also"></a><span data-ttu-id="0f0b8-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f0b8-109">See also</span></span>

- [<span data-ttu-id="0f0b8-110">Identificadores</span><span class="sxs-lookup"><span data-stu-id="0f0b8-110">Identifiers</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)
- [<span data-ttu-id="0f0b8-111">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0f0b8-111">Parameters</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md)
- [<span data-ttu-id="0f0b8-112">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="0f0b8-112">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
