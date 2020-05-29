---
ms.openlocfilehash: 1e4c0ac1f0f9011f4b8fc136ec2e383d38567355
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83435396"
---
### <a name="resizing-a-grid-can-hang"></a>El cambio de tamaño de una cuadrícula puede dejar de responder

|   |   |
|---|---|
|Detalles|Se puede producir un bucle infinito durante el diseño de un control <code>T:System.Windows.Controls.Grid</code> en las siguientes circunstancias:<ul><li>Las definiciones de fila contienen dos filas \*, que declaran un valor MinHeight y un valor MaxHeight.</li><li>El contenido de las filas \* no supera el valor MaxHeight correspondiente.</li><li>El alto disponible de la cuadrícula se supera con el primer valor MinHeight (más cualquier otra fila fija o automática).</li><li>La aplicación tiene como destino .NET Framework 4.7 o admite el algoritmo de asignación de la versión 4.7 estableciendo <code>Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=false</code>.</li></ul>El bucle también se podría producir con más de dos filas o en el mismo caso para las columnas. El problema se corrigió en .NET Framework 4.7.1.|
|Sugerencia|Actualice a .NET Framework 4.7.1.  Como alternativa, si ya no necesita el algoritmo de asignación de la versión 4.7, puede usar la opción de configuración siguiente:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Ámbito|Borde|
|Versión|4.7|
|Tipo|Tiempo de ejecución|
