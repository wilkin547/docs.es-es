---
title: Funciones matemáticas
ms.date: 03/30/2017
ms.assetid: b040c7cb-156d-40f2-9152-61065b18148c
ms.openlocfilehash: 664d1a4f67ecced6713f83bf3dd11931c9b4dc18
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700001"
---
# <a name="mathematical-functions"></a><span data-ttu-id="c2d3f-102">Funciones matemáticas</span><span class="sxs-lookup"><span data-stu-id="c2d3f-102">Mathematical Functions</span></span>

<span data-ttu-id="c2d3f-103">El Proveedor de datos .NET Framework para SQL Server (SqlClient) proporciona funciones matemáticas que realizan cálculos con los valores de entrada que se proporcionan como argumentos y devuelven un resultado numérico.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides math functions that perform calculations on input values that are provided as arguments, and return a numeric value result.</span></span> <span data-ttu-id="c2d3f-104">Estas funciones están en el espacio de nombres SqlServer, que está disponible al utilizar SqlClient.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-104">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="c2d3f-105">La propiedad del espacio de nombres de un proveedor permite a Entity Framework detectar qué prefijo usa este proveedor para estructuras concretas, como tipos y funciones.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-105">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span> <span data-ttu-id="c2d3f-106">En la tabla siguiente se describen las funciones matemáticas de SqlClient.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-106">The following table describes the SqlClient math functions.</span></span>  
  
## <a name="absexpression"></a><span data-ttu-id="c2d3f-107">ABS (expresión)</span><span class="sxs-lookup"><span data-stu-id="c2d3f-107">ABS(expression)</span></span>

<span data-ttu-id="c2d3f-108">Lleva a cabo la función que devuelve el valor absoluto.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-108">Performs the absolute value function.</span></span>

<span data-ttu-id="c2d3f-109">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-109">**Arguments**</span></span>

<span data-ttu-id="c2d3f-110">`expression`: `Int32`, ,`Int64` O`Decimal`. `Double`</span><span class="sxs-lookup"><span data-stu-id="c2d3f-110">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="c2d3f-111">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-111">**Return Value**</span></span>

<span data-ttu-id="c2d3f-112">Valor absoluto de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-112">The absolute value of the specified expression.</span></span>

<span data-ttu-id="c2d3f-113">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-113">**Example**</span></span>

`SqlServer.ABS(-2)`

## <a name="acosexpression"></a><span data-ttu-id="c2d3f-114">ACOS (expresión)</span><span class="sxs-lookup"><span data-stu-id="c2d3f-114">ACOS(expression)</span></span>

<span data-ttu-id="c2d3f-115">Devuelve el valor del arcocoseno de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-115">Returns the arccosine value of the specified expression.</span></span>

<span data-ttu-id="c2d3f-116">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-116">**Arguments**</span></span>

<span data-ttu-id="c2d3f-117">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-117">`expression`: A `Double`.</span></span>

<span data-ttu-id="c2d3f-118">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-118">**Return Value**</span></span>

<span data-ttu-id="c2d3f-119">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-119">A `Double`.</span></span>

<span data-ttu-id="c2d3f-120">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-120">**Example**</span></span>

`SqlServer.ACOS(.9)`

## <a name="asinexpression"></a><span data-ttu-id="c2d3f-121">ASIN (expresión)</span><span class="sxs-lookup"><span data-stu-id="c2d3f-121">ASIN(expression)</span></span>

<span data-ttu-id="c2d3f-122">Devuelve el valor del arcoseno de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-122">Returns the arcsine value of the specified expression.</span></span>

<span data-ttu-id="c2d3f-123">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-123">**Arguments**</span></span>

<span data-ttu-id="c2d3f-124">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-124">`expression`: A `Double`.</span></span>

<span data-ttu-id="c2d3f-125">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-125">**Return Value**</span></span>

<span data-ttu-id="c2d3f-126">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-126">A `Double`.</span></span>

<span data-ttu-id="c2d3f-127">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-127">**Example**</span></span>

`SqlServer.ASIN(.9)`

## <a name="atanexpression"></a><span data-ttu-id="c2d3f-128">ATAN (expresión)</span><span class="sxs-lookup"><span data-stu-id="c2d3f-128">ATAN(expression)</span></span>

<span data-ttu-id="c2d3f-129">Devuelve el valor del arcotangente de la expresión numérica especificada.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-129">Returns the arctangent value of the specified numeric expression.</span></span>

