---
description: 'Más información acerca de: funciones matemáticas'
title: Funciones matemáticas
ms.date: 03/30/2017
ms.assetid: b040c7cb-156d-40f2-9152-61065b18148c
ms.openlocfilehash: 6bf1f116d6d88a8a188dc31cab91fbf26bdaea36
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795032"
---
# <a name="mathematical-functions"></a><span data-ttu-id="0851b-103">Funciones matemáticas</span><span class="sxs-lookup"><span data-stu-id="0851b-103">Mathematical Functions</span></span>

<span data-ttu-id="0851b-104">El Proveedor de datos .NET Framework para SQL Server (SqlClient) proporciona funciones matemáticas que realizan cálculos con los valores de entrada que se proporcionan como argumentos y devuelven un resultado numérico.</span><span class="sxs-lookup"><span data-stu-id="0851b-104">The .NET Framework Data Provider for SQL Server (SqlClient) provides math functions that perform calculations on input values that are provided as arguments, and return a numeric value result.</span></span> <span data-ttu-id="0851b-105">Estas funciones están en el espacio de nombres SqlServer, que está disponible al utilizar SqlClient.</span><span class="sxs-lookup"><span data-stu-id="0851b-105">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="0851b-106">La propiedad del espacio de nombres de un proveedor permite a Entity Framework detectar qué prefijo usa este proveedor para estructuras concretas, como tipos y funciones.</span><span class="sxs-lookup"><span data-stu-id="0851b-106">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span> <span data-ttu-id="0851b-107">En la tabla siguiente se describen las funciones matemáticas de SqlClient.</span><span class="sxs-lookup"><span data-stu-id="0851b-107">The following table describes the SqlClient math functions.</span></span>  
  
## <a name="absexpression"></a><span data-ttu-id="0851b-108">ABS (expresión)</span><span class="sxs-lookup"><span data-stu-id="0851b-108">ABS(expression)</span></span>

<span data-ttu-id="0851b-109">Lleva a cabo la función que devuelve el valor absoluto.</span><span class="sxs-lookup"><span data-stu-id="0851b-109">Performs the absolute value function.</span></span>

<span data-ttu-id="0851b-110">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="0851b-110">**Arguments**</span></span>

