---
description: 'Más información acerca de: Cómo difiere Entity SQL de Transact-SQL'
title: Diferencias entre Entity SQL y Transact-SQL
ms.date: 03/30/2017
ms.assetid: 9c9ee36d-f294-4c8b-a196-f0114c94f559
ms.openlocfilehash: 349dd64cc0e548ab0dc8d0e66e8bb14b58912d09
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696872"
---
# <a name="how-entity-sql-differs-from-transact-sql"></a><span data-ttu-id="241fb-103">Cómo difiere Entity SQL de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="241fb-103">How Entity SQL differs from Transact-SQL</span></span>

<span data-ttu-id="241fb-104">En este artículo se describen las diferencias entre Entity SQL y Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="241fb-104">This article describes the differences between Entity SQL and Transact-SQL.</span></span>  
  
## <a name="inheritance-and-relationships-support"></a><span data-ttu-id="241fb-105">Compatibilidad con herencia y relaciones</span><span class="sxs-lookup"><span data-stu-id="241fb-105">Inheritance and Relationships Support</span></span>  

 <span data-ttu-id="241fb-106">Entity SQL trabaja directamente con esquemas de entidades conceptuales y admite características del modelo conceptual como la herencia y las relaciones.</span><span class="sxs-lookup"><span data-stu-id="241fb-106">Entity SQL works directly with conceptual entity schemas and supports conceptual model features such as inheritance and relationships.</span></span>  
  
 <span data-ttu-id="241fb-107">Cuando se trabaja con la herencia, suele ser útil seleccionar instancias de un subtipo de una colección de instancias de supertipo.</span><span class="sxs-lookup"><span data-stu-id="241fb-107">When working with inheritance, it is often useful to select instances of a subtype from a collection of supertype instances.</span></span> <span data-ttu-id="241fb-108">El operador [untype](oftype-entity-sql.md) en Entity SQL (similar a `oftype` en secuencias de C#) proporciona esta capacidad.</span><span class="sxs-lookup"><span data-stu-id="241fb-108">The [oftype](oftype-entity-sql.md) operator in Entity SQL (similar to `oftype` in C# Sequences) provides this capability.</span></span>  
  
## <a name="support-for-collections"></a><span data-ttu-id="241fb-109">Compatibilidad con colecciones</span><span class="sxs-lookup"><span data-stu-id="241fb-109">Support for Collections</span></span>  

 <span data-ttu-id="241fb-110">Entity SQL trata las colecciones como entidades de primera clase.</span><span class="sxs-lookup"><span data-stu-id="241fb-110">Entity SQL treats collections as first-class entities.</span></span> <span data-ttu-id="241fb-111">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="241fb-111">For example:</span></span>  
  
- <span data-ttu-id="241fb-112">Las expresiones de colecciones son válidas en una cláusula `from`.</span><span class="sxs-lookup"><span data-stu-id="241fb-112">Collection expressions are valid in a `from` clause.</span></span>  
  
- <span data-ttu-id="241fb-113">Las subconsultas `in` y `exists` se han generalizado para permitir cualquier tipo de colección.</span><span class="sxs-lookup"><span data-stu-id="241fb-113">`in` and `exists` subqueries have been generalized to allow any collections.</span></span>  
  
     <span data-ttu-id="241fb-114">Una subconsulta es un tipo de colección.</span><span class="sxs-lookup"><span data-stu-id="241fb-114">A subquery is one kind of collection.</span></span> <span data-ttu-id="241fb-115">`e1 in e2` y `exists(e)` son las construcciones de Entity SQL para realizar estas operaciones.</span><span class="sxs-lookup"><span data-stu-id="241fb-115">`e1 in e2` and `exists(e)` are the Entity SQL constructs to perform these operations.</span></span>  
  
- <span data-ttu-id="241fb-116">Las operaciones Set, como `union`, `intersect` y `except`, funcionan ahora en colecciones.</span><span class="sxs-lookup"><span data-stu-id="241fb-116">Set operations, such as `union`, `intersect`, and `except`, now operate on collections.</span></span>  
  
- <span data-ttu-id="241fb-117">Las combinaciones funcionan en colecciones.</span><span class="sxs-lookup"><span data-stu-id="241fb-117">Joins operate on collections.</span></span>  
  
## <a name="support-for-expressions"></a><span data-ttu-id="241fb-118">Compatibilidad con expresiones</span><span class="sxs-lookup"><span data-stu-id="241fb-118">Support for Expressions</span></span>  

 <span data-ttu-id="241fb-119">Transact-SQL tiene subconsultas (tablas) y expresiones (filas y columnas).</span><span class="sxs-lookup"><span data-stu-id="241fb-119">Transact-SQL has subqueries (tables) and expressions (rows and columns).</span></span>  
  
 <span data-ttu-id="241fb-120">Para admitir colecciones y colecciones anidadas, Entity SQL convierte todo en una expresión.</span><span class="sxs-lookup"><span data-stu-id="241fb-120">To support collections and nested collections, Entity SQL makes everything an expression.</span></span> <span data-ttu-id="241fb-121">Entity SQL es más ajustable que Transact-SQL; todas las expresiones se pueden usar en cualquier lugar.</span><span class="sxs-lookup"><span data-stu-id="241fb-121">Entity SQL is more composable than Transact-SQL—every expression can be used anywhere.</span></span> <span data-ttu-id="241fb-122">Las expresiones de consulta siempre producen colecciones de los tipos proyectados y se pueden utilizar en cualquier parte donde se permita una expresión de colección.</span><span class="sxs-lookup"><span data-stu-id="241fb-122">Query expressions always result in collections of the projected types and can be used anywhere a collection expression is allowed.</span></span> <span data-ttu-id="241fb-123">Para obtener información sobre las expresiones de Transact-SQL que no se admiten en Entity SQL, vea [expresiones no admitidas](unsupported-expressions-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="241fb-123">For information about Transact-SQL expressions that are not supported in Entity SQL, see [Unsupported Expressions](unsupported-expressions-entity-sql.md).</span></span>  
  
 <span data-ttu-id="241fb-124">A continuación se muestran todas las consultas de Entity SQL válidas:</span><span class="sxs-lookup"><span data-stu-id="241fb-124">The following are all valid Entity SQL queries:</span></span>  
  
```sql  
1+2 *3  
"abc"  
row(1 as a, 2 as b)  
{ 1, 3, 5}
e1 union all e2  
set(e1)  
```  
  
## <a name="uniform-treatment-of-subqueries"></a><span data-ttu-id="241fb-125">Tratamiento uniforme de subconsultas</span><span class="sxs-lookup"><span data-stu-id="241fb-125">Uniform Treatment of Subqueries</span></span>  

 <span data-ttu-id="241fb-126">A partir de su énfasis en las tablas, Transact-SQL realiza la interpretación contextual de las subconsultas.</span><span class="sxs-lookup"><span data-stu-id="241fb-126">Given its emphasis on tables, Transact-SQL performs contextual interpretation of subqueries.</span></span> <span data-ttu-id="241fb-127">Por ejemplo, se considera que una subconsulta de la `from` cláusula es un conjunto múltiple (tabla).</span><span class="sxs-lookup"><span data-stu-id="241fb-127">For example, a subquery in the `from` clause is considered to be a multiset (table).</span></span> <span data-ttu-id="241fb-128">Pero la misma subconsulta utilizada en la cláusula `select` se considera una subconsulta escalar.</span><span class="sxs-lookup"><span data-stu-id="241fb-128">But the same subquery used in the `select` clause is considered to be a scalar subquery.</span></span> <span data-ttu-id="241fb-129">Del mismo modo, se considera que una subconsulta utilizada en el lado izquierdo de un `in` operador es una subconsulta escalar, mientras que se espera que el lado derecho sea una subconsulta MultiSet.</span><span class="sxs-lookup"><span data-stu-id="241fb-129">Similarly, a subquery used on the left side of an `in` operator is considered to be a scalar subquery, while the right side is expected to be a multiset subquery.</span></span>  
  
 <span data-ttu-id="241fb-130">Entity SQL elimina estas diferencias.</span><span class="sxs-lookup"><span data-stu-id="241fb-130">Entity SQL eliminates these differences.</span></span> <span data-ttu-id="241fb-131">Una expresión tiene una interpretación uniforme que no depende del contexto en el que se utiliza.</span><span class="sxs-lookup"><span data-stu-id="241fb-131">An expression has a uniform interpretation that does not depend on the context in which it is used.</span></span> <span data-ttu-id="241fb-132">Entity SQL considera que todas las subconsultas son subconsultas de MultiSet.</span><span class="sxs-lookup"><span data-stu-id="241fb-132">Entity SQL considers all subqueries to be multiset subqueries.</span></span> <span data-ttu-id="241fb-133">Si se desea un valor escalar de la subconsulta, Entity SQL proporciona el `anyelement` operador que opera en una colección (en este caso, la subconsulta) y extrae un valor singleton de la colección.</span><span class="sxs-lookup"><span data-stu-id="241fb-133">If a scalar value is desired from the subquery, Entity SQL provides the `anyelement` operator that operates on a collection (in this case, the subquery), and extracts a singleton value from the collection.</span></span>  
  
### <a name="avoiding-implicit-coercions-for-subqueries"></a><span data-ttu-id="241fb-134">Evitar conversiones implícitas en subconsultas</span><span class="sxs-lookup"><span data-stu-id="241fb-134">Avoiding Implicit Coercions for Subqueries</span></span>  

 <span data-ttu-id="241fb-135">Un efecto secundario relacionado del tratamiento uniforme de las subconsultas es la conversión implícita de las subconsultas en valores escalares.</span><span class="sxs-lookup"><span data-stu-id="241fb-135">A related side effect of uniform treatment of subqueries is implicit conversion of subqueries to scalar values.</span></span> <span data-ttu-id="241fb-136">En concreto, en Transact-SQL, un conjunto múltiple de filas (con un campo único) se convierte implícitamente en un valor escalar cuyo tipo de datos es el del campo.</span><span class="sxs-lookup"><span data-stu-id="241fb-136">Specifically, in Transact-SQL, a multiset of rows (with a single field) is implicitly converted into a scalar value whose data type is that of the field.</span></span>  
  
 <span data-ttu-id="241fb-137">Entity SQL no admite esta coerción implícita.</span><span class="sxs-lookup"><span data-stu-id="241fb-137">Entity SQL does not support this implicit coercion.</span></span> <span data-ttu-id="241fb-138">Entity SQL proporciona el `ANYELEMENT` operador para extraer un valor singleton de una colección y una `select value` cláusula para evitar la creación de un contenedor de filas durante una expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="241fb-138">Entity SQL provides the `ANYELEMENT` operator to extract a singleton value from a collection, and a `select value` clause to avoid creating a row-wrapper during a query expression.</span></span>  
  
## <a name="select-value-avoiding-the-implicit-row-wrapper"></a><span data-ttu-id="241fb-139">Seleccionar el valor: evitar el contenedor de filas implícitas</span><span class="sxs-lookup"><span data-stu-id="241fb-139">Select Value: Avoiding the Implicit Row Wrapper</span></span>  

 <span data-ttu-id="241fb-140">La cláusula SELECT de una subconsulta Transact-SQL crea implícitamente un contenedor de filas alrededor de los elementos de la cláusula.</span><span class="sxs-lookup"><span data-stu-id="241fb-140">The select clause in a Transact-SQL subquery implicitly creates a row wrapper around the items in the clause.</span></span> <span data-ttu-id="241fb-141">Esto implica que no podemos crear colecciones de valores escalares o de objetos.</span><span class="sxs-lookup"><span data-stu-id="241fb-141">This implies that we cannot create collections of scalars or objects.</span></span> <span data-ttu-id="241fb-142">Transact-SQL permite una conversión implícita entre un `rowtype` con un campo y un valor singleton del mismo tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="241fb-142">Transact-SQL allows an implicit coercion between a `rowtype` with one field and a singleton value of the same data type.</span></span>  
  
 <span data-ttu-id="241fb-143">Entity SQL proporciona la `select value` cláusula para omitir la construcción de filas implícita.</span><span class="sxs-lookup"><span data-stu-id="241fb-143">Entity SQL provides the `select value` clause to skip the implicit row construction.</span></span> <span data-ttu-id="241fb-144">Solo se puede especificar un elemento en una cláusula `select value`.</span><span class="sxs-lookup"><span data-stu-id="241fb-144">Only one item may be specified in a `select value` clause.</span></span> <span data-ttu-id="241fb-145">Cuando se utiliza este tipo de cláusula, no se crea ningún contenedor de filas en torno a los elementos de la `select` cláusula y se puede generar una colección de la forma deseada, por ejemplo, `select value a` .</span><span class="sxs-lookup"><span data-stu-id="241fb-145">When such a clause is used, no row wrapper is constructed around the items in the `select` clause, and a collection of the desired shape may be produced, for example, `select value a`.</span></span>  
  
 <span data-ttu-id="241fb-146">Entity SQL también proporciona el constructor de filas para construir filas arbitrarias.</span><span class="sxs-lookup"><span data-stu-id="241fb-146">Entity SQL also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="241fb-147">`select` toma uno o más elementos en la proyección y da como resultado un registro de datos con campos:</span><span class="sxs-lookup"><span data-stu-id="241fb-147">`select` takes one or more elements in the projection and results in a data record with fields:</span></span>  
  
 `select a, b, c`  
  
## <a name="left-correlation-and-aliasing"></a><span data-ttu-id="241fb-148">Correlación izquierda y uso de alias</span><span class="sxs-lookup"><span data-stu-id="241fb-148">Left Correlation and Aliasing</span></span>  

 <span data-ttu-id="241fb-149">En Transact-SQL, las expresiones de un ámbito determinado (una sola cláusula como `select` o `from` ) no pueden hacer referencia a expresiones definidas anteriormente en el mismo ámbito.</span><span class="sxs-lookup"><span data-stu-id="241fb-149">In Transact-SQL, expressions in a given scope (a single clause like `select` or `from`) cannot reference expressions defined earlier in the same scope.</span></span> <span data-ttu-id="241fb-150">Algunos dialectos de SQL (incluido Transact-SQL) admiten formas limitadas en la `from` cláusula.</span><span class="sxs-lookup"><span data-stu-id="241fb-150">Some dialects of SQL (including Transact-SQL) do support limited forms of these in the `from` clause.</span></span>  
  
 <span data-ttu-id="241fb-151">Entity SQL generaliza las correlaciones de la izquierda en la `from` cláusula y las trata de forma uniforme.</span><span class="sxs-lookup"><span data-stu-id="241fb-151">Entity SQL generalizes left correlations in the `from` clause, and treats them uniformly.</span></span> <span data-ttu-id="241fb-152">Las expresiones de la cláusula `from` pueden hacer referencia a definiciones anteriores (a la izquierda) en la misma cláusula sin necesidad de una sintaxis adicional.</span><span class="sxs-lookup"><span data-stu-id="241fb-152">Expressions in the `from` clause can reference earlier definitions (definitions to the left) in the same clause without the need for additional syntax.</span></span>  
  
 <span data-ttu-id="241fb-153">Entity SQL también impone restricciones adicionales en las consultas que implican `group by` cláusulas.</span><span class="sxs-lookup"><span data-stu-id="241fb-153">Entity SQL also imposes additional restrictions on queries involving `group by` clauses.</span></span> <span data-ttu-id="241fb-154">Las expresiones de la `select` cláusula y `having` de estas consultas solo pueden hacer referencia a las `group by` claves a través de sus alias.</span><span class="sxs-lookup"><span data-stu-id="241fb-154">Expressions in the `select` clause and `having` clause of such queries may only refer to the `group by` keys via their aliases.</span></span> <span data-ttu-id="241fb-155">La siguiente construcción es válida en Transact-SQL, pero no en Entity SQL:</span><span class="sxs-lookup"><span data-stu-id="241fb-155">The following construct is valid in Transact-SQL but are not in Entity SQL:</span></span>  
  
```sql  
SELECT t.x + t.y FROM T AS t group BY t.x + t.y
```  
  
 <span data-ttu-id="241fb-156">Para hacer esto en Entity SQL:</span><span class="sxs-lookup"><span data-stu-id="241fb-156">To do this in Entity SQL:</span></span>  
  
```sql  
SELET k FROM T AS t GROUP BY (t.x + t.y) AS k
```  
  
## <a name="referencing-columns-properties-of-tables-collections"></a><span data-ttu-id="241fb-157">Hacer referencia a columnas (propiedades) de tablas (colecciones)</span><span class="sxs-lookup"><span data-stu-id="241fb-157">Referencing Columns (Properties) of Tables (Collections)</span></span>  

 <span data-ttu-id="241fb-158">Todas las referencias de columna en Entity SQL deben estar calificadas con el alias de tabla.</span><span class="sxs-lookup"><span data-stu-id="241fb-158">All column references in Entity SQL must be qualified with the table alias.</span></span> <span data-ttu-id="241fb-159">La construcción siguiente (suponiendo que `a` es una columna válida de la tabla `T` ) es válida en TRANSACT-SQL, pero no en Entity SQL.</span><span class="sxs-lookup"><span data-stu-id="241fb-159">The following construct (assuming that `a` is a valid column of table `T`) is valid in Transact-SQL but not in Entity SQL.</span></span>  
  
```sql  
SELECT a FROM T
```  
  
 <span data-ttu-id="241fb-160">El formulario Entity SQL es</span><span class="sxs-lookup"><span data-stu-id="241fb-160">The Entity SQL form is</span></span>  
  
```sql  
SELECT t.a AS A FROM T AS t
```  
  
 <span data-ttu-id="241fb-161">Los alias de tabla son opcionales en la cláusula `from`.</span><span class="sxs-lookup"><span data-stu-id="241fb-161">The table aliases are optional in the `from` clause.</span></span> <span data-ttu-id="241fb-162">El nombre de la tabla se utiliza como alias implícito.</span><span class="sxs-lookup"><span data-stu-id="241fb-162">The name of the table is used as the implicit alias.</span></span> <span data-ttu-id="241fb-163">Entity SQL también permite el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="241fb-163">Entity SQL allows the following form as well:</span></span>  
  
```sql  
SELET Tab.a FROM Tab
```  
  
## <a name="navigation-through-objects"></a><span data-ttu-id="241fb-164">Navegación a través de objetos</span><span class="sxs-lookup"><span data-stu-id="241fb-164">Navigation Through Objects</span></span>  

 <span data-ttu-id="241fb-165">Transact-SQL usa la notación "." para hacer referencia a las columnas de una tabla (una fila de).</span><span class="sxs-lookup"><span data-stu-id="241fb-165">Transact-SQL uses the "." notation for referencing columns of (a row of) a table.</span></span> <span data-ttu-id="241fb-166">Entity SQL extiende esta notación (prestada de lenguajes de programación) para admitir la navegación a través de las propiedades de un objeto.</span><span class="sxs-lookup"><span data-stu-id="241fb-166">Entity SQL extends this notation (borrowed from programming languages) to support navigation through properties of an object.</span></span>  
  
 <span data-ttu-id="241fb-167">Por ejemplo, si `p` es una expresión de tipo Person, la siguiente es la sintaxis de Entity SQL para hacer referencia a la ciudad de la dirección de esta persona.</span><span class="sxs-lookup"><span data-stu-id="241fb-167">For example, if `p` is an expression of type Person, the following is the Entity SQL syntax for referencing the city of the address of this person.</span></span>  
  
```sql  
p.Address.City
```  
  
## <a name="no-support-for-"></a><span data-ttu-id="241fb-168">No se admite \*</span><span class="sxs-lookup"><span data-stu-id="241fb-168">No Support for \*</span></span>  

 <span data-ttu-id="241fb-169">Transact-SQL admite la sintaxis sin calificar \* como alias para toda la fila y la sintaxis completa \* (t. \* ) como un acceso directo para los campos de esa tabla.</span><span class="sxs-lookup"><span data-stu-id="241fb-169">Transact-SQL supports the unqualified \* syntax as an alias for the entire row, and the qualified \* syntax (t.\*) as a shortcut for the fields of that table.</span></span> <span data-ttu-id="241fb-170">Además, Transact-SQL permite un agregado Count () especial \* , que incluye valores NULL.</span><span class="sxs-lookup"><span data-stu-id="241fb-170">In addition, Transact-SQL allows for a special count(\*) aggregate, which includes nulls.</span></span>  
  
 <span data-ttu-id="241fb-171">Entity SQL no admite la construcción \*.</span><span class="sxs-lookup"><span data-stu-id="241fb-171">Entity SQL does not support the \* construct.</span></span> <span data-ttu-id="241fb-172">Las consultas de Transact-SQL del formulario `select * from T` y `select T1.* from T1, T2...` se pueden expresar en Entity SQL como `select value t from T as t` y `select value t1 from T1 as t1, T2 as t2...` , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="241fb-172">Transact-SQL queries of the form `select * from T` and `select T1.* from T1, T2...` can be expressed in Entity SQL as `select value t from T as t` and `select value t1 from T1 as t1, T2 as t2...`, respectively.</span></span> <span data-ttu-id="241fb-173">Además, estas construcciones administran la herencia (capacidad de sustitución de valores), mientras que las variantes de `select *` se restringen a las propiedades de nivel superior del tipo declarado.</span><span class="sxs-lookup"><span data-stu-id="241fb-173">Additionally, these constructs handle inheritance (value substitutability), while the `select *` variants are restricted to top-level properties of the declared type.</span></span>  
  
 <span data-ttu-id="241fb-174">Entity SQL no admite el `count(*)` agregado.</span><span class="sxs-lookup"><span data-stu-id="241fb-174">Entity SQL does not support the `count(*)` aggregate.</span></span> <span data-ttu-id="241fb-175">Utilice `count(0)` en su lugar.</span><span class="sxs-lookup"><span data-stu-id="241fb-175">Use `count(0)` instead.</span></span>  
  
## <a name="changes-to-group-by"></a><span data-ttu-id="241fb-176">Cambios de Group By</span><span class="sxs-lookup"><span data-stu-id="241fb-176">Changes to Group By</span></span>  

 <span data-ttu-id="241fb-177">Entity SQL admite el alias de `group by` claves.</span><span class="sxs-lookup"><span data-stu-id="241fb-177">Entity SQL supports aliasing of `group by` keys.</span></span> <span data-ttu-id="241fb-178">Las expresiones de la cláusula `select` y de la cláusula `having` deben hacer referencia a las claves `group by` a través de estos alias.</span><span class="sxs-lookup"><span data-stu-id="241fb-178">Expressions in the `select` clause and `having` clause must refer to the `group by` keys via these aliases.</span></span> <span data-ttu-id="241fb-179">Por ejemplo, esta sintaxis de Entity SQL:</span><span class="sxs-lookup"><span data-stu-id="241fb-179">For example, this Entity SQL syntax:</span></span>  
  
```sql  
SELECT k1, count(t.a), sum(t.a)
FROM T AS t
GROUP BY t.b + t.c AS k1
```  
  
 <span data-ttu-id="241fb-180">... es equivalente a la siguiente instrucción Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="241fb-180">...is equivalent to the following Transact-SQL:</span></span>  
  
```sql  
SELECT b + c, count(*), sum(a)
FROM T
GROUP BY b + c
```  
  
## <a name="collection-based-aggregates"></a><span data-ttu-id="241fb-181">Agregados basados en colecciones</span><span class="sxs-lookup"><span data-stu-id="241fb-181">Collection-Based Aggregates</span></span>  

 <span data-ttu-id="241fb-182">Entity SQL admite dos tipos de agregados.</span><span class="sxs-lookup"><span data-stu-id="241fb-182">Entity SQL supports two kinds of aggregates.</span></span>  
  
 <span data-ttu-id="241fb-183">Los agregados basados en colecciones operan en colecciones y generan el resultado agregado.</span><span class="sxs-lookup"><span data-stu-id="241fb-183">Collection-based aggregates operate on collections and produce the aggregated result.</span></span> <span data-ttu-id="241fb-184">Estos pueden aparecer en cualquier parte de la consulta y no requieren una cláusula `group by`.</span><span class="sxs-lookup"><span data-stu-id="241fb-184">These can appear anywhere in the query, and do not require a `group by` clause.</span></span> <span data-ttu-id="241fb-185">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="241fb-185">For example:</span></span>  
  
```sql  
SELECT t.a AS a, count({1,2,3}) AS b FROM T AS t
```  
  
 <span data-ttu-id="241fb-186">Entity SQL también admite agregados de estilo SQL.</span><span class="sxs-lookup"><span data-stu-id="241fb-186">Entity SQL also supports SQL-style aggregates.</span></span> <span data-ttu-id="241fb-187">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="241fb-187">For example:</span></span>  
  
```sql  
SELECT a, sum(t.b) FROM T AS t GROUP BY t.a AS a
```  
  
## <a name="order-by-clause-usage"></a><span data-ttu-id="241fb-188">Uso de la cláusula ORDER BY</span><span class="sxs-lookup"><span data-stu-id="241fb-188">ORDER BY Clause Usage</span></span>  

<span data-ttu-id="241fb-189">Transact-SQL permite `ORDER BY` que las cláusulas se especifiquen solo en el bloque de nivel superior `SELECT .. FROM .. WHERE` .</span><span class="sxs-lookup"><span data-stu-id="241fb-189">Transact-SQL allows `ORDER BY` clauses to be specified only in the topmost `SELECT .. FROM .. WHERE` block.</span></span> <span data-ttu-id="241fb-190">En Entity SQL, puede usar una expresión anidada `ORDER BY` y se puede colocar en cualquier parte de la consulta, pero no se conserva la ordenación en una consulta anidada.</span><span class="sxs-lookup"><span data-stu-id="241fb-190">In Entity SQL, you can use a nested `ORDER BY` expression and it can be placed anywhere in the query, but ordering in a nested query is not preserved.</span></span>  
  
```sql  
-- The following query will order the results by the last name  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact AS C1
        ORDER BY C1.LastName  
```  
  
```sql  
-- In the following query ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="identifiers"></a><span data-ttu-id="241fb-191">Identificadores</span><span class="sxs-lookup"><span data-stu-id="241fb-191">Identifiers</span></span>  

 <span data-ttu-id="241fb-192">En Transact-SQL, la comparación de identificadores se basa en la intercalación de la base de datos actual.</span><span class="sxs-lookup"><span data-stu-id="241fb-192">In Transact-SQL, identifier comparison is based on the collation of the current database.</span></span> <span data-ttu-id="241fb-193">En Entity SQL, los identificadores siempre distinguen mayúsculas de minúsculas y distinguen acentos (es decir, Entity SQL distingue entre caracteres acentuados y no acentuados; por ejemplo, ' a ' no es igual a ' é ').</span><span class="sxs-lookup"><span data-stu-id="241fb-193">In Entity SQL, identifiers are always case insensitive and accent sensitive (that is, Entity SQL distinguishes between accented and unaccented characters; for example, 'a' is not equal to 'ấ').</span></span> <span data-ttu-id="241fb-194">Entity SQL trata las versiones de letras que parecen iguales pero proceden de páginas de códigos diferentes como caracteres distintos.</span><span class="sxs-lookup"><span data-stu-id="241fb-194">Entity SQL treats versions of letters that appear the same but are from different code pages as different characters.</span></span> <span data-ttu-id="241fb-195">Para obtener más información, vea [juego de caracteres de entrada](input-character-set-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="241fb-195">For more information, see [Input Character Set](input-character-set-entity-sql.md).</span></span>  
  
## <a name="transact-sql-functionality-not-available-in-entity-sql"></a><span data-ttu-id="241fb-196">Funcionalidad de Transact-SQL no disponible en Entity SQL</span><span class="sxs-lookup"><span data-stu-id="241fb-196">Transact-SQL Functionality Not Available in Entity SQL</span></span>  

 <span data-ttu-id="241fb-197">La siguiente funcionalidad de Transact-SQL no está disponible en Entity SQL.</span><span class="sxs-lookup"><span data-stu-id="241fb-197">The following Transact-SQL functionality is not available in Entity SQL.</span></span>  
  
 <span data-ttu-id="241fb-198">DML</span><span class="sxs-lookup"><span data-stu-id="241fb-198">DML</span></span>  
 <span data-ttu-id="241fb-199">Actualmente, Entity SQL no proporciona compatibilidad con instrucciones DML (Insert, Update y Delete).</span><span class="sxs-lookup"><span data-stu-id="241fb-199">Entity SQL currently provides no support for DML statements (insert, update, delete).</span></span>  
  
 <span data-ttu-id="241fb-200">DDL</span><span class="sxs-lookup"><span data-stu-id="241fb-200">DDL</span></span>  
 <span data-ttu-id="241fb-201">Entity SQL no proporciona compatibilidad con DDL en la versión actual.</span><span class="sxs-lookup"><span data-stu-id="241fb-201">Entity SQL provides no support for DDL in the current version.</span></span>  
  
 <span data-ttu-id="241fb-202">Programación imperativa</span><span class="sxs-lookup"><span data-stu-id="241fb-202">Imperative Programming</span></span>  
 <span data-ttu-id="241fb-203">Entity SQL no proporciona compatibilidad con la programación imperativa, a diferencia de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="241fb-203">Entity SQL provides no support for imperative programming, unlike Transact-SQL.</span></span> <span data-ttu-id="241fb-204">Utilice un lenguaje de programación en su lugar.</span><span class="sxs-lookup"><span data-stu-id="241fb-204">Use a programming language instead.</span></span>  
  
 <span data-ttu-id="241fb-205">Funciones de agrupamiento</span><span class="sxs-lookup"><span data-stu-id="241fb-205">Grouping Functions</span></span>  
 <span data-ttu-id="241fb-206">Entity SQL aún no proporciona compatibilidad con las funciones de agrupación (por ejemplo, CUBE, ROLLUP y GROUPING_SET).</span><span class="sxs-lookup"><span data-stu-id="241fb-206">Entity SQL does not yet provide support for grouping functions (for example, CUBE, ROLLUP, and GROUPING_SET).</span></span>  
  
 <span data-ttu-id="241fb-207">Funciones analíticas</span><span class="sxs-lookup"><span data-stu-id="241fb-207">Analytic Functions</span></span>  
 <span data-ttu-id="241fb-208">Entity SQL no proporciona compatibilidad con las funciones analíticas.</span><span class="sxs-lookup"><span data-stu-id="241fb-208">Entity SQL does not (yet) provide support for analytic functions.</span></span>  
  
 <span data-ttu-id="241fb-209">Funciones y operadores integrados</span><span class="sxs-lookup"><span data-stu-id="241fb-209">Built-in Functions, Operators</span></span>  
 <span data-ttu-id="241fb-210">Entity SQL admite un subconjunto de funciones y operadores integrados de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="241fb-210">Entity SQL supports a subset of Transact-SQL's built in functions and operators.</span></span> <span data-ttu-id="241fb-211">Es probable que estos operadores y funciones sean admitidos por los principales proveedores de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="241fb-211">These operators and functions are likely to be supported by the major store providers.</span></span> <span data-ttu-id="241fb-212">Entity SQL usa las funciones específicas del almacén declaradas en un manifiesto del proveedor.</span><span class="sxs-lookup"><span data-stu-id="241fb-212">Entity SQL uses the store-specific functions declared in a provider manifest.</span></span> <span data-ttu-id="241fb-213">Además, el Entity Framework permite declarar funciones de almacenamiento existentes integradas y definidas por el usuario, para que Entity SQL las use.</span><span class="sxs-lookup"><span data-stu-id="241fb-213">Additionally, the Entity Framework allows you to declare built-in and user-defined existing store functions, for Entity SQL to use.</span></span>  
  
 <span data-ttu-id="241fb-214">Sugerencias</span><span class="sxs-lookup"><span data-stu-id="241fb-214">Hints</span></span>  
 <span data-ttu-id="241fb-215">Entity SQL no proporciona mecanismos para las sugerencias de consulta.</span><span class="sxs-lookup"><span data-stu-id="241fb-215">Entity SQL does not provide mechanisms for query hints.</span></span>  
  
 <span data-ttu-id="241fb-216">Resultados de un consulta por lotes</span><span class="sxs-lookup"><span data-stu-id="241fb-216">Batching Query Results</span></span>  
 <span data-ttu-id="241fb-217">Entity SQL no admite el procesamiento por lotes de los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="241fb-217">Entity SQL does not support batching query results.</span></span> <span data-ttu-id="241fb-218">Por ejemplo, el siguiente código de Transact-SQL es válido (se envía como un lote):</span><span class="sxs-lookup"><span data-stu-id="241fb-218">For example, the following is valid Transact-SQL (sending as a batch):</span></span>  
  
```sql  
SELECT * FROM products;
SELECT * FROM catagories;
```  
  
 <span data-ttu-id="241fb-219">Sin embargo, no se admite el Entity SQL equivalente:</span><span class="sxs-lookup"><span data-stu-id="241fb-219">However, the equivalent Entity SQL is not supported:</span></span>  
  
```sql  
SELECT value p FROM Products AS p;
SELECT value c FROM Categories AS c;
```  
  
 <span data-ttu-id="241fb-220">Entity SQL solo admite una instrucción de consulta de generación de resultados por comando.</span><span class="sxs-lookup"><span data-stu-id="241fb-220">Entity SQL only supports one result-producing query statement per command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="241fb-221">Vea también</span><span class="sxs-lookup"><span data-stu-id="241fb-221">See also</span></span>

- [<span data-ttu-id="241fb-222">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="241fb-222">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="241fb-223">Expresiones no admitidas</span><span class="sxs-lookup"><span data-stu-id="241fb-223">Unsupported Expressions</span></span>](unsupported-expressions-entity-sql.md)
