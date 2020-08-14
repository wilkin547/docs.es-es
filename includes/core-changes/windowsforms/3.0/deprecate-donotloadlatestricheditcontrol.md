---
ms.openlocfilehash: e10b5168d59edd56ff549a3a1e3a09d023fe5e28
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556229"
---
### <a name="donotloadlatestricheditcontrol-compatibility-switch-not-supported"></a><span data-ttu-id="7246d-101">No se admite el modificador de compatibilidad DoNotLoadLatestRichEditControl</span><span class="sxs-lookup"><span data-stu-id="7246d-101">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>

<span data-ttu-id="7246d-102">El modificador de compatibilidad `Switch.System.Windows.Forms.UseLegacyImages`, incorporado en .NET Framework 4.7.1, no se admite en Windows Forms en .NET Core ni .NET 5.0 y posterior.</span><span class="sxs-lookup"><span data-stu-id="7246d-102">The `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch, which was introduced in .NET Framework 4.7.1, is not supported in Windows Forms on .NET Core or .NET 5.0 and later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="7246d-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="7246d-103">Change description</span></span>

<span data-ttu-id="7246d-104">En .NET Framework 4.6.2 y versiones anteriores, el control <xref:System.Windows.Forms.RichTextBox> crea una instancia de RichEdit v3.0 de Win32 y, en las aplicaciones que tienen como destino .NET Framework 4.7.1, el control <xref:System.Windows.Forms.RichTextBox> crea una instancia de RichEdit v4.1 (en *msftedit.dll*).</span><span class="sxs-lookup"><span data-stu-id="7246d-104">In .NET Framework 4.6.2 and previous versions, the <xref:System.Windows.Forms.RichTextBox> control instantiates the Win32 RichEdit control v3.0, and for applications that target .NET Framework 4.7.1, the  <xref:System.Windows.Forms.RichTextBox> control instantiates RichEdit v4.1 (in *msftedit.dll*).</span></span> <span data-ttu-id="7246d-105">El modificador de compatibilidad `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` se incorporó para permitir que las aplicaciones que tienen como destino .NET Framework 4.7.1 y versiones posteriores omitan el nuevo control RichEdit v4.1 y, en su lugar, usen el antiguo control RichEdit v3.</span><span class="sxs-lookup"><span data-stu-id="7246d-105">The `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` compatibility switch was introduced to allow applications that target .NET Framework 4.7.1 and later versions to opt out of the new RichEdit v4.1 control and use the old RichEdit v3 control instead.</span></span>

<span data-ttu-id="7246d-106">En .NET Core y .NET 5.0 y versiones posteriores no se admite el modificador `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl`.</span><span class="sxs-lookup"><span data-stu-id="7246d-106">In .NET Core and .NET 5.0 and later versions, the `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` switch is not supported.</span></span> <span data-ttu-id="7246d-107">Solo se admiten las nuevas versiones del control <xref:System.Windows.Forms.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="7246d-107">Only new versions of the <xref:System.Windows.Forms.RichTextBox> control are supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="7246d-108">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="7246d-108">Version introduced</span></span>

<span data-ttu-id="7246d-109">3.0</span><span class="sxs-lookup"><span data-stu-id="7246d-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="7246d-110">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="7246d-110">Recommended action</span></span>

<span data-ttu-id="7246d-111">Quite el modificador.</span><span class="sxs-lookup"><span data-stu-id="7246d-111">Remove the switch.</span></span> <span data-ttu-id="7246d-112">No se admite el modificador y no hay ninguna funcionalidad alternativa disponible.</span><span class="sxs-lookup"><span data-stu-id="7246d-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="7246d-113">Categoría</span><span class="sxs-lookup"><span data-stu-id="7246d-113">Category</span></span>

<span data-ttu-id="7246d-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7246d-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7246d-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="7246d-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.RichTextBox?displayProperty=nameWithType>

<!-- 

#### Affected APIs

-  `T:System.Windows.Forms.RichTextBox` 

-->
