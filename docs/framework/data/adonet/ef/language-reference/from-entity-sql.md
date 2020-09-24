---
title: FROM (Entity SQL)
ms.date: 03/30/2017
ms.assetid: ff3e3048-0d5d-4502-ae5c-9187fcbd0514
ms.openlocfilehash: 8affac82fb1813aa0282540b5dc2f47d42234a1b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148065"
---
# <a name="from-entity-sql"></a><span data-ttu-id="08a1c-102">FROM (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="08a1c-102">FROM (Entity SQL)</span></span>

<span data-ttu-id="08a1c-103">Especifica la colección utilizada en las instrucciones [Select](select-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="08a1c-103">Specifies the collection used in [SELECT](select-entity-sql.md) statements.</span></span>

## <a name="syntax"></a><span data-ttu-id="08a1c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="08a1c-104">Syntax</span></span>

```sql
FROM expression [ ,...n ] AS C
```

## <a name="arguments"></a><span data-ttu-id="08a1c-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="08a1c-105">Arguments</span></span>

`expression` \
<span data-ttu-id="08a1c-106">Cualquier expresión de consulta válida que produce una colección que usar como origen en una instrucción `SELECT`.</span><span class="sxs-lookup"><span data-stu-id="08a1c-106">Any valid query expression that yields a collection to use as a source in a `SELECT` statement.</span></span>

## <a name="remarks"></a><span data-ttu-id="08a1c-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="08a1c-107">Remarks</span></span>

<span data-ttu-id="08a1c-108">Una cláusula `FROM` es una lista separada por comas de uno o varios elementos de la cláusula `FROM`.</span><span class="sxs-lookup"><span data-stu-id="08a1c-108">A `FROM` clause is a comma-separated list of one or more `FROM` clause items.</span></span> <span data-ttu-id="08a1c-109">La cláusula `FROM` se puede utilizar para especificar uno o varios orígenes para una instrucción `SELECT`.</span><span class="sxs-lookup"><span data-stu-id="08a1c-109">The `FROM` clause can be used to specify one or more sources for a `SELECT` statement.</span></span> <span data-ttu-id="08a1c-110">La forma más sencilla de una cláusula `FROM` es una expresión de una única consulta que identifica una colección y un alias que se usa como origen en una instrucción `SELECT`, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="08a1c-110">The simplest form of a `FROM` clause is a single query expression that identifies a collection and an alias used as the source in a `SELECT` statement, as illustrated in the following example:</span></span>

`FROM C as c`

## <a name="from-clause-items"></a><span data-ttu-id="08a1c-111">Elementos de la cláusula FROM</span><span class="sxs-lookup"><span data-stu-id="08a1c-111">FROM Clause Items</span></span>

<span data-ttu-id="08a1c-112">Cada elemento de la cláusula `FROM` hace referencia a una colección de origen en la consulta [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="08a1c-112">Each `FROM` clause item refers to a source collection in the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="08a1c-113">admite las siguientes clases de elementos de la cláusula `FROM`: elementos de la cláusula `FROM` simples, elementos de la cláusula `JOIN FROM` y elementos de la cláusula `APPLY FROM`.</span><span class="sxs-lookup"><span data-stu-id="08a1c-113">supports the following classes of `FROM` clause items: simple `FROM` clause items, `JOIN FROM` clause items, and `APPLY FROM` clause items.</span></span> <span data-ttu-id="08a1c-114">En las siguientes secciones se describe con más detalle cada uno de estos elementos de la cláusula `FROM`.</span><span class="sxs-lookup"><span data-stu-id="08a1c-114">Each of these `FROM` clause items is described in more detail in the following sections.</span></span>

### <a name="simple-from-clause-item"></a><span data-ttu-id="08a1c-115">Elemento de la cláusula FROM simple</span><span class="sxs-lookup"><span data-stu-id="08a1c-115">Simple FROM Clause Item</span></span>

<span data-ttu-id="08a1c-116">El elemento de la cláusula `FROM` más simple es una expresión única que identifica una colección y un alias.</span><span class="sxs-lookup"><span data-stu-id="08a1c-116">The simplest `FROM` clause item is a single expression that identifies a collection and an alias.</span></span> <span data-ttu-id="08a1c-117">La expresión puede ser simplemente un conjunto de entidades, una subconsulta o cualquier otra expresión que sea un tipo de colección.</span><span class="sxs-lookup"><span data-stu-id="08a1c-117">The expression can simply be an entity set, or a subquery, or any other expression that is a collection type.</span></span> <span data-ttu-id="08a1c-118">A continuación se muestra un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="08a1c-118">The following is an example:</span></span>

```sql
LOB.Customers as c
```

<span data-ttu-id="08a1c-119">La especificación del alias es opcional.</span><span class="sxs-lookup"><span data-stu-id="08a1c-119">The alias specification is optional.</span></span> <span data-ttu-id="08a1c-120">Una especificación alternativa del elemento de la cláusula FROM anterior podría ser la siguiente:</span><span class="sxs-lookup"><span data-stu-id="08a1c-120">An alternate specification of the above from clause item could be the following:</span></span>

```sql
LOB.Customers
```

<span data-ttu-id="08a1c-121">Si no se especifica un alias, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] intenta generar uno según la expresión de la colección.</span><span class="sxs-lookup"><span data-stu-id="08a1c-121">If no alias is specified, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] attempts to generate an alias based on the collection expression.</span></span>