<span data-ttu-id="0851b-111">`expression`: valor de tipo`Int32`,`Int64`, `Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="0851b-111">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="0851b-112">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="0851b-112">**Return Value**</span></span>

<span data-ttu-id="0851b-113">Valor absoluto de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="0851b-113">The absolute value of the specified expression.</span></span>

<span data-ttu-id="0851b-114">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="0851b-114">**Example**</span></span>

`SqlServer.ABS(-2)`

## <a name="acosexpression"></a><span data-ttu-id="0851b-115">ACOS (expresión)</span><span class="sxs-lookup"><span data-stu-id="0851b-115">ACOS(expression)</span></span>

<span data-ttu-id="0851b-116">Devuelve el valor del arcocoseno de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="0851b-116">Returns the arccosine value of the specified expression.</span></span>

<span data-ttu-id="0851b-117">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="0851b-117">**Arguments**</span></span>

<span data-ttu-id="0851b-118">`expression`: un valor `Double`.</span><span class="sxs-lookup"><span data-stu-id="0851b-118">`expression`: A `Double`.</span></span>

<span data-ttu-id="0851b-119">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="0851b-119">**Return Value**</span></span>

<span data-ttu-id="0851b-120">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="0851b-120">A `Double`.</span></span>

<span data-ttu-id="0851b-121">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="0851b-121">**Example**</span></span>

`SqlServer.ACOS(.9)`

## <a name="asinexpression"></a><span data-ttu-id="0851b-122">ASIN (expresión)</span><span class="sxs-lookup"><span data-stu-id="0851b-122">ASIN(expression)</span></span>

<span data-ttu-id="0851b-123">Devuelve el valor del arcoseno de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="0851b-123">Returns the arcsine value of the specified expression.</span></span>

<span data-ttu-id="0851b-124">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="0851b-124">**Arguments**</span></span>

<span data-ttu-id="0851b-125">`expression`: un valor `Double`.</span><span class="sxs-lookup"><span data-stu-id="0851b-125">`expression`: A `Double`.</span></span>

<span data-ttu-id="0851b-126">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="0851b-126">**Return Value**</span></span>

<span data-ttu-id="0851b-127">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="0851b-127">A `Double`.</span></span>

<span data-ttu-id="0851b-128">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="0851b-128">**Example**</span></span>

`SqlServer.ASIN(.9)`

## <a name="atanexpression"></a><span data-ttu-id="0851b-129">ATAN (expresión)</span><span class="sxs-lookup"><span data-stu-id="0851b-129">ATAN(expression)</span></span>

<span data-ttu-id="0851b-130">Devuelve el valor del arcotangente de la expresión numérica especificada.</span><span class="sxs-lookup"><span data-stu-id="0851b-130">Returns the arctangent value of the specified numeric expression.</span></span>

<span data-ttu-id="0851b-131">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="0851b-131">**Arguments**</span></span>

<span data-ttu-id="0851b-132">`expression`: un valor `Double`.</span><span class="sxs-lookup"><span data-stu-id="0851b-132">`expression`: A `Double`.</span></span>

<span data-ttu-id="0851b-133">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="0851b-133">**Return Value**</span></span>

<span data-ttu-id="0851b-134">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="0851b-134">A `Double`.</span></span>

<span data-ttu-id="0851b-135">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="0851b-135">**Example**</span></span>

`SqlServer.ATAN(9)`

## <a name="atn2expression-expression"></a><span data-ttu-id="0851b-136">ATN2 (expresión, expresión)</span><span class="sxs-lookup"><span data-stu-id="0851b-136">ATN2(expression, expression)</span></span>

<span data-ttu-id="0851b-137">Devuelve el ángulo, en radianes, cuya tangente se encuentra entre las dos expresiones numéricas especificadas.</span><span class="sxs-lookup"><span data-stu-id="0851b-137">Returns the angle, in radians, whose tangent is between the two specified numeric expressions.</span></span>

<span data-ttu-id="0851b-138">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="0851b-138">**Arguments**</span></span>

<span data-ttu-id="0851b-139">`expression`: un valor `Double`.</span><span class="sxs-lookup"><span data-stu-id="0851b-139">`expression`: A `Double`.</span></span>

<span data-ttu-id="0851b-140">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="0851b-140">**Return Value**</span></span>

<span data-ttu-id="0851b-141">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="0851b-141">A `Double`.</span></span>

<span data-ttu-id="0851b-142">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="0851b-142">**Example**</span></span>

`SqlServer.ATN2(9, 8)`

## <a name="ceilingexpression"></a><span data-ttu-id="0851b-143">CEILING (expresión)</span><span class="sxs-lookup"><span data-stu-id="0851b-143">CEILING(expression)</span></span>

<span data-ttu-id="0851b-144">Convierte la expresión especificada al número entero más pequeño mayor o igual que él.</span><span class="sxs-lookup"><span data-stu-id="0851b-144">Converts the specified expression to the smallest integer that is greater than or equal to it.</span></span>

<span data-ttu-id="0851b-145">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="0851b-145">**Arguments**</span></span>

<span data-ttu-id="0851b-146">`expression`: valor de tipo`Int32`,`Int64`, `Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="0851b-146">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="0851b-147">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="0851b-147">**Return Value**</span></span>

