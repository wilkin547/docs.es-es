---
description: 'Más información acerca de: desde (Entity SQL)'
title: FROM (Entity SQL)
ms.date: 03/30/2017
ms.assetid: ff3e3048-0d5d-4502-ae5c-9187fcbd0514
ms.openlocfilehash: e8f7906669b3ea9ee5c3be307bd31a2043b2650e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786347"
---
# <a name="from-entity-sql"></a><span data-ttu-id="aaf76-103">FROM (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="aaf76-103">FROM (Entity SQL)</span></span>

<span data-ttu-id="aaf76-104">Especifica la colección utilizada en las instrucciones [Select](select-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="aaf76-104">Specifies the collection used in [SELECT](select-entity-sql.md) statements.</span></span>

## <a name="syntax"></a><span data-ttu-id="aaf76-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aaf76-105">Syntax</span></span>

```sql
FROM expression [ ,...n ] AS C
```

## <a name="arguments"></a><span data-ttu-id="aaf76-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="aaf76-106">Arguments</span></span>

`expression` \
<span data-ttu-id="aaf76-107">Cualquier expresión de consulta válida que produce una colección que usar como origen en una instrucción `SELECT`.</span><span class="sxs-lookup"><span data-stu-id="aaf76-107">Any valid query expression that yields a collection to use as a source in a `SELECT` statement.</span></span>

## <a name="remarks"></a><span data-ttu-id="aaf76-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="aaf76-108">Remarks</span></span>

<span data-ttu-id="aaf76-109">Una cláusula `FROM` es una lista separada por comas de uno o varios elementos de la cláusula `FROM`.</span><span class="sxs-lookup"><span data-stu-id="aaf76-109">A `FROM` clause is a comma-separated list of one or more `FROM` clause items.</span></span> <span data-ttu-id="aaf76-110">La cláusula `FROM` se puede utilizar para especificar uno o varios orígenes para una instrucción `SELECT`.</span><span class="sxs-lookup"><span data-stu-id="aaf76-110">The `FROM` clause can be used to specify one or more sources for a `SELECT` statement.</span></span> <span data-ttu-id="aaf76-111">La forma más sencilla de una cláusula `FROM` es una expresión de una única consulta que identifica una colección y un alias que se usa como origen en una instrucción `SELECT`, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aaf76-111">The simplest form of a `FROM` clause is a single query expression that identifies a collection and an alias used as the source in a `SELECT` statement, as illustrated in the following example:</span></span>

`FROM C as c`

## <a name="from-clause-items"></a><span data-ttu-id="aaf76-112">Elementos de la cláusula FROM</span><span class="sxs-lookup"><span data-stu-id="aaf76-112">FROM Clause Items</span></span>

<span data-ttu-id="aaf76-113">Cada elemento de la cláusula `FROM` hace referencia a una colección de origen en la consulta [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aaf76-113">Each `FROM` clause item refers to a source collection in the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="aaf76-114">admite las siguientes clases de elementos de la cláusula `FROM`: elementos de la cláusula `FROM` simples, elementos de la cláusula `JOIN FROM` y elementos de la cláusula `APPLY FROM`.</span><span class="sxs-lookup"><span data-stu-id="aaf76-114">supports the following classes of `FROM` clause items: simple `FROM` clause items, `JOIN FROM` clause items, and `APPLY FROM` clause items.</span></span> <span data-ttu-id="aaf76-115">En las siguientes secciones se describe con más detalle cada uno de estos elementos de la cláusula `FROM`.</span><span class="sxs-lookup"><span data-stu-id="aaf76-115">Each of these `FROM` clause items is described in more detail in the following sections.</span></span>

### <a name="simple-from-clause-item"></a><span data-ttu-id="aaf76-116">Elemento de la cláusula FROM simple</span><span class="sxs-lookup"><span data-stu-id="aaf76-116">Simple FROM Clause Item</span></span>

<span data-ttu-id="aaf76-117">El elemento de la cláusula `FROM` más simple es una expresión única que identifica una colección y un alias.</span><span class="sxs-lookup"><span data-stu-id="aaf76-117">The simplest `FROM` clause item is a single expression that identifies a collection and an alias.</span></span> <span data-ttu-id="aaf76-118">La expresión puede ser simplemente un conjunto de entidades, una subconsulta o cualquier otra expresión que sea un tipo de colección.</span><span class="sxs-lookup"><span data-stu-id="aaf76-118">The expression can simply be an entity set, or a subquery, or any other expression that is a collection type.</span></span> <span data-ttu-id="aaf76-119">A continuación se muestra un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="aaf76-119">The following is an example:</span></span>

```sql
LOB.Customers as c
```

<span data-ttu-id="aaf76-120">La especificación del alias es opcional.</span><span class="sxs-lookup"><span data-stu-id="aaf76-120">The alias specification is optional.</span></span> <span data-ttu-id="aaf76-121">Una especificación alternativa del elemento de la cláusula FROM anterior podría ser la siguiente:</span><span class="sxs-lookup"><span data-stu-id="aaf76-121">An alternate specification of the above from clause item could be the following:</span></span>

```sql
LOB.Customers
```

<span data-ttu-id="aaf76-122">Si no se especifica un alias, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] intenta generar uno según la expresión de la colección.</span><span class="sxs-lookup"><span data-stu-id="aaf76-122">If no alias is specified, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] attempts to generate an alias based on the collection expression.</span></span>

