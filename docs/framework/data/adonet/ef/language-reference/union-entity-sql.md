---
title: UNION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: df98a4db-b00d-4c8b-bd74-0d285f27e1df
ms.openlocfilehash: 9c4106d26fb73219d7b5f0c6763736aaf9163d4b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200984"
---
# <a name="union-entity-sql"></a><span data-ttu-id="c6d30-102">UNION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c6d30-102">UNION (Entity SQL)</span></span>

<span data-ttu-id="c6d30-103">Combina los resultados de dos o más consultas en una sola colección.</span><span class="sxs-lookup"><span data-stu-id="c6d30-103">Combines the results of two or more queries into a single collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6d30-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c6d30-104">Syntax</span></span>  
  
```sql  
expression  
UNION [ ALL ]  
expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="c6d30-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c6d30-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="c6d30-106">Cualquier expresión de consulta válida que devuelva una colección que combine con la colección. Todas las expresiones deben ser del mismo tipo que `expression`o de un tipo base común o derivado.</span><span class="sxs-lookup"><span data-stu-id="c6d30-106">Any valid query expression that returns a collection to combine with the collection All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
 <span data-ttu-id="c6d30-107">UNION</span><span class="sxs-lookup"><span data-stu-id="c6d30-107">UNION</span></span>  
 <span data-ttu-id="c6d30-108">Especifica que se van a combinar varias colecciones y se van a devolver como una sola.</span><span class="sxs-lookup"><span data-stu-id="c6d30-108">Specifies that multiple collections are to be combined and returned as a single collection.</span></span>  
  
 <span data-ttu-id="c6d30-109">ALL</span><span class="sxs-lookup"><span data-stu-id="c6d30-109">ALL</span></span>  
 <span data-ttu-id="c6d30-110">Especifica que se van a combinar varias colecciones y se van a devolver como una sola, que incluye duplicados.</span><span class="sxs-lookup"><span data-stu-id="c6d30-110">Specifies that multiple collections are to be combined and returned as a single collection, including duplicates.</span></span> <span data-ttu-id="c6d30-111">Si no se especifica, los duplicados se quitan de la colección resultado.</span><span class="sxs-lookup"><span data-stu-id="c6d30-111">If not specified, duplicates are removed from the result collection.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c6d30-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c6d30-112">Return Value</span></span>  

 <span data-ttu-id="c6d30-113">Colección del mismo tipo que `expression`o de un tipo base común o derivado.</span><span class="sxs-lookup"><span data-stu-id="c6d30-113">A collection of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6d30-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c6d30-114">Remarks</span></span>  

 <span data-ttu-id="c6d30-115">UNION es uno de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c6d30-115">UNION is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="c6d30-116">Todos los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se evalúan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="c6d30-116">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="c6d30-117">Para obtener información sobre la prioridad de los [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operadores de conjuntos, vea [excepto](except-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="c6d30-117">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6d30-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c6d30-118">Example</span></span>  

 <span data-ttu-id="c6d30-119">La siguiente consulta de Entity SQL usa el operador UNION ALL para combinar los resultados de dos consultas en una sola colección.</span><span class="sxs-lookup"><span data-stu-id="c6d30-119">The following Entity SQL query uses the UNION ALL operator to combine the results of two queries into a single collection.</span></span> <span data-ttu-id="c6d30-120">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="c6d30-120">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="c6d30-121">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="c6d30-121">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="c6d30-122">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="c6d30-122">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="c6d30-123">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="c6d30-123">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#UNION](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#union)]  
  
## <a name="see-also"></a><span data-ttu-id="c6d30-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c6d30-124">See also</span></span>

- [<span data-ttu-id="c6d30-125">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="c6d30-125">Entity SQL Reference</span></span>](entity-sql-reference.md)
