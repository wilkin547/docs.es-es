---
title: Diferencias entre Entity SQL y Transact-SQL
ms.date: 03/30/2017
ms.assetid: 9c9ee36d-f294-4c8b-a196-f0114c94f559
ms.openlocfilehash: 299cb9bbe90c72619cf809a8fc673fca456bd6fd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150236"
---
# <a name="how-entity-sql-differs-from-transact-sql"></a><span data-ttu-id="60558-102">Diferencias entre Entity SQL y Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="60558-102">How Entity SQL Differs from Transact-SQL</span></span>
<span data-ttu-id="60558-103">En este tema se [!INCLUDE[esql](../../../../../../includes/esql-md.md)] describen las diferencias entre Y Transact-SQLTransact-SQL .</span><span class="sxs-lookup"><span data-stu-id="60558-103">This topic describes the differences between [!INCLUDE[esql](../../../../../../includes/esql-md.md)] and Transact-SQL.</span></span>  
  
## <a name="inheritance-and-relationships-support"></a><span data-ttu-id="60558-104">Compatibilidad con herencia y relaciones</span><span class="sxs-lookup"><span data-stu-id="60558-104">Inheritance and Relationships Support</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="60558-105">funciona directamente con esquemas de entidad conceptual y admite características de modelo conceptual como herencia y relaciones.</span><span class="sxs-lookup"><span data-stu-id="60558-105">works directly with conceptual entity schemas and supports conceptual model features such as inheritance and relationships.</span></span>  
  
 <span data-ttu-id="60558-106">Cuando se trabaja con la herencia, suele ser útil seleccionar instancias de un subtipo de una colección de instancias de supertipo.</span><span class="sxs-lookup"><span data-stu-id="60558-106">When working with inheritance, it is often useful to select instances of a subtype from a collection of supertype instances.</span></span> <span data-ttu-id="60558-107">El operador [oftype](oftype-entity-sql.md) [!INCLUDE[esql](../../../../../../includes/esql-md.md)] in `oftype` (similar a en secuencias de C) proporciona esta capacidad.</span><span class="sxs-lookup"><span data-stu-id="60558-107">The [oftype](oftype-entity-sql.md) operator in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] (similar to `oftype` in C# Sequences) provides this capability.</span></span>  
  
## <a name="support-for-collections"></a><span data-ttu-id="60558-108">Compatibilidad con colecciones</span><span class="sxs-lookup"><span data-stu-id="60558-108">Support for Collections</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="60558-109">trata las colecciones como entidades de primera clase.</span><span class="sxs-lookup"><span data-stu-id="60558-109">treats collections as first-class entities.</span></span> <span data-ttu-id="60558-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="60558-110">For example:</span></span>  
  
- <span data-ttu-id="60558-111">Las expresiones de colecciones son válidas en una cláusula `from`.</span><span class="sxs-lookup"><span data-stu-id="60558-111">Collection expressions are valid in a `from` clause.</span></span>  
  
- <span data-ttu-id="60558-112">Las subconsultas `in` y `exists` se han generalizado para permitir cualquier tipo de colección.</span><span class="sxs-lookup"><span data-stu-id="60558-112">`in` and `exists` subqueries have been generalized to allow any collections.</span></span>  
  
     <span data-ttu-id="60558-113">Una subconsulta es un tipo de colección.</span><span class="sxs-lookup"><span data-stu-id="60558-113">A subquery is one kind of collection.</span></span> <span data-ttu-id="60558-114">`e1 in e2` y `exists(e)` son las construcciones de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] que permiten realizar estas operaciones.</span><span class="sxs-lookup"><span data-stu-id="60558-114">`e1 in e2` and `exists(e)` are the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] constructs to perform these operations.</span></span>  
  
- <span data-ttu-id="60558-115">Las operaciones Set, como `union`, `intersect` y `except`, funcionan ahora en colecciones.</span><span class="sxs-lookup"><span data-stu-id="60558-115">Set operations, such as `union`, `intersect`, and `except`, now operate on collections.</span></span>  
  
