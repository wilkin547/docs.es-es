---
title: Funciones matemáticas
ms.date: 03/30/2017
ms.assetid: b040c7cb-156d-40f2-9152-61065b18148c
ms.openlocfilehash: 5e5658e28c7d806f7fd38f941bfa7254e7806e11
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182481"
---
# <a name="mathematical-functions"></a><span data-ttu-id="64182-102">Funciones matemáticas</span><span class="sxs-lookup"><span data-stu-id="64182-102">Mathematical Functions</span></span>

<span data-ttu-id="64182-103">El Proveedor de datos .NET Framework para SQL Server (SqlClient) proporciona funciones matemáticas que realizan cálculos con los valores de entrada que se proporcionan como argumentos y devuelven un resultado numérico.</span><span class="sxs-lookup"><span data-stu-id="64182-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides math functions that perform calculations on input values that are provided as arguments, and return a numeric value result.</span></span> <span data-ttu-id="64182-104">Estas funciones están en el espacio de nombres SqlServer, que está disponible al utilizar SqlClient.</span><span class="sxs-lookup"><span data-stu-id="64182-104">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="64182-105">La propiedad del espacio de nombres de un proveedor permite a Entity Framework detectar qué prefijo usa este proveedor para estructuras concretas, como tipos y funciones.</span><span class="sxs-lookup"><span data-stu-id="64182-105">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span> <span data-ttu-id="64182-106">En la tabla siguiente se describen las funciones matemáticas de SqlClient.</span><span class="sxs-lookup"><span data-stu-id="64182-106">The following table describes the SqlClient math functions.</span></span>  
  
## <a name="absexpression"></a><span data-ttu-id="64182-107">ABS (expresión)</span><span class="sxs-lookup"><span data-stu-id="64182-107">ABS(expression)</span></span>

<span data-ttu-id="64182-108">Lleva a cabo la función que devuelve el valor absoluto.</span><span class="sxs-lookup"><span data-stu-id="64182-108">Performs the absolute value function.</span></span>

<span data-ttu-id="64182-109">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="64182-109">**Arguments**</span></span>

<span data-ttu-id="64182-110">`expression`: `Int32`, ,`Int64` O`Decimal`. `Double`</span><span class="sxs-lookup"><span data-stu-id="64182-110">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="64182-111">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="64182-111">**Return Value**</span></span>

<span data-ttu-id="64182-112">Valor absoluto de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="64182-112">The absolute value of the specified expression.</span></span>

<span data-ttu-id="64182-113">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="64182-113">**Example**</span></span>

`SqlServer.ABS(-2)`

## <a name="acosexpression"></a><span data-ttu-id="64182-114">ACOS (expresión)</span><span class="sxs-lookup"><span data-stu-id="64182-114">ACOS(expression)</span></span>

<span data-ttu-id="64182-115">Devuelve el valor del arcocoseno de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="64182-115">Returns the arccosine value of the specified expression.</span></span>

<span data-ttu-id="64182-116">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="64182-116">**Arguments**</span></span>

<span data-ttu-id="64182-117">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="64182-117">`expression`: A `Double`.</span></span>

<span data-ttu-id="64182-118">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="64182-118">**Return Value**</span></span>

<span data-ttu-id="64182-119">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="64182-119">A `Double`.</span></span>

<span data-ttu-id="64182-120">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="64182-120">**Example**</span></span>

`SqlServer.ACOS(.9)`

## <a name="asinexpression"></a><span data-ttu-id="64182-121">ASIN (expresión)</span><span class="sxs-lookup"><span data-stu-id="64182-121">ASIN(expression)</span></span>

<span data-ttu-id="64182-122">Devuelve el valor del arcoseno de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="64182-122">Returns the arcsine value of the specified expression.</span></span>

<span data-ttu-id="64182-123">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="64182-123">**Arguments**</span></span>

<span data-ttu-id="64182-124">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="64182-124">`expression`: A `Double`.</span></span>

<span data-ttu-id="64182-125">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="64182-125">**Return Value**</span></span>

