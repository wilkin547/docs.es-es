---
title: Funciones matemáticas
ms.date: 03/30/2017
ms.assetid: b040c7cb-156d-40f2-9152-61065b18148c
ms.openlocfilehash: e6c58d781d7138f8295f2d0a2f0db110ad4b1dd6
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43456456"
---
# <a name="mathematical-functions"></a><span data-ttu-id="43682-102">Funciones matemáticas</span><span class="sxs-lookup"><span data-stu-id="43682-102">Mathematical Functions</span></span>

<span data-ttu-id="43682-103">El Proveedor de datos .NET Framework para SQL Server (SqlClient) proporciona funciones matemáticas que realizan cálculos con los valores de entrada que se proporcionan como argumentos y devuelven un resultado numérico.</span><span class="sxs-lookup"><span data-stu-id="43682-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides math functions that perform calculations on input values that are provided as arguments, and return a numeric value result.</span></span> <span data-ttu-id="43682-104">Estas funciones están en el espacio de nombres SqlServer, que está disponible al utilizar SqlClient.</span><span class="sxs-lookup"><span data-stu-id="43682-104">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="43682-105">La propiedad del espacio de nombres de un proveedor permite a Entity Framework detectar qué prefijo usa este proveedor para estructuras concretas, como los tipos y las funciones. La tabla siguiente describe las funciones matemáticas de SqlClient.</span><span class="sxs-lookup"><span data-stu-id="43682-105">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.The following table describes the SqlClient math functions.</span></span>  
  
## <a name="absexpression"></a><span data-ttu-id="43682-106">ABS(Expression)</span><span class="sxs-lookup"><span data-stu-id="43682-106">ABS(expression)</span></span>

<span data-ttu-id="43682-107">Lleva a cabo la función que devuelve el valor absoluto.</span><span class="sxs-lookup"><span data-stu-id="43682-107">Performs the absolute value function.</span></span>

<span data-ttu-id="43682-108">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="43682-108">**Arguments**</span></span>

