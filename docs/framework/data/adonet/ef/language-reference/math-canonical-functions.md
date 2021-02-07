---
description: 'Más información sobre: funciones canónicas matemáticas'
title: Funciones canónicas matemáticas
ms.date: 03/30/2017
ms.assetid: 6f6cddc6-b561-4ebe-84b6-841ef5b4113b
ms.openlocfilehash: 55072099f5766d48ea3067a2e9eaa187a8b3f111
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739370"
---
# <a name="math-canonical-functions"></a><span data-ttu-id="809ee-103">Funciones canónicas matemáticas</span><span class="sxs-lookup"><span data-stu-id="809ee-103">Math Canonical Functions</span></span>

<span data-ttu-id="809ee-104">Entity SQL incluye las siguientes funciones canónicas matemáticas:</span><span class="sxs-lookup"><span data-stu-id="809ee-104">Entity SQL includes the following math canonical functions:</span></span>
  
## <a name="absvalue"></a><span data-ttu-id="809ee-105">Abs(valor)</span><span class="sxs-lookup"><span data-stu-id="809ee-105">Abs(value)</span></span>

<span data-ttu-id="809ee-106">Devuelve el valor absoluto de `value`.</span><span class="sxs-lookup"><span data-stu-id="809ee-106">Returns the absolute value of `value`.</span></span>

<span data-ttu-id="809ee-107">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="809ee-107">**Arguments**</span></span>

<span data-ttu-id="809ee-108">`Int16`, `Int32` , `Int64` , `Byte` , `Single` , `Double` Y `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="809ee-108">An `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="809ee-109">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="809ee-109">**Return Value**</span></span>

<span data-ttu-id="809ee-110">Tipo de `value`.</span><span class="sxs-lookup"><span data-stu-id="809ee-110">The type of `value`.</span></span>

<span data-ttu-id="809ee-111">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="809ee-111">**Example**</span></span>

`Abs(-2)`

## <a name="ceilingvalue"></a><span data-ttu-id="809ee-112">Ceiling(valor)</span><span class="sxs-lookup"><span data-stu-id="809ee-112">Ceiling(value)</span></span>

<span data-ttu-id="809ee-113">Devuelve el menor entero que es mayor o igual que `value`.</span><span class="sxs-lookup"><span data-stu-id="809ee-113">Returns the smallest integer that is not less than `value`.</span></span>

<span data-ttu-id="809ee-114">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="809ee-114">**Arguments**</span></span>

<span data-ttu-id="809ee-115">`Single`, `Double` Y `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="809ee-115">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="809ee-116">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="809ee-116">**Return Value**</span></span>

<span data-ttu-id="809ee-117">Tipo de `value`.</span><span class="sxs-lookup"><span data-stu-id="809ee-117">The type of `value`.</span></span>

<span data-ttu-id="809ee-118">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="809ee-118">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_ceiling)]
[!code-sql[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_ceiling)]

## <a name="floorvalue"></a><span data-ttu-id="809ee-119">Floor(valor)</span><span class="sxs-lookup"><span data-stu-id="809ee-119">Floor(value)</span></span>

<span data-ttu-id="809ee-120">Devuelve el mayor entero que es menor o igual que `value`.</span><span class="sxs-lookup"><span data-stu-id="809ee-120">Returns the largest integer that is not greater than `value`.</span></span>

<span data-ttu-id="809ee-121">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="809ee-121">**Arguments**</span></span>

<span data-ttu-id="809ee-122">`Single`, `Double` Y `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="809ee-122">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="809ee-123">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="809ee-123">**Return Value**</span></span>

<span data-ttu-id="809ee-124">Tipo de `value`.</span><span class="sxs-lookup"><span data-stu-id="809ee-124">The type of `value`.</span></span>

<span data-ttu-id="809ee-125">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="809ee-125">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_floor)]
[!code-sql[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_floor)]

## <a name="powervalue-exponent"></a><span data-ttu-id="809ee-126">Power(valor, exponente)</span><span class="sxs-lookup"><span data-stu-id="809ee-126">Power(value, exponent)</span></span>

<span data-ttu-id="809ee-127">Devuelve el resultado del `value` especificado al `exponent` especificado.</span><span class="sxs-lookup"><span data-stu-id="809ee-127">Returns the result of the specified `value` to the specified `exponent`.</span></span>

<span data-ttu-id="809ee-128">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="809ee-128">**Arguments**</span></span>

|  |  |
|--|--|
|`value` | <span data-ttu-id="809ee-129">`Int32, Int64, Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="809ee-129">An `Int32, Int64, Double`, or `Decimal`.</span></span> |
|`exponent` | <span data-ttu-id="809ee-130">`Int64`, `Double` O `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="809ee-130">An `Int64`, `Double`, or `Decimal`.</span></span> |

<span data-ttu-id="809ee-131">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="809ee-131">**Return Value**</span></span>

