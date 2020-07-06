---
ms.openlocfilehash: 0ef39d67cd4335658658f5772b5bce49d827cad0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614939"
---
### <a name="selector-selectionchanged-event-and-selectedvalue-property"></a><span data-ttu-id="1b5f4-101">Evento SelectionChanged y propiedad SelectedValue de Selector</span><span class="sxs-lookup"><span data-stu-id="1b5f4-101">Selector SelectionChanged event and SelectedValue property</span></span>

#### <a name="details"></a><span data-ttu-id="1b5f4-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="1b5f4-102">Details</span></span>

<span data-ttu-id="1b5f4-103">A partir de .NET Framework 4.7.1, un <xref:System.Windows.Controls.Primitives.Selector> siempre actualiza el valor de su propiedad <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> antes de generar el evento <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> cuando cambia su selección.</span><span class="sxs-lookup"><span data-stu-id="1b5f4-103">Starting with the .NET Framework 4.7.1, a <xref:System.Windows.Controls.Primitives.Selector> always updates the value of its <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> property before raising the <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event, when its selection changes.</span></span> <span data-ttu-id="1b5f4-104">Esto hace que la propiedad SelectedValue sea coherente con las demás propiedades de selección (<xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A> y <xref:System.Windows.Controls.Primitives.Selector.SelectedIndex%2A>), que se actualizan antes de que se genere el evento.</span><span class="sxs-lookup"><span data-stu-id="1b5f4-104">This makes the SelectedValue property consistent with the other selection properties (<xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A> and <xref:System.Windows.Controls.Primitives.Selector.SelectedIndex%2A>), which are updated before raising the event.</span></span><p/><span data-ttu-id="1b5f4-105">En .NET Framework 4.7 y versiones anteriores, la actualización de SelectedValue se realizaba antes que el evento en la mayoría de los casos, pero se producía después del evento si el cambio de selección se debía al cambio de la propiedad <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="1b5f4-105">In the .NET Framework 4.7 and earlier versions, the update to SelectedValue happened before the event in most cases, but it happened after the event if the selection change was caused by changing the <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> property.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1b5f4-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="1b5f4-106">Suggestion</span></span>

<span data-ttu-id="1b5f4-107">Las aplicaciones que tienen como destino .NET Framework 4.7.1 o una versión posterior pueden rechazar este cambio y usar el comportamiento heredado si se agrega lo siguiente a la sección `<runtime>` del archivo de configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="1b5f4-107">Apps that target the .NET Framework 4.7.1 or later can opt out of this change and use legacy behavior by adding the following to the `<runtime>` section of the application configuration file:</span></span>

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

<span data-ttu-id="1b5f4-108">Las aplicaciones que tienen como destino .NET Framework 4.7 o versiones anteriores, pero que se ejecutan en .NET Framework 4.7.1 o versiones posteriores, pueden habilitar el comportamiento nuevo si se agrega la línea siguiente a la sección `<runtime>` del archivo .configuration de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="1b5f4-108">Apps that target the .NET Framework 4.7 or earlier but are running on the .NET Framework 4.7.1 or later can enable the new behavior by adding the following line to the `<runtime>` section of the application .configuration file:</span></span>

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="1b5f4-109">Nombre</span><span class="sxs-lookup"><span data-stu-id="1b5f4-109">Name</span></span>    | <span data-ttu-id="1b5f4-110">Valor</span><span class="sxs-lookup"><span data-stu-id="1b5f4-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1b5f4-111">Ámbito</span><span class="sxs-lookup"><span data-stu-id="1b5f4-111">Scope</span></span>   | <span data-ttu-id="1b5f4-112">Secundaria</span><span class="sxs-lookup"><span data-stu-id="1b5f4-112">Minor</span></span>       |
| <span data-ttu-id="1b5f4-113">Versión</span><span class="sxs-lookup"><span data-stu-id="1b5f4-113">Version</span></span> | <span data-ttu-id="1b5f4-114">4.7.1</span><span class="sxs-lookup"><span data-stu-id="1b5f4-114">4.7.1</span></span>       |
| <span data-ttu-id="1b5f4-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="1b5f4-115">Type</span></span>    | <span data-ttu-id="1b5f4-116">Redestinación</span><span class="sxs-lookup"><span data-stu-id="1b5f4-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="1b5f4-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="1b5f4-117">Affected APIs</span></span>

- <xref:System.Windows.Controls.TabControl.SelectedContent?displayProperty=nameWithType>
- <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged?displayProperty=nameWithType>
