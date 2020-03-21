---
title: Funciones matemáticas
ms.date: 03/30/2017
ms.assetid: b040c7cb-156d-40f2-9152-61065b18148c
ms.openlocfilehash: 4512aaa2eeb3e715a1d6f7a8655912eb15162124
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149770"
---
# <a name="mathematical-functions"></a><span data-ttu-id="52776-102">Funciones matemáticas</span><span class="sxs-lookup"><span data-stu-id="52776-102">Mathematical Functions</span></span>

<span data-ttu-id="52776-103">El Proveedor de datos .NET Framework para SQL Server (SqlClient) proporciona funciones matemáticas que realizan cálculos con los valores de entrada que se proporcionan como argumentos y devuelven un resultado numérico.</span><span class="sxs-lookup"><span data-stu-id="52776-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides math functions that perform calculations on input values that are provided as arguments, and return a numeric value result.</span></span> <span data-ttu-id="52776-104">Estas funciones están en el espacio de nombres SqlServer, que está disponible al utilizar SqlClient.</span><span class="sxs-lookup"><span data-stu-id="52776-104">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="52776-105">La propiedad del espacio de nombres de un proveedor permite a Entity Framework detectar qué prefijo usa este proveedor para estructuras concretas, como tipos y funciones.</span><span class="sxs-lookup"><span data-stu-id="52776-105">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span> <span data-ttu-id="52776-106">En la tabla siguiente se describen las funciones matemáticas SqlClient.</span><span class="sxs-lookup"><span data-stu-id="52776-106">The following table describes the SqlClient math functions.</span></span>  
  
## <a name="absexpression"></a><span data-ttu-id="52776-107">ABS (expresión)</span><span class="sxs-lookup"><span data-stu-id="52776-107">ABS(expression)</span></span>

<span data-ttu-id="52776-108">Lleva a cabo la función que devuelve el valor absoluto.</span><span class="sxs-lookup"><span data-stu-id="52776-108">Performs the absolute value function.</span></span>

<span data-ttu-id="52776-109">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="52776-109">**Arguments**</span></span>

