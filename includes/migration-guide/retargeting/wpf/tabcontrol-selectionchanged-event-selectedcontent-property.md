---
ms.openlocfilehash: dfdb62e8dd6db67d4fd12aba93928f4615e3f284
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614953"
---
### <a name="tabcontrol-selectionchanged-event-and-selectedcontent-property"></a>Evento SelectionChanged y propiedad SelectedContent de TabControl

#### <a name="details"></a>Detalles

A partir de .NET Framework 4.7.1, un control <xref:System.Windows.Controls.TabControl> actualiza el valor de su propiedad <xref:System.Windows.Controls.TabControl.SelectedContent> antes de generar el evento <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> cuando su selección cambia. En .NET Framework 4.7 y versiones anteriores, la actualización de SelectedContent se producía después del evento.

#### <a name="suggestion"></a>Sugerencia

Las aplicaciones que tienen como destino .NET Framework 4.7.1 o una versión posterior pueden rechazar este cambio y usar el comportamiento heredado si se agrega lo siguiente a la sección `<runtime>` del archivo de configuración de la aplicación:

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

Las aplicaciones que tienen como destino .NET Framework 4.7 o versiones anteriores, pero que se ejecutan en .NET Framework 4.7.1 o versiones posteriores, pueden habilitar el comportamiento nuevo si se agrega la línea siguiente a la sección `<runtime>` del archivo .configuration de la aplicación:

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

| Nombre    | Valor       |
|:--------|:------------|
| Ámbito   | Secundaria       |
| Versión | 4.7.1       |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Windows.Controls.TabControl.SelectedContent?displayProperty=nameWithType>
- <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged?displayProperty=nameWithType>
