---
title: Funciones de agregado (SqlClient para Entity Framework)
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: 1c32ccfe18c67c9baeb7df0f981c9129b3bbc8bb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204520"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a><span data-ttu-id="efb7d-102">Funciones de agregado (SqlClient para Entity Framework)</span><span class="sxs-lookup"><span data-stu-id="efb7d-102">Aggregate Functions (SqlClient for Entity Framework)</span></span>

<span data-ttu-id="efb7d-103">El Proveedor de datos .NET Framework para SQL Server (SqlClient) proporciona funciones de agregado.</span><span class="sxs-lookup"><span data-stu-id="efb7d-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides aggregate functions.</span></span> <span data-ttu-id="efb7d-104">Las funciones de agregado realizan cálculos en un conjunto de valores de entrada y devuelven un valor.</span><span class="sxs-lookup"><span data-stu-id="efb7d-104">Aggregate functions perform calculations on a set of input values and return a value.</span></span> <span data-ttu-id="efb7d-105">Estas funciones están en el espacio de nombres SqlServer, que está disponible al utilizar SqlClient.</span><span class="sxs-lookup"><span data-stu-id="efb7d-105">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="efb7d-106">La propiedad del espacio de nombres de un proveedor permite a Entity Framework detectar qué prefijo usa este proveedor para estructuras concretas, como tipos y funciones.</span><span class="sxs-lookup"><span data-stu-id="efb7d-106">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span>  
  
 <span data-ttu-id="efb7d-107">A continuación se enumeran las funciones de agregado SqlClient.</span><span class="sxs-lookup"><span data-stu-id="efb7d-107">The following are the SqlClient aggregate functions.</span></span>  

## <a name="avgexpression"></a><span data-ttu-id="efb7d-108">AVG (expresión)</span><span class="sxs-lookup"><span data-stu-id="efb7d-108">AVG(expression)</span></span>

<span data-ttu-id="efb7d-109">Devuelve el promedio de los valores de una colección.</span><span class="sxs-lookup"><span data-stu-id="efb7d-109">Returns the average of the values in a collection.</span></span> <span data-ttu-id="efb7d-110">Se omiten los valores NULL.</span><span class="sxs-lookup"><span data-stu-id="efb7d-110">Null values are ignored.</span></span>

<span data-ttu-id="efb7d-111">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="efb7d-111">**Arguments**</span></span>

