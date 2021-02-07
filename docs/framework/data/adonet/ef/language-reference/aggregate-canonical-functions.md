---
description: 'Más información sobre: funciones canónicas de agregado'
title: Funciones canónicas de agregado
ms.date: 03/30/2017
ms.assetid: 3bcff826-ca90-41b3-a791-04d6ff0e5085
ms.openlocfilehash: e26888ac15553a592f7d2cb9b1a0941161115615
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697301"
---
# <a name="aggregate-canonical-functions"></a><span data-ttu-id="37884-103">Funciones canónicas de agregado</span><span class="sxs-lookup"><span data-stu-id="37884-103">Aggregate Canonical Functions</span></span>

<span data-ttu-id="37884-104">Los agregados son expresiones que reducen una serie de valores de entrada a un único valor, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="37884-104">Aggregates are expressions that reduce a series of input values into, for example, a single value.</span></span> <span data-ttu-id="37884-105">Los agregados suelen usarse junto con la cláusula GROUP BY de la expresión SELECT y hay restricciones con respecto a dónde se pueden usar.</span><span class="sxs-lookup"><span data-stu-id="37884-105">Aggregates are normally used in conjunction with the GROUP BY clause of the SELECT expression, and there are constraints on where they can be used.</span></span>

## <a name="aggregate-entity-sql-canonical-functions"></a><span data-ttu-id="37884-106">Funciones canónicas de agregado Entity SQL</span><span class="sxs-lookup"><span data-stu-id="37884-106">Aggregate Entity SQL canonical functions</span></span>

<span data-ttu-id="37884-107">A continuación se muestran las funciones canónicas Entity SQL agregadas.</span><span class="sxs-lookup"><span data-stu-id="37884-107">The following are the aggregate Entity SQL canonical functions.</span></span>

### <a name="avgexpression"></a><span data-ttu-id="37884-108">Avg(expresión)</span><span class="sxs-lookup"><span data-stu-id="37884-108">Avg(expression)</span></span>

<span data-ttu-id="37884-109">Devuelve el promedio de los valores no NULL.</span><span class="sxs-lookup"><span data-stu-id="37884-109">Returns the average of the non-null values.</span></span>

<span data-ttu-id="37884-110">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="37884-110">**Arguments**</span></span>

