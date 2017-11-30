---
title: Diferencias entre Entity SQL y Transact-SQL
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c9ee36d-f294-4c8b-a196-f0114c94f559
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 5d99b433cb499316872cfb09d9fca7f7da753bb5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-entity-sql-differs-from-transact-sql"></a><span data-ttu-id="67faa-102">Diferencias entre Entity SQL y Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="67faa-102">How Entity SQL Differs from Transact-SQL</span></span>
<span data-ttu-id="67faa-103">En este tema se describe las diferencias entre [!INCLUDE[esql](../../../../../../includes/esql-md.md)] y [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67faa-103">This topic describes the differences between [!INCLUDE[esql](../../../../../../includes/esql-md.md)] and [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].</span></span>  
  
## <a name="inheritance-and-relationships-support"></a><span data-ttu-id="67faa-104">Compatibilidad con herencia y relaciones</span><span class="sxs-lookup"><span data-stu-id="67faa-104">Inheritance and Relationships Support</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="67faa-105">trabaja directamente con esquemas de entidades conceptuales y admite características del modelo conceptual tales como herencia y relaciones.</span><span class="sxs-lookup"><span data-stu-id="67faa-105"> works directly with conceptual entity schemas and supports conceptual model features such as inheritance and relationships.</span></span>  
  
 <span data-ttu-id="67faa-106">Cuando se trabaja con la herencia, suele ser útil seleccionar instancias de un subtipo de una colección de instancias de supertipo.</span><span class="sxs-lookup"><span data-stu-id="67faa-106">When working with inheritance, it is often useful to select instances of a subtype from a collection of supertype instances.</span></span> <span data-ttu-id="67faa-107">El [oftype](../../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md) operador en [!INCLUDE[esql](../../../../../../includes/esql-md.md)] (similar a `oftype` en las secuencias de C#) proporciona esta capacidad.</span><span class="sxs-lookup"><span data-stu-id="67faa-107">The [oftype](../../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md) operator in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] (similar to `oftype` in C# Sequences) provides this capability.</span></span>  
  
## <a name="support-for-collections"></a><span data-ttu-id="67faa-108">Compatibilidad con colecciones</span><span class="sxs-lookup"><span data-stu-id="67faa-108">Support for Collections</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="67faa-109">trata las colecciones como entidades de primera clase.</span><span class="sxs-lookup"><span data-stu-id="67faa-109"> treats collections as first-class entities.</span></span> <span data-ttu-id="67faa-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="67faa-110">For example:</span></span>  
  
-   <span data-ttu-id="67faa-111">Las expresiones de colecciones son válidas en una cláusula `from`.</span><span class="sxs-lookup"><span data-stu-id="67faa-111">Collection expressions are valid in a `from` clause.</span></span>  
  
-   <span data-ttu-id="67faa-112">Las subconsultas `in` y `exists` se han generalizado para permitir cualquier tipo de colección.</span><span class="sxs-lookup"><span data-stu-id="67faa-112">`in` and `exists` subqueries have been generalized to allow any collections.</span></span>  
  
     <span data-ttu-id="67faa-113">Una subconsulta es un tipo de colección.</span><span class="sxs-lookup"><span data-stu-id="67faa-113">A subquery is one kind of collection.</span></span> <span data-ttu-id="67faa-114">`e1 in e2` y `exists(e)` son las construcciones de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] que permiten realizar estas operaciones.</span><span class="sxs-lookup"><span data-stu-id="67faa-114">`e1 in e2` and `exists(e)` are the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] constructs to perform these operations.</span></span>  
  
-   <span data-ttu-id="67faa-115">Las operaciones Set, como `union`, `intersect` y `except`, funcionan ahora en colecciones.</span><span class="sxs-lookup"><span data-stu-id="67faa-115">Set operations, such as `union`, `intersect`, and `except`, now operate on collections.</span></span>  
  
-   <span data-ttu-id="67faa-116">Las combinaciones funcionan en colecciones.</span><span class="sxs-lookup"><span data-stu-id="67faa-116">Joins operate on collections.</span></span>  
  
