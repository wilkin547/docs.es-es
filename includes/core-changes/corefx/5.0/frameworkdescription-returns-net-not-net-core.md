---
ms.openlocfilehash: 80d13609f1b02ae0ac875b2028e745670bb8f503
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050576"
---
### <a name="frameworkdescriptions-value-is-net-instead-of-net-core"></a><span data-ttu-id="5d306-101">El valor de FrameworkDescription es .NET en lugar de .NET Core</span><span class="sxs-lookup"><span data-stu-id="5d306-101">FrameworkDescription's value is .NET instead of .NET Core</span></span>

<span data-ttu-id="5d306-102">Ahora <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> devuelve ".NET" en lugar de ".NET Core".</span><span class="sxs-lookup"><span data-stu-id="5d306-102"><xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> now returns ".NET" instead of ".NET Core".</span></span>

#### <a name="change-description"></a><span data-ttu-id="5d306-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="5d306-103">Change description</span></span>

<span data-ttu-id="5d306-104">En versiones anteriores de .NET, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> devuelve ".NET Core" como parte de la cadena de descripción, por ejemplo, `.NET Core 3.1.1`.</span><span class="sxs-lookup"><span data-stu-id="5d306-104">In previous .NET versions, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> returns ".NET Core" as part of the description string, for example, `.NET Core 3.1.1`.</span></span>

<span data-ttu-id="5d306-105">A partir de .NET 5.0, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> devuelve ".NET" como parte de la cadena de descripción, por ejemplo, `.NET 5.0.0`.</span><span class="sxs-lookup"><span data-stu-id="5d306-105">Starting in .NET 5.0, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> returns ".NET" as part of the description string, for example, `.NET 5.0.0`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="5d306-106">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="5d306-106">Reason for change</span></span>

<span data-ttu-id="5d306-107">Con .NET 5, `netcoreapp` se reemplaza por `net` como el moniker corto del marco de destino.</span><span class="sxs-lookup"><span data-stu-id="5d306-107">With .NET 5, `netcoreapp` is replaced by `net` as the short target-framework moniker.</span></span> <span data-ttu-id="5d306-108">Por coherencia, también se ha actualizado la descripción del marco.</span><span class="sxs-lookup"><span data-stu-id="5d306-108">For consistency, the framework's description has also been updated.</span></span> <span data-ttu-id="5d306-109">El cambio es cosmético, ya que `FrameworkName` solo se codifica en la propiedad <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5d306-109">The change is cosmetic, as the `FrameworkName` isn't encoded anywhere else than in the <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> property.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="5d306-110">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="5d306-110">Version introduced</span></span>

<span data-ttu-id="5d306-111">5.0</span><span class="sxs-lookup"><span data-stu-id="5d306-111">5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="5d306-112">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="5d306-112">Recommended action</span></span>

<span data-ttu-id="5d306-113">Actualice cualquier código que busque ".NET Core" en la cadena devuelta por <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription>.</span><span class="sxs-lookup"><span data-stu-id="5d306-113">Update any code that searches for ".NET Core" in the string returned by <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription>.</span></span>

#### <a name="category"></a><span data-ttu-id="5d306-114">Categoría</span><span class="sxs-lookup"><span data-stu-id="5d306-114">Category</span></span>

<span data-ttu-id="5d306-115">Bibliotecas de Core .NET</span><span class="sxs-lookup"><span data-stu-id="5d306-115">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="5d306-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="5d306-116">Affected APIs</span></span>

- <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription`

-->
