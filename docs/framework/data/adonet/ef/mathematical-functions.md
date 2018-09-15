---
title: Funciones matemáticas
ms.date: 03/30/2017
ms.assetid: b040c7cb-156d-40f2-9152-61065b18148c
ms.openlocfilehash: e6c58d781d7138f8295f2d0a2f0db110ad4b1dd6
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2018
ms.locfileid: "45595573"
---
# <a name="mathematical-functions"></a><span data-ttu-id="f13f1-102">Funciones matemáticas</span><span class="sxs-lookup"><span data-stu-id="f13f1-102">Mathematical Functions</span></span>

<span data-ttu-id="f13f1-103">El Proveedor de datos .NET Framework para SQL Server (SqlClient) proporciona funciones matemáticas que realizan cálculos con los valores de entrada que se proporcionan como argumentos y devuelven un resultado numérico.</span><span class="sxs-lookup"><span data-stu-id="f13f1-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides math functions that perform calculations on input values that are provided as arguments, and return a numeric value result.</span></span> <span data-ttu-id="f13f1-104">Estas funciones están en el espacio de nombres SqlServer, que está disponible al utilizar SqlClient.</span><span class="sxs-lookup"><span data-stu-id="f13f1-104">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="f13f1-105">La propiedad del espacio de nombres de un proveedor permite a Entity Framework detectar qué prefijo usa este proveedor para estructuras concretas, como los tipos y las funciones. La tabla siguiente describe las funciones matemáticas de SqlClient.</span><span class="sxs-lookup"><span data-stu-id="f13f1-105">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.The following table describes the SqlClient math functions.</span></span>  
  
## <a name="absexpression"></a><span data-ttu-id="f13f1-106">ABS(Expression)</span><span class="sxs-lookup"><span data-stu-id="f13f1-106">ABS(expression)</span></span>

<span data-ttu-id="f13f1-107">Lleva a cabo la función que devuelve el valor absoluto.</span><span class="sxs-lookup"><span data-stu-id="f13f1-107">Performs the absolute value function.</span></span>

<span data-ttu-id="f13f1-108">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="f13f1-108">**Arguments**</span></span>

