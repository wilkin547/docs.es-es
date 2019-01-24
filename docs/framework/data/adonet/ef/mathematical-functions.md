---
title: Funciones matemáticas
ms.date: 03/30/2017
ms.assetid: b040c7cb-156d-40f2-9152-61065b18148c
ms.openlocfilehash: d8d766cb1416a9a07476175364fe568d81fd9b25
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54652272"
---
# <a name="mathematical-functions"></a><span data-ttu-id="28ae7-102">Funciones matemáticas</span><span class="sxs-lookup"><span data-stu-id="28ae7-102">Mathematical Functions</span></span>

<span data-ttu-id="28ae7-103">El Proveedor de datos .NET Framework para SQL Server (SqlClient) proporciona funciones matemáticas que realizan cálculos con los valores de entrada que se proporcionan como argumentos y devuelven un resultado numérico.</span><span class="sxs-lookup"><span data-stu-id="28ae7-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides math functions that perform calculations on input values that are provided as arguments, and return a numeric value result.</span></span> <span data-ttu-id="28ae7-104">Estas funciones están en el espacio de nombres SqlServer, que está disponible al utilizar SqlClient.</span><span class="sxs-lookup"><span data-stu-id="28ae7-104">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="28ae7-105">La propiedad del espacio de nombres de un proveedor permite a Entity Framework detectar qué prefijo usa este proveedor para estructuras concretas, como tipos y funciones.</span><span class="sxs-lookup"><span data-stu-id="28ae7-105">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span> <span data-ttu-id="28ae7-106">En la tabla siguiente se describe las funciones matemáticas de SqlClient.</span><span class="sxs-lookup"><span data-stu-id="28ae7-106">The following table describes the SqlClient math functions.</span></span>  
  
## <a name="absexpression"></a><span data-ttu-id="28ae7-107">ABS(Expression)</span><span class="sxs-lookup"><span data-stu-id="28ae7-107">ABS(expression)</span></span>

<span data-ttu-id="28ae7-108">Lleva a cabo la función que devuelve el valor absoluto.</span><span class="sxs-lookup"><span data-stu-id="28ae7-108">Performs the absolute value function.</span></span>

<span data-ttu-id="28ae7-109">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="28ae7-109">**Arguments**</span></span>

