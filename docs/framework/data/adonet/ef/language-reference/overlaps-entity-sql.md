---
title: OVERLAPS (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 41743e89-79cb-4d7b-8a27-355b45024b61
ms.openlocfilehash: 6902a44af343c37ccb26412738d9f96b28551814
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204429"
---
# <a name="overlaps-entity-sql"></a><span data-ttu-id="43f95-102">OVERLAPS (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="43f95-102">OVERLAPS (Entity SQL)</span></span>

<span data-ttu-id="43f95-103">Determina si dos colecciones tienen elementos comunes.</span><span class="sxs-lookup"><span data-stu-id="43f95-103">Determines whether two collections have common elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43f95-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="43f95-104">Syntax</span></span>  
  
```sql  
expression OVERLAPS expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="43f95-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="43f95-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="43f95-106">Cualquier expresión de consulta válida que devuelva una colección para comparar con la colección que devuelve otra expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="43f95-106">Any valid query expression that returns a collection to compare with the collection returned from another query expression.</span></span> <span data-ttu-id="43f95-107">Todas las expresiones deben ser del mismo tipo que `expression`o de un tipo base común o derivado.</span><span class="sxs-lookup"><span data-stu-id="43f95-107">All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="43f95-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="43f95-108">Return Value</span></span>  

 <span data-ttu-id="43f95-109">`true` si las dos colecciones tienen elementos comunes; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="43f95-109">`true` if the two collections have common elements; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43f95-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="43f95-110">Remarks</span></span>  

 <span data-ttu-id="43f95-111">Las superposiciones proporcionan funcionalmente equivalente a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="43f95-111">OVERLAPS provides functionally equivalent to the following:</span></span>  
  
 `EXISTS ( expression INTERSECT expression )`  
  
 <span data-ttu-id="43f95-112">OVERLAPS es uno de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="43f95-112">OVERLAPS is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="43f95-113">Todos los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se evalúan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="43f95-113">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="43f95-114">Para obtener información sobre la prioridad de los [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operadores de conjuntos, vea [excepto](except-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="43f95-114">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="43f95-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="43f95-115">Example</span></span>  

 <span data-ttu-id="43f95-116">La siguiente consulta de Entity SQL usa el operador OVERLAPS para determinar si dos colecciones tienen un valor común.</span><span class="sxs-lookup"><span data-stu-id="43f95-116">The following Entity SQL query uses the OVERLAPS operator to determines whether two collections have a common value.</span></span> <span data-ttu-id="43f95-117">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="43f95-117">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="43f95-118">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="43f95-118">To compile and run this, follow these steps:</span></span>  
  
1. <span data-ttu-id="43f95-119">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="43f95-119">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="43f95-120">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="43f95-120">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#OVERLAPS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#overlaps)]  
  
## <a name="see-also"></a><span data-ttu-id="43f95-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="43f95-121">See also</span></span>

- [<span data-ttu-id="43f95-122">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="43f95-122">Entity SQL Reference</span></span>](entity-sql-reference.md)
