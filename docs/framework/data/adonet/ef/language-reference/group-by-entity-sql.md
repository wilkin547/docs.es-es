---
description: 'Más información acerca de: AGRUPAr por (Entity SQL)'
title: GROUP BY (Entity SQL)
ms.date: 03/30/2017
ms.assetid: cf4f4972-4724-4945-ba44-943a08549139
ms.openlocfilehash: 16328b46a59a2a07622cda43dce30d8b4f1d3dde
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696937"
---
# <a name="group-by-entity-sql"></a><span data-ttu-id="dbc5b-103">GROUP BY (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="dbc5b-103">GROUP BY (Entity SQL)</span></span>

<span data-ttu-id="dbc5b-104">Especifica los grupos en los que se van a colocar los objetos devueltos por una expresión de consulta ([SELECT](select-entity-sql.md)).</span><span class="sxs-lookup"><span data-stu-id="dbc5b-104">Specifies groups into which objects returned by a query ([SELECT](select-entity-sql.md)) expression are to be placed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbc5b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dbc5b-105">Syntax</span></span>  
  
```sql  
[ GROUP BY aliasedExpression [ ,...n ] ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="dbc5b-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="dbc5b-106">Arguments</span></span>  

 `aliasedExpression`  
 <span data-ttu-id="dbc5b-107">Cualquier expresión de consulta válida en la que se realice una agrupación.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-107">Any valid query expression on which grouping is performed.</span></span> <span data-ttu-id="dbc5b-108">`expression` puede ser una propiedad o una expresión no agregada que haga referencia a una propiedad devuelta por la cláusula FROM.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-108">`expression` can be a property or a non-aggregate expression that references a property returned by the FROM clause.</span></span> <span data-ttu-id="dbc5b-109">Cada expresión de una cláusula GROUP BY se debe evaluar como un tipo en el que se pueda comparar la igualdad.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-109">Each expression in a GROUP BY clause must evaluate to a type that can be compared for equality.</span></span> <span data-ttu-id="dbc5b-110">Estos tipos son generalmente primitivos escalares, como números, cadenas y fechas.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-110">These types are generally scalar primitives such as numbers, strings, and dates.</span></span> <span data-ttu-id="dbc5b-111">No se puede agrupar por una colección.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-111">You cannot group by a collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dbc5b-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="dbc5b-112">Remarks</span></span>  

 <span data-ttu-id="dbc5b-113">Si se incluyen funciones de agregado en la cláusula SELECT \<select list> , Group by calcula un valor de resumen para cada grupo.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-113">If aggregate functions are included in the SELECT clause \<select list>, GROUP BY calculates a summary value for each group.</span></span> <span data-ttu-id="dbc5b-114">Cuando se especifica GROUP BY, cada nombre de propiedad que esté en una expresión no agregada de la lista de selección se debe incluir en la lista de GROUP BY, o la expresión GROUP BY debe coincidir exactamente con la expresión de la lista de selección.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-114">When GROUP BY is specified, either each property name in any nonaggregate expression in the select list should be included in the GROUP BY list, or the GROUP BY expression must exactly match the select list expression.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dbc5b-115">Si no se especifica la cláusula ORDER BY, los grupos devueltos por la cláusula GROUP BY no estarán en un orden concreto.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-115">If the ORDER BY clause is not specified, groups returned by the GROUP BY clause are not in any particular order.</span></span> <span data-ttu-id="dbc5b-116">Se recomienda utilizar siempre la cláusula ORDER BY para especificar un orden concreto de los datos.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-116">To specify a particular ordering of the data, we recommend that you always use the ORDER BY clause.</span></span>  
  
 <span data-ttu-id="dbc5b-117">Cuando se especifica una cláusula GROUP BY, ya sea explícita o implícitamente (por ejemplo, mediante una cláusula HAVING en la consulta), se oculta el ámbito actual y se introduce un nuevo ámbito.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-117">When a GROUP BY clause is specified, either explicitly or implicitly (for example, by a HAVING clause in the query), the current scope is hidden, and a new scope is introduced.</span></span>  
  
 <span data-ttu-id="dbc5b-118">Las cláusulas SELECT, HAVING y ORDER BY ya no podrán hacer referencia a los nombres de elementos especificados en la cláusula FROM.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-118">The SELECT clause, the HAVING clause, and the ORDER BY clause will no longer be able to refer to element names specified in the FROM clause.</span></span> <span data-ttu-id="dbc5b-119">solo se puede hacer referencia a las propias expresiones de agrupación.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-119">You can only refer to the grouping expressions themselves.</span></span> <span data-ttu-id="dbc5b-120">Para ello, puede asignar un nuevo nombre (alias) a cada expresión de agrupación.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-120">To do this, you can assign new names (aliases) to each grouping expression.</span></span> <span data-ttu-id="dbc5b-121">Si no se especifica ningún alias para una expresión de agrupación, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] intentará generar uno utilizando las reglas de generación de alias, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-121">If no alias is specified for a grouping expression, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to generate one by using the alias generation rules, as illustrated in the following example.</span></span>  
  
 `SELECT g1, g2, ...gn FROM c as c1`  
  
 `GROUP BY e1 as g1, e2 as g2, ...en as gn`  
  
 <span data-ttu-id="dbc5b-122">Las expresiones de la cláusula GROUP BY no pueden hacer referencia a nombres definidos anteriormente en la misma cláusula GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-122">Expressions in the GROUP BY clause cannot refer to names defined earlier in the same GROUP BY clause.</span></span>  
  
 <span data-ttu-id="dbc5b-123">Además de los nombres de agrupación, también se pueden especificar agregados en las cláusulas SELECT, HAVING y ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-123">In addition to grouping names, you can also specify aggregates in the SELECT clause, HAVING clause, and the ORDER BY clause.</span></span> <span data-ttu-id="dbc5b-124">Un agregado contiene una expresión que se evalúa para cada elemento del grupo.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-124">An aggregate contains an expression that is evaluated for each element of the group.</span></span> <span data-ttu-id="dbc5b-125">El operador agregado reduce los valores de todas estas expresiones (normalmente, pero no siempre, en un valor único).</span><span class="sxs-lookup"><span data-stu-id="dbc5b-125">The aggregate operator reduces the values of all these expressions (usually, but not always, into a single value).</span></span> <span data-ttu-id="dbc5b-126">La expresión agregada puede realizar referencias a los nombres de elemento originales visibles en el ámbito primario, o a cualquiera de los nuevos nombres introducido por la propia cláusula GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-126">The aggregate expression can make references to the original element names visible in the parent scope, or to any of the new names introduced by the GROUP BY clause itself.</span></span> <span data-ttu-id="dbc5b-127">Aunque los agregados aparecen en las cláusulas SELECT, HAVING y ORDER BY, se evalúan realmente en el mismo ámbito que las expresiones de agrupación, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-127">Although the aggregates appear in the SELECT clause, HAVING clause, and ORDER BY clause, they are actually evaluated under the same scope as the grouping expressions, as illustrated in the following example.</span></span>  
  
 `SELECT name, sum(o.Price * o.Quantity) as total`  
  
 `FROM orderLines as o`  
  
 `GROUP BY o.Product as name`  
  
 <span data-ttu-id="dbc5b-128">Esta consulta utiliza la cláusula GROUP BY para generar un informe del costo de todos los productos pedidos, desglosado por producto.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-128">This query uses the GROUP BY clause to produce a report of the cost of all products ordered, broken down by product.</span></span> <span data-ttu-id="dbc5b-129">Asigna el nombre `name` al producto como parte de la expresión de agrupación y, a continuación, hace referencia a ese nombre en la lista SELECT.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-129">It gives the name `name` to the product as part of the grouping expression, and then references that name in the SELECT list.</span></span> <span data-ttu-id="dbc5b-130">También especifica el valor `sum` agregado en la lista SELECT que hace referencia internamente al precio y la cantidad de la línea de pedidos.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-130">It also specifies the aggregate `sum` in the SELECT list that internally references the price and quantity of the order line.</span></span>  
  
 <span data-ttu-id="dbc5b-131">Cada expresión de clave GROUP BY debe tener como mínimo una referencia al ámbito de entrada:</span><span class="sxs-lookup"><span data-stu-id="dbc5b-131">Each GROUP By key expression must have at least one reference to the input scope:</span></span>  
  
```sql  
SELECT FROM Persons as P  
GROUP BY Q + P   -- GOOD  
GROUP BY Q   -- BAD  
GROUP BY 1   -- BAD, a constant is not allowed  
```  
  
 <span data-ttu-id="dbc5b-132">Para obtener un ejemplo de cómo se usa GROUP BY, vea [HAVING](having-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="dbc5b-132">For an example of using GROUP BY, see [HAVING](having-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dbc5b-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dbc5b-133">Example</span></span>  

 <span data-ttu-id="dbc5b-134">La consulta de Entity SQL siguiente utiliza el operador GROUP BY para especificar los grupos en los que una consulta devuelve los objetos.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-134">The following Entity SQL query uses the GROUP BY operator to specify groups into which objects are returned by a query.</span></span> <span data-ttu-id="dbc5b-135">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="dbc5b-135">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="dbc5b-136">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="dbc5b-136">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="dbc5b-137">Siga el procedimiento descrito en [Cómo: ejecutar una consulta que devuelve resultados PrimitiveType](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="dbc5b-137">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="dbc5b-138">Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="dbc5b-138">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#GROUPBY](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#groupby)]  
  
## <a name="see-also"></a><span data-ttu-id="dbc5b-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="dbc5b-139">See also</span></span>

- [<span data-ttu-id="dbc5b-140">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="dbc5b-140">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="dbc5b-141">Expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="dbc5b-141">Query Expressions</span></span>](query-expressions-entity-sql.md)
