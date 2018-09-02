---
title: Funciones de agregado (SqlClient para Entity Framework)
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: 8ed9a58da9914724fe312876d6594cb526f2e0e9
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43452904"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a><span data-ttu-id="64c0f-102">Funciones de agregado (SqlClient para Entity Framework)</span><span class="sxs-lookup"><span data-stu-id="64c0f-102">Aggregate Functions (SqlClient for Entity Framework)</span></span>
<span data-ttu-id="64c0f-103">El Proveedor de datos .NET Framework para SQL Server (SqlClient) proporciona funciones de agregado.</span><span class="sxs-lookup"><span data-stu-id="64c0f-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides aggregate functions.</span></span> <span data-ttu-id="64c0f-104">Las funciones de agregado realizan cálculos en un conjunto de valores de entrada y devuelven un valor.</span><span class="sxs-lookup"><span data-stu-id="64c0f-104">Aggregate functions perform calculations on a set of input values and return a value.</span></span> <span data-ttu-id="64c0f-105">Estas funciones están en el espacio de nombres SqlServer, que está disponible al utilizar SqlClient.</span><span class="sxs-lookup"><span data-stu-id="64c0f-105">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="64c0f-106">La propiedad del espacio de nombres de un proveedor permite a Entity Framework detectar qué prefijo usa este proveedor para estructuras concretas, como tipos y funciones.</span><span class="sxs-lookup"><span data-stu-id="64c0f-106">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span>  
  
 <span data-ttu-id="64c0f-107">Las siguientes son las funciones de agregado de SqlClient.</span><span class="sxs-lookup"><span data-stu-id="64c0f-107">The following are the SqlClient aggregate functions.</span></span>  

## <a name="avgexpression"></a><span data-ttu-id="64c0f-108">AVG(Expression)</span><span class="sxs-lookup"><span data-stu-id="64c0f-108">AVG(expression)</span></span>

<span data-ttu-id="64c0f-109">Devuelve el promedio de los valores de una colección.</span><span class="sxs-lookup"><span data-stu-id="64c0f-109">Returns the average of the values in a collection.</span></span> <span data-ttu-id="64c0f-110">Los valores Null se pasan por alto.</span><span class="sxs-lookup"><span data-stu-id="64c0f-110">Null values are ignored.</span></span>

<span data-ttu-id="64c0f-111">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="64c0f-111">**Arguments**</span></span>

