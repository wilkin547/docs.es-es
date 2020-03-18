---
ms.openlocfilehash: e6c93a1bc31c041f36fca3704bca32012a2b42ac
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859018"
---
### <a name="selector-selectionchanged-event-and-selectedvalue-property"></a>Evento SelectionChanged y propiedad SelectedValue de Selector

|   |   |
|---|---|
|Detalles|A partir de .NET Framework 4.7.1, un <xref:System.Windows.Controls.Primitives.Selector> siempre actualiza el valor de su propiedad <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> antes de generar el evento <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> cuando cambia su selección. Esto hace que la propiedad SelectedValue sea coherente con las demás propiedades de selección (<xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A> y <xref:System.Windows.Controls.Primitives.Selector.SelectedIndex%2A>), que se actualizan antes de que se genere el evento.<p/>En .NET Framework 4.7 y versiones anteriores, la actualización de SelectedValue se realizaba antes que el evento en la mayoría de los casos, pero se producía después del evento si el cambio de selección se debía al cambio de la propiedad <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A>.|
|Sugerencia|Las aplicaciones que tienen como destino .NET Framework 4.7.1 o una versión posterior pueden rechazar este cambio y usar el comportamiento heredado si se agrega lo siguiente a la sección <code>&lt;runtime&gt;</code> del archivo de configuración de la aplicación:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Las aplicaciones que tienen como destino .NET Framework 4.7 o versiones anteriores, pero que se ejecutan en .NET Framework 4.7.1 o versiones posteriores, pueden habilitar el comportamiento nuevo si se agrega la línea siguiente a la sección <code>&lt;runtime&gt;</code> del archivo .configuration de la aplicación:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Ámbito|Secundaria|
|Versión|4.7.1|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.Windows.Controls.TabControl.SelectedContent?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.Primitives.Selector.SelectionChanged?displayProperty=nameWithType></li></ul>|
