---
title: Funciones matemáticas
ms.date: 03/30/2017
ms.assetid: b040c7cb-156d-40f2-9152-61065b18148c
ms.openlocfilehash: b6f248382f069df59a55e85e9a764b0df700fb26
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61780320"
---
# <a name="mathematical-functions"></a><span data-ttu-id="099b8-102">Funciones matemáticas</span><span class="sxs-lookup"><span data-stu-id="099b8-102">Mathematical Functions</span></span>

<span data-ttu-id="099b8-103">El Proveedor de datos .NET Framework para SQL Server (SqlClient) proporciona funciones matemáticas que realizan cálculos con los valores de entrada que se proporcionan como argumentos y devuelven un resultado numérico.</span><span class="sxs-lookup"><span data-stu-id="099b8-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides math functions that perform calculations on input values that are provided as arguments, and return a numeric value result.</span></span> <span data-ttu-id="099b8-104">Estas funciones están en el espacio de nombres SqlServer, que está disponible al utilizar SqlClient.</span><span class="sxs-lookup"><span data-stu-id="099b8-104">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="099b8-105">La propiedad del espacio de nombres de un proveedor permite a Entity Framework detectar qué prefijo usa este proveedor para estructuras concretas, como tipos y funciones.</span><span class="sxs-lookup"><span data-stu-id="099b8-105">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span> <span data-ttu-id="099b8-106">En la tabla siguiente se describe las funciones matemáticas de SqlClient.</span><span class="sxs-lookup"><span data-stu-id="099b8-106">The following table describes the SqlClient math functions.</span></span>  
  
## <a name="absexpression"></a><span data-ttu-id="099b8-107">ABS(Expression)</span><span class="sxs-lookup"><span data-stu-id="099b8-107">ABS(expression)</span></span>

<span data-ttu-id="099b8-108">Lleva a cabo la función que devuelve el valor absoluto.</span><span class="sxs-lookup"><span data-stu-id="099b8-108">Performs the absolute value function.</span></span>

<span data-ttu-id="099b8-109">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="099b8-109">**Arguments**</span></span>

