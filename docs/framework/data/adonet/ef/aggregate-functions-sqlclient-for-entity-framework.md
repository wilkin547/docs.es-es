---
title: Funciones de agregado (SqlClient para Entity Framework)
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: cf476192cf049f230c1956e390d215ad4abaa821
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251708"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a><span data-ttu-id="bb799-102">Funciones de agregado (SqlClient para Entity Framework)</span><span class="sxs-lookup"><span data-stu-id="bb799-102">Aggregate Functions (SqlClient for Entity Framework)</span></span>
<span data-ttu-id="bb799-103">El Proveedor de datos .NET Framework para SQL Server (SqlClient) proporciona funciones de agregado.</span><span class="sxs-lookup"><span data-stu-id="bb799-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides aggregate functions.</span></span> <span data-ttu-id="bb799-104">Las funciones de agregado realizan cálculos en un conjunto de valores de entrada y devuelven un valor.</span><span class="sxs-lookup"><span data-stu-id="bb799-104">Aggregate functions perform calculations on a set of input values and return a value.</span></span> <span data-ttu-id="bb799-105">Estas funciones están en el espacio de nombres SqlServer, que está disponible al utilizar SqlClient.</span><span class="sxs-lookup"><span data-stu-id="bb799-105">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="bb799-106">La propiedad del espacio de nombres de un proveedor permite a Entity Framework detectar qué prefijo usa este proveedor para estructuras concretas, como tipos y funciones.</span><span class="sxs-lookup"><span data-stu-id="bb799-106">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span>  
  
 <span data-ttu-id="bb799-107">A continuación se enumeran las funciones de agregado SqlClient.</span><span class="sxs-lookup"><span data-stu-id="bb799-107">The following are the SqlClient aggregate functions.</span></span>  

## <a name="avgexpression"></a><span data-ttu-id="bb799-108">AVG (expresión)</span><span class="sxs-lookup"><span data-stu-id="bb799-108">AVG(expression)</span></span>

<span data-ttu-id="bb799-109">Devuelve el promedio de los valores de una colección.</span><span class="sxs-lookup"><span data-stu-id="bb799-109">Returns the average of the values in a collection.</span></span> <span data-ttu-id="bb799-110">Los valores Null se pasan por alto.</span><span class="sxs-lookup"><span data-stu-id="bb799-110">Null values are ignored.</span></span>

<span data-ttu-id="bb799-111">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="bb799-111">**Arguments**</span></span>

<span data-ttu-id="bb799-112">`Int32` ,`Int64`, Y .`Decimal` `Double`</span><span class="sxs-lookup"><span data-stu-id="bb799-112">An `Int32`, `Int64`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="bb799-113">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="bb799-113">**Return Value**</span></span>

<span data-ttu-id="bb799-114">Tipo de `expression`.</span><span class="sxs-lookup"><span data-stu-id="bb799-114">The type of `expression`.</span></span>

<span data-ttu-id="bb799-115">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="bb799-115">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_avg)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksum_aggcollection"></a><span data-ttu-id="bb799-116">CHECKSUM_AGG (colección)</span><span class="sxs-lookup"><span data-stu-id="bb799-116">CHECKSUM_AGG(collection)</span></span>
 
 <span data-ttu-id="bb799-117">Devuelve la suma de comprobación de los valores de una colección.</span><span class="sxs-lookup"><span data-stu-id="bb799-117">Returns the checksum of the values in a collection.</span></span> <span data-ttu-id="bb799-118">Los valores Null se pasan por alto.</span><span class="sxs-lookup"><span data-stu-id="bb799-118">Null values are ignored.</span></span>
 
 <span data-ttu-id="bb799-119">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="bb799-119">**Arguments**</span></span>
 
 <span data-ttu-id="bb799-120">Colección (`Int32`).</span><span class="sxs-lookup"><span data-stu-id="bb799-120">A Collection(`Int32`).</span></span>
 
 <span data-ttu-id="bb799-121">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="bb799-121">**Return Value**</span></span>
 
 <span data-ttu-id="bb799-122">Una clase `Int32`.</span><span class="sxs-lookup"><span data-stu-id="bb799-122">An `Int32`.</span></span>
 
 <span data-ttu-id="bb799-123">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="bb799-123">**Example**</span></span>
 
 [!code-csharp[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_checksum)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]
   
## <a name="countexpression"></a><span data-ttu-id="bb799-124">COUNT (expresión)</span><span class="sxs-lookup"><span data-stu-id="bb799-124">COUNT(expression)</span></span>

<span data-ttu-id="bb799-125">Devuelve el número de elementos de una colección como un valor `Int32`.</span><span class="sxs-lookup"><span data-stu-id="bb799-125">Returns the number of items in a collection as an `Int32`.</span></span>

<span data-ttu-id="bb799-126">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="bb799-126">**Arguments**</span></span>

