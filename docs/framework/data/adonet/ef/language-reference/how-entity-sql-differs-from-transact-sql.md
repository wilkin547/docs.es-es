---
title: Diferencias entre Entity SQL y Transact-SQL
ms.date: 03/30/2017
ms.assetid: 9c9ee36d-f294-4c8b-a196-f0114c94f559
ms.openlocfilehash: e809cea2f853eed51d28e55f81a411f7af2e5a33
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854474"
---
# <a name="how-entity-sql-differs-from-transact-sql"></a><span data-ttu-id="5b98d-102">Diferencias entre Entity SQL y Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5b98d-102">How Entity SQL Differs from Transact-SQL</span></span>
<span data-ttu-id="5b98d-103">En este tema se describen las [!INCLUDE[esql](../../../../../../includes/esql-md.md)] diferencias entre y Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="5b98d-103">This topic describes the differences between [!INCLUDE[esql](../../../../../../includes/esql-md.md)] and Transact-SQL.</span></span>  
  
## <a name="inheritance-and-relationships-support"></a><span data-ttu-id="5b98d-104">Compatibilidad con herencia y relaciones</span><span class="sxs-lookup"><span data-stu-id="5b98d-104">Inheritance and Relationships Support</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="5b98d-105">trabaja directamente con esquemas de entidades conceptuales y admite características del modelo conceptual como la herencia y las relaciones.</span><span class="sxs-lookup"><span data-stu-id="5b98d-105">works directly with conceptual entity schemas and supports conceptual model features such as inheritance and relationships.</span></span>  
  
 <span data-ttu-id="5b98d-106">Cuando se trabaja con la herencia, suele ser útil seleccionar instancias de un subtipo de una colección de instancias de supertipo.</span><span class="sxs-lookup"><span data-stu-id="5b98d-106">When working with inheritance, it is often useful to select instances of a subtype from a collection of supertype instances.</span></span> <span data-ttu-id="5b98d-107">El operador de [tipo](oftype-entity-sql.md) en [!INCLUDE[esql](../../../../../../includes/esql-md.md)] (similar a `oftype` en C# secuencias) proporciona esta capacidad.</span><span class="sxs-lookup"><span data-stu-id="5b98d-107">The [oftype](oftype-entity-sql.md) operator in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] (similar to `oftype` in C# Sequences) provides this capability.</span></span>  
  
## <a name="support-for-collections"></a><span data-ttu-id="5b98d-108">Compatibilidad con colecciones</span><span class="sxs-lookup"><span data-stu-id="5b98d-108">Support for Collections</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="5b98d-109">trata las colecciones como entidades de primera clase.</span><span class="sxs-lookup"><span data-stu-id="5b98d-109">treats collections as first-class entities.</span></span> <span data-ttu-id="5b98d-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5b98d-110">For example:</span></span>  
  
- <span data-ttu-id="5b98d-111">Las expresiones de colecciones son válidas en una cláusula `from`.</span><span class="sxs-lookup"><span data-stu-id="5b98d-111">Collection expressions are valid in a `from` clause.</span></span>  
  
- <span data-ttu-id="5b98d-112">Las subconsultas `in` y `exists` se han generalizado para permitir cualquier tipo de colección.</span><span class="sxs-lookup"><span data-stu-id="5b98d-112">`in` and `exists` subqueries have been generalized to allow any collections.</span></span>  
  
     <span data-ttu-id="5b98d-113">Una subconsulta es un tipo de colección.</span><span class="sxs-lookup"><span data-stu-id="5b98d-113">A subquery is one kind of collection.</span></span> <span data-ttu-id="5b98d-114">`e1 in e2` y `exists(e)` son las construcciones de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] que permiten realizar estas operaciones.</span><span class="sxs-lookup"><span data-stu-id="5b98d-114">`e1 in e2` and `exists(e)` are the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] constructs to perform these operations.</span></span>  
  
- <span data-ttu-id="5b98d-115">Las operaciones Set, como `union`, `intersect` y `except`, funcionan ahora en colecciones.</span><span class="sxs-lookup"><span data-stu-id="5b98d-115">Set operations, such as `union`, `intersect`, and `except`, now operate on collections.</span></span>  
  
