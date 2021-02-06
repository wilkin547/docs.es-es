---
description: 'Más información sobre: funciones de agregado (SqlClient para Entity Framework)'
title: Funciones de agregado (SqlClient para Entity Framework)
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: b9f1ff8c75fc09de7532b459090b0b5cd1d47262
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99651085"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a><span data-ttu-id="af819-103">Funciones de agregado (SqlClient para Entity Framework)</span><span class="sxs-lookup"><span data-stu-id="af819-103">Aggregate Functions (SqlClient for Entity Framework)</span></span>

<span data-ttu-id="af819-104">El Proveedor de datos .NET Framework para SQL Server (SqlClient) proporciona funciones de agregado.</span><span class="sxs-lookup"><span data-stu-id="af819-104">The .NET Framework Data Provider for SQL Server (SqlClient) provides aggregate functions.</span></span> <span data-ttu-id="af819-105">Las funciones de agregado realizan cálculos en un conjunto de valores de entrada y devuelven un valor.</span><span class="sxs-lookup"><span data-stu-id="af819-105">Aggregate functions perform calculations on a set of input values and return a value.</span></span> <span data-ttu-id="af819-106">Estas funciones están en el espacio de nombres SqlServer, que está disponible al utilizar SqlClient.</span><span class="sxs-lookup"><span data-stu-id="af819-106">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="af819-107">La propiedad del espacio de nombres de un proveedor permite a Entity Framework detectar qué prefijo usa este proveedor para estructuras concretas, como tipos y funciones.</span><span class="sxs-lookup"><span data-stu-id="af819-107">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span>  
  
 <span data-ttu-id="af819-108">A continuación se enumeran las funciones de agregado SqlClient.</span><span class="sxs-lookup"><span data-stu-id="af819-108">The following are the SqlClient aggregate functions.</span></span>  

## <a name="avgexpression"></a><span data-ttu-id="af819-109">AVG (expresión)</span><span class="sxs-lookup"><span data-stu-id="af819-109">AVG(expression)</span></span>

<span data-ttu-id="af819-110">Devuelve el promedio de los valores de una colección.</span><span class="sxs-lookup"><span data-stu-id="af819-110">Returns the average of the values in a collection.</span></span> <span data-ttu-id="af819-111">Se omiten los valores NULL.</span><span class="sxs-lookup"><span data-stu-id="af819-111">Null values are ignored.</span></span>

<span data-ttu-id="af819-112">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="af819-112">**Arguments**</span></span>

