---
description: 'Más información acerca de: uso de (Entity SQL)'
title: USING (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
ms.openlocfilehash: 084ab56f25041377dd6a0a35dd743122f482eeba
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795058"
---
# <a name="using-entity-sql"></a><span data-ttu-id="11b1e-103">USING (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="11b1e-103">USING (Entity SQL)</span></span>

<span data-ttu-id="11b1e-104">Especifica espacios de nombres que se usan en una expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="11b1e-104">Specifies namespaces used in a query expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11b1e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="11b1e-105">Syntax</span></span>  
  
```sql  
USING [ alias = ] namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="11b1e-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="11b1e-106">Arguments</span></span>  

 `alias`  
 <span data-ttu-id="11b1e-107">Especifica un alias más breve con el que calificar un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="11b1e-107">Specifies a shorter alias to qualify a namespace with.</span></span>  
  
 `namespace`  
 <span data-ttu-id="11b1e-108">Cualquier espacio de nombres válido.</span><span class="sxs-lookup"><span data-stu-id="11b1e-108">Any valid namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="11b1e-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="11b1e-109">Example</span></span>  

 <span data-ttu-id="11b1e-110">En la consulta de Entity SQL siguiente se usa el operador USING para especificar los espacios de nombres que se usan en la expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="11b1e-110">The following Entity SQL query uses the USING operator to specify namespaces used in a query expression.</span></span> <span data-ttu-id="11b1e-111">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="11b1e-111">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="11b1e-112">Siga el procedimiento descrito en [Cómo: ejecutar una consulta que devuelve resultados PrimitiveType](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="11b1e-112">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="11b1e-113">Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="11b1e-113">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
```csharp
using SqlServer; RAND()  
```  
  
## <a name="see-also"></a><span data-ttu-id="11b1e-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="11b1e-114">See also</span></span>

- [<span data-ttu-id="11b1e-115">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="11b1e-115">Namespaces</span></span>](namespaces-entity-sql.md)
- [<span data-ttu-id="11b1e-116">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="11b1e-116">Entity SQL Reference</span></span>](entity-sql-reference.md)