- <span data-ttu-id="5b98d-116">Las combinaciones funcionan en colecciones.</span><span class="sxs-lookup"><span data-stu-id="5b98d-116">Joins operate on collections.</span></span>  
  
## <a name="support-for-expressions"></a><span data-ttu-id="5b98d-117">Compatibilidad con expresiones</span><span class="sxs-lookup"><span data-stu-id="5b98d-117">Support for Expressions</span></span>  
 <span data-ttu-id="5b98d-118">Transact-SQL tiene subconsultas (tablas) y expresiones (filas y columnas).</span><span class="sxs-lookup"><span data-stu-id="5b98d-118">Transact-SQL has subqueries (tables) and expressions (rows and columns).</span></span>  
  
 <span data-ttu-id="5b98d-119">Para admitir colecciones y colecciones anidadas, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] convierte todo en una expresión.</span><span class="sxs-lookup"><span data-stu-id="5b98d-119">To support collections and nested collections, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] makes everything an expression.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="5b98d-120">es más ajustable que Transact-SQL; todas las expresiones se pueden usar en cualquier lugar.</span><span class="sxs-lookup"><span data-stu-id="5b98d-120">is more composable than Transact-SQL—every expression can be used anywhere.</span></span> <span data-ttu-id="5b98d-121">Las expresiones de consulta siempre producen colecciones de los tipos proyectados y se pueden utilizar en cualquier parte donde se permita una expresión de colección.</span><span class="sxs-lookup"><span data-stu-id="5b98d-121">Query expressions always result in collections of the projected types and can be used anywhere a collection expression is allowed.</span></span> <span data-ttu-id="5b98d-122">Para obtener información sobre las expresiones de Transact-SQL que no [!INCLUDE[esql](../../../../../../includes/esql-md.md)]se admiten en, vea [expresiones no admitidas](unsupported-expressions-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="5b98d-122">For information about Transact-SQL expressions that are not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)], see [Unsupported Expressions](unsupported-expressions-entity-sql.md).</span></span>  
  
 <span data-ttu-id="5b98d-123">A continuación se muestran consultas válidas de [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="5b98d-123">The following are all valid [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries:</span></span>  
  
```  
1+2 *3  
"abc"  
row(1 as a, 2 as b)  
{ 1, 3, 5}   
e1 union all e2  
set(e1)  
```  
  
## <a name="uniform-treatment-of-subqueries"></a><span data-ttu-id="5b98d-124">Tratamiento uniforme de subconsultas</span><span class="sxs-lookup"><span data-stu-id="5b98d-124">Uniform Treatment of Subqueries</span></span>  
 <span data-ttu-id="5b98d-125">A partir de su énfasis en las tablas, Transact-SQL realiza la interpretación contextual de las subconsultas.</span><span class="sxs-lookup"><span data-stu-id="5b98d-125">Given its emphasis on tables, Transact-SQL performs contextual interpretation of subqueries.</span></span> <span data-ttu-id="5b98d-126">Por ejemplo, se considera que una subconsulta de la `from` cláusula es un conjunto múltiple (tabla).</span><span class="sxs-lookup"><span data-stu-id="5b98d-126">For example, a subquery in the `from` clause is considered to be a multiset (table).</span></span> <span data-ttu-id="5b98d-127">Pero la misma subconsulta utilizada en la cláusula `select` se considera una subconsulta escalar.</span><span class="sxs-lookup"><span data-stu-id="5b98d-127">But the same subquery used in the `select` clause is considered to be a scalar subquery.</span></span> <span data-ttu-id="5b98d-128">Del mismo modo, se considera que una subconsulta utilizada en `in` el lado izquierdo de un operador es una subconsulta escalar, mientras que se espera que el lado derecho sea una subconsulta MultiSet.</span><span class="sxs-lookup"><span data-stu-id="5b98d-128">Similarly, a subquery used on the left side of an `in` operator is considered to be a scalar subquery, while the right side is expected to be a multiset subquery.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="5b98d-129">elimina estas diferencias.</span><span class="sxs-lookup"><span data-stu-id="5b98d-129">eliminates these differences.</span></span> <span data-ttu-id="5b98d-130">Una expresión tiene una interpretación uniforme que no depende del contexto en el que se utiliza.</span><span class="sxs-lookup"><span data-stu-id="5b98d-130">An expression has a uniform interpretation that does not depend on the context in which it is used.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="5b98d-131">considera que todas las subconsultas son de conjunto múltiple.</span><span class="sxs-lookup"><span data-stu-id="5b98d-131">considers all subqueries to be multiset subqueries.</span></span> <span data-ttu-id="5b98d-132">Si se desea un valor escalar de la subconsulta [!INCLUDE[esql](../../../../../../includes/esql-md.md)] , proporciona `anyelement` el operador que opera en una colección (en este caso, la subconsulta) y extrae un valor singleton de la colección.</span><span class="sxs-lookup"><span data-stu-id="5b98d-132">If a scalar value is desired from the subquery, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] provides the `anyelement` operator that operates on a collection (in this case, the subquery), and extracts a singleton value from the collection.</span></span>  
  
### <a name="avoiding-implicit-coercions-for-subqueries"></a><span data-ttu-id="5b98d-133">Evitar conversiones implícitas en subconsultas</span><span class="sxs-lookup"><span data-stu-id="5b98d-133">Avoiding Implicit Coercions for Subqueries</span></span>  
 <span data-ttu-id="5b98d-134">Un efecto secundario relacionado del tratamiento uniforme de las subconsultas es la conversión implícita de las subconsultas en valores escalares.</span><span class="sxs-lookup"><span data-stu-id="5b98d-134">A related side effect of uniform treatment of subqueries is implicit conversion of subqueries to scalar values.</span></span> <span data-ttu-id="5b98d-135">En concreto, en Transact-SQL, un conjunto múltiple de filas (con un campo único) se convierte implícitamente en un valor escalar cuyo tipo de datos es el del campo.</span><span class="sxs-lookup"><span data-stu-id="5b98d-135">Specifically, in Transact-SQL, a multiset of rows (with a single field) is implicitly converted into a scalar value whose data type is that of the field.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="5b98d-136">no admite esta conversión implícita.</span><span class="sxs-lookup"><span data-stu-id="5b98d-136">does not support this implicit coercion.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="5b98d-137">proporciona el operador ANYELEMENT para extraer un valor singleton de una colección y una cláusula `select value` para evitar crear un contenedor de filas durante una expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="5b98d-137">provides the ANYELEMENT operator to extract a singleton value from a collection, and a `select value` clause to avoid creating a row-wrapper during a query expression.</span></span>  
  
## <a name="select-value-avoiding-the-implicit-row-wrapper"></a><span data-ttu-id="5b98d-138">Seleccionar valor: Evitar el contenedor de filas implícito</span><span class="sxs-lookup"><span data-stu-id="5b98d-138">Select Value: Avoiding the Implicit Row Wrapper</span></span>  
 <span data-ttu-id="5b98d-139">La cláusula SELECT de una subconsulta Transact-SQL crea implícitamente un contenedor de filas alrededor de los elementos de la cláusula.</span><span class="sxs-lookup"><span data-stu-id="5b98d-139">The select clause in a Transact-SQL subquery implicitly creates a row wrapper around the items in the clause.</span></span> <span data-ttu-id="5b98d-140">Esto implica que no podemos crear colecciones de valores escalares o de objetos.</span><span class="sxs-lookup"><span data-stu-id="5b98d-140">This implies that we cannot create collections of scalars or objects.</span></span> <span data-ttu-id="5b98d-141">Transact-SQL permite una conversión implícita entre un tipo de fila con un campo y un valor singleton del mismo tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="5b98d-141">Transact-SQL allows an implicit coercion between a rowtype with one field, and a singleton value of the same data type.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="5b98d-142">proporciona la cláusula `select value` para omitir la creación de filas implícitas.</span><span class="sxs-lookup"><span data-stu-id="5b98d-142">provides the `select value` clause to skip the implicit row construction.</span></span> <span data-ttu-id="5b98d-143">Solo se puede especificar un elemento en una cláusula `select value`.</span><span class="sxs-lookup"><span data-stu-id="5b98d-143">Only one item may be specified in a `select value` clause.</span></span> <span data-ttu-id="5b98d-144">Cuando se utiliza este tipo de cláusula, no se crea ningún contenedor de filas en torno a los elementos de la cláusula `select` y se puede generar una colección de la forma deseada, por ejemplo: `select value a`.</span><span class="sxs-lookup"><span data-stu-id="5b98d-144">When such a clause is used, no row wrapper is constructed around the items in the `select` clause, and a collection of the desired shape may be produced, for example: `select value a`.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="5b98d-145">también proporciona el constructor de filas para crear filas arbitrarias.</span><span class="sxs-lookup"><span data-stu-id="5b98d-145">also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="5b98d-146">La cláusula `select` toma uno o más elementos en la proyección y devuelve un registro de datos con campos, de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="5b98d-146">`select` takes one or more elements in the projection and results in a data record with fields, as follows:</span></span>  
  
 `select a, b, c`  
  
## <a name="left-correlation-and-aliasing"></a><span data-ttu-id="5b98d-147">Correlación izquierda y uso de alias</span><span class="sxs-lookup"><span data-stu-id="5b98d-147">Left Correlation and Aliasing</span></span>  
 <span data-ttu-id="5b98d-148">En Transact-SQL, las expresiones de un ámbito determinado (una sola cláusula `select` como `from`o) no pueden hacer referencia a expresiones definidas anteriormente en el mismo ámbito.</span><span class="sxs-lookup"><span data-stu-id="5b98d-148">In Transact-SQL, expressions in a given scope (a single clause like `select` or `from`) cannot reference expressions defined earlier in the same scope.</span></span> <span data-ttu-id="5b98d-149">Algunos dialectos de SQL (incluido Transact-SQL) admiten formas limitadas en la `from` cláusula.</span><span class="sxs-lookup"><span data-stu-id="5b98d-149">Some dialects of SQL (including Transact-SQL) do support limited forms of these in the `from` clause.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="5b98d-150">generaliza las correlaciones de la izquierda `from` en la cláusula y las trata de forma uniforme.</span><span class="sxs-lookup"><span data-stu-id="5b98d-150">generalizes left correlations in the `from` clause, and treats them uniformly.</span></span> <span data-ttu-id="5b98d-151">Las expresiones de la cláusula `from` pueden hacer referencia a definiciones anteriores (a la izquierda) en la misma cláusula sin necesidad de una sintaxis adicional.</span><span class="sxs-lookup"><span data-stu-id="5b98d-151">Expressions in the `from` clause can reference earlier definitions (definitions to the left) in the same clause without the need for additional syntax.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="5b98d-152">también impone restricciones adicionales en consultas que afectan a cláusulas `group by`.</span><span class="sxs-lookup"><span data-stu-id="5b98d-152">also imposes additional restrictions on queries involving `group by` clauses.</span></span> <span data-ttu-id="5b98d-153">Las expresiones de `select` la cláusula `having` y de estas consultas solo pueden hacer referencia a `group by` las claves a través de sus alias.</span><span class="sxs-lookup"><span data-stu-id="5b98d-153">Expressions in the `select` clause and `having` clause of such queries may only refer to the `group by` keys via their aliases.</span></span> <span data-ttu-id="5b98d-154">La siguiente construcción es válida en Transact-SQL, pero no en [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="5b98d-154">The following construct is valid in Transact-SQL but are not in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span></span>  
  
```  
select t.x + t.y from T as t group by t.x + t.y  
```  
  
 <span data-ttu-id="5b98d-155">Para hacer esto en [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="5b98d-155">To do this in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span></span>  
  
```  
select k from T as t group by (t.x + t.y) as k  
```  
  
## <a name="referencing-columns-properties-of-tables-collections"></a><span data-ttu-id="5b98d-156">Hacer referencia a columnas (propiedades) de tablas (colecciones)</span><span class="sxs-lookup"><span data-stu-id="5b98d-156">Referencing Columns (Properties) of Tables (Collections)</span></span>  
 <span data-ttu-id="5b98d-157">Todas las referencias de columna de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se deben calificar con el alias de la tabla.</span><span class="sxs-lookup"><span data-stu-id="5b98d-157">All column references in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] must be qualified with the table alias.</span></span> <span data-ttu-id="5b98d-158">La construcción siguiente (suponiendo que `a` es una columna válida de la `T`tabla) es válida en Transact-SQL, pero [!INCLUDE[esql](../../../../../../includes/esql-md.md)]no en.</span><span class="sxs-lookup"><span data-stu-id="5b98d-158">The following construct (assuming that `a` is a valid column of table `T`) is valid in Transact-SQL but not in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
```  
select a from T  
```  
  
 <span data-ttu-id="5b98d-159">El formato de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] es:</span><span class="sxs-lookup"><span data-stu-id="5b98d-159">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] form is</span></span>  
  