<span data-ttu-id="099b8-110">`expression`: Un `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="099b8-110">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="099b8-111">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="099b8-111">**Return Value**</span></span>

<span data-ttu-id="099b8-112">Valor absoluto de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="099b8-112">The absolute value of the specified expression.</span></span>

<span data-ttu-id="099b8-113">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="099b8-113">**Example**</span></span>

`SqlServer.ABS(-2)`

## <a name="acosexpression"></a><span data-ttu-id="099b8-114">ACOS(Expression)</span><span class="sxs-lookup"><span data-stu-id="099b8-114">ACOS(expression)</span></span>

<span data-ttu-id="099b8-115">Devuelve el valor del arcocoseno de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="099b8-115">Returns the arccosine value of the specified expression.</span></span>

<span data-ttu-id="099b8-116">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="099b8-116">**Arguments**</span></span>

<span data-ttu-id="099b8-117">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="099b8-117">`expression`: A `Double`.</span></span>

<span data-ttu-id="099b8-118">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="099b8-118">**Return Value**</span></span>

<span data-ttu-id="099b8-119">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="099b8-119">A `Double`.</span></span>

<span data-ttu-id="099b8-120">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="099b8-120">**Example**</span></span>

`SqlServer.ACOS(.9)`

## <a name="asinexpression"></a><span data-ttu-id="099b8-121">ASIN(Expression)</span><span class="sxs-lookup"><span data-stu-id="099b8-121">ASIN(expression)</span></span>

<span data-ttu-id="099b8-122">Devuelve el valor del arcoseno de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="099b8-122">Returns the arcsine value of the specified expression.</span></span>

<span data-ttu-id="099b8-123">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="099b8-123">**Arguments**</span></span>

<span data-ttu-id="099b8-124">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="099b8-124">`expression`: A `Double`.</span></span>

<span data-ttu-id="099b8-125">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="099b8-125">**Return Value**</span></span>

<span data-ttu-id="099b8-126">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="099b8-126">A `Double`.</span></span>

<span data-ttu-id="099b8-127">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="099b8-127">**Example**</span></span>

`SqlServer.ASIN(.9)`

## <a name="atanexpression"></a><span data-ttu-id="099b8-128">ATAN(Expression)</span><span class="sxs-lookup"><span data-stu-id="099b8-128">ATAN(expression)</span></span>

<span data-ttu-id="099b8-129">Devuelve el valor del arcotangente de la expresión numérica especificada.</span><span class="sxs-lookup"><span data-stu-id="099b8-129">Returns the arctangent value of the specified numeric expression.</span></span>

<span data-ttu-id="099b8-130">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="099b8-130">**Arguments**</span></span>

<span data-ttu-id="099b8-131">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="099b8-131">`expression`: A `Double`.</span></span>

<span data-ttu-id="099b8-132">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="099b8-132">**Return Value**</span></span>

<span data-ttu-id="099b8-133">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="099b8-133">A `Double`.</span></span>

<span data-ttu-id="099b8-134">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="099b8-134">**Example**</span></span>

`SqlServer.ATAN(9)`

## <a name="atn2expression-expression"></a><span data-ttu-id="099b8-135">ATN2(Expression, Expression)</span><span class="sxs-lookup"><span data-stu-id="099b8-135">ATN2(expression, expression)</span></span>

<span data-ttu-id="099b8-136">Devuelve el ángulo, en radianes, cuya tangente se encuentra entre las dos expresiones numéricas especificadas.</span><span class="sxs-lookup"><span data-stu-id="099b8-136">Returns the angle, in radians, whose tangent is between the two specified numeric expressions.</span></span>

<span data-ttu-id="099b8-137">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="099b8-137">**Arguments**</span></span>

<span data-ttu-id="099b8-138">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="099b8-138">`expression`: A `Double`.</span></span>

<span data-ttu-id="099b8-139">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="099b8-139">**Return Value**</span></span>

<span data-ttu-id="099b8-140">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="099b8-140">A `Double`.</span></span>

<span data-ttu-id="099b8-141">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="099b8-141">**Example**</span></span>

`SqlServer.ATN2(9, 8)`
 
## <a name="ceilingexpression"></a><span data-ttu-id="099b8-142">CEILING(Expression)</span><span class="sxs-lookup"><span data-stu-id="099b8-142">CEILING(expression)</span></span>

<span data-ttu-id="099b8-143">Convierte la expresión especificada al número entero más pequeño mayor o igual que él.</span><span class="sxs-lookup"><span data-stu-id="099b8-143">Converts the specified expression to the smallest integer that is greater than or equal to it.</span></span>

<span data-ttu-id="099b8-144">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="099b8-144">**Arguments**</span></span>

<span data-ttu-id="099b8-145">`expression`: Un `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="099b8-145">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="099b8-146">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="099b8-146">**Return Value**</span></span>