### <a name="join-from-clause-item"></a><span data-ttu-id="08a1c-122">Elemento de la cláusula JOIN FROM</span><span class="sxs-lookup"><span data-stu-id="08a1c-122">JOIN FROM Clause Item</span></span>

<span data-ttu-id="08a1c-123">Un elemento de la cláusula `JOIN FROM` representa una unión entre dos elementos de la cláusula `FROM`.</span><span class="sxs-lookup"><span data-stu-id="08a1c-123">A `JOIN FROM` clause item represents a join between two `FROM` clause items.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="08a1c-124">admite combinaciones cruzadas, combinaciones internas, combinaciones externas izquierda y derecha y combinaciones externas completas.</span><span class="sxs-lookup"><span data-stu-id="08a1c-124">supports cross joins, inner joins, left and right outer joins, and full outer joins.</span></span> <span data-ttu-id="08a1c-125">Todas estas combinaciones se admiten de forma similar a como se admiten en Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="08a1c-125">All these joins are supported similar to the way that they are supported in Transact-SQL.</span></span> <span data-ttu-id="08a1c-126">Como en Transact-SQL, los dos `FROM` elementos de la cláusula implicados en `JOIN` deben ser independientes.</span><span class="sxs-lookup"><span data-stu-id="08a1c-126">As in Transact-SQL, the two `FROM` clause items involved in the `JOIN` must be independent.</span></span> <span data-ttu-id="08a1c-127">Es decir, no pueden estar correlacionados.</span><span class="sxs-lookup"><span data-stu-id="08a1c-127">That is, they cannot be correlated.</span></span> <span data-ttu-id="08a1c-128">En estos casos se puede usar un elemento `CROSS APPLY` u `OUTER APPLY`.</span><span class="sxs-lookup"><span data-stu-id="08a1c-128">A `CROSS APPLY` or `OUTER APPLY` can be used for these cases.</span></span>

#### <a name="cross-joins"></a><span data-ttu-id="08a1c-129">Combinaciones cruzadas</span><span class="sxs-lookup"><span data-stu-id="08a1c-129">Cross Joins</span></span>

<span data-ttu-id="08a1c-130">Una expresión de consulta `CROSS JOIN` genera el producto cartesiano de las dos colecciones, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="08a1c-130">A `CROSS JOIN` query expression produces the Cartesian product of the two collections, as illustrated in the following example:</span></span>

`FROM C AS c CROSS JOIN D as d`

#### <a name="inner-joins"></a><span data-ttu-id="08a1c-131">Combinaciones internas</span><span class="sxs-lookup"><span data-stu-id="08a1c-131">Inner Joins</span></span>

<span data-ttu-id="08a1c-132">Una expresión de consulta `INNER JOIN` genera un producto cartesiano restringido de las dos colecciones, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="08a1c-132">An `INNER JOIN` produces a constrained Cartesian product of the two collections, as illustrated in the following example:</span></span>

`FROM C AS c [INNER] JOIN D AS d ON e`

<span data-ttu-id="08a1c-133">La expresión de consulta anterior procesa una combinación de cada elemento de la colección de la izquierda emparejada con cada elemento de la colección de la derecha, donde la condición `ON` es verdad.</span><span class="sxs-lookup"><span data-stu-id="08a1c-133">The previous query expression processes a combination of every element of the collection on the left paired against every element of the collection on the right, where the `ON` condition is true.</span></span> <span data-ttu-id="08a1c-134">Si no se especifica ninguna condición `ON`, una expresión `INNER JOIN` degenera en `CROSS JOIN`.</span><span class="sxs-lookup"><span data-stu-id="08a1c-134">If no `ON` condition is specified, an `INNER JOIN` degenerates to a `CROSS JOIN`.</span></span>