<span data-ttu-id="28ae7-110">`expression`: Un `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-110">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="28ae7-111">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="28ae7-111">**Return Value**</span></span>

<span data-ttu-id="28ae7-112">Valor absoluto de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="28ae7-112">The absolute value of the specified expression.</span></span>

<span data-ttu-id="28ae7-113">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="28ae7-113">**Example**</span></span>

`SqlServer.ABS(-2)`

## <a name="acosexpression"></a><span data-ttu-id="28ae7-114">ACOS(Expression)</span><span class="sxs-lookup"><span data-stu-id="28ae7-114">ACOS(expression)</span></span>

<span data-ttu-id="28ae7-115">Devuelve el valor del arcocoseno de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="28ae7-115">Returns the arccosine value of the specified expression.</span></span>

<span data-ttu-id="28ae7-116">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="28ae7-116">**Arguments**</span></span>

<span data-ttu-id="28ae7-117">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-117">`expression`: A `Double`.</span></span>

<span data-ttu-id="28ae7-118">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="28ae7-118">**Return Value**</span></span>

<span data-ttu-id="28ae7-119">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-119">A `Double`.</span></span>

<span data-ttu-id="28ae7-120">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="28ae7-120">**Example**</span></span>

`SqlServer.ACOS(.9)`

## <a name="asinexpression"></a><span data-ttu-id="28ae7-121">ASIN(Expression)</span><span class="sxs-lookup"><span data-stu-id="28ae7-121">ASIN(expression)</span></span>

<span data-ttu-id="28ae7-122">Devuelve el valor del arcoseno de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="28ae7-122">Returns the arcsine value of the specified expression.</span></span>

<span data-ttu-id="28ae7-123">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="28ae7-123">**Arguments**</span></span>

<span data-ttu-id="28ae7-124">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-124">`expression`: A `Double`.</span></span>

<span data-ttu-id="28ae7-125">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="28ae7-125">**Return Value**</span></span>

<span data-ttu-id="28ae7-126">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-126">A `Double`.</span></span>

<span data-ttu-id="28ae7-127">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="28ae7-127">**Example**</span></span>

`SqlServer.ASIN(.9)`

## <a name="atanexpression"></a><span data-ttu-id="28ae7-128">ATAN(Expression)</span><span class="sxs-lookup"><span data-stu-id="28ae7-128">ATAN(expression)</span></span>

<span data-ttu-id="28ae7-129">Devuelve el valor del arcotangente de la expresión numérica especificada.</span><span class="sxs-lookup"><span data-stu-id="28ae7-129">Returns the arctangent value of the specified numeric expression.</span></span>

<span data-ttu-id="28ae7-130">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="28ae7-130">**Arguments**</span></span>

<span data-ttu-id="28ae7-131">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-131">`expression`: A `Double`.</span></span>

<span data-ttu-id="28ae7-132">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="28ae7-132">**Return Value**</span></span>

<span data-ttu-id="28ae7-133">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-133">A `Double`.</span></span>

<span data-ttu-id="28ae7-134">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="28ae7-134">**Example**</span></span>

`SqlServer.ATAN(9)`

## <a name="atn2expression-expression"></a><span data-ttu-id="28ae7-135">ATN2(Expression, Expression)</span><span class="sxs-lookup"><span data-stu-id="28ae7-135">ATN2(expression, expression)</span></span>

<span data-ttu-id="28ae7-136">Devuelve el ángulo, en radianes, cuya tangente se encuentra entre las dos expresiones numéricas especificadas.</span><span class="sxs-lookup"><span data-stu-id="28ae7-136">Returns the angle, in radians, whose tangent is between the two specified numeric expressions.</span></span>

<span data-ttu-id="28ae7-137">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="28ae7-137">**Arguments**</span></span>

<span data-ttu-id="28ae7-138">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-138">`expression`: A `Double`.</span></span>

<span data-ttu-id="28ae7-139">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="28ae7-139">**Return Value**</span></span>

<span data-ttu-id="28ae7-140">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-140">A `Double`.</span></span>

<span data-ttu-id="28ae7-141">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="28ae7-141">**Example**</span></span>

`SqlServer.ATN2(9, 8)`
 
## <a name="ceilingexpression"></a><span data-ttu-id="28ae7-142">CEILING(Expression)</span><span class="sxs-lookup"><span data-stu-id="28ae7-142">CEILING(expression)</span></span>

<span data-ttu-id="28ae7-143">Convierte la expresión especificada al número entero más pequeño mayor o igual que él.</span><span class="sxs-lookup"><span data-stu-id="28ae7-143">Converts the specified expression to the smallest integer that is greater than or equal to it.</span></span>

<span data-ttu-id="28ae7-144">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="28ae7-144">**Arguments**</span></span>

<span data-ttu-id="28ae7-145">`expression`: Un `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-145">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="28ae7-146">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="28ae7-146">**Return Value**</span></span>

