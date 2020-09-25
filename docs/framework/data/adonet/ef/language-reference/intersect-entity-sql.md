---
title: INTERSECT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 93c6fe33-f341-4b52-911e-adf503891951
ms.openlocfilehash: 217cd9b2a428c890d83d2b55d45321a04488398e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203649"
---
# <a name="intersect-entity-sql"></a><span data-ttu-id="a9ac2-102">INTERSECT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="a9ac2-102">INTERSECT (Entity SQL)</span></span>

<span data-ttu-id="a9ac2-103">Devuelve una colección de los valores distintos que devuelven las expresiones de consulta situadas a los lados izquierdo y derecho del operando INTERSECT.</span><span class="sxs-lookup"><span data-stu-id="a9ac2-103">Returns a collection of any distinct values that are returned by both the query expressions on the left and right sides of the INTERSECT operand.</span></span> <span data-ttu-id="a9ac2-104">Todas las expresiones deben ser del mismo tipo que `expression`o de un tipo base común o derivado.</span><span class="sxs-lookup"><span data-stu-id="a9ac2-104">All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9ac2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9ac2-105">Syntax</span></span>  
  
```sql  
expression INTERSECT expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="a9ac2-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a9ac2-106">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="a9ac2-107">Cualquier expresión de consulta válida que devuelva una colección para comparar con la colección que devuelve otra expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="a9ac2-107">Any valid query expression that returns a collection to compare with the collection returned from another query expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a9ac2-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a9ac2-108">Return Value</span></span>  

 <span data-ttu-id="a9ac2-109">Colección del mismo tipo que `expression`o de un tipo base común o derivado.</span><span class="sxs-lookup"><span data-stu-id="a9ac2-109">A collection of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a9ac2-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a9ac2-110">Remarks</span></span>  

 <span data-ttu-id="a9ac2-111">INTERSECT es uno de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a9ac2-111">INTERSECT is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="a9ac2-112">Todos los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se evalúan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="a9ac2-112">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="a9ac2-113">Para obtener información sobre la prioridad de los [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operadores de conjuntos, vea [excepto](except-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="a9ac2-113">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9ac2-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a9ac2-114">Example</span></span>  

 <span data-ttu-id="a9ac2-115">La siguiente consulta de Entity SQL usa el operador INTERSECT para devolver una colección de los valores distintos que devuelven las expresiones de consulta situadas a los lados izquierdo y derecho del operando INTERSECT.</span><span class="sxs-lookup"><span data-stu-id="a9ac2-115">The following Entity SQL query uses the INTERSECT operator to return a collection of any distinct values that are returned by both the query expressions on the left and right sides of the INTERSECT operand.</span></span> <span data-ttu-id="a9ac2-116">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="a9ac2-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="a9ac2-117">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="a9ac2-117">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="a9ac2-118">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="a9ac2-118">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="a9ac2-119">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="a9ac2-119">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#INTERSECT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#intersect)]  
  
## <a name="see-also"></a><span data-ttu-id="a9ac2-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a9ac2-120">See also</span></span>

- [<span data-ttu-id="a9ac2-121">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a9ac2-121">Entity SQL Reference</span></span>](entity-sql-reference.md)
