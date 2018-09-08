---
title: Funciones canónicas matemáticas
ms.date: 03/30/2017
ms.assetid: 6f6cddc6-b561-4ebe-84b6-841ef5b4113b
ms.openlocfilehash: 0fc9f4942c3f76f139ab7e4400005f0bfe80204e
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44204687"
---
# <a name="math-canonical-functions"></a><span data-ttu-id="63012-102">Funciones canónicas matemáticas</span><span class="sxs-lookup"><span data-stu-id="63012-102">Math Canonical Functions</span></span>

<span data-ttu-id="63012-103">Entity SQL incluye las siguientes funciones canónicas matemáticas:</span><span class="sxs-lookup"><span data-stu-id="63012-103">Entity SQL includes the following math canonical functions:</span></span>
  
## <a name="absvalue"></a><span data-ttu-id="63012-104">Abs(valor)</span><span class="sxs-lookup"><span data-stu-id="63012-104">Abs(value)</span></span>

<span data-ttu-id="63012-105">Devuelve el valor absoluto de `value`.</span><span class="sxs-lookup"><span data-stu-id="63012-105">Returns the absolute value of `value`.</span></span>

<span data-ttu-id="63012-106">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="63012-106">**Arguments**</span></span>

<span data-ttu-id="63012-107">Un `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, y `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="63012-107">An `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="63012-108">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="63012-108">**Return Value**</span></span>

<span data-ttu-id="63012-109">Tipo de `value`.</span><span class="sxs-lookup"><span data-stu-id="63012-109">The type of `value`.</span></span>

<span data-ttu-id="63012-110">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="63012-110">**Example**</span></span>

`Abs(-2)`

## <a name="ceilingvalue"></a><span data-ttu-id="63012-111">Ceiling(valor)</span><span class="sxs-lookup"><span data-stu-id="63012-111">Ceiling(value)</span></span>

<span data-ttu-id="63012-112">Devuelve el menor entero que es mayor o igual que `value`.</span><span class="sxs-lookup"><span data-stu-id="63012-112">Returns the smallest integer that is not less than `value`.</span></span>

<span data-ttu-id="63012-113">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="63012-113">**Arguments**</span></span>

<span data-ttu-id="63012-114">Un `Single`, `Double`, y `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="63012-114">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="63012-115">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="63012-115">**Return Value**</span></span>

<span data-ttu-id="63012-116">Tipo de `value`.</span><span class="sxs-lookup"><span data-stu-id="63012-116">The type of `value`.</span></span>

<span data-ttu-id="63012-117">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="63012-117">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_ceiling)]
[!code-sql[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_ceiling)]

## <a name="floorvalue"></a><span data-ttu-id="63012-118">Floor(valor)</span><span class="sxs-lookup"><span data-stu-id="63012-118">Floor(value)</span></span>

<span data-ttu-id="63012-119">Devuelve el mayor entero que es menor o igual que `value`.</span><span class="sxs-lookup"><span data-stu-id="63012-119">Returns the largest integer that is not greater than `value`.</span></span>

<span data-ttu-id="63012-120">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="63012-120">**Arguments**</span></span>

<span data-ttu-id="63012-121">Un `Single`, `Double`, y `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="63012-121">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="63012-122">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="63012-122">**Return Value**</span></span>

<span data-ttu-id="63012-123">Tipo de `value`.</span><span class="sxs-lookup"><span data-stu-id="63012-123">The type of `value`.</span></span>

<span data-ttu-id="63012-124">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="63012-124">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_floor)]
[!code-sql[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_floor)]

## <a name="powervalue-exponent"></a><span data-ttu-id="63012-125">Power(valor, exponente)</span><span class="sxs-lookup"><span data-stu-id="63012-125">Power(value, exponent)</span></span>

<span data-ttu-id="63012-126">Devuelve el resultado del `value` especificado al `exponent` especificado.</span><span class="sxs-lookup"><span data-stu-id="63012-126">Returns the result of the specified `value` to the specified `exponent`.</span></span>

<span data-ttu-id="63012-127">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="63012-127">**Arguments**</span></span>

|  |  |
|--|--|
|`value` | <span data-ttu-id="63012-128">Un `Int32, Int64, Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="63012-128">An `Int32, Int64, Double`, or `Decimal`.</span></span> |
|`exponent` | <span data-ttu-id="63012-129">Un `Int64`, `Double`, o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="63012-129">An `Int64`, `Double`, or `Decimal`.</span></span> |

<span data-ttu-id="63012-130">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="63012-130">**Return Value**</span></span>

<span data-ttu-id="63012-131">Tipo de `value`.</span><span class="sxs-lookup"><span data-stu-id="63012-131">The type of `value`.</span></span>