<span data-ttu-id="52776-110">`expression`: valor de tipo`Int32`,`Int64`, `Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="52776-110">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="52776-111">**Valor de devolución**</span><span class="sxs-lookup"><span data-stu-id="52776-111">**Return Value**</span></span>

<span data-ttu-id="52776-112">Valor absoluto de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="52776-112">The absolute value of the specified expression.</span></span>

<span data-ttu-id="52776-113">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="52776-113">**Example**</span></span>

`SqlServer.ABS(-2)`

## <a name="acosexpression"></a><span data-ttu-id="52776-114">ACOS(expresión)</span><span class="sxs-lookup"><span data-stu-id="52776-114">ACOS(expression)</span></span>

<span data-ttu-id="52776-115">Devuelve el valor del arcocoseno de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="52776-115">Returns the arccosine value of the specified expression.</span></span>

<span data-ttu-id="52776-116">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="52776-116">**Arguments**</span></span>

<span data-ttu-id="52776-117">`expression`: un valor `Double`.</span><span class="sxs-lookup"><span data-stu-id="52776-117">`expression`: A `Double`.</span></span>

<span data-ttu-id="52776-118">**Valor de devolución**</span><span class="sxs-lookup"><span data-stu-id="52776-118">**Return Value**</span></span>

<span data-ttu-id="52776-119">`Double`.</span><span class="sxs-lookup"><span data-stu-id="52776-119">A `Double`.</span></span>

<span data-ttu-id="52776-120">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="52776-120">**Example**</span></span>

`SqlServer.ACOS(.9)`

## <a name="asinexpression"></a><span data-ttu-id="52776-121">ASIN(expresión)</span><span class="sxs-lookup"><span data-stu-id="52776-121">ASIN(expression)</span></span>

<span data-ttu-id="52776-122">Devuelve el valor del arcoseno de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="52776-122">Returns the arcsine value of the specified expression.</span></span>

<span data-ttu-id="52776-123">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="52776-123">**Arguments**</span></span>

<span data-ttu-id="52776-124">`expression`: un valor `Double`.</span><span class="sxs-lookup"><span data-stu-id="52776-124">`expression`: A `Double`.</span></span>

<span data-ttu-id="52776-125">**Valor de devolución**</span><span class="sxs-lookup"><span data-stu-id="52776-125">**Return Value**</span></span>

<span data-ttu-id="52776-126">`Double`.</span><span class="sxs-lookup"><span data-stu-id="52776-126">A `Double`.</span></span>

<span data-ttu-id="52776-127">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="52776-127">**Example**</span></span>

`SqlServer.ASIN(.9)`

## <a name="atanexpression"></a><span data-ttu-id="52776-128">ATAN(expresión)</span><span class="sxs-lookup"><span data-stu-id="52776-128">ATAN(expression)</span></span>

<span data-ttu-id="52776-129">Devuelve el valor del arcotangente de la expresión numérica especificada.</span><span class="sxs-lookup"><span data-stu-id="52776-129">Returns the arctangent value of the specified numeric expression.</span></span>

<span data-ttu-id="52776-130">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="52776-130">**Arguments**</span></span>

<span data-ttu-id="52776-131">`expression`: un valor `Double`.</span><span class="sxs-lookup"><span data-stu-id="52776-131">`expression`: A `Double`.</span></span>

<span data-ttu-id="52776-132">**Valor de devolución**</span><span class="sxs-lookup"><span data-stu-id="52776-132">**Return Value**</span></span>

<span data-ttu-id="52776-133">`Double`.</span><span class="sxs-lookup"><span data-stu-id="52776-133">A `Double`.</span></span>

<span data-ttu-id="52776-134">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="52776-134">**Example**</span></span>

`SqlServer.ATAN(9)`

## <a name="atn2expression-expression"></a><span data-ttu-id="52776-135">ATN2(expresión, expresión)</span><span class="sxs-lookup"><span data-stu-id="52776-135">ATN2(expression, expression)</span></span>

<span data-ttu-id="52776-136">Devuelve el ángulo, en radianes, cuya tangente se encuentra entre las dos expresiones numéricas especificadas.</span><span class="sxs-lookup"><span data-stu-id="52776-136">Returns the angle, in radians, whose tangent is between the two specified numeric expressions.</span></span>

<span data-ttu-id="52776-137">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="52776-137">**Arguments**</span></span>

<span data-ttu-id="52776-138">`expression`: un valor `Double`.</span><span class="sxs-lookup"><span data-stu-id="52776-138">`expression`: A `Double`.</span></span>

<span data-ttu-id="52776-139">**Valor de devolución**</span><span class="sxs-lookup"><span data-stu-id="52776-139">**Return Value**</span></span>

<span data-ttu-id="52776-140">`Double`.</span><span class="sxs-lookup"><span data-stu-id="52776-140">A `Double`.</span></span>

<span data-ttu-id="52776-141">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="52776-141">**Example**</span></span>

`SqlServer.ATN2(9, 8)`

## <a name="ceilingexpression"></a><span data-ttu-id="52776-142">CEILING(expresión)</span><span class="sxs-lookup"><span data-stu-id="52776-142">CEILING(expression)</span></span>

<span data-ttu-id="52776-143">Convierte la expresión especificada al número entero más pequeño mayor o igual que él.</span><span class="sxs-lookup"><span data-stu-id="52776-143">Converts the specified expression to the smallest integer that is greater than or equal to it.</span></span>

<span data-ttu-id="52776-144">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="52776-144">**Arguments**</span></span>

<span data-ttu-id="52776-145">`expression`: valor de tipo`Int32`,`Int64`, `Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="52776-145">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="52776-146">**Valor de devolución**</span><span class="sxs-lookup"><span data-stu-id="52776-146">**Return Value**</span></span>

<span data-ttu-id="52776-147">Un `Int32` `Int64`, `Double`, `Decimal`, o .</span><span class="sxs-lookup"><span data-stu-id="52776-147">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="52776-148">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="52776-148">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_ceiling)]

## <a name="cosexpression"></a><span data-ttu-id="52776-149">COS(expresión)</span><span class="sxs-lookup"><span data-stu-id="52776-149">COS(expression)</span></span>

<span data-ttu-id="52776-150">Calcula el coseno trigonométrico del ángulo especificado, en radianes.</span><span class="sxs-lookup"><span data-stu-id="52776-150">Calculates the trigonometric cosine of the specified angle in radians.</span></span>

<span data-ttu-id="52776-151">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="52776-151">**Arguments**</span></span>

