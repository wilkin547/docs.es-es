---
title: USING (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
ms.openlocfilehash: 6a5b374bc253cb2deb7a9e1de942c32d8e8bbfcf
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168030"
---
# <a name="using-entity-sql"></a><span data-ttu-id="a8a18-102">USING (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="a8a18-102">USING (Entity SQL)</span></span>
<span data-ttu-id="a8a18-103">Especifica espacios de nombres que se usan en una expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="a8a18-103">Specifies namespaces used in a query expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8a18-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a8a18-104">Syntax</span></span>  
  
```  
USING [ alias = ] namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="a8a18-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a8a18-105">Arguments</span></span>  
 `alias`  
 <span data-ttu-id="a8a18-106">Especifica un alias más breve con el que calificar un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="a8a18-106">Specifies a shorter alias to qualify a namespace with.</span></span>  
  
 `namespace`  
 <span data-ttu-id="a8a18-107">Cualquier espacio de nombres válido.</span><span class="sxs-lookup"><span data-stu-id="a8a18-107">Any valid namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8a18-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a8a18-108">Example</span></span>  
 <span data-ttu-id="a8a18-109">En la consulta de Entity SQL siguiente se usa el operador USING para especificar los espacios de nombres que se usan en la expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="a8a18-109">The following Entity SQL query uses the USING operator to specify namespaces used in a query expression.</span></span> <span data-ttu-id="a8a18-110">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="a8a18-110">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="a8a18-111">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="a8a18-111">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="a8a18-112">Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="a8a18-112">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
```  
using SqlServer; RAND()  
```  
  
## <a name="see-also"></a><span data-ttu-id="a8a18-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8a18-113">See also</span></span>

- [<span data-ttu-id="a8a18-114">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="a8a18-114">Namespaces</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md)
- [<span data-ttu-id="a8a18-115">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a8a18-115">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