<span data-ttu-id="bb799-127">Colección\<t >, donde t es uno de los tipos siguientes:</span><span class="sxs-lookup"><span data-stu-id="bb799-127">A Collection\<T>, where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="bb799-128">`Guid`(no se devuelve en SQL Server 2000)</span><span class="sxs-lookup"><span data-stu-id="bb799-128">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="bb799-129">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="bb799-129">**Return Value**</span></span>

<span data-ttu-id="bb799-130">Una clase `Int32`.</span><span class="sxs-lookup"><span data-stu-id="bb799-130">An `Int32`.</span></span>

<span data-ttu-id="bb799-131">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="bb799-131">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_count)]
<span data-ttu-id="bb799-132">[! code-SQL[DP EntityServices conceptos # SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)</span><span class="sxs-lookup"><span data-stu-id="bb799-132">[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)</span></span>
 
## <a name="count_bigexpression"></a><span data-ttu-id="bb799-133">COUNT_BIG (expresión)</span><span class="sxs-lookup"><span data-stu-id="bb799-133">COUNT_BIG(expression)</span></span>
 
 <span data-ttu-id="bb799-134">Devuelve el número de elementos de una colección como un valor `bigint`.</span><span class="sxs-lookup"><span data-stu-id="bb799-134">Returns the number of items in a collection as a `bigint`.</span></span>
 
 <span data-ttu-id="bb799-135">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="bb799-135">**Arguments**</span></span>
 
 <span data-ttu-id="bb799-136">Colección (T), donde T es uno de los tipos siguientes:</span><span class="sxs-lookup"><span data-stu-id="bb799-136">A Collection(T), where T is one of the following types:</span></span>
 
 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="bb799-137">`Guid`(no se devuelve en SQL Server 2000)</span><span class="sxs-lookup"><span data-stu-id="bb799-137">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="bb799-138">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="bb799-138">**Return Value**</span></span>

<span data-ttu-id="bb799-139">Una clase `Int64`.</span><span class="sxs-lookup"><span data-stu-id="bb799-139">An `Int64`.</span></span>

<span data-ttu-id="bb799-140">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="bb799-140">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_countbig)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a><span data-ttu-id="bb799-141">MAX (expresión)</span><span class="sxs-lookup"><span data-stu-id="bb799-141">MAX(expression)</span></span>

<span data-ttu-id="bb799-142">Devuelve el valor máximo de la colección.</span><span class="sxs-lookup"><span data-stu-id="bb799-142">Returns the maximum value the collection.</span></span>

<span data-ttu-id="bb799-143">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="bb799-143">**Arguments**</span></span>

<span data-ttu-id="bb799-144">Colección (T), donde T es uno de los tipos siguientes:</span><span class="sxs-lookup"><span data-stu-id="bb799-144">A Collection(T), where T is one of the following types:</span></span> 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="bb799-145">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="bb799-145">**Return Value**</span></span>

<span data-ttu-id="bb799-146">Tipo de `expression`.</span><span class="sxs-lookup"><span data-stu-id="bb799-146">The type of `expression`.</span></span>

<span data-ttu-id="bb799-147">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="bb799-147">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_max)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a><span data-ttu-id="bb799-148">MIN (expresión)</span><span class="sxs-lookup"><span data-stu-id="bb799-148">MIN(expression)</span></span>

<span data-ttu-id="bb799-149">Devuelve el valor mínimo de una colección.</span><span class="sxs-lookup"><span data-stu-id="bb799-149">Returns the minimum value in a collection.</span></span>

<span data-ttu-id="bb799-150">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="bb799-150">**Arguments**</span></span>

<span data-ttu-id="bb799-151">Colección (T), donde T es uno de los tipos siguientes:</span><span class="sxs-lookup"><span data-stu-id="bb799-151">A Collection(T), where T is one of the following types:</span></span> 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="bb799-152">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="bb799-152">**Return Value**</span></span>

<span data-ttu-id="bb799-153">Tipo de `expression`.</span><span class="sxs-lookup"><span data-stu-id="bb799-153">The type of `expression`.</span></span>

<span data-ttu-id="bb799-154">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="bb799-154">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_min)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a><span data-ttu-id="bb799-155">STDEV (expresión)</span><span class="sxs-lookup"><span data-stu-id="bb799-155">STDEV(expression)</span></span>

<span data-ttu-id="bb799-156">Devuelve la desviación estándar estadística de todos los valores de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="bb799-156">Returns the statistical standard deviation of all values in the specified expression.</span></span>

<span data-ttu-id="bb799-157">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="bb799-157">**Arguments**</span></span>

<span data-ttu-id="bb799-158">Colección (`Double`).</span><span class="sxs-lookup"><span data-stu-id="bb799-158">A Collection(`Double`).</span></span>

<span data-ttu-id="bb799-159">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="bb799-159">**Return Value**</span></span>

<span data-ttu-id="bb799-160">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="bb799-160">A `Double`.</span></span>

<span data-ttu-id="bb799-161">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="bb799-161">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdev)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a><span data-ttu-id="bb799-162">STDEVP (expresión)</span><span class="sxs-lookup"><span data-stu-id="bb799-162">STDEVP(expression)</span></span>

