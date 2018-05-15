---
title: GROUPPARTITION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: d0482e9b-086c-451c-9dfa-ccb024a9efb6
ms.openlocfilehash: 9f0f917380e6422da753282216529580f87f1a1a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="grouppartition-entity-sql"></a><span data-ttu-id="f6f46-102">GROUPPARTITION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="f6f46-102">GROUPPARTITION (Entity SQL)</span></span>
<span data-ttu-id="f6f46-103">Devuelve una colección de valores de argumento que se proyecta a partir de la partición de grupo actual con la que está relacionado el agregado.</span><span class="sxs-lookup"><span data-stu-id="f6f46-103">Returns a collection of argument values that are projected off the current group partition to which the aggregate is related.</span></span> <span data-ttu-id="f6f46-104">El agregado `GroupPartition` es un agregado basado en un grupo y no tiene ningún formulario basado en una colección.</span><span class="sxs-lookup"><span data-stu-id="f6f46-104">The `GroupPartition` aggregate is a group-based aggregate and has no collection-based form.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6f46-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f6f46-105">Syntax</span></span>  
  
```  
GROUPPARTITION( [ALL|DISTINCT] expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="f6f46-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="f6f46-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="f6f46-107">Cualquier expresión [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f6f46-107">Any [!INCLUDE[esql](../../../../../../includes/esql-md.md)] expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6f46-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f6f46-108">Remarks</span></span>  
 <span data-ttu-id="f6f46-109">La consulta siguiente genera una lista de productos y una colección de cantidades de la línea de pedidos por cada producto:</span><span class="sxs-lookup"><span data-stu-id="f6f46-109">The following query produces a list of products and a collection of order line quantities per each product:</span></span>  
  
```  
select p, GroupPartition(ol.Quantity) from LOB.OrderLines as ol  
  group by ol.Product as p  
```  
  
 <span data-ttu-id="f6f46-110">Las dos consultas siguientes son semánticamente iguales:</span><span class="sxs-lookup"><span data-stu-id="f6f46-110">The following two queries are semantically equal:</span></span>  
  
```  
select p, Sum(GroupPartition(ol.Quantity)) from LOB.OrderLines as ol  
  group by ol.Product as p  
select p, Sum(ol.Quantity) from LOB.OrderLines as ol  
  group by ol.Product as p  
```  
  
 <span data-ttu-id="f6f46-111">El operador `GROUPPARTITION` se puede utilizar junto con funciones de agregado definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="f6f46-111">The `GROUPPARTITION` operator can be used in conjunction with user-defined aggregate functions.</span></span>  
  
 <span data-ttu-id="f6f46-112">`GROUPPARTITION` es un operador agregado especial que retiene una referencia al conjunto de entrada agrupado.</span><span class="sxs-lookup"><span data-stu-id="f6f46-112">`GROUPPARTITION` is a special aggregate operator that holds a reference to the grouped input set.</span></span> <span data-ttu-id="f6f46-113">Esta referencia se puede utilizar en cualquier parte de la consulta donde GROUP BY se encuentre dentro del ámbito.</span><span class="sxs-lookup"><span data-stu-id="f6f46-113">This reference can be used anywhere in the query where GROUP BY is in scope.</span></span> <span data-ttu-id="f6f46-114">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="f6f46-114">For example,</span></span>  
  
```  
select p, GroupPartition(ol.Quantity) from LOB.OrderLines as ol group by ol.Product as p  
```  
  
 <span data-ttu-id="f6f46-115">Con un GROUP BY normal, se ocultan los resultados de la agrupación.</span><span class="sxs-lookup"><span data-stu-id="f6f46-115">With a regular GROUP BY, the results of the grouping are hidden.</span></span> <span data-ttu-id="f6f46-116">Los resultados solo pueden utilizarse en una función de agregado.</span><span class="sxs-lookup"><span data-stu-id="f6f46-116">You can only use the results in an aggregate function.</span></span> <span data-ttu-id="f6f46-117">Para ver los resultados de la agrupación, tiene que poner en correlación los resultados de la agrupación y el conjunto de entrada mediante una subconsulta.</span><span class="sxs-lookup"><span data-stu-id="f6f46-117">In order to see the results of the grouping, you have to correlate the results of the grouping and the input set by using a subquery.</span></span> <span data-ttu-id="f6f46-118">Las dos consultas siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="f6f46-118">The following two queries are equivalent:</span></span>  
  
```  
select p, (select q from GroupPartition(ol.Quantity) as q) from LOB.OrderLines as ol group by ol.Product as p  
select p, (select ol.Quantity as q from LOB.OrderLines as ol2 where ol2.Product = p) from LOB.OrderLines as ol group by ol.Product as p  
```  
  
 <span data-ttu-id="f6f46-119">Tal y como se ve en el ejemplo, el operador agregado GROUPPARTITION facilita la obtención de una referencia al conjunto de entrada después de la agrupación.</span><span class="sxs-lookup"><span data-stu-id="f6f46-119">As seen from the example, the GROUPPARTITION aggregate operator makes it easier to get a reference to the input set after the grouping.</span></span>  
  
 <span data-ttu-id="f6f46-120">El operador GROUPPARTITION puede especificar cualquier expresión [!INCLUDE[esql](../../../../../../includes/esql-md.md)] en la entrada del operador cuando se utiliza el parámetro `expression` .</span><span class="sxs-lookup"><span data-stu-id="f6f46-120">The GROUPPARTITION operator can specify any [!INCLUDE[esql](../../../../../../includes/esql-md.md)] expression in the operator input when you use the `expression` parameter.</span></span>  
  
 <span data-ttu-id="f6f46-121">Por ejemplo todas las expresiones de entrada siguientes a la partición de grupo son válidas:</span><span class="sxs-lookup"><span data-stu-id="f6f46-121">For instance all of the following input expressions to the group partition are valid:</span></span>  
  
```  
select groupkey, GroupPartition(b) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition(1) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition(a + b) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition({a + b}) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition({42}) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition(b > a) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
```  
  
## <a name="example"></a><span data-ttu-id="f6f46-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f6f46-122">Example</span></span>  
 <span data-ttu-id="f6f46-123">En el ejemplo siguiente se muestra cómo utilizar la cláusula GROUPPARTITION con la cláusula GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="f6f46-123">The following example shows how to use the GROUPPARTITION clause with the GROUP BY clause.</span></span> <span data-ttu-id="f6f46-124">La cláusula GROUP BY agrupa las entidades `SalesOrderHeader` por `Contact`.</span><span class="sxs-lookup"><span data-stu-id="f6f46-124">The GROUP BY clause groups `SalesOrderHeader` entities by their `Contact`.</span></span> <span data-ttu-id="f6f46-125">A continuación, la cláusula GROUPPARTITION proyecta la propiedad `TotalDue` para cada grupo, produciendo una colección de decimales.</span><span class="sxs-lookup"><span data-stu-id="f6f46-125">The GROUPPARTITION clause then projects the `TotalDue` property for each group, resulting in a collection of decimals.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#Collection_GroupPartition](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#collection_grouppartition)]