<span data-ttu-id="52776-152">`expression`: un valor `Double`.</span><span class="sxs-lookup"><span data-stu-id="52776-152">`expression`: A `Double`.</span></span>

<span data-ttu-id="52776-153">**Valor de devolución**</span><span class="sxs-lookup"><span data-stu-id="52776-153">**Return Value**</span></span>

<span data-ttu-id="52776-154">`Double`.</span><span class="sxs-lookup"><span data-stu-id="52776-154">A `Double`.</span></span>

<span data-ttu-id="52776-155">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="52776-155">**Example**</span></span>

`SqlServer.COS(45)`

## <a name="cotexpression"></a><span data-ttu-id="52776-156">COT(expresión)</span><span class="sxs-lookup"><span data-stu-id="52776-156">COT(expression)</span></span>

<span data-ttu-id="52776-157">Calcula la cotangente trigonométrica del ángulo especificado, en radianes.</span><span class="sxs-lookup"><span data-stu-id="52776-157">Calculates the trigonometric cotangent of the specified angle in radians.</span></span>

<span data-ttu-id="52776-158">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="52776-158">**Arguments**</span></span>

<span data-ttu-id="52776-159">`expression`: un valor `Double`.</span><span class="sxs-lookup"><span data-stu-id="52776-159">`expression`: A `Double`.</span></span>

<span data-ttu-id="52776-160">**Valor de devolución**</span><span class="sxs-lookup"><span data-stu-id="52776-160">**Return Value**</span></span>

<span data-ttu-id="52776-161">`Double`.</span><span class="sxs-lookup"><span data-stu-id="52776-161">A `Double`.</span></span>

<span data-ttu-id="52776-162">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="52776-162">**Example**</span></span>

`SqlServer.COT(60)`
  
## <a name="degreesradians"></a><span data-ttu-id="52776-163">DEGREES(radianes)</span><span class="sxs-lookup"><span data-stu-id="52776-163">DEGREES(radians)</span></span>

<span data-ttu-id="52776-164">Devuelve el ángulo correspondiente en grados.</span><span class="sxs-lookup"><span data-stu-id="52776-164">Returns the corresponding angle in degrees.</span></span>

<span data-ttu-id="52776-165">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="52776-165">**Arguments**</span></span>

