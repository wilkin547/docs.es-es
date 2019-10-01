---
title: Funciones de agregado (SqlClient para Entity Framework)
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: 3dbd4c0a24a5fc41153ea16747325e824669b0e5
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700055"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a><span data-ttu-id="44790-102">Funciones de agregado (SqlClient para Entity Framework)</span><span class="sxs-lookup"><span data-stu-id="44790-102">Aggregate Functions (SqlClient for Entity Framework)</span></span>
<span data-ttu-id="44790-103">El Proveedor de datos .NET Framework para SQL Server (SqlClient) proporciona funciones de agregado.</span><span class="sxs-lookup"><span data-stu-id="44790-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides aggregate functions.</span></span> <span data-ttu-id="44790-104">Las funciones de agregado realizan cálculos en un conjunto de valores de entrada y devuelven un valor.</span><span class="sxs-lookup"><span data-stu-id="44790-104">Aggregate functions perform calculations on a set of input values and return a value.</span></span> <span data-ttu-id="44790-105">Estas funciones están en el espacio de nombres SqlServer, que está disponible al utilizar SqlClient.</span><span class="sxs-lookup"><span data-stu-id="44790-105">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="44790-106">La propiedad del espacio de nombres de un proveedor permite a Entity Framework detectar qué prefijo usa este proveedor para estructuras concretas, como tipos y funciones.</span><span class="sxs-lookup"><span data-stu-id="44790-106">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span>  
  
 <span data-ttu-id="44790-107">A continuación se enumeran las funciones de agregado SqlClient.</span><span class="sxs-lookup"><span data-stu-id="44790-107">The following are the SqlClient aggregate functions.</span></span>  

## <a name="avgexpression"></a><span data-ttu-id="44790-108">AVG (expresión)</span><span class="sxs-lookup"><span data-stu-id="44790-108">AVG(expression)</span></span>

<span data-ttu-id="44790-109">Devuelve el promedio de los valores de una colección.</span><span class="sxs-lookup"><span data-stu-id="44790-109">Returns the average of the values in a collection.</span></span> <span data-ttu-id="44790-110">Los valores Null se pasan por alto.</span><span class="sxs-lookup"><span data-stu-id="44790-110">Null values are ignored.</span></span>

<span data-ttu-id="44790-111">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="44790-111">**Arguments**</span></span>

