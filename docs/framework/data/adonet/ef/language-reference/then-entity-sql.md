---
description: 'Más información acerca de: después (Entity SQL)'
title: THEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 54222642-23c6-4f61-9861-67caca53ac5f
ms.openlocfilehash: e1f0657cfef3786832f489434fd8fc0342e8687b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99673471"
---
# <a name="then-entity-sql"></a><span data-ttu-id="1cb4a-103">THEN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="1cb4a-103">THEN (Entity SQL)</span></span>

<span data-ttu-id="1cb4a-104">El resultado de una cláusula WHEN cuando se evalúa como `true`.</span><span class="sxs-lookup"><span data-stu-id="1cb4a-104">The result of a WHEN clause when it evaluates to `true`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cb4a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1cb4a-105">Syntax</span></span>  
  
```sql  
WHEN when_expression THEN then_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="1cb4a-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="1cb4a-106">Arguments</span></span>  

 `when_expression`  
 <span data-ttu-id="1cb4a-107">Cualquier expresión Boolean válida.</span><span class="sxs-lookup"><span data-stu-id="1cb4a-107">Any valid Boolean expression.</span></span>  
  
 `then_expression`  
 <span data-ttu-id="1cb4a-108">Expresión de consulta válida que devuelve una colección.</span><span class="sxs-lookup"><span data-stu-id="1cb4a-108">Any valid query expression that returns a collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1cb4a-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1cb4a-109">Remarks</span></span>  

 <span data-ttu-id="1cb4a-110">Si `when_expression` se evalúa como el valor `true`, el resultado es la `then-expression`correspondiente.</span><span class="sxs-lookup"><span data-stu-id="1cb4a-110">If `when_expression` evaluates to the value `true`, the result is the corresponding `then-expression`.</span></span> <span data-ttu-id="1cb4a-111">Si no se cumple ninguna de las condiciones WHEN, se evalúa `else-expression` .</span><span class="sxs-lookup"><span data-stu-id="1cb4a-111">If none of the WHEN conditions are satisfied, the `else-expression` is evaluated.</span></span> <span data-ttu-id="1cb4a-112">Sin embargo, si no hay ninguna `else-expression`, el resultado es Null.</span><span class="sxs-lookup"><span data-stu-id="1cb4a-112">However, if there is no `else-expression`, the result is null.</span></span>  
  
 <span data-ttu-id="1cb4a-113">Para obtener un ejemplo, vea [Case](case-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="1cb4a-113">For an example, see [CASE](case-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1cb4a-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1cb4a-114">Example</span></span>  

 <span data-ttu-id="1cb4a-115">La siguiente consulta de Entity SQL usa la expresión CASE para evaluar un conjunto de expresiones `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="1cb4a-115">The following Entity SQL query uses the CASE expression to evaluate a set of `Boolean` expressions.</span></span> <span data-ttu-id="1cb4a-116">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="1cb4a-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="1cb4a-117">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="1cb4a-117">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="1cb4a-118">Siga el procedimiento descrito en [Cómo: ejecutar una consulta que devuelve resultados PrimitiveType](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="1cb4a-118">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="1cb4a-119">Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="1cb4a-119">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#CASE_WHEN_THEN_ELSE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#case_when_then_else)]  
  
## <a name="see-also"></a><span data-ttu-id="1cb4a-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="1cb4a-120">See also</span></span>

- [<span data-ttu-id="1cb4a-121">CASE</span><span class="sxs-lookup"><span data-stu-id="1cb4a-121">CASE</span></span>](case-entity-sql.md)
- [<span data-ttu-id="1cb4a-122">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="1cb4a-122">Entity SQL Reference</span></span>](entity-sql-reference.md)
