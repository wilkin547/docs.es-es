---
ms.openlocfilehash: 77e231f8ef1dde8a263b8622311099a4a404062d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606724"
---
### <a name="hwndhost-now-correctly-resizes-child-hwnd-during-dpi-changes"></a>HwndHost ahora cambia correctamente el tamaño del elemento secundario HWND durante los cambios de PPP

#### <a name="details"></a>Detalles

En .NET Framework 4.7.2 y versiones anteriores, cuando WPF se ejecutaba en modo de reconocimiento por monitor, los controles hospedados en <xref:System.Windows.Interop.HwndHost> no tenían el tamaño correcto después de realizar cambios de PPP, como al mover las aplicaciones de un monitor a otro. Esta corrección garantiza que los controles hospedados tienen un tamaño apropiado.

#### <a name="suggestion"></a>Sugerencia

Para que la aplicación se beneficie de estos cambios, se debe ejecutar en .NET Framework 4.7.2 o versiones posteriores y debe participar en este comportamiento estableciendo [AppContext](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) en la sección `<runtime>` del archivo de configuración de aplicación en `false`, tal y como se muestra en el ejemplo siguiente.

<pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.DoNotUsePresentationDpiCapabilityTier2OrGreater=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Major       |
| Versión | 4.8         |
| Tipo    | Redestinación |