<span data-ttu-id="64182-126">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="64182-126">A `Double`.</span></span>

<span data-ttu-id="64182-127">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="64182-127">**Example**</span></span>

`SqlServer.ASIN(.9)`

## <a name="atanexpression"></a><span data-ttu-id="64182-128">ATAN (expresión)</span><span class="sxs-lookup"><span data-stu-id="64182-128">ATAN(expression)</span></span>

<span data-ttu-id="64182-129">Devuelve el valor del arcotangente de la expresión numérica especificada.</span><span class="sxs-lookup"><span data-stu-id="64182-129">Returns the arctangent value of the specified numeric expression.</span></span>

<span data-ttu-id="64182-130">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="64182-130">**Arguments**</span></span>

<span data-ttu-id="64182-131">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="64182-131">`expression`: A `Double`.</span></span>

<span data-ttu-id="64182-132">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="64182-132">**Return Value**</span></span>

<span data-ttu-id="64182-133">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="64182-133">A `Double`.</span></span>

<span data-ttu-id="64182-134">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="64182-134">**Example**</span></span>

`SqlServer.ATAN(9)`

## <a name="atn2expression-expression"></a><span data-ttu-id="64182-135">ATN2 (expresión, expresión)</span><span class="sxs-lookup"><span data-stu-id="64182-135">ATN2(expression, expression)</span></span>

<span data-ttu-id="64182-136">Devuelve el ángulo, en radianes, cuya tangente se encuentra entre las dos expresiones numéricas especificadas.</span><span class="sxs-lookup"><span data-stu-id="64182-136">Returns the angle, in radians, whose tangent is between the two specified numeric expressions.</span></span>

<span data-ttu-id="64182-137">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="64182-137">**Arguments**</span></span>

<span data-ttu-id="64182-138">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="64182-138">`expression`: A `Double`.</span></span>

<span data-ttu-id="64182-139">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="64182-139">**Return Value**</span></span>

<span data-ttu-id="64182-140">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="64182-140">A `Double`.</span></span>

<span data-ttu-id="64182-141">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="64182-141">**Example**</span></span>

`SqlServer.ATN2(9, 8)`
 
## <a name="ceilingexpression"></a><span data-ttu-id="64182-142">CEILING (expresión)</span><span class="sxs-lookup"><span data-stu-id="64182-142">CEILING(expression)</span></span>

<span data-ttu-id="64182-143">Convierte la expresión especificada al número entero más pequeño mayor o igual que él.</span><span class="sxs-lookup"><span data-stu-id="64182-143">Converts the specified expression to the smallest integer that is greater than or equal to it.</span></span>

<span data-ttu-id="64182-144">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="64182-144">**Arguments**</span></span>

<span data-ttu-id="64182-145">`expression`: `Int32`, ,`Int64` O`Decimal`. `Double`</span><span class="sxs-lookup"><span data-stu-id="64182-145">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="64182-146">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="64182-146">**Return Value**</span></span>

<span data-ttu-id="64182-147">`Int32`, ,`Int64` O`Decimal`. `Double`</span><span class="sxs-lookup"><span data-stu-id="64182-147">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="64182-148">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="64182-148">**Example**</span></span> 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_ceiling)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_ceiling)]

## <a name="cosexpression"></a><span data-ttu-id="64182-149">COS (expresión)</span><span class="sxs-lookup"><span data-stu-id="64182-149">COS(expression)</span></span>

<span data-ttu-id="64182-150">Calcula el coseno trigonométrico del ángulo especificado, en radianes.</span><span class="sxs-lookup"><span data-stu-id="64182-150">Calculates the trigonometric cosine of the specified angle in radians.</span></span> 

<span data-ttu-id="64182-151">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="64182-151">**Arguments**</span></span> 

<span data-ttu-id="64182-152">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="64182-152">`expression`: A `Double`.</span></span> 

<span data-ttu-id="64182-153">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="64182-153">**Return Value**</span></span> 

<span data-ttu-id="64182-154">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="64182-154">A `Double`.</span></span> 