- <span data-ttu-id="60558-116">Las combinaciones funcionan en colecciones.</span><span class="sxs-lookup"><span data-stu-id="60558-116">Joins operate on collections.</span></span>  
  
## <a name="support-for-expressions"></a><span data-ttu-id="60558-117">Compatibilidad con expresiones</span><span class="sxs-lookup"><span data-stu-id="60558-117">Support for Expressions</span></span>  
 <span data-ttu-id="60558-118">Transact-SQLTransact-SQL tiene subconsultas (tablas) y expresiones (filas y columnas).</span><span class="sxs-lookup"><span data-stu-id="60558-118">Transact-SQL has subqueries (tables) and expressions (rows and columns).</span></span>  
  
 <span data-ttu-id="60558-119">Para admitir colecciones [!INCLUDE[esql](../../../../../../includes/esql-md.md)] y colecciones anidadas, hace que todo sea una expresión.</span><span class="sxs-lookup"><span data-stu-id="60558-119">To support collections and nested collections, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] makes everything an expression.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="60558-120">es más componible que Transact-SQLTransact-SQL: cada expresión se puede usar en cualquier lugar.</span><span class="sxs-lookup"><span data-stu-id="60558-120">is more composable than Transact-SQL—every expression can be used anywhere.</span></span> <span data-ttu-id="60558-121">Las expresiones de consulta siempre producen colecciones de los tipos proyectados y se pueden utilizar en cualquier parte donde se permita una expresión de colección.</span><span class="sxs-lookup"><span data-stu-id="60558-121">Query expressions always result in collections of the projected types and can be used anywhere a collection expression is allowed.</span></span> <span data-ttu-id="60558-122">Para obtener información acerca de las [!INCLUDE[esql](../../../../../../includes/esql-md.md)]expresiones transact-SQLTransact-SQL que no se admiten en , vea [Expresiones no admitidas](unsupported-expressions-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="60558-122">For information about Transact-SQL expressions that are not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)], see [Unsupported Expressions](unsupported-expressions-entity-sql.md).</span></span>  
  
 <span data-ttu-id="60558-123">A continuación se muestran consultas válidas de [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="60558-123">The following are all valid [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries:</span></span>  
  
```sql  
1+2 *3  
"abc"  
row(1 as a, 2 as b)  
{ 1, 3, 5}
e1 union all e2  
set(e1)  
```  
  
## <a name="uniform-treatment-of-subqueries"></a><span data-ttu-id="60558-124">Tratamiento uniforme de subconsultas</span><span class="sxs-lookup"><span data-stu-id="60558-124">Uniform Treatment of Subqueries</span></span>  
 <span data-ttu-id="60558-125">Dado su énfasis en las tablas, Transact-SQLTransact-SQL realiza una interpretación contextual de las subconsultas.</span><span class="sxs-lookup"><span data-stu-id="60558-125">Given its emphasis on tables, Transact-SQL performs contextual interpretation of subqueries.</span></span> <span data-ttu-id="60558-126">Por ejemplo, una subconsulta de la `from` cláusula se considera un conjunto múltiple (tabla).</span><span class="sxs-lookup"><span data-stu-id="60558-126">For example, a subquery in the `from` clause is considered to be a multiset (table).</span></span> <span data-ttu-id="60558-127">Pero la misma subconsulta utilizada en la cláusula `select` se considera una subconsulta escalar.</span><span class="sxs-lookup"><span data-stu-id="60558-127">But the same subquery used in the `select` clause is considered to be a scalar subquery.</span></span> <span data-ttu-id="60558-128">De forma similar, una subconsulta `in` utilizada en el lado izquierdo de un operador se considera una subconsulta escalar, mientras que se espera que el lado derecho sea una subconsulta multiconjunto.</span><span class="sxs-lookup"><span data-stu-id="60558-128">Similarly, a subquery used on the left side of an `in` operator is considered to be a scalar subquery, while the right side is expected to be a multiset subquery.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="60558-129">elimina estas diferencias.</span><span class="sxs-lookup"><span data-stu-id="60558-129">eliminates these differences.</span></span> <span data-ttu-id="60558-130">Una expresión tiene una interpretación uniforme que no depende del contexto en el que se utiliza.</span><span class="sxs-lookup"><span data-stu-id="60558-130">An expression has a uniform interpretation that does not depend on the context in which it is used.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="60558-131">considera que todas las subconsultas son subconsultas multiconjunto.</span><span class="sxs-lookup"><span data-stu-id="60558-131">considers all subqueries to be multiset subqueries.</span></span> <span data-ttu-id="60558-132">Si se desea un valor escalar de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] la `anyelement` subconsulta, proporciona el operador que opera en una colección (en este caso, la subconsulta) y extrae un valor singleton de la colección.</span><span class="sxs-lookup"><span data-stu-id="60558-132">If a scalar value is desired from the subquery, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] provides the `anyelement` operator that operates on a collection (in this case, the subquery), and extracts a singleton value from the collection.</span></span>  
  
