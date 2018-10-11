---
title: Funciones canónicas matemáticas
ms.date: 03/30/2017
ms.assetid: 6f6cddc6-b561-4ebe-84b6-841ef5b4113b
ms.openlocfilehash: 0fc9f4942c3f76f139ab7e4400005f0bfe80204e
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/11/2018
ms.locfileid: "49087614"
---
# <a name="math-canonical-functions"></a><span data-ttu-id="cd433-102">Funciones canónicas matemáticas</span><span class="sxs-lookup"><span data-stu-id="cd433-102">Math Canonical Functions</span></span>

<span data-ttu-id="cd433-103">Entity SQL incluye las siguientes funciones canónicas matemáticas:</span><span class="sxs-lookup"><span data-stu-id="cd433-103">Entity SQL includes the following math canonical functions:</span></span>
  
## <a name="absvalue"></a><span data-ttu-id="cd433-104">Abs(valor)</span><span class="sxs-lookup"><span data-stu-id="cd433-104">Abs(value)</span></span>

<span data-ttu-id="cd433-105">Devuelve el valor absoluto de `value`.</span><span class="sxs-lookup"><span data-stu-id="cd433-105">Returns the absolute value of `value`.</span></span>

<span data-ttu-id="cd433-106">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="cd433-106">**Arguments**</span></span>

<span data-ttu-id="cd433-107">Un `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, y `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="cd433-107">An `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="cd433-108">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="cd433-108">**Return Value**</span></span>

<span data-ttu-id="cd433-109">Tipo de `value`.</span><span class="sxs-lookup"><span data-stu-id="cd433-109">The type of `value`.</span></span>

<span data-ttu-id="cd433-110">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="cd433-110">**Example**</span></span>

`Abs(-2)`

## <a name="ceilingvalue"></a><span data-ttu-id="cd433-111">Ceiling(valor)</span><span class="sxs-lookup"><span data-stu-id="cd433-111">Ceiling(value)</span></span>

<span data-ttu-id="cd433-112">Devuelve el menor entero que es mayor o igual que `value`.</span><span class="sxs-lookup"><span data-stu-id="cd433-112">Returns the smallest integer that is not less than `value`.</span></span>

<span data-ttu-id="cd433-113">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="cd433-113">**Arguments**</span></span>

<span data-ttu-id="cd433-114">Un `Single`, `Double`, y `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="cd433-114">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="cd433-115">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="cd433-115">**Return Value**</span></span>

<span data-ttu-id="cd433-116">Tipo de `value`.</span><span class="sxs-lookup"><span data-stu-id="cd433-116">The type of `value`.</span></span>

<span data-ttu-id="cd433-117">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="cd433-117">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_ceiling)]
[!code-sql[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_ceiling)]

## <a name="floorvalue"></a><span data-ttu-id="cd433-118">Floor(valor)</span><span class="sxs-lookup"><span data-stu-id="cd433-118">Floor(value)</span></span>

<span data-ttu-id="cd433-119">Devuelve el mayor entero que es menor o igual que `value`.</span><span class="sxs-lookup"><span data-stu-id="cd433-119">Returns the largest integer that is not greater than `value`.</span></span>

<span data-ttu-id="cd433-120">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="cd433-120">**Arguments**</span></span>

<span data-ttu-id="cd433-121">Un `Single`, `Double`, y `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="cd433-121">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="cd433-122">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="cd433-122">**Return Value**</span></span>

<span data-ttu-id="cd433-123">Tipo de `value`.</span><span class="sxs-lookup"><span data-stu-id="cd433-123">The type of `value`.</span></span>

<span data-ttu-id="cd433-124">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="cd433-124">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_floor)]
[!code-sql[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_floor)]

## <a name="powervalue-exponent"></a><span data-ttu-id="cd433-125">Power(valor, exponente)</span><span class="sxs-lookup"><span data-stu-id="cd433-125">Power(value, exponent)</span></span>

<span data-ttu-id="cd433-126">Devuelve el resultado del `value` especificado al `exponent` especificado.</span><span class="sxs-lookup"><span data-stu-id="cd433-126">Returns the result of the specified `value` to the specified `exponent`.</span></span>

<span data-ttu-id="cd433-127">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="cd433-127">**Arguments**</span></span>

|  |  |
|--|--|
|`value` | <span data-ttu-id="cd433-128">Un `Int32, Int64, Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="cd433-128">An `Int32, Int64, Double`, or `Decimal`.</span></span> |
|`exponent` | <span data-ttu-id="cd433-129">Un `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="cd433-129">An `Int64`, `Double`, or `Decimal`.</span></span> |

<span data-ttu-id="cd433-130">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="cd433-130">**Return Value**</span></span>

<span data-ttu-id="cd433-131">Tipo de `value`.</span><span class="sxs-lookup"><span data-stu-id="cd433-131">The type of `value`.</span></span>

<span data-ttu-id="cd433-132">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="cd433-132">**Example**</span></span>

`Power(748.58,2)`

## <a name="roundvalue"></a><span data-ttu-id="cd433-133">Round(valor)</span><span class="sxs-lookup"><span data-stu-id="cd433-133">Round(value)</span></span>

<span data-ttu-id="cd433-134">Devuelve la parte entera de `value`, redondeada al entero más próximo.</span><span class="sxs-lookup"><span data-stu-id="cd433-134">Returns the integer portion of `value`, rounded to the nearest integer.</span></span>

<span data-ttu-id="cd433-135">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="cd433-135">**Arguments**</span></span>

<span data-ttu-id="cd433-136">Un `Single`, `Double`, y `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="cd433-136">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="cd433-137">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="cd433-137">**Return Value**</span></span>