<span data-ttu-id="099b8-147">Un `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="099b8-147">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="099b8-148">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="099b8-148">**Example**</span></span> 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_ceiling)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_ceiling)]

## <a name="cosexpression"></a><span data-ttu-id="099b8-149">COS(Expression)</span><span class="sxs-lookup"><span data-stu-id="099b8-149">COS(expression)</span></span>

<span data-ttu-id="099b8-150">Calcula el coseno trigonométrico del ángulo especificado, en radianes.</span><span class="sxs-lookup"><span data-stu-id="099b8-150">Calculates the trigonometric cosine of the specified angle in radians.</span></span> 

<span data-ttu-id="099b8-151">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="099b8-151">**Arguments**</span></span> 

<span data-ttu-id="099b8-152">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="099b8-152">`expression`: A `Double`.</span></span> 

<span data-ttu-id="099b8-153">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="099b8-153">**Return Value**</span></span> 

<span data-ttu-id="099b8-154">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="099b8-154">A `Double`.</span></span> 

<span data-ttu-id="099b8-155">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="099b8-155">**Example**</span></span> 

`SqlServer.COS(45)`

## <a name="cotexpression"></a><span data-ttu-id="099b8-156">COT(Expression)</span><span class="sxs-lookup"><span data-stu-id="099b8-156">COT(expression)</span></span>

<span data-ttu-id="099b8-157">Calcula la cotangente trigonométrica del ángulo especificado, en radianes.</span><span class="sxs-lookup"><span data-stu-id="099b8-157">Calculates the trigonometric cotangent of the specified angle in radians.</span></span> 

<span data-ttu-id="099b8-158">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="099b8-158">**Arguments**</span></span> 

<span data-ttu-id="099b8-159">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="099b8-159">`expression`: A `Double`.</span></span> 

<span data-ttu-id="099b8-160">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="099b8-160">**Return Value**</span></span> 

<span data-ttu-id="099b8-161">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="099b8-161">A `Double`.</span></span> 

<span data-ttu-id="099b8-162">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="099b8-162">**Example**</span></span> 

`SqlServer.COT(60)`
  
## <a name="degreesradians"></a><span data-ttu-id="099b8-163">Degrees(RADIANS)</span><span class="sxs-lookup"><span data-stu-id="099b8-163">DEGREES(radians)</span></span>

<span data-ttu-id="099b8-164">Devuelve el ángulo correspondiente en grados.</span><span class="sxs-lookup"><span data-stu-id="099b8-164">Returns the corresponding angle in degrees.</span></span> 

<span data-ttu-id="099b8-165">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="099b8-165">**Arguments**</span></span> 

<span data-ttu-id="099b8-166">`expression`: Un `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="099b8-166">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="099b8-167">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="099b8-167">**Return Value**</span></span> 

