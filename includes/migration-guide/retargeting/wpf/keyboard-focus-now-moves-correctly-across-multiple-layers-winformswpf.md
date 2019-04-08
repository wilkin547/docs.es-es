---
ms.openlocfilehash: ae110d915241fe85453667e895ab54288302c20d
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760896"
---
### <a name="keyboard-focus-now-moves-correctly-across-multiple-layers-of-winformswpf-hosting"></a>El foco del teclado se mueve ahora correctamente entre varios niveles de hospedaje de WinForms y WPF

|   |   |
|---|---|
|Detalles|Suponga que una aplicación de WPF hospeda un control de WinForms que, a su vez, hospeda controles de WPF. Es posible que los usuarios no puedan presionar Tab para salir de la capa de WinForms si el primer control o el último de esa capa es <code>System.Windows.Forms.Integration.ElementHost</code> de WPF. Este cambio soluciona este problema y los usuarios ahora pueden presionar Tab para salir de la capa de WinForms. Las aplicaciones automatizadas que se basan en que el foco no escape nunca de la capa de WinForms ya no funcionarán según lo previsto.|
|Sugerencia|Un desarrollador que quiera usar este cambio mientras selecciona como destino una versión de la plataforma inferior a .NET Framework 4.7.2 puede establecer en false el conjunto siguiente de marcas de AppContext para habilitar el cambio.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>Las aplicaciones de WPF deben participar en todas las mejoras de accesibilidad anteriores para obtener las mejoras siguientes. En otras palabras, se deben establecer los modificadores <code>Switch.UseLegacyAccessibilityFeatures</code> y <code>Switch.UseLegacyAccessibilityFeatures.2</code>. Un desarrollador que requiera la funcionalidad anterior mientras selecciona como destino .NET Framework 4.7.2 o una versión posterior puede establecer en true la marca de AppContext siguiente para deshabilitar el cambio.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures.2=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Ámbito|Borde|
|Versión|4.7.2|
|Tipo|Redestinación|

