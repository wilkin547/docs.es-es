---
title: Funciones canónicas de agregado
ms.date: 03/30/2017
ms.assetid: 3bcff826-ca90-41b3-a791-04d6ff0e5085
ms.openlocfilehash: 3f4bb84c45e503fc0018e7869f3b41ddab4581a6
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251357"
---
# <a name="aggregate-canonical-functions"></a><span data-ttu-id="f8296-102">Funciones canónicas de agregado</span><span class="sxs-lookup"><span data-stu-id="f8296-102">Aggregate Canonical Functions</span></span>

<span data-ttu-id="f8296-103">Los agregados son expresiones que reducen una serie de valores de entrada a un único valor, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f8296-103">Aggregates are expressions that reduce a series of input values into, for example, a single value.</span></span> <span data-ttu-id="f8296-104">Los agregados suelen usarse junto con la cláusula GROUP BY de la expresión SELECT y hay restricciones con respecto a dónde se pueden usar.</span><span class="sxs-lookup"><span data-stu-id="f8296-104">Aggregates are normally used in conjunction with the GROUP BY clause of the SELECT expression, and there are constraints on where they can be used.</span></span>

## <a name="aggregate-entity-sql-canonical-functions"></a><span data-ttu-id="f8296-105">Funciones canónicas de agregado Entity SQL</span><span class="sxs-lookup"><span data-stu-id="f8296-105">Aggregate Entity SQL canonical functions</span></span>

<span data-ttu-id="f8296-106">A continuación se muestran las funciones canónicas Entity SQL agregadas.</span><span class="sxs-lookup"><span data-stu-id="f8296-106">The following are the aggregate Entity SQL canonical functions.</span></span>

### <a name="avgexpression"></a><span data-ttu-id="f8296-107">Avg(expresión)</span><span class="sxs-lookup"><span data-stu-id="f8296-107">Avg(expression)</span></span>

<span data-ttu-id="f8296-108">Devuelve el promedio de los valores no NULL.</span><span class="sxs-lookup"><span data-stu-id="f8296-108">Returns the average of the non-null values.</span></span>

<span data-ttu-id="f8296-109">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="f8296-109">**Arguments**</span></span>

<span data-ttu-id="f8296-110">`Int32` ,`Int64`, Y .`Decimal` `Double`</span><span class="sxs-lookup"><span data-stu-id="f8296-110">An `Int32`, `Int64`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="f8296-111">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="f8296-111">**Return Value**</span></span>