<span data-ttu-id="28ae7-147">Un `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-147">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="28ae7-148">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="28ae7-148">**Example**</span></span> 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_ceiling)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_ceiling)]

## <a name="cosexpression"></a><span data-ttu-id="28ae7-149">COS(Expression)</span><span class="sxs-lookup"><span data-stu-id="28ae7-149">COS(expression)</span></span>

<span data-ttu-id="28ae7-150">Calcula el coseno trigonométrico del ángulo especificado, en radianes.</span><span class="sxs-lookup"><span data-stu-id="28ae7-150">Calculates the trigonometric cosine of the specified angle in radians.</span></span> 

<span data-ttu-id="28ae7-151">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="28ae7-151">**Arguments**</span></span> 

<span data-ttu-id="28ae7-152">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-152">`expression`: A `Double`.</span></span> 

<span data-ttu-id="28ae7-153">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="28ae7-153">**Return Value**</span></span> 

<span data-ttu-id="28ae7-154">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-154">A `Double`.</span></span> 

<span data-ttu-id="28ae7-155">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="28ae7-155">**Example**</span></span> 

`SqlServer.COS(45)`

## <a name="cotexpression"></a><span data-ttu-id="28ae7-156">COT(Expression)</span><span class="sxs-lookup"><span data-stu-id="28ae7-156">COT(expression)</span></span>

<span data-ttu-id="28ae7-157">Calcula la cotangente trigonométrica del ángulo especificado, en radianes.</span><span class="sxs-lookup"><span data-stu-id="28ae7-157">Calculates the trigonometric cotangent of the specified angle in radians.</span></span> 

<span data-ttu-id="28ae7-158">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="28ae7-158">**Arguments**</span></span> 

<span data-ttu-id="28ae7-159">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-159">`expression`: A `Double`.</span></span> 

<span data-ttu-id="28ae7-160">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="28ae7-160">**Return Value**</span></span> 

<span data-ttu-id="28ae7-161">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-161">A `Double`.</span></span> 

<span data-ttu-id="28ae7-162">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="28ae7-162">**Example**</span></span> 

`SqlServer.COT(60)`
  
## <a name="degreesradians"></a><span data-ttu-id="28ae7-163">Degrees(RADIANS)</span><span class="sxs-lookup"><span data-stu-id="28ae7-163">DEGREES(radians)</span></span>

<span data-ttu-id="28ae7-164">Devuelve el ángulo correspondiente en grados.</span><span class="sxs-lookup"><span data-stu-id="28ae7-164">Returns the corresponding angle in degrees.</span></span> 

<span data-ttu-id="28ae7-165">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="28ae7-165">**Arguments**</span></span> 

<span data-ttu-id="28ae7-166">`expression`: Un `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-166">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="28ae7-167">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="28ae7-167">**Return Value**</span></span> 