### <a name="join-from-clause-item"></a><span data-ttu-id="aaf76-123">Elemento de la cláusula JOIN FROM</span><span class="sxs-lookup"><span data-stu-id="aaf76-123">JOIN FROM Clause Item</span></span>

<span data-ttu-id="aaf76-124">Un elemento de la cláusula `JOIN FROM` representa una unión entre dos elementos de la cláusula `FROM`.</span><span class="sxs-lookup"><span data-stu-id="aaf76-124">A `JOIN FROM` clause item represents a join between two `FROM` clause items.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="aaf76-125">admite combinaciones cruzadas, combinaciones internas, combinaciones externas izquierda y derecha y combinaciones externas completas.</span><span class="sxs-lookup"><span data-stu-id="aaf76-125">supports cross joins, inner joins, left and right outer joins, and full outer joins.</span></span> <span data-ttu-id="aaf76-126">Todas estas combinaciones se admiten de forma similar a como se admiten en Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="aaf76-126">All these joins are supported similar to the way that they are supported in Transact-SQL.</span></span> <span data-ttu-id="aaf76-127">Como en Transact-SQL, los dos `FROM` elementos de la cláusula implicados en `JOIN` deben ser independientes.</span><span class="sxs-lookup"><span data-stu-id="aaf76-127">As in Transact-SQL, the two `FROM` clause items involved in the `JOIN` must be independent.</span></span> <span data-ttu-id="aaf76-128">Es decir, no pueden estar correlacionados.</span><span class="sxs-lookup"><span data-stu-id="aaf76-128">That is, they cannot be correlated.</span></span> <span data-ttu-id="aaf76-129">En estos casos se puede usar un elemento `CROSS APPLY` u `OUTER APPLY`.</span><span class="sxs-lookup"><span data-stu-id="aaf76-129">A `CROSS APPLY` or `OUTER APPLY` can be used for these cases.</span></span>

#### <a name="cross-joins"></a><span data-ttu-id="aaf76-130">Combinaciones cruzadas</span><span class="sxs-lookup"><span data-stu-id="aaf76-130">Cross Joins</span></span>

<span data-ttu-id="aaf76-131">Una expresión de consulta `CROSS JOIN` genera el producto cartesiano de las dos colecciones, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aaf76-131">A `CROSS JOIN` query expression produces the Cartesian product of the two collections, as illustrated in the following example:</span></span>

`FROM C AS c CROSS JOIN D as d`

#### <a name="inner-joins"></a><span data-ttu-id="aaf76-132">Combinaciones internas</span><span class="sxs-lookup"><span data-stu-id="aaf76-132">Inner Joins</span></span>

<span data-ttu-id="aaf76-133">Una expresión de consulta `INNER JOIN` genera un producto cartesiano restringido de las dos colecciones, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aaf76-133">An `INNER JOIN` produces a constrained Cartesian product of the two collections, as illustrated in the following example:</span></span>

`FROM C AS c [INNER] JOIN D AS d ON e`

<span data-ttu-id="aaf76-134">La expresión de consulta anterior procesa una combinación de cada elemento de la colección de la izquierda emparejada con cada elemento de la colección de la derecha, donde la condición `ON` es verdad.</span><span class="sxs-lookup"><span data-stu-id="aaf76-134">The previous query expression processes a combination of every element of the collection on the left paired against every element of the collection on the right, where the `ON` condition is true.</span></span> <span data-ttu-id="aaf76-135">Si no se especifica ninguna condición `ON`, una expresión `INNER JOIN` degenera en `CROSS JOIN`.</span><span class="sxs-lookup"><span data-stu-id="aaf76-135">If no `ON` condition is specified, an `INNER JOIN` degenerates to a `CROSS JOIN`.</span></span>

