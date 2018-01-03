---
title: BETWEEN (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4dcdd754-ae01-4e78-bf28-8a117fb2b73e
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 06008847a564d91d92a596978b90b040b6c508f9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="between-entity-sql"></a><span data-ttu-id="b54af-102">BETWEEN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b54af-102">BETWEEN (Entity SQL)</span></span>
<span data-ttu-id="b54af-103">Determina si el resultado de una expresión es un valor incluido en un intervalo especificado.</span><span class="sxs-lookup"><span data-stu-id="b54af-103">Determines whether an expression results in a value in a specified range.</span></span> <span data-ttu-id="b54af-104">El [!INCLUDE[esql](../../../../../../includes/esql-md.md)] expresión BETWEEN tiene la misma funcionalidad que la expresión BETWEEN de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="b54af-104">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] BETWEEN expression has the same functionality as the Transact-SQL BETWEEN expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b54af-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b54af-105">Syntax</span></span>  
  
```  
expression [ NOT ] BETWEEN begin_expression AND end_expression    
```  
  
## <a name="arguments"></a><span data-ttu-id="b54af-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b54af-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="b54af-107">Cualquier expresión válida que se va a probar en el intervalo definido por `begin_expression` y `end_expression`.</span><span class="sxs-lookup"><span data-stu-id="b54af-107">Any valid expression to test for in the range defined by `begin_expression` and `end_expression`.</span></span> <span data-ttu-id="b54af-108">`expression` debe ser del mismo tipo que `begin_expression` y `end_expression`.</span><span class="sxs-lookup"><span data-stu-id="b54af-108">`expression` must be the same type as both `begin_expression` and `end_expression`.</span></span>  
  
 `begin_expression`  
 <span data-ttu-id="b54af-109">Cualquier expresión válida.</span><span class="sxs-lookup"><span data-stu-id="b54af-109">Any valid expression.</span></span> <span data-ttu-id="b54af-110">`begin_expression` debe ser del mismo tipo que `expression` y `end_expression`.</span><span class="sxs-lookup"><span data-stu-id="b54af-110">`begin_expression` must be the same type as both `expression` and `end_expression`.</span></span> <span data-ttu-id="b54af-111">`begin_expression` debe ser menor que `end_expression`; de lo contrario, el valor devuelto se negará.</span><span class="sxs-lookup"><span data-stu-id="b54af-111">`begin_expression` should be less than `end_expression`, else the return value will be negated.</span></span>  
  
 `end_expression`  
 <span data-ttu-id="b54af-112">Cualquier expresión válida.</span><span class="sxs-lookup"><span data-stu-id="b54af-112">Any valid expression.</span></span> <span data-ttu-id="b54af-113">`end_expression` debe ser del mismo tipo que `expression` y `begin_expression`.</span><span class="sxs-lookup"><span data-stu-id="b54af-113">`end_expression` must be the same type as both `expression` and `begin_expression`.</span></span>  
  
 <span data-ttu-id="b54af-114">NOT</span><span class="sxs-lookup"><span data-stu-id="b54af-114">NOT</span></span>  
 <span data-ttu-id="b54af-115">Especifica que el resultado de BETWEEN se niega.</span><span class="sxs-lookup"><span data-stu-id="b54af-115">Specifies that the result of BETWEEN be negated.</span></span>  
  
 <span data-ttu-id="b54af-116">AND</span><span class="sxs-lookup"><span data-stu-id="b54af-116">AND</span></span>  
 <span data-ttu-id="b54af-117">Actúa como un marcador de posición que indica que `expression` debe estar dentro del intervalo indicado por `begin_expression` y `end_expression`.</span><span class="sxs-lookup"><span data-stu-id="b54af-117">Acts as a placeholder that indicates `expression` should be within the range indicated by `begin_expression` and `end_expression`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b54af-118">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b54af-118">Return Value</span></span>  
 <span data-ttu-id="b54af-119">`true` si `expression` está dentro del intervalo indicado por `begin_expression` y `end_expression`; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="b54af-119">`true` if `expression` is between the range indicated by `begin_expression` and `end_expression`; otherwise, `false`.</span></span> <span data-ttu-id="b54af-120">Se devolverá `null` si `expression` es `null` o si `begin_expression` o `end_expression` es `null`.</span><span class="sxs-lookup"><span data-stu-id="b54af-120">`null` will be returned if `expression` is `null` or if `begin_expression` or `end_expression` is `null`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b54af-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b54af-121">Remarks</span></span>  
 <span data-ttu-id="b54af-122">Para especificar un intervalo exclusivo, utilice los operadores mayor que (>) y menor que (<) en lugar de BETWEEN.</span><span class="sxs-lookup"><span data-stu-id="b54af-122">To specify an exclusive range, use the greater than (>) and less than (<) operators instead of BETWEEN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b54af-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b54af-123">Example</span></span>  
 <span data-ttu-id="b54af-124">La consulta de Entity SQL siguiente utiliza el operador BETWEEN para determinar si el resultado de una expresión es un valor incluido en un intervalo especificado.</span><span class="sxs-lookup"><span data-stu-id="b54af-124">The following Entity SQL query uses BETWEEN operator to determine whether an expression results in a value in a specified range.</span></span> <span data-ttu-id="b54af-125">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="b54af-125">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="b54af-126">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="b54af-126">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="b54af-127">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="b54af-127">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="b54af-128">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="b54af-128">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#BETWEEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#between)]  
  
## <a name="see-also"></a><span data-ttu-id="b54af-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="b54af-129">See Also</span></span>  
 [<span data-ttu-id="b54af-130">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="b54af-130">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