<span data-ttu-id="64182-155">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="64182-155">**Example**</span></span> 

`SqlServer.COS(45)`

## <a name="cotexpression"></a><span data-ttu-id="64182-156">COT (expresión)</span><span class="sxs-lookup"><span data-stu-id="64182-156">COT(expression)</span></span>

<span data-ttu-id="64182-157">Calcula la cotangente trigonométrica del ángulo especificado, en radianes.</span><span class="sxs-lookup"><span data-stu-id="64182-157">Calculates the trigonometric cotangent of the specified angle in radians.</span></span> 

<span data-ttu-id="64182-158">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="64182-158">**Arguments**</span></span> 

<span data-ttu-id="64182-159">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="64182-159">`expression`: A `Double`.</span></span> 

<span data-ttu-id="64182-160">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="64182-160">**Return Value**</span></span> 

<span data-ttu-id="64182-161">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="64182-161">A `Double`.</span></span> 

<span data-ttu-id="64182-162">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="64182-162">**Example**</span></span> 

`SqlServer.COT(60)`
  
## <a name="degreesradians"></a><span data-ttu-id="64182-163">GRADOS (radianes)</span><span class="sxs-lookup"><span data-stu-id="64182-163">DEGREES(radians)</span></span>

<span data-ttu-id="64182-164">Devuelve el ángulo correspondiente en grados.</span><span class="sxs-lookup"><span data-stu-id="64182-164">Returns the corresponding angle in degrees.</span></span> 

<span data-ttu-id="64182-165">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="64182-165">**Arguments**</span></span> 

<span data-ttu-id="64182-166">`expression`: `Int32`, ,`Int64` O`Decimal`. `Double`</span><span class="sxs-lookup"><span data-stu-id="64182-166">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="64182-167">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="64182-167">**Return Value**</span></span> 

<span data-ttu-id="64182-168">`Int32`, ,`Int64` O`Decimal`. `Double`</span><span class="sxs-lookup"><span data-stu-id="64182-168">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="64182-169">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="64182-169">**Example**</span></span> 

`SqlServer.DEGREES(3.1)`

## <a name="expexpression"></a><span data-ttu-id="64182-170">EXP (expresión)</span><span class="sxs-lookup"><span data-stu-id="64182-170">EXP(expression)</span></span>

<span data-ttu-id="64182-171">Calcula el valor exponencial de la expresión numérica especificada.</span><span class="sxs-lookup"><span data-stu-id="64182-171">Calculates the exponential value of a specified numeric expression.</span></span> 

<span data-ttu-id="64182-172">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="64182-172">**Arguments**</span></span> 

<span data-ttu-id="64182-173">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="64182-173">`expression`: A `Double`.</span></span> 

<span data-ttu-id="64182-174">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="64182-174">**Return Value**</span></span> 

<span data-ttu-id="64182-175">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="64182-175">A `Double`.</span></span> 

<span data-ttu-id="64182-176">**Ejemplo** de`SqlServer.EXP(1)`</span><span class="sxs-lookup"><span data-stu-id="64182-176">**Example** `SqlServer.EXP(1)`</span></span>

## <a name="floorexpression"></a><span data-ttu-id="64182-177">FLOOR (expresión)</span><span class="sxs-lookup"><span data-stu-id="64182-177">FLOOR(expression)</span></span>

<span data-ttu-id="64182-178">Convierte la expresión especificada al número entero más grande que sea menor o igual que ella.</span><span class="sxs-lookup"><span data-stu-id="64182-178">Converts the specified expression to the largest integer less than or equal to it.</span></span> 

<span data-ttu-id="64182-179">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="64182-179">**Arguments**</span></span> 

<span data-ttu-id="64182-180">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="64182-180">`expression`: A `Double`.</span></span> 

<span data-ttu-id="64182-181">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="64182-181">**Return Value**</span></span> 

<span data-ttu-id="64182-182">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="64182-182">A `Double`.</span></span> 

