---
title: UNION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: df98a4db-b00d-4c8b-bd74-0d285f27e1df
ms.openlocfilehash: 52a7a332166250e8fa8084986fd0d89da6fdf42d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="union-entity-sql"></a><span data-ttu-id="1011c-102">UNION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="1011c-102">UNION (Entity SQL)</span></span>
<span data-ttu-id="1011c-103">Combina los resultados de dos o más consultas en una sola colección.</span><span class="sxs-lookup"><span data-stu-id="1011c-103">Combines the results of two or more queries into a single collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1011c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1011c-104">Syntax</span></span>  
  
```  
expression  
UNION [ ALL ]  
expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="1011c-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="1011c-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="1011c-106">Cualquier expresión de consulta válida que devuelva una colección que combine con la colección. Todas las expresiones deben ser del mismo tipo que `expression`o de un tipo base común o derivado.</span><span class="sxs-lookup"><span data-stu-id="1011c-106">Any valid query expression that returns a collection to combine with the collection All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
 <span data-ttu-id="1011c-107">UNION</span><span class="sxs-lookup"><span data-stu-id="1011c-107">UNION</span></span>  
 <span data-ttu-id="1011c-108">Especifica que se van a combinar varias colecciones y se van a devolver como una sola.</span><span class="sxs-lookup"><span data-stu-id="1011c-108">Specifies that multiple collections are to be combined and returned as a single collection.</span></span>  
  
 <span data-ttu-id="1011c-109">ALL</span><span class="sxs-lookup"><span data-stu-id="1011c-109">ALL</span></span>  
 <span data-ttu-id="1011c-110">Especifica que se van a combinar varias colecciones y se van a devolver como una sola, que incluye duplicados.</span><span class="sxs-lookup"><span data-stu-id="1011c-110">Specifies that multiple collections are to be combined and returned as a single collection, including duplicates.</span></span> <span data-ttu-id="1011c-111">Si no se especifica, los duplicados se quitan de la colección resultado.</span><span class="sxs-lookup"><span data-stu-id="1011c-111">If not specified, duplicates are removed from the result collection.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1011c-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1011c-112">Return Value</span></span>  
 <span data-ttu-id="1011c-113">Colección del mismo tipo que `expression`o de un tipo base común o derivado.</span><span class="sxs-lookup"><span data-stu-id="1011c-113">A collection of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1011c-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1011c-114">Remarks</span></span>  
 <span data-ttu-id="1011c-115">UNION es uno de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1011c-115">UNION is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="1011c-116">Todos los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se evalúan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="1011c-116">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="1011c-117">Para obtener información de prioridad para la [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operadores de conjuntos, vea [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="1011c-117">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1011c-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1011c-118">Example</span></span>  
 <span data-ttu-id="1011c-119">La siguiente consulta de Entity SQL usa el operador UNION ALL para combinar los resultados de dos consultas en una sola colección.</span><span class="sxs-lookup"><span data-stu-id="1011c-119">The following Entity SQL query uses the UNION ALL operator to combine the results of two queries into a single collection.</span></span> <span data-ttu-id="1011c-120">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="1011c-120">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="1011c-121">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="1011c-121">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="1011c-122">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="1011c-122">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="1011c-123">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="1011c-123">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#UNION](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#union)]  
  
## <a name="see-also"></a><span data-ttu-id="1011c-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="1011c-124">See Also</span></span>  
 [<span data-ttu-id="1011c-125">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="1011c-125">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