<span data-ttu-id="43682-109">`expression`: valor de tipo`Int32`,`Int64`, `Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="43682-109">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="43682-110">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="43682-110">**Return Value**</span></span>

<span data-ttu-id="43682-111">Valor absoluto de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="43682-111">The absolute value of the specified expression.</span></span>

<span data-ttu-id="43682-112">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="43682-112">**Example**</span></span>

`SqlServer.ABS(-2)`

## <a name="acosexpression"></a><span data-ttu-id="43682-113">ACOS(Expression)</span><span class="sxs-lookup"><span data-stu-id="43682-113">ACOS(expression)</span></span>

<span data-ttu-id="43682-114">Devuelve el valor del arcocoseno de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="43682-114">Returns the arccosine value of the specified expression.</span></span>

<span data-ttu-id="43682-115">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="43682-115">**Arguments**</span></span>

<span data-ttu-id="43682-116">`expression`: valor de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="43682-116">`expression`: A `Double`.</span></span>

<span data-ttu-id="43682-117">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="43682-117">**Return Value**</span></span>

<span data-ttu-id="43682-118">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="43682-118">A `Double`.</span></span>

<span data-ttu-id="43682-119">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="43682-119">**Example**</span></span>

`SqlServer.ACOS(.9)`

## <a name="asinexpression"></a><span data-ttu-id="43682-120">ASIN(Expression)</span><span class="sxs-lookup"><span data-stu-id="43682-120">ASIN(expression)</span></span>

<span data-ttu-id="43682-121">Devuelve el valor del arcoseno de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="43682-121">Returns the arcsine value of the specified expression.</span></span>

<span data-ttu-id="43682-122">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="43682-122">**Arguments**</span></span>

<span data-ttu-id="43682-123">`expression`: valor de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="43682-123">`expression`: A `Double`.</span></span>

<span data-ttu-id="43682-124">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="43682-124">**Return Value**</span></span>

<span data-ttu-id="43682-125">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="43682-125">A `Double`.</span></span>

<span data-ttu-id="43682-126">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="43682-126">**Example**</span></span>

`SqlServer.ASIN(.9)`

## <a name="atanexpression"></a><span data-ttu-id="43682-127">ATAN(Expression)</span><span class="sxs-lookup"><span data-stu-id="43682-127">ATAN(expression)</span></span>

<span data-ttu-id="43682-128">Devuelve el valor del arcotangente de la expresión numérica especificada.</span><span class="sxs-lookup"><span data-stu-id="43682-128">Returns the arctangent value of the specified numeric expression.</span></span>

<span data-ttu-id="43682-129">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="43682-129">**Arguments**</span></span>

<span data-ttu-id="43682-130">`expression`: valor de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="43682-130">`expression`: A `Double`.</span></span>

<span data-ttu-id="43682-131">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="43682-131">**Return Value**</span></span>

<span data-ttu-id="43682-132">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="43682-132">A `Double`.</span></span>

<span data-ttu-id="43682-133">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="43682-133">**Example**</span></span>

`SqlServer.ATAN(9)`

## <a name="atn2expression-expression"></a><span data-ttu-id="43682-134">ATN2(Expression, Expression)</span><span class="sxs-lookup"><span data-stu-id="43682-134">ATN2(expression, expression)</span></span>

<span data-ttu-id="43682-135">Devuelve el ángulo, en radianes, cuya tangente se encuentra entre las dos expresiones numéricas especificadas.</span><span class="sxs-lookup"><span data-stu-id="43682-135">Returns the angle, in radians, whose tangent is between the two specified numeric expressions.</span></span>

<span data-ttu-id="43682-136">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="43682-136">**Arguments**</span></span>

<span data-ttu-id="43682-137">`expression`: valor de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="43682-137">`expression`: A `Double`.</span></span>

<span data-ttu-id="43682-138">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="43682-138">**Return Value**</span></span>

<span data-ttu-id="43682-139">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="43682-139">A `Double`.</span></span>

<span data-ttu-id="43682-140">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="43682-140">**Example**</span></span>

`SqlServer.ATN2(9, 8)`
 
## <a name="ceilingexpression"></a><span data-ttu-id="43682-141">CEILING(Expression)</span><span class="sxs-lookup"><span data-stu-id="43682-141">CEILING(expression)</span></span>

<span data-ttu-id="43682-142">Convierte la expresión especificada al número entero más pequeño mayor o igual que él.</span><span class="sxs-lookup"><span data-stu-id="43682-142">Converts the specified expression to the smallest integer that is greater than or equal to it.</span></span>

<span data-ttu-id="43682-143">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="43682-143">**Arguments**</span></span>

<span data-ttu-id="43682-144">`expression`: valor de tipo`Int32`,`Int64`, `Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="43682-144">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="43682-145">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="43682-145">**Return Value**</span></span>

