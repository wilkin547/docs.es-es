---
title: Funciones canónicas matemáticas
ms.date: 03/30/2017
ms.assetid: 6f6cddc6-b561-4ebe-84b6-841ef5b4113b
ms.openlocfilehash: 0fc9f4942c3f76f139ab7e4400005f0bfe80204e
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47111664"
---
# <a name="math-canonical-functions"></a><span data-ttu-id="d91cf-102">Funciones canónicas matemáticas</span><span class="sxs-lookup"><span data-stu-id="d91cf-102">Math Canonical Functions</span></span>

<span data-ttu-id="d91cf-103">Entity SQL incluye las siguientes funciones canónicas matemáticas:</span><span class="sxs-lookup"><span data-stu-id="d91cf-103">Entity SQL includes the following math canonical functions:</span></span>
  
## <a name="absvalue"></a><span data-ttu-id="d91cf-104">Abs(valor)</span><span class="sxs-lookup"><span data-stu-id="d91cf-104">Abs(value)</span></span>

<span data-ttu-id="d91cf-105">Devuelve el valor absoluto de `value`.</span><span class="sxs-lookup"><span data-stu-id="d91cf-105">Returns the absolute value of `value`.</span></span>

<span data-ttu-id="d91cf-106">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="d91cf-106">**Arguments**</span></span>

<span data-ttu-id="d91cf-107">Un `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, y `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="d91cf-107">An `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="d91cf-108">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="d91cf-108">**Return Value**</span></span>

<span data-ttu-id="d91cf-109">Tipo de `value`.</span><span class="sxs-lookup"><span data-stu-id="d91cf-109">The type of `value`.</span></span>

<span data-ttu-id="d91cf-110">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="d91cf-110">**Example**</span></span>

`Abs(-2)`

## <a name="ceilingvalue"></a><span data-ttu-id="d91cf-111">Ceiling(valor)</span><span class="sxs-lookup"><span data-stu-id="d91cf-111">Ceiling(value)</span></span>

<span data-ttu-id="d91cf-112">Devuelve el menor entero que es mayor o igual que `value`.</span><span class="sxs-lookup"><span data-stu-id="d91cf-112">Returns the smallest integer that is not less than `value`.</span></span>

<span data-ttu-id="d91cf-113">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="d91cf-113">**Arguments**</span></span>

<span data-ttu-id="d91cf-114">Un `Single`, `Double`, y `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="d91cf-114">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="d91cf-115">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="d91cf-115">**Return Value**</span></span>

<span data-ttu-id="d91cf-116">Tipo de `value`.</span><span class="sxs-lookup"><span data-stu-id="d91cf-116">The type of `value`.</span></span>

<span data-ttu-id="d91cf-117">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="d91cf-117">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_ceiling)]
[!code-sql[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_ceiling)]

## <a name="floorvalue"></a><span data-ttu-id="d91cf-118">Floor(valor)</span><span class="sxs-lookup"><span data-stu-id="d91cf-118">Floor(value)</span></span>

<span data-ttu-id="d91cf-119">Devuelve el mayor entero que es menor o igual que `value`.</span><span class="sxs-lookup"><span data-stu-id="d91cf-119">Returns the largest integer that is not greater than `value`.</span></span>

<span data-ttu-id="d91cf-120">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="d91cf-120">**Arguments**</span></span>

<span data-ttu-id="d91cf-121">Un `Single`, `Double`, y `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="d91cf-121">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="d91cf-122">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="d91cf-122">**Return Value**</span></span>

<span data-ttu-id="d91cf-123">Tipo de `value`.</span><span class="sxs-lookup"><span data-stu-id="d91cf-123">The type of `value`.</span></span>

<span data-ttu-id="d91cf-124">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="d91cf-124">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_floor)]
[!code-sql[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_floor)]

## <a name="powervalue-exponent"></a><span data-ttu-id="d91cf-125">Power(valor, exponente)</span><span class="sxs-lookup"><span data-stu-id="d91cf-125">Power(value, exponent)</span></span>

<span data-ttu-id="d91cf-126">Devuelve el resultado del `value` especificado al `exponent` especificado.</span><span class="sxs-lookup"><span data-stu-id="d91cf-126">Returns the result of the specified `value` to the specified `exponent`.</span></span>

<span data-ttu-id="d91cf-127">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="d91cf-127">**Arguments**</span></span>

|  |  |
|--|--|
|`value` | <span data-ttu-id="d91cf-128">Un `Int32, Int64, Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="d91cf-128">An `Int32, Int64, Double`, or `Decimal`.</span></span> |
|`exponent` | <span data-ttu-id="d91cf-129">Un `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="d91cf-129">An `Int64`, `Double`, or `Decimal`.</span></span> |

<span data-ttu-id="d91cf-130">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="d91cf-130">**Return Value**</span></span>

<span data-ttu-id="d91cf-131">Tipo de `value`.</span><span class="sxs-lookup"><span data-stu-id="d91cf-131">The type of `value`.</span></span>

<span data-ttu-id="d91cf-132">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="d91cf-132">**Example**</span></span>

`Power(748.58,2)`

## <a name="roundvalue"></a><span data-ttu-id="d91cf-133">Round(valor)</span><span class="sxs-lookup"><span data-stu-id="d91cf-133">Round(value)</span></span>

<span data-ttu-id="d91cf-134">Devuelve la parte entera de `value`, redondeada al entero más próximo.</span><span class="sxs-lookup"><span data-stu-id="d91cf-134">Returns the integer portion of `value`, rounded to the nearest integer.</span></span>

<span data-ttu-id="d91cf-135">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="d91cf-135">**Arguments**</span></span>

<span data-ttu-id="d91cf-136">Un `Single`, `Double`, y `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="d91cf-136">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="d91cf-137">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="d91cf-137">**Return Value**</span></span>

