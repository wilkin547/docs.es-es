---
description: 'Más información sobre: superposiciones (Entity SQL)'
title: OVERLAPS (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 41743e89-79cb-4d7b-8a27-355b45024b61
ms.openlocfilehash: dd2f4a0925c57edcc3dd2d1264d00921b092525a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791912"
---
# <a name="overlaps-entity-sql"></a><span data-ttu-id="a89e6-103">OVERLAPS (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="a89e6-103">OVERLAPS (Entity SQL)</span></span>

<span data-ttu-id="a89e6-104">Determina si dos colecciones tienen elementos comunes.</span><span class="sxs-lookup"><span data-stu-id="a89e6-104">Determines whether two collections have common elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a89e6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a89e6-105">Syntax</span></span>  
  
```sql  
expression OVERLAPS expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="a89e6-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a89e6-106">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="a89e6-107">Cualquier expresión de consulta válida que devuelva una colección para comparar con la colección que devuelve otra expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="a89e6-107">Any valid query expression that returns a collection to compare with the collection returned from another query expression.</span></span> <span data-ttu-id="a89e6-108">Todas las expresiones deben ser del mismo tipo que `expression`o de un tipo base común o derivado.</span><span class="sxs-lookup"><span data-stu-id="a89e6-108">All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a89e6-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a89e6-109">Return Value</span></span>  

 <span data-ttu-id="a89e6-110">`true` si las dos colecciones tienen elementos comunes; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="a89e6-110">`true` if the two collections have common elements; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a89e6-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a89e6-111">Remarks</span></span>  

 <span data-ttu-id="a89e6-112">Las superposiciones proporcionan funcionalmente equivalente a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a89e6-112">OVERLAPS provides functionally equivalent to the following:</span></span>  
  
 `EXISTS ( expression INTERSECT expression )`  
  
 <span data-ttu-id="a89e6-113">OVERLAPS es uno de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a89e6-113">OVERLAPS is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="a89e6-114">Todos los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se evalúan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="a89e6-114">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="a89e6-115">Para obtener información sobre la prioridad de los [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operadores de conjuntos, vea [excepto](except-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="a89e6-115">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a89e6-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a89e6-116">Example</span></span>  

 <span data-ttu-id="a89e6-117">La siguiente consulta de Entity SQL usa el operador OVERLAPS para determinar si dos colecciones tienen un valor común.</span><span class="sxs-lookup"><span data-stu-id="a89e6-117">The following Entity SQL query uses the OVERLAPS operator to determines whether two collections have a common value.</span></span> <span data-ttu-id="a89e6-118">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="a89e6-118">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="a89e6-119">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="a89e6-119">To compile and run this, follow these steps:</span></span>  
  
1. <span data-ttu-id="a89e6-120">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="a89e6-120">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="a89e6-121">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="a89e6-121">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#OVERLAPS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#overlaps)]  
  
## <a name="see-also"></a><span data-ttu-id="a89e6-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="a89e6-122">See also</span></span>

- [<span data-ttu-id="a89e6-123">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a89e6-123">Entity SQL Reference</span></span>](entity-sql-reference.md)
