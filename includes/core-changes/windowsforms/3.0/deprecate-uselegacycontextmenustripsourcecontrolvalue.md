---
ms.openlocfilehash: 5c1dc42a451d2c6a82e2c2429115db023c610334
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643908"
---
### <a name="switchsystemwindowsformsuselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported"></a><span data-ttu-id="bd8e2-101">No se admite el modificador de compatibilidad Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue</span><span class="sxs-lookup"><span data-stu-id="bd8e2-101">Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>

<span data-ttu-id="bd8e2-102">El modificador de compatibilidad `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue`, que se introdujo en .NET Framework 4.7.2, no se admite en Windows Forms en .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="bd8e2-102">The `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` compatibility switch, which was introduced in .NET Framework 4.7.2, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="bd8e2-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="bd8e2-103">Change description</span></span>

<span data-ttu-id="bd8e2-104">A partir de .NET Framework 4.7.2, el modificador de compatibilidad `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` permite al desarrollador ignorar el nuevo comportamiento de la propiedad <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>, que ahora devuelve una referencia al control de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="bd8e2-104">Starting with the .NET Framework 4.7.2, the `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` compatibility switch allows the developer to opt out of the new behavior of the <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> property, which now returns a reference to the source control.</span></span> <span data-ttu-id="bd8e2-105">El comportamiento anterior de la propiedad era devolver `null`.</span><span class="sxs-lookup"><span data-stu-id="bd8e2-105">The previous behavior of the property was to return `null`.</span></span> <span data-ttu-id="bd8e2-106">Para obtener más información, consulte [Elemento \<AppContextSwitchOverrides>](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).</span><span class="sxs-lookup"><span data-stu-id="bd8e2-106">For more information, see [\<AppContextSwitchOverrides> element](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).</span></span>

<span data-ttu-id="bd8e2-107">En .NET Core, no se admite el modificador `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue`.</span><span class="sxs-lookup"><span data-stu-id="bd8e2-107">In .NET Core, the `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="bd8e2-108">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="bd8e2-108">Version introduced</span></span>

<span data-ttu-id="bd8e2-109">3.0 (versión preliminar 9)</span><span class="sxs-lookup"><span data-stu-id="bd8e2-109">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="bd8e2-110">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="bd8e2-110">Recommended action</span></span>

<span data-ttu-id="bd8e2-111">Quite el modificador.</span><span class="sxs-lookup"><span data-stu-id="bd8e2-111">Remove the switch.</span></span> <span data-ttu-id="bd8e2-112">No se admite el modificador y no hay ninguna funcionalidad alternativa disponible.</span><span class="sxs-lookup"><span data-stu-id="bd8e2-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="bd8e2-113">Categoría</span><span class="sxs-lookup"><span data-stu-id="bd8e2-113">Category</span></span>

<span data-ttu-id="bd8e2-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bd8e2-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="bd8e2-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="bd8e2-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `P:System.Windows.Forms.ContextMenuStrip.SourceControl`

-->