<span data-ttu-id="0851b-148">`Int32`, `Int64` , `Double` O `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="0851b-148">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="0851b-149">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="0851b-149">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_ceiling)]

## <a name="cosexpression"></a><span data-ttu-id="0851b-150">COS (expresión)</span><span class="sxs-lookup"><span data-stu-id="0851b-150">COS(expression)</span></span>

<span data-ttu-id="0851b-151">Calcula el coseno trigonométrico del ángulo especificado, en radianes.</span><span class="sxs-lookup"><span data-stu-id="0851b-151">Calculates the trigonometric cosine of the specified angle in radians.</span></span>

<span data-ttu-id="0851b-152">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="0851b-152">**Arguments**</span></span>

<span data-ttu-id="0851b-153">`expression`: un valor `Double`.</span><span class="sxs-lookup"><span data-stu-id="0851b-153">`expression`: A `Double`.</span></span>

<span data-ttu-id="0851b-154">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="0851b-154">**Return Value**</span></span>

<span data-ttu-id="0851b-155">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="0851b-155">A `Double`.</span></span>

<span data-ttu-id="0851b-156">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="0851b-156">**Example**</span></span>

`SqlServer.COS(45)`

## <a name="cotexpression"></a><span data-ttu-id="0851b-157">COT (expresión)</span><span class="sxs-lookup"><span data-stu-id="0851b-157">COT(expression)</span></span>

<span data-ttu-id="0851b-158">Calcula la cotangente trigonométrica del ángulo especificado, en radianes.</span><span class="sxs-lookup"><span data-stu-id="0851b-158">Calculates the trigonometric cotangent of the specified angle in radians.</span></span>

<span data-ttu-id="0851b-159">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="0851b-159">**Arguments**</span></span>

<span data-ttu-id="0851b-160">`expression`: un valor `Double`.</span><span class="sxs-lookup"><span data-stu-id="0851b-160">`expression`: A `Double`.</span></span>

<span data-ttu-id="0851b-161">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="0851b-161">**Return Value**</span></span>

<span data-ttu-id="0851b-162">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="0851b-162">A `Double`.</span></span>

<span data-ttu-id="0851b-163">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="0851b-163">**Example**</span></span>

`SqlServer.COT(60)`
  
## <a name="degreesradians"></a><span data-ttu-id="0851b-164">GRADOS (radianes)</span><span class="sxs-lookup"><span data-stu-id="0851b-164">DEGREES(radians)</span></span>

<span data-ttu-id="0851b-165">Devuelve el ángulo correspondiente en grados.</span><span class="sxs-lookup"><span data-stu-id="0851b-165">Returns the corresponding angle in degrees.</span></span>

<span data-ttu-id="0851b-166">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="0851b-166">**Arguments**</span></span>

<span data-ttu-id="0851b-167">`expression`: valor de tipo`Int32`,`Int64`, `Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="0851b-167">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="0851b-168">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="0851b-168">**Return Value**</span></span>