## <a name="support-for-expressions"></a><span data-ttu-id="67faa-117">Compatibilidad con expresiones</span><span class="sxs-lookup"><span data-stu-id="67faa-117">Support for Expressions</span></span>  
 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]<span data-ttu-id="67faa-118">tiene subconsultas (tablas) y expresiones (filas y columnas).</span><span class="sxs-lookup"><span data-stu-id="67faa-118"> has subqueries (tables) and expressions (rows and columns).</span></span>  
  
 <span data-ttu-id="67faa-119">Para admitir colecciones y colecciones anidadas, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] convierte todo en una expresión.</span><span class="sxs-lookup"><span data-stu-id="67faa-119">To support collections and nested collections, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] makes everything an expression.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="67faa-120"> es más ajustable que [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]: todas las expresiones se puede utilizar en cualquier parte.</span><span class="sxs-lookup"><span data-stu-id="67faa-120"> is more composable than [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]—every expression can be used anywhere.</span></span> <span data-ttu-id="67faa-121">Las expresiones de consulta siempre producen colecciones de los tipos proyectados y se pueden utilizar en cualquier parte donde se permita una expresión de colección.</span><span class="sxs-lookup"><span data-stu-id="67faa-121">Query expressions always result in collections of the projected types and can be used anywhere a collection expression is allowed.</span></span> <span data-ttu-id="67faa-122">Para obtener información acerca de [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] expresiones que no se admiten en [!INCLUDE[esql](../../../../../../includes/esql-md.md)], consulte [expresiones no admitidas](../../../../../../docs/framework/data/adonet/ef/language-reference/unsupported-expressions-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="67faa-122">For information about [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] expressions that are not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)], see [Unsupported Expressions](../../../../../../docs/framework/data/adonet/ef/language-reference/unsupported-expressions-entity-sql.md).</span></span>  
  
 <span data-ttu-id="67faa-123">A continuación se muestran consultas válidas de [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="67faa-123">The following are all valid [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries:</span></span>  
  
```  
1+2 *3  
"abc"  
row(1 as a, 2 as b)  
{ 1, 3, 5}   
e1 union all e2  
set(e1)  
```  
  
## <a name="uniform-treatment-of-subqueries"></a><span data-ttu-id="67faa-124">Tratamiento uniforme de subconsultas</span><span class="sxs-lookup"><span data-stu-id="67faa-124">Uniform Treatment of Subqueries</span></span>  
 <span data-ttu-id="67faa-125">Dada la importancia de las tablas, [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] realiza una interpretación contextual de las subconsultas.</span><span class="sxs-lookup"><span data-stu-id="67faa-125">Given its emphasis on tables, [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] performs contextual interpretation of subqueries.</span></span> <span data-ttu-id="67faa-126">Por ejemplo, una subconsulta en la `from` cláusula se considera un conjunto múltiple (tabla).</span><span class="sxs-lookup"><span data-stu-id="67faa-126">For example, a subquery in the `from` clause is considered to be a multiset (table).</span></span> <span data-ttu-id="67faa-127">Pero la misma subconsulta utilizada en la cláusula `select` se considera una subconsulta escalar.</span><span class="sxs-lookup"><span data-stu-id="67faa-127">But the same subquery used in the `select` clause is considered to be a scalar subquery.</span></span> <span data-ttu-id="67faa-128">De forma similar, una subconsulta utilizada en el lado izquierdo de una `in` operador se considera una subconsulta escalar, mientras se espera que el lado derecho sea una subconsulta de conjunto múltiple.</span><span class="sxs-lookup"><span data-stu-id="67faa-128">Similarly, a subquery used on the left side of an `in` operator is considered to be a scalar subquery, while the right side is expected to be a multiset subquery.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="67faa-129"> elimina estas diferencias.</span><span class="sxs-lookup"><span data-stu-id="67faa-129"> eliminates these differences.</span></span> <span data-ttu-id="67faa-130">Una expresión tiene una interpretación uniforme que no depende del contexto en el que se utiliza.</span><span class="sxs-lookup"><span data-stu-id="67faa-130">An expression has a uniform interpretation that does not depend on the context in which it is used.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="67faa-131">considera que todas las subconsultas son de conjunto múltiple.</span><span class="sxs-lookup"><span data-stu-id="67faa-131"> considers all subqueries to be multiset subqueries.</span></span> <span data-ttu-id="67faa-132">Si se desea un valor escalar de la subconsulta, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] proporciona el `anyelement` operador que opera en una colección (en este caso, la subconsulta) y extrae el valor singleton de la colección.</span><span class="sxs-lookup"><span data-stu-id="67faa-132">If a scalar value is desired from the subquery, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] provides the `anyelement` operator that operates on a collection (in this case, the subquery), and extracts a singleton value from the collection.</span></span>  
  
