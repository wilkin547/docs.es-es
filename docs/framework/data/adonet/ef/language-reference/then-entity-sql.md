---
title: THEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 54222642-23c6-4f61-9861-67caca53ac5f
ms.openlocfilehash: c64e440e8cd8f86706db69d923ba7085d0cb3b3a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248988"
---
# <a name="then-entity-sql"></a><span data-ttu-id="0beba-102">THEN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="0beba-102">THEN (Entity SQL)</span></span>
<span data-ttu-id="0beba-103">El resultado de una cláusula WHEN cuando se evalúa como `true`.</span><span class="sxs-lookup"><span data-stu-id="0beba-103">The result of a WHEN clause when it evaluates to `true`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0beba-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0beba-104">Syntax</span></span>  
  
```  
WHEN when_expression THEN then_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="0beba-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0beba-105">Arguments</span></span>  
 `when_expression`  
 <span data-ttu-id="0beba-106">Cualquier expresión Boolean válida.</span><span class="sxs-lookup"><span data-stu-id="0beba-106">Any valid Boolean expression.</span></span>  
  
 `then_expression`  
 <span data-ttu-id="0beba-107">Expresión de consulta válida que devuelve una colección.</span><span class="sxs-lookup"><span data-stu-id="0beba-107">Any valid query expression that returns a collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0beba-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0beba-108">Remarks</span></span>  
 <span data-ttu-id="0beba-109">Si `when_expression` se evalúa como el valor `true`, el resultado es la `then-expression`correspondiente.</span><span class="sxs-lookup"><span data-stu-id="0beba-109">If `when_expression` evaluates to the value `true`, the result is the corresponding `then-expression`.</span></span> <span data-ttu-id="0beba-110">Si no se cumple ninguna de las condiciones WHEN, se evalúa `else-expression` .</span><span class="sxs-lookup"><span data-stu-id="0beba-110">If none of the WHEN conditions are satisfied, the `else-expression` is evaluated.</span></span> <span data-ttu-id="0beba-111">Sin embargo, si no hay ninguna `else-expression`, el resultado es Null.</span><span class="sxs-lookup"><span data-stu-id="0beba-111">However, if there is no `else-expression`, the result is null.</span></span>  
  
 <span data-ttu-id="0beba-112">Para obtener un ejemplo, vea [Case](case-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="0beba-112">For an example, see [CASE](case-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0beba-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0beba-113">Example</span></span>  
 <span data-ttu-id="0beba-114">La siguiente consulta de Entity SQL usa la expresión CASE para evaluar un conjunto de expresiones `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="0beba-114">The following Entity SQL query uses the CASE expression to evaluate a set of `Boolean` expressions.</span></span> <span data-ttu-id="0beba-115">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="0beba-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="0beba-116">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="0beba-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="0beba-117">Siga el procedimiento descrito [en cómo: Ejecuta una consulta que devuelve resultados](../how-to-execute-a-query-that-returns-primitivetype-results.md)PrimitiveType.</span><span class="sxs-lookup"><span data-stu-id="0beba-117">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="0beba-118">Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="0beba-118">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## <a name="see-also"></a><span data-ttu-id="0beba-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="0beba-119">See also</span></span>

- [<span data-ttu-id="0beba-120">CASE</span><span class="sxs-lookup"><span data-stu-id="0beba-120">CASE</span></span>](case-entity-sql.md)
- [<span data-ttu-id="0beba-121">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="0beba-121">Entity SQL Reference</span></span>](entity-sql-reference.md)
