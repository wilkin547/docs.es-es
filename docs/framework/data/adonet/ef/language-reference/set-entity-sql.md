---
title: SET (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 28b4deac-c7e4-4f09-b428-4d352ef2dc94
ms.openlocfilehash: 2ac7db5b22ad21eb152788b6c6d6a8e65c1f6a7b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169640"
---
# <a name="set-entity-sql"></a><span data-ttu-id="038d6-102">SET (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="038d6-102">SET (Entity SQL)</span></span>

<span data-ttu-id="038d6-103">La expresión SET se usa para convertir una colección de objetos en un conjunto produciendo una colección nueva en la que se han quitado todos los elementos duplicados.</span><span class="sxs-lookup"><span data-stu-id="038d6-103">The SET expression is used to convert a collection of objects into a set by yielding a new collection with all duplicate elements removed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="038d6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="038d6-104">Syntax</span></span>  
  
```sql  
SET ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="038d6-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="038d6-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="038d6-106">Expresión de consulta válida que devuelve una colección.</span><span class="sxs-lookup"><span data-stu-id="038d6-106">Any valid query expression that returns a collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="038d6-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="038d6-107">Remarks</span></span>  

 <span data-ttu-id="038d6-108">La expresión set `SET(c)` es lógicamente equivalente a la instrucción select siguiente:</span><span class="sxs-lookup"><span data-stu-id="038d6-108">The set expression `SET(c)` is logically equivalent to the following select statement:</span></span>  
  
```sql  
SELECT VALUE DISTINCT c FROM c  
```  
  
 <span data-ttu-id="038d6-109">`SET` es uno de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="038d6-109">`SET` is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="038d6-110">Todos los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se evalúan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="038d6-110">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="038d6-111">Vea [excepto](except-entity-sql.md) para obtener información sobre la prioridad de los [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operadores de conjuntos.</span><span class="sxs-lookup"><span data-stu-id="038d6-111">See [EXCEPT](except-entity-sql.md) for precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="038d6-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="038d6-112">Example</span></span>  

 <span data-ttu-id="038d6-113">La siguiente consulta de Entity SQL usa la expresión SET para convertir una colección de objetos en un conjunto.</span><span class="sxs-lookup"><span data-stu-id="038d6-113">The following Entity SQL query uses the SET expression to convert a collection of objects into a set.</span></span> <span data-ttu-id="038d6-114">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="038d6-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="038d6-115">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="038d6-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="038d6-116">Siga el procedimiento descrito en [Cómo: ejecutar una consulta que devuelve resultados PrimitiveType](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="038d6-116">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="038d6-117">Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="038d6-117">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#SET](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#set)]  
  
## <a name="see-also"></a><span data-ttu-id="038d6-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="038d6-118">See also</span></span>

- [<span data-ttu-id="038d6-119">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="038d6-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
