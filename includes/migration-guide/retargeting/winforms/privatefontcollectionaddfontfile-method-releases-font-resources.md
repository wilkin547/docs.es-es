---
ms.openlocfilehash: 6ee290f6722480778381376f588e16877894f232
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606946"
---
### <a name="privatefontcollectionaddfontfile-method-releases-font-resources"></a>El método PrivateFontCollection.AddFontFile libera los recursos de fuente

#### <a name="details"></a>Detalles

En .NET Framework 4.7.1 y versiones anteriores, la clase <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> no libera los recursos de fuentes GDI+ después de que se elimine <xref:System.Drawing.Text.PrivateFontCollection> para los objetos <xref:System.Drawing.Font> que se agregaron a esta colección con el método <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)>. En .NET Framework 4.7.2 y versiones posteriores, <xref:System.Drawing.Text.FontCollection.Dispose%2A> libera las fuentes GDI+ que se agregaron a la colección como archivos.

#### <a name="suggestion"></a>Sugerencia

**Cómo participar o no en estos cambios** Para que una aplicación se beneficie de estos cambios, se debe ejecutar en .NET Framework 4.7.2 o una versión posterior. La aplicación se puede beneficiar de estos cambios de cualquiera de las maneras siguientes:

- Se recompila para tener .NET Framework 4.7.2 como destino. Este cambio está habilitado de forma predeterminada para las aplicaciones de Windows Forms destinadas a .NET Framework 4.7.2 o una versión posterior.
- Tiene como destino .NET Framework 4.7.1 o una versión anterior, y no participa en los comportamientos de accesibilidad heredados mediante la adición del [modificador de AppContext](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) siguiente a la sección `<runtime>` del archivo app.config y estableciéndolo en `false`, como se muestra en el ejemplo siguiente.

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Drawing.Text.DoNotRemoveGdiFontsResourcesFromFontCollection=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

En las aplicaciones destinadas a .NET Framework 4.7.2 o una versión posterior, y en las que se quiere conservar el comportamiento heredado, se puede participar en no liberar los recursos de fuente si se establece explícitamente este modificador de AppContext en `true`.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Borde        |
| Versión | 4.7.2       |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)?displayProperty=nameWithType>
- <xref:System.Drawing.Text.FontCollection.Dispose?displayProperty=nameWithType>
