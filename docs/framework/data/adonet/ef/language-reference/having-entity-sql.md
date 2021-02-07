---
description: 'Más información sobre: tener (Entity SQL)'
title: HAVING (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b5d52d97-8372-4335-beac-2d0b79dc3707
ms.openlocfilehash: 70ace20d67e93aa051873d2b32a49f560902e63d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696885"
---
# <a name="having-entity-sql"></a><span data-ttu-id="cb419-103">HAVING (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="cb419-103">HAVING (Entity SQL)</span></span>

<span data-ttu-id="cb419-104">Especifica una condición de búsqueda para un grupo o agregado.</span><span class="sxs-lookup"><span data-stu-id="cb419-104">Specifies a search condition for a group or an aggregate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb419-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cb419-105">Syntax</span></span>  
  
```sql  
[ HAVING search_condition ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="cb419-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="cb419-106">Arguments</span></span>  

 `search_condition`  
 <span data-ttu-id="cb419-107">Especifica la condición de búsqueda del grupo o del agregado que se debe cumplir.</span><span class="sxs-lookup"><span data-stu-id="cb419-107">Specifies the search condition for the group or the aggregate to meet.</span></span> <span data-ttu-id="cb419-108">Cuando se utiliza HAVING con GROUP BY ALL, la cláusula HAVING invalida ALL.</span><span class="sxs-lookup"><span data-stu-id="cb419-108">When HAVING is used with GROUP BY ALL, the HAVING clause overrides ALL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb419-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cb419-109">Remarks</span></span>  

 <span data-ttu-id="cb419-110">La cláusula HAVING se utiliza para especificar una condición de filtrado adicional en el resultado de una agrupación.</span><span class="sxs-lookup"><span data-stu-id="cb419-110">The HAVING clause is used to specify an additional filtering condition on the result of a grouping.</span></span> <span data-ttu-id="cb419-111">Si no se especifica una cláusula GROUP BY en la expresión de consulta, se supone un grupo de conjunto único implícito.</span><span class="sxs-lookup"><span data-stu-id="cb419-111">If no GROUP BY clause is specified in the query expression, an implicit single-set group is assumed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cb419-112">HAVING solo se puede usar con la instrucción [Select](select-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="cb419-112">HAVING can be used only with the [SELECT](select-entity-sql.md) statement.</span></span> <span data-ttu-id="cb419-113">Cuando no se usa [Group by](group-by-entity-sql.md) , having se comporta como una cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="cb419-113">When [GROUP BY](group-by-entity-sql.md) is not used, HAVING behaves like a WHERE clause.</span></span>  
  
<span data-ttu-id="cb419-114">La cláusula HAVING funciona como la cláusula WHERE salvo que se aplica después de la operación GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="cb419-114">The HAVING clause works like the WHERE clause except that it is applied after the GROUP BY operation.</span></span> <span data-ttu-id="cb419-115">Esto significa que la cláusula HAVING solo puede hacer referencias a agrupar alias y agregados, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cb419-115">This means that the HAVING clause can only make references to grouping aliases and aggregates, as illustrated in the following example:</span></span>
  
```sql  
SELECT Name, SUM(o.Price * o.Quantity) AS Total FROM orderLines AS o GROUP BY o.Product AS Name  
HAVING SUM(o.Quantity) > 1  
```  
  
 <span data-ttu-id="cb419-116">Todo lo anterior hace que se restrinjan los grupos a solo aquellos que incluyen más de un producto.</span><span class="sxs-lookup"><span data-stu-id="cb419-116">The previous restricts the groups to only those that include more than one product.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb419-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cb419-117">Example</span></span>  

 <span data-ttu-id="cb419-118">La consulta de Entity SQL siguiente utiliza los operadores HAVING y GROUP BY para especificar una condición de búsqueda para un grupo o un agregado.</span><span class="sxs-lookup"><span data-stu-id="cb419-118">The following Entity SQL query uses the HAVING and GROUP BY operators to specify a search condition for a group or an aggregate.</span></span> <span data-ttu-id="cb419-119">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="cb419-119">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="cb419-120">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="cb419-120">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="cb419-121">Siga el procedimiento descrito en [Cómo: ejecutar una consulta que devuelve resultados PrimitiveType](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="cb419-121">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="cb419-122">Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="cb419-122">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#HAVING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#having)]  
  
## <a name="see-also"></a><span data-ttu-id="cb419-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb419-123">See also</span></span>

- [<span data-ttu-id="cb419-124">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="cb419-124">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="cb419-125">Expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="cb419-125">Query Expressions</span></span>](query-expressions-entity-sql.md)