<span data-ttu-id="f13f1-109">`expression`: valor de tipo`Int32`,`Int64`, `Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-109">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="f13f1-110">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="f13f1-110">**Return Value**</span></span>

<span data-ttu-id="f13f1-111">Valor absoluto de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="f13f1-111">The absolute value of the specified expression.</span></span>

<span data-ttu-id="f13f1-112">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="f13f1-112">**Example**</span></span>

`SqlServer.ABS(-2)`

## <a name="acosexpression"></a><span data-ttu-id="f13f1-113">ACOS(Expression)</span><span class="sxs-lookup"><span data-stu-id="f13f1-113">ACOS(expression)</span></span>

<span data-ttu-id="f13f1-114">Devuelve el valor del arcocoseno de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="f13f1-114">Returns the arccosine value of the specified expression.</span></span>

<span data-ttu-id="f13f1-115">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="f13f1-115">**Arguments**</span></span>

<span data-ttu-id="f13f1-116">`expression`: valor de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-116">`expression`: A `Double`.</span></span>

<span data-ttu-id="f13f1-117">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="f13f1-117">**Return Value**</span></span>

<span data-ttu-id="f13f1-118">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-118">A `Double`.</span></span>

<span data-ttu-id="f13f1-119">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="f13f1-119">**Example**</span></span>

`SqlServer.ACOS(.9)`

## <a name="asinexpression"></a><span data-ttu-id="f13f1-120">ASIN(Expression)</span><span class="sxs-lookup"><span data-stu-id="f13f1-120">ASIN(expression)</span></span>

<span data-ttu-id="f13f1-121">Devuelve el valor del arcoseno de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="f13f1-121">Returns the arcsine value of the specified expression.</span></span>

<span data-ttu-id="f13f1-122">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="f13f1-122">**Arguments**</span></span>

<span data-ttu-id="f13f1-123">`expression`: valor de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-123">`expression`: A `Double`.</span></span>

<span data-ttu-id="f13f1-124">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="f13f1-124">**Return Value**</span></span>

<span data-ttu-id="f13f1-125">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-125">A `Double`.</span></span>

<span data-ttu-id="f13f1-126">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="f13f1-126">**Example**</span></span>

`SqlServer.ASIN(.9)`

## <a name="atanexpression"></a><span data-ttu-id="f13f1-127">ATAN(Expression)</span><span class="sxs-lookup"><span data-stu-id="f13f1-127">ATAN(expression)</span></span>

<span data-ttu-id="f13f1-128">Devuelve el valor del arcotangente de la expresión numérica especificada.</span><span class="sxs-lookup"><span data-stu-id="f13f1-128">Returns the arctangent value of the specified numeric expression.</span></span>

<span data-ttu-id="f13f1-129">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="f13f1-129">**Arguments**</span></span>

<span data-ttu-id="f13f1-130">`expression`: valor de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-130">`expression`: A `Double`.</span></span>

<span data-ttu-id="f13f1-131">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="f13f1-131">**Return Value**</span></span>

<span data-ttu-id="f13f1-132">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-132">A `Double`.</span></span>

<span data-ttu-id="f13f1-133">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="f13f1-133">**Example**</span></span>

`SqlServer.ATAN(9)`

## <a name="atn2expression-expression"></a><span data-ttu-id="f13f1-134">ATN2(Expression, Expression)</span><span class="sxs-lookup"><span data-stu-id="f13f1-134">ATN2(expression, expression)</span></span>

<span data-ttu-id="f13f1-135">Devuelve el ángulo, en radianes, cuya tangente se encuentra entre las dos expresiones numéricas especificadas.</span><span class="sxs-lookup"><span data-stu-id="f13f1-135">Returns the angle, in radians, whose tangent is between the two specified numeric expressions.</span></span>

<span data-ttu-id="f13f1-136">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="f13f1-136">**Arguments**</span></span>

<span data-ttu-id="f13f1-137">`expression`: valor de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-137">`expression`: A `Double`.</span></span>

<span data-ttu-id="f13f1-138">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="f13f1-138">**Return Value**</span></span>

<span data-ttu-id="f13f1-139">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-139">A `Double`.</span></span>

<span data-ttu-id="f13f1-140">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="f13f1-140">**Example**</span></span>

`SqlServer.ATN2(9, 8)`
 
## <a name="ceilingexpression"></a><span data-ttu-id="f13f1-141">CEILING(Expression)</span><span class="sxs-lookup"><span data-stu-id="f13f1-141">CEILING(expression)</span></span>

<span data-ttu-id="f13f1-142">Convierte la expresión especificada al número entero más pequeño mayor o igual que él.</span><span class="sxs-lookup"><span data-stu-id="f13f1-142">Converts the specified expression to the smallest integer that is greater than or equal to it.</span></span>

<span data-ttu-id="f13f1-143">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="f13f1-143">**Arguments**</span></span>

<span data-ttu-id="f13f1-144">`expression`: valor de tipo`Int32`,`Int64`, `Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-144">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="f13f1-145">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="f13f1-145">**Return Value**</span></span>

