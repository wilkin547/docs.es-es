---
ms.openlocfilehash: 75baa4f23eae838defafd3ce9b3907a187982a18
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937103"
---
### <a name="enablevisualstylevalidation-compatibility-switch-not-supported"></a><span data-ttu-id="f7ac1-101">No se admite el modificador de compatibilidad EnableVisualStyleValidation</span><span class="sxs-lookup"><span data-stu-id="f7ac1-101">EnableVisualStyleValidation compatibility switch not supported</span></span>

<span data-ttu-id="f7ac1-102">No se admite el modificador de compatibilidad `Switch.System.Windows.Forms.EnableVisualStyleValidation` en Windows Forms en .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="f7ac1-102">The `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="f7ac1-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="f7ac1-103">Change description</span></span>

<span data-ttu-id="f7ac1-104">En .NET Framework, el modificador de compatibilidad `Switch.System.Windows.Forms.EnableVisualStyleValidation` permitía que una aplicación rechazara la validación de los estilos visuales proporcionados en un formato numérico.</span><span class="sxs-lookup"><span data-stu-id="f7ac1-104">In .NET Framework, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch allowed an application to opt out of validation of visual styles supplied in a numeric form.</span></span>

<span data-ttu-id="f7ac1-105">En .NET Core, no se admite el modificador `Switch.System.Windows.Forms.EnableVisualStyleValidation`.</span><span class="sxs-lookup"><span data-stu-id="f7ac1-105">In .NET Core, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f7ac1-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="f7ac1-106">Version introduced</span></span>

<span data-ttu-id="f7ac1-107">3.0 (versión preliminar 9)</span><span class="sxs-lookup"><span data-stu-id="f7ac1-107">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f7ac1-108">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="f7ac1-108">Recommended action</span></span>

<span data-ttu-id="f7ac1-109">Quite el modificador.</span><span class="sxs-lookup"><span data-stu-id="f7ac1-109">Remove the switch.</span></span> <span data-ttu-id="f7ac1-110">No se admite el modificador y no hay ninguna funcionalidad alternativa disponible.</span><span class="sxs-lookup"><span data-stu-id="f7ac1-110">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="f7ac1-111">Categoría</span><span class="sxs-lookup"><span data-stu-id="f7ac1-111">Category</span></span>

<span data-ttu-id="f7ac1-112">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f7ac1-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f7ac1-113">API afectadas</span><span class="sxs-lookup"><span data-stu-id="f7ac1-113">Affected APIs</span></span>

- <span data-ttu-id="f7ac1-114">Ninguna</span><span class="sxs-lookup"><span data-stu-id="f7ac1-114">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