<span data-ttu-id="28ae7-168">Un `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-168">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="28ae7-169">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="28ae7-169">**Example**</span></span> 

`SqlServer.DEGREES(3.1)`

## <a name="expexpression"></a><span data-ttu-id="28ae7-170">EXP(Expression)</span><span class="sxs-lookup"><span data-stu-id="28ae7-170">EXP(expression)</span></span>

<span data-ttu-id="28ae7-171">Calcula el valor exponencial de la expresión numérica especificada.</span><span class="sxs-lookup"><span data-stu-id="28ae7-171">Calculates the exponential value of a specified numeric expression.</span></span> 

<span data-ttu-id="28ae7-172">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="28ae7-172">**Arguments**</span></span> 

<span data-ttu-id="28ae7-173">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-173">`expression`: A `Double`.</span></span> 

<span data-ttu-id="28ae7-174">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="28ae7-174">**Return Value**</span></span> 

<span data-ttu-id="28ae7-175">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-175">A `Double`.</span></span> 

<span data-ttu-id="28ae7-176">**Ejemplo** `SqlServer.EXP(1)`</span><span class="sxs-lookup"><span data-stu-id="28ae7-176">**Example** `SqlServer.EXP(1)`</span></span>

## <a name="floorexpression"></a><span data-ttu-id="28ae7-177">Floor(Expression)</span><span class="sxs-lookup"><span data-stu-id="28ae7-177">FLOOR(expression)</span></span>

<span data-ttu-id="28ae7-178">Convierte la expresión especificada al número entero más grande que sea menor o igual que ella.</span><span class="sxs-lookup"><span data-stu-id="28ae7-178">Converts the specified expression to the largest integer less than or equal to it.</span></span> 

<span data-ttu-id="28ae7-179">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="28ae7-179">**Arguments**</span></span> 

<span data-ttu-id="28ae7-180">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-180">`expression`: A `Double`.</span></span> 

<span data-ttu-id="28ae7-181">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="28ae7-181">**Return Value**</span></span> 

<span data-ttu-id="28ae7-182">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-182">A `Double`.</span></span> 

<span data-ttu-id="28ae7-183">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="28ae7-183">**Example**</span></span> 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_floor)] 
[!code-sql[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_floor)]

## <a name="logexpression"></a><span data-ttu-id="28ae7-184">LOG(Expression)</span><span class="sxs-lookup"><span data-stu-id="28ae7-184">LOG(expression)</span></span>

<span data-ttu-id="28ae7-185">Calcula el logaritmo natural de la expresión `float` especificada.</span><span class="sxs-lookup"><span data-stu-id="28ae7-185">Calculates the natural logarithm of the specified `float` expression.</span></span> 

<span data-ttu-id="28ae7-186">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="28ae7-186">**Arguments**</span></span> 

<span data-ttu-id="28ae7-187">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-187">`expression`: A `Double`.</span></span> 

<span data-ttu-id="28ae7-188">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="28ae7-188">**Return Value**</span></span> 

<span data-ttu-id="28ae7-189">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-189">A `Double`.</span></span> 

<span data-ttu-id="28ae7-190">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="28ae7-190">**Example**</span></span> 

`SqlServer.LOG(100)`

## <a name="log10expression"></a><span data-ttu-id="28ae7-191">LOG10(Expression)</span><span class="sxs-lookup"><span data-stu-id="28ae7-191">LOG10(expression)</span></span>

<span data-ttu-id="28ae7-192">Devuelve el logaritmo en base 10 de la expresión `Double` especificada.</span><span class="sxs-lookup"><span data-stu-id="28ae7-192">Returns the base-10 logarithm of the specified `Double` expression.</span></span> 

<span data-ttu-id="28ae7-193">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="28ae7-193">**Arguments**</span></span> 

<span data-ttu-id="28ae7-194">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-194">`expression`: A `Double`.</span></span> 

<span data-ttu-id="28ae7-195">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="28ae7-195">**Return Value**</span></span> 

<span data-ttu-id="28ae7-196">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-196">A `Double`.</span></span> 

<span data-ttu-id="28ae7-197">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="28ae7-197">**Example**</span></span> 

`SqlServer.LOG10(100)`

## <a name="pi"></a><span data-ttu-id="28ae7-198">PI()</span><span class="sxs-lookup"><span data-stu-id="28ae7-198">PI()</span></span>

<span data-ttu-id="28ae7-199">Devuelve el valor constante de Pi como un `Double`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-199">Returns the constant value of pi as a `Double`.</span></span> 

<span data-ttu-id="28ae7-200">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="28ae7-200">**Return Value**</span></span> 

<span data-ttu-id="28ae7-201">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-201">A `Double`.</span></span> 

<span data-ttu-id="28ae7-202">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="28ae7-202">**Example**</span></span> 

`SqlServer.PI()`

## <a name="powernumericexpression-powerexpression"></a><span data-ttu-id="28ae7-203">POWER (numeric_expression, power_expression)</span><span class="sxs-lookup"><span data-stu-id="28ae7-203">POWER(numeric_expression, power_expression)</span></span>

<span data-ttu-id="28ae7-204">Calcula el valor de la expresión especificada elevada a la potencia indicada.</span><span class="sxs-lookup"><span data-stu-id="28ae7-204">Calculates the value of a specified expression to a specified power.</span></span>

<span data-ttu-id="28ae7-205">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="28ae7-205">**Arguments**</span></span> 

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="28ae7-206">Un `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-206">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>|
|`power_expression`| <span data-ttu-id="28ae7-207">Un `Double` que representa la potencia a la que se va a generar el `numeric_expression`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-207">A `Double` that represents the power to which to raise the `numeric_expression`.</span></span>| 

<span data-ttu-id="28ae7-208">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="28ae7-208">**Return Value**</span></span> 

<span data-ttu-id="28ae7-209">Valor de la `numeric_expression` especificada a la `power_expression` especificada.</span><span class="sxs-lookup"><span data-stu-id="28ae7-209">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span> 