<span data-ttu-id="099b8-168">Un `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="099b8-168">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="099b8-169">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="099b8-169">**Example**</span></span> 

`SqlServer.DEGREES(3.1)`

## <a name="expexpression"></a><span data-ttu-id="099b8-170">EXP(Expression)</span><span class="sxs-lookup"><span data-stu-id="099b8-170">EXP(expression)</span></span>

<span data-ttu-id="099b8-171">Calcula el valor exponencial de la expresión numérica especificada.</span><span class="sxs-lookup"><span data-stu-id="099b8-171">Calculates the exponential value of a specified numeric expression.</span></span> 

<span data-ttu-id="099b8-172">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="099b8-172">**Arguments**</span></span> 

<span data-ttu-id="099b8-173">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="099b8-173">`expression`: A `Double`.</span></span> 

<span data-ttu-id="099b8-174">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="099b8-174">**Return Value**</span></span> 

<span data-ttu-id="099b8-175">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="099b8-175">A `Double`.</span></span> 

<span data-ttu-id="099b8-176">**Ejemplo** `SqlServer.EXP(1)`</span><span class="sxs-lookup"><span data-stu-id="099b8-176">**Example** `SqlServer.EXP(1)`</span></span>

## <a name="floorexpression"></a><span data-ttu-id="099b8-177">Floor(Expression)</span><span class="sxs-lookup"><span data-stu-id="099b8-177">FLOOR(expression)</span></span>

<span data-ttu-id="099b8-178">Convierte la expresión especificada al número entero más grande que sea menor o igual que ella.</span><span class="sxs-lookup"><span data-stu-id="099b8-178">Converts the specified expression to the largest integer less than or equal to it.</span></span> 

<span data-ttu-id="099b8-179">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="099b8-179">**Arguments**</span></span> 

<span data-ttu-id="099b8-180">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="099b8-180">`expression`: A `Double`.</span></span> 

<span data-ttu-id="099b8-181">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="099b8-181">**Return Value**</span></span> 

<span data-ttu-id="099b8-182">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="099b8-182">A `Double`.</span></span> 

<span data-ttu-id="099b8-183">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="099b8-183">**Example**</span></span> 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_floor)] 
[!code-sql[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_floor)]

## <a name="logexpression"></a><span data-ttu-id="099b8-184">LOG(Expression)</span><span class="sxs-lookup"><span data-stu-id="099b8-184">LOG(expression)</span></span>

<span data-ttu-id="099b8-185">Calcula el logaritmo natural de la expresión `float` especificada.</span><span class="sxs-lookup"><span data-stu-id="099b8-185">Calculates the natural logarithm of the specified `float` expression.</span></span> 

<span data-ttu-id="099b8-186">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="099b8-186">**Arguments**</span></span> 

<span data-ttu-id="099b8-187">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="099b8-187">`expression`: A `Double`.</span></span> 

<span data-ttu-id="099b8-188">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="099b8-188">**Return Value**</span></span> 

<span data-ttu-id="099b8-189">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="099b8-189">A `Double`.</span></span> 

<span data-ttu-id="099b8-190">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="099b8-190">**Example**</span></span> 

`SqlServer.LOG(100)`

## <a name="log10expression"></a><span data-ttu-id="099b8-191">LOG10(Expression)</span><span class="sxs-lookup"><span data-stu-id="099b8-191">LOG10(expression)</span></span>

<span data-ttu-id="099b8-192">Devuelve el logaritmo en base 10 de la expresión `Double` especificada.</span><span class="sxs-lookup"><span data-stu-id="099b8-192">Returns the base-10 logarithm of the specified `Double` expression.</span></span> 

<span data-ttu-id="099b8-193">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="099b8-193">**Arguments**</span></span> 

<span data-ttu-id="099b8-194">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="099b8-194">`expression`: A `Double`.</span></span> 

<span data-ttu-id="099b8-195">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="099b8-195">**Return Value**</span></span> 

<span data-ttu-id="099b8-196">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="099b8-196">A `Double`.</span></span> 

<span data-ttu-id="099b8-197">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="099b8-197">**Example**</span></span> 

`SqlServer.LOG10(100)`

## <a name="pi"></a><span data-ttu-id="099b8-198">PI()</span><span class="sxs-lookup"><span data-stu-id="099b8-198">PI()</span></span>

<span data-ttu-id="099b8-199">Devuelve el valor constante de Pi como un `Double`.</span><span class="sxs-lookup"><span data-stu-id="099b8-199">Returns the constant value of pi as a `Double`.</span></span> 

<span data-ttu-id="099b8-200">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="099b8-200">**Return Value**</span></span> 

<span data-ttu-id="099b8-201">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="099b8-201">A `Double`.</span></span> 

<span data-ttu-id="099b8-202">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="099b8-202">**Example**</span></span> 

`SqlServer.PI()`

## <a name="powernumericexpression-powerexpression"></a><span data-ttu-id="099b8-203">POWER (numeric_expression, power_expression)</span><span class="sxs-lookup"><span data-stu-id="099b8-203">POWER(numeric_expression, power_expression)</span></span>

<span data-ttu-id="099b8-204">Calcula el valor de la expresión especificada elevada a la potencia indicada.</span><span class="sxs-lookup"><span data-stu-id="099b8-204">Calculates the value of a specified expression to a specified power.</span></span>

<span data-ttu-id="099b8-205">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="099b8-205">**Arguments**</span></span> 

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="099b8-206">Un `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="099b8-206">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>|
|`power_expression`| <span data-ttu-id="099b8-207">Un `Double` que representa la potencia a la que se va a generar el `numeric_expression`.</span><span class="sxs-lookup"><span data-stu-id="099b8-207">A `Double` that represents the power to which to raise the `numeric_expression`.</span></span>| 

<span data-ttu-id="099b8-208">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="099b8-208">**Return Value**</span></span> 

<span data-ttu-id="099b8-209">Valor de la `numeric_expression` especificada a la `power_expression` especificada.</span><span class="sxs-lookup"><span data-stu-id="099b8-209">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span> 

<span data-ttu-id="099b8-210">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="099b8-210">**Example**</span></span> 

`SqlServer.POWER(2,7)`

