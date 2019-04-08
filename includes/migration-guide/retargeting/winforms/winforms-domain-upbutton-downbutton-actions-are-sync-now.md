---
ms.openlocfilehash: 7344fddbc61d47d4ca735808f0b92f63e33e15a3
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760868"
---
### <a name="winforms-domain-upbutton-and-downbutton-actions-are-in-sync-now"></a>Las acciones upbutton y downbutton de Domain de WinForm ahora están sincronizadas

|   |   |
|---|---|
|Detalles|En .NET Framework 4.7.1 y versiones anteriores, se omite la acción <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> del control <xref:System.Windows.Forms.DomainUpDown> cuando el texto del control está presente y el desarrollador tiene que usar la acción <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> en el control antes de usar la acción <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>. A partir de .NET Framework 4.7.2, las acciones <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> y <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> funcionan de manera independiente en este escenario y permanecen sincronizadas.|
|Sugerencia|Para que una aplicación se beneficie de estos cambios, se debe ejecutar en .NET Framework 4.7.2 o una versión posterior. La aplicación se puede beneficiar de estos cambios de cualquiera de las maneras siguientes:<ul><li>Se recompila para tener .NET Framework 4.7.2 como destino. Este cambio está habilitado de forma predeterminada para las aplicaciones de Windows Forms destinadas a .NET Framework 4.7.2 o una versión posterior.</li><li>No participa en el comportamiento de desplazamiento heredado mediante la adición del [modificador de AppContext](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) a la sección <code>&lt;runtime&gt;</code> del archivo app.config y estableciéndolo en <code>false</code>, como se muestra en el ejemplo siguiente.</li></ul><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Ámbito|Borde|
|Versión|4.7.2|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType></li><li><xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType></li></ul>|

