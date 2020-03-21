---
title: Funciones de agregado (SqlClient para Entity Framework)
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: 1fad25f2229b4fa810cf82a96dcb8c50a9de3070
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150654"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a><span data-ttu-id="d69b1-102">Funciones de agregado (SqlClient para Entity Framework)</span><span class="sxs-lookup"><span data-stu-id="d69b1-102">Aggregate Functions (SqlClient for Entity Framework)</span></span>
<span data-ttu-id="d69b1-103">El Proveedor de datos .NET Framework para SQL Server (SqlClient) proporciona funciones de agregado.</span><span class="sxs-lookup"><span data-stu-id="d69b1-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides aggregate functions.</span></span> <span data-ttu-id="d69b1-104">Las funciones de agregado realizan cálculos en un conjunto de valores de entrada y devuelven un valor.</span><span class="sxs-lookup"><span data-stu-id="d69b1-104">Aggregate functions perform calculations on a set of input values and return a value.</span></span> <span data-ttu-id="d69b1-105">Estas funciones están en el espacio de nombres SqlServer, que está disponible al utilizar SqlClient.</span><span class="sxs-lookup"><span data-stu-id="d69b1-105">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="d69b1-106">La propiedad del espacio de nombres de un proveedor permite a Entity Framework detectar qué prefijo usa este proveedor para estructuras concretas, como tipos y funciones.</span><span class="sxs-lookup"><span data-stu-id="d69b1-106">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span>  
  
 <span data-ttu-id="d69b1-107">A continuación se muestran las funciones de agregado SqlClient.</span><span class="sxs-lookup"><span data-stu-id="d69b1-107">The following are the SqlClient aggregate functions.</span></span>  

## <a name="avgexpression"></a><span data-ttu-id="d69b1-108">AVG(expresión)</span><span class="sxs-lookup"><span data-stu-id="d69b1-108">AVG(expression)</span></span>

<span data-ttu-id="d69b1-109">Devuelve el promedio de los valores de una colección.</span><span class="sxs-lookup"><span data-stu-id="d69b1-109">Returns the average of the values in a collection.</span></span> <span data-ttu-id="d69b1-110">Se omiten los valores NULL.</span><span class="sxs-lookup"><span data-stu-id="d69b1-110">Null values are ignored.</span></span>

<span data-ttu-id="d69b1-111">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="d69b1-111">**Arguments**</span></span>

<span data-ttu-id="d69b1-112">Un `Int32` `Int64`, `Double`, `Decimal`, y .</span><span class="sxs-lookup"><span data-stu-id="d69b1-112">An `Int32`, `Int64`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="d69b1-113">**Valor de devolución**</span><span class="sxs-lookup"><span data-stu-id="d69b1-113">**Return Value**</span></span>

<span data-ttu-id="d69b1-114">Tipo de `expression`.</span><span class="sxs-lookup"><span data-stu-id="d69b1-114">The type of `expression`.</span></span>

<span data-ttu-id="d69b1-115">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="d69b1-115">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksum_aggcollection"></a><span data-ttu-id="d69b1-116">CHECKSUM_AGG (colección)</span><span class="sxs-lookup"><span data-stu-id="d69b1-116">CHECKSUM_AGG(collection)</span></span>

 <span data-ttu-id="d69b1-117">Devuelve la suma de comprobación de los valores de una colección.</span><span class="sxs-lookup"><span data-stu-id="d69b1-117">Returns the checksum of the values in a collection.</span></span> <span data-ttu-id="d69b1-118">Se omiten los valores NULL.</span><span class="sxs-lookup"><span data-stu-id="d69b1-118">Null values are ignored.</span></span>

 <span data-ttu-id="d69b1-119">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="d69b1-119">**Arguments**</span></span>

 <span data-ttu-id="d69b1-120">A Collection(`Int32`).</span><span class="sxs-lookup"><span data-stu-id="d69b1-120">A Collection(`Int32`).</span></span>

 <span data-ttu-id="d69b1-121">**Valor de devolución**</span><span class="sxs-lookup"><span data-stu-id="d69b1-121">**Return Value**</span></span>

 <span data-ttu-id="d69b1-122">Un valor de tipo `Int32`.</span><span class="sxs-lookup"><span data-stu-id="d69b1-122">An `Int32`.</span></span>

 <span data-ttu-id="d69b1-123">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="d69b1-123">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]

## <a name="countexpression"></a><span data-ttu-id="d69b1-124">COUNT(expresión)</span><span class="sxs-lookup"><span data-stu-id="d69b1-124">COUNT(expression)</span></span>

<span data-ttu-id="d69b1-125">Devuelve el número de elementos de una colección como un valor `Int32`.</span><span class="sxs-lookup"><span data-stu-id="d69b1-125">Returns the number of items in a collection as an `Int32`.</span></span>

<span data-ttu-id="d69b1-126">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="d69b1-126">**Arguments**</span></span>

