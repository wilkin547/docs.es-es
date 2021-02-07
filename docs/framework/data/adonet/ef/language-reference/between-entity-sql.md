---
description: 'Más información acerca de: entre (Entity SQL)'
title: BETWEEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4dcdd754-ae01-4e78-bf28-8a117fb2b73e
ms.openlocfilehash: 35ac16e94f2e55f6a0f76591daf0f91f9708aa53
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697119"
---
# <a name="between-entity-sql"></a><span data-ttu-id="3ff80-103">BETWEEN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="3ff80-103">BETWEEN (Entity SQL)</span></span>

<span data-ttu-id="3ff80-104">Determina si el resultado de una expresión es un valor incluido en un intervalo especificado.</span><span class="sxs-lookup"><span data-stu-id="3ff80-104">Determines whether an expression results in a value in a specified range.</span></span> <span data-ttu-id="3ff80-105">La [!INCLUDE[esql](../../../../../../includes/esql-md.md)] expresión between tiene la misma funcionalidad que la expresión Transact-SQL between.</span><span class="sxs-lookup"><span data-stu-id="3ff80-105">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] BETWEEN expression has the same functionality as the Transact-SQL BETWEEN expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ff80-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3ff80-106">Syntax</span></span>  
  
```csharp  
expression [ NOT ] BETWEEN begin_expression AND end_expression
```  
  
## <a name="arguments"></a><span data-ttu-id="3ff80-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="3ff80-107">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="3ff80-108">Cualquier expresión válida que se va a probar en el intervalo definido por `begin_expression` y `end_expression`.</span><span class="sxs-lookup"><span data-stu-id="3ff80-108">Any valid expression to test for in the range defined by `begin_expression` and `end_expression`.</span></span> <span data-ttu-id="3ff80-109">`expression` debe ser del mismo tipo que `begin_expression` y `end_expression`.</span><span class="sxs-lookup"><span data-stu-id="3ff80-109">`expression` must be the same type as both `begin_expression` and `end_expression`.</span></span>  
  
 `begin_expression`  
 <span data-ttu-id="3ff80-110">Cualquier expresión válida.</span><span class="sxs-lookup"><span data-stu-id="3ff80-110">Any valid expression.</span></span> <span data-ttu-id="3ff80-111">`begin_expression` debe ser del mismo tipo que `expression` y `end_expression`.</span><span class="sxs-lookup"><span data-stu-id="3ff80-111">`begin_expression` must be the same type as both `expression` and `end_expression`.</span></span> <span data-ttu-id="3ff80-112">`begin_expression` debe ser menor que `end_expression`; de lo contrario, el valor devuelto se negará.</span><span class="sxs-lookup"><span data-stu-id="3ff80-112">`begin_expression` should be less than `end_expression`, else the return value will be negated.</span></span>  
  
 `end_expression`  
 <span data-ttu-id="3ff80-113">Cualquier expresión válida.</span><span class="sxs-lookup"><span data-stu-id="3ff80-113">Any valid expression.</span></span> <span data-ttu-id="3ff80-114">`end_expression` debe ser del mismo tipo que `expression` y `begin_expression`.</span><span class="sxs-lookup"><span data-stu-id="3ff80-114">`end_expression` must be the same type as both `expression` and `begin_expression`.</span></span>  
  
 <span data-ttu-id="3ff80-115">NOT</span><span class="sxs-lookup"><span data-stu-id="3ff80-115">NOT</span></span>  
 <span data-ttu-id="3ff80-116">Especifica que el resultado de BETWEEN se niega.</span><span class="sxs-lookup"><span data-stu-id="3ff80-116">Specifies that the result of BETWEEN be negated.</span></span>  
  
 <span data-ttu-id="3ff80-117">y</span><span class="sxs-lookup"><span data-stu-id="3ff80-117">AND</span></span>  
 <span data-ttu-id="3ff80-118">Actúa como un marcador de posición que indica que `expression` debe estar dentro del intervalo indicado por `begin_expression` y `end_expression`.</span><span class="sxs-lookup"><span data-stu-id="3ff80-118">Acts as a placeholder that indicates `expression` should be within the range indicated by `begin_expression` and `end_expression`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3ff80-119">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3ff80-119">Return Value</span></span>  

 <span data-ttu-id="3ff80-120">`true` si `expression` está dentro del intervalo indicado por `begin_expression` y `end_expression`; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="3ff80-120">`true` if `expression` is between the range indicated by `begin_expression` and `end_expression`; otherwise, `false`.</span></span> <span data-ttu-id="3ff80-121">Se devolverá `null` si `expression` es `null` o si `begin_expression` o `end_expression` es `null`.</span><span class="sxs-lookup"><span data-stu-id="3ff80-121">`null` will be returned if `expression` is `null` or if `begin_expression` or `end_expression` is `null`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ff80-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3ff80-122">Remarks</span></span>  

 <span data-ttu-id="3ff80-123">Para especificar un intervalo exclusivo, utilice los operadores mayor que (>) y menor que (<) en lugar de entre.</span><span class="sxs-lookup"><span data-stu-id="3ff80-123">To specify an exclusive range, use the greater than (>) and less than (<) operators instead of BETWEEN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ff80-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3ff80-124">Example</span></span>  

 <span data-ttu-id="3ff80-125">La consulta de Entity SQL siguiente utiliza el operador BETWEEN para determinar si el resultado de una expresión es un valor incluido en un intervalo especificado.</span><span class="sxs-lookup"><span data-stu-id="3ff80-125">The following Entity SQL query uses BETWEEN operator to determine whether an expression results in a value in a specified range.</span></span> <span data-ttu-id="3ff80-126">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="3ff80-126">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="3ff80-127">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="3ff80-127">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="3ff80-128">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="3ff80-128">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="3ff80-129">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="3ff80-129">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#BETWEEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#between)]  
  
## <a name="see-also"></a><span data-ttu-id="3ff80-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ff80-130">See also</span></span>

- [<span data-ttu-id="3ff80-131">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="3ff80-131">Entity SQL Reference</span></span>](entity-sql-reference.md)