## <a name="radiansexpression"></a><span data-ttu-id="099b8-211">RADIANS(Expression)</span><span class="sxs-lookup"><span data-stu-id="099b8-211">RADIANS(expression)</span></span>

<span data-ttu-id="099b8-212">Convierte grados en radianes.</span><span class="sxs-lookup"><span data-stu-id="099b8-212">Converts degrees to radians.</span></span> 

<span data-ttu-id="099b8-213">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="099b8-213">**Arguments**</span></span> 

<span data-ttu-id="099b8-214">`expression`: Un `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="099b8-214">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="099b8-215">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="099b8-215">**Return Value**</span></span> 

<span data-ttu-id="099b8-216">Un `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="099b8-216">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="099b8-217">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="099b8-217">**Example**</span></span> 

`SqlServer.RADIANS(360.0)`

## <a name="randseed"></a><span data-ttu-id="099b8-218">RAND([SEED])</span><span class="sxs-lookup"><span data-stu-id="099b8-218">RAND([seed])</span></span>

<span data-ttu-id="099b8-219">Devuelve un valor aleatorio de 0 a 1.</span><span class="sxs-lookup"><span data-stu-id="099b8-219">Returns a random value from 0 through 1.</span></span> 

<span data-ttu-id="099b8-220">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="099b8-220">**Arguments**</span></span> 

<span data-ttu-id="099b8-221">El valor de inicialización como una `Int32`.</span><span class="sxs-lookup"><span data-stu-id="099b8-221">The seed value as an `Int32`.</span></span> <span data-ttu-id="099b8-222">Si la inicialización no se especifica, el motor de base de datos de SQL Server asigna uno de forma aleatoria.</span><span class="sxs-lookup"><span data-stu-id="099b8-222">If the seed is not specified, the SQL Server Database Engine assigns a seed value at random.</span></span> <span data-ttu-id="099b8-223">Para un valor de inicialización especificado, el resultado devuelto es siempre el mismo.</span><span class="sxs-lookup"><span data-stu-id="099b8-223">For a specified seed value, the result returned is always the same.</span></span>

<span data-ttu-id="099b8-224">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="099b8-224">**Return Value**</span></span> 

<span data-ttu-id="099b8-225">Valor `Double` aleatorio de 0 a 1.</span><span class="sxs-lookup"><span data-stu-id="099b8-225">A random `Double` value from 0 through 1.</span></span> 

<span data-ttu-id="099b8-226">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="099b8-226">**Example**</span></span> 

`SqlServer.RAND()`
  
## <a name="roundnumericexpression-lengthfunction"></a><span data-ttu-id="099b8-227">Round(numeric_expression, Length[,Function])</span><span class="sxs-lookup"><span data-stu-id="099b8-227">ROUND(numeric_expression, length[,function])</span></span>

<span data-ttu-id="099b8-228">Devuelve una expresión numérica, redondeada a la longitud o precisión especificadas.</span><span class="sxs-lookup"><span data-stu-id="099b8-228">Returns a numeric expression, rounded to the specified length or precision.</span></span> 

