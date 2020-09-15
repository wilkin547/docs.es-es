---
ms.openlocfilehash: f907cb1939e111c586d68243e6b8a8e291974e36
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615774"
---
### <a name="wpf-layout-rounding-of-margins-has-changed"></a>Ha cambiado el redondeo del diseño de márgenes en WPF

#### <a name="details"></a>Detalles

Ha cambiado la manera en la que se redondean los márgenes, así como los bordes y el fondo de estos. Debido a este cambio:

- El ancho o alto de los elementos puede aumentar o disminuir un píxel como máximo.
- La posición de un objeto se puede mover un píxel como máximo.
- Los elementos centrados pueden estar descentrados como máximo en un píxel en vertical o en horizontal.
De forma predeterminada, este nuevo diseño solo está habilitado para las aplicaciones que tienen como destino .NET Framework 4.6.

#### <a name="suggestion"></a>Sugerencia

Dado que esta modificación tiende a eliminar el recorte de la parte derecha o inferior de los controles WPF en PPP altos, las aplicaciones destinadas a versiones anteriores de .NET Framework que se ejecutan en .NET Framework 4.6 pueden optar por este nuevo comportamiento agregando la siguiente línea a la sección `<runtime>` del archivo app.config:

<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false&quot; /&gt;&#39;&#13;&#10;</code></pre>

Las aplicaciones que tienen como destino .NET Framework 4.6 pero que quieren que los controles de WPF se representen con el algoritmo de diseño anterior pueden hacerlo mediante la adición de la línea siguiente a la sección `<runtime>` del archivo app.config:

<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true&quot; /&gt;&#39;.&#13;&#10;</code></pre>

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Secundaria       |
| Versión | 4.6         |
| Tipo    | Redestinación |
