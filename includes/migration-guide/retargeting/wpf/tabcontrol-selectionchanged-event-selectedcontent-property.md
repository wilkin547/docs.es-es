---
ms.openlocfilehash: dfdb62e8dd6db67d4fd12aba93928f4615e3f284
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614953"
---
### <a name="tabcontrol-selectionchanged-event-and-selectedcontent-property"></a><span data-ttu-id="389c8-101">Evento SelectionChanged y propiedad SelectedContent de TabControl</span><span class="sxs-lookup"><span data-stu-id="389c8-101">TabControl SelectionChanged event and SelectedContent property</span></span>

#### <a name="details"></a><span data-ttu-id="389c8-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="389c8-102">Details</span></span>

<span data-ttu-id="389c8-103">A partir de .NET Framework 4.7.1, un control <xref:System.Windows.Controls.TabControl> actualiza el valor de su propiedad <xref:System.Windows.Controls.TabControl.SelectedContent> antes de generar el evento <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> cuando su selección cambia. En .NET Framework 4.7 y versiones anteriores, la actualización de SelectedContent se producía después del evento.</span><span class="sxs-lookup"><span data-stu-id="389c8-103">Starting with the .NET Framework 4.7.1, a <xref:System.Windows.Controls.TabControl> updates the value of its <xref:System.Windows.Controls.TabControl.SelectedContent> property before raising the <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event, when its selection changes.In the .NET Framework 4.7 and earlier versions, the update to SelectedContent happened after the event.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="389c8-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="389c8-104">Suggestion</span></span>

<span data-ttu-id="389c8-105">Las aplicaciones que tienen como destino .NET Framework 4.7.1 o una versión posterior pueden rechazar este cambio y usar el comportamiento heredado si se agrega lo siguiente a la sección `<runtime>` del archivo de configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="389c8-105">Apps that target the .NET Framework 4.7.1 or later can opt out of this change and use legacy behavior by adding the following to the `<runtime>` section of the application configuration file:</span></span>

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

<span data-ttu-id="389c8-106">Las aplicaciones que tienen como destino .NET Framework 4.7 o versiones anteriores, pero que se ejecutan en .NET Framework 4.7.1 o versiones posteriores, pueden habilitar el comportamiento nuevo si se agrega la línea siguiente a la sección `<runtime>` del archivo .configuration de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="389c8-106">Apps that target the .NET Framework 4.7 or earlier but are running on the .NET Framework 4.7.1 or later can enable the new behavior by adding the following line to the `<runtime>` section of the application .configuration file:</span></span>

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="389c8-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="389c8-107">Name</span></span>    | <span data-ttu-id="389c8-108">Valor</span><span class="sxs-lookup"><span data-stu-id="389c8-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="389c8-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="389c8-109">Scope</span></span>   | <span data-ttu-id="389c8-110">Secundaria</span><span class="sxs-lookup"><span data-stu-id="389c8-110">Minor</span></span>       |
| <span data-ttu-id="389c8-111">Versión</span><span class="sxs-lookup"><span data-stu-id="389c8-111">Version</span></span> | <span data-ttu-id="389c8-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="389c8-112">4.7.1</span></span>       |
| <span data-ttu-id="389c8-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="389c8-113">Type</span></span>    | <span data-ttu-id="389c8-114">Redestinación</span><span class="sxs-lookup"><span data-stu-id="389c8-114">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="389c8-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="389c8-115">Affected APIs</span></span>

- <xref:System.Windows.Controls.TabControl.SelectedContent?displayProperty=nameWithType>
- <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged?displayProperty=nameWithType>