### <a name="avoiding-implicit-coercions-for-subqueries"></a><span data-ttu-id="60558-133">Evitar conversiones implícitas en subconsultas</span><span class="sxs-lookup"><span data-stu-id="60558-133">Avoiding Implicit Coercions for Subqueries</span></span>  
 <span data-ttu-id="60558-134">Un efecto secundario relacionado del tratamiento uniforme de las subconsultas es la conversión implícita de las subconsultas en valores escalares.</span><span class="sxs-lookup"><span data-stu-id="60558-134">A related side effect of uniform treatment of subqueries is implicit conversion of subqueries to scalar values.</span></span> <span data-ttu-id="60558-135">En concreto, en Transact-SQLTransact-SQL, un conjunto múltiple de filas (con un solo campo) se convierte implícitamente en un valor escalar cuyo tipo de datos es el del campo.</span><span class="sxs-lookup"><span data-stu-id="60558-135">Specifically, in Transact-SQL, a multiset of rows (with a single field) is implicitly converted into a scalar value whose data type is that of the field.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="60558-136">no admite esta conversión implícita.</span><span class="sxs-lookup"><span data-stu-id="60558-136">does not support this implicit coercion.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="60558-137">proporciona el operador ANYELEMENT para extraer un valor singleton de una colección y una cláusula `select value` para evitar crear un contenedor de filas durante una expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="60558-137">provides the ANYELEMENT operator to extract a singleton value from a collection, and a `select value` clause to avoid creating a row-wrapper during a query expression.</span></span>  
  
## <a name="select-value-avoiding-the-implicit-row-wrapper"></a><span data-ttu-id="60558-138">Seleccionar el valor: evitar el contenedor de filas implícitas</span><span class="sxs-lookup"><span data-stu-id="60558-138">Select Value: Avoiding the Implicit Row Wrapper</span></span>  
 <span data-ttu-id="60558-139">La cláusula select de una subconsulta de Transact-SQLTransact-SQL crea implícitamente un contenedor de filas alrededor de los elementos de la cláusula.</span><span class="sxs-lookup"><span data-stu-id="60558-139">The select clause in a Transact-SQL subquery implicitly creates a row wrapper around the items in the clause.</span></span> <span data-ttu-id="60558-140">Esto implica que no podemos crear colecciones de valores escalares o de objetos.</span><span class="sxs-lookup"><span data-stu-id="60558-140">This implies that we cannot create collections of scalars or objects.</span></span> <span data-ttu-id="60558-141">Transact-SQLTransact-SQL permite una coerción implícita entre un tipo de fila con un campo y un valor singleton del mismo tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="60558-141">Transact-SQL allows an implicit coercion between a rowtype with one field, and a singleton value of the same data type.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="60558-142">proporciona la cláusula `select value` para omitir la creación de filas implícitas.</span><span class="sxs-lookup"><span data-stu-id="60558-142">provides the `select value` clause to skip the implicit row construction.</span></span> <span data-ttu-id="60558-143">Solo se puede especificar un elemento en una cláusula `select value`.</span><span class="sxs-lookup"><span data-stu-id="60558-143">Only one item may be specified in a `select value` clause.</span></span> <span data-ttu-id="60558-144">Cuando se utiliza este tipo de cláusula, no se crea ningún contenedor de filas en torno a los elementos de la cláusula `select` y se puede generar una colección de la forma deseada, por ejemplo: `select value a`.</span><span class="sxs-lookup"><span data-stu-id="60558-144">When such a clause is used, no row wrapper is constructed around the items in the `select` clause, and a collection of the desired shape may be produced, for example: `select value a`.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="60558-145">también proporciona el constructor de filas para crear filas arbitrarias.</span><span class="sxs-lookup"><span data-stu-id="60558-145">also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="60558-146">La cláusula `select` toma uno o más elementos en la proyección y devuelve un registro de datos con campos, de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="60558-146">`select` takes one or more elements in the projection and results in a data record with fields, as follows:</span></span>  
  
 `select a, b, c`  
  
