---
ms.openlocfilehash: 75baa4f23eae838defafd3ce9b3907a187982a18
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937103"
---
### <a name="enablevisualstylevalidation-compatibility-switch-not-supported"></a><span data-ttu-id="86cf3-101">No se admite el modificador de compatibilidad EnableVisualStyleValidation</span><span class="sxs-lookup"><span data-stu-id="86cf3-101">EnableVisualStyleValidation compatibility switch not supported</span></span>

<span data-ttu-id="86cf3-102">No se admite el modificador de compatibilidad `Switch.System.Windows.Forms.EnableVisualStyleValidation` en Windows Forms en .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="86cf3-102">The `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="86cf3-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="86cf3-103">Change description</span></span>

<span data-ttu-id="86cf3-104">En .NET Framework, el modificador de compatibilidad `Switch.System.Windows.Forms.EnableVisualStyleValidation` permitía que una aplicación rechazara la validación de los estilos visuales proporcionados en un formato numérico.</span><span class="sxs-lookup"><span data-stu-id="86cf3-104">In .NET Framework, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch allowed an application to opt out of validation of visual styles supplied in a numeric form.</span></span>

<span data-ttu-id="86cf3-105">En .NET Core, no se admite el modificador `Switch.System.Windows.Forms.EnableVisualStyleValidation`.</span><span class="sxs-lookup"><span data-stu-id="86cf3-105">In .NET Core, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="86cf3-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="86cf3-106">Version introduced</span></span>

<span data-ttu-id="86cf3-107">3.0 (versión preliminar 9)</span><span class="sxs-lookup"><span data-stu-id="86cf3-107">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="86cf3-108">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="86cf3-108">Recommended action</span></span>

<span data-ttu-id="86cf3-109">Quite el modificador.</span><span class="sxs-lookup"><span data-stu-id="86cf3-109">Remove the switch.</span></span> <span data-ttu-id="86cf3-110">No se admite el modificador y no hay ninguna funcionalidad alternativa disponible.</span><span class="sxs-lookup"><span data-stu-id="86cf3-110">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="86cf3-111">Categoría</span><span class="sxs-lookup"><span data-stu-id="86cf3-111">Category</span></span>

<span data-ttu-id="86cf3-112">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="86cf3-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="86cf3-113">API afectadas</span><span class="sxs-lookup"><span data-stu-id="86cf3-113">Affected APIs</span></span>

- <span data-ttu-id="86cf3-114">None</span><span class="sxs-lookup"><span data-stu-id="86cf3-114">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