<span data-ttu-id="28ae7-210">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="28ae7-210">**Example**</span></span> 

`SqlServer.POWER(2,7)`

## <a name="radiansexpression"></a><span data-ttu-id="28ae7-211">RADIANS(Expression)</span><span class="sxs-lookup"><span data-stu-id="28ae7-211">RADIANS(expression)</span></span>

<span data-ttu-id="28ae7-212">Convierte grados en radianes.</span><span class="sxs-lookup"><span data-stu-id="28ae7-212">Converts degrees to radians.</span></span> 

<span data-ttu-id="28ae7-213">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="28ae7-213">**Arguments**</span></span> 

<span data-ttu-id="28ae7-214">`expression`: Un `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-214">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="28ae7-215">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="28ae7-215">**Return Value**</span></span> 

<span data-ttu-id="28ae7-216">Un `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-216">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="28ae7-217">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="28ae7-217">**Example**</span></span> 

`SqlServer.RADIANS(360.0)`

## <a name="randseed"></a><span data-ttu-id="28ae7-218">RAND([SEED])</span><span class="sxs-lookup"><span data-stu-id="28ae7-218">RAND([seed])</span></span>

<span data-ttu-id="28ae7-219">Devuelve un valor aleatorio de 0 a 1.</span><span class="sxs-lookup"><span data-stu-id="28ae7-219">Returns a random value from 0 through 1.</span></span> 

<span data-ttu-id="28ae7-220">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="28ae7-220">**Arguments**</span></span> 

<span data-ttu-id="28ae7-221">El valor de inicialización como una `Int32`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-221">The seed value as an `Int32`.</span></span> <span data-ttu-id="28ae7-222">Si la inicialización no se especifica, el motor de base de datos de SQL Server asigna uno de forma aleatoria.</span><span class="sxs-lookup"><span data-stu-id="28ae7-222">If the seed is not specified, the SQL Server Database Engine assigns a seed value at random.</span></span> <span data-ttu-id="28ae7-223">Para un valor de inicialización especificado, el resultado devuelto es siempre el mismo.</span><span class="sxs-lookup"><span data-stu-id="28ae7-223">For a specified seed value, the result returned is always the same.</span></span>

<span data-ttu-id="28ae7-224">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="28ae7-224">**Return Value**</span></span> 

<span data-ttu-id="28ae7-225">Valor `Double` aleatorio de 0 a 1.</span><span class="sxs-lookup"><span data-stu-id="28ae7-225">A random `Double` value from 0 through 1.</span></span> 

<span data-ttu-id="28ae7-226">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="28ae7-226">**Example**</span></span> 

`SqlServer.RAND()`
  
## <a name="roundnumericexpression-lengthfunction"></a><span data-ttu-id="28ae7-227">Round(numeric_expression, Length[,Function])</span><span class="sxs-lookup"><span data-stu-id="28ae7-227">ROUND(numeric_expression, length[,function])</span></span>

<span data-ttu-id="28ae7-228">Devuelve una expresión numérica, redondeada a la longitud o precisión especificadas.</span><span class="sxs-lookup"><span data-stu-id="28ae7-228">Returns a numeric expression, rounded to the specified length or precision.</span></span> 