## <a name="left-correlation-and-aliasing"></a><span data-ttu-id="60558-147">Correlación izquierda y uso de alias</span><span class="sxs-lookup"><span data-stu-id="60558-147">Left Correlation and Aliasing</span></span>  
 <span data-ttu-id="60558-148">En Transact-SQLTransact-SQL, las expresiones `select` de `from`un ámbito determinado (una sola cláusula como o ) no pueden hacer referencia a expresiones definidas anteriormente en el mismo ámbito.</span><span class="sxs-lookup"><span data-stu-id="60558-148">In Transact-SQL, expressions in a given scope (a single clause like `select` or `from`) cannot reference expressions defined earlier in the same scope.</span></span> <span data-ttu-id="60558-149">Algunos dialectos de SQL (incluido Transact-SQLTransact-SQL) admiten formas limitadas de estos en la `from` cláusula.</span><span class="sxs-lookup"><span data-stu-id="60558-149">Some dialects of SQL (including Transact-SQL) do support limited forms of these in the `from` clause.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="60558-150">generaliza las correlaciones `from` izquierdas en la cláusula y las trata uniformemente.</span><span class="sxs-lookup"><span data-stu-id="60558-150">generalizes left correlations in the `from` clause, and treats them uniformly.</span></span> <span data-ttu-id="60558-151">Las expresiones de la cláusula `from` pueden hacer referencia a definiciones anteriores (a la izquierda) en la misma cláusula sin necesidad de una sintaxis adicional.</span><span class="sxs-lookup"><span data-stu-id="60558-151">Expressions in the `from` clause can reference earlier definitions (definitions to the left) in the same clause without the need for additional syntax.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="60558-152">también impone restricciones adicionales en consultas que afectan a cláusulas `group by`.</span><span class="sxs-lookup"><span data-stu-id="60558-152">also imposes additional restrictions on queries involving `group by` clauses.</span></span> <span data-ttu-id="60558-153">Las expresiones de la `select` cláusula y `having` cláusula `group by` de dichas consultas solo pueden hacer referencia a las claves a través de sus alias.</span><span class="sxs-lookup"><span data-stu-id="60558-153">Expressions in the `select` clause and `having` clause of such queries may only refer to the `group by` keys via their aliases.</span></span> <span data-ttu-id="60558-154">La siguiente construcción es válida en Transact-SQLTransact-SQL, pero no está en: [!INCLUDE[esql](../../../../../../includes/esql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60558-154">The following construct is valid in Transact-SQL but are not in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span></span>  
  
```sql  
SELECT t.x + t.y FROM T AS t group BY t.x + t.y
```  
  
 <span data-ttu-id="60558-155">Para hacer esto en [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="60558-155">To do this in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span></span>  
  
```sql  
SELET k FROM T AS t GROUP BY (t.x + t.y) AS k
```  
  
## <a name="referencing-columns-properties-of-tables-collections"></a><span data-ttu-id="60558-156">Hacer referencia a columnas (propiedades) de tablas (colecciones)</span><span class="sxs-lookup"><span data-stu-id="60558-156">Referencing Columns (Properties) of Tables (Collections)</span></span>  
 <span data-ttu-id="60558-157">Todas las referencias de columna de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se deben calificar con el alias de la tabla.</span><span class="sxs-lookup"><span data-stu-id="60558-157">All column references in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] must be qualified with the table alias.</span></span> <span data-ttu-id="60558-158">La siguiente construcción (suponiendo que `a` es `T`una columna válida de tabla [!INCLUDE[esql](../../../../../../includes/esql-md.md)]) es válida en Transact-SQLTransact-SQL pero no en .</span><span class="sxs-lookup"><span data-stu-id="60558-158">The following construct (assuming that `a` is a valid column of table `T`) is valid in Transact-SQL but not in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
```sql  
SELECT a FROM T
```  
  
 <span data-ttu-id="60558-159">El formato de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] es:</span><span class="sxs-lookup"><span data-stu-id="60558-159">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] form is</span></span>  
  
