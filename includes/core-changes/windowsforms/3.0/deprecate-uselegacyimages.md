---
ms.openlocfilehash: 07527c247e6ccd53d2a77793946ffc796c3e1cbb
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643920"
---
### <a name="switchsystemwindowsformsuselegacyimages-compatibility-switch-not-supported"></a><span data-ttu-id="021a7-101">No se admite el modificador de compatibilidad Switch.System.Windows.Forms.UseLegacyImages</span><span class="sxs-lookup"><span data-stu-id="021a7-101">Switch.System.Windows.Forms.UseLegacyImages compatibility switch not supported</span></span>

<span data-ttu-id="021a7-102">El modificador de compatibilidad `Switch.System.Windows.Forms.UseLegacyImages`, que se introdujo en .NET Framework 4.8, no se admite en Windows Forms en .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="021a7-102">The `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch, which was introduced in .NET Framework 4.8, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="021a7-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="021a7-103">Change description</span></span>

<span data-ttu-id="021a7-104">A partir de .NET Framework 4.8, el modificador de compatibilidad `Switch.System.Windows.Forms.UseLegacyImages` soluciona posibles problemas de escalado de imágenes en escenarios de ClickOnce en entornos con valores altos de PPP.</span><span class="sxs-lookup"><span data-stu-id="021a7-104">Starting with the .NET Framework 4.8, the `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch addressed possible image scaling issues in ClickOnce scenarios in high DPI environments.</span></span> <span data-ttu-id="021a7-105">Cuando se establece en `true`, el modificador permite al usuario restaurar el escalado de imágenes heredadas en pantallas con valores altos de PPP cuya escala está establecida en un valor mayor que 100 %.</span><span class="sxs-lookup"><span data-stu-id="021a7-105">When set to `true`, the switch allows the user to restore legacy image scaling on high DPI displays whose scale is set to greater than 100%.</span></span> <span data-ttu-id="021a7-106">Para obtener más información, consulte [Notas de la versión de .NET Framework 4.8](https://github.com/microsoft/dotnet/blob/master/releases/net48/dotnet48-changes.md#clickonce) en GitHub.</span><span class="sxs-lookup"><span data-stu-id="021a7-106">For more information, see [.NET Framework 4.8 Release Notes](https://github.com/microsoft/dotnet/blob/master/releases/net48/dotnet48-changes.md#clickonce) on GitHub.</span></span>

<span data-ttu-id="021a7-107">En .NET Core, no se admite el modificador `Switch.System.Windows.Forms.UseLegacyImages`.</span><span class="sxs-lookup"><span data-stu-id="021a7-107">In .NET Core, the `Switch.System.Windows.Forms.UseLegacyImages` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="021a7-108">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="021a7-108">Version introduced</span></span>

<span data-ttu-id="021a7-109">3.0 (versión preliminar 9)</span><span class="sxs-lookup"><span data-stu-id="021a7-109">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="021a7-110">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="021a7-110">Recommended action</span></span>

<span data-ttu-id="021a7-111">Quite el modificador.</span><span class="sxs-lookup"><span data-stu-id="021a7-111">Remove the switch.</span></span> <span data-ttu-id="021a7-112">No se admite el modificador y no hay ninguna funcionalidad alternativa disponible.</span><span class="sxs-lookup"><span data-stu-id="021a7-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="021a7-113">Categoría</span><span class="sxs-lookup"><span data-stu-id="021a7-113">Category</span></span>

<span data-ttu-id="021a7-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="021a7-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="021a7-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="021a7-115">Affected APIs</span></span>

- <span data-ttu-id="021a7-116">None</span><span class="sxs-lookup"><span data-stu-id="021a7-116">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
