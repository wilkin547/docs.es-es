---
title: USING (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
ms.openlocfilehash: 0bcd4a2140a04fa0ecbfa7eee450ed029f278286
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319205"
---
# <a name="using-entity-sql"></a><span data-ttu-id="f5172-102">USING (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="f5172-102">USING (Entity SQL)</span></span>
<span data-ttu-id="f5172-103">Especifica espacios de nombres que se usan en una expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="f5172-103">Specifies namespaces used in a query expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5172-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f5172-104">Syntax</span></span>  
  
```sql  
USING [ alias = ] namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="f5172-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="f5172-105">Arguments</span></span>  
 `alias`  
 <span data-ttu-id="f5172-106">Especifica un alias más breve con el que calificar un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="f5172-106">Specifies a shorter alias to qualify a namespace with.</span></span>  
  
 `namespace`  
 <span data-ttu-id="f5172-107">Cualquier espacio de nombres válido.</span><span class="sxs-lookup"><span data-stu-id="f5172-107">Any valid namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5172-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f5172-108">Example</span></span>  
 <span data-ttu-id="f5172-109">En la consulta de Entity SQL siguiente se usa el operador USING para especificar los espacios de nombres que se usan en la expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="f5172-109">The following Entity SQL query uses the USING operator to specify namespaces used in a query expression.</span></span> <span data-ttu-id="f5172-110">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="f5172-110">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="f5172-111">Siga el procedimiento descrito en [Cómo: ejecutar una consulta que devuelve resultados PrimitiveType](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="f5172-111">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="f5172-112">Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="f5172-112">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
```csharp
using SqlServer; RAND()  
```  
  
## <a name="see-also"></a><span data-ttu-id="f5172-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5172-113">See also</span></span>

- [<span data-ttu-id="f5172-114">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="f5172-114">Namespaces</span></span>](namespaces-entity-sql.md)
- [<span data-ttu-id="f5172-115">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="f5172-115">Entity SQL Reference</span></span>](entity-sql-reference.md)