```  
select t.a as A from T as t  
```  
  
 <span data-ttu-id="5b98d-160">Los alias de tabla son opcionales en la cláusula `from`.</span><span class="sxs-lookup"><span data-stu-id="5b98d-160">The table aliases are optional in the `from` clause.</span></span> <span data-ttu-id="5b98d-161">El nombre de la tabla se utiliza como alias implícito.</span><span class="sxs-lookup"><span data-stu-id="5b98d-161">The name of the table is used as the implicit alias.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="5b98d-162">también permite el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="5b98d-162">allows the following form as well:</span></span>  
  
```  
select Tab.a from Tab  
```  
  
## <a name="navigation-through-objects"></a><span data-ttu-id="5b98d-163">Navegación a través de objetos</span><span class="sxs-lookup"><span data-stu-id="5b98d-163">Navigation Through Objects</span></span>  
 <span data-ttu-id="5b98d-164">Transact-SQL usa la notación "." para hacer referencia a las columnas de una tabla (una fila de).</span><span class="sxs-lookup"><span data-stu-id="5b98d-164">Transact-SQL uses the "." notation for referencing columns of (a row of) a table.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="5b98d-165">amplía esta notación (que toma prestada de los lenguajes de programación) para admitir la navegación a través de las propiedades de un objeto.</span><span class="sxs-lookup"><span data-stu-id="5b98d-165">extends this notation (borrowed from programming languages) to support navigation through properties of an object.</span></span>  
  
 <span data-ttu-id="5b98d-166">Por ejemplo, si `p` es una expresión de tipo Persona, lo siguiente es la sintaxis de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] para hacer referencia a la ciudad de la dirección de esta persona.</span><span class="sxs-lookup"><span data-stu-id="5b98d-166">For example, if `p` is an expression of type Person, the following is the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] syntax for referencing the city of the address of this person.</span></span>  
  