<span data-ttu-id="809ee-132">Tipo de `value`.</span><span class="sxs-lookup"><span data-stu-id="809ee-132">The type of `value`.</span></span>

<span data-ttu-id="809ee-133">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="809ee-133">**Example**</span></span>

`Power(748.58,2)`

## <a name="roundvalue"></a><span data-ttu-id="809ee-134">Round(valor)</span><span class="sxs-lookup"><span data-stu-id="809ee-134">Round(value)</span></span>

<span data-ttu-id="809ee-135">Devuelve la parte entera de `value`, redondeada al entero más próximo.</span><span class="sxs-lookup"><span data-stu-id="809ee-135">Returns the integer portion of `value`, rounded to the nearest integer.</span></span>

<span data-ttu-id="809ee-136">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="809ee-136">**Arguments**</span></span>

<span data-ttu-id="809ee-137">`Single`, `Double` Y `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="809ee-137">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="809ee-138">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="809ee-138">**Return Value**</span></span>

<span data-ttu-id="809ee-139">Tipo de `value`.</span><span class="sxs-lookup"><span data-stu-id="809ee-139">The type of `value`.</span></span>

<span data-ttu-id="809ee-140">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="809ee-140">**Example**</span></span>

`Round(748.58)`

## <a name="roundvalue-digits"></a><span data-ttu-id="809ee-141">Round(valor, dígitos)</span><span class="sxs-lookup"><span data-stu-id="809ee-141">Round(value, digits)</span></span>

<span data-ttu-id="809ee-142">Devuelve `value`, redondeado a los `digits` especificados más próximos.</span><span class="sxs-lookup"><span data-stu-id="809ee-142">Returns the `value`, rounded to the nearest specified `digits`.</span></span>

<span data-ttu-id="809ee-143">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="809ee-143">**Arguments**</span></span>

|  |  |
|--|--|
|`value`|<span data-ttu-id="809ee-144">`Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="809ee-144">`Double` or `Decimal`.</span></span>|
|`digits`|<span data-ttu-id="809ee-145">`Int16` o `Int32`.</span><span class="sxs-lookup"><span data-stu-id="809ee-145">`Int16` or `Int32`.</span></span>|

<span data-ttu-id="809ee-146">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="809ee-146">**Return Value**</span></span>

<span data-ttu-id="809ee-147">Tipo de `value`.</span><span class="sxs-lookup"><span data-stu-id="809ee-147">The type of `value`.</span></span>

<span data-ttu-id="809ee-148">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="809ee-148">**Example**</span></span>

`Round(748.58,1)`

## <a name="truncatevalue-digits"></a><span data-ttu-id="809ee-149">Truncate(valor, dígitos)</span><span class="sxs-lookup"><span data-stu-id="809ee-149">Truncate(value, digits)</span></span>

<span data-ttu-id="809ee-150">Devuelve `value`, truncado a los `digits` especificados más próximos.</span><span class="sxs-lookup"><span data-stu-id="809ee-150">Returns the `value`, truncated to the nearest specified `digits`.</span></span>

<span data-ttu-id="809ee-151">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="809ee-151">**Arguments**</span></span>

|  |  |
|--|--|
|`value`|<span data-ttu-id="809ee-152">`Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="809ee-152">`Double` or `Decimal`.</span></span>|
|`digits`|<span data-ttu-id="809ee-153">`Int16` o `Int32`.</span><span class="sxs-lookup"><span data-stu-id="809ee-153">`Int16` or `Int32`.</span></span>|

<span data-ttu-id="809ee-154">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="809ee-154">**Return Value**</span></span>

<span data-ttu-id="809ee-155">Tipo de `value`.</span><span class="sxs-lookup"><span data-stu-id="809ee-155">The type of `value`.</span></span>

<span data-ttu-id="809ee-156">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="809ee-156">**Example**</span></span>

`Truncate(748.58,1)`  
  
 <span data-ttu-id="809ee-157">Estas funciones devolverán `null` si se proporciona la entrada `null`.</span><span class="sxs-lookup"><span data-stu-id="809ee-157">These functions will return `null` if given `null` input.</span></span>  
  
 <span data-ttu-id="809ee-158">La funcionalidad equivalente está disponible en el proveedor administrado de Microsoft SQL Client.</span><span class="sxs-lookup"><span data-stu-id="809ee-158">Equivalent functionality is available in the Microsoft SQL Client Managed Provider.</span></span> <span data-ttu-id="809ee-159">Para obtener más información, vea [SqlClient para funciones de Entity Framework](../sqlclient-for-ef-functions.md).</span><span class="sxs-lookup"><span data-stu-id="809ee-159">For more information, see [SqlClient for Entity Framework Functions](../sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="809ee-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="809ee-160">See also</span></span>

- [<span data-ttu-id="809ee-161">Funciones canónicas</span><span class="sxs-lookup"><span data-stu-id="809ee-161">Canonical Functions</span></span>](canonical-functions.md)