```sql  
SELECT t.a AS A FROM T AS t
```  
  
 <span data-ttu-id="60558-160">Los alias de tabla son opcionales en la cláusula `from`.</span><span class="sxs-lookup"><span data-stu-id="60558-160">The table aliases are optional in the `from` clause.</span></span> <span data-ttu-id="60558-161">El nombre de la tabla se utiliza como alias implícito.</span><span class="sxs-lookup"><span data-stu-id="60558-161">The name of the table is used as the implicit alias.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="60558-162">también permite el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="60558-162">allows the following form as well:</span></span>  
  
```sql  
SELET Tab.a FROM Tab
```  
  
## <a name="navigation-through-objects"></a><span data-ttu-id="60558-163">Navegación a través de objetos</span><span class="sxs-lookup"><span data-stu-id="60558-163">Navigation Through Objects</span></span>  
 <span data-ttu-id="60558-164">Transact-SQLTransact-SQL usa la notación "." para hacer referencia a columnas de (una fila de) una tabla.</span><span class="sxs-lookup"><span data-stu-id="60558-164">Transact-SQL uses the "." notation for referencing columns of (a row of) a table.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="60558-165">amplía esta notación (que toma prestada de los lenguajes de programación) para admitir la navegación a través de las propiedades de un objeto.</span><span class="sxs-lookup"><span data-stu-id="60558-165">extends this notation (borrowed from programming languages) to support navigation through properties of an object.</span></span>  
  
 <span data-ttu-id="60558-166">Por ejemplo, si `p` es una expresión de tipo Persona, lo siguiente es la sintaxis de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] para hacer referencia a la ciudad de la dirección de esta persona.</span><span class="sxs-lookup"><span data-stu-id="60558-166">For example, if `p` is an expression of type Person, the following is the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] syntax for referencing the city of the address of this person.</span></span>  
  
```sql  
p.Address.City
```  
  
## <a name="no-support-for-"></a><span data-ttu-id="60558-167">No hay compatibilidad con \*</span><span class="sxs-lookup"><span data-stu-id="60558-167">No Support for \*</span></span>  
 <span data-ttu-id="60558-168">Transact-SQLTransact-SQL admite la sintaxis \* no calificada \* como alias\*para toda la fila y la sintaxis calificada (t. ) como método abreviado para los campos de esa tabla.</span><span class="sxs-lookup"><span data-stu-id="60558-168">Transact-SQL supports the unqualified \* syntax as an alias for the entire row, and the qualified \* syntax (t.\*) as a shortcut for the fields of that table.</span></span> <span data-ttu-id="60558-169">Además, Transact-SQLTransact-SQL\*permite un agregado count( ) especial, que incluye valores NULL.</span><span class="sxs-lookup"><span data-stu-id="60558-169">In addition, Transact-SQL allows for a special count(\*) aggregate, which includes nulls.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="60558-170">no admite la construcción \*.</span><span class="sxs-lookup"><span data-stu-id="60558-170">does not support the \* construct.</span></span> <span data-ttu-id="60558-171">Consultas de Transact-SQLTransact-SQL del [!INCLUDE[esql](../../../../../../includes/esql-md.md)] `select value t from T as t` formulario `select value t1 from T1 as t1, T2 as t2...` `select * from T` y `select T1.* from T1, T2...` se pueden expresar en como y , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="60558-171">Transact-SQL queries of the form `select * from T` and `select T1.* from T1, T2...` can be expressed in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] as `select value t from T as t` and `select value t1 from T1 as t1, T2 as t2...`, respectively.</span></span> <span data-ttu-id="60558-172">Además, estas construcciones administran la herencia (capacidad de sustitución de valores), mientras que las variantes de `select *` se restringen a las propiedades de nivel superior del tipo declarado.</span><span class="sxs-lookup"><span data-stu-id="60558-172">Additionally, these constructs handle inheritance (value substitutability), while the `select *` variants are restricted to top-level properties of the declared type.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="60558-173">no admite el agregado `count(*)`.</span><span class="sxs-lookup"><span data-stu-id="60558-173">does not support the `count(*)` aggregate.</span></span> <span data-ttu-id="60558-174">En su lugar, use `count(0)`.</span><span class="sxs-lookup"><span data-stu-id="60558-174">Use `count(0)` instead.</span></span>  
  