#### <a name="left-outer-joins-and-right-outer-joins"></a><span data-ttu-id="08a1c-135">Combinación externa izquierda y combinación externa derecha</span><span class="sxs-lookup"><span data-stu-id="08a1c-135">Left Outer Joins and Right Outer Joins</span></span>

<span data-ttu-id="08a1c-136">Una expresión de consulta `OUTER JOIN` genera el producto cartesiano restringido de las dos colecciones, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="08a1c-136">An `OUTER JOIN` query expression produces a constrained Cartesian product of the two collections, as illustrated in the following example:</span></span>

`FROM C AS c LEFT OUTER JOIN D AS d ON e`

<span data-ttu-id="08a1c-137">La expresión de consulta anterior procesa una combinación de cada elemento de la colección de la izquierda emparejada con cada elemento de la colección de la derecha, donde la condición `ON` es verdad.</span><span class="sxs-lookup"><span data-stu-id="08a1c-137">The previous query expression processes a combination of every element of the collection on the left paired against every element of the collection on the right, where the `ON` condition is true.</span></span> <span data-ttu-id="08a1c-138">Si la condición `ON` es falsa, la expresión todavía procesa una única instancia del elemento de la izquierda emparejado con el elemento de la derecha, con el valor NULL.</span><span class="sxs-lookup"><span data-stu-id="08a1c-138">If the `ON` condition is false, the expression still processes a single instance of the element on the left paired against the element on the right, with the value null.</span></span>

<span data-ttu-id="08a1c-139">Una expresión `RIGHT OUTER JOIN` se puede expresar de una manera similar.</span><span class="sxs-lookup"><span data-stu-id="08a1c-139">A `RIGHT OUTER JOIN` may be expressed in a similar manner.</span></span>

#### <a name="full-outer-joins"></a><span data-ttu-id="08a1c-140">Combinación externa completa</span><span class="sxs-lookup"><span data-stu-id="08a1c-140">Full Outer Joins</span></span>

<span data-ttu-id="08a1c-141">Una expresión de consulta `FULL OUTER JOIN` explícita genera un producto cartesiano restringido de las dos colecciones, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="08a1c-141">An explicit `FULL OUTER JOIN` produces a constrained Cartesian product of the two collections as illustrated in the following example:</span></span>

`FROM C AS c FULL OUTER JOIN D AS d ON e`

<span data-ttu-id="08a1c-142">La expresión de consulta anterior procesa una combinación de cada elemento de la colección de la izquierda emparejada con cada elemento de la colección de la derecha, donde la condición `ON` es verdad.</span><span class="sxs-lookup"><span data-stu-id="08a1c-142">The previous query expression processes a combination of every element of the collection on the left paired against every element of the collection on the right, where the `ON` condition is true.</span></span> <span data-ttu-id="08a1c-143">Si la condición `ON` es falsa, la expresión aún procesa una instancia del elemento de la izquierda emparejada con el elemento de la derecha, con el valor NULL.</span><span class="sxs-lookup"><span data-stu-id="08a1c-143">If the `ON` condition is false, the expression still processes one instance of the element on the left paired against the element on the right, with the value null.</span></span> <span data-ttu-id="08a1c-144">También procesa una instancia del elemento de la derecha emparejado con el elemento de la izquierda, con el valor NULL.</span><span class="sxs-lookup"><span data-stu-id="08a1c-144">It also processes one instance of the element on the right paired against the element on the left, with the value null.</span></span>

> [!NOTE]
> <span data-ttu-id="08a1c-145">Para conservar la compatibilidad con SQL-92, en Transact-SQL la palabra clave OUTER es opcional.</span><span class="sxs-lookup"><span data-stu-id="08a1c-145">To preserve compatibility with SQL-92, in Transact-SQL the OUTER keyword is optional.</span></span> <span data-ttu-id="08a1c-146">Por lo tanto, `LEFT JOIN`, `RIGHT JOIN` y `FULL JOIN` son sinónimos de `LEFT OUTER JOIN`, `RIGHT OUTER JOIN` y `FULL OUTER JOIN`.</span><span class="sxs-lookup"><span data-stu-id="08a1c-146">Therefore, `LEFT JOIN`, `RIGHT JOIN`, and `FULL JOIN` are synonyms for `LEFT OUTER JOIN`, `RIGHT OUTER JOIN`, and `FULL OUTER JOIN`.</span></span>