### <a name="avoiding-implicit-coercions-for-subqueries"></a><span data-ttu-id="67faa-133">Evitar conversiones implícitas en subconsultas</span><span class="sxs-lookup"><span data-stu-id="67faa-133">Avoiding Implicit Coercions for Subqueries</span></span>  
 <span data-ttu-id="67faa-134">Un efecto secundario relacionado del tratamiento uniforme de las subconsultas es la conversión implícita de las subconsultas en valores escalares.</span><span class="sxs-lookup"><span data-stu-id="67faa-134">A related side effect of uniform treatment of subqueries is implicit conversion of subqueries to scalar values.</span></span> <span data-ttu-id="67faa-135">En concreto, en [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], un conjunto múltiple de filas (con un campo único) se convierte implícitamente en un valor escalar cuyo tipo de datos es el del campo.</span><span class="sxs-lookup"><span data-stu-id="67faa-135">Specifically, in [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], a multiset of rows (with a single field) is implicitly converted into a scalar value whose data type is that of the field.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="67faa-136"> no admite esta conversión implícita.</span><span class="sxs-lookup"><span data-stu-id="67faa-136"> does not support this implicit coercion.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="67faa-137"> proporciona el operador ANYELEMENT para extraer un valor singleton de una colección y una cláusula `select value` para evitar crear un contenedor de filas durante una expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="67faa-137"> provides the ANYELEMENT operator to extract a singleton value from a collection, and a `select value` clause to avoid creating a row-wrapper during a query expression.</span></span>  
  
## <a name="select-value-avoiding-the-implicit-row-wrapper"></a><span data-ttu-id="67faa-138">Seleccionar el valor: evitar el contenedor de filas implícitas</span><span class="sxs-lookup"><span data-stu-id="67faa-138">Select Value: Avoiding the Implicit Row Wrapper</span></span>  
 <span data-ttu-id="67faa-139">La cláusula select en una [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] subconsulta crea implícitamente un contenedor de filas alrededor de los elementos en la cláusula.</span><span class="sxs-lookup"><span data-stu-id="67faa-139">The select clause in a [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] subquery implicitly creates a row wrapper around the items in the clause.</span></span> <span data-ttu-id="67faa-140">Esto implica que no podemos crear colecciones de valores escalares o de objetos.</span><span class="sxs-lookup"><span data-stu-id="67faa-140">This implies that we cannot create collections of scalars or objects.</span></span> [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]<span data-ttu-id="67faa-141">permite una conversión implícita entre un tipo de fila con un campo y un valor singleton del mismo tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="67faa-141"> allows an implicit coercion between a rowtype with one field, and a singleton value of the same data type.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="67faa-142"> proporciona la cláusula `select value` para omitir la creación de filas implícitas.</span><span class="sxs-lookup"><span data-stu-id="67faa-142"> provides the `select value` clause to skip the implicit row construction.</span></span> <span data-ttu-id="67faa-143">Solo se puede especificar un elemento en una cláusula `select value`.</span><span class="sxs-lookup"><span data-stu-id="67faa-143">Only one item may be specified in a `select value` clause.</span></span> <span data-ttu-id="67faa-144">Cuando se utiliza este tipo de cláusula, no se crea ningún contenedor de filas en torno a los elementos de la cláusula `select` y se puede generar una colección de la forma deseada, por ejemplo: `select value a`.</span><span class="sxs-lookup"><span data-stu-id="67faa-144">When such a clause is used, no row wrapper is constructed around the items in the `select` clause, and a collection of the desired shape may be produced, for example: `select value a`.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="67faa-145"> también proporciona el constructor de filas para crear filas arbitrarias.</span><span class="sxs-lookup"><span data-stu-id="67faa-145"> also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="67faa-146">La cláusula `select` toma uno o más elementos en la proyección y devuelve un registro de datos con campos, de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="67faa-146">`select` takes one or more elements in the projection and results in a data record with fields, as follows:</span></span>  
  
 `select a, b, c`  
  