<span data-ttu-id="43682-146">Un `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="43682-146">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="43682-147">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="43682-147">**Example**</span></span> 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_ceiling)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_ceiling)]

## <a name="cosexpression"></a><span data-ttu-id="43682-148">COS(Expression)</span><span class="sxs-lookup"><span data-stu-id="43682-148">COS(expression)</span></span>

<span data-ttu-id="43682-149">Calcula el coseno trigonométrico del ángulo especificado, en radianes.</span><span class="sxs-lookup"><span data-stu-id="43682-149">Calculates the trigonometric cosine of the specified angle in radians.</span></span> 

<span data-ttu-id="43682-150">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="43682-150">**Arguments**</span></span> 

<span data-ttu-id="43682-151">`expression`: valor de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="43682-151">`expression`: A `Double`.</span></span> 

<span data-ttu-id="43682-152">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="43682-152">**Return Value**</span></span> 

<span data-ttu-id="43682-153">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="43682-153">A `Double`.</span></span> 

<span data-ttu-id="43682-154">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="43682-154">**Example**</span></span> 

`SqlServer.COS(45)`

## <a name="cotexpression"></a><span data-ttu-id="43682-155">COT(Expression)</span><span class="sxs-lookup"><span data-stu-id="43682-155">COT(expression)</span></span>

<span data-ttu-id="43682-156">Calcula la cotangente trigonométrica del ángulo especificado, en radianes.</span><span class="sxs-lookup"><span data-stu-id="43682-156">Calculates the trigonometric cotangent of the specified angle in radians.</span></span> 

<span data-ttu-id="43682-157">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="43682-157">**Arguments**</span></span> 

<span data-ttu-id="43682-158">`expression`: valor de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="43682-158">`expression`: A `Double`.</span></span> 

<span data-ttu-id="43682-159">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="43682-159">**Return Value**</span></span> 

<span data-ttu-id="43682-160">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="43682-160">A `Double`.</span></span> 

<span data-ttu-id="43682-161">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="43682-161">**Example**</span></span> 

`SqlServer.COT(60)`
  
## <a name="degreesradians"></a><span data-ttu-id="43682-162">Degrees(RADIANS)</span><span class="sxs-lookup"><span data-stu-id="43682-162">DEGREES(radians)</span></span>

<span data-ttu-id="43682-163">Devuelve el ángulo correspondiente en grados.</span><span class="sxs-lookup"><span data-stu-id="43682-163">Returns the corresponding angle in degrees.</span></span> 

<span data-ttu-id="43682-164">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="43682-164">**Arguments**</span></span> 

<span data-ttu-id="43682-165">`expression`: valor de tipo`Int32`,`Int64`, `Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="43682-165">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="43682-166">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="43682-166">**Return Value**</span></span> 