<span data-ttu-id="c2d3f-130">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-130">**Arguments**</span></span>

<span data-ttu-id="c2d3f-131">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-131">`expression`: A `Double`.</span></span>

<span data-ttu-id="c2d3f-132">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-132">**Return Value**</span></span>

<span data-ttu-id="c2d3f-133">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-133">A `Double`.</span></span>

<span data-ttu-id="c2d3f-134">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-134">**Example**</span></span>

`SqlServer.ATAN(9)`

## <a name="atn2expression-expression"></a><span data-ttu-id="c2d3f-135">ATN2 (expresión, expresión)</span><span class="sxs-lookup"><span data-stu-id="c2d3f-135">ATN2(expression, expression)</span></span>

<span data-ttu-id="c2d3f-136">Devuelve el ángulo, en radianes, cuya tangente se encuentra entre las dos expresiones numéricas especificadas.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-136">Returns the angle, in radians, whose tangent is between the two specified numeric expressions.</span></span>

<span data-ttu-id="c2d3f-137">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-137">**Arguments**</span></span>

<span data-ttu-id="c2d3f-138">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-138">`expression`: A `Double`.</span></span>

<span data-ttu-id="c2d3f-139">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-139">**Return Value**</span></span>

<span data-ttu-id="c2d3f-140">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-140">A `Double`.</span></span>

<span data-ttu-id="c2d3f-141">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-141">**Example**</span></span>

`SqlServer.ATN2(9, 8)`
 
## <a name="ceilingexpression"></a><span data-ttu-id="c2d3f-142">CEILING (expresión)</span><span class="sxs-lookup"><span data-stu-id="c2d3f-142">CEILING(expression)</span></span>

<span data-ttu-id="c2d3f-143">Convierte la expresión especificada al número entero más pequeño mayor o igual que él.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-143">Converts the specified expression to the smallest integer that is greater than or equal to it.</span></span>

<span data-ttu-id="c2d3f-144">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-144">**Arguments**</span></span>

<span data-ttu-id="c2d3f-145">`expression`: `Int32`, ,`Int64` O`Decimal`. `Double`</span><span class="sxs-lookup"><span data-stu-id="c2d3f-145">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="c2d3f-146">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-146">**Return Value**</span></span>

<span data-ttu-id="c2d3f-147">`Int32`, ,`Int64` O`Decimal`. `Double`</span><span class="sxs-lookup"><span data-stu-id="c2d3f-147">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="c2d3f-148">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-148">**Example**</span></span> 

[!code-sql[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_ceiling)]

## <a name="cosexpression"></a><span data-ttu-id="c2d3f-149">COS (expresión)</span><span class="sxs-lookup"><span data-stu-id="c2d3f-149">COS(expression)</span></span>

<span data-ttu-id="c2d3f-150">Calcula el coseno trigonométrico del ángulo especificado, en radianes.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-150">Calculates the trigonometric cosine of the specified angle in radians.</span></span> 

<span data-ttu-id="c2d3f-151">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-151">**Arguments**</span></span> 

<span data-ttu-id="c2d3f-152">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-152">`expression`: A `Double`.</span></span> 

<span data-ttu-id="c2d3f-153">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-153">**Return Value**</span></span> 

<span data-ttu-id="c2d3f-154">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-154">A `Double`.</span></span> 

<span data-ttu-id="c2d3f-155">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-155">**Example**</span></span> 

`SqlServer.COS(45)`

## <a name="cotexpression"></a><span data-ttu-id="c2d3f-156">COT (expresión)</span><span class="sxs-lookup"><span data-stu-id="c2d3f-156">COT(expression)</span></span>

<span data-ttu-id="c2d3f-157">Calcula la cotangente trigonométrica del ángulo especificado, en radianes.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-157">Calculates the trigonometric cotangent of the specified angle in radians.</span></span> 

<span data-ttu-id="c2d3f-158">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-158">**Arguments**</span></span> 

<span data-ttu-id="c2d3f-159">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-159">`expression`: A `Double`.</span></span> 

<span data-ttu-id="c2d3f-160">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-160">**Return Value**</span></span> 

<span data-ttu-id="c2d3f-161">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-161">A `Double`.</span></span> 

<span data-ttu-id="c2d3f-162">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-162">**Example**</span></span> 