<span data-ttu-id="28ae7-229">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="28ae7-229">**Arguments**</span></span> 

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="28ae7-230">Un `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-230">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 
|`length`| <span data-ttu-id="28ae7-231">Valor `Int32` que representa la precisión a la que se va a redondear `numeric_expression`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-231">An `Int32` that represents the precision to which `numeric_expression` is to be rounded.</span></span> <span data-ttu-id="28ae7-232">Si `length` es un número positivo, `numeric_expression` se redondea al número de posiciones decimales que especifica `length`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-232">When `length` is a positive number, `numeric_expression` is rounded to the number of decimal positions specified by `length`.</span></span> <span data-ttu-id="28ae7-233">Si `length` es un número negativo, `numeric_expression` se redondea a la izquierda del separador decimal, según se especifica en `length`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-233">When `length` is a negative number, `numeric_expression` is rounded on the left side of the decimal point, as specified by `length`.</span></span>|
|`function` | <span data-ttu-id="28ae7-234">Opcional.</span><span class="sxs-lookup"><span data-stu-id="28ae7-234">Optional.</span></span> <span data-ttu-id="28ae7-235">Un `Int32` que representa el tipo de operación que se realiza.</span><span class="sxs-lookup"><span data-stu-id="28ae7-235">An `Int32` that represents the type of operation to perform.</span></span> <span data-ttu-id="28ae7-236">Cuando la función se omite o tiene un valor de 0 (valor predeterminado), `numeric_expression` se redondea.</span><span class="sxs-lookup"><span data-stu-id="28ae7-236">When function is omitted or has a value of 0 (default), `numeric_expression` is rounded.</span></span> <span data-ttu-id="28ae7-237">Si un valor distinto de 0 se especifica, `numeric_expression` se trunca.</span><span class="sxs-lookup"><span data-stu-id="28ae7-237">When a value other than 0 is specified, `numeric_expression` is truncated.</span></span> |

<span data-ttu-id="28ae7-238">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="28ae7-238">**Return Value**</span></span> 

<span data-ttu-id="28ae7-239">Valor de la `numeric_expression` especificada a la `power_expression` especificada.</span><span class="sxs-lookup"><span data-stu-id="28ae7-239">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span>

<span data-ttu-id="28ae7-240">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="28ae7-240">**Example**</span></span> 

`SqlServer.ROUND(748.58, -3)`

## <a name="signexpression"></a><span data-ttu-id="28ae7-241">Sign(Expression)</span><span class="sxs-lookup"><span data-stu-id="28ae7-241">SIGN(expression)</span></span> 

<span data-ttu-id="28ae7-242">Devuelve el signo positivo (+1), cero (0) o negativo (-1) de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="28ae7-242">Returns the positive (+1), zero (0), or negative (-1) sign of the specified expression.</span></span> 

<span data-ttu-id="28ae7-243">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="28ae7-243">**Arguments**</span></span> 

<span data-ttu-id="28ae7-244">`expression`: `Int32`, `Int64`, `Double` o `Decimal`</span><span class="sxs-lookup"><span data-stu-id="28ae7-244">`expression`: `Int32`, `Int64`, `Double`, or `Decimal`</span></span> 

<span data-ttu-id="28ae7-245">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="28ae7-245">**Return Value**</span></span> 

<span data-ttu-id="28ae7-246">Un `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-246">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="28ae7-247">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="28ae7-247">**Example**</span></span> 

`SqlServer.SIGN(-10)`

## <a name="sinexpression"></a><span data-ttu-id="28ae7-248">SIN(Expression)</span><span class="sxs-lookup"><span data-stu-id="28ae7-248">SIN(expression)</span></span>

<span data-ttu-id="28ae7-249">Calcula el seno trigonométrico de un ángulo especificado, en radianes, y devuelve una expresión de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-249">Calculates the trigonometric sine of the specified angle in radians, and returns a `Double` expression.</span></span> 

<span data-ttu-id="28ae7-250">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="28ae7-250">**Arguments**</span></span> 

<span data-ttu-id="28ae7-251">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-251">`expression`: A `Double`.</span></span> 

<span data-ttu-id="28ae7-252">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="28ae7-252">**Return Value**</span></span> 

<span data-ttu-id="28ae7-253">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-253">A `Double`.</span></span> 

<span data-ttu-id="28ae7-254">**Ejemplo** `SqlServer.SIN(20)`</span><span class="sxs-lookup"><span data-stu-id="28ae7-254">**Example** `SqlServer.SIN(20)`</span></span>

## <a name="sqrtexpression"></a><span data-ttu-id="28ae7-255">SQRT(Expression)</span><span class="sxs-lookup"><span data-stu-id="28ae7-255">SQRT(expression)</span></span>

<span data-ttu-id="28ae7-256">Devuelve la raíz cuadrada de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="28ae7-256">Returns the square root of the specified expression.</span></span> 

