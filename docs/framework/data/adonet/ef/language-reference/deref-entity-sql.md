---
description: 'Más información acerca de: DEREF (Entity SQL)'
title: DEREF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4c78e833-b260-453d-9bf4-eb39857dd0fa
ms.openlocfilehash: 9d0f29123c1459c6eab21ea9cd860b5c9e77f591
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724731"
---
# <a name="deref-entity-sql"></a><span data-ttu-id="91f87-103">DEREF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="91f87-103">DEREF (Entity SQL)</span></span>

<span data-ttu-id="91f87-104">Desreferencia un valor de referencia y genera el resultado de dicha desreferenciación.</span><span class="sxs-lookup"><span data-stu-id="91f87-104">Dereferences a reference value and produces the result of that dereference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91f87-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="91f87-105">Syntax</span></span>  
  
```sql  
SELECT DEREF ( o.expression ) FROM Table AS o;
```  
  
## <a name="arguments"></a><span data-ttu-id="91f87-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="91f87-106">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="91f87-107">Expresión de consulta válida que devuelve una colección.</span><span class="sxs-lookup"><span data-stu-id="91f87-107">Any valid query expression that returns a collection.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="91f87-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="91f87-108">Return Value</span></span>  

 <span data-ttu-id="91f87-109">El valor de la entidad a la que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="91f87-109">The value of the entity that is referenced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91f87-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="91f87-110">Remarks</span></span>  

 <span data-ttu-id="91f87-111">El operador DEREF desreferencia un valor de referencia y genera el resultado de dicha desreferenciación.</span><span class="sxs-lookup"><span data-stu-id="91f87-111">The DEREF operator dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="91f87-112">Por ejemplo, si `r` es una referencia de tipo REF \<T> , `Deref(r)` es una expresión de tipo `T` que produce la entidad a la que hace referencia `r` .</span><span class="sxs-lookup"><span data-stu-id="91f87-112">For example, if `r` is a reference of type ref\<T>, `Deref(r)` is an expression of type `T` that yields the entity referenced by `r`.</span></span> <span data-ttu-id="91f87-113">Si el valor de referencia es NULL, o está pendiente (es decir, el destino de la referencia no existe), el resultado del operador DEREF es NULL.</span><span class="sxs-lookup"><span data-stu-id="91f87-113">If the reference value is null, or is dangling (that is, the target of the reference does not exist), the result of the DEREF operator is null.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91f87-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="91f87-114">Example</span></span>  

 <span data-ttu-id="91f87-115">La consulta [!INCLUDE[esql](../../../../../../includes/esql-md.md)] utiliza el operador DEREF para desreferenciar un valor de referencia y generar el resultado de dicha desreferenciación.</span><span class="sxs-lookup"><span data-stu-id="91f87-115">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the DEREF operator to dereference a reference value and produce the result of that dereference.</span></span> <span data-ttu-id="91f87-116">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="91f87-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="91f87-117">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="91f87-117">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="91f87-118">Siga el procedimiento descrito en [Cómo: ejecutar una consulta que devuelve resultados PrimitiveType](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="91f87-118">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="91f87-119">Pase la consulta siguiente como argumento al método ExecutePrimitiveTypeQuery:</span><span class="sxs-lookup"><span data-stu-id="91f87-119">Pass the following query as an argument to the ExecutePrimitiveTypeQuery method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#DEREF](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#deref)]  
  
## <a name="see-also"></a><span data-ttu-id="91f87-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="91f87-120">See also</span></span>

- [<span data-ttu-id="91f87-121">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="91f87-121">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="91f87-122">CLI</span><span class="sxs-lookup"><span data-stu-id="91f87-122">REF</span></span>](ref-entity-sql.md)
- [<span data-ttu-id="91f87-123">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="91f87-123">CREATEREF</span></span>](createref-entity-sql.md)
- [<span data-ttu-id="91f87-124">KEY</span><span class="sxs-lookup"><span data-stu-id="91f87-124">KEY</span></span>](key-entity-sql.md)
- [<span data-ttu-id="91f87-125">Tipos estructurados que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="91f87-125">Nullable Structured Types</span></span>](nullable-structured-types-entity-sql.md)
