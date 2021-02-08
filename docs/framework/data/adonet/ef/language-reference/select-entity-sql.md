---
description: 'Más información acerca de: SELECT (Entity SQL)'
title: SELECT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 9a33bd0d-ded1-41e7-ba3c-305502755e3b
ms.openlocfilehash: 7feaf1d9a5101cb745e67afeba8d608104430e7f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791873"
---
# <a name="select-entity-sql"></a><span data-ttu-id="f1cee-103">SELECT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="f1cee-103">SELECT (Entity SQL)</span></span>

<span data-ttu-id="f1cee-104">Especifica los elementos devueltos por una consulta.</span><span class="sxs-lookup"><span data-stu-id="f1cee-104">Specifies the elements returned by a query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1cee-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f1cee-105">Syntax</span></span>  
  
```sql  
SELECT [ ALL | DISTINCT ] [ topSubclause ] aliasedExpr
      [{ , aliasedExpr }] FROM fromClause [ WHERE whereClause ] [ GROUP BY groupByClause [ HAVING havingClause ] ] [ ORDER BY orderByClause ]  
-- or  
SELECT VALUE [ ALL | DISTINCT ] [ topSubclause ] expr FROM fromClause [ WHERE whereClause ] [ GROUP BY groupByClause [ HAVING havingClause ] ] [ ORDER BY orderByClause  
```  
  