<span data-ttu-id="52776-166">`expression`: valor de tipo`Int32`,`Int64`, `Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="52776-166">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="52776-167">**Valor de devolución**</span><span class="sxs-lookup"><span data-stu-id="52776-167">**Return Value**</span></span>

<span data-ttu-id="52776-168">Un `Int32` `Int64`, `Double`, `Decimal`, o .</span><span class="sxs-lookup"><span data-stu-id="52776-168">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="52776-169">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="52776-169">**Example**</span></span>

`SqlServer.DEGREES(3.1)`

## <a name="expexpression"></a><span data-ttu-id="52776-170">EXP(expresión)</span><span class="sxs-lookup"><span data-stu-id="52776-170">EXP(expression)</span></span>

<span data-ttu-id="52776-171">Calcula el valor exponencial de la expresión numérica especificada.</span><span class="sxs-lookup"><span data-stu-id="52776-171">Calculates the exponential value of a specified numeric expression.</span></span>

<span data-ttu-id="52776-172">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="52776-172">**Arguments**</span></span>

<span data-ttu-id="52776-173">`expression`: un valor `Double`.</span><span class="sxs-lookup"><span data-stu-id="52776-173">`expression`: A `Double`.</span></span>

<span data-ttu-id="52776-174">**Valor de devolución**</span><span class="sxs-lookup"><span data-stu-id="52776-174">**Return Value**</span></span>

<span data-ttu-id="52776-175">`Double`.</span><span class="sxs-lookup"><span data-stu-id="52776-175">A `Double`.</span></span>

<span data-ttu-id="52776-176">**Ejemplo**`SqlServer.EXP(1)`</span><span class="sxs-lookup"><span data-stu-id="52776-176">**Example** `SqlServer.EXP(1)`</span></span>

## <a name="floorexpression"></a><span data-ttu-id="52776-177">PLANTA(expresión)</span><span class="sxs-lookup"><span data-stu-id="52776-177">FLOOR(expression)</span></span>

<span data-ttu-id="52776-178">Convierte la expresión especificada al número entero más grande que sea menor o igual que ella.</span><span class="sxs-lookup"><span data-stu-id="52776-178">Converts the specified expression to the largest integer less than or equal to it.</span></span>

<span data-ttu-id="52776-179">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="52776-179">**Arguments**</span></span>

<span data-ttu-id="52776-180">`expression`: un valor `Double`.</span><span class="sxs-lookup"><span data-stu-id="52776-180">`expression`: A `Double`.</span></span>

<span data-ttu-id="52776-181">**Valor de devolución**</span><span class="sxs-lookup"><span data-stu-id="52776-181">**Return Value**</span></span>

<span data-ttu-id="52776-182">`Double`.</span><span class="sxs-lookup"><span data-stu-id="52776-182">A `Double`.</span></span>

<span data-ttu-id="52776-183">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="52776-183">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_floor)]

## <a name="logexpression"></a><span data-ttu-id="52776-184">LOG(expresión)</span><span class="sxs-lookup"><span data-stu-id="52776-184">LOG(expression)</span></span>

<span data-ttu-id="52776-185">Calcula el logaritmo natural de la expresión `float` especificada.</span><span class="sxs-lookup"><span data-stu-id="52776-185">Calculates the natural logarithm of the specified `float` expression.</span></span>

<span data-ttu-id="52776-186">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="52776-186">**Arguments**</span></span>

<span data-ttu-id="52776-187">`expression`: un valor `Double`.</span><span class="sxs-lookup"><span data-stu-id="52776-187">`expression`: A `Double`.</span></span>

<span data-ttu-id="52776-188">**Valor de devolución**</span><span class="sxs-lookup"><span data-stu-id="52776-188">**Return Value**</span></span>

<span data-ttu-id="52776-189">`Double`.</span><span class="sxs-lookup"><span data-stu-id="52776-189">A `Double`.</span></span>

<span data-ttu-id="52776-190">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="52776-190">**Example**</span></span>

`SqlServer.LOG(100)`

## <a name="log10expression"></a><span data-ttu-id="52776-191">LOG10(expresión)</span><span class="sxs-lookup"><span data-stu-id="52776-191">LOG10(expression)</span></span>

<span data-ttu-id="52776-192">Devuelve el logaritmo en base 10 de la expresión `Double` especificada.</span><span class="sxs-lookup"><span data-stu-id="52776-192">Returns the base-10 logarithm of the specified `Double` expression.</span></span>

<span data-ttu-id="52776-193">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="52776-193">**Arguments**</span></span>

<span data-ttu-id="52776-194">`expression`: un valor `Double`.</span><span class="sxs-lookup"><span data-stu-id="52776-194">`expression`: A `Double`.</span></span>

<span data-ttu-id="52776-195">**Valor de devolución**</span><span class="sxs-lookup"><span data-stu-id="52776-195">**Return Value**</span></span>

<span data-ttu-id="52776-196">`Double`.</span><span class="sxs-lookup"><span data-stu-id="52776-196">A `Double`.</span></span>

<span data-ttu-id="52776-197">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="52776-197">**Example**</span></span>

`SqlServer.LOG10(100)`

## <a name="pi"></a><span data-ttu-id="52776-198">PI()</span><span class="sxs-lookup"><span data-stu-id="52776-198">PI()</span></span>

<span data-ttu-id="52776-199">Devuelve el valor constante de Pi como un `Double`.</span><span class="sxs-lookup"><span data-stu-id="52776-199">Returns the constant value of pi as a `Double`.</span></span>

<span data-ttu-id="52776-200">**Valor de devolución**</span><span class="sxs-lookup"><span data-stu-id="52776-200">**Return Value**</span></span>

<span data-ttu-id="52776-201">`Double`.</span><span class="sxs-lookup"><span data-stu-id="52776-201">A `Double`.</span></span>

<span data-ttu-id="52776-202">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="52776-202">**Example**</span></span>

`SqlServer.PI()`

## <a name="powernumeric_expression-power_expression"></a><span data-ttu-id="52776-203">POTENCIA(numeric_expression, power_expression)</span><span class="sxs-lookup"><span data-stu-id="52776-203">POWER(numeric_expression, power_expression)</span></span>

<span data-ttu-id="52776-204">Calcula el valor de la expresión especificada elevada a la potencia indicada.</span><span class="sxs-lookup"><span data-stu-id="52776-204">Calculates the value of a specified expression to a specified power.</span></span>

<span data-ttu-id="52776-205">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="52776-205">**Arguments**</span></span>

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="52776-206">Un `Int32` `Int64`, `Double`, `Decimal`, o .</span><span class="sxs-lookup"><span data-stu-id="52776-206">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>|
|`power_expression`| <span data-ttu-id="52776-207">A `Double` que representa el poder al `numeric_expression`que elevar el archivo .</span><span class="sxs-lookup"><span data-stu-id="52776-207">A `Double` that represents the power to which to raise the `numeric_expression`.</span></span>|

<span data-ttu-id="52776-208">**Valor de devolución**</span><span class="sxs-lookup"><span data-stu-id="52776-208">**Return Value**</span></span>

<span data-ttu-id="52776-209">Valor de la `numeric_expression` especificada a la `power_expression` especificada.</span><span class="sxs-lookup"><span data-stu-id="52776-209">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span>

<span data-ttu-id="52776-210">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="52776-210">**Example**</span></span>

`SqlServer.POWER(2,7)`

## <a name="radiansexpression"></a><span data-ttu-id="52776-211">RADIANS(expresión)</span><span class="sxs-lookup"><span data-stu-id="52776-211">RADIANS(expression)</span></span>

<span data-ttu-id="52776-212">Convierte los grados en radianes.</span><span class="sxs-lookup"><span data-stu-id="52776-212">Converts degrees to radians.</span></span>

<span data-ttu-id="52776-213">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="52776-213">**Arguments**</span></span>

<span data-ttu-id="52776-214">`expression`: valor de tipo`Int32`,`Int64`, `Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="52776-214">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="52776-215">**Valor de devolución**</span><span class="sxs-lookup"><span data-stu-id="52776-215">**Return Value**</span></span>