<span data-ttu-id="af819-113">`Int32`,, `Int64` `Double` Y `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="af819-113">An `Int32`, `Int64`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="af819-114">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="af819-114">**Return Value**</span></span>

<span data-ttu-id="af819-115">Tipo de `expression`.</span><span class="sxs-lookup"><span data-stu-id="af819-115">The type of `expression`.</span></span>

<span data-ttu-id="af819-116">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="af819-116">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksum_aggcollection"></a><span data-ttu-id="af819-117">CHECKSUM_AGG (colección)</span><span class="sxs-lookup"><span data-stu-id="af819-117">CHECKSUM_AGG(collection)</span></span>

 <span data-ttu-id="af819-118">Devuelve la suma de comprobación de los valores de una colección.</span><span class="sxs-lookup"><span data-stu-id="af819-118">Returns the checksum of the values in a collection.</span></span> <span data-ttu-id="af819-119">Se omiten los valores NULL.</span><span class="sxs-lookup"><span data-stu-id="af819-119">Null values are ignored.</span></span>

 <span data-ttu-id="af819-120">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="af819-120">**Arguments**</span></span>

 <span data-ttu-id="af819-121">Colección ( `Int32` ).</span><span class="sxs-lookup"><span data-stu-id="af819-121">A Collection(`Int32`).</span></span>

 <span data-ttu-id="af819-122">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="af819-122">**Return Value**</span></span>

 <span data-ttu-id="af819-123">Una clase `Int32`.</span><span class="sxs-lookup"><span data-stu-id="af819-123">An `Int32`.</span></span>

 <span data-ttu-id="af819-124">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="af819-124">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]

## <a name="countexpression"></a><span data-ttu-id="af819-125">COUNT(expression)</span><span class="sxs-lookup"><span data-stu-id="af819-125">COUNT(expression)</span></span>

<span data-ttu-id="af819-126">Devuelve el número de elementos de una colección como un valor `Int32`.</span><span class="sxs-lookup"><span data-stu-id="af819-126">Returns the number of items in a collection as an `Int32`.</span></span>

<span data-ttu-id="af819-127">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="af819-127">**Arguments**</span></span>

<span data-ttu-id="af819-128">Una colección \<T> , donde T es uno de los tipos siguientes:</span><span class="sxs-lookup"><span data-stu-id="af819-128">A Collection\<T>, where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="af819-129">`Guid` (no se devuelve en SQL Server 2000)</span><span class="sxs-lookup"><span data-stu-id="af819-129">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="af819-130">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="af819-130">**Return Value**</span></span>

<span data-ttu-id="af819-131">Una clase `Int32`.</span><span class="sxs-lookup"><span data-stu-id="af819-131">An `Int32`.</span></span>

<span data-ttu-id="af819-132">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="af819-132">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)]

## <a name="count_bigexpression"></a><span data-ttu-id="af819-133">COUNT_BIG (expresión)</span><span class="sxs-lookup"><span data-stu-id="af819-133">COUNT_BIG(expression)</span></span>

<span data-ttu-id="af819-134">Devuelve el número de elementos de una colección como un valor `bigint`.</span><span class="sxs-lookup"><span data-stu-id="af819-134">Returns the number of items in a collection as a `bigint`.</span></span>

 <span data-ttu-id="af819-135">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="af819-135">**Arguments**</span></span>

 <span data-ttu-id="af819-136">Colección (T), donde T es uno de los tipos siguientes:</span><span class="sxs-lookup"><span data-stu-id="af819-136">A Collection(T), where T is one of the following types:</span></span>

 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="af819-137">`Guid` (no se devuelve en SQL Server 2000)</span><span class="sxs-lookup"><span data-stu-id="af819-137">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="af819-138">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="af819-138">**Return Value**</span></span>

<span data-ttu-id="af819-139">Una clase `Int64`.</span><span class="sxs-lookup"><span data-stu-id="af819-139">An `Int64`.</span></span>

<span data-ttu-id="af819-140">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="af819-140">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a><span data-ttu-id="af819-141">MAX (expresión)</span><span class="sxs-lookup"><span data-stu-id="af819-141">MAX(expression)</span></span>

<span data-ttu-id="af819-142">Devuelve el valor máximo de la colección.</span><span class="sxs-lookup"><span data-stu-id="af819-142">Returns the maximum value the collection.</span></span>

<span data-ttu-id="af819-143">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="af819-143">**Arguments**</span></span>

<span data-ttu-id="af819-144">Colección (T), donde T es uno de los tipos siguientes:</span><span class="sxs-lookup"><span data-stu-id="af819-144">A Collection(T), where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="af819-145">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="af819-145">**Return Value**</span></span>

<span data-ttu-id="af819-146">Tipo de `expression`.</span><span class="sxs-lookup"><span data-stu-id="af819-146">The type of `expression`.</span></span>

<span data-ttu-id="af819-147">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="af819-147">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a><span data-ttu-id="af819-148">MIN(expression)</span><span class="sxs-lookup"><span data-stu-id="af819-148">MIN(expression)</span></span>

<span data-ttu-id="af819-149">Devuelve el valor mínimo de una colección.</span><span class="sxs-lookup"><span data-stu-id="af819-149">Returns the minimum value in a collection.</span></span>

<span data-ttu-id="af819-150">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="af819-150">**Arguments**</span></span>

<span data-ttu-id="af819-151">Colección (T), donde T es uno de los tipos siguientes:</span><span class="sxs-lookup"><span data-stu-id="af819-151">A Collection(T), where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="af819-152">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="af819-152">**Return Value**</span></span>

<span data-ttu-id="af819-153">Tipo de `expression`.</span><span class="sxs-lookup"><span data-stu-id="af819-153">The type of `expression`.</span></span>

<span data-ttu-id="af819-154">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="af819-154">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a><span data-ttu-id="af819-155">STDEV (expresión)</span><span class="sxs-lookup"><span data-stu-id="af819-155">STDEV(expression)</span></span>

<span data-ttu-id="af819-156">Devuelve la desviación típica estadística de todos los valores de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="af819-156">Returns the statistical standard deviation of all values in the specified expression.</span></span>

<span data-ttu-id="af819-157">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="af819-157">**Arguments**</span></span>

<span data-ttu-id="af819-158">Colección ( `Double` ).</span><span class="sxs-lookup"><span data-stu-id="af819-158">A Collection(`Double`).</span></span>

<span data-ttu-id="af819-159">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="af819-159">**Return Value**</span></span>

<span data-ttu-id="af819-160">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="af819-160">A `Double`.</span></span>

<span data-ttu-id="af819-161">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="af819-161">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a><span data-ttu-id="af819-162">STDEVP (expresión)</span><span class="sxs-lookup"><span data-stu-id="af819-162">STDEVP(expression)</span></span>

<span data-ttu-id="af819-163">Devuelve la desviación estadística estándar para la población de todos los valores de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="af819-163">Returns the statistical standard deviation for the population for all values in the specified expression.</span></span>

<span data-ttu-id="af819-164">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="af819-164">**Arguments**</span></span>

<span data-ttu-id="af819-165">Colección ( `Double` ).</span><span class="sxs-lookup"><span data-stu-id="af819-165">A Collection(`Double`).</span></span>

<span data-ttu-id="af819-166">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="af819-166">**Return Value**</span></span>

<span data-ttu-id="af819-167">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="af819-167">A `Double`.</span></span>

<span data-ttu-id="af819-168">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="af819-168">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a><span data-ttu-id="af819-169">SUM(expression)</span><span class="sxs-lookup"><span data-stu-id="af819-169">SUM(expression)</span></span>

<span data-ttu-id="af819-170">Devuelve la suma de todos los valores de la colección.</span><span class="sxs-lookup"><span data-stu-id="af819-170">Returns the sum of all the values in the collection.</span></span>

<span data-ttu-id="af819-171">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="af819-171">**Arguments**</span></span>

<span data-ttu-id="af819-172">Colección (T), donde T es uno de los tipos siguientes: `Int32` , `Int64` , `Double` , `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="af819-172">A Collection(T) where T is one of the following types: `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="af819-173">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="af819-173">**Return Value**</span></span>

<span data-ttu-id="af819-174">Tipo de `expression`.</span><span class="sxs-lookup"><span data-stu-id="af819-174">The type of `expression`.</span></span>

<span data-ttu-id="af819-175">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="af819-175">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a><span data-ttu-id="af819-176">VAR (expresión)</span><span class="sxs-lookup"><span data-stu-id="af819-176">VAR(expression)</span></span>

<span data-ttu-id="af819-177">Devuelve la varianza estadística de todos los valores de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="af819-177">Returns the statistical variance of all values in the specified expression.</span></span>

<span data-ttu-id="af819-178">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="af819-178">**Arguments**</span></span>

<span data-ttu-id="af819-179">Colección ( `Double` ).</span><span class="sxs-lookup"><span data-stu-id="af819-179">A Collection(`Double`).</span></span>

<span data-ttu-id="af819-180">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="af819-180">**Return Value**</span></span>

<span data-ttu-id="af819-181">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="af819-181">A `Double`.</span></span>

<span data-ttu-id="af819-182">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="af819-182">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a><span data-ttu-id="af819-183">VARP (expresión)</span><span class="sxs-lookup"><span data-stu-id="af819-183">VARP(expression)</span></span>

<span data-ttu-id="af819-184">Devuelve la varianza estadística de la población para todos los valores de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="af819-184">Returns the statistical variance for the population for all values in the specified expression.</span></span>

<span data-ttu-id="af819-185">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="af819-185">**Arguments**</span></span>

<span data-ttu-id="af819-186">Colección ( `Double` ).</span><span class="sxs-lookup"><span data-stu-id="af819-186">A Collection(`Double`).</span></span>

<span data-ttu-id="af819-187">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="af819-187">**Return Value**</span></span>

<span data-ttu-id="af819-188">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="af819-188">A `Double`.</span></span>

<span data-ttu-id="af819-189">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="af819-189">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)]
  
## <a name="see-also"></a><span data-ttu-id="af819-190">Vea también</span><span class="sxs-lookup"><span data-stu-id="af819-190">See also</span></span>

- [<span data-ttu-id="af819-191">Funciones de agregado (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="af819-191">Aggregate Functions (Transact-SQL)</span></span>](/sql/t-sql/functions/aggregate-functions-transact-sql)
- [<span data-ttu-id="af819-192">Lenguaje Entity SQL</span><span class="sxs-lookup"><span data-stu-id="af819-192">Entity SQL Language</span></span>](./language-reference/entity-sql-language.md)
- [<span data-ttu-id="af819-193">Funciones canónicas de agregado</span><span class="sxs-lookup"><span data-stu-id="af819-193">Aggregate Canonical Functions</span></span>](./language-reference/aggregate-canonical-functions.md)
