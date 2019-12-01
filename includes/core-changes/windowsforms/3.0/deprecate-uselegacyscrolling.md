---
ms.openlocfilehash: 459e7e1f0b5543f069682dadf60668e94b472377
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643866"
---
### <a name="switchsystemwindowsformsdomainupdownuselegacyscrolling-compatibility-switch-not-supported"></a><span data-ttu-id="a1a5c-101">No se admite el modificador de compatibilidad Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling</span><span class="sxs-lookup"><span data-stu-id="a1a5c-101">Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>

<span data-ttu-id="a1a5c-102">El modificador de compatibilidad `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling`, que se introdujo en .NET Framework 4.7.1, no se admite en Windows Forms en .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="a1a5c-102">The `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` compatibility switch, which was introduced in .NET Framework 4.7.1, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="a1a5c-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="a1a5c-103">Change description</span></span>

<span data-ttu-id="a1a5c-104">A partir de .NET Framework 4.7.1, el modificador de compatibilidad `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` permite a los desarrolladores rechazar las acciones independientes de <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> y <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a1a5c-104">Starting with the .NET Framework 4.7.1, the `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` compatibility switch allowed developers to opt-out of independent <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> and <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> actions.</span></span> <span data-ttu-id="a1a5c-105">El modificador restaura el comportamiento heredado, en el que se rechaza la acción <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> si hay texto de contexto, y el desarrollador debe usar la acción <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> en el control antes de la acción <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a1a5c-105">The switch restored the legacy behavior, in which the <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> is ignored if context text is present, and the developer is required to use <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> action on the control before the <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> action.</span></span> <span data-ttu-id="a1a5c-106">Para obtener más información, consulte [Elemento \<AppContextSwitchOverrides>](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).</span><span class="sxs-lookup"><span data-stu-id="a1a5c-106">For more information, see [\<AppContextSwitchOverrides> element](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).</span></span>

<span data-ttu-id="a1a5c-107">En .NET Core, no se admite el modificador `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling`.</span><span class="sxs-lookup"><span data-stu-id="a1a5c-107">In .NET Core, the `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a1a5c-108">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="a1a5c-108">Version introduced</span></span>

<span data-ttu-id="a1a5c-109">3.0 (versión preliminar 9)</span><span class="sxs-lookup"><span data-stu-id="a1a5c-109">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a1a5c-110">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="a1a5c-110">Recommended action</span></span>

<span data-ttu-id="a1a5c-111">Quite el modificador.</span><span class="sxs-lookup"><span data-stu-id="a1a5c-111">Remove the switch.</span></span> <span data-ttu-id="a1a5c-112">No se admite el modificador y no hay ninguna funcionalidad alternativa disponible.</span><span class="sxs-lookup"><span data-stu-id="a1a5c-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="a1a5c-113">Categoría</span><span class="sxs-lookup"><span data-stu-id="a1a5c-113">Category</span></span>

<span data-ttu-id="a1a5c-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a1a5c-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a1a5c-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="a1a5c-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `M:System.Windows.Forms.DomainUpDown.DownButton`
- `M:System.Windows.Forms.DomainUpDown.UpButton`

-->