`SqlServer.COT(60)`
  
## <a name="degreesradians"></a><span data-ttu-id="c2d3f-163">GRADOS (radianes)</span><span class="sxs-lookup"><span data-stu-id="c2d3f-163">DEGREES(radians)</span></span>

<span data-ttu-id="c2d3f-164">Devuelve el ángulo correspondiente en grados.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-164">Returns the corresponding angle in degrees.</span></span> 

<span data-ttu-id="c2d3f-165">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-165">**Arguments**</span></span> 

<span data-ttu-id="c2d3f-166">`expression`: `Int32`, ,`Int64` O`Decimal`. `Double`</span><span class="sxs-lookup"><span data-stu-id="c2d3f-166">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="c2d3f-167">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-167">**Return Value**</span></span> 

<span data-ttu-id="c2d3f-168">`Int32`, ,`Int64` O`Decimal`. `Double`</span><span class="sxs-lookup"><span data-stu-id="c2d3f-168">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="c2d3f-169">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-169">**Example**</span></span> 

`SqlServer.DEGREES(3.1)`

## <a name="expexpression"></a><span data-ttu-id="c2d3f-170">EXP (expresión)</span><span class="sxs-lookup"><span data-stu-id="c2d3f-170">EXP(expression)</span></span>

<span data-ttu-id="c2d3f-171">Calcula el valor exponencial de la expresión numérica especificada.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-171">Calculates the exponential value of a specified numeric expression.</span></span> 

<span data-ttu-id="c2d3f-172">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-172">**Arguments**</span></span> 

<span data-ttu-id="c2d3f-173">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-173">`expression`: A `Double`.</span></span> 

<span data-ttu-id="c2d3f-174">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-174">**Return Value**</span></span> 

<span data-ttu-id="c2d3f-175">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-175">A `Double`.</span></span> 

<span data-ttu-id="c2d3f-176">**Ejemplo** de`SqlServer.EXP(1)`</span><span class="sxs-lookup"><span data-stu-id="c2d3f-176">**Example** `SqlServer.EXP(1)`</span></span>

## <a name="floorexpression"></a><span data-ttu-id="c2d3f-177">FLOOR (expresión)</span><span class="sxs-lookup"><span data-stu-id="c2d3f-177">FLOOR(expression)</span></span>

<span data-ttu-id="c2d3f-178">Convierte la expresión especificada al número entero más grande que sea menor o igual que ella.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-178">Converts the specified expression to the largest integer less than or equal to it.</span></span> 

<span data-ttu-id="c2d3f-179">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-179">**Arguments**</span></span> 

<span data-ttu-id="c2d3f-180">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-180">`expression`: A `Double`.</span></span> 

<span data-ttu-id="c2d3f-181">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-181">**Return Value**</span></span> 

<span data-ttu-id="c2d3f-182">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-182">A `Double`.</span></span> 

<span data-ttu-id="c2d3f-183">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-183">**Example**</span></span> 

[!code-sql[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_floor)]

## <a name="logexpression"></a><span data-ttu-id="c2d3f-184">LOG (expresión)</span><span class="sxs-lookup"><span data-stu-id="c2d3f-184">LOG(expression)</span></span>

<span data-ttu-id="c2d3f-185">Calcula el logaritmo natural de la expresión `float` especificada.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-185">Calculates the natural logarithm of the specified `float` expression.</span></span> 

<span data-ttu-id="c2d3f-186">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-186">**Arguments**</span></span> 

<span data-ttu-id="c2d3f-187">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-187">`expression`: A `Double`.</span></span> 

<span data-ttu-id="c2d3f-188">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-188">**Return Value**</span></span> 

<span data-ttu-id="c2d3f-189">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-189">A `Double`.</span></span> 

<span data-ttu-id="c2d3f-190">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-190">**Example**</span></span> 

`SqlServer.LOG(100)`

## <a name="log10expression"></a><span data-ttu-id="c2d3f-191">LOG10 (expresión)</span><span class="sxs-lookup"><span data-stu-id="c2d3f-191">LOG10(expression)</span></span>

<span data-ttu-id="c2d3f-192">Devuelve el logaritmo en base 10 de la expresión `Double` especificada.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-192">Returns the base-10 logarithm of the specified `Double` expression.</span></span> 

<span data-ttu-id="c2d3f-193">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-193">**Arguments**</span></span> 