```  
p.Address.City   
```  
  
## <a name="no-support-for-"></a><span data-ttu-id="5b98d-167">No hay compatibilidad con \*</span><span class="sxs-lookup"><span data-stu-id="5b98d-167">No Support for \*</span></span>  
 <span data-ttu-id="5b98d-168">Transact-SQL admite la sintaxis de \* Unqualified como alias para toda la fila y la sintaxis calificada \* (t.\*) como un acceso directo para los campos de esa tabla.</span><span class="sxs-lookup"><span data-stu-id="5b98d-168">Transact-SQL supports the unqualified \* syntax as an alias for the entire row, and the qualified \* syntax (t.\*) as a shortcut for the fields of that table.</span></span> <span data-ttu-id="5b98d-169">Además, Transact-SQL permite un agregado Count (\*) especial, que incluye valores NULL.</span><span class="sxs-lookup"><span data-stu-id="5b98d-169">In addition, Transact-SQL allows for a special count(\*) aggregate, which includes nulls.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="5b98d-170">no admite la construcción \*.</span><span class="sxs-lookup"><span data-stu-id="5b98d-170">does not support the \* construct.</span></span> <span data-ttu-id="5b98d-171">Las consultas de Transact-SQL del `select * from T` formulario `select T1.* from T1, T2...` y se pueden expresar [!INCLUDE[esql](../../../../../../includes/esql-md.md)] en `select value t from T as t` como `select value t1 from T1 as t1, T2 as t2...`y, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="5b98d-171">Transact-SQL queries of the form `select * from T` and `select T1.* from T1, T2...` can be expressed in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] as `select value t from T as t` and `select value t1 from T1 as t1, T2 as t2...`, respectively.</span></span> <span data-ttu-id="5b98d-172">Además, estas construcciones administran la herencia (capacidad de sustitución de valores), mientras que las variantes de `select *` se restringen a las propiedades de nivel superior del tipo declarado.</span><span class="sxs-lookup"><span data-stu-id="5b98d-172">Additionally, these constructs handle inheritance (value substitutability), while the `select *` variants are restricted to top-level properties of the declared type.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="5b98d-173">no admite el agregado `count(*)`.</span><span class="sxs-lookup"><span data-stu-id="5b98d-173">does not support the `count(*)` aggregate.</span></span> <span data-ttu-id="5b98d-174">Utilice `count(0)` en su lugar.</span><span class="sxs-lookup"><span data-stu-id="5b98d-174">Use `count(0)` instead.</span></span>  
  