## <a name="changes-to-group-by"></a><span data-ttu-id="60558-175">Cambios de Group By</span><span class="sxs-lookup"><span data-stu-id="60558-175">Changes to Group By</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="60558-176">admite el uso de alias de las claves `group by`.</span><span class="sxs-lookup"><span data-stu-id="60558-176">supports aliasing of `group by` keys.</span></span> <span data-ttu-id="60558-177">Las expresiones de la cláusula `select` y de la cláusula `having` deben hacer referencia a las claves `group by` a través de estos alias.</span><span class="sxs-lookup"><span data-stu-id="60558-177">Expressions in the `select` clause and `having` clause must refer to the `group by` keys via these aliases.</span></span> <span data-ttu-id="60558-178">Por ejemplo, considere esta sintaxis de [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="60558-178">For example, this [!INCLUDE[esql](../../../../../../includes/esql-md.md)] syntax:</span></span>  
  
```sql  
SELECT k1, count(t.a), sum(t.a)
FROM T AS t
GROUP BY t.b + t.c AS k1
```  
  
 <span data-ttu-id="60558-179">... es equivalente al siguiente Transact-SQLTransact-SQL:</span><span class="sxs-lookup"><span data-stu-id="60558-179">...is equivalent to the following Transact-SQL:</span></span>  
  
```sql  
SELECT b + c, count(*), sum(a)
FROM T
GROUP BY b + c
```  
  
## <a name="collection-based-aggregates"></a><span data-ttu-id="60558-180">Agregados basados en colecciones</span><span class="sxs-lookup"><span data-stu-id="60558-180">Collection-Based Aggregates</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="60558-181">admite dos tipos de agregados.</span><span class="sxs-lookup"><span data-stu-id="60558-181">supports two kinds of aggregates.</span></span>  
  
 <span data-ttu-id="60558-182">Los agregados basados en colecciones operan en colecciones y generan el resultado agregado.</span><span class="sxs-lookup"><span data-stu-id="60558-182">Collection-based aggregates operate on collections and produce the aggregated result.</span></span> <span data-ttu-id="60558-183">Estos pueden aparecer en cualquier parte de la consulta y no requieren una cláusula `group by`.</span><span class="sxs-lookup"><span data-stu-id="60558-183">These can appear anywhere in the query, and do not require a `group by` clause.</span></span> <span data-ttu-id="60558-184">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="60558-184">For example:</span></span>  
  
```sql  
SELECT t.a AS a, count({1,2,3}) AS b FROM T AS t
```  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="60558-185">también admite agregados del estilo de SQL.</span><span class="sxs-lookup"><span data-stu-id="60558-185">also supports SQL-style aggregates.</span></span> <span data-ttu-id="60558-186">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="60558-186">For example:</span></span>  
  
```sql  
SELECT a, sum(t.b) FROM T AS t GROUP BY t.a AS a
```  
  
