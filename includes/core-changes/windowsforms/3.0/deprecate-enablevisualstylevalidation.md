---
ms.openlocfilehash: 196a26bd235e5e2556baa7fac979b3316ff81e1f
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556221"
---
### <a name="enablevisualstylevalidation-compatibility-switch-not-supported"></a><span data-ttu-id="3000d-101">No se admite el modificador de compatibilidad EnableVisualStyleValidation</span><span class="sxs-lookup"><span data-stu-id="3000d-101">EnableVisualStyleValidation compatibility switch not supported</span></span>

<span data-ttu-id="3000d-102">El modificador de compatibilidad `Switch.System.Windows.Forms.EnableVisualStyleValidation` no se admite en Windows Forms en .NET Core ni .NET 5.0 y posterior.</span><span class="sxs-lookup"><span data-stu-id="3000d-102">The `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch is not supported in Windows Forms on .NET Core or .NET 5.0 and later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="3000d-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="3000d-103">Change description</span></span>

<span data-ttu-id="3000d-104">En .NET Framework, el modificador de compatibilidad `Switch.System.Windows.Forms.EnableVisualStyleValidation` permitía que una aplicación rechazara la validación de los estilos visuales proporcionados en un formato numérico.</span><span class="sxs-lookup"><span data-stu-id="3000d-104">In .NET Framework, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch allowed an application to opt out of validation of visual styles supplied in a numeric form.</span></span>

<span data-ttu-id="3000d-105">En .NET Core y .NET 5.0 y posterior no se admite el modificador `Switch.System.Windows.Forms.EnableVisualStyleValidation`.</span><span class="sxs-lookup"><span data-stu-id="3000d-105">In .NET Core and .NET 5.0 and later, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3000d-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="3000d-106">Version introduced</span></span>

<span data-ttu-id="3000d-107">3.0</span><span class="sxs-lookup"><span data-stu-id="3000d-107">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3000d-108">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="3000d-108">Recommended action</span></span>

<span data-ttu-id="3000d-109">Quite el modificador.</span><span class="sxs-lookup"><span data-stu-id="3000d-109">Remove the switch.</span></span> <span data-ttu-id="3000d-110">No se admite el modificador y no hay ninguna funcionalidad alternativa disponible.</span><span class="sxs-lookup"><span data-stu-id="3000d-110">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="3000d-111">Categoría</span><span class="sxs-lookup"><span data-stu-id="3000d-111">Category</span></span>

<span data-ttu-id="3000d-112">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3000d-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3000d-113">API afectadas</span><span class="sxs-lookup"><span data-stu-id="3000d-113">Affected APIs</span></span>

- <span data-ttu-id="3000d-114">Ninguna</span><span class="sxs-lookup"><span data-stu-id="3000d-114">None</span></span>

<!-- 

#### Affected APIs

- Not detectable via API analysis

-->