#### <a name="left-outer-joins-and-right-outer-joins"></a><span data-ttu-id="aaf76-136">Combinación externa izquierda y combinación externa derecha</span><span class="sxs-lookup"><span data-stu-id="aaf76-136">Left Outer Joins and Right Outer Joins</span></span>

<span data-ttu-id="aaf76-137">Una expresión de consulta `OUTER JOIN` genera el producto cartesiano restringido de las dos colecciones, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aaf76-137">An `OUTER JOIN` query expression produces a constrained Cartesian product of the two collections, as illustrated in the following example:</span></span>

`FROM C AS c LEFT OUTER JOIN D AS d ON e`

<span data-ttu-id="aaf76-138">La expresión de consulta anterior procesa una combinación de cada elemento de la colección de la izquierda emparejada con cada elemento de la colección de la derecha, donde la condición `ON` es verdad.</span><span class="sxs-lookup"><span data-stu-id="aaf76-138">The previous query expression processes a combination of every element of the collection on the left paired against every element of the collection on the right, where the `ON` condition is true.</span></span> <span data-ttu-id="aaf76-139">Si la condición `ON` es falsa, la expresión todavía procesa una única instancia del elemento de la izquierda emparejado con el elemento de la derecha, con el valor NULL.</span><span class="sxs-lookup"><span data-stu-id="aaf76-139">If the `ON` condition is false, the expression still processes a single instance of the element on the left paired against the element on the right, with the value null.</span></span>

<span data-ttu-id="aaf76-140">Una expresión `RIGHT OUTER JOIN` se puede expresar de una manera similar.</span><span class="sxs-lookup"><span data-stu-id="aaf76-140">A `RIGHT OUTER JOIN` may be expressed in a similar manner.</span></span>

#### <a name="full-outer-joins"></a><span data-ttu-id="aaf76-141">Combinación externa completa</span><span class="sxs-lookup"><span data-stu-id="aaf76-141">Full Outer Joins</span></span>

<span data-ttu-id="aaf76-142">Una expresión de consulta `FULL OUTER JOIN` explícita genera un producto cartesiano restringido de las dos colecciones, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aaf76-142">An explicit `FULL OUTER JOIN` produces a constrained Cartesian product of the two collections as illustrated in the following example:</span></span>

`FROM C AS c FULL OUTER JOIN D AS d ON e`

<span data-ttu-id="aaf76-143">La expresión de consulta anterior procesa una combinación de cada elemento de la colección de la izquierda emparejada con cada elemento de la colección de la derecha, donde la condición `ON` es verdad.</span><span class="sxs-lookup"><span data-stu-id="aaf76-143">The previous query expression processes a combination of every element of the collection on the left paired against every element of the collection on the right, where the `ON` condition is true.</span></span> <span data-ttu-id="aaf76-144">Si la condición `ON` es falsa, la expresión aún procesa una instancia del elemento de la izquierda emparejada con el elemento de la derecha, con el valor NULL.</span><span class="sxs-lookup"><span data-stu-id="aaf76-144">If the `ON` condition is false, the expression still processes one instance of the element on the left paired against the element on the right, with the value null.</span></span> <span data-ttu-id="aaf76-145">También procesa una instancia del elemento de la derecha emparejado con el elemento de la izquierda, con el valor NULL.</span><span class="sxs-lookup"><span data-stu-id="aaf76-145">It also processes one instance of the element on the right paired against the element on the left, with the value null.</span></span>

> [!NOTE]
> <span data-ttu-id="aaf76-146">Para conservar la compatibilidad con SQL-92, en Transact-SQL la palabra clave OUTER es opcional.</span><span class="sxs-lookup"><span data-stu-id="aaf76-146">To preserve compatibility with SQL-92, in Transact-SQL the OUTER keyword is optional.</span></span> <span data-ttu-id="aaf76-147">Por lo tanto, `LEFT JOIN`, `RIGHT JOIN` y `FULL JOIN` son sinónimos de `LEFT OUTER JOIN`, `RIGHT OUTER JOIN` y `FULL OUTER JOIN`.</span><span class="sxs-lookup"><span data-stu-id="aaf76-147">Therefore, `LEFT JOIN`, `RIGHT JOIN`, and `FULL JOIN` are synonyms for `LEFT OUTER JOIN`, `RIGHT OUTER JOIN`, and `FULL OUTER JOIN`.</span></span>