<span data-ttu-id="64c0f-112">Un `Int32`, `Int64`, `Double`, y `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="64c0f-112">An `Int32`, `Int64`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="64c0f-113">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="64c0f-113">**Return Value**</span></span>

<span data-ttu-id="64c0f-114">Tipo de `expression`.</span><span class="sxs-lookup"><span data-stu-id="64c0f-114">The type of `expression`.</span></span>

<span data-ttu-id="64c0f-115">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="64c0f-115">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_avg)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksumaggcollection"></a><span data-ttu-id="64c0f-116">CHECKSUM_AGG(Collection)</span><span class="sxs-lookup"><span data-stu-id="64c0f-116">CHECKSUM_AGG(collection)</span></span>
 
 <span data-ttu-id="64c0f-117">Devuelve la suma de comprobación de los valores de una colección.</span><span class="sxs-lookup"><span data-stu-id="64c0f-117">Returns the checksum of the values in a collection.</span></span> <span data-ttu-id="64c0f-118">Los valores Null se pasan por alto.</span><span class="sxs-lookup"><span data-stu-id="64c0f-118">Null values are ignored.</span></span>
 
 <span data-ttu-id="64c0f-119">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="64c0f-119">**Arguments**</span></span>
 
 <span data-ttu-id="64c0f-120">Una colección (`Int32`).</span><span class="sxs-lookup"><span data-stu-id="64c0f-120">A Collection(`Int32`).</span></span>
 
 <span data-ttu-id="64c0f-121">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="64c0f-121">**Return Value**</span></span>
 
 <span data-ttu-id="64c0f-122">Una clase `Int32`.</span><span class="sxs-lookup"><span data-stu-id="64c0f-122">An `Int32`.</span></span>
 
 <span data-ttu-id="64c0f-123">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="64c0f-123">**Example**</span></span>
 
 [!code-csharp[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_checksum)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]
   
## <a name="countexpression"></a><span data-ttu-id="64c0f-124">COUNT_BIG</span><span class="sxs-lookup"><span data-stu-id="64c0f-124">COUNT(expression)</span></span>

<span data-ttu-id="64c0f-125">Devuelve el número de elementos de una colección como un valor `Int32`.</span><span class="sxs-lookup"><span data-stu-id="64c0f-125">Returns the number of items in a collection as an `Int32`.</span></span>

<span data-ttu-id="64c0f-126">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="64c0f-126">**Arguments**</span></span>

<span data-ttu-id="64c0f-127">Una colección\<T >, donde T es uno de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="64c0f-127">A Collection\<T>, where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="64c0f-128">`Guid` (no se devuelve en SQL Server 2000)</span><span class="sxs-lookup"><span data-stu-id="64c0f-128">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="64c0f-129">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="64c0f-129">**Return Value**</span></span>

<span data-ttu-id="64c0f-130">Una clase `Int32`.</span><span class="sxs-lookup"><span data-stu-id="64c0f-130">An `Int32`.</span></span>

<span data-ttu-id="64c0f-131">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="64c0f-131">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_count)]
<span data-ttu-id="64c0f-132">[! código sql[DP EntityServices conceptos #SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)</span><span class="sxs-lookup"><span data-stu-id="64c0f-132">[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)</span></span>
 
## <a name="countbigexpression"></a><span data-ttu-id="64c0f-133">COUNT_BIG(Expression)</span><span class="sxs-lookup"><span data-stu-id="64c0f-133">COUNT_BIG(expression)</span></span>
 
 <span data-ttu-id="64c0f-134">Devuelve el número de elementos de una colección como un valor `bigint`.</span><span class="sxs-lookup"><span data-stu-id="64c0f-134">Returns the number of items in a collection as a `bigint`.</span></span>
 
 <span data-ttu-id="64c0f-135">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="64c0f-135">**Arguments**</span></span>
 
 <span data-ttu-id="64c0f-136">Collection(T), donde T es uno de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="64c0f-136">A Collection(T), where T is one of the following types:</span></span>
 
 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="64c0f-137">`Guid` (no se devuelve en SQL Server 2000)</span><span class="sxs-lookup"><span data-stu-id="64c0f-137">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="64c0f-138">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="64c0f-138">**Return Value**</span></span>

<span data-ttu-id="64c0f-139">Una clase `Int64`.</span><span class="sxs-lookup"><span data-stu-id="64c0f-139">An `Int64`.</span></span>

<span data-ttu-id="64c0f-140">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="64c0f-140">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_countbig)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a><span data-ttu-id="64c0f-141">Max(Expression)</span><span class="sxs-lookup"><span data-stu-id="64c0f-141">MAX(expression)</span></span>

<span data-ttu-id="64c0f-142">Devuelve el valor máximo de la colección.</span><span class="sxs-lookup"><span data-stu-id="64c0f-142">Returns the maximum value the collection.</span></span>

<span data-ttu-id="64c0f-143">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="64c0f-143">**Arguments**</span></span>

<span data-ttu-id="64c0f-144">Collection(T), donde T es uno de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="64c0f-144">A Collection(T), where T is one of the following types:</span></span> 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="64c0f-145">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="64c0f-145">**Return Value**</span></span>

<span data-ttu-id="64c0f-146">Tipo de `expression`.</span><span class="sxs-lookup"><span data-stu-id="64c0f-146">The type of `expression`.</span></span>

<span data-ttu-id="64c0f-147">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="64c0f-147">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_max)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a><span data-ttu-id="64c0f-148">MIN(Expression)</span><span class="sxs-lookup"><span data-stu-id="64c0f-148">MIN(expression)</span></span>

<span data-ttu-id="64c0f-149">Devuelve el valor mínimo de una colección.</span><span class="sxs-lookup"><span data-stu-id="64c0f-149">Returns the minimum value in a collection.</span></span>

<span data-ttu-id="64c0f-150">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="64c0f-150">**Arguments**</span></span>

<span data-ttu-id="64c0f-151">Collection(T), donde T es uno de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="64c0f-151">A Collection(T), where T is one of the following types:</span></span> 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="64c0f-152">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="64c0f-152">**Return Value**</span></span>

<span data-ttu-id="64c0f-153">Tipo de `expression`.</span><span class="sxs-lookup"><span data-stu-id="64c0f-153">The type of `expression`.</span></span>

<span data-ttu-id="64c0f-154">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="64c0f-154">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_min)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a><span data-ttu-id="64c0f-155">STDEV(Expression)</span><span class="sxs-lookup"><span data-stu-id="64c0f-155">STDEV(expression)</span></span>

<span data-ttu-id="64c0f-156">Devuelve la desviación estándar estadística de todos los valores de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="64c0f-156">Returns the statistical standard deviation of all values in the specified expression.</span></span>

<span data-ttu-id="64c0f-157">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="64c0f-157">**Arguments**</span></span>

<span data-ttu-id="64c0f-158">Una colección (`Double`).</span><span class="sxs-lookup"><span data-stu-id="64c0f-158">A Collection(`Double`).</span></span>

<span data-ttu-id="64c0f-159">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="64c0f-159">**Return Value**</span></span>

<span data-ttu-id="64c0f-160">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="64c0f-160">A `Double`.</span></span>

<span data-ttu-id="64c0f-161">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="64c0f-161">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdev)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a><span data-ttu-id="64c0f-162">STDEVP(Expression)</span><span class="sxs-lookup"><span data-stu-id="64c0f-162">STDEVP(expression)</span></span>

<span data-ttu-id="64c0f-163">Devuelve la desviación estándar estadística de la población para todos los valores de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="64c0f-163">Returns the statistical standard deviation for the population for all values in the specified expression.</span></span>

<span data-ttu-id="64c0f-164">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="64c0f-164">**Arguments**</span></span>

<span data-ttu-id="64c0f-165">Una colección (`Double`).</span><span class="sxs-lookup"><span data-stu-id="64c0f-165">A Collection(`Double`).</span></span>

<span data-ttu-id="64c0f-166">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="64c0f-166">**Return Value**</span></span>

<span data-ttu-id="64c0f-167">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="64c0f-167">A `Double`.</span></span>

<span data-ttu-id="64c0f-168">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="64c0f-168">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdevp)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a><span data-ttu-id="64c0f-169">SUM(Expression)</span><span class="sxs-lookup"><span data-stu-id="64c0f-169">SUM(expression)</span></span>

<span data-ttu-id="64c0f-170">Devuelve la suma de todos los valores de la colección.</span><span class="sxs-lookup"><span data-stu-id="64c0f-170">Returns the sum of all the values in the collection.</span></span>

<span data-ttu-id="64c0f-171">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="64c0f-171">**Arguments**</span></span>

<span data-ttu-id="64c0f-172">Un Collection(T) donde T es uno de los siguientes tipos: `Int32`, `Int64`, `Double`, `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="64c0f-172">A Collection(T) where T is one of the following types: `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="64c0f-173">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="64c0f-173">**Return Value**</span></span>

<span data-ttu-id="64c0f-174">Tipo de `expression`.</span><span class="sxs-lookup"><span data-stu-id="64c0f-174">The type of `expression`.</span></span>

<span data-ttu-id="64c0f-175">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="64c0f-175">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_sum)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a><span data-ttu-id="64c0f-176">Var</span><span class="sxs-lookup"><span data-stu-id="64c0f-176">VAR(expression)</span></span>

<span data-ttu-id="64c0f-177">Devuelve la varianza estadística de todos los valores de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="64c0f-177">Returns the statistical variance of all values in the specified expression.</span></span>

<span data-ttu-id="64c0f-178">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="64c0f-178">**Arguments**</span></span>

<span data-ttu-id="64c0f-179">Una colección (`Double`).</span><span class="sxs-lookup"><span data-stu-id="64c0f-179">A Collection(`Double`).</span></span>

<span data-ttu-id="64c0f-180">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="64c0f-180">**Return Value**</span></span>

<span data-ttu-id="64c0f-181">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="64c0f-181">A `Double`.</span></span>

<span data-ttu-id="64c0f-182">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="64c0f-182">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_var)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a><span data-ttu-id="64c0f-183">VarP(Expression)</span><span class="sxs-lookup"><span data-stu-id="64c0f-183">VARP(expression)</span></span>

<span data-ttu-id="64c0f-184">Devuelve la varianza estadística de la población para todos los valores de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="64c0f-184">Returns the statistical variance for the population for all values in the specified expression.</span></span>

<span data-ttu-id="64c0f-185">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="64c0f-185">**Arguments**</span></span>

<span data-ttu-id="64c0f-186">Una colección (`Double`).</span><span class="sxs-lookup"><span data-stu-id="64c0f-186">A Collection(`Double`).</span></span>

<span data-ttu-id="64c0f-187">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="64c0f-187">**Return Value**</span></span>

<span data-ttu-id="64c0f-188">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="64c0f-188">A `Double`.</span></span>

<span data-ttu-id="64c0f-189">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="64c0f-189">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_varp)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)] 
  
## <a name="see-also"></a><span data-ttu-id="64c0f-190">Vea también</span><span class="sxs-lookup"><span data-stu-id="64c0f-190">See also</span></span>

<span data-ttu-id="64c0f-191">Para obtener más información sobre las funciones de agregado que SqlClient admite, consulte la documentación de la versión de SQL Server que especificó en el manifiesto del proveedor SQLCLIENT:</span><span class="sxs-lookup"><span data-stu-id="64c0f-191">For more information about the aggregate functions that SqlClient supports, see the documentation for the SQL Server version that you specified in the SqlClient provider manifest:</span></span>  
  
<span data-ttu-id="64c0f-192">**SQL Server 2005**: [funciones de agregado (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms173454(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="64c0f-192">**SQL Server 2005**: [Aggregate Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms173454(v=sql.90))</span></span>  
<span data-ttu-id="64c0f-193">**SQL Server 2008 y versiones posterior**: [las funciones de agregado (Transact-SQL)](/sql/t-sql/functions/aggregate-functions-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="64c0f-193">**SQL Server 2008 and later**:  [Aggregate Functions (Transact-SQL)](/sql/t-sql/functions/aggregate-functions-transact-sql)</span></span>  
[<span data-ttu-id="64c0f-194">Lenguaje Entity SQL</span><span class="sxs-lookup"><span data-stu-id="64c0f-194">Entity SQL Language</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)  
[<span data-ttu-id="64c0f-195">Funciones canónicas de agregado</span><span class="sxs-lookup"><span data-stu-id="64c0f-195">Aggregate Canonical Functions</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)