<span data-ttu-id="f13f1-146">Un `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-146">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="f13f1-147">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="f13f1-147">**Example**</span></span> 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_ceiling)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_ceiling)]

## <a name="cosexpression"></a><span data-ttu-id="f13f1-148">COS(Expression)</span><span class="sxs-lookup"><span data-stu-id="f13f1-148">COS(expression)</span></span>

<span data-ttu-id="f13f1-149">Calcula el coseno trigonométrico del ángulo especificado, en radianes.</span><span class="sxs-lookup"><span data-stu-id="f13f1-149">Calculates the trigonometric cosine of the specified angle in radians.</span></span> 

<span data-ttu-id="f13f1-150">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="f13f1-150">**Arguments**</span></span> 

<span data-ttu-id="f13f1-151">`expression`: valor de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-151">`expression`: A `Double`.</span></span> 

<span data-ttu-id="f13f1-152">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="f13f1-152">**Return Value**</span></span> 

<span data-ttu-id="f13f1-153">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-153">A `Double`.</span></span> 

<span data-ttu-id="f13f1-154">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="f13f1-154">**Example**</span></span> 

`SqlServer.COS(45)`

## <a name="cotexpression"></a><span data-ttu-id="f13f1-155">COT(Expression)</span><span class="sxs-lookup"><span data-stu-id="f13f1-155">COT(expression)</span></span>

<span data-ttu-id="f13f1-156">Calcula la cotangente trigonométrica del ángulo especificado, en radianes.</span><span class="sxs-lookup"><span data-stu-id="f13f1-156">Calculates the trigonometric cotangent of the specified angle in radians.</span></span> 

<span data-ttu-id="f13f1-157">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="f13f1-157">**Arguments**</span></span> 

<span data-ttu-id="f13f1-158">`expression`: valor de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-158">`expression`: A `Double`.</span></span> 

<span data-ttu-id="f13f1-159">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="f13f1-159">**Return Value**</span></span> 

<span data-ttu-id="f13f1-160">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-160">A `Double`.</span></span> 

<span data-ttu-id="f13f1-161">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="f13f1-161">**Example**</span></span> 

`SqlServer.COT(60)`
  
## <a name="degreesradians"></a><span data-ttu-id="f13f1-162">Degrees(RADIANS)</span><span class="sxs-lookup"><span data-stu-id="f13f1-162">DEGREES(radians)</span></span>

<span data-ttu-id="f13f1-163">Devuelve el ángulo correspondiente en grados.</span><span class="sxs-lookup"><span data-stu-id="f13f1-163">Returns the corresponding angle in degrees.</span></span> 

<span data-ttu-id="f13f1-164">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="f13f1-164">**Arguments**</span></span> 

<span data-ttu-id="f13f1-165">`expression`: valor de tipo`Int32`,`Int64`, `Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-165">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="f13f1-166">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="f13f1-166">**Return Value**</span></span> 