<span data-ttu-id="37884-111">`Int32`,, `Int64` `Double` Y `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="37884-111">An `Int32`, `Int64`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="37884-112">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="37884-112">**Return Value**</span></span>

<span data-ttu-id="37884-113">El tipo de `expression` , o `null` si todos los valores de entrada son `null` valores.</span><span class="sxs-lookup"><span data-stu-id="37884-113">The type of `expression`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="37884-114">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="37884-114">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_AVG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_avg)]
[!code-sql[DP EntityServices Concepts#EDM_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_avg)]

### <a name="bigcountexpression"></a><span data-ttu-id="37884-115">BigCount(expresión)</span><span class="sxs-lookup"><span data-stu-id="37884-115">BigCount(expression)</span></span>

<span data-ttu-id="37884-116">Devuelve el tamaño del agregado, incluyendo los valores NULL y los duplicados.</span><span class="sxs-lookup"><span data-stu-id="37884-116">Returns the size of the aggregate including null and duplicate values.</span></span>

<span data-ttu-id="37884-117">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="37884-117">**Arguments**</span></span>

<span data-ttu-id="37884-118">Cualquier tipo.</span><span class="sxs-lookup"><span data-stu-id="37884-118">Any type.</span></span>

<span data-ttu-id="37884-119">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="37884-119">**Return Value**</span></span>

<span data-ttu-id="37884-120">Una clase `Int64`.</span><span class="sxs-lookup"><span data-stu-id="37884-120">An `Int64`.</span></span>

<span data-ttu-id="37884-121">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="37884-121">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_BIGCOUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_bigcount)]
[!code-sql[DP EntityServices Concepts#EDM_BIGCOUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_bigcount)]

### <a name="countexpression"></a><span data-ttu-id="37884-122">Count(expresión)</span><span class="sxs-lookup"><span data-stu-id="37884-122">Count(expression)</span></span>

<span data-ttu-id="37884-123">Devuelve el tamaño del agregado, incluyendo los valores NULL y los duplicados.</span><span class="sxs-lookup"><span data-stu-id="37884-123">Returns the size of the aggregate including null and duplicate values.</span></span>

<span data-ttu-id="37884-124">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="37884-124">**Arguments**</span></span>

<span data-ttu-id="37884-125">Cualquier tipo.</span><span class="sxs-lookup"><span data-stu-id="37884-125">Any type.</span></span>

<span data-ttu-id="37884-126">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="37884-126">**Return Value**</span></span>

<span data-ttu-id="37884-127">Una clase `Int32`.</span><span class="sxs-lookup"><span data-stu-id="37884-127">An `Int32`.</span></span>

<span data-ttu-id="37884-128">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="37884-128">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_COUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_count)]
[!code-sql[DP EntityServices Concepts#EDM_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_count)]

### <a name="maxexpression"></a><span data-ttu-id="37884-129">Max(expresión)</span><span class="sxs-lookup"><span data-stu-id="37884-129">Max(expression)</span></span>

<span data-ttu-id="37884-130">Devuelve el máximo de los valores no NULL.</span><span class="sxs-lookup"><span data-stu-id="37884-130">Returns the maximum of the non-null values.</span></span>

<span data-ttu-id="37884-131">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="37884-131">**Arguments**</span></span>

<span data-ttu-id="37884-132">Valor de tipo `Byte``Int16``Int32``Int64``Byte``Single``Double``Decimal``DateTime``DateTimeOffset``Time``String`.</span><span class="sxs-lookup"><span data-stu-id="37884-132">A `Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary`.</span></span>

<span data-ttu-id="37884-133">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="37884-133">**Return Value**</span></span>

<span data-ttu-id="37884-134">El tipo de `expression` , o `null` si todos los valores de entrada son `null` valores.</span><span class="sxs-lookup"><span data-stu-id="37884-134">The type of `expression`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="37884-135">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="37884-135">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_MAX](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_max)]
[!code-sql[DP EntityServices Concepts#EDM_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_max)]

### <a name="minexpression"></a><span data-ttu-id="37884-136">Min(expresión)</span><span class="sxs-lookup"><span data-stu-id="37884-136">Min(expression)</span></span>

<span data-ttu-id="37884-137">Devuelve el mínimo de los valores no NULL.</span><span class="sxs-lookup"><span data-stu-id="37884-137">Returns the minimum of the non-null values.</span></span>

<span data-ttu-id="37884-138">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="37884-138">**Arguments**</span></span>

<span data-ttu-id="37884-139">Valor de tipo `Byte``Int16``Int32``Int64``Byte``Single``Double``Decimal``DateTime``DateTimeOffset``Time``String`.</span><span class="sxs-lookup"><span data-stu-id="37884-139">A `Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary`.</span></span>

<span data-ttu-id="37884-140">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="37884-140">**Return Value**</span></span>

<span data-ttu-id="37884-141">El tipo de `expression` , o `null` si todos los valores de entrada son `null` valores.</span><span class="sxs-lookup"><span data-stu-id="37884-141">The type of `expression`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="37884-142">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="37884-142">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_MIN](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_min)]
[!code-sql[DP EntityServices Concepts#EDM_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_min)]

### <a name="stdevexpression"></a><span data-ttu-id="37884-143">StDev(expresión)</span><span class="sxs-lookup"><span data-stu-id="37884-143">StDev(expression)</span></span>

<span data-ttu-id="37884-144">Devuelve la desviación estándar de los valores no NULL.</span><span class="sxs-lookup"><span data-stu-id="37884-144">Returns the standard deviation of the non-null values.</span></span>

<span data-ttu-id="37884-145">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="37884-145">**Arguments**</span></span>

<span data-ttu-id="37884-146">Valor de tipo `Int32`, `Int64`, `Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="37884-146">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="37884-147">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="37884-147">**Return Value**</span></span>

<span data-ttu-id="37884-148">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="37884-148">A `Double`.</span></span> <span data-ttu-id="37884-149">`Null` si los valores de entrada son `null`.</span><span class="sxs-lookup"><span data-stu-id="37884-149">`Null`, if all input values are `null` values.</span></span>