<span data-ttu-id="bb799-163">Devuelve la desviación estándar estadística de la población para todos los valores de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="bb799-163">Returns the statistical standard deviation for the population for all values in the specified expression.</span></span>

<span data-ttu-id="bb799-164">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="bb799-164">**Arguments**</span></span>

<span data-ttu-id="bb799-165">Colección (`Double`).</span><span class="sxs-lookup"><span data-stu-id="bb799-165">A Collection(`Double`).</span></span>

<span data-ttu-id="bb799-166">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="bb799-166">**Return Value**</span></span>

<span data-ttu-id="bb799-167">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="bb799-167">A `Double`.</span></span>

<span data-ttu-id="bb799-168">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="bb799-168">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdevp)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a><span data-ttu-id="bb799-169">SUM (expresión)</span><span class="sxs-lookup"><span data-stu-id="bb799-169">SUM(expression)</span></span>

<span data-ttu-id="bb799-170">Devuelve la suma de todos los valores de la colección.</span><span class="sxs-lookup"><span data-stu-id="bb799-170">Returns the sum of all the values in the collection.</span></span>

<span data-ttu-id="bb799-171">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="bb799-171">**Arguments**</span></span>

<span data-ttu-id="bb799-172">Colección (T), donde T es uno de los tipos siguientes: `Int32`, `Int64`, `Double`, `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="bb799-172">A Collection(T) where T is one of the following types: `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="bb799-173">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="bb799-173">**Return Value**</span></span>

<span data-ttu-id="bb799-174">Tipo de `expression`.</span><span class="sxs-lookup"><span data-stu-id="bb799-174">The type of `expression`.</span></span>

<span data-ttu-id="bb799-175">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="bb799-175">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_sum)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a><span data-ttu-id="bb799-176">VAR (expresión)</span><span class="sxs-lookup"><span data-stu-id="bb799-176">VAR(expression)</span></span>

<span data-ttu-id="bb799-177">Devuelve la varianza estadística de todos los valores de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="bb799-177">Returns the statistical variance of all values in the specified expression.</span></span>

<span data-ttu-id="bb799-178">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="bb799-178">**Arguments**</span></span>

<span data-ttu-id="bb799-179">Colección (`Double`).</span><span class="sxs-lookup"><span data-stu-id="bb799-179">A Collection(`Double`).</span></span>

<span data-ttu-id="bb799-180">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="bb799-180">**Return Value**</span></span>

<span data-ttu-id="bb799-181">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="bb799-181">A `Double`.</span></span>

<span data-ttu-id="bb799-182">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="bb799-182">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_var)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a><span data-ttu-id="bb799-183">VARP (expresión)</span><span class="sxs-lookup"><span data-stu-id="bb799-183">VARP(expression)</span></span>

<span data-ttu-id="bb799-184">Devuelve la varianza estadística de la población para todos los valores de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="bb799-184">Returns the statistical variance for the population for all values in the specified expression.</span></span>

<span data-ttu-id="bb799-185">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="bb799-185">**Arguments**</span></span>

<span data-ttu-id="bb799-186">Colección (`Double`).</span><span class="sxs-lookup"><span data-stu-id="bb799-186">A Collection(`Double`).</span></span>

<span data-ttu-id="bb799-187">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="bb799-187">**Return Value**</span></span>

<span data-ttu-id="bb799-188">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="bb799-188">A `Double`.</span></span>

<span data-ttu-id="bb799-189">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="bb799-189">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_varp)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)] 
  
## <a name="see-also"></a><span data-ttu-id="bb799-190">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb799-190">See also</span></span>

<span data-ttu-id="bb799-191">Para obtener más información sobre las funciones de agregado que SqlClient admite, consulte la documentación de la versión de SQL Server que especificó en el manifiesto del proveedor SQLCLIENT:</span><span class="sxs-lookup"><span data-stu-id="bb799-191">For more information about the aggregate functions that SqlClient supports, see the documentation for the SQL Server version that you specified in the SqlClient provider manifest:</span></span>

- <span data-ttu-id="bb799-192">**SQL Server 2005:** [Funciones de agregado (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms173454(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="bb799-192">**SQL Server 2005:** [Aggregate Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms173454(v=sql.90))</span></span>
- <span data-ttu-id="bb799-193">**SQL Server 2008 y versiones posteriores:** [Funciones de agregado (Transact-SQL)](/sql/t-sql/functions/aggregate-functions-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="bb799-193">**SQL Server 2008 and later:** [Aggregate Functions (Transact-SQL)](/sql/t-sql/functions/aggregate-functions-transact-sql)</span></span>

- [<span data-ttu-id="bb799-194">Lenguaje Entity SQL</span><span class="sxs-lookup"><span data-stu-id="bb799-194">Entity SQL Language</span></span>](./language-reference/entity-sql-language.md)
- [<span data-ttu-id="bb799-195">Funciones canónicas de agregado</span><span class="sxs-lookup"><span data-stu-id="bb799-195">Aggregate Canonical Functions</span></span>](./language-reference/aggregate-canonical-functions.md)
