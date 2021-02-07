---
description: 'Más información acerca de: SET (Entity SQL)'
title: SET (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 28b4deac-c7e4-4f09-b428-4d352ef2dc94
ms.openlocfilehash: 80be5b76e654c39776d97413c4ece5a8f3df8d2b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768030"
---
# <a name="set-entity-sql"></a><span data-ttu-id="0351d-103">SET (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="0351d-103">SET (Entity SQL)</span></span>

<span data-ttu-id="0351d-104">La expresión SET se usa para convertir una colección de objetos en un conjunto produciendo una colección nueva en la que se han quitado todos los elementos duplicados.</span><span class="sxs-lookup"><span data-stu-id="0351d-104">The SET expression is used to convert a collection of objects into a set by yielding a new collection with all duplicate elements removed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0351d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0351d-105">Syntax</span></span>  
  
```sql  
SET ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="0351d-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0351d-106">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="0351d-107">Expresión de consulta válida que devuelve una colección.</span><span class="sxs-lookup"><span data-stu-id="0351d-107">Any valid query expression that returns a collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0351d-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0351d-108">Remarks</span></span>  

 <span data-ttu-id="0351d-109">La expresión set `SET(c)` es lógicamente equivalente a la instrucción select siguiente:</span><span class="sxs-lookup"><span data-stu-id="0351d-109">The set expression `SET(c)` is logically equivalent to the following select statement:</span></span>  
  
```sql  
SELECT VALUE DISTINCT c FROM c  
```  
  
 <span data-ttu-id="0351d-110">`SET` es uno de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0351d-110">`SET` is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="0351d-111">Todos los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se evalúan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="0351d-111">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="0351d-112">Vea [excepto](except-entity-sql.md) para obtener información sobre la prioridad de los [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operadores de conjuntos.</span><span class="sxs-lookup"><span data-stu-id="0351d-112">See [EXCEPT](except-entity-sql.md) for precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0351d-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0351d-113">Example</span></span>  

 <span data-ttu-id="0351d-114">La siguiente consulta de Entity SQL usa la expresión SET para convertir una colección de objetos en un conjunto.</span><span class="sxs-lookup"><span data-stu-id="0351d-114">The following Entity SQL query uses the SET expression to convert a collection of objects into a set.</span></span> <span data-ttu-id="0351d-115">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="0351d-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="0351d-116">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="0351d-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="0351d-117">Siga el procedimiento descrito en [Cómo: ejecutar una consulta que devuelve resultados PrimitiveType](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="0351d-117">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="0351d-118">Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="0351d-118">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#SET](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#set)]  
  
## <a name="see-also"></a><span data-ttu-id="0351d-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="0351d-119">See also</span></span>

- [<span data-ttu-id="0351d-120">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="0351d-120">Entity SQL Reference</span></span>](entity-sql-reference.md)