### <a name="apply-clause-item"></a><span data-ttu-id="08a1c-147">Elemento de la cláusula APPLY</span><span class="sxs-lookup"><span data-stu-id="08a1c-147">APPLY Clause Item</span></span>

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="08a1c-148">admite dos clases de `APPLY`: `CROSS APPLY` y `OUTER APPLY`.</span><span class="sxs-lookup"><span data-stu-id="08a1c-148">supports two kinds of `APPLY`: `CROSS APPLY` and `OUTER APPLY`.</span></span>

<span data-ttu-id="08a1c-149">`CROSS APPLY` genera un emparejamiento único de cada elemento de la colección de la izquierda con un elemento de la colección que se crea al evaluar la expresión de la derecha.</span><span class="sxs-lookup"><span data-stu-id="08a1c-149">A `CROSS APPLY` produces a unique pairing of each element of the collection on the left with an element of the collection produced by evaluating the expression on the right.</span></span> <span data-ttu-id="08a1c-150">Con una expresión `CROSS APPLY`, la expresión de la derecha es funcionalmente dependiente del elemento de la izquierda, tal y como se muestra en el ejemplo de colección asociada siguiente:</span><span class="sxs-lookup"><span data-stu-id="08a1c-150">With a `CROSS APPLY`, the expression on the right is functionally dependent on the element on the left, as illustrated in the following associated collection example:</span></span>

`SELECT c, f FROM C AS c CROSS APPLY c.Assoc AS f`

<span data-ttu-id="08a1c-151">El comportamiento de `CROSS APPLY` es similar a la lista de combinaciones.</span><span class="sxs-lookup"><span data-stu-id="08a1c-151">The behavior of `CROSS APPLY` is similar to the join list.</span></span> <span data-ttu-id="08a1c-152">Si la expresión de la derecha se evalúa como una colección vacía, `CROSS APPLY` no genera ningún emparejamiento para esa instancia del elemento de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="08a1c-152">If the expression on the right evaluates to an empty collection, the `CROSS APPLY` produces no pairings for that instance of the element on the left.</span></span>

<span data-ttu-id="08a1c-153">Una expresión `OUTER APPLY` se parece a `CROSS APPLY`, excepto en que se sigue produciendo un emparejamiento incluso cuando la expresión de la derecha se evalúa como una colección vacía.</span><span class="sxs-lookup"><span data-stu-id="08a1c-153">An `OUTER APPLY` resembles a `CROSS APPLY`, except a pairing is still produced even when the expression on the right evaluates to an empty collection.</span></span> <span data-ttu-id="08a1c-154">El siguiente es un ejemplo de `OUTER APPLY`:</span><span class="sxs-lookup"><span data-stu-id="08a1c-154">The following is an example of an `OUTER APPLY`:</span></span>

`SELECT c, f FROM C AS c OUTER APPLY c.Assoc AS f`

