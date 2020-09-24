---
title: EXCEPT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 69cc23e5-3f8f-4b49-b20e-2f84ff11c80d
ms.openlocfilehash: 6797f8038a83533b5a6bd41ad402daec7abdc7de
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148064"
---
# <a name="except-entity-sql"></a><span data-ttu-id="bf8d7-102">EXCEPT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="bf8d7-102">EXCEPT (Entity SQL)</span></span>

<span data-ttu-id="bf8d7-103">Devuelve una colección de los valores distintos de la expresión de consulta situada a la izquierda del operando EXCEPT, que tampoco se devuelven en la expresión de consulta situada a la derecha del operando EXCEPT.</span><span class="sxs-lookup"><span data-stu-id="bf8d7-103">Returns a collection of any distinct values from the query expression to the left of the EXCEPT operand that are not also returned from the query expression to the right of the EXCEPT operand.</span></span> <span data-ttu-id="bf8d7-104">Todas las expresiones deben ser del mismo tipo que `expression`o de un tipo base común o derivado.</span><span class="sxs-lookup"><span data-stu-id="bf8d7-104">All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf8d7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bf8d7-105">Syntax</span></span>  
  
```sql  
expression EXCEPT expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="bf8d7-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="bf8d7-106">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="bf8d7-107">Cualquier expresión de consulta válida que devuelva una colección para comparar con la colección que devuelve otra expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="bf8d7-107">Any valid query expression that returns a collection to compare with the collection returned from another query expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bf8d7-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bf8d7-108">Return Value</span></span>  

 <span data-ttu-id="bf8d7-109">Colección del mismo tipo que `expression`o de un tipo base común o derivado.</span><span class="sxs-lookup"><span data-stu-id="bf8d7-109">A collection of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf8d7-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bf8d7-110">Remarks</span></span>  

 <span data-ttu-id="bf8d7-111">EXCEPT es uno de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bf8d7-111">EXCEPT is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="bf8d7-112">Todos los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se evalúan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="bf8d7-112">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="bf8d7-113">En la tabla siguiente se muestra la prioridad de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bf8d7-113">The following table shows the precedence of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
|<span data-ttu-id="bf8d7-114">Prioridad</span><span class="sxs-lookup"><span data-stu-id="bf8d7-114">Precedence</span></span>|<span data-ttu-id="bf8d7-115">Operadores</span><span class="sxs-lookup"><span data-stu-id="bf8d7-115">Operators</span></span>|  
|----------------|---------------|  
|<span data-ttu-id="bf8d7-116">Highest (el más alto)</span><span class="sxs-lookup"><span data-stu-id="bf8d7-116">Highest</span></span>|<span data-ttu-id="bf8d7-117">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="bf8d7-117">INTERSECT</span></span>|  
||<span data-ttu-id="bf8d7-118">UNION</span><span class="sxs-lookup"><span data-stu-id="bf8d7-118">UNION</span></span><br /><br /> <span data-ttu-id="bf8d7-119">UNION ALL</span><span class="sxs-lookup"><span data-stu-id="bf8d7-119">UNION ALL</span></span>|  
||<span data-ttu-id="bf8d7-120">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="bf8d7-120">EXCEPT</span></span>|  
|<span data-ttu-id="bf8d7-121">Mínima</span><span class="sxs-lookup"><span data-stu-id="bf8d7-121">Lowest</span></span>|<span data-ttu-id="bf8d7-122">EXISTS</span><span class="sxs-lookup"><span data-stu-id="bf8d7-122">EXISTS</span></span><br /><br /> <span data-ttu-id="bf8d7-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="bf8d7-123">OVERLAPS</span></span><br /><br /> <span data-ttu-id="bf8d7-124">FLATTEN</span><span class="sxs-lookup"><span data-stu-id="bf8d7-124">FLATTEN</span></span><br /><br /> <span data-ttu-id="bf8d7-125">SET</span><span class="sxs-lookup"><span data-stu-id="bf8d7-125">SET</span></span>|  
  
## <a name="example"></a><span data-ttu-id="bf8d7-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bf8d7-126">Example</span></span>  

 <span data-ttu-id="bf8d7-127">La siguiente consulta de Entity SQL usa el operador EXCEPT para devolver una colección de valores distintos de dos expresiones de consulta.</span><span class="sxs-lookup"><span data-stu-id="bf8d7-127">The following Entity SQL query uses the EXCEPT operator to return a collection of any distinct values from two query expressions.</span></span> <span data-ttu-id="bf8d7-128">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="bf8d7-128">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="bf8d7-129">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="bf8d7-129">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="bf8d7-130">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="bf8d7-130">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="bf8d7-131">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="bf8d7-131">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#EXCEPT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#except)]  
  
## <a name="see-also"></a><span data-ttu-id="bf8d7-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf8d7-132">See also</span></span>

- [<span data-ttu-id="bf8d7-133">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="bf8d7-133">Entity SQL Reference</span></span>](entity-sql-reference.md)
