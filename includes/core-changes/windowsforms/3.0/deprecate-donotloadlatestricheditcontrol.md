---
ms.openlocfilehash: 3f0e8fb4d0d727b40cff5de7cfdc7529bf32dac4
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937042"
---
### <a name="donotloadlatestricheditcontrol-compatibility-switch-not-supported"></a><span data-ttu-id="cd1bd-101">No se admite el modificador de compatibilidad DoNotLoadLatestRichEditControl</span><span class="sxs-lookup"><span data-stu-id="cd1bd-101">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>

<span data-ttu-id="cd1bd-102">El modificador de compatibilidad `Switch.System.Windows.Forms.UseLegacyImages`, que se introdujo en .NET Framework 4.7.1, no se admite en Windows Forms en .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="cd1bd-102">The `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch, which was introduced in .NET Framework 4.7.1, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="cd1bd-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="cd1bd-103">Change description</span></span>

<span data-ttu-id="cd1bd-104">En .NET Framework 4.6.2 y en versiones anteriores, el control <xref:System.Windows.Forms.RichTextBox> crea una instancia del control RichEdit v3.0 de Win32 y, para las aplicaciones que tienen como destino .NET Framework 4.7.1, el control <xref:System.Windows.Forms.RichTextBox> crea una instancia de RichEdit v4.1 (en *msftedit.dll*).</span><span class="sxs-lookup"><span data-stu-id="cd1bd-104">In the .NET Framework 4.6.2 and previous versions, the <xref:System.Windows.Forms.RichTextBox> control would instantiate the Win32 RichEdit control v3.0, and for applications that target .NET Framework 4.7.1, the  <xref:System.Windows.Forms.RichTextBox> control would instantiate RichEdit v4.1 (in *msftedit.dll*).</span></span> <span data-ttu-id="cd1bd-105">Se introdujo el modificador de compatibilidad `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` para permitir que las aplicaciones que tienen como destino .NET Framework 4.7.1 y versiones posteriores ignoren el nuevo control RichEdit v4.1 y usen en su lugar el antiguo control RichEdit v3.</span><span class="sxs-lookup"><span data-stu-id="cd1bd-105">The `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` compatibility switch was introduced to allow applications that target .NET Framework 4.7.1 and later versions to opt-out of the new RichEdit v4.1 control and use the old RichEdit v3 control instead.</span></span>

<span data-ttu-id="cd1bd-106">En .NET Core, no se admite el modificador `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl`.</span><span class="sxs-lookup"><span data-stu-id="cd1bd-106">In .NET Core, the `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` switch is not supported.</span></span> <span data-ttu-id="cd1bd-107">Solo se admiten las nuevas versiones del control <xref:System.Windows.Forms.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="cd1bd-107">Only new versions of the  <xref:System.Windows.Forms.RichTextBox> control are supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="cd1bd-108">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="cd1bd-108">Version introduced</span></span>

<span data-ttu-id="cd1bd-109">3.0 (versión preliminar 9)</span><span class="sxs-lookup"><span data-stu-id="cd1bd-109">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="cd1bd-110">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="cd1bd-110">Recommended action</span></span>

<span data-ttu-id="cd1bd-111">Quite el modificador.</span><span class="sxs-lookup"><span data-stu-id="cd1bd-111">Remove the switch.</span></span> <span data-ttu-id="cd1bd-112">No se admite el modificador y no hay ninguna funcionalidad alternativa disponible.</span><span class="sxs-lookup"><span data-stu-id="cd1bd-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="cd1bd-113">Categoría</span><span class="sxs-lookup"><span data-stu-id="cd1bd-113">Category</span></span>

<span data-ttu-id="cd1bd-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cd1bd-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="cd1bd-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="cd1bd-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.RichTextBox?displayProperty=nameWithType>

<!-- 

### Affected APIs

-  `T:System.Windows.Forms.RichTextBox` 

-->
