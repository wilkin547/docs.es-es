---
title: Parámetros (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 8d618edd-0988-4ff2-8263-ce59448af7a5
ms.openlocfilehash: e1bb633f7f7c7908a5f424991f20a5cd89aee5aa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150019"
---
# <a name="parameters-entity-sql"></a><span data-ttu-id="e2426-102">Parámetros (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e2426-102">Parameters (Entity SQL)</span></span>
<span data-ttu-id="e2426-103">Los parámetros son variables que se definen fuera de [!INCLUDE[esql](../../../../../../includes/esql-md.md)], normalmente a través de una API de enlace que se usa en un lenguaje host.</span><span class="sxs-lookup"><span data-stu-id="e2426-103">Parameters are variables that are defined outside [!INCLUDE[esql](../../../../../../includes/esql-md.md)], usually through a binding API that is used by a host language.</span></span> <span data-ttu-id="e2426-104">Cada parámetro tiene un nombre y un tipo.</span><span class="sxs-lookup"><span data-stu-id="e2426-104">Each parameter has a name and a type.</span></span> <span data-ttu-id="e2426-105">Los nombres de los parámetros se definen en expresiones de consulta con el símbolo (@) como prefijo.</span><span class="sxs-lookup"><span data-stu-id="e2426-105">Parameter names are defined in query expressions with the at (@) symbol as a prefix.</span></span> <span data-ttu-id="e2426-106">De esta forma se elimina su ambigüedad en los nombres de las propiedades o en otros nombres que se definen en la consulta.</span><span class="sxs-lookup"><span data-stu-id="e2426-106">This disambiguates them from the names of properties or other names that are defined in the query.</span></span>  
  
 <span data-ttu-id="e2426-107">La API de enlace de lenguaje host proporciona otras API para los parámetros de enlace.</span><span class="sxs-lookup"><span data-stu-id="e2426-107">The host-language binding API provides APIs for binding parameters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2426-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e2426-108">Example</span></span>  
  
```sql  
SELECT c
      FROM LOB.Customers AS c
      WHERE c.Name = @name  
```  
  
## <a name="see-also"></a><span data-ttu-id="e2426-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e2426-109">See also</span></span>

- [<span data-ttu-id="e2426-110">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="e2426-110">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="e2426-111">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="e2426-111">Entity SQL Overview</span></span>](entity-sql-overview.md)