## <a name="left-correlation-and-aliasing"></a><span data-ttu-id="67faa-147">Correlación izquierda y uso de alias</span><span class="sxs-lookup"><span data-stu-id="67faa-147">Left Correlation and Aliasing</span></span>  
 <span data-ttu-id="67faa-148">En [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], las expresiones de un ámbito determinado (una cláusula única como `select` o `from`) no pueden hacer referencia a expresiones definidas anteriormente en el mismo ámbito.</span><span class="sxs-lookup"><span data-stu-id="67faa-148">In [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], expressions in a given scope (a single clause like `select` or `from`) cannot reference expressions defined earlier in the same scope.</span></span> <span data-ttu-id="67faa-149">Algunos dialectos de SQL (incluido [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]) admiten formas limitadas de estas en la cláusula `from`.</span><span class="sxs-lookup"><span data-stu-id="67faa-149">Some dialects of SQL (including [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]) do support limited forms of these in the `from` clause.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="67faa-150">generaliza las correlaciones izquierdas de la `from` cláusula y las trata uniformemente.</span><span class="sxs-lookup"><span data-stu-id="67faa-150"> generalizes left correlations in the `from` clause, and treats them uniformly.</span></span> <span data-ttu-id="67faa-151">Las expresiones de la cláusula `from` pueden hacer referencia a definiciones anteriores (a la izquierda) en la misma cláusula sin necesidad de una sintaxis adicional.</span><span class="sxs-lookup"><span data-stu-id="67faa-151">Expressions in the `from` clause can reference earlier definitions (definitions to the left) in the same clause without the need for additional syntax.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="67faa-152"> también impone restricciones adicionales en consultas que afectan a cláusulas `group by`.</span><span class="sxs-lookup"><span data-stu-id="67faa-152"> also imposes additional restrictions on queries involving `group by` clauses.</span></span> <span data-ttu-id="67faa-153">Expresiones en el `select` cláusula y `having` cláusula de dichas consultas solo puede hacer referencia a la `group by` claves a través de sus alias.</span><span class="sxs-lookup"><span data-stu-id="67faa-153">Expressions in the `select` clause and `having` clause of such queries may only refer to the `group by` keys via their aliases.</span></span> <span data-ttu-id="67faa-154">La construcción siguiente es válida en [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] pero no están en [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="67faa-154">The following construct is valid in [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] but are not in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span></span>  
  
```  
select t.x + t.y from T as t group by t.x + t.y  
```  
  
 <span data-ttu-id="67faa-155">Para hacer esto en [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="67faa-155">To do this in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span></span>  
  
```  
select k from T as t group by (t.x + t.y) as k  
```  
  
## <a name="referencing-columns-properties-of-tables-collections"></a><span data-ttu-id="67faa-156">Hacer referencia a columnas (propiedades) de tablas (colecciones)</span><span class="sxs-lookup"><span data-stu-id="67faa-156">Referencing Columns (Properties) of Tables (Collections)</span></span>  
 <span data-ttu-id="67faa-157">Todas las referencias de columna de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se deben calificar con el alias de la tabla.</span><span class="sxs-lookup"><span data-stu-id="67faa-157">All column references in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] must be qualified with the table alias.</span></span> <span data-ttu-id="67faa-158">La construcción siguiente (suponiendo que `a` es una columna válida de la tabla `T`) es válido en [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] , pero no en [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67faa-158">The following construct (assuming that `a` is a valid column of table `T`) is valid in [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] but not in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
```  
select a from T  
```  
  
 <span data-ttu-id="67faa-159">El formato de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] es:</span><span class="sxs-lookup"><span data-stu-id="67faa-159">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] form is</span></span>  
  
