---
title: OVERLAPS (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 41743e89-79cb-4d7b-8a27-355b45024b61
ms.openlocfilehash: bdee9281fd406a3d029d3a10536cbdd48d2f7a58
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319415"
---
# <a name="overlaps-entity-sql"></a><span data-ttu-id="c12da-102">OVERLAPS (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c12da-102">OVERLAPS (Entity SQL)</span></span>
<span data-ttu-id="c12da-103">Determina si dos colecciones tienen elementos comunes.</span><span class="sxs-lookup"><span data-stu-id="c12da-103">Determines whether two collections have common elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c12da-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c12da-104">Syntax</span></span>  
  
```sql  
expression OVERLAPS expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="c12da-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c12da-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="c12da-106">Cualquier expresión de consulta válida que devuelva una colección para comparar con la colección que devuelve otra expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="c12da-106">Any valid query expression that returns a collection to compare with the collection returned from another query expression.</span></span> <span data-ttu-id="c12da-107">Todas las expresiones deben ser del mismo tipo que `expression`o de un tipo base común o derivado.</span><span class="sxs-lookup"><span data-stu-id="c12da-107">All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c12da-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c12da-108">Return Value</span></span>  
 <span data-ttu-id="c12da-109">`true` si las dos colecciones tienen elementos comunes; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="c12da-109">`true` if the two collections have common elements; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c12da-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c12da-110">Remarks</span></span>  
 <span data-ttu-id="c12da-111">Las superposiciones proporcionan funcionalmente equivalente a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c12da-111">OVERLAPS provides functionally equivalent to the following:</span></span>  
  
 `EXISTS ( expression INTERSECT expression )`  
  
 <span data-ttu-id="c12da-112">OVERLAPS es uno de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c12da-112">OVERLAPS is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="c12da-113">Todos los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se evalúan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="c12da-113">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="c12da-114">Para obtener información sobre la prioridad de los operadores de conjuntos [!INCLUDE[esql](../../../../../../includes/esql-md.md)], vea [Except](except-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="c12da-114">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c12da-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c12da-115">Example</span></span>  
 <span data-ttu-id="c12da-116">La siguiente consulta de Entity SQL usa el operador OVERLAPS para determinar si dos colecciones tienen un valor común.</span><span class="sxs-lookup"><span data-stu-id="c12da-116">The following Entity SQL query uses the OVERLAPS operator to determines whether two collections have a common value.</span></span> <span data-ttu-id="c12da-117">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="c12da-117">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="c12da-118">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="c12da-118">To compile and run this, follow these steps:</span></span>  
  
1. <span data-ttu-id="c12da-119">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="c12da-119">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="c12da-120">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="c12da-120">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#OVERLAPS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#overlaps)]  
  
## <a name="see-also"></a><span data-ttu-id="c12da-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="c12da-121">See also</span></span>

- [<span data-ttu-id="c12da-122">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="c12da-122">Entity SQL Reference</span></span>](entity-sql-reference.md)
