---
ms.openlocfilehash: f1a1eab471d46f018a8e0d0cf787d487cf67c11e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774095"
---
### <a name="contextmenustripsourcecontrol-property-contains-a-valid-control-in-the-case-of-nested-toolstripmenuitems"></a>La propiedad ContextMenuStrip.SourceControl contiene un control válido en el caso de controles ToolStripMenuItem anidados

|   |   |
|---|---|
|Detalles|En .NET Framework 4.7.1 y versiones anteriores, la propiedad <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> devuelve NULL de forma incorrecta cuando el usuario abre el menú desde controles <xref:System.Windows.Forms.ToolStripMenuItem> anidados. En .NET Framework 4.7.2 y versiones posteriores, la propiedad <xref:System.Windows.Forms.ContextMenuStrip.SourceControl> siempre se establece en el control de origen real.|
|Sugerencia|<strong>Cómo participar o no en estos cambios</strong> Para que una aplicación se beneficie de estos cambios, se debe ejecutar en .NET Framework 4.7.2 o una versión posterior. La aplicación se puede beneficiar de estos cambios de cualquiera de las maneras siguientes:<ul><li>Tiene como destino .NET Framework 4.7.2. Este cambio está habilitado de forma predeterminada para las aplicaciones de Windows Forms destinadas a .NET Framework 4.7.2 o una versión posterior.</li><li>Tiene como destino .NET Framework 4.7.1 o una versión anterior, y no participa en los comportamientos de accesibilidad heredados mediante la adición del [modificador de AppContext](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) siguiente a la sección <code>&lt;runtime&gt;</code> del archivo app.config y estableciéndolo en <code>false</code>, como se muestra en el ejemplo siguiente.</li></ul><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>En las aplicaciones destinadas a .NET Framework 4.7.2 o una versión posterior, y en las que se quiere conservar el comportamiento heredado, se puede participar en el uso del valor de control de origen heredado si se establece explícitamente este modificador de AppContext en <code>true</code>.|
|Ámbito|Borde|
|Versión|4.7.2|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType></li></ul>|