```  
select t.a as A from T as t  
```  
  
 <span data-ttu-id="67faa-160">Los alias de tabla son opcionales en la cláusula `from`.</span><span class="sxs-lookup"><span data-stu-id="67faa-160">The table aliases are optional in the `from` clause.</span></span> <span data-ttu-id="67faa-161">El nombre de la tabla se utiliza como alias implícito.</span><span class="sxs-lookup"><span data-stu-id="67faa-161">The name of the table is used as the implicit alias.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="67faa-162"> también permite el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="67faa-162"> allows the following form as well:</span></span>  
  
```  
select Tab.a from Tab  
```  
  
## <a name="navigation-through-objects"></a><span data-ttu-id="67faa-163">Navegación a través de objetos</span><span class="sxs-lookup"><span data-stu-id="67faa-163">Navigation Through Objects</span></span>  
 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]<span data-ttu-id="67faa-164"> usa la notación "." para hacer referencia a las columnas de (una fila de) una tabla.</span><span class="sxs-lookup"><span data-stu-id="67faa-164"> uses the "." notation for referencing columns of (a row of) a table.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="67faa-165"> amplía esta notación (que toma prestada de los lenguajes de programación) para admitir la navegación a través de las propiedades de un objeto.</span><span class="sxs-lookup"><span data-stu-id="67faa-165"> extends this notation (borrowed from programming languages) to support navigation through properties of an object.</span></span>  
  
 <span data-ttu-id="67faa-166">Por ejemplo, si `p` es una expresión de tipo Persona, lo siguiente es la sintaxis de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] para hacer referencia a la ciudad de la dirección de esta persona.</span><span class="sxs-lookup"><span data-stu-id="67faa-166">For example, if `p` is an expression of type Person, the following is the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] syntax for referencing the city of the address of this person.</span></span>  
  
```  
p.Address.City   
```  
  
## <a name="no-support-for-"></a><span data-ttu-id="67faa-167">No hay compatibilidad con *</span><span class="sxs-lookup"><span data-stu-id="67faa-167">No Support for *</span></span>  
 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]<span data-ttu-id="67faa-168">admite la sin calificar * sintaxis como un alias para toda la fila y el acceso \* sintaxis (t.\*) como un acceso directo para los campos de esa tabla.</span><span class="sxs-lookup"><span data-stu-id="67faa-168"> supports the unqualified * syntax as an alias for the entire row, and the qualified \* syntax (t.\*) as a shortcut for the fields of that table.</span></span> <span data-ttu-id="67faa-169">Además, [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] permite un número especial (\*) agregado, que incluye valores NULL.</span><span class="sxs-lookup"><span data-stu-id="67faa-169">In addition, [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] allows for a special count(\*) aggregate, which includes nulls.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="67faa-170"> no admite la construcción *.</span><span class="sxs-lookup"><span data-stu-id="67faa-170"> does not support the * construct.</span></span> <span data-ttu-id="67faa-171">Las consultas [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] con el formato `select * from T` y `select T1.* from T1, T2...` se pueden expresar en [!INCLUDE[esql](../../../../../../includes/esql-md.md)] como `select value t from T as t` y `select value t1 from T1 as t1, T2 as t2...`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="67faa-171">[!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] queries of the form `select * from T` and `select T1.* from T1, T2...` can be expressed in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] as `select value t from T as t` and `select value t1 from T1 as t1, T2 as t2...`, respectively.</span></span> <span data-ttu-id="67faa-172">Además, estas construcciones administran la herencia (capacidad de sustitución de valores), mientras que las variantes de `select *` se restringen a las propiedades de nivel superior del tipo declarado.</span><span class="sxs-lookup"><span data-stu-id="67faa-172">Additionally, these constructs handle inheritance (value substitutability), while the `select *` variants are restricted to top-level properties of the declared type.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="67faa-173"> no admite el agregado `count(*)`.</span><span class="sxs-lookup"><span data-stu-id="67faa-173"> does not support the `count(*)` aggregate.</span></span> <span data-ttu-id="67faa-174">Utilice `count(0)` en su lugar.</span><span class="sxs-lookup"><span data-stu-id="67faa-174">Use `count(0)` instead.</span></span>  
  
