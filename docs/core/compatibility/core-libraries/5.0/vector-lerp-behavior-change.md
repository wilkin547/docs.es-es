---
title: 'Cambio importante: Cambio de comportamiento de Vector2.Lerp y Vector4.Lerp'
description: Obtenga información sobre el cambio importante de .NET 5.0 en las bibliotecas básicas de .NET donde la implementación de Vector2.Lerp y Vector4.Lerp ha cambiado para tener en cuenta correctamente un error de redondeo de punto flotante.
ms.date: 11/01/2020
ms.openlocfilehash: 8e363a559dba8b7563c40637c47f101d59951216
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760129"
---
# <a name="behavior-change-for-vector2lerp-and-vector4lerp"></a><span data-ttu-id="f5fb4-103">Cambio de comportamiento de Vector2.Lerp y Vector4.Lerp</span><span class="sxs-lookup"><span data-stu-id="f5fb4-103">Behavior change for Vector2.Lerp and Vector4.Lerp</span></span>

<span data-ttu-id="f5fb4-104">La implementación de <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> y <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> ha cambiado para tener en cuenta correctamente un error de redondeo de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="f5fb4-104">The implementation of <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> and <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> changed to correctly account for a floating-point rounding error.</span></span>

## <a name="change-description"></a><span data-ttu-id="f5fb4-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="f5fb4-105">Change description</span></span>

<span data-ttu-id="f5fb4-106">Anteriormente, <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> y <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> se implementaban como `value1 + (value2 - value1) * amount`.</span><span class="sxs-lookup"><span data-stu-id="f5fb4-106">Previously, <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> and <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> were implemented as `value1 + (value2 - value1) * amount`.</span></span> <span data-ttu-id="f5fb4-107">Pero debido a un error de redondeo de punto flotante, este algoritmo no siempre devuelve `value2` cuando `amount` es `1.0f`.</span><span class="sxs-lookup"><span data-stu-id="f5fb4-107">However, due to a floating-point rounding error, this algorithm doesn't always return `value2` when `amount` is `1.0f`.</span></span>

<span data-ttu-id="f5fb4-108">En .NET 5.0 y versiones posteriores, la implementación usa el mismo algoritmo que <xref:System.Numerics.Vector3.Lerp(System.Numerics.Vector3,System.Numerics.Vector3,System.Single)?displayProperty=nameWithType>, que es `(value1 * (1.0f - amount)) + (value2 * amount)`.</span><span class="sxs-lookup"><span data-stu-id="f5fb4-108">In .NET 5.0 and later, the implementation uses the same algorithm as <xref:System.Numerics.Vector3.Lerp(System.Numerics.Vector3,System.Numerics.Vector3,System.Single)?displayProperty=nameWithType>, which is `(value1 * (1.0f - amount)) + (value2 * amount)`.</span></span> <span data-ttu-id="f5fb4-109">Este algoritmo tiene en cuenta correctamente el error de redondeo.</span><span class="sxs-lookup"><span data-stu-id="f5fb4-109">This algorithm correctly accounts for the rounding error.</span></span> <span data-ttu-id="f5fb4-110">Ahora, cuando `amount` es `1.0f`, el resultado es precisamente `value2`.</span><span class="sxs-lookup"><span data-stu-id="f5fb4-110">Now, when `amount` is `1.0f`, the result is precisely `value2`.</span></span> <span data-ttu-id="f5fb4-111">El algoritmo actualizado también permite optimizar libremente el algoritmo mediante <xref:System.MathF.FusedMultiplyAdd%2A?displayProperty=nameWithType> cuando está disponible.</span><span class="sxs-lookup"><span data-stu-id="f5fb4-111">The updated algorithm also allows the algorithm to be freely optimized using <xref:System.MathF.FusedMultiplyAdd%2A?displayProperty=nameWithType> when it's available.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="f5fb4-112">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="f5fb4-112">Version introduced</span></span>

<span data-ttu-id="f5fb4-113">5.0</span><span class="sxs-lookup"><span data-stu-id="f5fb4-113">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="f5fb4-114">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="f5fb4-114">Recommended action</span></span>

<span data-ttu-id="f5fb4-115">No se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="f5fb4-115">No action is necessary.</span></span> <span data-ttu-id="f5fb4-116">Pero si quiere mantener el comportamiento anterior, puede implementar una función `Lerp` propia que use el algoritmo anterior de `value1 + (value2 - value1) * amount`.</span><span class="sxs-lookup"><span data-stu-id="f5fb4-116">However, if you want to maintain the old behavior, you can implement your own `Lerp` function that uses the previous algorithm of `value1 + (value2 - value1) * amount`.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="f5fb4-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="f5fb4-117">Affected APIs</span></span>

- <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=fullName>
- <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `M:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)`
- `M:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)`

-->