<span data-ttu-id="52776-216">Un `Int32` `Int64`, `Double`, `Decimal`, o .</span><span class="sxs-lookup"><span data-stu-id="52776-216">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="52776-217">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="52776-217">**Example**</span></span>

`SqlServer.RADIANS(360.0)`

## <a name="randseed"></a><span data-ttu-id="52776-218">RAND([semilla])</span><span class="sxs-lookup"><span data-stu-id="52776-218">RAND([seed])</span></span>

<span data-ttu-id="52776-219">Devuelve un valor aleatorio de 0 a 1.</span><span class="sxs-lookup"><span data-stu-id="52776-219">Returns a random value from 0 through 1.</span></span>

<span data-ttu-id="52776-220">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="52776-220">**Arguments**</span></span>

<span data-ttu-id="52776-221">El valor de `Int32`semilla como un archivo .</span><span class="sxs-lookup"><span data-stu-id="52776-221">The seed value as an `Int32`.</span></span> <span data-ttu-id="52776-222">Si la inicialización no se especifica, el motor de base de datos de SQL Server asigna uno de forma aleatoria.</span><span class="sxs-lookup"><span data-stu-id="52776-222">If the seed is not specified, the SQL Server Database Engine assigns a seed value at random.</span></span> <span data-ttu-id="52776-223">Para un valor de inicialización especificado, el resultado devuelto es siempre el mismo.</span><span class="sxs-lookup"><span data-stu-id="52776-223">For a specified seed value, the result returned is always the same.</span></span>

<span data-ttu-id="52776-224">**Valor de devolución**</span><span class="sxs-lookup"><span data-stu-id="52776-224">**Return Value**</span></span>

<span data-ttu-id="52776-225">Valor `Double` aleatorio de 0 a 1.</span><span class="sxs-lookup"><span data-stu-id="52776-225">A random `Double` value from 0 through 1.</span></span>

<span data-ttu-id="52776-226">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="52776-226">**Example**</span></span>

`SqlServer.RAND()`
  
## <a name="roundnumeric_expression-lengthfunction"></a><span data-ttu-id="52776-227">ROUND(numeric_expression, length[,function])</span><span class="sxs-lookup"><span data-stu-id="52776-227">ROUND(numeric_expression, length[,function])</span></span>

<span data-ttu-id="52776-228">Devuelve una expresión numérica, redondeada a la longitud o precisión especificadas.</span><span class="sxs-lookup"><span data-stu-id="52776-228">Returns a numeric expression, rounded to the specified length or precision.</span></span>

