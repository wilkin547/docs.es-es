---
ms.openlocfilehash: c64431fd651fd7d53fb46231c6acc10c5cb43fff
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606266"
---
### <a name="winforms-domain-upbutton-and-downbutton-actions-are-in-sync-now"></a>Las acciones upbutton y downbutton de Domain de WinForm ahora están sincronizadas

#### <a name="details"></a>Detalles

En .NET Framework 4.7.1 y versiones anteriores, se omite la acción <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> del control <xref:System.Windows.Forms.DomainUpDown> cuando el texto del control está presente y el desarrollador tiene que usar la acción <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> en el control antes de usar la acción <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>. A partir de .NET Framework 4.7.2, las acciones <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> y <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> funcionan de manera independiente en este escenario y permanecen sincronizadas.

#### <a name="suggestion"></a>Sugerencia

Para que una aplicación se beneficie de estos cambios, se debe ejecutar en .NET Framework 4.7.2 o una versión posterior. La aplicación se puede beneficiar de estos cambios de cualquiera de las maneras siguientes:

- Se recompila para tener .NET Framework 4.7.2 como destino. Este cambio está habilitado de forma predeterminada para las aplicaciones de Windows Forms destinadas a .NET Framework 4.7.2 o una versión posterior.
- No participa en el comportamiento de desplazamiento heredado mediante la adición del [modificador de AppContext](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) a la sección `<runtime>` del archivo app.config y estableciéndolo en `false`, como se muestra en el ejemplo siguiente.

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Borde        |
| Versión | 4.7.2       |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>
