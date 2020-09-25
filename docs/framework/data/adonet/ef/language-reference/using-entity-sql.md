---
title: USING (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
ms.openlocfilehash: bdab81ed8acae5e757de0a669922dc79d0303ee4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203597"
---
# <a name="using-entity-sql"></a><span data-ttu-id="1673d-102">USING (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="1673d-102">USING (Entity SQL)</span></span>

<span data-ttu-id="1673d-103">Especifica espacios de nombres que se usan en una expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="1673d-103">Specifies namespaces used in a query expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1673d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1673d-104">Syntax</span></span>  
  
```sql  
USING [ alias = ] namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="1673d-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="1673d-105">Arguments</span></span>  

 `alias`  
 <span data-ttu-id="1673d-106">Especifica un alias más breve con el que calificar un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="1673d-106">Specifies a shorter alias to qualify a namespace with.</span></span>  
  
 `namespace`  
 <span data-ttu-id="1673d-107">Cualquier espacio de nombres válido.</span><span class="sxs-lookup"><span data-stu-id="1673d-107">Any valid namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1673d-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1673d-108">Example</span></span>  

 <span data-ttu-id="1673d-109">En la consulta de Entity SQL siguiente se usa el operador USING para especificar los espacios de nombres que se usan en la expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="1673d-109">The following Entity SQL query uses the USING operator to specify namespaces used in a query expression.</span></span> <span data-ttu-id="1673d-110">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="1673d-110">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="1673d-111">Siga el procedimiento descrito en [Cómo: ejecutar una consulta que devuelve resultados PrimitiveType](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="1673d-111">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="1673d-112">Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="1673d-112">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
```csharp
using SqlServer; RAND()  
```  
  
## <a name="see-also"></a><span data-ttu-id="1673d-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1673d-113">See also</span></span>

- [<span data-ttu-id="1673d-114">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="1673d-114">Namespaces</span></span>](namespaces-entity-sql.md)
- [<span data-ttu-id="1673d-115">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="1673d-115">Entity SQL Reference</span></span>](entity-sql-reference.md)