## <a name="changes-to-group-by"></a><span data-ttu-id="67faa-175">Cambios de Group By</span><span class="sxs-lookup"><span data-stu-id="67faa-175">Changes to Group By</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="67faa-176"> admite el uso de alias de las claves `group by`.</span><span class="sxs-lookup"><span data-stu-id="67faa-176"> supports aliasing of `group by` keys.</span></span> <span data-ttu-id="67faa-177">Las expresiones de la cláusula `select` y de la cláusula `having` deben hacer referencia a las claves `group by` a través de estos alias.</span><span class="sxs-lookup"><span data-stu-id="67faa-177">Expressions in the `select` clause and `having` clause must refer to the `group by` keys via these aliases.</span></span> <span data-ttu-id="67faa-178">Por ejemplo, considere esta sintaxis de [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="67faa-178">For example, this [!INCLUDE[esql](../../../../../../includes/esql-md.md)] syntax:</span></span>  
  
```  
select k1, count(t.a), sum(t.a)  
from T as t  
group by t.b + t.c as k1  
```  
  
 <span data-ttu-id="67faa-179">...es equivalente al código siguiente de [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="67faa-179">...is equivalent to the following [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]:</span></span>  
  
```  
select b + c, count(*), sum(a)   
from T  
group by b + c  
```  
  
## <a name="collection-based-aggregates"></a><span data-ttu-id="67faa-180">Agregados basados en colecciones</span><span class="sxs-lookup"><span data-stu-id="67faa-180">Collection-Based Aggregates</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="67faa-181"> admite dos tipos de agregados.</span><span class="sxs-lookup"><span data-stu-id="67faa-181"> supports two kinds of aggregates.</span></span>  
  
 <span data-ttu-id="67faa-182">Los agregados basados en colecciones operan en colecciones y generan el resultado agregado.</span><span class="sxs-lookup"><span data-stu-id="67faa-182">Collection-based aggregates operate on collections and produce the aggregated result.</span></span> <span data-ttu-id="67faa-183">Estos pueden aparecer en cualquier parte de la consulta y no requieren una cláusula `group by`.</span><span class="sxs-lookup"><span data-stu-id="67faa-183">These can appear anywhere in the query, and do not require a `group by` clause.</span></span> <span data-ttu-id="67faa-184">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="67faa-184">For example:</span></span>  
  
```  
select t.a as a, count({1,2,3}) as b from T as t     
```  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="67faa-185"> también admite agregados del estilo de SQL.</span><span class="sxs-lookup"><span data-stu-id="67faa-185"> also supports SQL-style aggregates.</span></span> <span data-ttu-id="67faa-186">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="67faa-186">For example:</span></span>  
  
```  
select a, sum(t.b) from T as t group by t.a as a  
```  
  
## <a name="order-by-clause-usage"></a><span data-ttu-id="67faa-187">Uso de la cláusula ORDER BY</span><span class="sxs-lookup"><span data-stu-id="67faa-187">ORDER BY Clause Usage</span></span>  
 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]<span data-ttu-id="67faa-188"> permite especificar cláusulas ORDER BY solo en el bloque SELECT ..</span><span class="sxs-lookup"><span data-stu-id="67faa-188"> allows ORDER BY clauses to be specified only in the topmost SELECT ..</span></span> <span data-ttu-id="67faa-189">FROM ..</span><span class="sxs-lookup"><span data-stu-id="67faa-189">FROM ..</span></span> <span data-ttu-id="67faa-190">WHERE de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="67faa-190">WHERE block.</span></span> <span data-ttu-id="67faa-191">En [!INCLUDE[esql](../../../../../../includes/esql-md.md)], puede utilizar una expresión ORDER BY anidada que se puede colocar en cualquier parte de la consulta, pero la ordenación en una consulta anidada no se conserva.</span><span class="sxs-lookup"><span data-stu-id="67faa-191">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] you can use a nested ORDER BY expression and it can be placed anywhere in the query, but ordering in a nested query is not preserved.</span></span>  
  
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
  