## <a name="order-by-clause-usage"></a><span data-ttu-id="60558-187">Uso de la cláusula ORDER BY</span><span class="sxs-lookup"><span data-stu-id="60558-187">ORDER BY Clause Usage</span></span>  
<span data-ttu-id="60558-188">Transact-SQLTransact-SQL permite `ORDER BY` especificar cláusulas solo `SELECT .. FROM .. WHERE` en el bloque superior.</span><span class="sxs-lookup"><span data-stu-id="60558-188">Transact-SQL allows `ORDER BY` clauses to be specified only in the topmost `SELECT .. FROM .. WHERE` block.</span></span> <span data-ttu-id="60558-189">En [!INCLUDE[esql](../../../../../../includes/esql-md.md)] usted puede `ORDER BY` usar una expresión anidada y se puede colocar en cualquier lugar de la consulta, pero el orden en una consulta anidada no se conserva.</span><span class="sxs-lookup"><span data-stu-id="60558-189">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] you can use a nested `ORDER BY` expression and it can be placed anywhere in the query, but ordering in a nested query is not preserved.</span></span>  
  
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
  
## <a name="identifiers"></a><span data-ttu-id="60558-190">Identificadores</span><span class="sxs-lookup"><span data-stu-id="60558-190">Identifiers</span></span>  
 <span data-ttu-id="60558-191">En Transact-SQLTransact-SQL, la comparación de identificadores se basa en la intercalación de la base de datos actual.</span><span class="sxs-lookup"><span data-stu-id="60558-191">In Transact-SQL, identifier comparison is based on the collation of the current database.</span></span> <span data-ttu-id="60558-192">En [!INCLUDE[esql](../../../../../../includes/esql-md.md)], los identificadores son siempre sin distinción entre mayúsculas y minúsculas, pero tienen en cuenta los acentos (es decir, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] distingue entre caracteres con y sin acento; por ejemplo, 'e' no es igual a 'é').</span><span class="sxs-lookup"><span data-stu-id="60558-192">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)], identifiers are always case insensitive and accent sensitive (that is, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] distinguishes between accented and unaccented characters; for example, 'a' is not equal to 'ấ').</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="60558-193">trata las versiones de letras que parecen iguales pero proceden de páginas de códigos diferentes como caracteres distintos.</span><span class="sxs-lookup"><span data-stu-id="60558-193">treats versions of letters that appear the same but are from different code pages as different characters.</span></span> <span data-ttu-id="60558-194">Para obtener más información, consulte Conjunto de [caracteres](input-character-set-entity-sql.md)de entrada .</span><span class="sxs-lookup"><span data-stu-id="60558-194">For more information, see [Input Character Set](input-character-set-entity-sql.md).</span></span>  
  