<span data-ttu-id="efb7d-112">`Int32`,, `Int64` `Double` Y `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="efb7d-112">An `Int32`, `Int64`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="efb7d-113">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="efb7d-113">**Return Value**</span></span>

<span data-ttu-id="efb7d-114">Tipo de `expression`.</span><span class="sxs-lookup"><span data-stu-id="efb7d-114">The type of `expression`.</span></span>

<span data-ttu-id="efb7d-115">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="efb7d-115">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksum_aggcollection"></a><span data-ttu-id="efb7d-116">CHECKSUM_AGG (colección)</span><span class="sxs-lookup"><span data-stu-id="efb7d-116">CHECKSUM_AGG(collection)</span></span>

 <span data-ttu-id="efb7d-117">Devuelve la suma de comprobación de los valores de una colección.</span><span class="sxs-lookup"><span data-stu-id="efb7d-117">Returns the checksum of the values in a collection.</span></span> <span data-ttu-id="efb7d-118">Se omiten los valores NULL.</span><span class="sxs-lookup"><span data-stu-id="efb7d-118">Null values are ignored.</span></span>

 <span data-ttu-id="efb7d-119">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="efb7d-119">**Arguments**</span></span>

 <span data-ttu-id="efb7d-120">Colección ( `Int32` ).</span><span class="sxs-lookup"><span data-stu-id="efb7d-120">A Collection(`Int32`).</span></span>

 <span data-ttu-id="efb7d-121">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="efb7d-121">**Return Value**</span></span>

 <span data-ttu-id="efb7d-122">Una clase `Int32`.</span><span class="sxs-lookup"><span data-stu-id="efb7d-122">An `Int32`.</span></span>

 <span data-ttu-id="efb7d-123">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="efb7d-123">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]

## <a name="countexpression"></a><span data-ttu-id="efb7d-124">COUNT(expression)</span><span class="sxs-lookup"><span data-stu-id="efb7d-124">COUNT(expression)</span></span>

<span data-ttu-id="efb7d-125">Devuelve el número de elementos de una colección como un valor `Int32`.</span><span class="sxs-lookup"><span data-stu-id="efb7d-125">Returns the number of items in a collection as an `Int32`.</span></span>

<span data-ttu-id="efb7d-126">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="efb7d-126">**Arguments**</span></span>

<span data-ttu-id="efb7d-127">Una colección \<T> , donde T es uno de los tipos siguientes:</span><span class="sxs-lookup"><span data-stu-id="efb7d-127">A Collection\<T>, where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="efb7d-128">`Guid` (no se devuelve en SQL Server 2000)</span><span class="sxs-lookup"><span data-stu-id="efb7d-128">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="efb7d-129">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="efb7d-129">**Return Value**</span></span>

<span data-ttu-id="efb7d-130">Una clase `Int32`.</span><span class="sxs-lookup"><span data-stu-id="efb7d-130">An `Int32`.</span></span>

<span data-ttu-id="efb7d-131">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="efb7d-131">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)]

## <a name="count_bigexpression"></a><span data-ttu-id="efb7d-132">COUNT_BIG (expresión)</span><span class="sxs-lookup"><span data-stu-id="efb7d-132">COUNT_BIG(expression)</span></span>

<span data-ttu-id="efb7d-133">Devuelve el número de elementos de una colección como un valor `bigint`.</span><span class="sxs-lookup"><span data-stu-id="efb7d-133">Returns the number of items in a collection as a `bigint`.</span></span>

 <span data-ttu-id="efb7d-134">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="efb7d-134">**Arguments**</span></span>

 <span data-ttu-id="efb7d-135">Colección (T), donde T es uno de los tipos siguientes:</span><span class="sxs-lookup"><span data-stu-id="efb7d-135">A Collection(T), where T is one of the following types:</span></span>

 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="efb7d-136">`Guid` (no se devuelve en SQL Server 2000)</span><span class="sxs-lookup"><span data-stu-id="efb7d-136">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="efb7d-137">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="efb7d-137">**Return Value**</span></span>

<span data-ttu-id="efb7d-138">Una clase `Int64`.</span><span class="sxs-lookup"><span data-stu-id="efb7d-138">An `Int64`.</span></span>

<span data-ttu-id="efb7d-139">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="efb7d-139">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a><span data-ttu-id="efb7d-140">MAX(expression)</span><span class="sxs-lookup"><span data-stu-id="efb7d-140">MAX(expression)</span></span>

<span data-ttu-id="efb7d-141">Devuelve el valor máximo de la colección.</span><span class="sxs-lookup"><span data-stu-id="efb7d-141">Returns the maximum value the collection.</span></span>

<span data-ttu-id="efb7d-142">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="efb7d-142">**Arguments**</span></span>

<span data-ttu-id="efb7d-143">Colección (T), donde T es uno de los tipos siguientes:</span><span class="sxs-lookup"><span data-stu-id="efb7d-143">A Collection(T), where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="efb7d-144">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="efb7d-144">**Return Value**</span></span>

<span data-ttu-id="efb7d-145">Tipo de `expression`.</span><span class="sxs-lookup"><span data-stu-id="efb7d-145">The type of `expression`.</span></span>

<span data-ttu-id="efb7d-146">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="efb7d-146">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a><span data-ttu-id="efb7d-147">MIN(expression)</span><span class="sxs-lookup"><span data-stu-id="efb7d-147">MIN(expression)</span></span>

<span data-ttu-id="efb7d-148">Devuelve el valor mínimo de una colección.</span><span class="sxs-lookup"><span data-stu-id="efb7d-148">Returns the minimum value in a collection.</span></span>

<span data-ttu-id="efb7d-149">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="efb7d-149">**Arguments**</span></span>

<span data-ttu-id="efb7d-150">Colección (T), donde T es uno de los tipos siguientes:</span><span class="sxs-lookup"><span data-stu-id="efb7d-150">A Collection(T), where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="efb7d-151">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="efb7d-151">**Return Value**</span></span>

<span data-ttu-id="efb7d-152">Tipo de `expression`.</span><span class="sxs-lookup"><span data-stu-id="efb7d-152">The type of `expression`.</span></span>

<span data-ttu-id="efb7d-153">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="efb7d-153">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a><span data-ttu-id="efb7d-154">STDEV (expresión)</span><span class="sxs-lookup"><span data-stu-id="efb7d-154">STDEV(expression)</span></span>

<span data-ttu-id="efb7d-155">Devuelve la desviación típica estadística de todos los valores de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="efb7d-155">Returns the statistical standard deviation of all values in the specified expression.</span></span>

<span data-ttu-id="efb7d-156">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="efb7d-156">**Arguments**</span></span>

<span data-ttu-id="efb7d-157">Colección ( `Double` ).</span><span class="sxs-lookup"><span data-stu-id="efb7d-157">A Collection(`Double`).</span></span>

<span data-ttu-id="efb7d-158">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="efb7d-158">**Return Value**</span></span>

<span data-ttu-id="efb7d-159">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="efb7d-159">A `Double`.</span></span>

<span data-ttu-id="efb7d-160">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="efb7d-160">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a><span data-ttu-id="efb7d-161">STDEVP (expresión)</span><span class="sxs-lookup"><span data-stu-id="efb7d-161">STDEVP(expression)</span></span>

<span data-ttu-id="efb7d-162">Devuelve la desviación estadística estándar para la población de todos los valores de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="efb7d-162">Returns the statistical standard deviation for the population for all values in the specified expression.</span></span>

<span data-ttu-id="efb7d-163">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="efb7d-163">**Arguments**</span></span>

<span data-ttu-id="efb7d-164">Colección ( `Double` ).</span><span class="sxs-lookup"><span data-stu-id="efb7d-164">A Collection(`Double`).</span></span>

<span data-ttu-id="efb7d-165">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="efb7d-165">**Return Value**</span></span>

<span data-ttu-id="efb7d-166">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="efb7d-166">A `Double`.</span></span>

<span data-ttu-id="efb7d-167">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="efb7d-167">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a><span data-ttu-id="efb7d-168">SUM(expression)</span><span class="sxs-lookup"><span data-stu-id="efb7d-168">SUM(expression)</span></span>

<span data-ttu-id="efb7d-169">Devuelve la suma de todos los valores de la colección.</span><span class="sxs-lookup"><span data-stu-id="efb7d-169">Returns the sum of all the values in the collection.</span></span>

<span data-ttu-id="efb7d-170">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="efb7d-170">**Arguments**</span></span>

<span data-ttu-id="efb7d-171">Colección (T), donde T es uno de los tipos siguientes: `Int32` , `Int64` , `Double` , `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="efb7d-171">A Collection(T) where T is one of the following types: `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="efb7d-172">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="efb7d-172">**Return Value**</span></span>

<span data-ttu-id="efb7d-173">Tipo de `expression`.</span><span class="sxs-lookup"><span data-stu-id="efb7d-173">The type of `expression`.</span></span>

<span data-ttu-id="efb7d-174">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="efb7d-174">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a><span data-ttu-id="efb7d-175">VAR (expresión)</span><span class="sxs-lookup"><span data-stu-id="efb7d-175">VAR(expression)</span></span>

<span data-ttu-id="efb7d-176">Devuelve la varianza estadística de todos los valores de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="efb7d-176">Returns the statistical variance of all values in the specified expression.</span></span>

<span data-ttu-id="efb7d-177">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="efb7d-177">**Arguments**</span></span>

<span data-ttu-id="efb7d-178">Colección ( `Double` ).</span><span class="sxs-lookup"><span data-stu-id="efb7d-178">A Collection(`Double`).</span></span>

<span data-ttu-id="efb7d-179">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="efb7d-179">**Return Value**</span></span>

<span data-ttu-id="efb7d-180">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="efb7d-180">A `Double`.</span></span>

<span data-ttu-id="efb7d-181">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="efb7d-181">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a><span data-ttu-id="efb7d-182">VARP (expresión)</span><span class="sxs-lookup"><span data-stu-id="efb7d-182">VARP(expression)</span></span>

<span data-ttu-id="efb7d-183">Devuelve la varianza estadística de la población para todos los valores de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="efb7d-183">Returns the statistical variance for the population for all values in the specified expression.</span></span>

<span data-ttu-id="efb7d-184">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="efb7d-184">**Arguments**</span></span>

<span data-ttu-id="efb7d-185">Colección ( `Double` ).</span><span class="sxs-lookup"><span data-stu-id="efb7d-185">A Collection(`Double`).</span></span>

<span data-ttu-id="efb7d-186">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="efb7d-186">**Return Value**</span></span>

<span data-ttu-id="efb7d-187">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="efb7d-187">A `Double`.</span></span>

<span data-ttu-id="efb7d-188">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="efb7d-188">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)]
  
## <a name="see-also"></a><span data-ttu-id="efb7d-189">Consulte también</span><span class="sxs-lookup"><span data-stu-id="efb7d-189">See also</span></span>

- [<span data-ttu-id="efb7d-190">Funciones de agregado (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="efb7d-190">Aggregate Functions (Transact-SQL)</span></span>](/sql/t-sql/functions/aggregate-functions-transact-sql)
- [<span data-ttu-id="efb7d-191">Lenguaje Entity SQL</span><span class="sxs-lookup"><span data-stu-id="efb7d-191">Entity SQL Language</span></span>](./language-reference/entity-sql-language.md)
- [<span data-ttu-id="efb7d-192">Funciones canónicas de agregado</span><span class="sxs-lookup"><span data-stu-id="efb7d-192">Aggregate Canonical Functions</span></span>](./language-reference/aggregate-canonical-functions.md)