<span data-ttu-id="43682-167">Un `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="43682-167">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="43682-168">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="43682-168">**Example**</span></span> 

`SqlServer.DEGREES(3.1)`

## <a name="expexpression"></a><span data-ttu-id="43682-169">EXP(Expression)</span><span class="sxs-lookup"><span data-stu-id="43682-169">EXP(expression)</span></span>

<span data-ttu-id="43682-170">Calcula el valor exponencial de la expresión numérica especificada.</span><span class="sxs-lookup"><span data-stu-id="43682-170">Calculates the exponential value of a specified numeric expression.</span></span> 

<span data-ttu-id="43682-171">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="43682-171">**Arguments**</span></span> 

<span data-ttu-id="43682-172">`expression`: valor de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="43682-172">`expression`: A `Double`.</span></span> 

<span data-ttu-id="43682-173">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="43682-173">**Return Value**</span></span> 

<span data-ttu-id="43682-174">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="43682-174">A `Double`.</span></span> 

<span data-ttu-id="43682-175">**Ejemplo** `SqlServer.EXP(1)`</span><span class="sxs-lookup"><span data-stu-id="43682-175">**Example** `SqlServer.EXP(1)`</span></span>

## <a name="floorexpression"></a><span data-ttu-id="43682-176">Floor(Expression)</span><span class="sxs-lookup"><span data-stu-id="43682-176">FLOOR(expression)</span></span>

<span data-ttu-id="43682-177">Convierte la expresión especificada al número entero más grande que sea menor o igual que ella.</span><span class="sxs-lookup"><span data-stu-id="43682-177">Converts the specified expression to the largest integer less than or equal to it.</span></span> 

<span data-ttu-id="43682-178">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="43682-178">**Arguments**</span></span> 

<span data-ttu-id="43682-179">`expression`: valor de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="43682-179">`expression`: A `Double`.</span></span> 

<span data-ttu-id="43682-180">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="43682-180">**Return Value**</span></span> 

<span data-ttu-id="43682-181">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="43682-181">A `Double`.</span></span> 

<span data-ttu-id="43682-182">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="43682-182">**Example**</span></span> 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_floor)] 
[!code-sql[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_floor)]

## <a name="logexpression"></a><span data-ttu-id="43682-183">LOG(Expression)</span><span class="sxs-lookup"><span data-stu-id="43682-183">LOG(expression)</span></span>

<span data-ttu-id="43682-184">Calcula el logaritmo natural de la expresión `float` especificada.</span><span class="sxs-lookup"><span data-stu-id="43682-184">Calculates the natural logarithm of the specified `float` expression.</span></span> 

<span data-ttu-id="43682-185">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="43682-185">**Arguments**</span></span> 

<span data-ttu-id="43682-186">`expression`: valor de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="43682-186">`expression`: A `Double`.</span></span> 

<span data-ttu-id="43682-187">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="43682-187">**Return Value**</span></span> 

<span data-ttu-id="43682-188">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="43682-188">A `Double`.</span></span> 

<span data-ttu-id="43682-189">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="43682-189">**Example**</span></span> 

`SqlServer.LOG(100)`

## <a name="log10expression"></a><span data-ttu-id="43682-190">LOG10(Expression)</span><span class="sxs-lookup"><span data-stu-id="43682-190">LOG10(expression)</span></span>

<span data-ttu-id="43682-191">Devuelve el logaritmo en base 10 de la expresión `Double` especificada.</span><span class="sxs-lookup"><span data-stu-id="43682-191">Returns the base-10 logarithm of the specified `Double` expression.</span></span> 

<span data-ttu-id="43682-192">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="43682-192">**Arguments**</span></span> 

<span data-ttu-id="43682-193">`expression`: valor de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="43682-193">`expression`: A `Double`.</span></span> 

<span data-ttu-id="43682-194">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="43682-194">**Return Value**</span></span> 

<span data-ttu-id="43682-195">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="43682-195">A `Double`.</span></span> 

<span data-ttu-id="43682-196">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="43682-196">**Example**</span></span> 

`SqlServer.LOG10(100)`

## <a name="pi"></a><span data-ttu-id="43682-197">PI()</span><span class="sxs-lookup"><span data-stu-id="43682-197">PI()</span></span>

<span data-ttu-id="43682-198">Devuelve el valor constante de Pi como un `Double`.</span><span class="sxs-lookup"><span data-stu-id="43682-198">Returns the constant value of pi as a `Double`.</span></span> 

<span data-ttu-id="43682-199">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="43682-199">**Return Value**</span></span> 

<span data-ttu-id="43682-200">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="43682-200">A `Double`.</span></span> 

<span data-ttu-id="43682-201">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="43682-201">**Example**</span></span> 

`SqlServer.PI()`

## <a name="powernumericexpression-powerexpression"></a><span data-ttu-id="43682-202">POWER (numeric_expression, power_expression)</span><span class="sxs-lookup"><span data-stu-id="43682-202">POWER(numeric_expression, power_expression)</span></span>

<span data-ttu-id="43682-203">Calcula el valor de la expresión especificada elevada a la potencia indicada.</span><span class="sxs-lookup"><span data-stu-id="43682-203">Calculates the value of a specified expression to a specified power.</span></span>

<span data-ttu-id="43682-204">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="43682-204">**Arguments**</span></span> 

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="43682-205">Un `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="43682-205">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>|
|`power_expression`| <span data-ttu-id="43682-206">Un `Double` que representa la potencia a la que se va a generar el `numeric_expression`.</span><span class="sxs-lookup"><span data-stu-id="43682-206">A `Double` that represents the power to which to raise the `numeric_expression`.</span></span>| 

<span data-ttu-id="43682-207">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="43682-207">**Return Value**</span></span> 

<span data-ttu-id="43682-208">Valor de la `numeric_expression` especificada a la `power_expression` especificada.</span><span class="sxs-lookup"><span data-stu-id="43682-208">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span> 

<span data-ttu-id="43682-209">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="43682-209">**Example**</span></span> 

`SqlServer.POWER(2,7)`