<span data-ttu-id="0851b-169">`Int32`, `Int64` , `Double` O `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="0851b-169">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="0851b-170">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="0851b-170">**Example**</span></span>

`SqlServer.DEGREES(3.1)`

## <a name="expexpression"></a><span data-ttu-id="0851b-171">EXP (expresión)</span><span class="sxs-lookup"><span data-stu-id="0851b-171">EXP(expression)</span></span>

<span data-ttu-id="0851b-172">Calcula el valor exponencial de la expresión numérica especificada.</span><span class="sxs-lookup"><span data-stu-id="0851b-172">Calculates the exponential value of a specified numeric expression.</span></span>

<span data-ttu-id="0851b-173">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="0851b-173">**Arguments**</span></span>

<span data-ttu-id="0851b-174">`expression`: un valor `Double`.</span><span class="sxs-lookup"><span data-stu-id="0851b-174">`expression`: A `Double`.</span></span>

<span data-ttu-id="0851b-175">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="0851b-175">**Return Value**</span></span>

<span data-ttu-id="0851b-176">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="0851b-176">A `Double`.</span></span>

<span data-ttu-id="0851b-177">**Ejemplo** de `SqlServer.EXP(1)`</span><span class="sxs-lookup"><span data-stu-id="0851b-177">**Example** `SqlServer.EXP(1)`</span></span>

## <a name="floorexpression"></a><span data-ttu-id="0851b-178">FLOOR (expresión)</span><span class="sxs-lookup"><span data-stu-id="0851b-178">FLOOR(expression)</span></span>

<span data-ttu-id="0851b-179">Convierte la expresión especificada al número entero más grande que sea menor o igual que ella.</span><span class="sxs-lookup"><span data-stu-id="0851b-179">Converts the specified expression to the largest integer less than or equal to it.</span></span>

<span data-ttu-id="0851b-180">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="0851b-180">**Arguments**</span></span>

<span data-ttu-id="0851b-181">`expression`: un valor `Double`.</span><span class="sxs-lookup"><span data-stu-id="0851b-181">`expression`: A `Double`.</span></span>

<span data-ttu-id="0851b-182">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="0851b-182">**Return Value**</span></span>

<span data-ttu-id="0851b-183">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="0851b-183">A `Double`.</span></span>

<span data-ttu-id="0851b-184">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="0851b-184">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_floor)]

## <a name="logexpression"></a><span data-ttu-id="0851b-185">LOG (expresión)</span><span class="sxs-lookup"><span data-stu-id="0851b-185">LOG(expression)</span></span>

<span data-ttu-id="0851b-186">Calcula el logaritmo natural de la expresión `float` especificada.</span><span class="sxs-lookup"><span data-stu-id="0851b-186">Calculates the natural logarithm of the specified `float` expression.</span></span>

<span data-ttu-id="0851b-187">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="0851b-187">**Arguments**</span></span>

<span data-ttu-id="0851b-188">`expression`: un valor `Double`.</span><span class="sxs-lookup"><span data-stu-id="0851b-188">`expression`: A `Double`.</span></span>

<span data-ttu-id="0851b-189">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="0851b-189">**Return Value**</span></span>

<span data-ttu-id="0851b-190">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="0851b-190">A `Double`.</span></span>

<span data-ttu-id="0851b-191">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="0851b-191">**Example**</span></span>

`SqlServer.LOG(100)`

## <a name="log10expression"></a><span data-ttu-id="0851b-192">LOG10 (expresión)</span><span class="sxs-lookup"><span data-stu-id="0851b-192">LOG10(expression)</span></span>

<span data-ttu-id="0851b-193">Devuelve el logaritmo en base 10 de la expresión `Double` especificada.</span><span class="sxs-lookup"><span data-stu-id="0851b-193">Returns the base-10 logarithm of the specified `Double` expression.</span></span>

<span data-ttu-id="0851b-194">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="0851b-194">**Arguments**</span></span>

<span data-ttu-id="0851b-195">`expression`: un valor `Double`.</span><span class="sxs-lookup"><span data-stu-id="0851b-195">`expression`: A `Double`.</span></span>

<span data-ttu-id="0851b-196">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="0851b-196">**Return Value**</span></span>

<span data-ttu-id="0851b-197">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="0851b-197">A `Double`.</span></span>

<span data-ttu-id="0851b-198">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="0851b-198">**Example**</span></span>

`SqlServer.LOG10(100)`

## <a name="pi"></a><span data-ttu-id="0851b-199">PI ()</span><span class="sxs-lookup"><span data-stu-id="0851b-199">PI()</span></span>

<span data-ttu-id="0851b-200">Devuelve el valor constante de Pi como un `Double`.</span><span class="sxs-lookup"><span data-stu-id="0851b-200">Returns the constant value of pi as a `Double`.</span></span>

<span data-ttu-id="0851b-201">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="0851b-201">**Return Value**</span></span>

<span data-ttu-id="0851b-202">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="0851b-202">A `Double`.</span></span>

<span data-ttu-id="0851b-203">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="0851b-203">**Example**</span></span>

`SqlServer.PI()`

## <a name="powernumeric_expression-power_expression"></a><span data-ttu-id="0851b-204">POWER (numeric_expression, power_expression)</span><span class="sxs-lookup"><span data-stu-id="0851b-204">POWER(numeric_expression, power_expression)</span></span>

<span data-ttu-id="0851b-205">Calcula el valor de la expresión especificada elevada a la potencia indicada.</span><span class="sxs-lookup"><span data-stu-id="0851b-205">Calculates the value of a specified expression to a specified power.</span></span>

<span data-ttu-id="0851b-206">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="0851b-206">**Arguments**</span></span>

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="0851b-207">`Int32`, `Int64` , `Double` O `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="0851b-207">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>|
|`power_expression`| <span data-ttu-id="0851b-208">`Double`Que representa la potencia a la que se eleva el `numeric_expression` .</span><span class="sxs-lookup"><span data-stu-id="0851b-208">A `Double` that represents the power to which to raise the `numeric_expression`.</span></span>|

