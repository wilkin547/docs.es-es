---
description: 'Más información acerca de: Except (Entity SQL)'
title: EXCEPT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 69cc23e5-3f8f-4b49-b20e-2f84ff11c80d
ms.openlocfilehash: fd66d8dc6e22a73afbfd27e6eb1fd6c8bb9d3475
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786399"
---
# <a name="except-entity-sql"></a><span data-ttu-id="b9332-103">EXCEPT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b9332-103">EXCEPT (Entity SQL)</span></span>

<span data-ttu-id="b9332-104">Devuelve una colección de los valores distintos de la expresión de consulta situada a la izquierda del operando EXCEPT, que tampoco se devuelven en la expresión de consulta situada a la derecha del operando EXCEPT.</span><span class="sxs-lookup"><span data-stu-id="b9332-104">Returns a collection of any distinct values from the query expression to the left of the EXCEPT operand that are not also returned from the query expression to the right of the EXCEPT operand.</span></span> <span data-ttu-id="b9332-105">Todas las expresiones deben ser del mismo tipo que `expression`o de un tipo base común o derivado.</span><span class="sxs-lookup"><span data-stu-id="b9332-105">All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9332-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b9332-106">Syntax</span></span>  
  
```sql  
expression EXCEPT expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="b9332-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b9332-107">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="b9332-108">Cualquier expresión de consulta válida que devuelva una colección para comparar con la colección que devuelve otra expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="b9332-108">Any valid query expression that returns a collection to compare with the collection returned from another query expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b9332-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b9332-109">Return Value</span></span>  

 <span data-ttu-id="b9332-110">Colección del mismo tipo que `expression`o de un tipo base común o derivado.</span><span class="sxs-lookup"><span data-stu-id="b9332-110">A collection of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9332-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b9332-111">Remarks</span></span>  

 <span data-ttu-id="b9332-112">EXCEPT es uno de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b9332-112">EXCEPT is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="b9332-113">Todos los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se evalúan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="b9332-113">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="b9332-114">En la tabla siguiente se muestra la prioridad de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b9332-114">The following table shows the precedence of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
|<span data-ttu-id="b9332-115">Prioridad</span><span class="sxs-lookup"><span data-stu-id="b9332-115">Precedence</span></span>|<span data-ttu-id="b9332-116">Operadores</span><span class="sxs-lookup"><span data-stu-id="b9332-116">Operators</span></span>|  
|----------------|---------------|  
|<span data-ttu-id="b9332-117">Highest (el más alto)</span><span class="sxs-lookup"><span data-stu-id="b9332-117">Highest</span></span>|<span data-ttu-id="b9332-118">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="b9332-118">INTERSECT</span></span>|  
||<span data-ttu-id="b9332-119">UNION</span><span class="sxs-lookup"><span data-stu-id="b9332-119">UNION</span></span><br /><br /> <span data-ttu-id="b9332-120">UNION ALL</span><span class="sxs-lookup"><span data-stu-id="b9332-120">UNION ALL</span></span>|  
||<span data-ttu-id="b9332-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="b9332-121">EXCEPT</span></span>|  
|<span data-ttu-id="b9332-122">Mínima</span><span class="sxs-lookup"><span data-stu-id="b9332-122">Lowest</span></span>|<span data-ttu-id="b9332-123">EXISTS</span><span class="sxs-lookup"><span data-stu-id="b9332-123">EXISTS</span></span><br /><br /> <span data-ttu-id="b9332-124">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="b9332-124">OVERLAPS</span></span><br /><br /> <span data-ttu-id="b9332-125">FLATTEN</span><span class="sxs-lookup"><span data-stu-id="b9332-125">FLATTEN</span></span><br /><br /> <span data-ttu-id="b9332-126">SET</span><span class="sxs-lookup"><span data-stu-id="b9332-126">SET</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b9332-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b9332-127">Example</span></span>  

 <span data-ttu-id="b9332-128">La siguiente consulta de Entity SQL usa el operador EXCEPT para devolver una colección de valores distintos de dos expresiones de consulta.</span><span class="sxs-lookup"><span data-stu-id="b9332-128">The following Entity SQL query uses the EXCEPT operator to return a collection of any distinct values from two query expressions.</span></span> <span data-ttu-id="b9332-129">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="b9332-129">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="b9332-130">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="b9332-130">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="b9332-131">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="b9332-131">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="b9332-132">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="b9332-132">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#EXCEPT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#except)]  
  
## <a name="see-also"></a><span data-ttu-id="b9332-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9332-133">See also</span></span>

- [<span data-ttu-id="b9332-134">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="b9332-134">Entity SQL Reference</span></span>](entity-sql-reference.md)