## <a name="radiansexpression"></a><span data-ttu-id="43682-210">RADIANS(Expression)</span><span class="sxs-lookup"><span data-stu-id="43682-210">RADIANS(expression)</span></span>

<span data-ttu-id="43682-211">Convierte grados en radianes.</span><span class="sxs-lookup"><span data-stu-id="43682-211">Converts degrees to radians.</span></span> 

<span data-ttu-id="43682-212">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="43682-212">**Arguments**</span></span> 

<span data-ttu-id="43682-213">`expression`: valor de tipo`Int32`,`Int64`, `Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="43682-213">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="43682-214">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="43682-214">**Return Value**</span></span> 

<span data-ttu-id="43682-215">Un `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="43682-215">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="43682-216">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="43682-216">**Example**</span></span> 

`SqlServer.RADIANS(360.0)`

## <a name="randseed"></a><span data-ttu-id="43682-217">RAND([SEED])</span><span class="sxs-lookup"><span data-stu-id="43682-217">RAND([seed])</span></span>

<span data-ttu-id="43682-218">Devuelve un valor aleatorio de 0 a 1.</span><span class="sxs-lookup"><span data-stu-id="43682-218">Returns a random value from 0 through 1.</span></span> 

<span data-ttu-id="43682-219">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="43682-219">**Arguments**</span></span> 

<span data-ttu-id="43682-220">El valor de inicialización como una `Int32`.</span><span class="sxs-lookup"><span data-stu-id="43682-220">The seed value as an `Int32`.</span></span> <span data-ttu-id="43682-221">Si la inicialización no se especifica, el motor de base de datos de SQL Server asigna uno de forma aleatoria.</span><span class="sxs-lookup"><span data-stu-id="43682-221">If the seed is not specified, the SQL Server Database Engine assigns a seed value at random.</span></span> <span data-ttu-id="43682-222">Para un valor de inicialización especificado, el resultado devuelto es siempre el mismo.</span><span class="sxs-lookup"><span data-stu-id="43682-222">For a specified seed value, the result returned is always the same.</span></span>

<span data-ttu-id="43682-223">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="43682-223">**Return Value**</span></span> 

<span data-ttu-id="43682-224">Valor `Double` aleatorio de 0 a 1.</span><span class="sxs-lookup"><span data-stu-id="43682-224">A random `Double` value from 0 through 1.</span></span> 

<span data-ttu-id="43682-225">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="43682-225">**Example**</span></span> 

`SqlServer.RAND()`
  
## <a name="roundnumericexpression-lengthfunction"></a><span data-ttu-id="43682-226">Round(numeric_expression, Length[,Function])</span><span class="sxs-lookup"><span data-stu-id="43682-226">ROUND(numeric_expression, length[,function])</span></span>

<span data-ttu-id="43682-227">Devuelve una expresión numérica, redondeada a la longitud o precisión especificadas.</span><span class="sxs-lookup"><span data-stu-id="43682-227">Returns a numeric expression, rounded to the specified length or precision.</span></span> 