## <a name="identifiers"></a><span data-ttu-id="67faa-192">Identificadores</span><span class="sxs-lookup"><span data-stu-id="67faa-192">Identifiers</span></span>  
 <span data-ttu-id="67faa-193">En [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], la comparación del identificador está basada en la intercalación de la base de datos actual.</span><span class="sxs-lookup"><span data-stu-id="67faa-193">In [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], identifier comparison is based on the collation of the current database.</span></span> <span data-ttu-id="67faa-194">En [!INCLUDE[esql](../../../../../../includes/esql-md.md)], los identificadores son siempre sin distinción entre mayúsculas y minúsculas, pero tienen en cuenta los acentos (es decir, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] distingue entre caracteres con y sin acento; por ejemplo, 'e' no es igual a 'é').</span><span class="sxs-lookup"><span data-stu-id="67faa-194">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)], identifiers are always case insensitive and accent sensitive (that is, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] distinguishes between accented and unaccented characters; for example, 'a' is not equal to 'ấ').</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="67faa-195"> trata las versiones de letras que parecen iguales pero proceden de páginas de códigos diferentes como caracteres distintos.</span><span class="sxs-lookup"><span data-stu-id="67faa-195"> treats versions of letters that appear the same but are from different code pages as different characters.</span></span> <span data-ttu-id="67faa-196">Para obtener más información, consulte [juego de caracteres de entrada](../../../../../../docs/framework/data/adonet/ef/language-reference/input-character-set-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="67faa-196">For more information, see [Input Character Set](../../../../../../docs/framework/data/adonet/ef/language-reference/input-character-set-entity-sql.md).</span></span>  
  
## <a name="transact-sql-functionality-not-available-in-entity-sql"></a><span data-ttu-id="67faa-197">Funcionalidad de Transact-SQL no disponible en Entity SQL</span><span class="sxs-lookup"><span data-stu-id="67faa-197">Transact-SQL Functionality Not Available in Entity SQL</span></span>  
 <span data-ttu-id="67faa-198">La funcionalidad de [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] siguiente no está disponible en [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67faa-198">The following [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] functionality is not available in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
 <span data-ttu-id="67faa-199">DML</span><span class="sxs-lookup"><span data-stu-id="67faa-199">DML</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="67faa-200">actualmente no proporciona compatibilidad con las instrucciones DML (Insertar, actualizar y eliminar).</span><span class="sxs-lookup"><span data-stu-id="67faa-200"> currently provides no support for DML statements (insert, update, delete).</span></span>  
  
 <span data-ttu-id="67faa-201">DDL</span><span class="sxs-lookup"><span data-stu-id="67faa-201">DDL</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="67faa-202"> no proporciona compatibilidad con DDL en la versión actual.</span><span class="sxs-lookup"><span data-stu-id="67faa-202"> provides no support for DDL in the current version.</span></span>  
  
 <span data-ttu-id="67faa-203">Programación imperativa</span><span class="sxs-lookup"><span data-stu-id="67faa-203">Imperative Programming</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="67faa-204"> no proporciona compatibilidad con la programación imperativa, a diferencia de [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67faa-204"> provides no support for imperative programming, unlike [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="67faa-205">Utilice un lenguaje de programación en su lugar.</span><span class="sxs-lookup"><span data-stu-id="67faa-205">Use a programming language instead.</span></span>  
  
 <span data-ttu-id="67faa-206">Funciones de agrupamiento</span><span class="sxs-lookup"><span data-stu-id="67faa-206">Grouping Functions</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="67faa-207"> no proporciona aún compatibilidad con las funciones de agrupamiento (por ejemplo, CUBE, ROLLUP y GROUPING_SET).</span><span class="sxs-lookup"><span data-stu-id="67faa-207"> does not yet provide support for grouping functions (for example, CUBE, ROLLUP, and GROUPING_SET).</span></span>  
  
 <span data-ttu-id="67faa-208">Funciones analíticas</span><span class="sxs-lookup"><span data-stu-id="67faa-208">Analytic Functions</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="67faa-209"> no proporciona aún compatibilidad con las funciones analíticas.</span><span class="sxs-lookup"><span data-stu-id="67faa-209"> does not (yet) provide support for analytic functions.</span></span>  
  
 <span data-ttu-id="67faa-210">Funciones y operadores integrados</span><span class="sxs-lookup"><span data-stu-id="67faa-210">Built-in Functions, Operators</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="67faa-211">admite un subconjunto de [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]funciones y operadores integrados.</span><span class="sxs-lookup"><span data-stu-id="67faa-211"> supports a subset of [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]'s built in functions and operators.</span></span> <span data-ttu-id="67faa-212">Es probable que estos operadores y funciones sean admitidos por los principales proveedores de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="67faa-212">These operators and functions are likely to be supported by the major store providers.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="67faa-213">usa las funciones específicas del almacén declaradas en un manifiesto del proveedor.</span><span class="sxs-lookup"><span data-stu-id="67faa-213"> uses the store-specific functions declared in a provider manifest.</span></span> <span data-ttu-id="67faa-214">Además, el [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] permite declarar integrados y definidos por el usuario funciones de almacenamiento existentes, para [!INCLUDE[esql](../../../../../../includes/esql-md.md)] a usar.</span><span class="sxs-lookup"><span data-stu-id="67faa-214">Additionally, the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] allows you to declare built-in and user-defined existing store functions, for [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to use.</span></span>  
  
 <span data-ttu-id="67faa-215">Sugerencias</span><span class="sxs-lookup"><span data-stu-id="67faa-215">Hints</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="67faa-216"> no proporciona mecanismos para sugerencias de consulta.</span><span class="sxs-lookup"><span data-stu-id="67faa-216"> does not provide mechanisms for query hints.</span></span>  
  
 <span data-ttu-id="67faa-217">Resultados de un consulta por lotes</span><span class="sxs-lookup"><span data-stu-id="67faa-217">Batching Query Results</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="67faa-218"> no admite resultados de una consulta por lotes.</span><span class="sxs-lookup"><span data-stu-id="67faa-218"> does not support batching query results.</span></span> <span data-ttu-id="67faa-219">Por ejemplo, la siguiente es válida [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] (que se envía como un lote):</span><span class="sxs-lookup"><span data-stu-id="67faa-219">For example, the following is valid [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] (sending as a batch):</span></span>  
  
```  
select * from products;  
select * from catagories;  
```  
  
 <span data-ttu-id="67faa-220">Sin embargo, no se admite el código [!INCLUDE[esql](../../../../../../includes/esql-md.md)] equivalente:</span><span class="sxs-lookup"><span data-stu-id="67faa-220">However, the equivalent [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is not supported:</span></span>  
  
```  
Select value p from Products as p;  
Select value c from Categories as c;  
```  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="67faa-221"> admite únicamente una instrucción de consulta que genera un solo resultado por comando.</span><span class="sxs-lookup"><span data-stu-id="67faa-221"> only supports one result-producing query statement per command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67faa-222">Vea también</span><span class="sxs-lookup"><span data-stu-id="67faa-222">See Also</span></span>  
 [<span data-ttu-id="67faa-223">Información general sobre de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="67faa-223">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [<span data-ttu-id="67faa-224">Expresiones no admitidas</span><span class="sxs-lookup"><span data-stu-id="67faa-224">Unsupported Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/unsupported-expressions-entity-sql.md)
