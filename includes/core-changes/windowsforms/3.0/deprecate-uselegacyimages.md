---
ms.openlocfilehash: d69f619522c7abc3171f1c089e53cc2754899f93
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556226"
---
### <a name="uselegacyimages-compatibility-switch-not-supported"></a><span data-ttu-id="44e20-101">No se admite el modificador de compatibilidad UseLegacyImages</span><span class="sxs-lookup"><span data-stu-id="44e20-101">UseLegacyImages compatibility switch not supported</span></span>

<span data-ttu-id="44e20-102">El modificador de compatibilidad `Switch.System.Windows.Forms.UseLegacyImages`, incorporado en .NET Framework 4.8, no se admite en Windows Forms en .NET Core ni .NET 5.0 y posterior.</span><span class="sxs-lookup"><span data-stu-id="44e20-102">The `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch, which was introduced in .NET Framework 4.8, is not supported in Windows Forms on .NET Core or .NET 5.0 and later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="44e20-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="44e20-103">Change description</span></span>

<span data-ttu-id="44e20-104">A partir de .NET Framework 4.8, el modificador de compatibilidad `Switch.System.Windows.Forms.UseLegacyImages` soluciona posibles problemas de escalado de imágenes en escenarios de ClickOnce en entornos con valores altos de PPP.</span><span class="sxs-lookup"><span data-stu-id="44e20-104">Starting with .NET Framework 4.8, the `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch addressed possible image scaling issues in ClickOnce scenarios in high DPI environments.</span></span> <span data-ttu-id="44e20-105">Cuando se establece en `true`, el modificador permite al usuario restaurar el escalado de imágenes heredadas en pantallas con valores altos de PPP cuya escala está establecida en un valor mayor que 100 %.</span><span class="sxs-lookup"><span data-stu-id="44e20-105">When set to `true`, the switch allows the user to restore legacy image scaling on high DPI displays whose scale is set to greater than 100%.</span></span> <span data-ttu-id="44e20-106">Para obtener más información, consulte [Notas de la versión de .NET Framework 4.8](https://github.com/microsoft/dotnet/blob/master/releases/net48/dotnet48-changes.md#clickonce) en GitHub.</span><span class="sxs-lookup"><span data-stu-id="44e20-106">For more information, see [.NET Framework 4.8 Release Notes](https://github.com/microsoft/dotnet/blob/master/releases/net48/dotnet48-changes.md#clickonce) on GitHub.</span></span>

<span data-ttu-id="44e20-107">En .NET Core y .NET 5.0 y posterior no se admite el modificador `Switch.System.Windows.Forms.UseLegacyImages`.</span><span class="sxs-lookup"><span data-stu-id="44e20-107">In .NET Core and .NET 5.0 and later, the `Switch.System.Windows.Forms.UseLegacyImages` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="44e20-108">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="44e20-108">Version introduced</span></span>

<span data-ttu-id="44e20-109">3.0</span><span class="sxs-lookup"><span data-stu-id="44e20-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="44e20-110">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="44e20-110">Recommended action</span></span>

<span data-ttu-id="44e20-111">Quite el modificador.</span><span class="sxs-lookup"><span data-stu-id="44e20-111">Remove the switch.</span></span> <span data-ttu-id="44e20-112">No se admite el modificador y no hay ninguna funcionalidad alternativa disponible.</span><span class="sxs-lookup"><span data-stu-id="44e20-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="44e20-113">Categoría</span><span class="sxs-lookup"><span data-stu-id="44e20-113">Category</span></span>

<span data-ttu-id="44e20-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="44e20-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="44e20-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="44e20-115">Affected APIs</span></span>

- <span data-ttu-id="44e20-116">Ninguna</span><span class="sxs-lookup"><span data-stu-id="44e20-116">None</span></span>

<!-- 

#### Affected APIs

- Not detectable via API analysis

-->
