---
ms.openlocfilehash: 55c13aa70a03bcc548ce1d096cca8f40de6cda84
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721339"
---
### <a name="dontsupportreentrantfiltermessage-compatibility-switch-not-supported"></a><span data-ttu-id="09198-101">No se admite el modificador de compatibilidad DontSupportReentrantFilterMessage</span><span class="sxs-lookup"><span data-stu-id="09198-101">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>

<span data-ttu-id="09198-102">El modificador de compatibilidad `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage`, que se introdujo en .NET Framework 4.6.1, no se admite en Windows Forms en .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="09198-102">The `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` compatibility switch, which was introduced in .NET Framework 4.6.1, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="09198-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="09198-103">Change description</span></span>

<span data-ttu-id="09198-104">A partir de .NET Framework 4.6.1, el modificador de compatibilidad `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` soluciona las posibles excepciones <xref:System.IndexOutOfRangeException> cuando se llama al mensaje <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> con una implementación personalizada de <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="09198-104">Starting with the .NET Framework 4.6.1, the `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` compatibility switch addresses possible <xref:System.IndexOutOfRangeException> exceptions when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> message is called with a custom <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="09198-105">Para más información, consulte [Mitigación: personalizar implementaciones de IMessageFilter.PreFilterMessage](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).</span><span class="sxs-lookup"><span data-stu-id="09198-105">For more information, see [Mitigation: Custom IMessageFilter.PreFilterMessage Implementations](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).</span></span>

<span data-ttu-id="09198-106">En .NET Core, no se admite el modificador `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage`.</span><span class="sxs-lookup"><span data-stu-id="09198-106">In .NET Core, the `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="09198-107">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="09198-107">Version introduced</span></span>

<span data-ttu-id="09198-108">3.0 (versión preliminar 9)</span><span class="sxs-lookup"><span data-stu-id="09198-108">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="09198-109">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="09198-109">Recommended action</span></span>

<span data-ttu-id="09198-110">Quite el modificador.</span><span class="sxs-lookup"><span data-stu-id="09198-110">Remove the switch.</span></span> <span data-ttu-id="09198-111">No se admite el modificador y no hay ninguna funcionalidad alternativa disponible.</span><span class="sxs-lookup"><span data-stu-id="09198-111">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="09198-112">Categoría</span><span class="sxs-lookup"><span data-stu-id="09198-112">Category</span></span>

<span data-ttu-id="09198-113">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="09198-113">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="09198-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="09198-114">Affected APIs</span></span>

- <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `M:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message)`

-->
