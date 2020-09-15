---
ms.openlocfilehash: eb89cbc72d8b09fd1aa5bc775a6c539eb208fa70
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614897"
---
### <a name="wpf-pointer-based-touch-stack"></a>Pila táctil basada en punteros de WPF

#### <a name="details"></a>Detalles

Este cambio agrega la posibilidad de habilitar una pila táctil o de lápiz de WPF opcional basada en WM_POINTER.  Los desarrolladores que no lo habiliten explícitamente no deberían ver ningún cambio en el comportamiento del lápiz o la entrada táctil de WPF. Problemas conocidos actuales con la pila táctil o de lápiz opcional basada en WM_POINTER:

- No se admiten las entradas manuscritas en tiempo real.
- Aunque los complementos de lápiz y entrada manuscrita seguirán funcionando, se procesarán en el subproceso de la interfaz de usuario, lo que puede provocar un rendimiento deficiente.
- El comportamiento cambia debido a las modificaciones en la promoción de los eventos de lápiz o de entrada táctil a los eventos de mouse.
- Es posible que la manipulación se comporte de otra forma.
- Arrastrar y colocar no mostrará la información adecuada para la entrada táctil.
- Esto no afecta a la entrada de lápiz.
- Arrastrar y colocar ya no se puede iniciar en los eventos de lápiz o entrada táctil.
- Esto puede hacer que la aplicación de detenga hasta que se detecte la entrada del mouse.
- En su lugar, los desarrolladores deben iniciar Arrastrar y colocar en los eventos del mouse.

#### <a name="suggestion"></a>Sugerencia

Los desarrolladores que quieran habilitar esta pila pueden agregar o combinar lo siguiente en el archivo App.config de la aplicación:

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Input.Stylus.EnablePointerSupport=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

Si se elimina esto o el valor se establece en false, esta pila opcional se desactivará. Tenga en cuenta que esta pila solo está disponible en Windows 10 Creators Update y versiones posteriores.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Borde        |
| Versión | 4.7         |
| Tipo    | Redestinación |