<span data-ttu-id="52776-229">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="52776-229">**Arguments**</span></span>

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="52776-230">Un `Int32` `Int64`, `Double`, `Decimal`, o .</span><span class="sxs-lookup"><span data-stu-id="52776-230">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>
|`length`| <span data-ttu-id="52776-231">Valor `Int32` que representa la precisión a la que se va a redondear `numeric_expression`.</span><span class="sxs-lookup"><span data-stu-id="52776-231">An `Int32` that represents the precision to which `numeric_expression` is to be rounded.</span></span> <span data-ttu-id="52776-232">Si `length` es un número positivo, `numeric_expression` se redondea al número de posiciones decimales que especifica `length`.</span><span class="sxs-lookup"><span data-stu-id="52776-232">When `length` is a positive number, `numeric_expression` is rounded to the number of decimal positions specified by `length`.</span></span> <span data-ttu-id="52776-233">Si `length` es un número negativo, `numeric_expression` se redondea a la izquierda del separador decimal, según se especifica en `length`.</span><span class="sxs-lookup"><span data-stu-id="52776-233">When `length` is a negative number, `numeric_expression` is rounded on the left side of the decimal point, as specified by `length`.</span></span>|
|`function` | <span data-ttu-id="52776-234">Opcional.</span><span class="sxs-lookup"><span data-stu-id="52776-234">Optional.</span></span> <span data-ttu-id="52776-235">Un `Int32` que representa el tipo de operación que se va a realizar.</span><span class="sxs-lookup"><span data-stu-id="52776-235">An `Int32` that represents the type of operation to perform.</span></span> <span data-ttu-id="52776-236">Cuando se omite la función o tiene `numeric_expression` un valor de 0 (predeterminado), se redondea.</span><span class="sxs-lookup"><span data-stu-id="52776-236">When function is omitted or has a value of 0 (default), `numeric_expression` is rounded.</span></span> <span data-ttu-id="52776-237">Cuando se especifica un valor `numeric_expression` distinto de 0, se trunca.</span><span class="sxs-lookup"><span data-stu-id="52776-237">When a value other than 0 is specified, `numeric_expression` is truncated.</span></span> |

<span data-ttu-id="52776-238">**Valor de devolución**</span><span class="sxs-lookup"><span data-stu-id="52776-238">**Return Value**</span></span>

<span data-ttu-id="52776-239">Valor de la `numeric_expression` especificada a la `power_expression` especificada.</span><span class="sxs-lookup"><span data-stu-id="52776-239">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span>

<span data-ttu-id="52776-240">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="52776-240">**Example**</span></span>

`SqlServer.ROUND(748.58, -3)`

## <a name="signexpression"></a><span data-ttu-id="52776-241">SIGN(expresión)</span><span class="sxs-lookup"><span data-stu-id="52776-241">SIGN(expression)</span></span>

<span data-ttu-id="52776-242">Devuelve el signo positivo (+1), cero (0) o negativo (-1) de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="52776-242">Returns the positive (+1), zero (0), or negative (-1) sign of the specified expression.</span></span>

<span data-ttu-id="52776-243">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="52776-243">**Arguments**</span></span>

<span data-ttu-id="52776-244">`expression`: `Int32`, `Int64`, `Double` o `Decimal`</span><span class="sxs-lookup"><span data-stu-id="52776-244">`expression`: `Int32`, `Int64`, `Double`, or `Decimal`</span></span>

<span data-ttu-id="52776-245">**Valor de devolución**</span><span class="sxs-lookup"><span data-stu-id="52776-245">**Return Value**</span></span>

<span data-ttu-id="52776-246">Un `Int32` `Int64`, `Double`, `Decimal`, o .</span><span class="sxs-lookup"><span data-stu-id="52776-246">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="52776-247">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="52776-247">**Example**</span></span>

`SqlServer.SIGN(-10)`

## <a name="sinexpression"></a><span data-ttu-id="52776-248">SIN(expresión)</span><span class="sxs-lookup"><span data-stu-id="52776-248">SIN(expression)</span></span>

<span data-ttu-id="52776-249">Calcula el seno trigonométrico de un ángulo especificado, en radianes, y devuelve una expresión de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="52776-249">Calculates the trigonometric sine of the specified angle in radians, and returns a `Double` expression.</span></span>

<span data-ttu-id="52776-250">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="52776-250">**Arguments**</span></span>

