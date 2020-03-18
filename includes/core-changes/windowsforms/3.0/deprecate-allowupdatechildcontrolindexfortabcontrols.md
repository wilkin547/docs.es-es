---
ms.openlocfilehash: 7e76c32ddeb50eaf1ee93d7cf3cac7469187cc41
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937097"
---
### <a name="allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported"></a><span data-ttu-id="570fe-101">No se admite el modificador de compatibilidad AllowUpdateChildControlIndexForTabControls</span><span class="sxs-lookup"><span data-stu-id="570fe-101">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>

<span data-ttu-id="570fe-102">El modificador de compatibilidad `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` se admite en Windows Forms en .NET Framework 4.6 y en versiones posteriores, pero no se admite en Windows Forms a partir de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="570fe-102">The `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` compatibility switch is supported in Windows Forms on .NET Framework 4.6 and later versions but is not supported in Windows Forms starting with .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="570fe-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="570fe-103">Change description</span></span>

<span data-ttu-id="570fe-104">En .NET Framework 4.6 y en versiones posteriores, al seleccionar una pestaña, se reordena su colección de controles.</span><span class="sxs-lookup"><span data-stu-id="570fe-104">In .NET Framework 4.6 and later versions, selecting a tab reorders its control collection.</span></span> <span data-ttu-id="570fe-105">El modificador de compatibilidad `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` permite a una aplicación omitir esta reordenación cuando no se desea este comportamiento.</span><span class="sxs-lookup"><span data-stu-id="570fe-105">The `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` compatibility switch allows an application to skip this reordering when this behavior is undesirable.</span></span>

<span data-ttu-id="570fe-106">En .NET Core, no se admite el modificador `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls`.</span><span class="sxs-lookup"><span data-stu-id="570fe-106">In .NET Core, the `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="570fe-107">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="570fe-107">Version introduced</span></span>

<span data-ttu-id="570fe-108">3.0 (versión preliminar 9)</span><span class="sxs-lookup"><span data-stu-id="570fe-108">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="570fe-109">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="570fe-109">Recommended action</span></span>

<span data-ttu-id="570fe-110">Quite el modificador.</span><span class="sxs-lookup"><span data-stu-id="570fe-110">Remove the switch.</span></span> <span data-ttu-id="570fe-111">No se admite el modificador y no hay ninguna funcionalidad alternativa disponible.</span><span class="sxs-lookup"><span data-stu-id="570fe-111">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="570fe-112">Categoría</span><span class="sxs-lookup"><span data-stu-id="570fe-112">Category</span></span>

<span data-ttu-id="570fe-113">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="570fe-113">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="570fe-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="570fe-114">Affected APIs</span></span>

- <span data-ttu-id="570fe-115">Ninguna</span><span class="sxs-lookup"><span data-stu-id="570fe-115">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