<span data-ttu-id="c2d3f-194">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-194">`expression`: A `Double`.</span></span> 

<span data-ttu-id="c2d3f-195">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-195">**Return Value**</span></span> 

<span data-ttu-id="c2d3f-196">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-196">A `Double`.</span></span> 

<span data-ttu-id="c2d3f-197">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-197">**Example**</span></span> 

`SqlServer.LOG10(100)`

## <a name="pi"></a><span data-ttu-id="c2d3f-198">PI()</span><span class="sxs-lookup"><span data-stu-id="c2d3f-198">PI()</span></span>

<span data-ttu-id="c2d3f-199">Devuelve el valor constante de Pi como un `Double`.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-199">Returns the constant value of pi as a `Double`.</span></span> 

<span data-ttu-id="c2d3f-200">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-200">**Return Value**</span></span> 

<span data-ttu-id="c2d3f-201">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-201">A `Double`.</span></span> 

<span data-ttu-id="c2d3f-202">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-202">**Example**</span></span> 

`SqlServer.PI()`

## <a name="powernumeric_expression-power_expression"></a><span data-ttu-id="c2d3f-203">POWER (numeric_expression, power_expression)</span><span class="sxs-lookup"><span data-stu-id="c2d3f-203">POWER(numeric_expression, power_expression)</span></span>

<span data-ttu-id="c2d3f-204">Calcula el valor de la expresión especificada elevada a la potencia indicada.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-204">Calculates the value of a specified expression to a specified power.</span></span>

<span data-ttu-id="c2d3f-205">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-205">**Arguments**</span></span> 

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="c2d3f-206">`Int32`, ,`Int64` O`Decimal`. `Double`</span><span class="sxs-lookup"><span data-stu-id="c2d3f-206">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>|
|`power_expression`| <span data-ttu-id="c2d3f-207">Que representa la potencia a la que se eleva el `numeric_expression`. `Double`</span><span class="sxs-lookup"><span data-stu-id="c2d3f-207">A `Double` that represents the power to which to raise the `numeric_expression`.</span></span>| 

<span data-ttu-id="c2d3f-208">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-208">**Return Value**</span></span> 

<span data-ttu-id="c2d3f-209">Valor de la `numeric_expression` especificada a la `power_expression` especificada.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-209">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span> 

<span data-ttu-id="c2d3f-210">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-210">**Example**</span></span> 

`SqlServer.POWER(2,7)`

## <a name="radiansexpression"></a><span data-ttu-id="c2d3f-211">RADIAnes (expresión)</span><span class="sxs-lookup"><span data-stu-id="c2d3f-211">RADIANS(expression)</span></span>

<span data-ttu-id="c2d3f-212">Convierte grados en radianes.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-212">Converts degrees to radians.</span></span> 

<span data-ttu-id="c2d3f-213">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-213">**Arguments**</span></span> 

<span data-ttu-id="c2d3f-214">`expression`: `Int32`, ,`Int64` O`Decimal`. `Double`</span><span class="sxs-lookup"><span data-stu-id="c2d3f-214">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="c2d3f-215">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-215">**Return Value**</span></span> 

<span data-ttu-id="c2d3f-216">`Int32`, ,`Int64` O`Decimal`. `Double`</span><span class="sxs-lookup"><span data-stu-id="c2d3f-216">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="c2d3f-217">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-217">**Example**</span></span> 

`SqlServer.RADIANS(360.0)`

## <a name="randseed"></a><span data-ttu-id="c2d3f-218">RAND ([SEED])</span><span class="sxs-lookup"><span data-stu-id="c2d3f-218">RAND([seed])</span></span>

<span data-ttu-id="c2d3f-219">Devuelve un valor aleatorio de 0 a 1.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-219">Returns a random value from 0 through 1.</span></span> 

<span data-ttu-id="c2d3f-220">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-220">**Arguments**</span></span> 

<span data-ttu-id="c2d3f-221">Valor de inicialización como `Int32`.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-221">The seed value as an `Int32`.</span></span> <span data-ttu-id="c2d3f-222">Si la inicialización no se especifica, el motor de base de datos de SQL Server asigna uno de forma aleatoria.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-222">If the seed is not specified, the SQL Server Database Engine assigns a seed value at random.</span></span> <span data-ttu-id="c2d3f-223">Para un valor de inicialización especificado, el resultado devuelto es siempre el mismo.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-223">For a specified seed value, the result returned is always the same.</span></span>