<span data-ttu-id="64182-183">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="64182-183">**Example**</span></span> 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_floor)] 
[!code-sql[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_floor)]

## <a name="logexpression"></a><span data-ttu-id="64182-184">LOG (expresión)</span><span class="sxs-lookup"><span data-stu-id="64182-184">LOG(expression)</span></span>

<span data-ttu-id="64182-185">Calcula el logaritmo natural de la expresión `float` especificada.</span><span class="sxs-lookup"><span data-stu-id="64182-185">Calculates the natural logarithm of the specified `float` expression.</span></span> 

<span data-ttu-id="64182-186">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="64182-186">**Arguments**</span></span> 

<span data-ttu-id="64182-187">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="64182-187">`expression`: A `Double`.</span></span> 

<span data-ttu-id="64182-188">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="64182-188">**Return Value**</span></span> 

<span data-ttu-id="64182-189">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="64182-189">A `Double`.</span></span> 

<span data-ttu-id="64182-190">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="64182-190">**Example**</span></span> 

`SqlServer.LOG(100)`

## <a name="log10expression"></a><span data-ttu-id="64182-191">LOG10 (expresión)</span><span class="sxs-lookup"><span data-stu-id="64182-191">LOG10(expression)</span></span>

<span data-ttu-id="64182-192">Devuelve el logaritmo en base 10 de la expresión `Double` especificada.</span><span class="sxs-lookup"><span data-stu-id="64182-192">Returns the base-10 logarithm of the specified `Double` expression.</span></span> 

<span data-ttu-id="64182-193">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="64182-193">**Arguments**</span></span> 

<span data-ttu-id="64182-194">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="64182-194">`expression`: A `Double`.</span></span> 

<span data-ttu-id="64182-195">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="64182-195">**Return Value**</span></span> 

<span data-ttu-id="64182-196">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="64182-196">A `Double`.</span></span> 

<span data-ttu-id="64182-197">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="64182-197">**Example**</span></span> 

`SqlServer.LOG10(100)`

## <a name="pi"></a><span data-ttu-id="64182-198">PI()</span><span class="sxs-lookup"><span data-stu-id="64182-198">PI()</span></span>

<span data-ttu-id="64182-199">Devuelve el valor constante de Pi como un `Double`.</span><span class="sxs-lookup"><span data-stu-id="64182-199">Returns the constant value of pi as a `Double`.</span></span> 

<span data-ttu-id="64182-200">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="64182-200">**Return Value**</span></span> 

<span data-ttu-id="64182-201">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="64182-201">A `Double`.</span></span> 

<span data-ttu-id="64182-202">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="64182-202">**Example**</span></span> 

`SqlServer.PI()`

## <a name="powernumeric_expression-power_expression"></a><span data-ttu-id="64182-203">POWER (numeric_expression, power_expression)</span><span class="sxs-lookup"><span data-stu-id="64182-203">POWER(numeric_expression, power_expression)</span></span>

<span data-ttu-id="64182-204">Calcula el valor de la expresión especificada elevada a la potencia indicada.</span><span class="sxs-lookup"><span data-stu-id="64182-204">Calculates the value of a specified expression to a specified power.</span></span>

<span data-ttu-id="64182-205">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="64182-205">**Arguments**</span></span> 

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="64182-206">`Int32`, ,`Int64` O`Decimal`. `Double`</span><span class="sxs-lookup"><span data-stu-id="64182-206">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>|
|`power_expression`| <span data-ttu-id="64182-207">Que representa la potencia a la que se eleva el `numeric_expression`. `Double`</span><span class="sxs-lookup"><span data-stu-id="64182-207">A `Double` that represents the power to which to raise the `numeric_expression`.</span></span>| 

<span data-ttu-id="64182-208">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="64182-208">**Return Value**</span></span> 

<span data-ttu-id="64182-209">Valor de la `numeric_expression` especificada a la `power_expression` especificada.</span><span class="sxs-lookup"><span data-stu-id="64182-209">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span> 

<span data-ttu-id="64182-210">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="64182-210">**Example**</span></span> 