<span data-ttu-id="28ae7-257">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="28ae7-257">**Arguments**</span></span> 

<span data-ttu-id="28ae7-258">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-258">`expression`: A `Double`.</span></span> 

<span data-ttu-id="28ae7-259">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="28ae7-259">**Return Value**</span></span> 

<span data-ttu-id="28ae7-260">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-260">A `Double`.</span></span> 

<span data-ttu-id="28ae7-261">**Ejemplo** `SqlServer.SQRT(3600)`</span><span class="sxs-lookup"><span data-stu-id="28ae7-261">**Example** `SqlServer.SQRT(3600)`</span></span>

## <a name="squareexpression"></a><span data-ttu-id="28ae7-262">Square(Expression)</span><span class="sxs-lookup"><span data-stu-id="28ae7-262">SQUARE(expression)</span></span>

<span data-ttu-id="28ae7-263">Devuelve la raíz cuadrada de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="28ae7-263">Returns the square of the specified expression.</span></span> 

<span data-ttu-id="28ae7-264">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="28ae7-264">**Arguments**</span></span> 

<span data-ttu-id="28ae7-265">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-265">`expression`: A `Double`.</span></span> 

<span data-ttu-id="28ae7-266">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="28ae7-266">**Return Value**</span></span> 

<span data-ttu-id="28ae7-267">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="28ae7-267">A `Double`.</span></span> 

<span data-ttu-id="28ae7-268">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="28ae7-268">**Example**</span></span> 

`SqlServer.SQUARE(25)`

## <a name="tanexpression"></a><span data-ttu-id="28ae7-269">TAN(Expression)</span><span class="sxs-lookup"><span data-stu-id="28ae7-269">TAN(expression)</span></span>

<span data-ttu-id="28ae7-270">Calcula la tangente de una expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="28ae7-270">Calculates the tangent of a specified expression.</span></span>

<span data-ttu-id="28ae7-271">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="28ae7-271">**Arguments**</span></span> 

<span data-ttu-id="28ae7-272">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="28ae7-272">`expression`: `Double`</span></span> 

<span data-ttu-id="28ae7-273">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="28ae7-273">**Return Value**</span></span> 

`Double` 

<span data-ttu-id="28ae7-274">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="28ae7-274">**Example**</span></span> 

`SqlServer.TAN(45.0)`
  
## <a name="see-also"></a><span data-ttu-id="28ae7-275">Vea también</span><span class="sxs-lookup"><span data-stu-id="28ae7-275">See also</span></span>

<span data-ttu-id="28ae7-276">Para obtener más información sobre las funciones matemáticas que SqlClient admite, consulte la documentación de la versión de SQL Server que especificó en el manifiesto del proveedor SqlClient:</span><span class="sxs-lookup"><span data-stu-id="28ae7-276">For more information about the mathematical functions that SqlClient supports, see the documentation for the SQL Server version that you specified in the SqlClient provider manifest:</span></span>  

<span data-ttu-id="28ae7-277">**SQL Server 2005:** [Funciones matemáticas (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms177516(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="28ae7-277">**SQL Server 2005:** [Mathematical Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms177516(v=sql.90))</span></span>  
<span data-ttu-id="28ae7-278">**SQL Server 2008:** [Funciones matemáticas (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms177516(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="28ae7-278">**SQL Server 2008:** [Mathematical Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms177516(v=sql.100))</span></span>  
<span data-ttu-id="28ae7-279">**SQL Server 2012 y versiones posterior:** [Funciones matemáticas (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql?view=sql-server-2017)</span><span class="sxs-lookup"><span data-stu-id="28ae7-279">**SQL Server 2012 and later:** [Mathematical Functions (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql?view=sql-server-2017)</span></span>   

- [<span data-ttu-id="28ae7-280">SqlClient para las funciones de Entity Framework</span><span class="sxs-lookup"><span data-stu-id="28ae7-280">SqlClient for Entity Framework Functions</span></span>](sqlclient-for-ef-functions.md)