## <a name="changes-to-group-by"></a><span data-ttu-id="5b98d-175">Cambios de Group By</span><span class="sxs-lookup"><span data-stu-id="5b98d-175">Changes to Group By</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="5b98d-176">admite el uso de alias de las claves `group by`.</span><span class="sxs-lookup"><span data-stu-id="5b98d-176">supports aliasing of `group by` keys.</span></span> <span data-ttu-id="5b98d-177">Las expresiones de la cláusula `select` y de la cláusula `having` deben hacer referencia a las claves `group by` a través de estos alias.</span><span class="sxs-lookup"><span data-stu-id="5b98d-177">Expressions in the `select` clause and `having` clause must refer to the `group by` keys via these aliases.</span></span> <span data-ttu-id="5b98d-178">Por ejemplo, considere esta sintaxis de [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="5b98d-178">For example, this [!INCLUDE[esql](../../../../../../includes/esql-md.md)] syntax:</span></span>  
  
```  
select k1, count(t.a), sum(t.a)  
from T as t  
group by t.b + t.c as k1  
```  
  
 <span data-ttu-id="5b98d-179">... es equivalente a la siguiente instrucción Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="5b98d-179">...is equivalent to the following Transact-SQL:</span></span>  
  
```  
select b + c, count(*), sum(a)   
from T  
group by b + c  
```  
  