<span data-ttu-id="0851b-209">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="0851b-209">**Return Value**</span></span>

<span data-ttu-id="0851b-210">Valor de la `numeric_expression` especificada a la `power_expression` especificada.</span><span class="sxs-lookup"><span data-stu-id="0851b-210">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span>

<span data-ttu-id="0851b-211">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="0851b-211">**Example**</span></span>

`SqlServer.POWER(2,7)`

## <a name="radiansexpression"></a><span data-ttu-id="0851b-212">RADIAnes (expresión)</span><span class="sxs-lookup"><span data-stu-id="0851b-212">RADIANS(expression)</span></span>

<span data-ttu-id="0851b-213">Convierte los grados en radianes.</span><span class="sxs-lookup"><span data-stu-id="0851b-213">Converts degrees to radians.</span></span>

<span data-ttu-id="0851b-214">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="0851b-214">**Arguments**</span></span>

<span data-ttu-id="0851b-215">`expression`: valor de tipo`Int32`,`Int64`, `Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="0851b-215">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="0851b-216">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="0851b-216">**Return Value**</span></span>

<span data-ttu-id="0851b-217">`Int32`, `Int64` , `Double` O `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="0851b-217">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="0851b-218">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="0851b-218">**Example**</span></span>

`SqlServer.RADIANS(360.0)`

## <a name="randseed"></a><span data-ttu-id="0851b-219">RAND ([SEED])</span><span class="sxs-lookup"><span data-stu-id="0851b-219">RAND([seed])</span></span>

<span data-ttu-id="0851b-220">Devuelve un valor aleatorio de 0 a 1.</span><span class="sxs-lookup"><span data-stu-id="0851b-220">Returns a random value from 0 through 1.</span></span>

<span data-ttu-id="0851b-221">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="0851b-221">**Arguments**</span></span>

<span data-ttu-id="0851b-222">Valor de inicialización como `Int32` .</span><span class="sxs-lookup"><span data-stu-id="0851b-222">The seed value as an `Int32`.</span></span> <span data-ttu-id="0851b-223">Si la inicialización no se especifica, el motor de base de datos de SQL Server asigna uno de forma aleatoria.</span><span class="sxs-lookup"><span data-stu-id="0851b-223">If the seed is not specified, the SQL Server Database Engine assigns a seed value at random.</span></span> <span data-ttu-id="0851b-224">Para un valor de inicialización especificado, el resultado devuelto es siempre el mismo.</span><span class="sxs-lookup"><span data-stu-id="0851b-224">For a specified seed value, the result returned is always the same.</span></span>

<span data-ttu-id="0851b-225">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="0851b-225">**Return Value**</span></span>

<span data-ttu-id="0851b-226">Valor `Double` aleatorio de 0 a 1.</span><span class="sxs-lookup"><span data-stu-id="0851b-226">A random `Double` value from 0 through 1.</span></span>

<span data-ttu-id="0851b-227">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="0851b-227">**Example**</span></span>

`SqlServer.RAND()`
  
## <a name="roundnumeric_expression-lengthfunction"></a><span data-ttu-id="0851b-228">ROUND (numeric_expression, longitud [, función])</span><span class="sxs-lookup"><span data-stu-id="0851b-228">ROUND(numeric_expression, length[,function])</span></span>

<span data-ttu-id="0851b-229">Devuelve una expresión numérica, redondeada a la longitud o precisión especificadas.</span><span class="sxs-lookup"><span data-stu-id="0851b-229">Returns a numeric expression, rounded to the specified length or precision.</span></span>