<span data-ttu-id="d69b1-127">Un\<T de colección>, donde T es uno de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="d69b1-127">A Collection\<T>, where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="d69b1-128">`Guid`(no devuelto en SQL Server 2000)</span><span class="sxs-lookup"><span data-stu-id="d69b1-128">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="d69b1-129">**Valor de devolución**</span><span class="sxs-lookup"><span data-stu-id="d69b1-129">**Return Value**</span></span>

<span data-ttu-id="d69b1-130">Un valor de tipo `Int32`.</span><span class="sxs-lookup"><span data-stu-id="d69b1-130">An `Int32`.</span></span>

<span data-ttu-id="d69b1-131">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="d69b1-131">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)]

## <a name="count_bigexpression"></a><span data-ttu-id="d69b1-132">COUNT_BIG(expresión)</span><span class="sxs-lookup"><span data-stu-id="d69b1-132">COUNT_BIG(expression)</span></span>

<span data-ttu-id="d69b1-133">Devuelve el número de elementos de una colección como un valor `bigint`.</span><span class="sxs-lookup"><span data-stu-id="d69b1-133">Returns the number of items in a collection as a `bigint`.</span></span>

 <span data-ttu-id="d69b1-134">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="d69b1-134">**Arguments**</span></span>

 <span data-ttu-id="d69b1-135">Una colección(T), donde T es uno de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="d69b1-135">A Collection(T), where T is one of the following types:</span></span>

 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="d69b1-136">`Guid`(no devuelto en SQL Server 2000)</span><span class="sxs-lookup"><span data-stu-id="d69b1-136">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="d69b1-137">**Valor de devolución**</span><span class="sxs-lookup"><span data-stu-id="d69b1-137">**Return Value**</span></span>

<span data-ttu-id="d69b1-138">Un valor de tipo `Int64`.</span><span class="sxs-lookup"><span data-stu-id="d69b1-138">An `Int64`.</span></span>

<span data-ttu-id="d69b1-139">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="d69b1-139">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a><span data-ttu-id="d69b1-140">MAX(expresión)</span><span class="sxs-lookup"><span data-stu-id="d69b1-140">MAX(expression)</span></span>

<span data-ttu-id="d69b1-141">Devuelve el valor máximo de la colección.</span><span class="sxs-lookup"><span data-stu-id="d69b1-141">Returns the maximum value the collection.</span></span>

<span data-ttu-id="d69b1-142">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="d69b1-142">**Arguments**</span></span>

<span data-ttu-id="d69b1-143">Una colección(T), donde T es uno de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="d69b1-143">A Collection(T), where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="d69b1-144">**Valor de devolución**</span><span class="sxs-lookup"><span data-stu-id="d69b1-144">**Return Value**</span></span>

<span data-ttu-id="d69b1-145">Tipo de `expression`.</span><span class="sxs-lookup"><span data-stu-id="d69b1-145">The type of `expression`.</span></span>

<span data-ttu-id="d69b1-146">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="d69b1-146">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a><span data-ttu-id="d69b1-147">MIN(expresión)</span><span class="sxs-lookup"><span data-stu-id="d69b1-147">MIN(expression)</span></span>

<span data-ttu-id="d69b1-148">Devuelve el valor mínimo de una colección.</span><span class="sxs-lookup"><span data-stu-id="d69b1-148">Returns the minimum value in a collection.</span></span>

<span data-ttu-id="d69b1-149">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="d69b1-149">**Arguments**</span></span>

<span data-ttu-id="d69b1-150">Una colección(T), donde T es uno de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="d69b1-150">A Collection(T), where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="d69b1-151">**Valor de devolución**</span><span class="sxs-lookup"><span data-stu-id="d69b1-151">**Return Value**</span></span>

<span data-ttu-id="d69b1-152">Tipo de `expression`.</span><span class="sxs-lookup"><span data-stu-id="d69b1-152">The type of `expression`.</span></span>

<span data-ttu-id="d69b1-153">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="d69b1-153">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a><span data-ttu-id="d69b1-154">STDEV(expresión)</span><span class="sxs-lookup"><span data-stu-id="d69b1-154">STDEV(expression)</span></span>

<span data-ttu-id="d69b1-155">Devuelve la desviación típica estadística de todos los valores de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="d69b1-155">Returns the statistical standard deviation of all values in the specified expression.</span></span>

<span data-ttu-id="d69b1-156">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="d69b1-156">**Arguments**</span></span>

<span data-ttu-id="d69b1-157">A Collection(`Double`).</span><span class="sxs-lookup"><span data-stu-id="d69b1-157">A Collection(`Double`).</span></span>

<span data-ttu-id="d69b1-158">**Valor de devolución**</span><span class="sxs-lookup"><span data-stu-id="d69b1-158">**Return Value**</span></span>

<span data-ttu-id="d69b1-159">`Double`.</span><span class="sxs-lookup"><span data-stu-id="d69b1-159">A `Double`.</span></span>

<span data-ttu-id="d69b1-160">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="d69b1-160">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a><span data-ttu-id="d69b1-161">STDEVP(expresión)</span><span class="sxs-lookup"><span data-stu-id="d69b1-161">STDEVP(expression)</span></span>