## <a name="arguments"></a><span data-ttu-id="f1cee-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="f1cee-106">Arguments</span></span>  

 <span data-ttu-id="f1cee-107">ALL</span><span class="sxs-lookup"><span data-stu-id="f1cee-107">ALL</span></span>  
 <span data-ttu-id="f1cee-108">Especifica que el conjunto de resultados puede incluir resultados duplicados.</span><span class="sxs-lookup"><span data-stu-id="f1cee-108">Specifies that duplicates can appear in the result set.</span></span> <span data-ttu-id="f1cee-109">ALL es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f1cee-109">ALL is the default.</span></span>  
  
 <span data-ttu-id="f1cee-110">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="f1cee-110">DISTINCT</span></span>  
 <span data-ttu-id="f1cee-111">Especifica que el conjunto de resultados solo puede incluir resultados únicos.</span><span class="sxs-lookup"><span data-stu-id="f1cee-111">Specifies that only unique results can appear in the result set.</span></span>  
  
 <span data-ttu-id="f1cee-112">VALOR</span><span class="sxs-lookup"><span data-stu-id="f1cee-112">VALUE</span></span>  
 <span data-ttu-id="f1cee-113">Solo permite que se especifique un elemento y no agrega un contenedor de filas.</span><span class="sxs-lookup"><span data-stu-id="f1cee-113">Allows only one item to be specified, and does not add on a row wrapper.</span></span>  
  
 `topSubclause`  
 <span data-ttu-id="f1cee-114">Cualquier expresión válida que indique el número de primeros resultados que ha de devolver la consulta, del tipo `top(expr)`.</span><span class="sxs-lookup"><span data-stu-id="f1cee-114">Any valid expression that indicates the number of first results to return from the query, of the form `top(expr)`.</span></span>  
  
 <span data-ttu-id="f1cee-115">El parámetro LIMIT del operador [order by](order-by-entity-sql.md) también permite seleccionar los primeros n elementos del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="f1cee-115">The LIMIT parameter of the [ORDER BY](order-by-entity-sql.md) operator also lets you select the first n items in the result set.</span></span>  
  
 `aliasedExpr`  
 <span data-ttu-id="f1cee-116">Expresión del tipo:</span><span class="sxs-lookup"><span data-stu-id="f1cee-116">An expression of the form:</span></span>  
  
 <span data-ttu-id="f1cee-117">`expr` como `identifier` &#124; `expr`</span><span class="sxs-lookup"><span data-stu-id="f1cee-117">`expr` as `identifier` &#124; `expr`</span></span>  
  
 `expr`  
 <span data-ttu-id="f1cee-118">Literal o expresión.</span><span class="sxs-lookup"><span data-stu-id="f1cee-118">A literal or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1cee-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f1cee-119">Remarks</span></span>  

 <span data-ttu-id="f1cee-120">La cláusula SELECT se evalúa después de que se hayan evaluado las cláusulas [from](from-entity-sql.md), [Group by](group-by-entity-sql.md)y [having](having-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="f1cee-120">The SELECT clause is evaluated after the [FROM](from-entity-sql.md), [GROUP BY](group-by-entity-sql.md), and [HAVING](having-entity-sql.md) clauses have been evaluated.</span></span> <span data-ttu-id="f1cee-121">La cláusula SELECT solo puede hacer referencia a elementos que están actualmente en el ámbito (de la cláusula FROM o de ámbitos externos).</span><span class="sxs-lookup"><span data-stu-id="f1cee-121">The SELECT clause can only refer to items currently in-scope (from the FROM clause, or from outer scopes).</span></span> <span data-ttu-id="f1cee-122">Si se ha especificado una cláusula GROUP BY, la cláusula SELECT solo se permite para hacer referencia a los alias para las claves GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="f1cee-122">If a GROUP BY clause has been specified, the SELECT clause is only allowed to reference the aliases for the GROUP BY keys.</span></span> <span data-ttu-id="f1cee-123">La referencia a los elementos de la cláusula de FROM solo se permite en funciones de agregado.</span><span class="sxs-lookup"><span data-stu-id="f1cee-123">Referring to the FROM clause items is only permitted in aggregate functions.</span></span>  
  
 <span data-ttu-id="f1cee-124">La lista de una o más expresiones de consulta que siguen a la palabra clave SELECT se conoce como lista de selección o más formalmente como proyección.</span><span class="sxs-lookup"><span data-stu-id="f1cee-124">The list of one or more query expressions following the SELECT keyword is known as the select list, or more formally as the projection.</span></span> <span data-ttu-id="f1cee-125">La forma más general de proyección es una expresión de consulta única.</span><span class="sxs-lookup"><span data-stu-id="f1cee-125">The most general form of projection is a single query expression.</span></span> <span data-ttu-id="f1cee-126">Si selecciona un miembro `member1` de una colección `collection1`, generará una nueva colección de todos los valores de `member1` para cada objeto de `collection1`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f1cee-126">If you select a member `member1` from a collection `collection1`, you will produce a new collection of all the `member1` values for each object in `collection1`, as illustrated in the following example.</span></span>  
  
```sql  
SELECT collection1.member1 FROM collection1  
```  
  
 <span data-ttu-id="f1cee-127">Por ejemplo, si `customers` es una colección de tipo `Customer` que tiene una propiedad `Name` que es de tipo `string`, la acción de seleccionar `Name` de `customers` producirá una colección de cadenas, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f1cee-127">For example, if `customers` is a collection of type `Customer` that has a property `Name` that is of type `string`, selecting `Name` from `customers` will yield a collection of strings, as illustrated in the following example.</span></span>  
  
```sql  
SELECT customers.Name FROM customers AS c  
```  
  
 <span data-ttu-id="f1cee-128">También es posible utilizar la sintaxis de JOIN (FULL, INNER, LEFT, OUTER, ON y RIGHT).</span><span class="sxs-lookup"><span data-stu-id="f1cee-128">It is also possible to use JOIN syntax (FULL, INNER, LEFT, OUTER, ON, and RIGHT).</span></span> <span data-ttu-id="f1cee-129">ON se requiere para combinaciones internas y no se permite para combinaciones cruzadas.</span><span class="sxs-lookup"><span data-stu-id="f1cee-129">ON is required for inner joins and is nto allowed for cross joins.</span></span>  
  
## <a name="row-and-value-select-clauses"></a><span data-ttu-id="f1cee-130">Cláusulas de selección de fila y valor</span><span class="sxs-lookup"><span data-stu-id="f1cee-130">Row and Value Select Clauses</span></span>  

 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="f1cee-131">admite dos variantes de la cláusula SELECT.</span><span class="sxs-lookup"><span data-stu-id="f1cee-131">supports two variants of the SELECT clause.</span></span> <span data-ttu-id="f1cee-132">La primera variante, selección de fila, se identifica mediante la palabra clave SELECT y se puede utilizar para especificar uno o más valores que se deben proyectar. Dado que un contenedor de filas se agrega implícitamente alrededor de los valores devueltos, el resultado de la expresión de consulta siempre es un conjunto múltiple de filas.</span><span class="sxs-lookup"><span data-stu-id="f1cee-132">The first variant, row select, is identified by the SELECT keyword, and can be used to specify one or more values that should be projected out. Because a row wrapper is implicitly added around the values returned, the result of the query expression is always a multiset of rows.</span></span>  
  
 <span data-ttu-id="f1cee-133">Cada expresión de consulta en una selección de filas debe especificar un alias.</span><span class="sxs-lookup"><span data-stu-id="f1cee-133">Each query expression in a row select must specify an alias.</span></span> <span data-ttu-id="f1cee-134">Si no se especifica un alias,[!INCLUDE[esql](../../../../../../includes/esql-md.md)] intenta generar uno usando las reglas de generación de alias.</span><span class="sxs-lookup"><span data-stu-id="f1cee-134">If no alias is specified,[!INCLUDE[esql](../../../../../../includes/esql-md.md)] attempts to generate an alias by using the alias generation rules.</span></span>  
  
 <span data-ttu-id="f1cee-135">La otra variante de la cláusula SELECT, selección de valor, se identifica mediante la palabra clave SELECT VALUE.</span><span class="sxs-lookup"><span data-stu-id="f1cee-135">The other variant of the SELECT clause, value select, is identified by the SELECT VALUE keyword.</span></span> <span data-ttu-id="f1cee-136">Solo permite que se especifique un valor y no agrega un contenedor de filas.</span><span class="sxs-lookup"><span data-stu-id="f1cee-136">It allows only one value to be specified, and does not add a row wrapper.</span></span>  
  
 <span data-ttu-id="f1cee-137">Una selección de fila siempre se puede expresar en términos de VALUE SELECT, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f1cee-137">A row select is always expressible in terms of VALUE SELECT, as illustrated in the following example.</span></span>  
  
```sql  
SELECT 1 AS a, "abc" AS b FROM C  
SELECT VALUE ROW(1 AS a, "abc" AS b) FROM C
```  
  
## <a name="all-and-distinct-modifiers"></a><span data-ttu-id="f1cee-138">Modificadores All y Distinct</span><span class="sxs-lookup"><span data-stu-id="f1cee-138">All and Distinct Modifiers</span></span>  

 <span data-ttu-id="f1cee-139">Las dos variantes de SELECT en [!INCLUDE[esql](../../../../../../includes/esql-md.md)] permiten la especificación de un modificador ALL o DISTINCT.</span><span class="sxs-lookup"><span data-stu-id="f1cee-139">Both variants of SELECT in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] allow the specification of an ALL or DISTINCT modifier.</span></span> <span data-ttu-id="f1cee-140">Si se especifica el modificador DISTINCT, los resultados duplicados se eliminan de la colección producida por la expresión de consulta (hasta la cláusula SELECT e incluida dicha cláusula).</span><span class="sxs-lookup"><span data-stu-id="f1cee-140">If the DISTINCT modifier is specified, duplicates are eliminated from the collection produced by the query expression (up to and including the SELECT clause).</span></span> <span data-ttu-id="f1cee-141">Si se especifica el modificador ALL, no se lleva a cabo la eliminación de resultados duplicados; ALL es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f1cee-141">If the ALL modifier is specified, no duplicate elimination is performed; ALL is the default.</span></span>  
  
