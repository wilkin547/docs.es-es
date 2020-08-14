---
ms.openlocfilehash: 3db4b0b42a154c5bc9296889ae9dc4b7ecf1e58e
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556234"
---
### <a name="allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported"></a><span data-ttu-id="12fc3-101">No se admite el modificador de compatibilidad AllowUpdateChildControlIndexForTabControls</span><span class="sxs-lookup"><span data-stu-id="12fc3-101">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>

<span data-ttu-id="12fc3-102">El modificador de compatibilidad `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` se admite en Windows Forms en .NET Framework 4.6 y versiones posteriores, pero no se admite en .NET Core ni .NET 5.0 y posterior.</span><span class="sxs-lookup"><span data-stu-id="12fc3-102">The `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` compatibility switch is supported in Windows Forms on .NET Framework 4.6 and later versions but is not supported on .NET Core or .NET 5.0 and later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="12fc3-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="12fc3-103">Change description</span></span>

<span data-ttu-id="12fc3-104">En .NET Framework 4.6 y en versiones posteriores, al seleccionar una pestaña, se reordena su colección de controles.</span><span class="sxs-lookup"><span data-stu-id="12fc3-104">In .NET Framework 4.6 and later versions, selecting a tab reorders its control collection.</span></span> <span data-ttu-id="12fc3-105">El modificador de compatibilidad `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` permite a una aplicación omitir esta reordenación cuando no se desea este comportamiento.</span><span class="sxs-lookup"><span data-stu-id="12fc3-105">The `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` compatibility switch allows an application to skip this reordering when this behavior is undesirable.</span></span>

<span data-ttu-id="12fc3-106">En .NET Core y .NET 5.0 y posterior no se admite el modificador `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls`.</span><span class="sxs-lookup"><span data-stu-id="12fc3-106">In .NET Core and .NET 5.0 and later, the `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="12fc3-107">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="12fc3-107">Version introduced</span></span>

<span data-ttu-id="12fc3-108">3.0</span><span class="sxs-lookup"><span data-stu-id="12fc3-108">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="12fc3-109">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="12fc3-109">Recommended action</span></span>

<span data-ttu-id="12fc3-110">Quite el modificador.</span><span class="sxs-lookup"><span data-stu-id="12fc3-110">Remove the switch.</span></span> <span data-ttu-id="12fc3-111">No se admite el modificador y no hay ninguna funcionalidad alternativa disponible.</span><span class="sxs-lookup"><span data-stu-id="12fc3-111">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="12fc3-112">Categoría</span><span class="sxs-lookup"><span data-stu-id="12fc3-112">Category</span></span>

<span data-ttu-id="12fc3-113">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="12fc3-113">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="12fc3-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="12fc3-114">Affected APIs</span></span>

- <span data-ttu-id="12fc3-115">Ninguna</span><span class="sxs-lookup"><span data-stu-id="12fc3-115">None</span></span>

<!-- 

#### Affected APIs

- Not detectable via API analysis

-->