<span data-ttu-id="c2d3f-224">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-224">**Return Value**</span></span> 

<span data-ttu-id="c2d3f-225">Valor `Double` aleatorio de 0 a 1.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-225">A random `Double` value from 0 through 1.</span></span> 

<span data-ttu-id="c2d3f-226">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-226">**Example**</span></span> 

`SqlServer.RAND()`
  
## <a name="roundnumeric_expression-lengthfunction"></a><span data-ttu-id="c2d3f-227">ROUND (numeric_expression, longitud [, función])</span><span class="sxs-lookup"><span data-stu-id="c2d3f-227">ROUND(numeric_expression, length[,function])</span></span>

<span data-ttu-id="c2d3f-228">Devuelve una expresión numérica, redondeada a la longitud o precisión especificadas.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-228">Returns a numeric expression, rounded to the specified length or precision.</span></span> 

<span data-ttu-id="c2d3f-229">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-229">**Arguments**</span></span> 

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="c2d3f-230">`Int32`, ,`Int64` O`Decimal`. `Double`</span><span class="sxs-lookup"><span data-stu-id="c2d3f-230">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 
|`length`| <span data-ttu-id="c2d3f-231">Valor `Int32` que representa la precisión a la que se va a redondear `numeric_expression`.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-231">An `Int32` that represents the precision to which `numeric_expression` is to be rounded.</span></span> <span data-ttu-id="c2d3f-232">Si `length` es un número positivo, `numeric_expression` se redondea al número de posiciones decimales que especifica `length`.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-232">When `length` is a positive number, `numeric_expression` is rounded to the number of decimal positions specified by `length`.</span></span> <span data-ttu-id="c2d3f-233">Si `length` es un número negativo, `numeric_expression` se redondea a la izquierda del separador decimal, según se especifica en `length`.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-233">When `length` is a negative number, `numeric_expression` is rounded on the left side of the decimal point, as specified by `length`.</span></span>|
|`function` | <span data-ttu-id="c2d3f-234">Opcional.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-234">Optional.</span></span> <span data-ttu-id="c2d3f-235">`Int32` Que representa el tipo de operación que se va a realizar.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-235">An `Int32` that represents the type of operation to perform.</span></span> <span data-ttu-id="c2d3f-236">Cuando se omite la función o tiene un valor de 0 (valor predeterminado `numeric_expression` ), se redondea.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-236">When function is omitted or has a value of 0 (default), `numeric_expression` is rounded.</span></span> <span data-ttu-id="c2d3f-237">Cuando se especifica un valor distinto de 0, `numeric_expression` se trunca.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-237">When a value other than 0 is specified, `numeric_expression` is truncated.</span></span> |

<span data-ttu-id="c2d3f-238">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-238">**Return Value**</span></span> 

<span data-ttu-id="c2d3f-239">Valor de la `numeric_expression` especificada a la `power_expression` especificada.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-239">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span>

<span data-ttu-id="c2d3f-240">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-240">**Example**</span></span> 

`SqlServer.ROUND(748.58, -3)`

## <a name="signexpression"></a><span data-ttu-id="c2d3f-241">SIGN (expresión)</span><span class="sxs-lookup"><span data-stu-id="c2d3f-241">SIGN(expression)</span></span> 

<span data-ttu-id="c2d3f-242">Devuelve el signo positivo (+1), cero (0) o negativo (-1) de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-242">Returns the positive (+1), zero (0), or negative (-1) sign of the specified expression.</span></span> 

<span data-ttu-id="c2d3f-243">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-243">**Arguments**</span></span> 

<span data-ttu-id="c2d3f-244">`expression`: `Int32`, `Int64`, `Double` o `Decimal`</span><span class="sxs-lookup"><span data-stu-id="c2d3f-244">`expression`: `Int32`, `Int64`, `Double`, or `Decimal`</span></span> 

<span data-ttu-id="c2d3f-245">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-245">**Return Value**</span></span> 

<span data-ttu-id="c2d3f-246">`Int32`, ,`Int64` O`Decimal`. `Double`</span><span class="sxs-lookup"><span data-stu-id="c2d3f-246">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="c2d3f-247">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-247">**Example**</span></span> 

`SqlServer.SIGN(-10)`

