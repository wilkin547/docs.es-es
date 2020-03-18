---
ms.openlocfilehash: 73096e5f61e5257e062df9743cae0f5464892357
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804584"
---
### <a name="wpf-layout-rounding-of-margins-has-changed"></a>Ha cambiado el redondeo del diseño de márgenes en WPF

|   |   |
|---|---|
|Detalles|Ha cambiado la manera en la que se redondean los márgenes, así como los bordes y el fondo de estos. Debido a este cambio:<ul><li>El ancho o alto de los elementos puede aumentar o disminuir un píxel como máximo.</li><li>La posición de un objeto se puede mover un píxel como máximo.</li><li>Los elementos centrados pueden estar descentrados como máximo en un píxel en vertical o en horizontal.</li></ul>De forma predeterminada, este nuevo diseño solo está habilitado para las aplicaciones que tienen como destino .NET Framework 4.6.|
|Sugerencia|Dado que esta modificación tiende a eliminar el recorte de la parte derecha o inferior de los controles WPF en PPP altos, las aplicaciones destinadas a versiones anteriores de .NET Framework que se ejecutan en .NET Framework 4.6 pueden optar por este nuevo comportamiento agregando la siguiente línea a la sección <code>&lt;runtime&gt;</code> del archivo app.config:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false&quot; /&gt;&#39;&#13;&#10;</code></pre>Las aplicaciones que tienen como destino .NET Framework 4.6 pero que quieren que los controles de WPF se representen con el algoritmo de diseño anterior pueden hacerlo mediante la adición de la línea siguiente a la sección <code>&lt;runtime&gt;</code> del archivo app.config:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true&quot; /&gt;&#39;.&#13;&#10;</code></pre>|
|Ámbito|Secundaria|
|Versión|4.6|
|Tipo|Redestinación|