<span data-ttu-id="43682-228">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="43682-228">**Arguments**</span></span> 

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="43682-229">Un `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="43682-229">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 
|`length`| <span data-ttu-id="43682-230">Valor `Int32` que representa la precisión a la que se va a redondear `numeric_expression`.</span><span class="sxs-lookup"><span data-stu-id="43682-230">An `Int32` that represents the precision to which `numeric_expression` is to be rounded.</span></span> <span data-ttu-id="43682-231">Si `length` es un número positivo, `numeric_expression` se redondea al número de posiciones decimales que especifica `length`.</span><span class="sxs-lookup"><span data-stu-id="43682-231">When `length` is a positive number, `numeric_expression` is rounded to the number of decimal positions specified by `length`.</span></span> <span data-ttu-id="43682-232">Si `length` es un número negativo, `numeric_expression` se redondea a la izquierda del separador decimal, según se especifica en `length`.</span><span class="sxs-lookup"><span data-stu-id="43682-232">When `length` is a negative number, `numeric_expression` is rounded on the left side of the decimal point, as specified by `length`.</span></span>|
|`function` | <span data-ttu-id="43682-233">Opcional.</span><span class="sxs-lookup"><span data-stu-id="43682-233">Optional.</span></span> <span data-ttu-id="43682-234">Un `Int32` que representa el tipo de operación que se realiza.</span><span class="sxs-lookup"><span data-stu-id="43682-234">An `Int32` that represents the type of operation to perform.</span></span> <span data-ttu-id="43682-235">Cuando la función se omite o tiene un valor de 0 (valor predeterminado), `numeric_expression` se redondea.</span><span class="sxs-lookup"><span data-stu-id="43682-235">When function is omitted or has a value of 0 (default), `numeric_expression` is rounded.</span></span> <span data-ttu-id="43682-236">Si un valor distinto de 0 se especifica, `numeric_expression` se trunca.</span><span class="sxs-lookup"><span data-stu-id="43682-236">When a value other than 0 is specified, `numeric_expression` is truncated.</span></span> |

<span data-ttu-id="43682-237">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="43682-237">**Return Value**</span></span> 

<span data-ttu-id="43682-238">Valor de la `numeric_expression` especificada a la `power_expression` especificada.</span><span class="sxs-lookup"><span data-stu-id="43682-238">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span>

<span data-ttu-id="43682-239">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="43682-239">**Example**</span></span> 

`SqlServer.ROUND(748.58, -3)`

## <a name="signexpression"></a><span data-ttu-id="43682-240">Sign(Expression)</span><span class="sxs-lookup"><span data-stu-id="43682-240">SIGN(expression)</span></span> 

<span data-ttu-id="43682-241">Devuelve el signo positivo (+1), cero (0) o negativo (-1) de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="43682-241">Returns the positive (+1), zero (0), or negative (-1) sign of the specified expression.</span></span> 

<span data-ttu-id="43682-242">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="43682-242">**Arguments**</span></span> 

<span data-ttu-id="43682-243">`expression`: `Int32`, `Int64`, `Double` o `Decimal`</span><span class="sxs-lookup"><span data-stu-id="43682-243">`expression`: `Int32`, `Int64`, `Double`, or `Decimal`</span></span> 

<span data-ttu-id="43682-244">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="43682-244">**Return Value**</span></span> 

<span data-ttu-id="43682-245">Un `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="43682-245">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="43682-246">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="43682-246">**Example**</span></span> 

`SqlServer.SIGN(-10)`

## <a name="sinexpression"></a><span data-ttu-id="43682-247">SIN(Expression)</span><span class="sxs-lookup"><span data-stu-id="43682-247">SIN(expression)</span></span>

<span data-ttu-id="43682-248">Calcula el seno trigonométrico de un ángulo especificado, en radianes, y devuelve una expresión de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="43682-248">Calculates the trigonometric sine of the specified angle in radians, and returns a `Double` expression.</span></span> 

<span data-ttu-id="43682-249">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="43682-249">**Arguments**</span></span> 

<span data-ttu-id="43682-250">`expression`: valor de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="43682-250">`expression`: A `Double`.</span></span> 

<span data-ttu-id="43682-251">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="43682-251">**Return Value**</span></span> 

<span data-ttu-id="43682-252">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="43682-252">A `Double`.</span></span> 

<span data-ttu-id="43682-253">**Ejemplo** `SqlServer.SIN(20)`</span><span class="sxs-lookup"><span data-stu-id="43682-253">**Example** `SqlServer.SIN(20)`</span></span>

## <a name="sqrtexpression"></a><span data-ttu-id="43682-254">SQRT(Expression)</span><span class="sxs-lookup"><span data-stu-id="43682-254">SQRT(expression)</span></span>

