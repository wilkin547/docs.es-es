---
title: Funciones de agregado (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: acfd3149-f519-4c6e-8fe1-b21d243a0e58
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: ff9462b1a5a6f6f9f4614098c38bb5fab14a5203
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="aggregate-functions-entity-sql"></a><span data-ttu-id="4a71d-102">Funciones de agregado (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="4a71d-102">Aggregate Functions (Entity SQL)</span></span>
<span data-ttu-id="4a71d-103">Un agregado es una construcción de lenguaje que comprime una colección en una propiedad escalar como parte de una operación de grupo.</span><span class="sxs-lookup"><span data-stu-id="4a71d-103">An aggregate is a language construct that condenses a collection into a scalar as a part of a group operation.</span></span> <span data-ttu-id="4a71d-104">Los agregados de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tienen dos formas:</span><span class="sxs-lookup"><span data-stu-id="4a71d-104">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] aggregates come in two forms:</span></span>  
  
-   [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="4a71d-105">funciones de colección que se pueden usar en cualquier parte en una expresión.</span><span class="sxs-lookup"><span data-stu-id="4a71d-105"> collection functions that may be used anywhere in an expression.</span></span> <span data-ttu-id="4a71d-106">Esto incluye el uso de funciones de agregado en proyecciones y predicados que actúan en colecciones.</span><span class="sxs-lookup"><span data-stu-id="4a71d-106">This includes using aggregate functions in projections and predicates that act on collections.</span></span> <span data-ttu-id="4a71d-107">Las funciones de colección constituyen el modo preferido de especificar agregados en [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4a71d-107">Collection functions are the preferred mode of specifying aggregates in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
-   <span data-ttu-id="4a71d-108">Agregados basados en grupos en expresiones de consulta que tienen una cláusula GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="4a71d-108">Group aggregates in query expressions that have a GROUP BY clause.</span></span> <span data-ttu-id="4a71d-109">Como en [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], los agregados de grupo aceptan los modificadores DISTINCT y ALL como modificadores para la entrada agregada.</span><span class="sxs-lookup"><span data-stu-id="4a71d-109">As in [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], group aggregates accept DISTINCT and ALL as modifiers to the aggregate input.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="4a71d-110">primero intenta interpretar una expresión como una función de colección y, si la expresión es en el contexto de una expresión SELECT interpreta como un agregado de grupo.</span><span class="sxs-lookup"><span data-stu-id="4a71d-110"> first tries to interpret an expression as a collection function and if the expression is in the context of a SELECT expression it interprets it as a group aggregate.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="4a71d-111">define un operador agregado especial denominado [GROUPPARTITION](../../../../../../docs/framework/data/adonet/ef/language-reference/grouppartition-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="4a71d-111"> defines a special aggregate operator called [GROUPPARTITION](../../../../../../docs/framework/data/adonet/ef/language-reference/grouppartition-entity-sql.md).</span></span> <span data-ttu-id="4a71d-112">Este operador permite obtener una referencia al conjunto de entrada agrupado.</span><span class="sxs-lookup"><span data-stu-id="4a71d-112">This operator enables you to get a reference to the grouped input set.</span></span> <span data-ttu-id="4a71d-113">Esto permite más consultas de agrupación avanzadas, donde los resultados de la cláusula GROUP BY se pueden utilizar en lugares distintos de las funciones de colección o los agregados de grupo.</span><span class="sxs-lookup"><span data-stu-id="4a71d-113">This allows more advanced grouping queries, where the results of the GROUP BY clause can be used in places other than group aggregate or collection functions.</span></span>  
  
## <a name="collection-functions"></a><span data-ttu-id="4a71d-114">Funciones de colección</span><span class="sxs-lookup"><span data-stu-id="4a71d-114">Collection Functions</span></span>  
 <span data-ttu-id="4a71d-115">Las funciones de colección operan en colecciones y devuelven un valor escalar.</span><span class="sxs-lookup"><span data-stu-id="4a71d-115">Collection functions operate on collections and return a scalar value.</span></span> <span data-ttu-id="4a71d-116">Por ejemplo, si `orders` es una colección de todos los pedidos (`orders`), puede calcular la fecha de entrega más reciente con la expresión siguiente:</span><span class="sxs-lookup"><span data-stu-id="4a71d-116">For example, if `orders` is a collection of all `orders`, you can calculate the earliest ship date with the following expression:</span></span>  
  
 `min(select value o.ShipDate from LOB.Orders as o)`  
  
## <a name="group-aggregates"></a><span data-ttu-id="4a71d-117">Agregados basados en grupo</span><span class="sxs-lookup"><span data-stu-id="4a71d-117">Group Aggregates</span></span>  
 <span data-ttu-id="4a71d-118">Los agregados basados en un grupo se calculan sobre un resultado de grupo según define la cláusula GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="4a71d-118">Group aggregates are calculated over a group result as defined by the GROUP BY clause.</span></span> <span data-ttu-id="4a71d-119">La cláusula GROUP BY divide los datos en grupos.</span><span class="sxs-lookup"><span data-stu-id="4a71d-119">The GROUP BY clause partitions data  into groups.</span></span> <span data-ttu-id="4a71d-120">Para cada grupo del resultado, se aplica la función de agregado y se calcula un agregado diferente utilizando los elementos de cada grupo como entradas del cálculo del agregado.</span><span class="sxs-lookup"><span data-stu-id="4a71d-120">For each group in the result, the aggregate function is applied and a separate aggregate is calculated by using the elements in each group as inputs to the aggregate calculation.</span></span> <span data-ttu-id="4a71d-121">Cuando se usa una cláusula GROUP BY en una expresión SELECT, solo pueden estar presentes en la cláusula ORDER BY, HAVING o de la proyección los nombres de la expresión de agrupamiento, los agregados o las expresiones constantes.</span><span class="sxs-lookup"><span data-stu-id="4a71d-121">When a GROUP BY clause is used in a SELECT expression, only grouping expression names, aggregates, or constant expressions may be present in the projection, HAVING, or ORDER BY clause.</span></span>  
  
 <span data-ttu-id="4a71d-122">En el ejemplo siguiente se calcula la cantidad promedio pedida de cada producto.</span><span class="sxs-lookup"><span data-stu-id="4a71d-122">The following example calculates the average quantity ordered for each product.</span></span>  
  
 `select p, avg(ol.Quantity) from LOB.OrderLines as ol`  
  
 `group by ol.Product as p`  
  
 <span data-ttu-id="4a71d-123">Es posible tener un agregado basado en un grupo sin una cláusula GROUP BY explícita en la expresión SELECT.</span><span class="sxs-lookup"><span data-stu-id="4a71d-123">It is possible to have a group aggregate without an explicit GROUP BY clause in the SELECT expression.</span></span> <span data-ttu-id="4a71d-124">Todos los elementos se tratarán como un grupo único, como en el caso de especificar una agrupación basada en una constante.</span><span class="sxs-lookup"><span data-stu-id="4a71d-124">All elements will be treated as a single group, equivalent to the case of specifying a grouping based on a constant.</span></span>  
  
 `select avg(ol.Quantity) from LOB.OrderLines as ol`  
  
 `select avg(ol.Quantity) from LOB.OrderLines as ol group by 1`  
  
 <span data-ttu-id="4a71d-125">Las expresiones usadas en la clausula GROUP BY se evalúan usando el mismo ámbito de resolución de nombres que sería visible para la expresión de la cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="4a71d-125">Expressions used in the GROUP BY clause are evaluated by using the same name-resolution scope that would be visible to the WHERE clause expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a71d-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a71d-126">See Also</span></span>  
 [<span data-ttu-id="4a71d-127">Funciones</span><span class="sxs-lookup"><span data-stu-id="4a71d-127">Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)
