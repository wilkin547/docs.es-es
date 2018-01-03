---
title: GROUP BY (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf4f4972-4724-4945-ba44-943a08549139
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 877478ae953dd5867077608a5e93035b77bcee0a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="group-by-entity-sql"></a><span data-ttu-id="f2145-102">GROUP BY (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="f2145-102">GROUP BY (Entity SQL)</span></span>
<span data-ttu-id="f2145-103">Especifica los grupos en los que se van a colocar los objetos devueltos por una expresión de consulta ([SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)).</span><span class="sxs-lookup"><span data-stu-id="f2145-103">Specifies groups into which objects returned by a query ([SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)) expression are to be placed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2145-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f2145-104">Syntax</span></span>  
  
```  
[ GROUP BY aliasedExpression [ ,...n ] ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="f2145-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="f2145-105">Arguments</span></span>  
 `aliasedExpression`  
 <span data-ttu-id="f2145-106">Cualquier expresión de consulta válida en la que se realice una agrupación.</span><span class="sxs-lookup"><span data-stu-id="f2145-106">Any valid query expression on which grouping is performed.</span></span> <span data-ttu-id="f2145-107">`expression` puede ser una propiedad o una expresión no agregada que haga referencia a una propiedad devuelta por la cláusula FROM.</span><span class="sxs-lookup"><span data-stu-id="f2145-107">`expression` can be a property or a non-aggregate expression that references a property returned by the FROM clause.</span></span> <span data-ttu-id="f2145-108">Cada expresión de una cláusula GROUP BY se debe evaluar como un tipo en el que se pueda comparar la igualdad.</span><span class="sxs-lookup"><span data-stu-id="f2145-108">Each expression in a GROUP BY clause must evaluate to a type that can be compared for equality.</span></span> <span data-ttu-id="f2145-109">Estos tipos son generalmente primitivos escalares, como números, cadenas y fechas.</span><span class="sxs-lookup"><span data-stu-id="f2145-109">These types are generally scalar primitives such as numbers, strings, and dates.</span></span> <span data-ttu-id="f2145-110">No se puede agrupar por una colección.</span><span class="sxs-lookup"><span data-stu-id="f2145-110">You cannot group by a collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2145-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f2145-111">Remarks</span></span>  
 <span data-ttu-id="f2145-112">Si se incluyen funciones de agregado en la cláusula SELECT \<lista de selección >, GROUP BY calcula un valor de resumen para cada grupo.</span><span class="sxs-lookup"><span data-stu-id="f2145-112">If aggregate functions are included in the SELECT clause \<select list>, GROUP BY calculates a summary value for each group.</span></span> <span data-ttu-id="f2145-113">Cuando se especifica GROUP BY, cada nombre de propiedad que esté en una expresión no agregada de la lista de selección se debe incluir en la lista de GROUP BY, o la expresión GROUP BY debe coincidir exactamente con la expresión de la lista de selección.</span><span class="sxs-lookup"><span data-stu-id="f2145-113">When GROUP BY is specified, either each property name in any nonaggregate expression in the select list should be included in the GROUP BY list, or the GROUP BY expression must exactly match the select list expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f2145-114">Si no se especifica la cláusula ORDER BY, los grupos devueltos por la cláusula GROUP BY no estarán en un orden concreto.</span><span class="sxs-lookup"><span data-stu-id="f2145-114">If the ORDER BY clause is not specified, groups returned by the GROUP BY clause are not in any particular order.</span></span> <span data-ttu-id="f2145-115">Se recomienda utilizar siempre la cláusula ORDER BY para especificar un orden concreto de los datos.</span><span class="sxs-lookup"><span data-stu-id="f2145-115">To specify a particular ordering of the data, we recommend that you always use the ORDER BY clause.</span></span>  
  
 <span data-ttu-id="f2145-116">Cuando se especifica una cláusula GROUP BY, ya sea explícita o implícitamente (por ejemplo, mediante una cláusula HAVING en la consulta), se oculta el ámbito actual y se introduce un nuevo ámbito.</span><span class="sxs-lookup"><span data-stu-id="f2145-116">When a GROUP BY clause is specified, either explicitly or implicitly (for example, by a HAVING clause in the query), the current scope is hidden, and a new scope is introduced.</span></span>  
  
 <span data-ttu-id="f2145-117">Las cláusulas SELECT, HAVING y ORDER BY ya no podrán hacer referencia a los nombres de elementos especificados en la cláusula FROM.</span><span class="sxs-lookup"><span data-stu-id="f2145-117">The SELECT clause, the HAVING clause, and the ORDER BY clause will no longer be able to refer to element names specified in the FROM clause.</span></span> <span data-ttu-id="f2145-118">solo se puede hacer referencia a las propias expresiones de agrupación.</span><span class="sxs-lookup"><span data-stu-id="f2145-118">You can only refer to the grouping expressions themselves.</span></span> <span data-ttu-id="f2145-119">Para ello, puede asignar un nuevo nombre (alias) a cada expresión de agrupación.</span><span class="sxs-lookup"><span data-stu-id="f2145-119">To do this, you can assign new names (aliases) to each grouping expression.</span></span> <span data-ttu-id="f2145-120">Si no se especifica ningún alias para una expresión de agrupación, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] intentará generar uno utilizando las reglas de generación de alias, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f2145-120">If no alias is specified for a grouping expression, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to generate one by using the alias generation rules, as illustrated in the following example.</span></span>  
  
 `SELECT g1, g2, ...gn FROM c as c1`  
  
 `GROUP BY e1 as g1, e2 as g2, ...en as gn`  
  
 <span data-ttu-id="f2145-121">Las expresiones de la cláusula GROUP BY no pueden hacer referencia a nombres definidos anteriormente en la misma cláusula GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="f2145-121">Expressions in the GROUP BY clause cannot refer to names defined earlier in the same GROUP BY clause.</span></span>  
  
 <span data-ttu-id="f2145-122">Además de los nombres de agrupación, también se pueden especificar agregados en las cláusulas SELECT, HAVING y ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="f2145-122">In addition to grouping names, you can also specify aggregates in the SELECT clause, HAVING clause, and the ORDER BY clause.</span></span> <span data-ttu-id="f2145-123">Un agregado contiene una expresión que se evalúa para cada elemento del grupo.</span><span class="sxs-lookup"><span data-stu-id="f2145-123">An aggregate contains an expression that is evaluated for each element of the group.</span></span> <span data-ttu-id="f2145-124">El operador agregado reduce los valores de todas estas expresiones (normalmente, pero no siempre, en un valor único).</span><span class="sxs-lookup"><span data-stu-id="f2145-124">The aggregate operator reduces the values of all these expressions (usually, but not always, into a single value).</span></span> <span data-ttu-id="f2145-125">La expresión agregada puede realizar referencias a los nombres de elemento originales visibles en el ámbito primario, o a cualquiera de los nuevos nombres introducido por la propia cláusula GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="f2145-125">The aggregate expression can make references to the original element names visible in the parent scope, or to any of the new names introduced by the GROUP BY clause itself.</span></span> <span data-ttu-id="f2145-126">Aunque los agregados aparecen en las cláusulas SELECT, HAVING y ORDER BY, se evalúan realmente en el mismo ámbito que las expresiones de agrupación, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f2145-126">Although the aggregates appear in the SELECT clause, HAVING clause, and ORDER BY clause, they are actually evaluated under the same scope as the grouping expressions, as illustrated in the following example.</span></span>  
  
 `SELECT name, sum(o.Price * o.Quantity) as total`  
  
 `FROM orderLines as o`  
  
 `GROUP BY o.Product as name`  
  
 <span data-ttu-id="f2145-127">Esta consulta utiliza la cláusula GROUP BY para generar un informe del costo de todos los productos pedidos, desglosado por producto.</span><span class="sxs-lookup"><span data-stu-id="f2145-127">This query uses the GROUP BY clause to produce a report of the cost of all products ordered, broken down by product.</span></span> <span data-ttu-id="f2145-128">Asigna el nombre `name` al producto como parte de la expresión de agrupación y, a continuación, hace referencia a ese nombre en la lista SELECT.</span><span class="sxs-lookup"><span data-stu-id="f2145-128">It gives the name `name` to the product as part of the grouping expression, and then references that name in the SELECT list.</span></span> <span data-ttu-id="f2145-129">También especifica el valor `sum` agregado en la lista SELECT que hace referencia internamente al precio y la cantidad de la línea de pedidos.</span><span class="sxs-lookup"><span data-stu-id="f2145-129">It also specifies the aggregate `sum` in the SELECT list that internally references the price and quantity of the order line.</span></span>  
  
 <span data-ttu-id="f2145-130">Cada expresión de clave GROUP BY debe tener como mínimo una referencia al ámbito de entrada:</span><span class="sxs-lookup"><span data-stu-id="f2145-130">Each GROUP By key expression must have at least one reference to the input scope:</span></span>  
  
```  
SELECT FROM Persons as P  
GROUP BY Q + P   -- GOOD  
GROUP BY Q   -- BAD  
GROUP BY 1   -- BAD, a constant is not allowed  
```  
  
 <span data-ttu-id="f2145-131">Para obtener un ejemplo de cómo se usa GROUP BY, vea [HAVING](../../../../../../docs/framework/data/adonet/ef/language-reference/having-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="f2145-131">For an example of using GROUP BY, see [HAVING](../../../../../../docs/framework/data/adonet/ef/language-reference/having-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2145-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f2145-132">Example</span></span>  
 <span data-ttu-id="f2145-133">La consulta de Entity SQL siguiente utiliza el operador GROUP BY para especificar los grupos en los que una consulta devuelve los objetos.</span><span class="sxs-lookup"><span data-stu-id="f2145-133">The following Entity SQL query uses the GROUP BY operator to specify groups into which objects are returned by a query.</span></span> <span data-ttu-id="f2145-134">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="f2145-134">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="f2145-135">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="f2145-135">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="f2145-136">Siga el procedimiento de [Cómo: ejecutar una consulta que muestra los resultados PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="f2145-136">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="f2145-137">Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="f2145-137">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#GROUPBY](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#groupby)]  
  
## <a name="see-also"></a><span data-ttu-id="f2145-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2145-138">See Also</span></span>  
 [<span data-ttu-id="f2145-139">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="f2145-139">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="f2145-140">Expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="f2145-140">Query Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