<span data-ttu-id="37884-150">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="37884-150">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_STDEV](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_stdev)]
[!code-sql[DP EntityServices Concepts#EDM_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_stdev)]

### <a name="stdevpexpression"></a><span data-ttu-id="37884-151">StDevP(expresión)</span><span class="sxs-lookup"><span data-stu-id="37884-151">StDevP(expression)</span></span>

<span data-ttu-id="37884-152">Devuelve la desviación estándar de la población para todos los valores.</span><span class="sxs-lookup"><span data-stu-id="37884-152">Returns the standard deviation for the population of all values.</span></span>

<span data-ttu-id="37884-153">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="37884-153">**Arguments**</span></span>

<span data-ttu-id="37884-154">Valor de tipo `Int32`, `Int64`, `Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="37884-154">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="37884-155">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="37884-155">**Return Value**</span></span>

<span data-ttu-id="37884-156">`Double`O `null` si todos los valores de entrada son `null` valores.</span><span class="sxs-lookup"><span data-stu-id="37884-156">A `Double`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="37884-157">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="37884-157">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_STDEVP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_stdevp)]
[!code-sql[DP EntityServices Concepts#EDM_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_stdevp)]

### <a name="sumexpression"></a><span data-ttu-id="37884-158">Sum(expresión)</span><span class="sxs-lookup"><span data-stu-id="37884-158">Sum(expression)</span></span>

<span data-ttu-id="37884-159">Devuelve la suma de los valores no NULL.</span><span class="sxs-lookup"><span data-stu-id="37884-159">Returns the sum of the non-null values.</span></span>

<span data-ttu-id="37884-160">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="37884-160">**Arguments**</span></span>

<span data-ttu-id="37884-161">Valor de tipo `Int32`, `Int64`, `Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="37884-161">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="37884-162">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="37884-162">**Return Value**</span></span>

<span data-ttu-id="37884-163">`Double`O `null` si todos los valores de entrada son `null` valores.</span><span class="sxs-lookup"><span data-stu-id="37884-163">A `Double`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="37884-164">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="37884-164">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_SUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_sum)]
[!code-sql[DP EntityServices Concepts#EDM_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_sum)]

### <a name="varexpression"></a><span data-ttu-id="37884-165">Var(expresión)</span><span class="sxs-lookup"><span data-stu-id="37884-165">Var(expression)</span></span>

<span data-ttu-id="37884-166">Devuelve la varianza de todos los valores no nulos.</span><span class="sxs-lookup"><span data-stu-id="37884-166">Returns the variance of all non-null values.</span></span>

<span data-ttu-id="37884-167">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="37884-167">**Arguments**</span></span>

<span data-ttu-id="37884-168">Valor de tipo `Int32`, `Int64`, `Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="37884-168">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="37884-169">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="37884-169">**Return Value**</span></span>

<span data-ttu-id="37884-170">`Double`O `null` si todos los valores de entrada son `null` valores.</span><span class="sxs-lookup"><span data-stu-id="37884-170">A `Double`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="37884-171">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="37884-171">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_VAR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_var)]
[!code-sql[DP EntityServices Concepts#EDM_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_var)]

### <a name="varpexpression"></a><span data-ttu-id="37884-172">VarP(expresión)</span><span class="sxs-lookup"><span data-stu-id="37884-172">VarP(expression)</span></span>

<span data-ttu-id="37884-173">Devuelve la varianza de la población para todos los valores no nulos.</span><span class="sxs-lookup"><span data-stu-id="37884-173">Returns the variance for the population of all non-null values.</span></span>

<span data-ttu-id="37884-174">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="37884-174">**Arguments**</span></span>

<span data-ttu-id="37884-175">Valor de tipo `Int32`, `Int64`, `Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="37884-175">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="37884-176">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="37884-176">**Return Value**</span></span>

<span data-ttu-id="37884-177">`Double`O `null` si todos los valores de entrada son `null` valores.</span><span class="sxs-lookup"><span data-stu-id="37884-177">A `Double`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="37884-178">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="37884-178">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_VARP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_varp)]
[!code-sql[DP EntityServices Concepts#EDM_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_varp)]

<span data-ttu-id="37884-179">La funcionalidad equivalente está disponible en el proveedor administrado de Microsoft SQL Client.</span><span class="sxs-lookup"><span data-stu-id="37884-179">Equivalent functionality is available in the Microsoft SQL Client Managed Provider.</span></span> <span data-ttu-id="37884-180">Para obtener más información, vea [SqlClient para funciones de Entity Framework](../sqlclient-for-ef-functions.md).</span><span class="sxs-lookup"><span data-stu-id="37884-180">For more information, see [SqlClient for Entity Framework Functions](../sqlclient-for-ef-functions.md).</span></span>

## <a name="collection-based-aggregates"></a><span data-ttu-id="37884-181">Agregados basados en una colección</span><span class="sxs-lookup"><span data-stu-id="37884-181">Collection-based aggregates</span></span>

<span data-ttu-id="37884-182">Los agregados basados en una colección (funciones de colección) operan en las colecciones y devuelven un valor.</span><span class="sxs-lookup"><span data-stu-id="37884-182">Collection-based aggregates (collection functions) operate on collections and return a value.</span></span> <span data-ttu-id="37884-183">Por ejemplo, si ORDERs es una colección de todos los pedidos, puede calcular la fecha de envío más temprana con la expresión siguiente:</span><span class="sxs-lookup"><span data-stu-id="37884-183">For example if ORDERS is a collection of all orders, you can calculate the earliest ship date with the following expression:</span></span>

```sql
min(select value o.ShipDate from LOB.Orders as o)
```

<span data-ttu-id="37884-184">Las expresiones que se encuentran dentro de agregados basados en una colección se evalúan dentro del ámbito actual de la resolución de nombres.</span><span class="sxs-lookup"><span data-stu-id="37884-184">Expressions inside collection-based aggregates are evaluated within the current ambient name-resolution scope.</span></span>

## <a name="group-based-aggregates"></a><span data-ttu-id="37884-185">Agregados basados en grupos</span><span class="sxs-lookup"><span data-stu-id="37884-185">Group-based aggregates</span></span>

<span data-ttu-id="37884-186">Los agregados basados en un grupo se calculan sobre un grupo según define la cláusula GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="37884-186">Group-based aggregates are calculated over a group as defined by the GROUP BY clause.</span></span> <span data-ttu-id="37884-187">Para cada grupo del resultado, se calcula un agregado diferente utilizando los elementos de cada grupo como entrada del cálculo del agregado.</span><span class="sxs-lookup"><span data-stu-id="37884-187">For each group in the result, a separate aggregate is calculated by using the elements in each group as input to the aggregate calculation.</span></span> <span data-ttu-id="37884-188">Cuando se usa una cláusula GROUP-BY en una expresión SELECT, solo se pueden presentar en la cláusula ORDER-BY o de la proyección los nombres de la expresión de agrupamiento, los agregados o las expresiones constantes.</span><span class="sxs-lookup"><span data-stu-id="37884-188">When a group-by clause is used in a select expression, only grouping expression names, aggregates, or constant expressions can be present in the projection or order-by clause.</span></span>

<span data-ttu-id="37884-189">En el ejemplo siguiente se calcula la cantidad promedio pedida de cada producto:</span><span class="sxs-lookup"><span data-stu-id="37884-189">The following example calculates the average quantity ordered for each product:</span></span>

```sql
select p, avg(ol.Quantity) from LOB.OrderLines as ol
  group by ol.Product as p
```

<span data-ttu-id="37884-190">Es posible tener un agregado basado en un grupo sin una cláusula Group-by explícita en la expresión SELECT.</span><span class="sxs-lookup"><span data-stu-id="37884-190">It's possible to have a group-based aggregate without an explicit group-by clause in the SELECT expression.</span></span> <span data-ttu-id="37884-191">En este caso, todos los elementos se tratan como un solo grupo.</span><span class="sxs-lookup"><span data-stu-id="37884-191">In this case, all elements are treated as a single group.</span></span> <span data-ttu-id="37884-192">Esto es equivalente a especificar una agrupación basada en una constante.</span><span class="sxs-lookup"><span data-stu-id="37884-192">This is equivalent of specifying a grouping based on a constant.</span></span> <span data-ttu-id="37884-193">Tome como ejemplo la siguiente expresión:</span><span class="sxs-lookup"><span data-stu-id="37884-193">Take, for example, the following expression:</span></span>

```sql
select avg(ol.Quantity) from LOB.OrderLines as ol
```

<span data-ttu-id="37884-194">Es equivalente a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="37884-194">This is equivalent to the following:</span></span>

```sql
select avg(ol.Quantity) from LOB.OrderLines as ol group by 1
```

<span data-ttu-id="37884-195">Las expresiones que se encuentran dentro del agregado basado en un grupo se evalúan dentro del ámbito de resolución de nombres que sería visible para la expresión de la cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="37884-195">Expressions inside the group-based aggregate are evaluated within the name-resolution scope that would be visible to the WHERE clause expression.</span></span>

<span data-ttu-id="37884-196">Como en Transact-SQL, los agregados basados en grupos también pueden especificar un modificador ALL o DISTINCt.</span><span class="sxs-lookup"><span data-stu-id="37884-196">As in Transact-SQL, group-based aggregates can also specify an ALL or DISTINCT modifier.</span></span> <span data-ttu-id="37884-197">Si se especifica el modificador DISTINCT, los duplicados se eliminan de la colección de entrada del agregado, antes de calcularlo.</span><span class="sxs-lookup"><span data-stu-id="37884-197">If the DISTINCT modifier is specified, duplicates are eliminated from the aggregate input collection, before the aggregate is computed.</span></span> <span data-ttu-id="37884-198">Si se especifica el modificador ALL o no se especifica ningún modificador, no se lleva a cabo la eliminación de los duplicados.</span><span class="sxs-lookup"><span data-stu-id="37884-198">If the ALL modifier is specified (or if no modifier is specified), no duplicate elimination is performed.</span></span>

## <a name="see-also"></a><span data-ttu-id="37884-199">Vea también</span><span class="sxs-lookup"><span data-stu-id="37884-199">See also</span></span>

- [<span data-ttu-id="37884-200">Funciones canónicas</span><span class="sxs-lookup"><span data-stu-id="37884-200">Canonical Functions</span></span>](canonical-functions.md)