`SqlServer.POWER(2,7)`

## <a name="radiansexpression"></a><span data-ttu-id="64182-211">RADIAnes (expresión)</span><span class="sxs-lookup"><span data-stu-id="64182-211">RADIANS(expression)</span></span>

<span data-ttu-id="64182-212">Convierte grados en radianes.</span><span class="sxs-lookup"><span data-stu-id="64182-212">Converts degrees to radians.</span></span> 

<span data-ttu-id="64182-213">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="64182-213">**Arguments**</span></span> 

<span data-ttu-id="64182-214">`expression`: `Int32`, ,`Int64` O`Decimal`. `Double`</span><span class="sxs-lookup"><span data-stu-id="64182-214">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="64182-215">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="64182-215">**Return Value**</span></span> 

<span data-ttu-id="64182-216">`Int32`, ,`Int64` O`Decimal`. `Double`</span><span class="sxs-lookup"><span data-stu-id="64182-216">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="64182-217">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="64182-217">**Example**</span></span> 

`SqlServer.RADIANS(360.0)`

## <a name="randseed"></a><span data-ttu-id="64182-218">RAND ([SEED])</span><span class="sxs-lookup"><span data-stu-id="64182-218">RAND([seed])</span></span>

<span data-ttu-id="64182-219">Devuelve un valor aleatorio de 0 a 1.</span><span class="sxs-lookup"><span data-stu-id="64182-219">Returns a random value from 0 through 1.</span></span> 

<span data-ttu-id="64182-220">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="64182-220">**Arguments**</span></span> 

<span data-ttu-id="64182-221">Valor de inicialización como `Int32`.</span><span class="sxs-lookup"><span data-stu-id="64182-221">The seed value as an `Int32`.</span></span> <span data-ttu-id="64182-222">Si la inicialización no se especifica, el motor de base de datos de SQL Server asigna uno de forma aleatoria.</span><span class="sxs-lookup"><span data-stu-id="64182-222">If the seed is not specified, the SQL Server Database Engine assigns a seed value at random.</span></span> <span data-ttu-id="64182-223">Para un valor de inicialización especificado, el resultado devuelto es siempre el mismo.</span><span class="sxs-lookup"><span data-stu-id="64182-223">For a specified seed value, the result returned is always the same.</span></span>

<span data-ttu-id="64182-224">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="64182-224">**Return Value**</span></span> 

<span data-ttu-id="64182-225">Valor `Double` aleatorio de 0 a 1.</span><span class="sxs-lookup"><span data-stu-id="64182-225">A random `Double` value from 0 through 1.</span></span> 

<span data-ttu-id="64182-226">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="64182-226">**Example**</span></span> 

`SqlServer.RAND()`
  
## <a name="roundnumeric_expression-lengthfunction"></a><span data-ttu-id="64182-227">ROUND (numeric_expression, longitud [, función])</span><span class="sxs-lookup"><span data-stu-id="64182-227">ROUND(numeric_expression, length[,function])</span></span>

<span data-ttu-id="64182-228">Devuelve una expresión numérica, redondeada a la longitud o precisión especificadas.</span><span class="sxs-lookup"><span data-stu-id="64182-228">Returns a numeric expression, rounded to the specified length or precision.</span></span> 