<span data-ttu-id="d69b1-162">Devuelve la desviación estadística estándar para la población de todos los valores de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="d69b1-162">Returns the statistical standard deviation for the population for all values in the specified expression.</span></span>

<span data-ttu-id="d69b1-163">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="d69b1-163">**Arguments**</span></span>

<span data-ttu-id="d69b1-164">A Collection(`Double`).</span><span class="sxs-lookup"><span data-stu-id="d69b1-164">A Collection(`Double`).</span></span>

<span data-ttu-id="d69b1-165">**Valor de devolución**</span><span class="sxs-lookup"><span data-stu-id="d69b1-165">**Return Value**</span></span>

<span data-ttu-id="d69b1-166">`Double`.</span><span class="sxs-lookup"><span data-stu-id="d69b1-166">A `Double`.</span></span>

<span data-ttu-id="d69b1-167">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="d69b1-167">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a><span data-ttu-id="d69b1-168">SUM(expresión)</span><span class="sxs-lookup"><span data-stu-id="d69b1-168">SUM(expression)</span></span>

<span data-ttu-id="d69b1-169">Devuelve la suma de todos los valores de la colección.</span><span class="sxs-lookup"><span data-stu-id="d69b1-169">Returns the sum of all the values in the collection.</span></span>

<span data-ttu-id="d69b1-170">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="d69b1-170">**Arguments**</span></span>

<span data-ttu-id="d69b1-171">Una colección(T) donde T es `Int32`uno `Int64` `Double`de `Decimal`los siguientes tipos: , , , .</span><span class="sxs-lookup"><span data-stu-id="d69b1-171">A Collection(T) where T is one of the following types: `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="d69b1-172">**Valor de devolución**</span><span class="sxs-lookup"><span data-stu-id="d69b1-172">**Return Value**</span></span>

<span data-ttu-id="d69b1-173">Tipo de `expression`.</span><span class="sxs-lookup"><span data-stu-id="d69b1-173">The type of `expression`.</span></span>

<span data-ttu-id="d69b1-174">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="d69b1-174">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a><span data-ttu-id="d69b1-175">VAR(expresión)</span><span class="sxs-lookup"><span data-stu-id="d69b1-175">VAR(expression)</span></span>

<span data-ttu-id="d69b1-176">Devuelve la varianza estadística de todos los valores de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="d69b1-176">Returns the statistical variance of all values in the specified expression.</span></span>

<span data-ttu-id="d69b1-177">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="d69b1-177">**Arguments**</span></span>

<span data-ttu-id="d69b1-178">A Collection(`Double`).</span><span class="sxs-lookup"><span data-stu-id="d69b1-178">A Collection(`Double`).</span></span>

<span data-ttu-id="d69b1-179">**Valor de devolución**</span><span class="sxs-lookup"><span data-stu-id="d69b1-179">**Return Value**</span></span>

<span data-ttu-id="d69b1-180">`Double`.</span><span class="sxs-lookup"><span data-stu-id="d69b1-180">A `Double`.</span></span>

<span data-ttu-id="d69b1-181">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="d69b1-181">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a><span data-ttu-id="d69b1-182">VARP(expresión)</span><span class="sxs-lookup"><span data-stu-id="d69b1-182">VARP(expression)</span></span>

<span data-ttu-id="d69b1-183">Devuelve la varianza estadística de la población para todos los valores de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="d69b1-183">Returns the statistical variance for the population for all values in the specified expression.</span></span>

<span data-ttu-id="d69b1-184">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="d69b1-184">**Arguments**</span></span>

<span data-ttu-id="d69b1-185">A Collection(`Double`).</span><span class="sxs-lookup"><span data-stu-id="d69b1-185">A Collection(`Double`).</span></span>

<span data-ttu-id="d69b1-186">**Valor de devolución**</span><span class="sxs-lookup"><span data-stu-id="d69b1-186">**Return Value**</span></span>

<span data-ttu-id="d69b1-187">`Double`.</span><span class="sxs-lookup"><span data-stu-id="d69b1-187">A `Double`.</span></span>

<span data-ttu-id="d69b1-188">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="d69b1-188">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)]
  
## <a name="see-also"></a><span data-ttu-id="d69b1-189">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d69b1-189">See also</span></span>

- [<span data-ttu-id="d69b1-190">Funciones de agregado (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="d69b1-190">Aggregate Functions (Transact-SQL)</span></span>](/sql/t-sql/functions/aggregate-functions-transact-sql)
- [<span data-ttu-id="d69b1-191">Lenguaje Entity SQL</span><span class="sxs-lookup"><span data-stu-id="d69b1-191">Entity SQL Language</span></span>](./language-reference/entity-sql-language.md)
- [<span data-ttu-id="d69b1-192">Funciones canónicas de agregado</span><span class="sxs-lookup"><span data-stu-id="d69b1-192">Aggregate Canonical Functions</span></span>](./language-reference/aggregate-canonical-functions.md)
