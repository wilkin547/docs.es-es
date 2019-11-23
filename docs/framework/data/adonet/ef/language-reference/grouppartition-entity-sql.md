---
title: GROUPPARTITION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: d0482e9b-086c-451c-9dfa-ccb024a9efb6
ms.openlocfilehash: 19df566c254a3f3202eb3554ab43ee0d7c944181
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833760"
---
# <a name="grouppartition-entity-sql"></a><span data-ttu-id="82892-102">GROUPPARTITION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="82892-102">GROUPPARTITION (Entity SQL)</span></span>
<span data-ttu-id="82892-103">Devuelve una colección de valores de argumento que se proyecta a partir de la partición de grupo actual con la que está relacionado el agregado.</span><span class="sxs-lookup"><span data-stu-id="82892-103">Returns a collection of argument values that are projected off the current group partition to which the aggregate is related.</span></span> <span data-ttu-id="82892-104">El agregado `GroupPartition` es un agregado basado en un grupo y no tiene ningún formulario basado en una colección.</span><span class="sxs-lookup"><span data-stu-id="82892-104">The `GroupPartition` aggregate is a group-based aggregate and has no collection-based form.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82892-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="82892-105">Syntax</span></span>  
  
```sql  
GROUPPARTITION( [ALL|DISTINCT] expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="82892-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="82892-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="82892-107">Cualquier expresión [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="82892-107">Any [!INCLUDE[esql](../../../../../../includes/esql-md.md)] expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82892-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="82892-108">Remarks</span></span>  
 <span data-ttu-id="82892-109">La consulta siguiente genera una lista de productos y una colección de cantidades de la línea de pedidos por cada producto:</span><span class="sxs-lookup"><span data-stu-id="82892-109">The following query produces a list of products and a collection of order line quantities per each product:</span></span>  
  
```sql  
SELECT p, GroupPartition(ol.Quantity) FROM LOB.OrderLines AS ol
  GROUP BY ol.Product AS p
```  
  
 <span data-ttu-id="82892-110">Las dos consultas siguientes son semánticamente iguales:</span><span class="sxs-lookup"><span data-stu-id="82892-110">The following two queries are semantically equal:</span></span>  
  
```sql  
SELECT p, Sum(GroupPartition(ol.Quantity)) FROM LOB.OrderLines AS ol
  GROUP BY ol.Product AS p
SELET p, Sum(ol.Quantity) FROM LOB.OrderLines AS ol
  group by ol.Product as p  
```  
  
 <span data-ttu-id="82892-111">El operador `GROUPPARTITION` se puede utilizar junto con funciones de agregado definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="82892-111">The `GROUPPARTITION` operator can be used in conjunction with user-defined aggregate functions.</span></span>  
  
<span data-ttu-id="82892-112">`GROUPPARTITION` es un operador agregado especial que retiene una referencia al conjunto de entrada agrupado.</span><span class="sxs-lookup"><span data-stu-id="82892-112">`GROUPPARTITION` is a special aggregate operator that holds a reference to the grouped input set.</span></span> <span data-ttu-id="82892-113">Esta referencia se puede utilizar en cualquier parte de la consulta donde GROUP BY se encuentre dentro del ámbito.</span><span class="sxs-lookup"><span data-stu-id="82892-113">This reference can be used anywhere in the query where GROUP BY is in scope.</span></span> <span data-ttu-id="82892-114">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="82892-114">For example:</span></span>
  
```sql  
SELECT p, GroupPartition(ol.Quantity) FROM LOB.OrderLines AS ol GROUP BY ol.Product AS p
```  
  
 <span data-ttu-id="82892-115">Con un `GROUP BY`normal, se ocultan los resultados de la agrupación.</span><span class="sxs-lookup"><span data-stu-id="82892-115">With a regular `GROUP BY`, the results of the grouping are hidden.</span></span> <span data-ttu-id="82892-116">Los resultados solo pueden utilizarse en una función de agregado.</span><span class="sxs-lookup"><span data-stu-id="82892-116">You can only use the results in an aggregate function.</span></span> <span data-ttu-id="82892-117">Para ver los resultados de la agrupación, tiene que poner en correlación los resultados de la agrupación y el conjunto de entrada mediante una subconsulta.</span><span class="sxs-lookup"><span data-stu-id="82892-117">In order to see the results of the grouping, you have to correlate the results of the grouping and the input set by using a subquery.</span></span> <span data-ttu-id="82892-118">Las dos consultas siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="82892-118">The following two queries are equivalent:</span></span>  
  
```sql  
SELET p, (SELECT q FROM GroupPartition(ol.Quantity) AS q) FROM LOB.OrderLines AS ol GROUP BY ol.Product AS p
SELECT p, (SELECT ol.Quantity AS q FROM LOB.OrderLines AS ol2 WHERE ol2.Product = p) FROM LOB.OrderLines AS ol GROUP BY ol.Product AS p
```  
  
 <span data-ttu-id="82892-119">Tal y como se ve en el ejemplo, el operador agregado GROUPPARTITION facilita la obtención de una referencia al conjunto de entrada después de la agrupación.</span><span class="sxs-lookup"><span data-stu-id="82892-119">As seen from the example, the GROUPPARTITION aggregate operator makes it easier to get a reference to the input set after the grouping.</span></span>  
  
 <span data-ttu-id="82892-120">El operador GROUPPARTITION puede especificar cualquier expresión [!INCLUDE[esql](../../../../../../includes/esql-md.md)] en la entrada del operador cuando se utiliza el parámetro `expression` .</span><span class="sxs-lookup"><span data-stu-id="82892-120">The GROUPPARTITION operator can specify any [!INCLUDE[esql](../../../../../../includes/esql-md.md)] expression in the operator input when you use the `expression` parameter.</span></span>  
  
 <span data-ttu-id="82892-121">Por ejemplo todas las expresiones de entrada siguientes a la partición de grupo son válidas:</span><span class="sxs-lookup"><span data-stu-id="82892-121">For instance all of the following input expressions to the group partition are valid:</span></span>  
  
```sql  
SELECT groupkey, GroupPartition(b) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey
SELECT groupkey, GroupPartition(1) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey
SELECT groupkey, GroupPartition(a + b) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey
SELECT groupkey, GroupPartition({a + b}) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey  
SELECT groupkey, GroupPartition({42}) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey  
SELECT groupkey, GroupPartition(b > a) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey  
```  
  
## <a name="example"></a><span data-ttu-id="82892-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="82892-122">Example</span></span>  
 <span data-ttu-id="82892-123">En el ejemplo siguiente se muestra cómo utilizar la cláusula GROUPPARTITION con la cláusula GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="82892-123">The following example shows how to use the GROUPPARTITION clause with the GROUP BY clause.</span></span> <span data-ttu-id="82892-124">La cláusula GROUP BY agrupa las entidades `SalesOrderHeader` por `Contact`.</span><span class="sxs-lookup"><span data-stu-id="82892-124">The GROUP BY clause groups `SalesOrderHeader` entities by their `Contact`.</span></span> <span data-ttu-id="82892-125">A continuación, la cláusula GROUPPARTITION proyecta la propiedad `TotalDue` para cada grupo, produciendo una colección de decimales.</span><span class="sxs-lookup"><span data-stu-id="82892-125">The GROUPPARTITION clause then projects the `TotalDue` property for each group, resulting in a collection of decimals.</span></span>  
  
 [!code-sql[DP EntityServices Concepts#Collection_GroupPartition](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#collection_grouppartition)]
