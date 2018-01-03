---
title: WHERE (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 2ad170500770bc370eb67a04ab29d0c9f9dcaabd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="where-entity-sql"></a><span data-ttu-id="02eab-102">WHERE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="02eab-102">WHERE (Entity SQL)</span></span>
<span data-ttu-id="02eab-103">La cláusula WHERE se aplica directamente después del [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md) cláusula.</span><span class="sxs-lookup"><span data-stu-id="02eab-103">The WHERE clause is applied directly after the [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md) clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02eab-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="02eab-104">Syntax</span></span>  
  
```  
[ WHERE expression ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="02eab-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="02eab-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="02eab-106">Tipo Boolean.</span><span class="sxs-lookup"><span data-stu-id="02eab-106">A Boolean type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02eab-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="02eab-107">Remarks</span></span>  
 <span data-ttu-id="02eab-108">La cláusula WHERE tiene la misma semántica que la descrita para [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02eab-108">The WHERE clause has the same semantics as described for [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="02eab-109">Restringe los objetos generados por la expresión de consulta limitando los elementos de las colecciones de origen a los que cumplen la condición.</span><span class="sxs-lookup"><span data-stu-id="02eab-109">It restricts the objects produced by the query expression by limiting the elements of the source collections to those that pass the condition.</span></span>  
  
```  
select c from cs as c where e  
```  
  
 <span data-ttu-id="02eab-110">La expresión `e` debe tener el tipo Boolean.</span><span class="sxs-lookup"><span data-stu-id="02eab-110">The expression `e` must have the type Boolean.</span></span>  
  
 <span data-ttu-id="02eab-111">La cláusula WHERE se aplica directamente después de la cláusula FROM y antes de que tenga lugar cualquier agrupación, ordenación o proyección.</span><span class="sxs-lookup"><span data-stu-id="02eab-111">The WHERE clause is applied directly after the FROM clause and before any grouping, ordering, or projection takes place.</span></span> <span data-ttu-id="02eab-112">Todos los nombres de elemento definidos en la cláusula FROM son visibles para la expresión de la cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="02eab-112">All element names defined in the FROM clause are visible to the expression of the WHERE clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02eab-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="02eab-113">See Also</span></span>  
 [<span data-ttu-id="02eab-114">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="02eab-114">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="02eab-115">Expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="02eab-115">Query Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