<span data-ttu-id="63012-132">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="63012-132">**Example**</span></span>

`Power(748.58,2)`

## <a name="roundvalue"></a><span data-ttu-id="63012-133">Round(valor)</span><span class="sxs-lookup"><span data-stu-id="63012-133">Round(value)</span></span>

<span data-ttu-id="63012-134">Devuelve la parte entera de `value`, redondeada al entero más próximo.</span><span class="sxs-lookup"><span data-stu-id="63012-134">Returns the integer portion of `value`, rounded to the nearest integer.</span></span>

<span data-ttu-id="63012-135">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="63012-135">**Arguments**</span></span>

<span data-ttu-id="63012-136">Un `Single`, `Double`, y `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="63012-136">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="63012-137">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="63012-137">**Return Value**</span></span>

<span data-ttu-id="63012-138">Tipo de `value`.</span><span class="sxs-lookup"><span data-stu-id="63012-138">The type of `value`.</span></span>

<span data-ttu-id="63012-139">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="63012-139">**Example**</span></span>

`Round(748.58)`

## <a name="roundvalue-digits"></a><span data-ttu-id="63012-140">Round(valor, dígitos)</span><span class="sxs-lookup"><span data-stu-id="63012-140">Round(value, digits)</span></span>

<span data-ttu-id="63012-141">Devuelve `value`, redondeado a los `digits` especificados más próximos.</span><span class="sxs-lookup"><span data-stu-id="63012-141">Returns the `value`, rounded to the nearest specified `digits`.</span></span>

<span data-ttu-id="63012-142">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="63012-142">**Arguments**</span></span>

|  |  |
|--|--|
|`value`|<span data-ttu-id="63012-143">`Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="63012-143">`Double` or `Decimal`.</span></span>|
|`digits`|<span data-ttu-id="63012-144">`Int16` o `Int32`.</span><span class="sxs-lookup"><span data-stu-id="63012-144">`Int16` or `Int32`.</span></span>|

<span data-ttu-id="63012-145">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="63012-145">**Return Value**</span></span>

<span data-ttu-id="63012-146">Tipo de `value`.</span><span class="sxs-lookup"><span data-stu-id="63012-146">The type of `value`.</span></span>

<span data-ttu-id="63012-147">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="63012-147">**Example**</span></span>

`Round(748.58,1)`

## <a name="truncatevalue-digits"></a><span data-ttu-id="63012-148">Truncate(valor, dígitos)</span><span class="sxs-lookup"><span data-stu-id="63012-148">Truncate(value, digits)</span></span>

<span data-ttu-id="63012-149">Devuelve `value`, truncado a los `digits` especificados más próximos.</span><span class="sxs-lookup"><span data-stu-id="63012-149">Returns the `value`, truncated to the nearest specified `digits`.</span></span>

<span data-ttu-id="63012-150">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="63012-150">**Arguments**</span></span>

|  |  |
|--|--|
|`value`|<span data-ttu-id="63012-151">`Double` o `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="63012-151">`Double` or `Decimal`.</span></span>|
|`digits`|<span data-ttu-id="63012-152">`Int16` o `Int32`.</span><span class="sxs-lookup"><span data-stu-id="63012-152">`Int16` or `Int32`.</span></span>|

<span data-ttu-id="63012-153">**Valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="63012-153">**Return Value**</span></span>

<span data-ttu-id="63012-154">Tipo de `value`.</span><span class="sxs-lookup"><span data-stu-id="63012-154">The type of `value`.</span></span>

<span data-ttu-id="63012-155">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="63012-155">**Example**</span></span>

`Truncate(748.58,1)`  
  
 <span data-ttu-id="63012-156">Estas funciones devolverán `null` si se proporciona la entrada `null`.</span><span class="sxs-lookup"><span data-stu-id="63012-156">These functions will return `null` if given `null` input.</span></span>  
  
 <span data-ttu-id="63012-157">La funcionalidad equivalente está disponible en el proveedor administrado de Microsoft SQL Client.</span><span class="sxs-lookup"><span data-stu-id="63012-157">Equivalent functionality is available in the Microsoft SQL Client Managed Provider.</span></span> <span data-ttu-id="63012-158">Para obtener más información, consulte [SqlClient para las funciones de Entity Framework](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span><span class="sxs-lookup"><span data-stu-id="63012-158">For more information, see [SqlClient for Entity Framework Functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63012-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="63012-159">See Also</span></span>  
 [<span data-ttu-id="63012-160">Funciones canónicas</span><span class="sxs-lookup"><span data-stu-id="63012-160">Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
