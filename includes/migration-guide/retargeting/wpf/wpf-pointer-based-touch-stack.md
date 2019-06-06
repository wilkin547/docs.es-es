---
ms.openlocfilehash: bb3d7c1afa9e506ffc7c6d068c48428d1e66ccb6
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/30/2019
ms.locfileid: "66379442"
---
### <a name="wpf-pointer-based-touch-stack"></a>Pila táctil basada en punteros de WPF

|   |   |
|---|---|
|Detalles|Este cambio agrega la posibilidad de habilitar una pila táctil o de lápiz de WPF opcional basada en WM_POINTER.  Los desarrolladores que no lo habiliten explícitamente no deberían ver ningún cambio en el comportamiento del lápiz o la entrada táctil de WPF. Problemas conocidos actuales con la pila táctil o de lápiz opcional basada en WM_POINTER:<ul><li>No se admiten las entradas manuscritas en tiempo real.</li><li>Aunque los complementos de lápiz y entrada manuscrita seguirán funcionando, se procesarán en el subproceso de la interfaz de usuario, lo que puede provocar un rendimiento deficiente.</li><li>El comportamiento cambia debido a las modificaciones en la promoción de los eventos de lápiz o de entrada táctil a los eventos de mouse.</li><li>Es posible que la manipulación se comporte de otra forma.</li><li>Arrastrar y colocar no mostrará la información adecuada para la entrada táctil.</li><li>Esto no afecta a la entrada de lápiz.</li><li>Arrastrar y colocar ya no se puede iniciar en los eventos de lápiz o entrada táctil.</li><li>Esto puede hacer que la aplicación deje de responder hasta que se detecte la entrada del mouse.</li><li>En su lugar, los desarrolladores deben iniciar Arrastrar y colocar en los eventos del mouse.</li></ul>|
|Sugerencia|Los desarrolladores que quieran habilitar esta pila pueden agregar o combinar lo siguiente en el archivo App.config de la aplicación:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Input.Stylus.EnablePointerSupport=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>Si se elimina esto o el valor se establece en false, esta pila opcional se desactivará. Tenga en cuenta que esta pila solo está disponible en Windows 10 Creators Update y versiones posteriores.|
|Ámbito|Borde|
|Versión|4.7|
|Tipo|Redestinación|