<span data-ttu-id="f13f1-167">Un `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-167">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="f13f1-168">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="f13f1-168">**Example**</span></span> 

`SqlServer.DEGREES(3.1)`

## <a name="expexpression"></a><span data-ttu-id="f13f1-169">EXP(Expression)</span><span class="sxs-lookup"><span data-stu-id="f13f1-169">EXP(expression)</span></span>

<span data-ttu-id="f13f1-170">Calcula el valor exponencial de la expresión numérica especificada.</span><span class="sxs-lookup"><span data-stu-id="f13f1-170">Calculates the exponential value of a specified numeric expression.</span></span> 

<span data-ttu-id="f13f1-171">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="f13f1-171">**Arguments**</span></span> 

<span data-ttu-id="f13f1-172">`expression`: valor de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-172">`expression`: A `Double`.</span></span> 

<span data-ttu-id="f13f1-173">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="f13f1-173">**Return Value**</span></span> 

<span data-ttu-id="f13f1-174">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-174">A `Double`.</span></span> 

<span data-ttu-id="f13f1-175">**Ejemplo** `SqlServer.EXP(1)`</span><span class="sxs-lookup"><span data-stu-id="f13f1-175">**Example** `SqlServer.EXP(1)`</span></span>

## <a name="floorexpression"></a><span data-ttu-id="f13f1-176">Floor(Expression)</span><span class="sxs-lookup"><span data-stu-id="f13f1-176">FLOOR(expression)</span></span>

<span data-ttu-id="f13f1-177">Convierte la expresión especificada al número entero más grande que sea menor o igual que ella.</span><span class="sxs-lookup"><span data-stu-id="f13f1-177">Converts the specified expression to the largest integer less than or equal to it.</span></span> 

<span data-ttu-id="f13f1-178">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="f13f1-178">**Arguments**</span></span> 

<span data-ttu-id="f13f1-179">`expression`: valor de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-179">`expression`: A `Double`.</span></span> 

<span data-ttu-id="f13f1-180">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="f13f1-180">**Return Value**</span></span> 

<span data-ttu-id="f13f1-181">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-181">A `Double`.</span></span> 

<span data-ttu-id="f13f1-182">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="f13f1-182">**Example**</span></span> 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_floor)] 
[!code-sql[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_floor)]

## <a name="logexpression"></a><span data-ttu-id="f13f1-183">LOG(Expression)</span><span class="sxs-lookup"><span data-stu-id="f13f1-183">LOG(expression)</span></span>

<span data-ttu-id="f13f1-184">Calcula el logaritmo natural de la expresión `float` especificada.</span><span class="sxs-lookup"><span data-stu-id="f13f1-184">Calculates the natural logarithm of the specified `float` expression.</span></span> 

<span data-ttu-id="f13f1-185">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="f13f1-185">**Arguments**</span></span> 

<span data-ttu-id="f13f1-186">`expression`: valor de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-186">`expression`: A `Double`.</span></span> 

<span data-ttu-id="f13f1-187">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="f13f1-187">**Return Value**</span></span> 

<span data-ttu-id="f13f1-188">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-188">A `Double`.</span></span> 

<span data-ttu-id="f13f1-189">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="f13f1-189">**Example**</span></span> 

`SqlServer.LOG(100)`

## <a name="log10expression"></a><span data-ttu-id="f13f1-190">LOG10(Expression)</span><span class="sxs-lookup"><span data-stu-id="f13f1-190">LOG10(expression)</span></span>

<span data-ttu-id="f13f1-191">Devuelve el logaritmo en base 10 de la expresión `Double` especificada.</span><span class="sxs-lookup"><span data-stu-id="f13f1-191">Returns the base-10 logarithm of the specified `Double` expression.</span></span> 

<span data-ttu-id="f13f1-192">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="f13f1-192">**Arguments**</span></span> 

<span data-ttu-id="f13f1-193">`expression`: valor de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-193">`expression`: A `Double`.</span></span> 

<span data-ttu-id="f13f1-194">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="f13f1-194">**Return Value**</span></span> 

<span data-ttu-id="f13f1-195">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-195">A `Double`.</span></span> 

<span data-ttu-id="f13f1-196">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="f13f1-196">**Example**</span></span> 

`SqlServer.LOG10(100)`

## <a name="pi"></a><span data-ttu-id="f13f1-197">PI()</span><span class="sxs-lookup"><span data-stu-id="f13f1-197">PI()</span></span>

<span data-ttu-id="f13f1-198">Devuelve el valor constante de Pi como un `Double`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-198">Returns the constant value of pi as a `Double`.</span></span> 

<span data-ttu-id="f13f1-199">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="f13f1-199">**Return Value**</span></span> 

<span data-ttu-id="f13f1-200">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-200">A `Double`.</span></span> 

<span data-ttu-id="f13f1-201">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="f13f1-201">**Example**</span></span> 

`SqlServer.PI()`

## <a name="powernumericexpression-powerexpression"></a><span data-ttu-id="f13f1-202">POWER (numeric_expression, power_expression)</span><span class="sxs-lookup"><span data-stu-id="f13f1-202">POWER(numeric_expression, power_expression)</span></span>

<span data-ttu-id="f13f1-203">Calcula el valor de la expresión especificada elevada a la potencia indicada.</span><span class="sxs-lookup"><span data-stu-id="f13f1-203">Calculates the value of a specified expression to a specified power.</span></span>

<span data-ttu-id="f13f1-204">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="f13f1-204">**Arguments**</span></span> 

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="f13f1-205">Un `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-205">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>|
|`power_expression`| <span data-ttu-id="f13f1-206">Un `Double` que representa la potencia a la que se va a generar el `numeric_expression`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-206">A `Double` that represents the power to which to raise the `numeric_expression`.</span></span>| 

<span data-ttu-id="f13f1-207">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="f13f1-207">**Return Value**</span></span> 

<span data-ttu-id="f13f1-208">Valor de la `numeric_expression` especificada a la `power_expression` especificada.</span><span class="sxs-lookup"><span data-stu-id="f13f1-208">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span> 

