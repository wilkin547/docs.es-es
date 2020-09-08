---
ms.openlocfilehash: 8dc1b4d94d01813a8124d1340b50fa78a9b157f8
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497078"
---
### <a name="resizing-a-grid-can-hang"></a>El cambio de tamaño de una cuadrícula puede dejar de responder

#### <a name="details"></a>Detalles

Se puede producir un bucle infinito durante el diseño de un control <code>T:System.Windows.Controls.Grid</code> en las siguientes circunstancias:<ul><li>Las definiciones de fila contienen dos filas \*, que declaran un valor MinHeight y un valor MaxHeight.</li><li>El contenido de las filas \* no supera el valor MaxHeight correspondiente.</li><li>El alto disponible de la cuadrícula se supera con el primer valor MinHeight (más cualquier otra fila fija o automática).</li><li>La aplicación tiene como destino .NET Framework 4.7 o admite el algoritmo de asignación de la versión 4.7 estableciendo <code>Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=false</code>.</li></ul>El bucle también se podría producir con más de dos filas o en el mismo caso para las columnas. El problema se corrigió en .NET Framework 4.7.1.

#### <a name="suggestion"></a>Sugerencia

Actualice a .NET Framework 4.7.1.  Como alternativa, si ya no necesita el algoritmo de asignación de la versión 4.7, puede usar la opción de configuración siguiente:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

| Nombre    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.7|
|Tipo|Tiempo de ejecución|

#### <a name="affected-apis"></a>API afectadas

No detectable a través del análisis de la API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