## <a name="collection-based-aggregates"></a><span data-ttu-id="5b98d-180">Agregados basados en colecciones</span><span class="sxs-lookup"><span data-stu-id="5b98d-180">Collection-Based Aggregates</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="5b98d-181">admite dos tipos de agregados.</span><span class="sxs-lookup"><span data-stu-id="5b98d-181">supports two kinds of aggregates.</span></span>  
  
 <span data-ttu-id="5b98d-182">Los agregados basados en colecciones operan en colecciones y generan el resultado agregado.</span><span class="sxs-lookup"><span data-stu-id="5b98d-182">Collection-based aggregates operate on collections and produce the aggregated result.</span></span> <span data-ttu-id="5b98d-183">Estos pueden aparecer en cualquier parte de la consulta y no requieren una cláusula `group by`.</span><span class="sxs-lookup"><span data-stu-id="5b98d-183">These can appear anywhere in the query, and do not require a `group by` clause.</span></span> <span data-ttu-id="5b98d-184">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5b98d-184">For example:</span></span>  
  
```  
select t.a as a, count({1,2,3}) as b from T as t     
```  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="5b98d-185">también admite agregados del estilo de SQL.</span><span class="sxs-lookup"><span data-stu-id="5b98d-185">also supports SQL-style aggregates.</span></span> <span data-ttu-id="5b98d-186">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5b98d-186">For example:</span></span>  
  
```  
select a, sum(t.b) from T as t group by t.a as a  
```  
  