<span data-ttu-id="cd433-138">Tipo de `value`.</span><span class="sxs-lookup"><span data-stu-id="cd433-138">The type of `value`.</span></span>

<span data-ttu-id="cd433-139">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="cd433-139">**Example**</span></span>

`Round(748.58)`

## <a name="roundvalue-digits"></a><span data-ttu-id="cd433-140">Round(valor, dígitos)</span><span class="sxs-lookup"><span data-stu-id="cd433-140">Round(value, digits)</span></span>

<span data-ttu-id="cd433-141">Devuelve `value`, redondeado a los `digits` especificados más próximos.</span><span class="sxs-lookup"><span data-stu-id="cd433-141">Returns the `value`, rounded to the nearest specified `digits`.</span></span>

<span data-ttu-id="cd433-142">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="cd433-142">**Arguments**</span></span>

|  |  |
|--|--|
|`value`|<span data-ttu-id="cd433-143">`Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="cd433-143">`Double` or `Decimal`.</span></span>|
|`digits`|<span data-ttu-id="cd433-144">`Int16` o `Int32`.</span><span class="sxs-lookup"><span data-stu-id="cd433-144">`Int16` or `Int32`.</span></span>|

<span data-ttu-id="cd433-145">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="cd433-145">**Return Value**</span></span>

<span data-ttu-id="cd433-146">Tipo de `value`.</span><span class="sxs-lookup"><span data-stu-id="cd433-146">The type of `value`.</span></span>

<span data-ttu-id="cd433-147">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="cd433-147">**Example**</span></span>

`Round(748.58,1)`

## <a name="truncatevalue-digits"></a><span data-ttu-id="cd433-148">Truncate(valor, dígitos)</span><span class="sxs-lookup"><span data-stu-id="cd433-148">Truncate(value, digits)</span></span>

<span data-ttu-id="cd433-149">Devuelve `value`, truncado a los `digits` especificados más próximos.</span><span class="sxs-lookup"><span data-stu-id="cd433-149">Returns the `value`, truncated to the nearest specified `digits`.</span></span>

<span data-ttu-id="cd433-150">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="cd433-150">**Arguments**</span></span>

|  |  |
|--|--|
|`value`|<span data-ttu-id="cd433-151">`Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="cd433-151">`Double` or `Decimal`.</span></span>|
|`digits`|<span data-ttu-id="cd433-152">`Int16` o `Int32`.</span><span class="sxs-lookup"><span data-stu-id="cd433-152">`Int16` or `Int32`.</span></span>|

<span data-ttu-id="cd433-153">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="cd433-153">**Return Value**</span></span>

<span data-ttu-id="cd433-154">Tipo de `value`.</span><span class="sxs-lookup"><span data-stu-id="cd433-154">The type of `value`.</span></span>

<span data-ttu-id="cd433-155">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="cd433-155">**Example**</span></span>

`Truncate(748.58,1)`  
  
 <span data-ttu-id="cd433-156">Estas funciones devolverán `null` si se proporciona la entrada `null`.</span><span class="sxs-lookup"><span data-stu-id="cd433-156">These functions will return `null` if given `null` input.</span></span>  
  
 <span data-ttu-id="cd433-157">La funcionalidad equivalente está disponible en el proveedor administrado de Microsoft SQL Client.</span><span class="sxs-lookup"><span data-stu-id="cd433-157">Equivalent functionality is available in the Microsoft SQL Client Managed Provider.</span></span> <span data-ttu-id="cd433-158">Para obtener más información, consulte [SqlClient para las funciones de Entity Framework](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span><span class="sxs-lookup"><span data-stu-id="cd433-158">For more information, see [SqlClient for Entity Framework Functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd433-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="cd433-159">See Also</span></span>  
 [<span data-ttu-id="cd433-160">Funciones canónicas</span><span class="sxs-lookup"><span data-stu-id="cd433-160">Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
