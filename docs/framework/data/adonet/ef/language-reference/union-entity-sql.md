---
description: 'Más información acerca de: UNION (Entity SQL)'
title: UNION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: df98a4db-b00d-4c8b-bd74-0d285f27e1df
ms.openlocfilehash: f02b3d76d8c21848b7a1b7ef5e7bbf749aea5c0f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99673315"
---
# <a name="union-entity-sql"></a><span data-ttu-id="6cca6-103">UNION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="6cca6-103">UNION (Entity SQL)</span></span>

<span data-ttu-id="6cca6-104">Combina los resultados de dos o más consultas en una sola colección.</span><span class="sxs-lookup"><span data-stu-id="6cca6-104">Combines the results of two or more queries into a single collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cca6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6cca6-105">Syntax</span></span>  
  
```sql  
expression  
UNION [ ALL ]  
expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="6cca6-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="6cca6-106">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="6cca6-107">Cualquier expresión de consulta válida que devuelva una colección que combine con la colección. Todas las expresiones deben ser del mismo tipo que `expression`o de un tipo base común o derivado.</span><span class="sxs-lookup"><span data-stu-id="6cca6-107">Any valid query expression that returns a collection to combine with the collection All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
 <span data-ttu-id="6cca6-108">UNION</span><span class="sxs-lookup"><span data-stu-id="6cca6-108">UNION</span></span>  
 <span data-ttu-id="6cca6-109">Especifica que se van a combinar varias colecciones y se van a devolver como una sola.</span><span class="sxs-lookup"><span data-stu-id="6cca6-109">Specifies that multiple collections are to be combined and returned as a single collection.</span></span>  
  
 <span data-ttu-id="6cca6-110">ALL</span><span class="sxs-lookup"><span data-stu-id="6cca6-110">ALL</span></span>  
 <span data-ttu-id="6cca6-111">Especifica que se van a combinar varias colecciones y se van a devolver como una sola, que incluye duplicados.</span><span class="sxs-lookup"><span data-stu-id="6cca6-111">Specifies that multiple collections are to be combined and returned as a single collection, including duplicates.</span></span> <span data-ttu-id="6cca6-112">Si no se especifica, los duplicados se quitan de la colección resultado.</span><span class="sxs-lookup"><span data-stu-id="6cca6-112">If not specified, duplicates are removed from the result collection.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6cca6-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6cca6-113">Return Value</span></span>  

 <span data-ttu-id="6cca6-114">Colección del mismo tipo que `expression`o de un tipo base común o derivado.</span><span class="sxs-lookup"><span data-stu-id="6cca6-114">A collection of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6cca6-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6cca6-115">Remarks</span></span>  

 <span data-ttu-id="6cca6-116">UNION es uno de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6cca6-116">UNION is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="6cca6-117">Todos los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se evalúan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="6cca6-117">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="6cca6-118">Para obtener información sobre la prioridad de los [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operadores de conjuntos, vea [excepto](except-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="6cca6-118">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6cca6-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6cca6-119">Example</span></span>  

 <span data-ttu-id="6cca6-120">La siguiente consulta de Entity SQL usa el operador UNION ALL para combinar los resultados de dos consultas en una sola colección.</span><span class="sxs-lookup"><span data-stu-id="6cca6-120">The following Entity SQL query uses the UNION ALL operator to combine the results of two queries into a single collection.</span></span> <span data-ttu-id="6cca6-121">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="6cca6-121">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="6cca6-122">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6cca6-122">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="6cca6-123">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="6cca6-123">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="6cca6-124">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="6cca6-124">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#UNION](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#union)]  
  
## <a name="see-also"></a><span data-ttu-id="6cca6-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="6cca6-125">See also</span></span>

- [<span data-ttu-id="6cca6-126">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="6cca6-126">Entity SQL Reference</span></span>](entity-sql-reference.md)