## <a name="sinexpression"></a><span data-ttu-id="c2d3f-248">SIN (expresión)</span><span class="sxs-lookup"><span data-stu-id="c2d3f-248">SIN(expression)</span></span>

<span data-ttu-id="c2d3f-249">Calcula el seno trigonométrico de un ángulo especificado, en radianes, y devuelve una expresión de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-249">Calculates the trigonometric sine of the specified angle in radians, and returns a `Double` expression.</span></span> 

<span data-ttu-id="c2d3f-250">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-250">**Arguments**</span></span> 

<span data-ttu-id="c2d3f-251">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-251">`expression`: A `Double`.</span></span> 

<span data-ttu-id="c2d3f-252">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-252">**Return Value**</span></span> 

<span data-ttu-id="c2d3f-253">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-253">A `Double`.</span></span> 

<span data-ttu-id="c2d3f-254">**Ejemplo** de`SqlServer.SIN(20)`</span><span class="sxs-lookup"><span data-stu-id="c2d3f-254">**Example** `SqlServer.SIN(20)`</span></span>

## <a name="sqrtexpression"></a><span data-ttu-id="c2d3f-255">SQRT (expresión)</span><span class="sxs-lookup"><span data-stu-id="c2d3f-255">SQRT(expression)</span></span>

<span data-ttu-id="c2d3f-256">Devuelve la raíz cuadrada de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-256">Returns the square root of the specified expression.</span></span> 

<span data-ttu-id="c2d3f-257">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-257">**Arguments**</span></span> 

<span data-ttu-id="c2d3f-258">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-258">`expression`: A `Double`.</span></span> 

<span data-ttu-id="c2d3f-259">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-259">**Return Value**</span></span> 

<span data-ttu-id="c2d3f-260">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-260">A `Double`.</span></span> 

<span data-ttu-id="c2d3f-261">**Ejemplo** de`SqlServer.SQRT(3600)`</span><span class="sxs-lookup"><span data-stu-id="c2d3f-261">**Example** `SqlServer.SQRT(3600)`</span></span>

## <a name="squareexpression"></a><span data-ttu-id="c2d3f-262">SQUARE (expresión)</span><span class="sxs-lookup"><span data-stu-id="c2d3f-262">SQUARE(expression)</span></span>

<span data-ttu-id="c2d3f-263">Devuelve la raíz cuadrada de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-263">Returns the square of the specified expression.</span></span> 

<span data-ttu-id="c2d3f-264">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-264">**Arguments**</span></span> 

<span data-ttu-id="c2d3f-265">`expression`: OBJETO `Double`.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-265">`expression`: A `Double`.</span></span> 

<span data-ttu-id="c2d3f-266">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-266">**Return Value**</span></span> 

<span data-ttu-id="c2d3f-267">Objeto `Double`.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-267">A `Double`.</span></span> 

<span data-ttu-id="c2d3f-268">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-268">**Example**</span></span> 

`SqlServer.SQUARE(25)`

## <a name="tanexpression"></a><span data-ttu-id="c2d3f-269">TAN (expresión)</span><span class="sxs-lookup"><span data-stu-id="c2d3f-269">TAN(expression)</span></span>

<span data-ttu-id="c2d3f-270">Calcula la tangente de una expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="c2d3f-270">Calculates the tangent of a specified expression.</span></span>

<span data-ttu-id="c2d3f-271">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-271">**Arguments**</span></span> 

<span data-ttu-id="c2d3f-272">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="c2d3f-272">`expression`: `Double`</span></span> 

<span data-ttu-id="c2d3f-273">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-273">**Return Value**</span></span> 

`Double` 

<span data-ttu-id="c2d3f-274">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="c2d3f-274">**Example**</span></span> 

`SqlServer.TAN(45.0)`
  
## <a name="see-also"></a><span data-ttu-id="c2d3f-275">Vea también</span><span class="sxs-lookup"><span data-stu-id="c2d3f-275">See also</span></span>

- [<span data-ttu-id="c2d3f-276">Funciones matemáticas (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c2d3f-276">Mathematical Functions (Transact-SQL)</span></span>](/sql/t-sql/functions/mathematical-functions-transact-sql)
- [<span data-ttu-id="c2d3f-277">SqlClient para las funciones de Entity Framework</span><span class="sxs-lookup"><span data-stu-id="c2d3f-277">SqlClient for Entity Framework Functions</span></span>](sqlclient-for-ef-functions.md)