<span data-ttu-id="64182-229">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="64182-229">**Arguments**</span></span> 

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="64182-230">`Int32`, ,`Int64` O`Decimal`. `Double`</span><span class="sxs-lookup"><span data-stu-id="64182-230">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 
|`length`| <span data-ttu-id="64182-231">Valor `Int32` que representa la precisión a la que se va a redondear `numeric_expression`.</span><span class="sxs-lookup"><span data-stu-id="64182-231">An `Int32` that represents the precision to which `numeric_expression` is to be rounded.</span></span> <span data-ttu-id="64182-232">Si `length` es un número positivo, `numeric_expression` se redondea al número de posiciones decimales que especifica `length`.</span><span class="sxs-lookup"><span data-stu-id="64182-232">When `length` is a positive number, `numeric_expression` is rounded to the number of decimal positions specified by `length`.</span></span> <span data-ttu-id="64182-233">Si `length` es un número negativo, `numeric_expression` se redondea a la izquierda del separador decimal, según se especifica en `length`.</span><span class="sxs-lookup"><span data-stu-id="64182-233">When `length` is a negative number, `numeric_expression` is rounded on the left side of the decimal point, as specified by `length`.</span></span>|
|`function` | <span data-ttu-id="64182-234">Opcional.</span><span class="sxs-lookup"><span data-stu-id="64182-234">Optional.</span></span> <span data-ttu-id="64182-235">`Int32` Que representa el tipo de operación que se va a realizar.</span><span class="sxs-lookup"><span data-stu-id="64182-235">An `Int32` that represents the type of operation to perform.</span></span> <span data-ttu-id="64182-236">Cuando se omite la función o tiene un valor de 0 (valor predeterminado `numeric_expression` ), se redondea.</span><span class="sxs-lookup"><span data-stu-id="64182-236">When function is omitted or has a value of 0 (default), `numeric_expression` is rounded.</span></span> <span data-ttu-id="64182-237">Cuando se especifica un valor distinto de 0, `numeric_expression` se trunca.</span><span class="sxs-lookup"><span data-stu-id="64182-237">When a value other than 0 is specified, `numeric_expression` is truncated.</span></span> |

<span data-ttu-id="64182-238">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="64182-238">**Return Value**</span></span> 

<span data-ttu-id="64182-239">Valor de la `numeric_expression` especificada a la `power_expression` especificada.</span><span class="sxs-lookup"><span data-stu-id="64182-239">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span>

<span data-ttu-id="64182-240">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="64182-240">**Example**</span></span> 

`SqlServer.ROUND(748.58, -3)`

## <a name="signexpression"></a><span data-ttu-id="64182-241">SIGN (expresión)</span><span class="sxs-lookup"><span data-stu-id="64182-241">SIGN(expression)</span></span> 

<span data-ttu-id="64182-242">Devuelve el signo positivo (+1), cero (0) o negativo (-1) de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="64182-242">Returns the positive (+1), zero (0), or negative (-1) sign of the specified expression.</span></span> 

<span data-ttu-id="64182-243">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="64182-243">**Arguments**</span></span> 

<span data-ttu-id="64182-244">`expression`: `Int32`, `Int64`, `Double` o `Decimal`</span><span class="sxs-lookup"><span data-stu-id="64182-244">`expression`: `Int32`, `Int64`, `Double`, or `Decimal`</span></span> 

<span data-ttu-id="64182-245">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="64182-245">**Return Value**</span></span> 

<span data-ttu-id="64182-246">`Int32`, ,`Int64` O`Decimal`. `Double`</span><span class="sxs-lookup"><span data-stu-id="64182-246">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="64182-247">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="64182-247">**Example**</span></span> 

`SqlServer.SIGN(-10)`

## <a name="sinexpression"></a><span data-ttu-id="64182-248">SIN (expresión)</span><span class="sxs-lookup"><span data-stu-id="64182-248">SIN(expression)</span></span>

<span data-ttu-id="64182-249">Calcula el seno trigonométrico de un ángulo especificado, en radianes, y devuelve una expresión de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="64182-249">Calculates the trigonometric sine of the specified angle in radians, and returns a `Double` expression.</span></span> 

<span data-ttu-id="64182-250">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="64182-250">**Arguments**</span></span> 

<span data-ttu-id="64182-251">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="64182-251">`expression`: A `Double`.</span></span> 

<span data-ttu-id="64182-252">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="64182-252">**Return Value**</span></span> 

<span data-ttu-id="64182-253">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="64182-253">A `Double`.</span></span> 

<span data-ttu-id="64182-254">**Ejemplo** de`SqlServer.SIN(20)`</span><span class="sxs-lookup"><span data-stu-id="64182-254">**Example** `SqlServer.SIN(20)`</span></span>

