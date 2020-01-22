---
ms.openlocfilehash: 7f528510e4158dad71280a7b1f269a231b8c60f2
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116344"
---
### <a name="types-in-microsoftvisualbasicdevices-namespace-not-available"></a><span data-ttu-id="d8760-101">Los tipos del espacio de nombres Microsoft.VisualBasic.Devices no están disponibles</span><span class="sxs-lookup"><span data-stu-id="d8760-101">Types in Microsoft.VisualBasic.Devices namespace not available</span></span>

<span data-ttu-id="d8760-102">Los tipos del espacio de nombres <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="d8760-102">The types in the <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> namespace are not available.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d8760-103">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="d8760-103">Version introduced</span></span>

<span data-ttu-id="d8760-104">.NET Core 3.0 (versión preliminar 8)</span><span class="sxs-lookup"><span data-stu-id="d8760-104">.NET Core 3.0 Preview 8</span></span>

#### <a name="change-description"></a><span data-ttu-id="d8760-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="d8760-105">Change description</span></span>

<span data-ttu-id="d8760-106">Los tipos del espacio de nombres <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> estaban disponibles en algunas versiones preliminares de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="d8760-106">The types in the <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> namespace were available in some .NET Core 3.0 Preview releases,.</span></span> <span data-ttu-id="d8760-107">A partir del SDK de .NET Core 3.0 (versión preliminar 9), ya no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="d8760-107">They are no longer available starting with .NET Core 3.0 Preview 9.</span></span>

<span data-ttu-id="d8760-108">Los tipos se han quitado para evitar dependencias de ensamblado innecesarias o cambios importantes en las versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="d8760-108">The types were removed to avoid unnecessary assembly dependencies or breaking changes in subsequent releases.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d8760-109">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="d8760-109">Recommended action</span></span>

<span data-ttu-id="d8760-110">Si su código depende del uso de los tipos <xref:Microsoft.VisualBasic.Devices> y de sus miembros, es posible que pueda usar un tipo o miembro equivalente de la biblioteca de clases .NET.</span><span class="sxs-lookup"><span data-stu-id="d8760-110">If your code depends on the use of <xref:Microsoft.VisualBasic.Devices> types and their members, you may be able to use a corresponding type or member in the .NET class library.</span></span> <span data-ttu-id="d8760-111">Por ejemplo, los tipos <xref:System.DateTime?displayProperty=nameWithType> y <xref:System.Environment?displayProperty=nameWithType> proporcionan una funcionalidad equivalente a la clase <xref:Microsoft.VisualBasic.Devices.Clock?displayProperty=nameWithType>, y la funcionalidad equivalente a la clase <xref:Microsoft.VisualBasic.Devices.Ports?displayProperty=nameWithType> la proporcionan los tipos del espacio de nombres <xref:System.IO.Ports?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d8760-111">For example, equivalent functionality to the <xref:Microsoft.VisualBasic.Devices.Clock?displayProperty=nameWithType> class is provided by the <xref:System.DateTime?displayProperty=nameWithType> and <xref:System.Environment?displayProperty=nameWithType> types, and equivalent functionality to the <xref:Microsoft.VisualBasic.Devices.Ports?displayProperty=nameWithType> class is provided by types in the <xref:System.IO.Ports?displayProperty=nameWithType> namespace.</span></span>

#### <a name="category"></a><span data-ttu-id="d8760-112">Categoría</span><span class="sxs-lookup"><span data-stu-id="d8760-112">Category</span></span>

<span data-ttu-id="d8760-113">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d8760-113">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d8760-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="d8760-114">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.Devices`

-->