<span data-ttu-id="0851b-230">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="0851b-230">**Arguments**</span></span>

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="0851b-231">`Int32`, `Int64` , `Double` O `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="0851b-231">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>
|`length`| <span data-ttu-id="0851b-232">Valor `Int32` que representa la precisión a la que se va a redondear `numeric_expression`.</span><span class="sxs-lookup"><span data-stu-id="0851b-232">An `Int32` that represents the precision to which `numeric_expression` is to be rounded.</span></span> <span data-ttu-id="0851b-233">Si `length` es un número positivo, `numeric_expression` se redondea al número de posiciones decimales que especifica `length`.</span><span class="sxs-lookup"><span data-stu-id="0851b-233">When `length` is a positive number, `numeric_expression` is rounded to the number of decimal positions specified by `length`.</span></span> <span data-ttu-id="0851b-234">Si `length` es un número negativo, `numeric_expression` se redondea a la izquierda del separador decimal, según se especifica en `length`.</span><span class="sxs-lookup"><span data-stu-id="0851b-234">When `length` is a negative number, `numeric_expression` is rounded on the left side of the decimal point, as specified by `length`.</span></span>|
|`function` | <span data-ttu-id="0851b-235">Opcional.</span><span class="sxs-lookup"><span data-stu-id="0851b-235">Optional.</span></span> <span data-ttu-id="0851b-236">`Int32`Que representa el tipo de operación que se va a realizar.</span><span class="sxs-lookup"><span data-stu-id="0851b-236">An `Int32` that represents the type of operation to perform.</span></span> <span data-ttu-id="0851b-237">Cuando se omite la función o tiene un valor de 0 (valor predeterminado), `numeric_expression` se redondea.</span><span class="sxs-lookup"><span data-stu-id="0851b-237">When function is omitted or has a value of 0 (default), `numeric_expression` is rounded.</span></span> <span data-ttu-id="0851b-238">Cuando se especifica un valor distinto de 0, `numeric_expression` se trunca.</span><span class="sxs-lookup"><span data-stu-id="0851b-238">When a value other than 0 is specified, `numeric_expression` is truncated.</span></span> |

<span data-ttu-id="0851b-239">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="0851b-239">**Return Value**</span></span>

<span data-ttu-id="0851b-240">Valor de la `numeric_expression` especificada a la `power_expression` especificada.</span><span class="sxs-lookup"><span data-stu-id="0851b-240">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span>

<span data-ttu-id="0851b-241">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="0851b-241">**Example**</span></span>

`SqlServer.ROUND(748.58, -3)`

## <a name="signexpression"></a><span data-ttu-id="0851b-242">SIGN (expresión)</span><span class="sxs-lookup"><span data-stu-id="0851b-242">SIGN(expression)</span></span>

<span data-ttu-id="0851b-243">Devuelve el signo positivo (+1), cero (0) o negativo (-1) de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="0851b-243">Returns the positive (+1), zero (0), or negative (-1) sign of the specified expression.</span></span>

<span data-ttu-id="0851b-244">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="0851b-244">**Arguments**</span></span>

<span data-ttu-id="0851b-245">`expression`: `Int32`, `Int64`, `Double` o `Decimal`</span><span class="sxs-lookup"><span data-stu-id="0851b-245">`expression`: `Int32`, `Int64`, `Double`, or `Decimal`</span></span>

<span data-ttu-id="0851b-246">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="0851b-246">**Return Value**</span></span>

<span data-ttu-id="0851b-247">`Int32`, `Int64` , `Double` O `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="0851b-247">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="0851b-248">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="0851b-248">**Example**</span></span>

`SqlServer.SIGN(-10)`

## <a name="sinexpression"></a><span data-ttu-id="0851b-249">SIN (expresión)</span><span class="sxs-lookup"><span data-stu-id="0851b-249">SIN(expression)</span></span>

<span data-ttu-id="0851b-250">Calcula el seno trigonométrico de un ángulo especificado, en radianes, y devuelve una expresión de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="0851b-250">Calculates the trigonometric sine of the specified angle in radians, and returns a `Double` expression.</span></span>

<span data-ttu-id="0851b-251">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="0851b-251">**Arguments**</span></span>