<span data-ttu-id="f13f1-209">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="f13f1-209">**Example**</span></span> 

`SqlServer.POWER(2,7)`

## <a name="radiansexpression"></a><span data-ttu-id="f13f1-210">RADIANS(Expression)</span><span class="sxs-lookup"><span data-stu-id="f13f1-210">RADIANS(expression)</span></span>

<span data-ttu-id="f13f1-211">Convierte grados en radianes.</span><span class="sxs-lookup"><span data-stu-id="f13f1-211">Converts degrees to radians.</span></span> 

<span data-ttu-id="f13f1-212">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="f13f1-212">**Arguments**</span></span> 

<span data-ttu-id="f13f1-213">`expression`: valor de tipo`Int32`,`Int64`, `Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-213">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="f13f1-214">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="f13f1-214">**Return Value**</span></span> 

<span data-ttu-id="f13f1-215">Un `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-215">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="f13f1-216">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="f13f1-216">**Example**</span></span> 

`SqlServer.RADIANS(360.0)`

## <a name="randseed"></a><span data-ttu-id="f13f1-217">RAND([SEED])</span><span class="sxs-lookup"><span data-stu-id="f13f1-217">RAND([seed])</span></span>

<span data-ttu-id="f13f1-218">Devuelve un valor aleatorio de 0 a 1.</span><span class="sxs-lookup"><span data-stu-id="f13f1-218">Returns a random value from 0 through 1.</span></span> 

<span data-ttu-id="f13f1-219">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="f13f1-219">**Arguments**</span></span> 

<span data-ttu-id="f13f1-220">El valor de inicialización como una `Int32`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-220">The seed value as an `Int32`.</span></span> <span data-ttu-id="f13f1-221">Si la inicialización no se especifica, el motor de base de datos de SQL Server asigna uno de forma aleatoria.</span><span class="sxs-lookup"><span data-stu-id="f13f1-221">If the seed is not specified, the SQL Server Database Engine assigns a seed value at random.</span></span> <span data-ttu-id="f13f1-222">Para un valor de inicialización especificado, el resultado devuelto es siempre el mismo.</span><span class="sxs-lookup"><span data-stu-id="f13f1-222">For a specified seed value, the result returned is always the same.</span></span>

<span data-ttu-id="f13f1-223">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="f13f1-223">**Return Value**</span></span> 

<span data-ttu-id="f13f1-224">Valor `Double` aleatorio de 0 a 1.</span><span class="sxs-lookup"><span data-stu-id="f13f1-224">A random `Double` value from 0 through 1.</span></span> 

<span data-ttu-id="f13f1-225">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="f13f1-225">**Example**</span></span> 

`SqlServer.RAND()`
  
## <a name="roundnumericexpression-lengthfunction"></a><span data-ttu-id="f13f1-226">Round(numeric_expression, Length[,Function])</span><span class="sxs-lookup"><span data-stu-id="f13f1-226">ROUND(numeric_expression, length[,function])</span></span>

<span data-ttu-id="f13f1-227">Devuelve una expresión numérica, redondeada a la longitud o precisión especificadas.</span><span class="sxs-lookup"><span data-stu-id="f13f1-227">Returns a numeric expression, rounded to the specified length or precision.</span></span> 