### <a name="apply-clause-item"></a><span data-ttu-id="aaf76-148">Elemento de la cláusula APPLY</span><span class="sxs-lookup"><span data-stu-id="aaf76-148">APPLY Clause Item</span></span>

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="aaf76-149">admite dos clases de `APPLY`: `CROSS APPLY` y `OUTER APPLY`.</span><span class="sxs-lookup"><span data-stu-id="aaf76-149">supports two kinds of `APPLY`: `CROSS APPLY` and `OUTER APPLY`.</span></span>

<span data-ttu-id="aaf76-150">`CROSS APPLY` genera un emparejamiento único de cada elemento de la colección de la izquierda con un elemento de la colección que se crea al evaluar la expresión de la derecha.</span><span class="sxs-lookup"><span data-stu-id="aaf76-150">A `CROSS APPLY` produces a unique pairing of each element of the collection on the left with an element of the collection produced by evaluating the expression on the right.</span></span> <span data-ttu-id="aaf76-151">Con una expresión `CROSS APPLY`, la expresión de la derecha es funcionalmente dependiente del elemento de la izquierda, tal y como se muestra en el ejemplo de colección asociada siguiente:</span><span class="sxs-lookup"><span data-stu-id="aaf76-151">With a `CROSS APPLY`, the expression on the right is functionally dependent on the element on the left, as illustrated in the following associated collection example:</span></span>

`SELECT c, f FROM C AS c CROSS APPLY c.Assoc AS f`

<span data-ttu-id="aaf76-152">El comportamiento de `CROSS APPLY` es similar a la lista de combinaciones.</span><span class="sxs-lookup"><span data-stu-id="aaf76-152">The behavior of `CROSS APPLY` is similar to the join list.</span></span> <span data-ttu-id="aaf76-153">Si la expresión de la derecha se evalúa como una colección vacía, `CROSS APPLY` no genera ningún emparejamiento para esa instancia del elemento de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="aaf76-153">If the expression on the right evaluates to an empty collection, the `CROSS APPLY` produces no pairings for that instance of the element on the left.</span></span>

<span data-ttu-id="aaf76-154">Una expresión `OUTER APPLY` se parece a `CROSS APPLY`, excepto en que se sigue produciendo un emparejamiento incluso cuando la expresión de la derecha se evalúa como una colección vacía.</span><span class="sxs-lookup"><span data-stu-id="aaf76-154">An `OUTER APPLY` resembles a `CROSS APPLY`, except a pairing is still produced even when the expression on the right evaluates to an empty collection.</span></span> <span data-ttu-id="aaf76-155">El siguiente es un ejemplo de `OUTER APPLY`:</span><span class="sxs-lookup"><span data-stu-id="aaf76-155">The following is an example of an `OUTER APPLY`:</span></span>

`SELECT c, f FROM C AS c OUTER APPLY c.Assoc AS f`

