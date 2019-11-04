---
ms.openlocfilehash: 84b6bfc32f5a73597b227098e5aee1e3450cf85b
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198562"
---
### <a name="switchsystemwindowsformsenablevisualstylevalidation-compatibility-switch-not-supported"></a><span data-ttu-id="b5e15-101">No se admite el modificador de compatibilidad Switch.System.Windows.Forms.EnableVisualStyleValidation</span><span class="sxs-lookup"><span data-stu-id="b5e15-101">Switch.System.Windows.Forms.EnableVisualStyleValidation compatibility switch not supported</span></span>

<span data-ttu-id="b5e15-102">No se admite el modificador de compatibilidad `Switch.System.Windows.Forms.EnableVisualStyleValidation` en Windows Forms en .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="b5e15-102">The `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="b5e15-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="b5e15-103">Change description</span></span>

<span data-ttu-id="b5e15-104">En .NET Framework, el modificador de compatibilidad `Switch.System.Windows.Forms.EnableVisualStyleValidation` permitía que una aplicación rechazara la validación de los estilos visuales proporcionados en un formato numérico.</span><span class="sxs-lookup"><span data-stu-id="b5e15-104">In .NET Framework, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch allowed an application to opt out of validation of visual styles supplied in a numeric form.</span></span>

<span data-ttu-id="b5e15-105">En .NET Core, no se admite el modificador `Switch.System.Windows.Forms.EnableVisualStyleValidation`.</span><span class="sxs-lookup"><span data-stu-id="b5e15-105">In .NET Core, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b5e15-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="b5e15-106">Version introduced</span></span>

<span data-ttu-id="b5e15-107">3.0 (versión preliminar 9)</span><span class="sxs-lookup"><span data-stu-id="b5e15-107">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b5e15-108">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="b5e15-108">Recommended action</span></span>

<span data-ttu-id="b5e15-109">Quite el modificador.</span><span class="sxs-lookup"><span data-stu-id="b5e15-109">Remove the switch.</span></span> <span data-ttu-id="b5e15-110">No se admite el modificador y no hay ninguna funcionalidad alternativa disponible.</span><span class="sxs-lookup"><span data-stu-id="b5e15-110">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="b5e15-111">Categoría</span><span class="sxs-lookup"><span data-stu-id="b5e15-111">Category</span></span>

<span data-ttu-id="b5e15-112">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b5e15-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b5e15-113">API afectadas</span><span class="sxs-lookup"><span data-stu-id="b5e15-113">Affected APIs</span></span>

- <span data-ttu-id="b5e15-114">None</span><span class="sxs-lookup"><span data-stu-id="b5e15-114">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
