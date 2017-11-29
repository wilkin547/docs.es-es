---
title: DEREF (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4c78e833-b260-453d-9bf4-eb39857dd0fa
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 49ae645baccf877a8e9c0f80ac8827823b9d6c34
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="deref-entity-sql"></a><span data-ttu-id="80282-102">DEREF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="80282-102">DEREF (Entity SQL)</span></span>
<span data-ttu-id="80282-103">Desreferencia un valor de referencia y genera el resultado de dicha desreferenciación.</span><span class="sxs-lookup"><span data-stu-id="80282-103">Dereferences a reference value and produces the result of that dereference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80282-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="80282-104">Syntax</span></span>  
  
```  
SELECT DEREF ( o.expression ) from Table as o;  
```  
  
## <a name="arguments"></a><span data-ttu-id="80282-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="80282-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="80282-106">Expresión de consulta válida que devuelve una colección.</span><span class="sxs-lookup"><span data-stu-id="80282-106">Any valid query expression that returns a collection.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80282-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="80282-107">Return Value</span></span>  
 <span data-ttu-id="80282-108">El valor de la entidad a la que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="80282-108">The value of the entity that is referenced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80282-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="80282-109">Remarks</span></span>  
 <span data-ttu-id="80282-110">El operador DEREF desreferencia un valor de referencia y genera el resultado de dicha desreferenciación.</span><span class="sxs-lookup"><span data-stu-id="80282-110">The DEREF operator dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="80282-111">Por ejemplo, si `r` es una referencia de tipo ref\<T >, `Deref``(r)` es una expresión de tipo `T` que obtiene la entidad al que hace referencia `r`.</span><span class="sxs-lookup"><span data-stu-id="80282-111">For example, if `r` is a reference of type ref\<T>, `Deref``(r)` is an expression of type `T` that yields the entity referenced by `r`.</span></span> <span data-ttu-id="80282-112">Si el valor de referencia es NULL, o está pendiente (es decir, el destino de la referencia no existe), el resultado del operador DEREF es NULL.</span><span class="sxs-lookup"><span data-stu-id="80282-112">If the reference value is null, or is dangling (that is, the target of the reference does not exist), the result of the DEREF operator is null.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80282-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="80282-113">Example</span></span>  
 <span data-ttu-id="80282-114">La consulta [!INCLUDE[esql](../../../../../../includes/esql-md.md)] utiliza el operador DEREF para desreferenciar un valor de referencia y generar el resultado de dicha desreferenciación.</span><span class="sxs-lookup"><span data-stu-id="80282-114">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the DEREF operator to dereference a reference value and produce the result of that dereference.</span></span> <span data-ttu-id="80282-115">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="80282-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="80282-116">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="80282-116">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="80282-117">Siga el procedimiento de [Cómo: ejecutar una consulta que muestra los resultados PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="80282-117">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="80282-118">Pase la consulta siguiente como argumento al método ExecutePrimitiveTypeQuery:</span><span class="sxs-lookup"><span data-stu-id="80282-118">Pass the following query as an argument to the ExecutePrimitiveTypeQuery method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#DEREF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#deref)]  
  
## <a name="see-also"></a><span data-ttu-id="80282-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="80282-119">See Also</span></span>  
 [<span data-ttu-id="80282-120">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="80282-120">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="80282-121">REF</span><span class="sxs-lookup"><span data-stu-id="80282-121">REF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)  
 [<span data-ttu-id="80282-122">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="80282-122">CREATEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)  
 [<span data-ttu-id="80282-123">CLAVE</span><span class="sxs-lookup"><span data-stu-id="80282-123">KEY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)  
 [<span data-ttu-id="80282-124">Tipos estructurados que admiten valores null</span><span class="sxs-lookup"><span data-stu-id="80282-124">Nullable Structured Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)