<span data-ttu-id="52776-251">`expression`: un valor `Double`.</span><span class="sxs-lookup"><span data-stu-id="52776-251">`expression`: A `Double`.</span></span>

<span data-ttu-id="52776-252">**Valor de devolución**</span><span class="sxs-lookup"><span data-stu-id="52776-252">**Return Value**</span></span>

<span data-ttu-id="52776-253">`Double`.</span><span class="sxs-lookup"><span data-stu-id="52776-253">A `Double`.</span></span>

<span data-ttu-id="52776-254">**Ejemplo**`SqlServer.SIN(20)`</span><span class="sxs-lookup"><span data-stu-id="52776-254">**Example** `SqlServer.SIN(20)`</span></span>

## <a name="sqrtexpression"></a><span data-ttu-id="52776-255">SQRT(expresión)</span><span class="sxs-lookup"><span data-stu-id="52776-255">SQRT(expression)</span></span>

<span data-ttu-id="52776-256">Devuelve la raíz cuadrada de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="52776-256">Returns the square root of the specified expression.</span></span>

<span data-ttu-id="52776-257">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="52776-257">**Arguments**</span></span>

<span data-ttu-id="52776-258">`expression`: un valor `Double`.</span><span class="sxs-lookup"><span data-stu-id="52776-258">`expression`: A `Double`.</span></span>

<span data-ttu-id="52776-259">**Valor de devolución**</span><span class="sxs-lookup"><span data-stu-id="52776-259">**Return Value**</span></span>

<span data-ttu-id="52776-260">`Double`.</span><span class="sxs-lookup"><span data-stu-id="52776-260">A `Double`.</span></span>

<span data-ttu-id="52776-261">**Ejemplo**`SqlServer.SQRT(3600)`</span><span class="sxs-lookup"><span data-stu-id="52776-261">**Example** `SqlServer.SQRT(3600)`</span></span>

## <a name="squareexpression"></a><span data-ttu-id="52776-262">SQUARE(expresión)</span><span class="sxs-lookup"><span data-stu-id="52776-262">SQUARE(expression)</span></span>

<span data-ttu-id="52776-263">Devuelve la raíz cuadrada de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="52776-263">Returns the square of the specified expression.</span></span>

<span data-ttu-id="52776-264">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="52776-264">**Arguments**</span></span>

<span data-ttu-id="52776-265">`expression`: un valor `Double`.</span><span class="sxs-lookup"><span data-stu-id="52776-265">`expression`: A `Double`.</span></span>

<span data-ttu-id="52776-266">**Valor de devolución**</span><span class="sxs-lookup"><span data-stu-id="52776-266">**Return Value**</span></span>

<span data-ttu-id="52776-267">`Double`.</span><span class="sxs-lookup"><span data-stu-id="52776-267">A `Double`.</span></span>

<span data-ttu-id="52776-268">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="52776-268">**Example**</span></span>

`SqlServer.SQUARE(25)`

## <a name="tanexpression"></a><span data-ttu-id="52776-269">TAN(expresión)</span><span class="sxs-lookup"><span data-stu-id="52776-269">TAN(expression)</span></span>

<span data-ttu-id="52776-270">Calcula la tangente de una expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="52776-270">Calculates the tangent of a specified expression.</span></span>

<span data-ttu-id="52776-271">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="52776-271">**Arguments**</span></span>

<span data-ttu-id="52776-272">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="52776-272">`expression`: `Double`</span></span>

<span data-ttu-id="52776-273">**Valor de devolución**</span><span class="sxs-lookup"><span data-stu-id="52776-273">**Return Value**</span></span>

`Double`

<span data-ttu-id="52776-274">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="52776-274">**Example**</span></span>

`SqlServer.TAN(45.0)`
  
## <a name="see-also"></a><span data-ttu-id="52776-275">Consulte también</span><span class="sxs-lookup"><span data-stu-id="52776-275">See also</span></span>

- [<span data-ttu-id="52776-276">Funciones matemáticas (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="52776-276">Mathematical Functions (Transact-SQL)</span></span>](/sql/t-sql/functions/mathematical-functions-transact-sql)
- [<span data-ttu-id="52776-277">SqlClient para las funciones de Entity Framework</span><span class="sxs-lookup"><span data-stu-id="52776-277">SqlClient for Entity Framework Functions</span></span>](sqlclient-for-ef-functions.md)
