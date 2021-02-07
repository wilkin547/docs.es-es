---
description: 'Más información acerca de: IN (Entity SQL)'
title: IN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 51662950-ee01-4857-b7b9-311dd8515966
ms.openlocfilehash: 234ed15430e44d12d4ca7c98fcb4a7bc03d117f9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99748601"
---
# <a name="in-entity-sql"></a><span data-ttu-id="c5675-103">IN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c5675-103">IN (Entity SQL)</span></span>

<span data-ttu-id="c5675-104">Determina si un valor determinado coincide con algún valor de una colección.</span><span class="sxs-lookup"><span data-stu-id="c5675-104">Determines whether a value matches any value in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5675-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c5675-105">Syntax</span></span>  
  
```sql  
value [ NOT ] IN expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="c5675-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c5675-106">Arguments</span></span>  

 `value`  
 <span data-ttu-id="c5675-107">Expresión válida que devuelve el valor que hay que buscar.</span><span class="sxs-lookup"><span data-stu-id="c5675-107">Any valid expression that returns the value to match.</span></span>  
  
 <span data-ttu-id="c5675-108">[ NOT ]</span><span class="sxs-lookup"><span data-stu-id="c5675-108">[ NOT ]</span></span>  
 <span data-ttu-id="c5675-109">Especifica que el resultado `Boolean` de IN se niega.</span><span class="sxs-lookup"><span data-stu-id="c5675-109">Specifies that the `Boolean` result of IN be negated.</span></span>  
  
 `expression`  
 <span data-ttu-id="c5675-110">Expresión válida que devuelve la colección en la que hay que buscar una coincidencia.</span><span class="sxs-lookup"><span data-stu-id="c5675-110">Any valid expression that returns the collection to test for a match.</span></span> <span data-ttu-id="c5675-111">Todas las expresiones deben ser del mismo tipo que `value`o de un tipo base común o derivado.</span><span class="sxs-lookup"><span data-stu-id="c5675-111">All expressions must be of the same type or of a common base or derived type as `value`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c5675-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c5675-112">Return Value</span></span>  

 <span data-ttu-id="c5675-113">`true` si el valor se encuentra en la colección; Null si el valor o la colección son Null; `false`, en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="c5675-113">`true` if the value is found in the collection; null if the value is null or the collection is null; otherwise, `false`.</span></span> <span data-ttu-id="c5675-114">El uso de NOT IN niega el resultado de IN.</span><span class="sxs-lookup"><span data-stu-id="c5675-114">Using NOT IN negates the results of IN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5675-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5675-115">Example</span></span>  

 <span data-ttu-id="c5675-116">La siguiente consulta de Entity SQL usa el operador IN para determinar si un valor coincide con algún valor de una colección.</span><span class="sxs-lookup"><span data-stu-id="c5675-116">The following Entity SQL query uses the IN operator to determine whether a value matches any value in a collection.</span></span> <span data-ttu-id="c5675-117">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="c5675-117">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="c5675-118">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="c5675-118">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="c5675-119">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="c5675-119">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="c5675-120">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="c5675-120">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#IN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#in)]  
  
## <a name="see-also"></a><span data-ttu-id="c5675-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5675-121">See also</span></span>

- [<span data-ttu-id="c5675-122">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="c5675-122">Entity SQL Reference</span></span>](entity-sql-reference.md)
