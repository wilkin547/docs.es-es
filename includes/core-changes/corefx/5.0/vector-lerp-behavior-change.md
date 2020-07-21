---
ms.openlocfilehash: 4bc060f991501b81db0cb7c521e55996a2b5e91e
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281318"
---
### <a name="behavior-change-for-vector2lerp-and-vector4lerp"></a><span data-ttu-id="29f7f-101">Cambio de comportamiento de Vector2.Lerp y Vector4.Lerp</span><span class="sxs-lookup"><span data-stu-id="29f7f-101">Behavior change for Vector2.Lerp and Vector4.Lerp</span></span>

<span data-ttu-id="29f7f-102">La implementación de <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> y <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> ha cambiado para tener en cuenta correctamente un error de redondeo de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="29f7f-102">The implementation of <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> and <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> changed to correctly account for a floating-point rounding error.</span></span>

#### <a name="change-description"></a><span data-ttu-id="29f7f-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="29f7f-103">Change description</span></span>

<span data-ttu-id="29f7f-104">Anteriormente, <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> y <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> se implementaban como `value1 + (value2 - value1) * amount`.</span><span class="sxs-lookup"><span data-stu-id="29f7f-104">Previously, <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> and <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> were implemented as `value1 + (value2 - value1) * amount`.</span></span> <span data-ttu-id="29f7f-105">Pero debido a un error de redondeo de punto flotante, este algoritmo no siempre devuelve `value2` cuando `amount` es `1.0f`.</span><span class="sxs-lookup"><span data-stu-id="29f7f-105">However, due to a floating-point rounding error, this algorithm doesn't always return `value2` when `amount` is `1.0f`.</span></span>

<span data-ttu-id="29f7f-106">En .NET 5.0 y versiones posteriores, la implementación usa el mismo algoritmo que <xref:System.Numerics.Vector3.Lerp(System.Numerics.Vector3,System.Numerics.Vector3,System.Single)?displayProperty=nameWithType>, que es `(value1 * (1.0f - amount)) + (value2 * amount)`.</span><span class="sxs-lookup"><span data-stu-id="29f7f-106">In .NET 5.0 and later, the implementation uses the same algorithm as <xref:System.Numerics.Vector3.Lerp(System.Numerics.Vector3,System.Numerics.Vector3,System.Single)?displayProperty=nameWithType>, which is `(value1 * (1.0f - amount)) + (value2 * amount)`.</span></span> <span data-ttu-id="29f7f-107">Este algoritmo tiene en cuenta correctamente el error de redondeo.</span><span class="sxs-lookup"><span data-stu-id="29f7f-107">This algorithm correctly accounts for the rounding error.</span></span> <span data-ttu-id="29f7f-108">Ahora, cuando `amount` es `1.0f`, el resultado es precisamente `value2`.</span><span class="sxs-lookup"><span data-stu-id="29f7f-108">Now, when `amount` is `1.0f`, the result is precisely `value2`.</span></span> <span data-ttu-id="29f7f-109">El algoritmo actualizado también permite optimizar libremente el algoritmo mediante <xref:System.MathF.FusedMultiplyAdd%2A?displayProperty=nameWithType> cuando está disponible.</span><span class="sxs-lookup"><span data-stu-id="29f7f-109">The updated algorithm also allows the algorithm to be freely optimized using <xref:System.MathF.FusedMultiplyAdd%2A?displayProperty=nameWithType> when it's available.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="29f7f-110">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="29f7f-110">Version introduced</span></span>

<span data-ttu-id="29f7f-111">5.0 (versión preliminar 7)</span><span class="sxs-lookup"><span data-stu-id="29f7f-111">5.0 Preview 7</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="29f7f-112">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="29f7f-112">Recommended action</span></span>

<span data-ttu-id="29f7f-113">No se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="29f7f-113">No action is necessary.</span></span> <span data-ttu-id="29f7f-114">Pero si quiere mantener el comportamiento anterior, puede implementar una función `Lerp` propia que use el algoritmo anterior de `value1 + (value2 - value1) * amount`.</span><span class="sxs-lookup"><span data-stu-id="29f7f-114">However, if you want to maintain the old behavior, you can implement your own `Lerp` function that uses the previous algorithm of `value1 + (value2 - value1) * amount`.</span></span>

#### <a name="category"></a><span data-ttu-id="29f7f-115">Categoría</span><span class="sxs-lookup"><span data-stu-id="29f7f-115">Category</span></span>

<span data-ttu-id="29f7f-116">Bibliotecas de Core .NET</span><span class="sxs-lookup"><span data-stu-id="29f7f-116">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="29f7f-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="29f7f-117">Affected APIs</span></span>

- <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=fullName>
- <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)`
- `M:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)`

-->