## <a name="transact-sql-functionality-not-available-in-entity-sql"></a><span data-ttu-id="60558-195">Funcionalidad de Transact-SQL no disponible en Entity SQL</span><span class="sxs-lookup"><span data-stu-id="60558-195">Transact-SQL Functionality Not Available in Entity SQL</span></span>  
 <span data-ttu-id="60558-196">La siguiente funcionalidad de Transact-SQLTransact-SQL no está disponible en [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60558-196">The following Transact-SQL functionality is not available in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
 <span data-ttu-id="60558-197">DML</span><span class="sxs-lookup"><span data-stu-id="60558-197">DML</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="60558-198">actualmente no proporciona compatibilidad con instrucciones DML (insertar, actualizar, eliminar).</span><span class="sxs-lookup"><span data-stu-id="60558-198">currently provides no support for DML statements (insert, update, delete).</span></span>  
  
 <span data-ttu-id="60558-199">DDL</span><span class="sxs-lookup"><span data-stu-id="60558-199">DDL</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="60558-200">no proporciona compatibilidad con DDL en la versión actual.</span><span class="sxs-lookup"><span data-stu-id="60558-200">provides no support for DDL in the current version.</span></span>  
  
 <span data-ttu-id="60558-201">Programación imperativa</span><span class="sxs-lookup"><span data-stu-id="60558-201">Imperative Programming</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="60558-202">no proporciona compatibilidad para la programación imperativa, a diferencia de Transact-SQLTransact-SQL.</span><span class="sxs-lookup"><span data-stu-id="60558-202">provides no support for imperative programming, unlike Transact-SQL.</span></span> <span data-ttu-id="60558-203">Utilice un lenguaje de programación en su lugar.</span><span class="sxs-lookup"><span data-stu-id="60558-203">Use a programming language instead.</span></span>  
  
 <span data-ttu-id="60558-204">Funciones de agrupamiento</span><span class="sxs-lookup"><span data-stu-id="60558-204">Grouping Functions</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="60558-205">no proporciona aún compatibilidad con las funciones de agrupamiento (por ejemplo, CUBE, ROLLUP y GROUPING_SET).</span><span class="sxs-lookup"><span data-stu-id="60558-205">does not yet provide support for grouping functions (for example, CUBE, ROLLUP, and GROUPING_SET).</span></span>  
  
 <span data-ttu-id="60558-206">Funciones analíticas</span><span class="sxs-lookup"><span data-stu-id="60558-206">Analytic Functions</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="60558-207">no proporciona aún compatibilidad con las funciones analíticas.</span><span class="sxs-lookup"><span data-stu-id="60558-207">does not (yet) provide support for analytic functions.</span></span>  
  
 <span data-ttu-id="60558-208">Funciones y operadores integrados</span><span class="sxs-lookup"><span data-stu-id="60558-208">Built-in Functions, Operators</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="60558-209">admite un subconjunto de funciones y operadores integrados de Transact-SQLTransact-SQL .</span><span class="sxs-lookup"><span data-stu-id="60558-209">supports a subset of Transact-SQL's built in functions and operators.</span></span> <span data-ttu-id="60558-210">Es probable que estos operadores y funciones sean admitidos por los principales proveedores de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="60558-210">These operators and functions are likely to be supported by the major store providers.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="60558-211">utiliza las funciones específicas del almacén declaradas en un manifiesto de proveedor.</span><span class="sxs-lookup"><span data-stu-id="60558-211">uses the store-specific functions declared in a provider manifest.</span></span> <span data-ttu-id="60558-212">Además, Entity Framework permite declarar funciones de almacén existentes [!INCLUDE[esql](../../../../../../includes/esql-md.md)] integradas y definidas por el usuario, para su uso.</span><span class="sxs-lookup"><span data-stu-id="60558-212">Additionally, the Entity Framework allows you to declare built-in and user-defined existing store functions, for [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to use.</span></span>  
  
 <span data-ttu-id="60558-213">Sugerencias</span><span class="sxs-lookup"><span data-stu-id="60558-213">Hints</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="60558-214">no proporciona mecanismos para sugerencias de consulta.</span><span class="sxs-lookup"><span data-stu-id="60558-214">does not provide mechanisms for query hints.</span></span>  
  
 <span data-ttu-id="60558-215">Resultados de un consulta por lotes</span><span class="sxs-lookup"><span data-stu-id="60558-215">Batching Query Results</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="60558-216">no admite resultados de una consulta por lotes.</span><span class="sxs-lookup"><span data-stu-id="60558-216">does not support batching query results.</span></span> <span data-ttu-id="60558-217">Por ejemplo, lo siguiente es Transact-SQLTransact-SQL válido (envío como lote):</span><span class="sxs-lookup"><span data-stu-id="60558-217">For example, the following is valid Transact-SQL (sending as a batch):</span></span>  
  
```sql  
SELECT * FROM products;
SELECT * FROM catagories;
```  
  
 <span data-ttu-id="60558-218">Sin embargo, no se admite el código [!INCLUDE[esql](../../../../../../includes/esql-md.md)] equivalente:</span><span class="sxs-lookup"><span data-stu-id="60558-218">However, the equivalent [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is not supported:</span></span>  
  
```sql  
SELECT value p FROM Products AS p;
SELECT value c FROM Categories AS c;
```  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="60558-219">admite únicamente una instrucción de consulta que genera un solo resultado por comando.</span><span class="sxs-lookup"><span data-stu-id="60558-219">only supports one result-producing query statement per command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60558-220">Consulte también</span><span class="sxs-lookup"><span data-stu-id="60558-220">See also</span></span>

- [<span data-ttu-id="60558-221">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="60558-221">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="60558-222">Expresiones no admitidas</span><span class="sxs-lookup"><span data-stu-id="60558-222">Unsupported Expressions</span></span>](unsupported-expressions-entity-sql.md)