<span data-ttu-id="099b8-229">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="099b8-229">**Arguments**</span></span> 

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="099b8-230">Un `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="099b8-230">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 
|`length`| <span data-ttu-id="099b8-231">Valor `Int32` que representa la precisión a la que se va a redondear `numeric_expression`.</span><span class="sxs-lookup"><span data-stu-id="099b8-231">An `Int32` that represents the precision to which `numeric_expression` is to be rounded.</span></span> <span data-ttu-id="099b8-232">Si `length` es un número positivo, `numeric_expression` se redondea al número de posiciones decimales que especifica `length`.</span><span class="sxs-lookup"><span data-stu-id="099b8-232">When `length` is a positive number, `numeric_expression` is rounded to the number of decimal positions specified by `length`.</span></span> <span data-ttu-id="099b8-233">Si `length` es un número negativo, `numeric_expression` se redondea a la izquierda del separador decimal, según se especifica en `length`.</span><span class="sxs-lookup"><span data-stu-id="099b8-233">When `length` is a negative number, `numeric_expression` is rounded on the left side of the decimal point, as specified by `length`.</span></span>|
|`function` | <span data-ttu-id="099b8-234">Opcional.</span><span class="sxs-lookup"><span data-stu-id="099b8-234">Optional.</span></span> <span data-ttu-id="099b8-235">Un `Int32` que representa el tipo de operación que se realiza.</span><span class="sxs-lookup"><span data-stu-id="099b8-235">An `Int32` that represents the type of operation to perform.</span></span> <span data-ttu-id="099b8-236">Cuando la función se omite o tiene un valor de 0 (valor predeterminado), `numeric_expression` se redondea.</span><span class="sxs-lookup"><span data-stu-id="099b8-236">When function is omitted or has a value of 0 (default), `numeric_expression` is rounded.</span></span> <span data-ttu-id="099b8-237">Si un valor distinto de 0 se especifica, `numeric_expression` se trunca.</span><span class="sxs-lookup"><span data-stu-id="099b8-237">When a value other than 0 is specified, `numeric_expression` is truncated.</span></span> |

<span data-ttu-id="099b8-238">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="099b8-238">**Return Value**</span></span> 

<span data-ttu-id="099b8-239">Valor de la `numeric_expression` especificada a la `power_expression` especificada.</span><span class="sxs-lookup"><span data-stu-id="099b8-239">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span>

<span data-ttu-id="099b8-240">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="099b8-240">**Example**</span></span> 

`SqlServer.ROUND(748.58, -3)`

## <a name="signexpression"></a><span data-ttu-id="099b8-241">Sign(Expression)</span><span class="sxs-lookup"><span data-stu-id="099b8-241">SIGN(expression)</span></span> 

<span data-ttu-id="099b8-242">Devuelve el signo positivo (+1), cero (0) o negativo (-1) de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="099b8-242">Returns the positive (+1), zero (0), or negative (-1) sign of the specified expression.</span></span> 

<span data-ttu-id="099b8-243">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="099b8-243">**Arguments**</span></span> 

<span data-ttu-id="099b8-244">`expression`: `Int32`, `Int64`, `Double` o `Decimal`</span><span class="sxs-lookup"><span data-stu-id="099b8-244">`expression`: `Int32`, `Int64`, `Double`, or `Decimal`</span></span> 

<span data-ttu-id="099b8-245">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="099b8-245">**Return Value**</span></span> 

<span data-ttu-id="099b8-246">Un `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="099b8-246">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="099b8-247">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="099b8-247">**Example**</span></span> 

`SqlServer.SIGN(-10)`

## <a name="sinexpression"></a><span data-ttu-id="099b8-248">SIN(Expression)</span><span class="sxs-lookup"><span data-stu-id="099b8-248">SIN(expression)</span></span>

<span data-ttu-id="099b8-249">Calcula el seno trigonométrico de un ángulo especificado, en radianes, y devuelve una expresión de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="099b8-249">Calculates the trigonometric sine of the specified angle in radians, and returns a `Double` expression.</span></span> 

<span data-ttu-id="099b8-250">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="099b8-250">**Arguments**</span></span> 

<span data-ttu-id="099b8-251">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="099b8-251">`expression`: A `Double`.</span></span> 

<span data-ttu-id="099b8-252">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="099b8-252">**Return Value**</span></span> 

<span data-ttu-id="099b8-253">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="099b8-253">A `Double`.</span></span> 

<span data-ttu-id="099b8-254">**Ejemplo** `SqlServer.SIN(20)`</span><span class="sxs-lookup"><span data-stu-id="099b8-254">**Example** `SqlServer.SIN(20)`</span></span>

## <a name="sqrtexpression"></a><span data-ttu-id="099b8-255">SQRT(Expression)</span><span class="sxs-lookup"><span data-stu-id="099b8-255">SQRT(expression)</span></span>