<span data-ttu-id="0851b-252">`expression`: un valor `Double`.</span><span class="sxs-lookup"><span data-stu-id="0851b-252">`expression`: A `Double`.</span></span>

<span data-ttu-id="0851b-253">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="0851b-253">**Return Value**</span></span>

<span data-ttu-id="0851b-254">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="0851b-254">A `Double`.</span></span>

<span data-ttu-id="0851b-255">**Ejemplo** de `SqlServer.SIN(20)`</span><span class="sxs-lookup"><span data-stu-id="0851b-255">**Example** `SqlServer.SIN(20)`</span></span>

## <a name="sqrtexpression"></a><span data-ttu-id="0851b-256">SQRT (expresión)</span><span class="sxs-lookup"><span data-stu-id="0851b-256">SQRT(expression)</span></span>

<span data-ttu-id="0851b-257">Devuelve la raíz cuadrada de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="0851b-257">Returns the square root of the specified expression.</span></span>

<span data-ttu-id="0851b-258">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="0851b-258">**Arguments**</span></span>

<span data-ttu-id="0851b-259">`expression`: un valor `Double`.</span><span class="sxs-lookup"><span data-stu-id="0851b-259">`expression`: A `Double`.</span></span>

<span data-ttu-id="0851b-260">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="0851b-260">**Return Value**</span></span>

<span data-ttu-id="0851b-261">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="0851b-261">A `Double`.</span></span>

<span data-ttu-id="0851b-262">**Ejemplo** de `SqlServer.SQRT(3600)`</span><span class="sxs-lookup"><span data-stu-id="0851b-262">**Example** `SqlServer.SQRT(3600)`</span></span>

## <a name="squareexpression"></a><span data-ttu-id="0851b-263">SQUARE (expresión)</span><span class="sxs-lookup"><span data-stu-id="0851b-263">SQUARE(expression)</span></span>

<span data-ttu-id="0851b-264">Devuelve la raíz cuadrada de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="0851b-264">Returns the square of the specified expression.</span></span>

<span data-ttu-id="0851b-265">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="0851b-265">**Arguments**</span></span>

<span data-ttu-id="0851b-266">`expression`: un valor `Double`.</span><span class="sxs-lookup"><span data-stu-id="0851b-266">`expression`: A `Double`.</span></span>

<span data-ttu-id="0851b-267">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="0851b-267">**Return Value**</span></span>

<span data-ttu-id="0851b-268">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="0851b-268">A `Double`.</span></span>

<span data-ttu-id="0851b-269">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="0851b-269">**Example**</span></span>

`SqlServer.SQUARE(25)`

## <a name="tanexpression"></a><span data-ttu-id="0851b-270">TAN (expresión)</span><span class="sxs-lookup"><span data-stu-id="0851b-270">TAN(expression)</span></span>

<span data-ttu-id="0851b-271">Calcula la tangente de una expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="0851b-271">Calculates the tangent of a specified expression.</span></span>

<span data-ttu-id="0851b-272">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="0851b-272">**Arguments**</span></span>

<span data-ttu-id="0851b-273">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="0851b-273">`expression`: `Double`</span></span>

<span data-ttu-id="0851b-274">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="0851b-274">**Return Value**</span></span>

`Double`

<span data-ttu-id="0851b-275">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="0851b-275">**Example**</span></span>

`SqlServer.TAN(45.0)`
  
## <a name="see-also"></a><span data-ttu-id="0851b-276">Vea también</span><span class="sxs-lookup"><span data-stu-id="0851b-276">See also</span></span>

- [<span data-ttu-id="0851b-277">Funciones matemáticas (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0851b-277">Mathematical Functions (Transact-SQL)</span></span>](/sql/t-sql/functions/mathematical-functions-transact-sql)
- [<span data-ttu-id="0851b-278">SqlClient para las funciones de Entity Framework</span><span class="sxs-lookup"><span data-stu-id="0851b-278">SqlClient for Entity Framework Functions</span></span>](sqlclient-for-ef-functions.md)