<span data-ttu-id="43682-255">Devuelve la raíz cuadrada de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="43682-255">Returns the square root of the specified expression.</span></span> 

<span data-ttu-id="43682-256">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="43682-256">**Arguments**</span></span> 

<span data-ttu-id="43682-257">`expression`: valor de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="43682-257">`expression`: A `Double`.</span></span> 

<span data-ttu-id="43682-258">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="43682-258">**Return Value**</span></span> 

<span data-ttu-id="43682-259">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="43682-259">A `Double`.</span></span> 

<span data-ttu-id="43682-260">**Ejemplo** `SqlServer.SQRT(3600)`</span><span class="sxs-lookup"><span data-stu-id="43682-260">**Example** `SqlServer.SQRT(3600)`</span></span>

## <a name="squareexpression"></a><span data-ttu-id="43682-261">Square(Expression)</span><span class="sxs-lookup"><span data-stu-id="43682-261">SQUARE(expression)</span></span>

<span data-ttu-id="43682-262">Devuelve la raíz cuadrada de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="43682-262">Returns the square of the specified expression.</span></span> 

<span data-ttu-id="43682-263">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="43682-263">**Arguments**</span></span> 

<span data-ttu-id="43682-264">`expression`: valor de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="43682-264">`expression`: A `Double`.</span></span> 

<span data-ttu-id="43682-265">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="43682-265">**Return Value**</span></span> 

<span data-ttu-id="43682-266">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="43682-266">A `Double`.</span></span> 

<span data-ttu-id="43682-267">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="43682-267">**Example**</span></span> 

`SqlServer.SQUARE(25)`

## <a name="tanexpression"></a><span data-ttu-id="43682-268">TAN(Expression)</span><span class="sxs-lookup"><span data-stu-id="43682-268">TAN(expression)</span></span>

<span data-ttu-id="43682-269">Calcula la tangente de una expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="43682-269">Calculates the tangent of a specified expression.</span></span>

<span data-ttu-id="43682-270">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="43682-270">**Arguments**</span></span> 

<span data-ttu-id="43682-271">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="43682-271">`expression`: `Double`</span></span> 

<span data-ttu-id="43682-272">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="43682-272">**Return Value**</span></span> 

`Double` 

<span data-ttu-id="43682-273">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="43682-273">**Example**</span></span> 

`SqlServer.TAN(45.0)`
  
## <a name="see-also"></a><span data-ttu-id="43682-274">Vea también</span><span class="sxs-lookup"><span data-stu-id="43682-274">See also</span></span>

<span data-ttu-id="43682-275">Para obtener más información sobre las funciones matemáticas que SqlClient admite, consulte la documentación de la versión de SQL Server que especificó en el manifiesto del proveedor SqlClient:</span><span class="sxs-lookup"><span data-stu-id="43682-275">For more information about the mathematical functions that SqlClient supports, see the documentation for the SQL Server version that you specified in the SqlClient provider manifest:</span></span>  
  
<span data-ttu-id="43682-276">**SQL Server 2005:** [funciones matemáticas (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms177516(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="43682-276">**SQL Server 2005:** [Mathematical Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms177516(v=sql.90))</span></span>  
<span data-ttu-id="43682-277">**SQL Server 2008:** [funciones matemáticas (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms177516(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="43682-277">**SQL Server 2008:** [Mathematical Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms177516(v=sql.100))</span></span>  
<span data-ttu-id="43682-278">**SQL Server 2012 y versiones posterior:** [funciones matemáticas (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql?view=sql-server-2017)</span><span class="sxs-lookup"><span data-stu-id="43682-278">**SQL Server 2012 and later:** [Mathematical Functions (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql?view=sql-server-2017)</span></span>   

 [<span data-ttu-id="43682-279">SqlClient para las funciones de Entity Framework</span><span class="sxs-lookup"><span data-stu-id="43682-279">SqlClient for Entity Framework Functions</span></span>](sqlclient-for-ef-functions.md)
