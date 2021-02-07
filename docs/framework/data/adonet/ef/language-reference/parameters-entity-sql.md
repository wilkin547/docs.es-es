---
description: 'Más información acerca de: parámetros (Entity SQL)'
title: Parámetros (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 8d618edd-0988-4ff2-8263-ce59448af7a5
ms.openlocfilehash: 77b1e6ee95b5d367fec8d99345bbb416c2b9787d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724536"
---
# <a name="parameters-entity-sql"></a><span data-ttu-id="ccaad-103">Parámetros (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ccaad-103">Parameters (Entity SQL)</span></span>

<span data-ttu-id="ccaad-104">Los parámetros son variables que se definen fuera de [!INCLUDE[esql](../../../../../../includes/esql-md.md)], normalmente a través de una API de enlace que se usa en un lenguaje host.</span><span class="sxs-lookup"><span data-stu-id="ccaad-104">Parameters are variables that are defined outside [!INCLUDE[esql](../../../../../../includes/esql-md.md)], usually through a binding API that is used by a host language.</span></span> <span data-ttu-id="ccaad-105">Cada parámetro tiene un nombre y un tipo.</span><span class="sxs-lookup"><span data-stu-id="ccaad-105">Each parameter has a name and a type.</span></span> <span data-ttu-id="ccaad-106">Los nombres de los parámetros se definen en expresiones de consulta con el símbolo (@) como prefijo.</span><span class="sxs-lookup"><span data-stu-id="ccaad-106">Parameter names are defined in query expressions with the at (@) symbol as a prefix.</span></span> <span data-ttu-id="ccaad-107">De esta forma se elimina su ambigüedad en los nombres de las propiedades o en otros nombres que se definen en la consulta.</span><span class="sxs-lookup"><span data-stu-id="ccaad-107">This disambiguates them from the names of properties or other names that are defined in the query.</span></span>  
  
 <span data-ttu-id="ccaad-108">La API de enlace de lenguaje host proporciona otras API para los parámetros de enlace.</span><span class="sxs-lookup"><span data-stu-id="ccaad-108">The host-language binding API provides APIs for binding parameters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ccaad-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ccaad-109">Example</span></span>  
  
```sql  
SELECT c
      FROM LOB.Customers AS c
      WHERE c.Name = @name  
```  
  
## <a name="see-also"></a><span data-ttu-id="ccaad-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="ccaad-110">See also</span></span>

- [<span data-ttu-id="ccaad-111">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="ccaad-111">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="ccaad-112">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="ccaad-112">Entity SQL Overview</span></span>](entity-sql-overview.md)