<span data-ttu-id="f13f1-228">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="f13f1-228">**Arguments**</span></span> 

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="f13f1-229">Un `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-229">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 
|`length`| <span data-ttu-id="f13f1-230">Valor `Int32` que representa la precisión a la que se va a redondear `numeric_expression`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-230">An `Int32` that represents the precision to which `numeric_expression` is to be rounded.</span></span> <span data-ttu-id="f13f1-231">Si `length` es un número positivo, `numeric_expression` se redondea al número de posiciones decimales que especifica `length`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-231">When `length` is a positive number, `numeric_expression` is rounded to the number of decimal positions specified by `length`.</span></span> <span data-ttu-id="f13f1-232">Si `length` es un número negativo, `numeric_expression` se redondea a la izquierda del separador decimal, según se especifica en `length`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-232">When `length` is a negative number, `numeric_expression` is rounded on the left side of the decimal point, as specified by `length`.</span></span>|
|`function` | <span data-ttu-id="f13f1-233">Opcional.</span><span class="sxs-lookup"><span data-stu-id="f13f1-233">Optional.</span></span> <span data-ttu-id="f13f1-234">Un `Int32` que representa el tipo de operación que se realiza.</span><span class="sxs-lookup"><span data-stu-id="f13f1-234">An `Int32` that represents the type of operation to perform.</span></span> <span data-ttu-id="f13f1-235">Cuando la función se omite o tiene un valor de 0 (valor predeterminado), `numeric_expression` se redondea.</span><span class="sxs-lookup"><span data-stu-id="f13f1-235">When function is omitted or has a value of 0 (default), `numeric_expression` is rounded.</span></span> <span data-ttu-id="f13f1-236">Si un valor distinto de 0 se especifica, `numeric_expression` se trunca.</span><span class="sxs-lookup"><span data-stu-id="f13f1-236">When a value other than 0 is specified, `numeric_expression` is truncated.</span></span> |

<span data-ttu-id="f13f1-237">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="f13f1-237">**Return Value**</span></span> 

<span data-ttu-id="f13f1-238">Valor de la `numeric_expression` especificada a la `power_expression` especificada.</span><span class="sxs-lookup"><span data-stu-id="f13f1-238">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span>

<span data-ttu-id="f13f1-239">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="f13f1-239">**Example**</span></span> 

`SqlServer.ROUND(748.58, -3)`

## <a name="signexpression"></a><span data-ttu-id="f13f1-240">Sign(Expression)</span><span class="sxs-lookup"><span data-stu-id="f13f1-240">SIGN(expression)</span></span> 

<span data-ttu-id="f13f1-241">Devuelve el signo positivo (+1), cero (0) o negativo (-1) de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="f13f1-241">Returns the positive (+1), zero (0), or negative (-1) sign of the specified expression.</span></span> 

<span data-ttu-id="f13f1-242">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="f13f1-242">**Arguments**</span></span> 

<span data-ttu-id="f13f1-243">`expression`: `Int32`, `Int64`, `Double` o `Decimal`</span><span class="sxs-lookup"><span data-stu-id="f13f1-243">`expression`: `Int32`, `Int64`, `Double`, or `Decimal`</span></span> 

<span data-ttu-id="f13f1-244">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="f13f1-244">**Return Value**</span></span> 

<span data-ttu-id="f13f1-245">Un `Int32`, `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-245">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="f13f1-246">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="f13f1-246">**Example**</span></span> 

`SqlServer.SIGN(-10)`

## <a name="sinexpression"></a><span data-ttu-id="f13f1-247">SIN(Expression)</span><span class="sxs-lookup"><span data-stu-id="f13f1-247">SIN(expression)</span></span>

<span data-ttu-id="f13f1-248">Calcula el seno trigonométrico de un ángulo especificado, en radianes, y devuelve una expresión de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-248">Calculates the trigonometric sine of the specified angle in radians, and returns a `Double` expression.</span></span> 

<span data-ttu-id="f13f1-249">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="f13f1-249">**Arguments**</span></span> 

<span data-ttu-id="f13f1-250">`expression`: valor de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-250">`expression`: A `Double`.</span></span> 

<span data-ttu-id="f13f1-251">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="f13f1-251">**Return Value**</span></span> 

<span data-ttu-id="f13f1-252">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-252">A `Double`.</span></span> 

<span data-ttu-id="f13f1-253">**Ejemplo** `SqlServer.SIN(20)`</span><span class="sxs-lookup"><span data-stu-id="f13f1-253">**Example** `SqlServer.SIN(20)`</span></span>

## <a name="sqrtexpression"></a><span data-ttu-id="f13f1-254">SQRT(Expression)</span><span class="sxs-lookup"><span data-stu-id="f13f1-254">SQRT(expression)</span></span>

<span data-ttu-id="f13f1-255">Devuelve la raíz cuadrada de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="f13f1-255">Returns the square root of the specified expression.</span></span> 