## <a name="sqrtexpression"></a><span data-ttu-id="64182-255">SQRT (expresión)</span><span class="sxs-lookup"><span data-stu-id="64182-255">SQRT(expression)</span></span>

<span data-ttu-id="64182-256">Devuelve la raíz cuadrada de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="64182-256">Returns the square root of the specified expression.</span></span> 

<span data-ttu-id="64182-257">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="64182-257">**Arguments**</span></span> 

<span data-ttu-id="64182-258">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="64182-258">`expression`: A `Double`.</span></span> 

<span data-ttu-id="64182-259">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="64182-259">**Return Value**</span></span> 

<span data-ttu-id="64182-260">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="64182-260">A `Double`.</span></span> 

<span data-ttu-id="64182-261">**Ejemplo** de`SqlServer.SQRT(3600)`</span><span class="sxs-lookup"><span data-stu-id="64182-261">**Example** `SqlServer.SQRT(3600)`</span></span>

## <a name="squareexpression"></a><span data-ttu-id="64182-262">SQUARE (expresión)</span><span class="sxs-lookup"><span data-stu-id="64182-262">SQUARE(expression)</span></span>

<span data-ttu-id="64182-263">Devuelve la raíz cuadrada de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="64182-263">Returns the square of the specified expression.</span></span> 

<span data-ttu-id="64182-264">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="64182-264">**Arguments**</span></span> 

<span data-ttu-id="64182-265">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="64182-265">`expression`: A `Double`.</span></span> 

<span data-ttu-id="64182-266">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="64182-266">**Return Value**</span></span> 

<span data-ttu-id="64182-267">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="64182-267">A `Double`.</span></span> 

<span data-ttu-id="64182-268">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="64182-268">**Example**</span></span> 

`SqlServer.SQUARE(25)`

## <a name="tanexpression"></a><span data-ttu-id="64182-269">TAN (expresión)</span><span class="sxs-lookup"><span data-stu-id="64182-269">TAN(expression)</span></span>

<span data-ttu-id="64182-270">Calcula la tangente de una expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="64182-270">Calculates the tangent of a specified expression.</span></span>

<span data-ttu-id="64182-271">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="64182-271">**Arguments**</span></span> 

<span data-ttu-id="64182-272">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="64182-272">`expression`: `Double`</span></span> 

<span data-ttu-id="64182-273">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="64182-273">**Return Value**</span></span> 

`Double` 

<span data-ttu-id="64182-274">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="64182-274">**Example**</span></span> 

`SqlServer.TAN(45.0)`
  
## <a name="see-also"></a><span data-ttu-id="64182-275">Vea también</span><span class="sxs-lookup"><span data-stu-id="64182-275">See also</span></span>

<span data-ttu-id="64182-276">Para obtener más información sobre las funciones matemáticas que SqlClient admite, consulte la documentación de la versión de SQL Server que especificó en el manifiesto del proveedor SqlClient:</span><span class="sxs-lookup"><span data-stu-id="64182-276">For more information about the mathematical functions that SqlClient supports, see the documentation for the SQL Server version that you specified in the SqlClient provider manifest:</span></span>

- <span data-ttu-id="64182-277">**SQL Server 2005:** [Funciones matemáticas (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms177516(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="64182-277">**SQL Server 2005:** [Mathematical Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms177516(v=sql.90))</span></span>
- <span data-ttu-id="64182-278">**SQL Server 2008:** [Funciones matemáticas (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms177516(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="64182-278">**SQL Server 2008:** [Mathematical Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms177516(v=sql.100))</span></span>
- <span data-ttu-id="64182-279">**SQL Server 2012 y versiones posteriores:** [Funciones matemáticas (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="64182-279">**SQL Server 2012 and later:** [Mathematical Functions (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql)</span></span>

- [<span data-ttu-id="64182-280">SqlClient para las funciones de Entity Framework</span><span class="sxs-lookup"><span data-stu-id="64182-280">SqlClient for Entity Framework Functions</span></span>](sqlclient-for-ef-functions.md)