> [!NOTE]
> <span data-ttu-id="08a1c-155">A diferencia de Transact-SQL, no es necesario un paso explícito UNNEST en [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="08a1c-155">Unlike in Transact-SQL, there is no need for an explicit unnest step in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>

> [!NOTE]
> <span data-ttu-id="08a1c-156">`CROSS` los `OUTER APPLY` operadores y se introdujeron en SQL Server 2005.</span><span class="sxs-lookup"><span data-stu-id="08a1c-156">`CROSS` and `OUTER APPLY` operators were introduced in SQL Server 2005.</span></span> <span data-ttu-id="08a1c-157">En algunos casos, la canalización de la consulta podría generar código de Transact-SQL que contiene los operadores `CROSS APPLY` y `OUTER APPLY`.</span><span class="sxs-lookup"><span data-stu-id="08a1c-157">In some cases, the query pipeline might produce Transact-SQL that contains `CROSS APPLY` and/or `OUTER APPLY` operators.</span></span> <span data-ttu-id="08a1c-158">Dado que algunos proveedores de back-end, incluidas las versiones de SQL Server anteriores a SQL Server 2005, no admiten estos operadores, tales consultas no se pueden ejecutar en estos proveedores de back-end.</span><span class="sxs-lookup"><span data-stu-id="08a1c-158">Because some backend providers, including versions of SQL Server earlier than SQL Server 2005, do not support these operators, such queries cannot be executed on these backend providers.</span></span>
>
> <span data-ttu-id="08a1c-159">Algunos escenarios típicos que podrían conducir  a la presencia de los operadores `CROSS APPLY``OUTER APPLY` en la consulta de salida son las siguientes: una subconsulta correlacionada con la paginación; AnyElement sobre una subconsulta correlacionada o sobre una colección generada mediante navegación; consultas LINQ que utilizan métodos de agrupación que aceptan un selector de elemento; una consulta en la que se especifica explícitamente `CROSS APPLY` u `OUTER APPLY`; una consulta que tiene una construcción `DEREF` sobre una construcción `REF`.</span><span class="sxs-lookup"><span data-stu-id="08a1c-159">Some typical scenarios that might lead to the presence of `CROSS APPLY` and/or `OUTER APPLY` operators in the output query are the following: a correlated subquery with paging; AnyElement over a correlated subquery or over a collection produced by navigation; LINQ queries that use grouping methods that accept an element selector; a query in which a `CROSS APPLY` or an `OUTER APPLY` are explicitly specified; a query that has a `DEREF` construct over a `REF` construct.</span></span>

## <a name="multiple-collections-in-the-from-clause"></a><span data-ttu-id="08a1c-160">Varias colecciones en la cláusula FROM</span><span class="sxs-lookup"><span data-stu-id="08a1c-160">Multiple Collections in the FROM Clause</span></span>

<span data-ttu-id="08a1c-161">La cláusula `FROM` puede contener más de una colección separada por comas.</span><span class="sxs-lookup"><span data-stu-id="08a1c-161">The `FROM` clause can contain more than one collection separated by commas.</span></span> <span data-ttu-id="08a1c-162">En estos casos, se supone que las colecciones están combinadas.</span><span class="sxs-lookup"><span data-stu-id="08a1c-162">In these cases, the collections are assumed to be joined together.</span></span> <span data-ttu-id="08a1c-163">Considérelas como una operación CROSS JOIN de n direcciones.</span><span class="sxs-lookup"><span data-stu-id="08a1c-163">Think of these as an n-way CROSS JOIN.</span></span>

<span data-ttu-id="08a1c-164">En el ejemplo siguiente, `C` y `D` son colecciones independientes, pero `c.Names` depende de `C` .</span><span class="sxs-lookup"><span data-stu-id="08a1c-164">In the following example, `C` and `D` are independent collections, but `c.Names` is dependent on `C`.</span></span>

```sql
FROM C AS c, D AS d, c.Names AS e
```

<span data-ttu-id="08a1c-165">El ejemplo anterior es lógicamente equivalente al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="08a1c-165">The previous example is logically equivalent to the following example:</span></span>

`FROM (C AS c JOIN D AS d) CROSS APPLY c.Names AS e`

## <a name="left-correlation"></a><span data-ttu-id="08a1c-166">Correlación izquierda</span><span class="sxs-lookup"><span data-stu-id="08a1c-166">Left Correlation</span></span>

 <span data-ttu-id="08a1c-167">Los elementos de la cláusula `FROM` pueden hacer referencia a los elementos especificados en las cláusulas anteriores.</span><span class="sxs-lookup"><span data-stu-id="08a1c-167">Items in the `FROM` clause can refer to items specified in earlier clauses.</span></span> <span data-ttu-id="08a1c-168">En el ejemplo siguiente, `C` y `D` son colecciones independientes, pero `c.Names` depende de `C`:</span><span class="sxs-lookup"><span data-stu-id="08a1c-168">In the following example, `C` and `D` are independent collections, but `c.Names` is dependent on `C`:</span></span>

```sql
from C as c, D as d, c.Names as e
```

<span data-ttu-id="08a1c-169">Esto es lógicamente equivalente a:</span><span class="sxs-lookup"><span data-stu-id="08a1c-169">This is logically equivalent to:</span></span>

```sql
from (C as c join D as d) cross apply c.Names as e
```

## <a name="semantics"></a><span data-ttu-id="08a1c-170">Semántica</span><span class="sxs-lookup"><span data-stu-id="08a1c-170">Semantics</span></span>

<span data-ttu-id="08a1c-171">Lógicamente, se supone que las colecciones de la cláusula `FROM` forman parte de la combinación cruzada de `n` direcciones (excepto en el caso de una combinación cruzada unidireccional).</span><span class="sxs-lookup"><span data-stu-id="08a1c-171">Logically, the collections in the `FROM` clause are assumed to be part of an `n`-way cross join (except in the case of a 1-way cross join).</span></span> <span data-ttu-id="08a1c-172">Los alias de la cláusula `FROM` se procesan de izquierda a derecha y se agregan al ámbito actual como referencia.</span><span class="sxs-lookup"><span data-stu-id="08a1c-172">Aliases in the `FROM` clause are processed left to right, and are added to the current scope for later reference.</span></span> <span data-ttu-id="08a1c-173">Se supone que la cláusula `FROM` genera un multiconjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="08a1c-173">The `FROM` clause is assumed to produce a multiset of rows.</span></span> <span data-ttu-id="08a1c-174">Habrá un campo para cada elemento de la cláusula `FROM` que representa un elemento único de esa colección.</span><span class="sxs-lookup"><span data-stu-id="08a1c-174">There will be one field for each item in the `FROM` clause that represents a single element from that collection item.</span></span>

<span data-ttu-id="08a1c-175">La cláusula `FROM` genera lógicamente un multiconjunto de filas de tipo Row(c, d, e), donde los campos c, d y e se supone que son del tipo de elemento de `C`, `D` y `c.Names`.</span><span class="sxs-lookup"><span data-stu-id="08a1c-175">The `FROM` clause logically produces a multiset of rows of type Row(c, d, e) where fields c, d, and e are assumed to be of the element type of `C`, `D`, and `c.Names`.</span></span>

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="08a1c-176">introduce un alias para cada elemento de la cláusula `FROM` simple en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="08a1c-176">introduces an alias for each simple `FROM` clause item in scope.</span></span> <span data-ttu-id="08a1c-177">Por ejemplo, en el fragmento de código de la cláusula FROM siguiente, los nombres introducidos en el ámbito son c, d y e.</span><span class="sxs-lookup"><span data-stu-id="08a1c-177">For example, in the following FROM clause snippet, The names introduced into scope are c, d, and e.</span></span>

```sql
from (C as c join D as d) cross apply c.Names as e
```

<span data-ttu-id="08a1c-178">En [!INCLUDE[esql](../../../../../../includes/esql-md.md)] (a diferencia de Transact-SQL), la `FROM` cláusula solo introduce los alias en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="08a1c-178">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] (unlike Transact-SQL), the `FROM` clause only introduces the aliases into scope.</span></span> <span data-ttu-id="08a1c-179">Cualquier referencia a las columnas (propiedades) de estas colecciones se debe certificar con el alias.</span><span class="sxs-lookup"><span data-stu-id="08a1c-179">Any references to columns (properties) of these collections must be qualified with the alias.</span></span>