<span data-ttu-id="f13f1-256">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="f13f1-256">**Arguments**</span></span> 

<span data-ttu-id="f13f1-257">`expression`: valor de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-257">`expression`: A `Double`.</span></span> 

<span data-ttu-id="f13f1-258">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="f13f1-258">**Return Value**</span></span> 

<span data-ttu-id="f13f1-259">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-259">A `Double`.</span></span> 

<span data-ttu-id="f13f1-260">**Ejemplo** `SqlServer.SQRT(3600)`</span><span class="sxs-lookup"><span data-stu-id="f13f1-260">**Example** `SqlServer.SQRT(3600)`</span></span>

## <a name="squareexpression"></a><span data-ttu-id="f13f1-261">Square(Expression)</span><span class="sxs-lookup"><span data-stu-id="f13f1-261">SQUARE(expression)</span></span>

<span data-ttu-id="f13f1-262">Devuelve la raíz cuadrada de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="f13f1-262">Returns the square of the specified expression.</span></span> 

<span data-ttu-id="f13f1-263">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="f13f1-263">**Arguments**</span></span> 

<span data-ttu-id="f13f1-264">`expression`: valor de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-264">`expression`: A `Double`.</span></span> 

<span data-ttu-id="f13f1-265">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="f13f1-265">**Return Value**</span></span> 

<span data-ttu-id="f13f1-266">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="f13f1-266">A `Double`.</span></span> 

<span data-ttu-id="f13f1-267">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="f13f1-267">**Example**</span></span> 

`SqlServer.SQUARE(25)`

## <a name="tanexpression"></a><span data-ttu-id="f13f1-268">TAN(Expression)</span><span class="sxs-lookup"><span data-stu-id="f13f1-268">TAN(expression)</span></span>

<span data-ttu-id="f13f1-269">Calcula la tangente de una expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="f13f1-269">Calculates the tangent of a specified expression.</span></span>

<span data-ttu-id="f13f1-270">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="f13f1-270">**Arguments**</span></span> 

<span data-ttu-id="f13f1-271">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="f13f1-271">`expression`: `Double`</span></span> 

<span data-ttu-id="f13f1-272">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="f13f1-272">**Return Value**</span></span> 

`Double` 

<span data-ttu-id="f13f1-273">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="f13f1-273">**Example**</span></span> 

`SqlServer.TAN(45.0)`
  
## <a name="see-also"></a><span data-ttu-id="f13f1-274">Vea también</span><span class="sxs-lookup"><span data-stu-id="f13f1-274">See also</span></span>

<span data-ttu-id="f13f1-275">Para obtener más información sobre las funciones matemáticas que SqlClient admite, consulte la documentación de la versión de SQL Server que especificó en el manifiesto del proveedor SqlClient:</span><span class="sxs-lookup"><span data-stu-id="f13f1-275">For more information about the mathematical functions that SqlClient supports, see the documentation for the SQL Server version that you specified in the SqlClient provider manifest:</span></span>  
  
<span data-ttu-id="f13f1-276">**SQL Server 2005:** [funciones matemáticas (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms177516(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="f13f1-276">**SQL Server 2005:** [Mathematical Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms177516(v=sql.90))</span></span>  
<span data-ttu-id="f13f1-277">**SQL Server 2008:** [funciones matemáticas (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms177516(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="f13f1-277">**SQL Server 2008:** [Mathematical Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms177516(v=sql.100))</span></span>  
<span data-ttu-id="f13f1-278">**SQL Server 2012 y versiones posterior:** [funciones matemáticas (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql?view=sql-server-2017)</span><span class="sxs-lookup"><span data-stu-id="f13f1-278">**SQL Server 2012 and later:** [Mathematical Functions (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql?view=sql-server-2017)</span></span>   

 [<span data-ttu-id="f13f1-279">SqlClient para las funciones de Entity Framework</span><span class="sxs-lookup"><span data-stu-id="f13f1-279">SqlClient for Entity Framework Functions</span></span>](sqlclient-for-ef-functions.md)
