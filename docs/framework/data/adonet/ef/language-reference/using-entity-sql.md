---
title: USING (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: d1a47102c7057918c981b53f920afef09b20afad
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="using-entity-sql"></a><span data-ttu-id="f8228-102">USING (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="f8228-102">USING (Entity SQL)</span></span>
<span data-ttu-id="f8228-103">Especifica espacios de nombres que se usan en una expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="f8228-103">Specifies namespaces used in a query expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8228-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f8228-104">Syntax</span></span>  
  
```  
USING [ alias = ] namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="f8228-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="f8228-105">Arguments</span></span>  
 `alias`  
 <span data-ttu-id="f8228-106">Especifica un alias más breve con el que calificar un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="f8228-106">Specifies a shorter alias to qualify a namespace with.</span></span>  
  
 `namespace`  
 <span data-ttu-id="f8228-107">Cualquier espacio de nombres válido.</span><span class="sxs-lookup"><span data-stu-id="f8228-107">Any valid namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8228-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f8228-108">Example</span></span>  
 <span data-ttu-id="f8228-109">En la consulta de Entity SQL siguiente se usa el operador USING para especificar los espacios de nombres que se usan en la expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="f8228-109">The following Entity SQL query uses the USING operator to specify namespaces used in a query expression.</span></span> <span data-ttu-id="f8228-110">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="f8228-110">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="f8228-111">Siga el procedimiento de [Cómo: ejecutar una consulta que muestra los resultados PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="f8228-111">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="f8228-112">Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="f8228-112">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
```  
using SqlServer; RAND()  
```  
  
## <a name="see-also"></a><span data-ttu-id="f8228-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8228-113">See Also</span></span>  
 [<span data-ttu-id="f8228-114">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="f8228-114">Namespaces</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md)  
 [<span data-ttu-id="f8228-115">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="f8228-115">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