## <a name="differences-from-transact-sql"></a><span data-ttu-id="f1cee-142">Diferencias respecto de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f1cee-142">Differences from Transact-SQL</span></span>  

 <span data-ttu-id="f1cee-143">A diferencia de Transact-SQL, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] no admite el uso del argumento \* en la cláusula SELECT.</span><span class="sxs-lookup"><span data-stu-id="f1cee-143">Unlike Transact-SQL, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] does not support use of the \* argument in the SELECT clause.</span></span>  <span data-ttu-id="f1cee-144">En su lugar, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] permite que las consultas proyecten externamente registros completos haciendo referencia a los alias para la colección de la cláusula FROM, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f1cee-144">Instead, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] allows queries to project out entire records by referencing the collection aliases from the FROM clause, as illustrated in the following example.</span></span>  
  
```sql  
SELECT * FROM T1, T2  
```  
  
 <span data-ttu-id="f1cee-145">La expresión de consulta de Transact-SQL anterior se expresa en [!INCLUDE[esql](../../../../../../includes/esql-md.md)] de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="f1cee-145">The previous Transact-SQL query expression is expressed in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] in the following way.</span></span>  
  
```sql  
SELECT a1, a2 FROM T1 AS a1, T2 AS a2  
```  
  
## <a name="example"></a><span data-ttu-id="f1cee-146">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f1cee-146">Example</span></span>  

 <span data-ttu-id="f1cee-147">La consulta de Entity SQL siguiente utiliza el operador SELECT para especificar los elementos que ha de devolver una consulta.</span><span class="sxs-lookup"><span data-stu-id="f1cee-147">The following Entity SQL query uses the SELECT operator to specify the elements to be returned by a query.</span></span> <span data-ttu-id="f1cee-148">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="f1cee-148">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="f1cee-149">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="f1cee-149">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="f1cee-150">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="f1cee-150">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="f1cee-151">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="f1cee-151">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#LESS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#less)]  
  
## <a name="see-also"></a><span data-ttu-id="f1cee-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1cee-152">See also</span></span>

- [<span data-ttu-id="f1cee-153">Expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="f1cee-153">Query Expressions</span></span>](query-expressions-entity-sql.md)
- [<span data-ttu-id="f1cee-154">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="f1cee-154">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="f1cee-155">TOP</span><span class="sxs-lookup"><span data-stu-id="f1cee-155">TOP</span></span>](top-entity-sql.md)
