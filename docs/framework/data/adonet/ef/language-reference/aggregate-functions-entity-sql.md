---
description: 'Más información sobre: funciones de agregado (Entity SQL)'
title: Funciones de agregado (Entity SQL)
ms.date: 03/30/2017
ms.assetid: acfd3149-f519-4c6e-8fe1-b21d243a0e58
ms.openlocfilehash: 077f0f103e739fe893b8aabff38b03e3ef8ebd96
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697262"
---
# <a name="aggregate-functions-entity-sql"></a><span data-ttu-id="54920-103">Funciones de agregado (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="54920-103">Aggregate Functions (Entity SQL)</span></span>

<span data-ttu-id="54920-104">Un agregado es una construcción de lenguaje que comprime una colección en una propiedad escalar como parte de una operación de grupo.</span><span class="sxs-lookup"><span data-stu-id="54920-104">An aggregate is a language construct that condenses a collection into a scalar as a part of a group operation.</span></span> <span data-ttu-id="54920-105">Los agregados de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tienen dos formas:</span><span class="sxs-lookup"><span data-stu-id="54920-105">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] aggregates come in two forms:</span></span>  
  
- [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="54920-106">funciones de colección que se pueden usar en cualquier parte de una expresión.</span><span class="sxs-lookup"><span data-stu-id="54920-106">collection functions that may be used anywhere in an expression.</span></span> <span data-ttu-id="54920-107">Esto incluye el uso de funciones de agregado en proyecciones y predicados que actúan en colecciones.</span><span class="sxs-lookup"><span data-stu-id="54920-107">This includes using aggregate functions in projections and predicates that act on collections.</span></span> <span data-ttu-id="54920-108">Las funciones de colección constituyen el modo preferido de especificar agregados en [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="54920-108">Collection functions are the preferred mode of specifying aggregates in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
- <span data-ttu-id="54920-109">Agregados basados en grupos en expresiones de consulta que tienen una cláusula GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="54920-109">Group aggregates in query expressions that have a GROUP BY clause.</span></span> <span data-ttu-id="54920-110">Como en Transact-SQL, los agregados de grupo aceptan DISTINCt y ALL como modificadores para la entrada de agregado.</span><span class="sxs-lookup"><span data-stu-id="54920-110">As in Transact-SQL, group aggregates accept DISTINCT and ALL as modifiers to the aggregate input.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="54920-111">primero intenta interpretar una expresión como una función de colección y si la expresión está en el contexto de una expresión SELECT, la interpreta como un agregado de grupo.</span><span class="sxs-lookup"><span data-stu-id="54920-111">first tries to interpret an expression as a collection function and if the expression is in the context of a SELECT expression it interprets it as a group aggregate.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="54920-112">define un operador agregado especial denominado [GROUPPARTITION](grouppartition-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="54920-112">defines a special aggregate operator called [GROUPPARTITION](grouppartition-entity-sql.md).</span></span> <span data-ttu-id="54920-113">Este operador permite obtener una referencia al conjunto de entrada agrupado.</span><span class="sxs-lookup"><span data-stu-id="54920-113">This operator enables you to get a reference to the grouped input set.</span></span> <span data-ttu-id="54920-114">Esto permite más consultas de agrupación avanzadas, donde los resultados de la cláusula GROUP BY se pueden utilizar en lugares distintos de las funciones de colección o los agregados de grupo.</span><span class="sxs-lookup"><span data-stu-id="54920-114">This allows more advanced grouping queries, where the results of the GROUP BY clause can be used in places other than group aggregate or collection functions.</span></span>  
  
## <a name="collection-functions"></a><span data-ttu-id="54920-115">Funciones de colección</span><span class="sxs-lookup"><span data-stu-id="54920-115">Collection Functions</span></span>  

 <span data-ttu-id="54920-116">Las funciones de colección operan en colecciones y devuelven un valor escalar.</span><span class="sxs-lookup"><span data-stu-id="54920-116">Collection functions operate on collections and return a scalar value.</span></span> <span data-ttu-id="54920-117">Por ejemplo, si `orders` es una colección de todos los pedidos (`orders`), puede calcular la fecha de entrega más reciente con la expresión siguiente:</span><span class="sxs-lookup"><span data-stu-id="54920-117">For example, if `orders` is a collection of all `orders`, you can calculate the earliest ship date with the following expression:</span></span>  
  
 `min(select value o.ShipDate from LOB.Orders as o)`  
  
## <a name="group-aggregates"></a><span data-ttu-id="54920-118">Agregados basados en grupo</span><span class="sxs-lookup"><span data-stu-id="54920-118">Group Aggregates</span></span>  

 <span data-ttu-id="54920-119">Los agregados basados en un grupo se calculan sobre un resultado de grupo según define la cláusula GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="54920-119">Group aggregates are calculated over a group result as defined by the GROUP BY clause.</span></span> <span data-ttu-id="54920-120">La cláusula GROUP BY divide los datos en grupos.</span><span class="sxs-lookup"><span data-stu-id="54920-120">The GROUP BY clause partitions data  into groups.</span></span> <span data-ttu-id="54920-121">Para cada grupo del resultado, se aplica la función de agregado y se calcula un agregado diferente utilizando los elementos de cada grupo como entradas del cálculo del agregado.</span><span class="sxs-lookup"><span data-stu-id="54920-121">For each group in the result, the aggregate function is applied and a separate aggregate is calculated by using the elements in each group as inputs to the aggregate calculation.</span></span> <span data-ttu-id="54920-122">Cuando se usa una cláusula GROUP BY en una expresión SELECT, solo pueden estar presentes en la cláusula ORDER BY, HAVING o de la proyección los nombres de la expresión de agrupamiento, los agregados o las expresiones constantes.</span><span class="sxs-lookup"><span data-stu-id="54920-122">When a GROUP BY clause is used in a SELECT expression, only grouping expression names, aggregates, or constant expressions may be present in the projection, HAVING, or ORDER BY clause.</span></span>  
  
 <span data-ttu-id="54920-123">En el ejemplo siguiente se calcula la cantidad promedio pedida de cada producto.</span><span class="sxs-lookup"><span data-stu-id="54920-123">The following example calculates the average quantity ordered for each product.</span></span>  
  
 `select p, avg(ol.Quantity) from LOB.OrderLines as ol`  
  
 `group by ol.Product as p`  
  
 <span data-ttu-id="54920-124">Es posible tener un agregado basado en un grupo sin una cláusula GROUP BY explícita en la expresión SELECT.</span><span class="sxs-lookup"><span data-stu-id="54920-124">It is possible to have a group aggregate without an explicit GROUP BY clause in the SELECT expression.</span></span> <span data-ttu-id="54920-125">Todos los elementos se tratarán como un grupo único, como en el caso de especificar una agrupación basada en una constante.</span><span class="sxs-lookup"><span data-stu-id="54920-125">All elements will be treated as a single group, equivalent to the case of specifying a grouping based on a constant.</span></span>  
  
 `select avg(ol.Quantity) from LOB.OrderLines as ol`  
  
 `select avg(ol.Quantity) from LOB.OrderLines as ol group by 1`  
  
 <span data-ttu-id="54920-126">Las expresiones usadas en la clausula GROUP BY se evalúan usando el mismo ámbito de resolución de nombres que sería visible para la expresión de la cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="54920-126">Expressions used in the GROUP BY clause are evaluated by using the same name-resolution scope that would be visible to the WHERE clause expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54920-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="54920-127">See also</span></span>

- [<span data-ttu-id="54920-128">Funciones</span><span class="sxs-lookup"><span data-stu-id="54920-128">Functions</span></span>](functions-entity-sql.md)