<span data-ttu-id="f8296-112">El tipo de `expression`, o `null` si todos los valores de `null` entrada son valores.</span><span class="sxs-lookup"><span data-stu-id="f8296-112">The type of `expression`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="f8296-113">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="f8296-113">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_AVG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_avg)]
[!code-sql[DP EntityServices Concepts#EDM_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_avg)]

### <a name="bigcountexpression"></a><span data-ttu-id="f8296-114">BigCount(expresión)</span><span class="sxs-lookup"><span data-stu-id="f8296-114">BigCount(expression)</span></span>

<span data-ttu-id="f8296-115">Devuelve el tamaño del agregado, incluyendo los valores NULL y los duplicados.</span><span class="sxs-lookup"><span data-stu-id="f8296-115">Returns the size of the aggregate including null and duplicate values.</span></span>

<span data-ttu-id="f8296-116">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="f8296-116">**Arguments**</span></span>

<span data-ttu-id="f8296-117">Cualquier tipo.</span><span class="sxs-lookup"><span data-stu-id="f8296-117">Any type.</span></span>

<span data-ttu-id="f8296-118">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="f8296-118">**Return Value**</span></span>

<span data-ttu-id="f8296-119">Una clase `Int64`.</span><span class="sxs-lookup"><span data-stu-id="f8296-119">An `Int64`.</span></span>

<span data-ttu-id="f8296-120">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="f8296-120">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_BIGCOUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_bigcount)]
[!code-sql[DP EntityServices Concepts#EDM_BIGCOUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_bigcount)]

### <a name="countexpression"></a><span data-ttu-id="f8296-121">Count(expresión)</span><span class="sxs-lookup"><span data-stu-id="f8296-121">Count(expression)</span></span>

<span data-ttu-id="f8296-122">Devuelve el tamaño del agregado, incluyendo los valores NULL y los duplicados.</span><span class="sxs-lookup"><span data-stu-id="f8296-122">Returns the size of the aggregate including null and duplicate values.</span></span>

<span data-ttu-id="f8296-123">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="f8296-123">**Arguments**</span></span>

<span data-ttu-id="f8296-124">Cualquier tipo.</span><span class="sxs-lookup"><span data-stu-id="f8296-124">Any type.</span></span>

<span data-ttu-id="f8296-125">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="f8296-125">**Return Value**</span></span>

<span data-ttu-id="f8296-126">Una clase `Int32`.</span><span class="sxs-lookup"><span data-stu-id="f8296-126">An `Int32`.</span></span>

<span data-ttu-id="f8296-127">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="f8296-127">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_COUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_count)]
[!code-sql[DP EntityServices Concepts#EDM_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_count)]

### <a name="maxexpression"></a><span data-ttu-id="f8296-128">Max(expresión)</span><span class="sxs-lookup"><span data-stu-id="f8296-128">Max(expression)</span></span>

<span data-ttu-id="f8296-129">Devuelve el máximo de los valores no NULL.</span><span class="sxs-lookup"><span data-stu-id="f8296-129">Returns the maximum of the non-null values.</span></span>

<span data-ttu-id="f8296-130">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="f8296-130">**Arguments**</span></span>

<span data-ttu-id="f8296-131">A `Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary`.</span><span class="sxs-lookup"><span data-stu-id="f8296-131">A `Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary`.</span></span>

<span data-ttu-id="f8296-132">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="f8296-132">**Return Value**</span></span>

<span data-ttu-id="f8296-133">El tipo de `expression`, o `null` si todos los valores de `null` entrada son valores.</span><span class="sxs-lookup"><span data-stu-id="f8296-133">The type of `expression`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="f8296-134">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="f8296-134">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_MAX](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_max)]
[!code-sql[DP EntityServices Concepts#EDM_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_max)]

### <a name="minexpression"></a><span data-ttu-id="f8296-135">Min(expresión)</span><span class="sxs-lookup"><span data-stu-id="f8296-135">Min(expression)</span></span>

<span data-ttu-id="f8296-136">Devuelve el mínimo de los valores no NULL.</span><span class="sxs-lookup"><span data-stu-id="f8296-136">Returns the minimum of the non-null values.</span></span>

<span data-ttu-id="f8296-137">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="f8296-137">**Arguments**</span></span>

<span data-ttu-id="f8296-138">A `Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary`.</span><span class="sxs-lookup"><span data-stu-id="f8296-138">A `Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary`.</span></span>

<span data-ttu-id="f8296-139">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="f8296-139">**Return Value**</span></span>

<span data-ttu-id="f8296-140">El tipo de `expression`, o `null` si todos los valores de `null` entrada son valores.</span><span class="sxs-lookup"><span data-stu-id="f8296-140">The type of `expression`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="f8296-141">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="f8296-141">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_MIN](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_min)]
[!code-sql[DP EntityServices Concepts#EDM_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_min)]

### <a name="stdevexpression"></a><span data-ttu-id="f8296-142">StDev(expresión)</span><span class="sxs-lookup"><span data-stu-id="f8296-142">StDev(expression)</span></span>

<span data-ttu-id="f8296-143">Devuelve la desviación estándar de los valores no NULL.</span><span class="sxs-lookup"><span data-stu-id="f8296-143">Returns the standard deviation of the non-null values.</span></span>

<span data-ttu-id="f8296-144">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="f8296-144">**Arguments**</span></span>

<span data-ttu-id="f8296-145">Valor de tipo `Int32`, `Int64`, `Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="f8296-145">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="f8296-146">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="f8296-146">**Return Value**</span></span>

<span data-ttu-id="f8296-147">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="f8296-147">A `Double`.</span></span> <span data-ttu-id="f8296-148">`Null` si los valores de entrada son `null`.</span><span class="sxs-lookup"><span data-stu-id="f8296-148">`Null`, if all input values are `null` values.</span></span>

<span data-ttu-id="f8296-149">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="f8296-149">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_STDEV](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_stdev)]
[!code-sql[DP EntityServices Concepts#EDM_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_stdev)]

### <a name="stdevpexpression"></a><span data-ttu-id="f8296-150">StDevP(expresión)</span><span class="sxs-lookup"><span data-stu-id="f8296-150">StDevP(expression)</span></span>

<span data-ttu-id="f8296-151">Devuelve la desviación estándar de la población para todos los valores.</span><span class="sxs-lookup"><span data-stu-id="f8296-151">Returns the standard deviation for the population of all values.</span></span>

<span data-ttu-id="f8296-152">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="f8296-152">**Arguments**</span></span>

<span data-ttu-id="f8296-153">Valor de tipo `Int32`, `Int64`, `Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="f8296-153">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="f8296-154">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="f8296-154">**Return Value**</span></span>

<span data-ttu-id="f8296-155">O si todos los valores de entrada son `null` valores. `null` `Double`</span><span class="sxs-lookup"><span data-stu-id="f8296-155">A `Double`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="f8296-156">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="f8296-156">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_STDEVP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_stdevp)]
[!code-sql[DP EntityServices Concepts#EDM_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_stdevp)]

### <a name="sumexpression"></a><span data-ttu-id="f8296-157">Sum(expresión)</span><span class="sxs-lookup"><span data-stu-id="f8296-157">Sum(expression)</span></span>

<span data-ttu-id="f8296-158">Devuelve la suma de los valores no NULL.</span><span class="sxs-lookup"><span data-stu-id="f8296-158">Returns the sum of the non-null values.</span></span>

<span data-ttu-id="f8296-159">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="f8296-159">**Arguments**</span></span>

<span data-ttu-id="f8296-160">Valor de tipo `Int32`, `Int64`, `Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="f8296-160">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="f8296-161">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="f8296-161">**Return Value**</span></span>

<span data-ttu-id="f8296-162">O si todos los valores de entrada son `null` valores. `null` `Double`</span><span class="sxs-lookup"><span data-stu-id="f8296-162">A `Double`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="f8296-163">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="f8296-163">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_SUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_sum)]
[!code-sql[DP EntityServices Concepts#EDM_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_sum)]

### <a name="varexpression"></a><span data-ttu-id="f8296-164">Var(expresión)</span><span class="sxs-lookup"><span data-stu-id="f8296-164">Var(expression)</span></span>

<span data-ttu-id="f8296-165">Devuelve la varianza de todos los valores no nulos.</span><span class="sxs-lookup"><span data-stu-id="f8296-165">Returns the variance of all non-null values.</span></span>

<span data-ttu-id="f8296-166">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="f8296-166">**Arguments**</span></span>

<span data-ttu-id="f8296-167">Valor de tipo `Int32`, `Int64`, `Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="f8296-167">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="f8296-168">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="f8296-168">**Return Value**</span></span>

<span data-ttu-id="f8296-169">O si todos los valores de entrada son `null` valores. `null` `Double`</span><span class="sxs-lookup"><span data-stu-id="f8296-169">A `Double`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="f8296-170">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="f8296-170">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_VAR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_var)]
[!code-sql[DP EntityServices Concepts#EDM_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_var)]

### <a name="varpexpression"></a><span data-ttu-id="f8296-171">VarP(expresión)</span><span class="sxs-lookup"><span data-stu-id="f8296-171">VarP(expression)</span></span>

<span data-ttu-id="f8296-172">Devuelve la varianza de la población para todos los valores no nulos.</span><span class="sxs-lookup"><span data-stu-id="f8296-172">Returns the variance for the population of all non-null values.</span></span>

<span data-ttu-id="f8296-173">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="f8296-173">**Arguments**</span></span>

<span data-ttu-id="f8296-174">Valor de tipo `Int32`, `Int64`, `Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="f8296-174">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="f8296-175">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="f8296-175">**Return Value**</span></span>

<span data-ttu-id="f8296-176">O si todos los valores de entrada son `null` valores. `null` `Double`</span><span class="sxs-lookup"><span data-stu-id="f8296-176">A `Double`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="f8296-177">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="f8296-177">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_VARP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_varp)]
[!code-sql[DP EntityServices Concepts#EDM_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_varp)]

<span data-ttu-id="f8296-178">La funcionalidad equivalente está disponible en el proveedor administrado de Microsoft SQL Client.</span><span class="sxs-lookup"><span data-stu-id="f8296-178">Equivalent functionality is available in the Microsoft SQL Client Managed Provider.</span></span> <span data-ttu-id="f8296-179">Para obtener más información, vea [SqlClient para funciones de Entity Framework](../sqlclient-for-ef-functions.md).</span><span class="sxs-lookup"><span data-stu-id="f8296-179">For more information, see [SqlClient for Entity Framework Functions](../sqlclient-for-ef-functions.md).</span></span>

## <a name="collection-based-aggregates"></a><span data-ttu-id="f8296-180">Agregados basados en una colección</span><span class="sxs-lookup"><span data-stu-id="f8296-180">Collection-based aggregates</span></span>

<span data-ttu-id="f8296-181">Los agregados basados en una colección (funciones de colección) operan en las colecciones y devuelven un valor.</span><span class="sxs-lookup"><span data-stu-id="f8296-181">Collection-based aggregates (collection functions) operate on collections and return a value.</span></span> <span data-ttu-id="f8296-182">Por ejemplo, si ORDERs es una colección de todos los pedidos, puede calcular la fecha de envío más temprana con la expresión siguiente:</span><span class="sxs-lookup"><span data-stu-id="f8296-182">For example if ORDERS is a collection of all orders, you can calculate the earliest ship date with the following expression:</span></span>

```sql
min(select value o.ShipDate from LOB.Orders as o)
```

<span data-ttu-id="f8296-183">Las expresiones que se encuentran dentro de agregados basados en una colección se evalúan dentro del ámbito actual de la resolución de nombres.</span><span class="sxs-lookup"><span data-stu-id="f8296-183">Expressions inside collection-based aggregates are evaluated within the current ambient name-resolution scope.</span></span>

## <a name="group-based-aggregates"></a><span data-ttu-id="f8296-184">Agregados basados en grupos</span><span class="sxs-lookup"><span data-stu-id="f8296-184">Group-based aggregates</span></span>

<span data-ttu-id="f8296-185">Los agregados basados en un grupo se calculan sobre un grupo según define la cláusula GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="f8296-185">Group-based aggregates are calculated over a group as defined by the GROUP BY clause.</span></span> <span data-ttu-id="f8296-186">Para cada grupo del resultado, se calcula un agregado diferente utilizando los elementos de cada grupo como entrada del cálculo del agregado.</span><span class="sxs-lookup"><span data-stu-id="f8296-186">For each group in the result, a separate aggregate is calculated by using the elements in each group as input to the aggregate calculation.</span></span> <span data-ttu-id="f8296-187">Cuando se usa una cláusula GROUP-BY en una expresión SELECT, solo se pueden presentar en la cláusula ORDER-BY o de la proyección los nombres de la expresión de agrupamiento, los agregados o las expresiones constantes.</span><span class="sxs-lookup"><span data-stu-id="f8296-187">When a group-by clause is used in a select expression, only grouping expression names, aggregates, or constant expressions can be present in the projection or order-by clause.</span></span>

<span data-ttu-id="f8296-188">En el ejemplo siguiente se calcula la cantidad promedio pedida de cada producto:</span><span class="sxs-lookup"><span data-stu-id="f8296-188">The following example calculates the average quantity ordered for each product:</span></span>

```sql
select p, avg(ol.Quantity) from LOB.OrderLines as ol
  group by ol.Product as p
```

<span data-ttu-id="f8296-189">Es posible tener un agregado basado en un grupo sin una cláusula Group-by explícita en la expresión SELECT.</span><span class="sxs-lookup"><span data-stu-id="f8296-189">It's possible to have a group-based aggregate without an explicit group-by clause in the SELECT expression.</span></span> <span data-ttu-id="f8296-190">En este caso, todos los elementos se tratan como un solo grupo.</span><span class="sxs-lookup"><span data-stu-id="f8296-190">In this case, all elements are treated as a single group.</span></span> <span data-ttu-id="f8296-191">Esto es equivalente a especificar una agrupación basada en una constante.</span><span class="sxs-lookup"><span data-stu-id="f8296-191">This is equivalent of specifying a grouping based on a constant.</span></span> <span data-ttu-id="f8296-192">Tome como ejemplo la siguiente expresión:</span><span class="sxs-lookup"><span data-stu-id="f8296-192">Take, for example, the following expression:</span></span>

```sql
select avg(ol.Quantity) from LOB.OrderLines as ol
```

<span data-ttu-id="f8296-193">Es equivalente a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="f8296-193">This is equivalent to the following:</span></span>

```sql
select avg(ol.Quantity) from LOB.OrderLines as ol group by 1
```

<span data-ttu-id="f8296-194">Las expresiones que se encuentran dentro del agregado basado en un grupo se evalúan dentro del ámbito de resolución de nombres que sería visible para la expresión de la cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="f8296-194">Expressions inside the group-based aggregate are evaluated within the name-resolution scope that would be visible to the WHERE clause expression.</span></span>

<span data-ttu-id="f8296-195">Como en Transact-SQL, los agregados basados en grupos también pueden especificar un modificador ALL o DISTINCt.</span><span class="sxs-lookup"><span data-stu-id="f8296-195">As in Transact-SQL, group-based aggregates can also specify an ALL or DISTINCT modifier.</span></span> <span data-ttu-id="f8296-196">Si se especifica el modificador DISTINCT, los duplicados se eliminan de la colección de entrada del agregado, antes de calcularlo.</span><span class="sxs-lookup"><span data-stu-id="f8296-196">If the DISTINCT modifier is specified, duplicates are eliminated from the aggregate input collection, before the aggregate is computed.</span></span> <span data-ttu-id="f8296-197">Si se especifica el modificador ALL o no se especifica ningún modificador, no se lleva a cabo la eliminación de los duplicados.</span><span class="sxs-lookup"><span data-stu-id="f8296-197">If the ALL modifier is specified (or if no modifier is specified), no duplicate elimination is performed.</span></span>

## <a name="see-also"></a><span data-ttu-id="f8296-198">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8296-198">See also</span></span>

- [<span data-ttu-id="f8296-199">Funciones canónicas</span><span class="sxs-lookup"><span data-stu-id="f8296-199">Canonical Functions</span></span>](canonical-functions.md)