> [!NOTE]
> <span data-ttu-id="aaf76-156">A diferencia de Transact-SQL, no es necesario un paso explícito UNNEST en [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aaf76-156">Unlike in Transact-SQL, there is no need for an explicit unnest step in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>

> [!NOTE]
> <span data-ttu-id="aaf76-157">`CROSS` los `OUTER APPLY` operadores y se introdujeron en SQL Server 2005.</span><span class="sxs-lookup"><span data-stu-id="aaf76-157">`CROSS` and `OUTER APPLY` operators were introduced in SQL Server 2005.</span></span> <span data-ttu-id="aaf76-158">En algunos casos, la canalización de la consulta podría generar código de Transact-SQL que contiene los operadores `CROSS APPLY` y `OUTER APPLY`.</span><span class="sxs-lookup"><span data-stu-id="aaf76-158">In some cases, the query pipeline might produce Transact-SQL that contains `CROSS APPLY` and/or `OUTER APPLY` operators.</span></span> <span data-ttu-id="aaf76-159">Dado que algunos proveedores de back-end, incluidas las versiones de SQL Server anteriores a SQL Server 2005, no admiten estos operadores, tales consultas no se pueden ejecutar en estos proveedores de back-end.</span><span class="sxs-lookup"><span data-stu-id="aaf76-159">Because some backend providers, including versions of SQL Server earlier than SQL Server 2005, do not support these operators, such queries cannot be executed on these backend providers.</span></span>
>
> <span data-ttu-id="aaf76-160">Algunos escenarios típicos que podrían conducir  a la presencia de los operadores `CROSS APPLY``OUTER APPLY` en la consulta de salida son las siguientes: una subconsulta correlacionada con la paginación; AnyElement sobre una subconsulta correlacionada o sobre una colección generada mediante navegación; consultas LINQ que utilizan métodos de agrupación que aceptan un selector de elemento; una consulta en la que se especifica explícitamente `CROSS APPLY` u `OUTER APPLY`; una consulta que tiene una construcción `DEREF` sobre una construcción `REF`.</span><span class="sxs-lookup"><span data-stu-id="aaf76-160">Some typical scenarios that might lead to the presence of `CROSS APPLY` and/or `OUTER APPLY` operators in the output query are the following: a correlated subquery with paging; AnyElement over a correlated subquery or over a collection produced by navigation; LINQ queries that use grouping methods that accept an element selector; a query in which a `CROSS APPLY` or an `OUTER APPLY` are explicitly specified; a query that has a `DEREF` construct over a `REF` construct.</span></span>

## <a name="multiple-collections-in-the-from-clause"></a><span data-ttu-id="aaf76-161">Varias colecciones en la cláusula FROM</span><span class="sxs-lookup"><span data-stu-id="aaf76-161">Multiple Collections in the FROM Clause</span></span>

<span data-ttu-id="aaf76-162">La cláusula `FROM` puede contener más de una colección separada por comas.</span><span class="sxs-lookup"><span data-stu-id="aaf76-162">The `FROM` clause can contain more than one collection separated by commas.</span></span> <span data-ttu-id="aaf76-163">En estos casos, se supone que las colecciones están combinadas.</span><span class="sxs-lookup"><span data-stu-id="aaf76-163">In these cases, the collections are assumed to be joined together.</span></span> <span data-ttu-id="aaf76-164">Considérelas como una operación CROSS JOIN de n direcciones.</span><span class="sxs-lookup"><span data-stu-id="aaf76-164">Think of these as an n-way CROSS JOIN.</span></span>

<span data-ttu-id="aaf76-165">En el ejemplo siguiente, `C` y `D` son colecciones independientes, pero `c.Names` depende de `C` .</span><span class="sxs-lookup"><span data-stu-id="aaf76-165">In the following example, `C` and `D` are independent collections, but `c.Names` is dependent on `C`.</span></span>

```sql
FROM C AS c, D AS d, c.Names AS e
```

<span data-ttu-id="aaf76-166">El ejemplo anterior es lógicamente equivalente al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aaf76-166">The previous example is logically equivalent to the following example:</span></span>

`FROM (C AS c JOIN D AS d) CROSS APPLY c.Names AS e`

## <a name="left-correlation"></a><span data-ttu-id="aaf76-167">Correlación izquierda</span><span class="sxs-lookup"><span data-stu-id="aaf76-167">Left Correlation</span></span>

 <span data-ttu-id="aaf76-168">Los elementos de la cláusula `FROM` pueden hacer referencia a los elementos especificados en las cláusulas anteriores.</span><span class="sxs-lookup"><span data-stu-id="aaf76-168">Items in the `FROM` clause can refer to items specified in earlier clauses.</span></span> <span data-ttu-id="aaf76-169">En el ejemplo siguiente, `C` y `D` son colecciones independientes, pero `c.Names` depende de `C`:</span><span class="sxs-lookup"><span data-stu-id="aaf76-169">In the following example, `C` and `D` are independent collections, but `c.Names` is dependent on `C`:</span></span>

```sql
from C as c, D as d, c.Names as e
```

<span data-ttu-id="aaf76-170">Esto es lógicamente equivalente a:</span><span class="sxs-lookup"><span data-stu-id="aaf76-170">This is logically equivalent to:</span></span>

```sql
from (C as c join D as d) cross apply c.Names as e
```

## <a name="semantics"></a><span data-ttu-id="aaf76-171">Semántica</span><span class="sxs-lookup"><span data-stu-id="aaf76-171">Semantics</span></span>

<span data-ttu-id="aaf76-172">Lógicamente, se supone que las colecciones de la cláusula `FROM` forman parte de la combinación cruzada de `n` direcciones (excepto en el caso de una combinación cruzada unidireccional).</span><span class="sxs-lookup"><span data-stu-id="aaf76-172">Logically, the collections in the `FROM` clause are assumed to be part of an `n`-way cross join (except in the case of a 1-way cross join).</span></span> <span data-ttu-id="aaf76-173">Los alias de la cláusula `FROM` se procesan de izquierda a derecha y se agregan al ámbito actual como referencia.</span><span class="sxs-lookup"><span data-stu-id="aaf76-173">Aliases in the `FROM` clause are processed left to right, and are added to the current scope for later reference.</span></span> <span data-ttu-id="aaf76-174">Se supone que la cláusula `FROM` genera un multiconjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="aaf76-174">The `FROM` clause is assumed to produce a multiset of rows.</span></span> <span data-ttu-id="aaf76-175">Habrá un campo para cada elemento de la cláusula `FROM` que representa un elemento único de esa colección.</span><span class="sxs-lookup"><span data-stu-id="aaf76-175">There will be one field for each item in the `FROM` clause that represents a single element from that collection item.</span></span>

<span data-ttu-id="aaf76-176">La cláusula `FROM` genera lógicamente un multiconjunto de filas de tipo Row(c, d, e), donde los campos c, d y e se supone que son del tipo de elemento de `C`, `D` y `c.Names`.</span><span class="sxs-lookup"><span data-stu-id="aaf76-176">The `FROM` clause logically produces a multiset of rows of type Row(c, d, e) where fields c, d, and e are assumed to be of the element type of `C`, `D`, and `c.Names`.</span></span>

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="aaf76-177">introduce un alias para cada elemento de la cláusula `FROM` simple en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="aaf76-177">introduces an alias for each simple `FROM` clause item in scope.</span></span> <span data-ttu-id="aaf76-178">Por ejemplo, en el fragmento de código de la cláusula FROM siguiente, los nombres introducidos en el ámbito son c, d y e.</span><span class="sxs-lookup"><span data-stu-id="aaf76-178">For example, in the following FROM clause snippet, The names introduced into scope are c, d, and e.</span></span>

```sql
from (C as c join D as d) cross apply c.Names as e
```

<span data-ttu-id="aaf76-179">En [!INCLUDE[esql](../../../../../../includes/esql-md.md)] (a diferencia de Transact-SQL), la `FROM` cláusula solo introduce los alias en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="aaf76-179">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] (unlike Transact-SQL), the `FROM` clause only introduces the aliases into scope.</span></span> <span data-ttu-id="aaf76-180">Cualquier referencia a las columnas (propiedades) de estas colecciones se debe certificar con el alias.</span><span class="sxs-lookup"><span data-stu-id="aaf76-180">Any references to columns (properties) of these collections must be qualified with the alias.</span></span>