## <a name="order-by-clause-usage"></a><span data-ttu-id="5b98d-187">Uso de la cláusula ORDER BY</span><span class="sxs-lookup"><span data-stu-id="5b98d-187">ORDER BY Clause Usage</span></span>  
 <span data-ttu-id="5b98d-188">Transact-SQL permite especificar cláusulas ORDER BY solo en el nivel superior SELECT.</span><span class="sxs-lookup"><span data-stu-id="5b98d-188">Transact-SQL allows ORDER BY clauses to be specified only in the topmost SELECT ..</span></span> <span data-ttu-id="5b98d-189">FROM .</span><span class="sxs-lookup"><span data-stu-id="5b98d-189">FROM ..</span></span> <span data-ttu-id="5b98d-190">WHERE de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="5b98d-190">WHERE block.</span></span> <span data-ttu-id="5b98d-191">En [!INCLUDE[esql](../../../../../../includes/esql-md.md)], puede utilizar una expresión ORDER BY anidada que se puede colocar en cualquier parte de la consulta, pero la ordenación en una consulta anidada no se conserva.</span><span class="sxs-lookup"><span data-stu-id="5b98d-191">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] you can use a nested ORDER BY expression and it can be placed anywhere in the query, but ordering in a nested query is not preserved.</span></span>  
  
```  
-- The following query will order the results by the last name  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName  
```  
  
