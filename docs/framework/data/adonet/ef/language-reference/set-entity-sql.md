---
title: SET (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 28b4deac-c7e4-4f09-b428-4d352ef2dc94
ms.openlocfilehash: dab124e139f3491c4a7a42eb90c4ffb3b3a92258
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59158566"
---
# <a name="set-entity-sql"></a><span data-ttu-id="95c2d-102">SET (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="95c2d-102">SET (Entity SQL)</span></span>
<span data-ttu-id="95c2d-103">La expresión SET se usa para convertir una colección de objetos en un conjunto produciendo una colección nueva en la que se han quitado todos los elementos duplicados.</span><span class="sxs-lookup"><span data-stu-id="95c2d-103">The SET expression is used to convert a collection of objects into a set by yielding a new collection with all duplicate elements removed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95c2d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="95c2d-104">Syntax</span></span>  
  
```  
SET ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="95c2d-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="95c2d-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="95c2d-106">Expresión de consulta válida que devuelve una colección.</span><span class="sxs-lookup"><span data-stu-id="95c2d-106">Any valid query expression that returns a collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="95c2d-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="95c2d-107">Remarks</span></span>  
 <span data-ttu-id="95c2d-108">La expresión set `SET(c)` es lógicamente equivalente a la instrucción select siguiente:</span><span class="sxs-lookup"><span data-stu-id="95c2d-108">The set expression `SET(c)` is logically equivalent to the following select statement:</span></span>  
  
```  
SELECT VALUE DISTINCT c FROM c  
```  
  
 `SET` <span data-ttu-id="95c2d-109">es uno de los [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operadores de conjuntos.</span><span class="sxs-lookup"><span data-stu-id="95c2d-109">is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="95c2d-110">Todos los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se evalúan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="95c2d-110">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="95c2d-111">Consulte [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md) para obtener información de prioridad para la [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operadores de conjuntos.</span><span class="sxs-lookup"><span data-stu-id="95c2d-111">See [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md) for precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="95c2d-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="95c2d-112">Example</span></span>  
 <span data-ttu-id="95c2d-113">La siguiente consulta de Entity SQL usa la expresión SET para convertir una colección de objetos en un conjunto.</span><span class="sxs-lookup"><span data-stu-id="95c2d-113">The following Entity SQL query uses the SET expression to convert a collection of objects into a set.</span></span> <span data-ttu-id="95c2d-114">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="95c2d-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="95c2d-115">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="95c2d-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="95c2d-116">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="95c2d-116">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="95c2d-117">Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="95c2d-117">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#SET](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#set)]  
  
## <a name="see-also"></a><span data-ttu-id="95c2d-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="95c2d-118">See also</span></span>

- [<span data-ttu-id="95c2d-119">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="95c2d-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