## <a name="pulling-up-keys-from-nested-queries"></a><span data-ttu-id="aaf76-181">Extraer claves de las consultas anidadas</span><span class="sxs-lookup"><span data-stu-id="aaf76-181">Pulling Up Keys from Nested Queries</span></span>

<span data-ttu-id="aaf76-182">No se admiten ciertos tipos de consultas que requieren la extracción de las claves de una consulta anidada.</span><span class="sxs-lookup"><span data-stu-id="aaf76-182">Certain types of queries that require pulling up keys from a nested query are not supported.</span></span> <span data-ttu-id="aaf76-183">Por ejemplo, la consulta siguiente es válida:</span><span class="sxs-lookup"><span data-stu-id="aaf76-183">For example, the following query is valid:</span></span>

```sql
select c.Orders from Customers as c
```

<span data-ttu-id="aaf76-184">Sin embargo, la consulta siguiente no es válida, porque la consulta anidada no tiene ninguna clave:</span><span class="sxs-lookup"><span data-stu-id="aaf76-184">However, the following query is not valid, because the nested query does not have any keys:</span></span>

```sql
select {1} from {2, 3}
```

## <a name="see-also"></a><span data-ttu-id="aaf76-185">Vea también</span><span class="sxs-lookup"><span data-stu-id="aaf76-185">See also</span></span>

- [<span data-ttu-id="aaf76-186">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="aaf76-186">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="aaf76-187">Expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="aaf76-187">Query Expressions</span></span>](query-expressions-entity-sql.md)
- [<span data-ttu-id="aaf76-188">Tipos estructurados que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="aaf76-188">Nullable Structured Types</span></span>](nullable-structured-types-entity-sql.md)