```  
-- In the following query ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="identifiers"></a><span data-ttu-id="5b98d-192">Identificadores</span><span class="sxs-lookup"><span data-stu-id="5b98d-192">Identifiers</span></span>  
 <span data-ttu-id="5b98d-193">En Transact-SQL, la comparación de identificadores se basa en la intercalación de la base de datos actual.</span><span class="sxs-lookup"><span data-stu-id="5b98d-193">In Transact-SQL, identifier comparison is based on the collation of the current database.</span></span> <span data-ttu-id="5b98d-194">En [!INCLUDE[esql](../../../../../../includes/esql-md.md)], los identificadores son siempre sin distinción entre mayúsculas y minúsculas, pero tienen en cuenta los acentos (es decir, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] distingue entre caracteres con y sin acento; por ejemplo, 'e' no es igual a 'é').</span><span class="sxs-lookup"><span data-stu-id="5b98d-194">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)], identifiers are always case insensitive and accent sensitive (that is, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] distinguishes between accented and unaccented characters; for example, 'a' is not equal to 'ấ').</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="5b98d-195">trata las versiones de letras que parecen iguales pero proceden de páginas de códigos diferentes como caracteres distintos.</span><span class="sxs-lookup"><span data-stu-id="5b98d-195">treats versions of letters that appear the same but are from different code pages as different characters.</span></span> <span data-ttu-id="5b98d-196">Para obtener más información, vea [juego de caracteres de entrada](input-character-set-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="5b98d-196">For more information, see [Input Character Set](input-character-set-entity-sql.md).</span></span>  
  
## <a name="transact-sql-functionality-not-available-in-entity-sql"></a><span data-ttu-id="5b98d-197">Funcionalidad de Transact-SQL no disponible en Entity SQL</span><span class="sxs-lookup"><span data-stu-id="5b98d-197">Transact-SQL Functionality Not Available in Entity SQL</span></span>  
 <span data-ttu-id="5b98d-198">La siguiente funcionalidad de Transact-SQL no está disponible [!INCLUDE[esql](../../../../../../includes/esql-md.md)]en.</span><span class="sxs-lookup"><span data-stu-id="5b98d-198">The following Transact-SQL functionality is not available in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
 <span data-ttu-id="5b98d-199">DML</span><span class="sxs-lookup"><span data-stu-id="5b98d-199">DML</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="5b98d-200">Actualmente no proporciona compatibilidad con instrucciones DML (Insert, Update y Delete).</span><span class="sxs-lookup"><span data-stu-id="5b98d-200">currently provides no support for DML statements (insert, update, delete).</span></span>  
  
 <span data-ttu-id="5b98d-201">DDL</span><span class="sxs-lookup"><span data-stu-id="5b98d-201">DDL</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="5b98d-202">no proporciona compatibilidad con DDL en la versión actual.</span><span class="sxs-lookup"><span data-stu-id="5b98d-202">provides no support for DDL in the current version.</span></span>  
  
 <span data-ttu-id="5b98d-203">Programación imperativa</span><span class="sxs-lookup"><span data-stu-id="5b98d-203">Imperative Programming</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="5b98d-204">no proporciona compatibilidad con la programación imperativa, a diferencia de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="5b98d-204">provides no support for imperative programming, unlike Transact-SQL.</span></span> <span data-ttu-id="5b98d-205">Utilice un lenguaje de programación en su lugar.</span><span class="sxs-lookup"><span data-stu-id="5b98d-205">Use a programming language instead.</span></span>  
  
 <span data-ttu-id="5b98d-206">Funciones de agrupamiento</span><span class="sxs-lookup"><span data-stu-id="5b98d-206">Grouping Functions</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="5b98d-207">no proporciona aún compatibilidad con las funciones de agrupamiento (por ejemplo, CUBE, ROLLUP y GROUPING_SET).</span><span class="sxs-lookup"><span data-stu-id="5b98d-207">does not yet provide support for grouping functions (for example, CUBE, ROLLUP, and GROUPING_SET).</span></span>  
  
 <span data-ttu-id="5b98d-208">Funciones analíticas</span><span class="sxs-lookup"><span data-stu-id="5b98d-208">Analytic Functions</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="5b98d-209">no proporciona aún compatibilidad con las funciones analíticas.</span><span class="sxs-lookup"><span data-stu-id="5b98d-209">does not (yet) provide support for analytic functions.</span></span>  
  
 <span data-ttu-id="5b98d-210">Funciones y operadores integrados</span><span class="sxs-lookup"><span data-stu-id="5b98d-210">Built-in Functions, Operators</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="5b98d-211">admite un subconjunto de funciones y operadores integrados de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="5b98d-211">supports a subset of Transact-SQL's built in functions and operators.</span></span> <span data-ttu-id="5b98d-212">Es probable que estos operadores y funciones sean admitidos por los principales proveedores de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="5b98d-212">These operators and functions are likely to be supported by the major store providers.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="5b98d-213">utiliza las funciones específicas del almacén declaradas en un manifiesto del proveedor.</span><span class="sxs-lookup"><span data-stu-id="5b98d-213">uses the store-specific functions declared in a provider manifest.</span></span> <span data-ttu-id="5b98d-214">Además, el Entity Framework permite declarar funciones de almacenamiento existentes integradas y definidas por el usuario para [!INCLUDE[esql](../../../../../../includes/esql-md.md)] que las use.</span><span class="sxs-lookup"><span data-stu-id="5b98d-214">Additionally, the Entity Framework allows you to declare built-in and user-defined existing store functions, for [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to use.</span></span>  
  
 <span data-ttu-id="5b98d-215">Sugerencias</span><span class="sxs-lookup"><span data-stu-id="5b98d-215">Hints</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="5b98d-216">no proporciona mecanismos para sugerencias de consulta.</span><span class="sxs-lookup"><span data-stu-id="5b98d-216">does not provide mechanisms for query hints.</span></span>  
  
 <span data-ttu-id="5b98d-217">Resultados de un consulta por lotes</span><span class="sxs-lookup"><span data-stu-id="5b98d-217">Batching Query Results</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="5b98d-218">no admite resultados de una consulta por lotes.</span><span class="sxs-lookup"><span data-stu-id="5b98d-218">does not support batching query results.</span></span> <span data-ttu-id="5b98d-219">Por ejemplo, el siguiente código de Transact-SQL es válido (se envía como un lote):</span><span class="sxs-lookup"><span data-stu-id="5b98d-219">For example, the following is valid Transact-SQL (sending as a batch):</span></span>  
  
```  
select * from products;  
select * from catagories;  
```  
  
 <span data-ttu-id="5b98d-220">Sin embargo, no se admite el código [!INCLUDE[esql](../../../../../../includes/esql-md.md)] equivalente:</span><span class="sxs-lookup"><span data-stu-id="5b98d-220">However, the equivalent [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is not supported:</span></span>  
  
```  
Select value p from Products as p;  
Select value c from Categories as c;  
```  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="5b98d-221">admite únicamente una instrucción de consulta que genera un solo resultado por comando.</span><span class="sxs-lookup"><span data-stu-id="5b98d-221">only supports one result-producing query statement per command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b98d-222">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b98d-222">See also</span></span>

- [<span data-ttu-id="5b98d-223">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="5b98d-223">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="5b98d-224">Expresiones no admitidas</span><span class="sxs-lookup"><span data-stu-id="5b98d-224">Unsupported Expressions</span></span>](unsupported-expressions-entity-sql.md)