<span data-ttu-id="44790-112">@No__t-0, `Int64`, `Double` y `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="44790-112">An `Int32`, `Int64`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="44790-113">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="44790-113">**Return Value**</span></span>

<span data-ttu-id="44790-114">Tipo de `expression`.</span><span class="sxs-lookup"><span data-stu-id="44790-114">The type of `expression`.</span></span>

<span data-ttu-id="44790-115">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="44790-115">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksum_aggcollection"></a><span data-ttu-id="44790-116">CHECKSUM_AGG (colección)</span><span class="sxs-lookup"><span data-stu-id="44790-116">CHECKSUM_AGG(collection)</span></span>
 
 <span data-ttu-id="44790-117">Devuelve la suma de comprobación de los valores de una colección.</span><span class="sxs-lookup"><span data-stu-id="44790-117">Returns the checksum of the values in a collection.</span></span> <span data-ttu-id="44790-118">Los valores Null se pasan por alto.</span><span class="sxs-lookup"><span data-stu-id="44790-118">Null values are ignored.</span></span>
 
 <span data-ttu-id="44790-119">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="44790-119">**Arguments**</span></span>
 
 <span data-ttu-id="44790-120">Colección (`Int32`).</span><span class="sxs-lookup"><span data-stu-id="44790-120">A Collection(`Int32`).</span></span>
 
 <span data-ttu-id="44790-121">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="44790-121">**Return Value**</span></span>
 
 <span data-ttu-id="44790-122">Una clase `Int32`.</span><span class="sxs-lookup"><span data-stu-id="44790-122">An `Int32`.</span></span>
 
 <span data-ttu-id="44790-123">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="44790-123">**Example**</span></span>
 
[!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]
   
## <a name="countexpression"></a><span data-ttu-id="44790-124">COUNT (expresión)</span><span class="sxs-lookup"><span data-stu-id="44790-124">COUNT(expression)</span></span>

<span data-ttu-id="44790-125">Devuelve el número de elementos de una colección como un valor `Int32`.</span><span class="sxs-lookup"><span data-stu-id="44790-125">Returns the number of items in a collection as an `Int32`.</span></span>

<span data-ttu-id="44790-126">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="44790-126">**Arguments**</span></span>

<span data-ttu-id="44790-127">Una colección @ no__t-0T >, donde T es uno de los tipos siguientes:</span><span class="sxs-lookup"><span data-stu-id="44790-127">A Collection\<T>, where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="44790-128">`Guid` (no se devuelve en SQL Server 2000)</span><span class="sxs-lookup"><span data-stu-id="44790-128">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="44790-129">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="44790-129">**Return Value**</span></span>

<span data-ttu-id="44790-130">Una clase `Int32`.</span><span class="sxs-lookup"><span data-stu-id="44790-130">An `Int32`.</span></span>

<span data-ttu-id="44790-131">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="44790-131">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)]
 
## <a name="count_bigexpression"></a><span data-ttu-id="44790-132">COUNT_BIG (expresión)</span><span class="sxs-lookup"><span data-stu-id="44790-132">COUNT_BIG(expression)</span></span>
 
<span data-ttu-id="44790-133">Devuelve el número de elementos de una colección como un valor `bigint`.</span><span class="sxs-lookup"><span data-stu-id="44790-133">Returns the number of items in a collection as a `bigint`.</span></span>
 
 <span data-ttu-id="44790-134">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="44790-134">**Arguments**</span></span>
 
 <span data-ttu-id="44790-135">Colección (T), donde T es uno de los tipos siguientes:</span><span class="sxs-lookup"><span data-stu-id="44790-135">A Collection(T), where T is one of the following types:</span></span>
 
 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="44790-136">`Guid` (no se devuelve en SQL Server 2000)</span><span class="sxs-lookup"><span data-stu-id="44790-136">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="44790-137">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="44790-137">**Return Value**</span></span>

<span data-ttu-id="44790-138">Una clase `Int64`.</span><span class="sxs-lookup"><span data-stu-id="44790-138">An `Int64`.</span></span>

<span data-ttu-id="44790-139">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="44790-139">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a><span data-ttu-id="44790-140">MAX (expresión)</span><span class="sxs-lookup"><span data-stu-id="44790-140">MAX(expression)</span></span>

<span data-ttu-id="44790-141">Devuelve el valor máximo de la colección.</span><span class="sxs-lookup"><span data-stu-id="44790-141">Returns the maximum value the collection.</span></span>

<span data-ttu-id="44790-142">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="44790-142">**Arguments**</span></span>

<span data-ttu-id="44790-143">Colección (T), donde T es uno de los tipos siguientes:</span><span class="sxs-lookup"><span data-stu-id="44790-143">A Collection(T), where T is one of the following types:</span></span> 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="44790-144">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="44790-144">**Return Value**</span></span>

<span data-ttu-id="44790-145">Tipo de `expression`.</span><span class="sxs-lookup"><span data-stu-id="44790-145">The type of `expression`.</span></span>

<span data-ttu-id="44790-146">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="44790-146">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a><span data-ttu-id="44790-147">MIN (expresión)</span><span class="sxs-lookup"><span data-stu-id="44790-147">MIN(expression)</span></span>

<span data-ttu-id="44790-148">Devuelve el valor mínimo de una colección.</span><span class="sxs-lookup"><span data-stu-id="44790-148">Returns the minimum value in a collection.</span></span>

<span data-ttu-id="44790-149">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="44790-149">**Arguments**</span></span>

<span data-ttu-id="44790-150">Colección (T), donde T es uno de los tipos siguientes:</span><span class="sxs-lookup"><span data-stu-id="44790-150">A Collection(T), where T is one of the following types:</span></span> 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="44790-151">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="44790-151">**Return Value**</span></span>

<span data-ttu-id="44790-152">Tipo de `expression`.</span><span class="sxs-lookup"><span data-stu-id="44790-152">The type of `expression`.</span></span>

<span data-ttu-id="44790-153">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="44790-153">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a><span data-ttu-id="44790-154">STDEV (expresión)</span><span class="sxs-lookup"><span data-stu-id="44790-154">STDEV(expression)</span></span>

<span data-ttu-id="44790-155">Devuelve la desviación estándar estadística de todos los valores de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="44790-155">Returns the statistical standard deviation of all values in the specified expression.</span></span>

<span data-ttu-id="44790-156">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="44790-156">**Arguments**</span></span>

<span data-ttu-id="44790-157">Colección (`Double`).</span><span class="sxs-lookup"><span data-stu-id="44790-157">A Collection(`Double`).</span></span>

<span data-ttu-id="44790-158">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="44790-158">**Return Value**</span></span>

<span data-ttu-id="44790-159">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="44790-159">A `Double`.</span></span>

<span data-ttu-id="44790-160">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="44790-160">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a><span data-ttu-id="44790-161">STDEVP (expresión)</span><span class="sxs-lookup"><span data-stu-id="44790-161">STDEVP(expression)</span></span>

<span data-ttu-id="44790-162">Devuelve la desviación estándar estadística de la población para todos los valores de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="44790-162">Returns the statistical standard deviation for the population for all values in the specified expression.</span></span>

<span data-ttu-id="44790-163">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="44790-163">**Arguments**</span></span>

<span data-ttu-id="44790-164">Colección (`Double`).</span><span class="sxs-lookup"><span data-stu-id="44790-164">A Collection(`Double`).</span></span>

<span data-ttu-id="44790-165">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="44790-165">**Return Value**</span></span>

<span data-ttu-id="44790-166">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="44790-166">A `Double`.</span></span>

<span data-ttu-id="44790-167">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="44790-167">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a><span data-ttu-id="44790-168">SUM (expresión)</span><span class="sxs-lookup"><span data-stu-id="44790-168">SUM(expression)</span></span>

<span data-ttu-id="44790-169">Devuelve la suma de todos los valores de la colección.</span><span class="sxs-lookup"><span data-stu-id="44790-169">Returns the sum of all the values in the collection.</span></span>

<span data-ttu-id="44790-170">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="44790-170">**Arguments**</span></span>

<span data-ttu-id="44790-171">Colección (T), donde T es uno de los tipos siguientes: `Int32`, `Int64`, `Double`, `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="44790-171">A Collection(T) where T is one of the following types: `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="44790-172">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="44790-172">**Return Value**</span></span>

<span data-ttu-id="44790-173">Tipo de `expression`.</span><span class="sxs-lookup"><span data-stu-id="44790-173">The type of `expression`.</span></span>

<span data-ttu-id="44790-174">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="44790-174">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a><span data-ttu-id="44790-175">VAR (expresión)</span><span class="sxs-lookup"><span data-stu-id="44790-175">VAR(expression)</span></span>

<span data-ttu-id="44790-176">Devuelve la varianza estadística de todos los valores de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="44790-176">Returns the statistical variance of all values in the specified expression.</span></span>

<span data-ttu-id="44790-177">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="44790-177">**Arguments**</span></span>

<span data-ttu-id="44790-178">Colección (`Double`).</span><span class="sxs-lookup"><span data-stu-id="44790-178">A Collection(`Double`).</span></span>

<span data-ttu-id="44790-179">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="44790-179">**Return Value**</span></span>

<span data-ttu-id="44790-180">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="44790-180">A `Double`.</span></span>

<span data-ttu-id="44790-181">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="44790-181">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a><span data-ttu-id="44790-182">VARP (expresión)</span><span class="sxs-lookup"><span data-stu-id="44790-182">VARP(expression)</span></span>

<span data-ttu-id="44790-183">Devuelve la varianza estadística de la población para todos los valores de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="44790-183">Returns the statistical variance for the population for all values in the specified expression.</span></span>

<span data-ttu-id="44790-184">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="44790-184">**Arguments**</span></span>

<span data-ttu-id="44790-185">Colección (`Double`).</span><span class="sxs-lookup"><span data-stu-id="44790-185">A Collection(`Double`).</span></span>

<span data-ttu-id="44790-186">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="44790-186">**Return Value**</span></span>

<span data-ttu-id="44790-187">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="44790-187">A `Double`.</span></span>

<span data-ttu-id="44790-188">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="44790-188">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)] 
  
## <a name="see-also"></a><span data-ttu-id="44790-189">Vea también</span><span class="sxs-lookup"><span data-stu-id="44790-189">See also</span></span>

- [<span data-ttu-id="44790-190">Funciones de agregado (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="44790-190">Aggregate Functions (Transact-SQL)</span></span>](/sql/t-sql/functions/aggregate-functions-transact-sql)
- [<span data-ttu-id="44790-191">Lenguaje Entity SQL</span><span class="sxs-lookup"><span data-stu-id="44790-191">Entity SQL Language</span></span>](./language-reference/entity-sql-language.md)
- [<span data-ttu-id="44790-192">Funciones canónicas de agregado</span><span class="sxs-lookup"><span data-stu-id="44790-192">Aggregate Canonical Functions</span></span>](./language-reference/aggregate-canonical-functions.md)