<span data-ttu-id="d91cf-138">Tipo de `value`.</span><span class="sxs-lookup"><span data-stu-id="d91cf-138">The type of `value`.</span></span>

<span data-ttu-id="d91cf-139">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="d91cf-139">**Example**</span></span>

`Round(748.58)`

## <a name="roundvalue-digits"></a><span data-ttu-id="d91cf-140">Round(valor, dígitos)</span><span class="sxs-lookup"><span data-stu-id="d91cf-140">Round(value, digits)</span></span>

<span data-ttu-id="d91cf-141">Devuelve `value`, redondeado a los `digits` especificados más próximos.</span><span class="sxs-lookup"><span data-stu-id="d91cf-141">Returns the `value`, rounded to the nearest specified `digits`.</span></span>

<span data-ttu-id="d91cf-142">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="d91cf-142">**Arguments**</span></span>

|  |  |
|--|--|
|`value`|<span data-ttu-id="d91cf-143">`Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="d91cf-143">`Double` or `Decimal`.</span></span>|
|`digits`|<span data-ttu-id="d91cf-144">`Int16` o `Int32`.</span><span class="sxs-lookup"><span data-stu-id="d91cf-144">`Int16` or `Int32`.</span></span>|

<span data-ttu-id="d91cf-145">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="d91cf-145">**Return Value**</span></span>

<span data-ttu-id="d91cf-146">Tipo de `value`.</span><span class="sxs-lookup"><span data-stu-id="d91cf-146">The type of `value`.</span></span>

<span data-ttu-id="d91cf-147">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="d91cf-147">**Example**</span></span>

`Round(748.58,1)`

## <a name="truncatevalue-digits"></a><span data-ttu-id="d91cf-148">Truncate(valor, dígitos)</span><span class="sxs-lookup"><span data-stu-id="d91cf-148">Truncate(value, digits)</span></span>

<span data-ttu-id="d91cf-149">Devuelve `value`, truncado a los `digits` especificados más próximos.</span><span class="sxs-lookup"><span data-stu-id="d91cf-149">Returns the `value`, truncated to the nearest specified `digits`.</span></span>

<span data-ttu-id="d91cf-150">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="d91cf-150">**Arguments**</span></span>

|  |  |
|--|--|
|`value`|<span data-ttu-id="d91cf-151">`Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="d91cf-151">`Double` or `Decimal`.</span></span>|
|`digits`|<span data-ttu-id="d91cf-152">`Int16` o `Int32`.</span><span class="sxs-lookup"><span data-stu-id="d91cf-152">`Int16` or `Int32`.</span></span>|

<span data-ttu-id="d91cf-153">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="d91cf-153">**Return Value**</span></span>

<span data-ttu-id="d91cf-154">Tipo de `value`.</span><span class="sxs-lookup"><span data-stu-id="d91cf-154">The type of `value`.</span></span>

<span data-ttu-id="d91cf-155">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="d91cf-155">**Example**</span></span>

`Truncate(748.58,1)`  
  
 <span data-ttu-id="d91cf-156">Estas funciones devolverán `null` si se proporciona la entrada `null`.</span><span class="sxs-lookup"><span data-stu-id="d91cf-156">These functions will return `null` if given `null` input.</span></span>  
  
 <span data-ttu-id="d91cf-157">La funcionalidad equivalente está disponible en el proveedor administrado de Microsoft SQL Client.</span><span class="sxs-lookup"><span data-stu-id="d91cf-157">Equivalent functionality is available in the Microsoft SQL Client Managed Provider.</span></span> <span data-ttu-id="d91cf-158">Para obtener más información, consulte [SqlClient para las funciones de Entity Framework](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span><span class="sxs-lookup"><span data-stu-id="d91cf-158">For more information, see [SqlClient for Entity Framework Functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d91cf-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="d91cf-159">See Also</span></span>  
 [<span data-ttu-id="d91cf-160">Funciones canónicas</span><span class="sxs-lookup"><span data-stu-id="d91cf-160">Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