<span data-ttu-id="099b8-256">Devuelve la raíz cuadrada de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="099b8-256">Returns the square root of the specified expression.</span></span> 

<span data-ttu-id="099b8-257">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="099b8-257">**Arguments**</span></span> 

<span data-ttu-id="099b8-258">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="099b8-258">`expression`: A `Double`.</span></span> 

<span data-ttu-id="099b8-259">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="099b8-259">**Return Value**</span></span> 

<span data-ttu-id="099b8-260">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="099b8-260">A `Double`.</span></span> 

<span data-ttu-id="099b8-261">**Ejemplo** `SqlServer.SQRT(3600)`</span><span class="sxs-lookup"><span data-stu-id="099b8-261">**Example** `SqlServer.SQRT(3600)`</span></span>

## <a name="squareexpression"></a><span data-ttu-id="099b8-262">Square(Expression)</span><span class="sxs-lookup"><span data-stu-id="099b8-262">SQUARE(expression)</span></span>

<span data-ttu-id="099b8-263">Devuelve la raíz cuadrada de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="099b8-263">Returns the square of the specified expression.</span></span> 

<span data-ttu-id="099b8-264">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="099b8-264">**Arguments**</span></span> 

<span data-ttu-id="099b8-265">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="099b8-265">`expression`: A `Double`.</span></span> 

<span data-ttu-id="099b8-266">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="099b8-266">**Return Value**</span></span> 

<span data-ttu-id="099b8-267">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="099b8-267">A `Double`.</span></span> 

<span data-ttu-id="099b8-268">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="099b8-268">**Example**</span></span> 

`SqlServer.SQUARE(25)`

## <a name="tanexpression"></a><span data-ttu-id="099b8-269">TAN(Expression)</span><span class="sxs-lookup"><span data-stu-id="099b8-269">TAN(expression)</span></span>

<span data-ttu-id="099b8-270">Calcula la tangente de una expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="099b8-270">Calculates the tangent of a specified expression.</span></span>

<span data-ttu-id="099b8-271">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="099b8-271">**Arguments**</span></span> 

<span data-ttu-id="099b8-272">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="099b8-272">`expression`: `Double`</span></span> 

<span data-ttu-id="099b8-273">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="099b8-273">**Return Value**</span></span> 

`Double` 

<span data-ttu-id="099b8-274">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="099b8-274">**Example**</span></span> 

`SqlServer.TAN(45.0)`
  
## <a name="see-also"></a><span data-ttu-id="099b8-275">Vea también</span><span class="sxs-lookup"><span data-stu-id="099b8-275">See also</span></span>

<span data-ttu-id="099b8-276">Para obtener más información sobre las funciones matemáticas que SqlClient admite, consulte la documentación de la versión de SQL Server que especificó en el manifiesto del proveedor SqlClient:</span><span class="sxs-lookup"><span data-stu-id="099b8-276">For more information about the mathematical functions that SqlClient supports, see the documentation for the SQL Server version that you specified in the SqlClient provider manifest:</span></span>

- <span data-ttu-id="099b8-277">**SQL Server 2005:** [Funciones matemáticas (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms177516(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="099b8-277">**SQL Server 2005:** [Mathematical Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms177516(v=sql.90))</span></span>
- <span data-ttu-id="099b8-278">**SQL Server 2008:** [Funciones matemáticas (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms177516(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="099b8-278">**SQL Server 2008:** [Mathematical Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms177516(v=sql.100))</span></span>
- <span data-ttu-id="099b8-279">**SQL Server 2012 y versiones posterior:** [Funciones matemáticas (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql?view=sql-server-2017)</span><span class="sxs-lookup"><span data-stu-id="099b8-279">**SQL Server 2012 and later:** [Mathematical Functions (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql?view=sql-server-2017)</span></span>

- [<span data-ttu-id="099b8-280">SqlClient para las funciones de Entity Framework</span><span class="sxs-lookup"><span data-stu-id="099b8-280">SqlClient for Entity Framework Functions</span></span>](sqlclient-for-ef-functions.md)