## <a name="pulling-up-keys-from-nested-queries"></a><span data-ttu-id="08a1c-180">Extraer claves de las consultas anidadas</span><span class="sxs-lookup"><span data-stu-id="08a1c-180">Pulling Up Keys from Nested Queries</span></span>

<span data-ttu-id="08a1c-181">No se admiten ciertos tipos de consultas que requieren la extracción de las claves de una consulta anidada.</span><span class="sxs-lookup"><span data-stu-id="08a1c-181">Certain types of queries that require pulling up keys from a nested query are not supported.</span></span> <span data-ttu-id="08a1c-182">Por ejemplo, la consulta siguiente es válida:</span><span class="sxs-lookup"><span data-stu-id="08a1c-182">For example, the following query is valid:</span></span>

```sql
select c.Orders from Customers as c
```

<span data-ttu-id="08a1c-183">Sin embargo, la consulta siguiente no es válida, porque la consulta anidada no tiene ninguna clave:</span><span class="sxs-lookup"><span data-stu-id="08a1c-183">However, the following query is not valid, because the nested query does not have any keys:</span></span>

```sql
select {1} from {2, 3}
```

## <a name="see-also"></a><span data-ttu-id="08a1c-184">Vea también</span><span class="sxs-lookup"><span data-stu-id="08a1c-184">See also</span></span>

- [<span data-ttu-id="08a1c-185">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="08a1c-185">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="08a1c-186">Expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="08a1c-186">Query Expressions</span></span>](query-expressions-entity-sql.md)
- [<span data-ttu-id="08a1c-187">Tipos estructurados que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="08a1c-187">Nullable Structured Types</span></span>](nullable-structured-types-entity-sql.md)
