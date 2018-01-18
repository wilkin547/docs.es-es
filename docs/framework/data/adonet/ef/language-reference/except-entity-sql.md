---
title: EXCEPT (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 69cc23e5-3f8f-4b49-b20e-2f84ff11c80d
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 546503d3fc51c863779c26f363721bf81be054b9
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="except-entity-sql"></a><span data-ttu-id="d5601-102">EXCEPT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d5601-102">EXCEPT (Entity SQL)</span></span>
<span data-ttu-id="d5601-103">Devuelve una colección de los valores distintos de la expresión de consulta situada a la izquierda del operando EXCEPT, que tampoco se devuelven en la expresión de consulta situada a la derecha del operando EXCEPT.</span><span class="sxs-lookup"><span data-stu-id="d5601-103">Returns a collection of any distinct values from the query expression to the left of the EXCEPT operand that are not also returned from the query expression to the right of the EXCEPT operand.</span></span> <span data-ttu-id="d5601-104">Todas las expresiones deben ser del mismo tipo que `expression`o de un tipo base común o derivado.</span><span class="sxs-lookup"><span data-stu-id="d5601-104">All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5601-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d5601-105">Syntax</span></span>  
  
```  
expression EXCEPT expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="d5601-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d5601-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="d5601-107">Cualquier expresión de consulta válida que devuelva una colección para comparar con la colección que devuelve otra expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="d5601-107">Any valid query expression that returns a collection to compare with the collection returned from another query expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d5601-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d5601-108">Return Value</span></span>  
 <span data-ttu-id="d5601-109">Colección del mismo tipo que `expression`o de un tipo base común o derivado.</span><span class="sxs-lookup"><span data-stu-id="d5601-109">A collection of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5601-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d5601-110">Remarks</span></span>  
 <span data-ttu-id="d5601-111">EXCEPT es uno de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d5601-111">EXCEPT is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="d5601-112">Todos los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se evalúan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="d5601-112">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="d5601-113">En la tabla siguiente se muestra la prioridad de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d5601-113">The following table shows the precedence of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
|<span data-ttu-id="d5601-114">Precedencia</span><span class="sxs-lookup"><span data-stu-id="d5601-114">Precedence</span></span>|<span data-ttu-id="d5601-115">Operadores</span><span class="sxs-lookup"><span data-stu-id="d5601-115">Operators</span></span>|  
|----------------|---------------|  
|<span data-ttu-id="d5601-116">Máxima</span><span class="sxs-lookup"><span data-stu-id="d5601-116">Highest</span></span>|<span data-ttu-id="d5601-117">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="d5601-117">INTERSECT</span></span>|  
||<span data-ttu-id="d5601-118">UNION</span><span class="sxs-lookup"><span data-stu-id="d5601-118">UNION</span></span><br /><br /> <span data-ttu-id="d5601-119">UNION ALL</span><span class="sxs-lookup"><span data-stu-id="d5601-119">UNION ALL</span></span>|  
||<span data-ttu-id="d5601-120">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="d5601-120">EXCEPT</span></span>|  
|<span data-ttu-id="d5601-121">Mínima</span><span class="sxs-lookup"><span data-stu-id="d5601-121">Lowest</span></span>|<span data-ttu-id="d5601-122">EXISTS</span><span class="sxs-lookup"><span data-stu-id="d5601-122">EXISTS</span></span><br /><br /> <span data-ttu-id="d5601-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="d5601-123">OVERLAPS</span></span><br /><br /> <span data-ttu-id="d5601-124">FLATTEN</span><span class="sxs-lookup"><span data-stu-id="d5601-124">FLATTEN</span></span><br /><br /> <span data-ttu-id="d5601-125">SET</span><span class="sxs-lookup"><span data-stu-id="d5601-125">SET</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d5601-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d5601-126">Example</span></span>  
 <span data-ttu-id="d5601-127">La siguiente consulta de Entity SQL usa el operador EXCEPT para devolver una colección de valores distintos de dos expresiones de consulta.</span><span class="sxs-lookup"><span data-stu-id="d5601-127">The following Entity SQL query uses the EXCEPT operator to return a collection of any distinct values from two query expressions.</span></span> <span data-ttu-id="d5601-128">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="d5601-128">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="d5601-129">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="d5601-129">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="d5601-130">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="d5601-130">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="d5601-131">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="d5601-131">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#EXCEPT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#except)]  
  
## <a name="see-also"></a><span data-ttu-id="d5601-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5601-132">See Also</span></span>  
 [<span data-ttu-id="d5601-133">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="d5601-133">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
