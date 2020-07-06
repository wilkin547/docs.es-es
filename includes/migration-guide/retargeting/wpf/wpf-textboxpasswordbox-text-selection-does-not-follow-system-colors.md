---
ms.openlocfilehash: 7c2e80669d9ef27f87cde9442d8eeab0ee31a524
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614981"
---
### <a name="wpf-textboxpasswordbox-text-selection-does-not-follow-system-colors"></a>La selección de texto de TextBox y PasswordBox de WPF no sigue los colores del sistema

#### <a name="details"></a>Detalles

En .NET Framework 4.7.1 y versiones anteriores, `System.Windows.Controls.TextBox` y `System.Windows.Controls.PasswordBox` de WPF solo podían representar una selección de texto en la capa de adornos. En algunos temas del sistema, esto tapaba el texto, y resultaba difícil de leer.  En .NET Framework 4.7.2 y versiones posteriores, los desarrolladores tienen una opción de habilitar un esquema de representación de la selección que no se basa en los adornos y que alivia este problema.

#### <a name="suggestion"></a>Sugerencia

Un desarrollador que quiera usar este cambio debe establecer correctamente la marca de AppContext siguiente.  Para usar esta característica, la versión instalada de .NET Framework debe ser 4.7.2 o posterior. Para habilitar la selección no basada en los adornos, use la marca de AppContext siguiente.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.Text.UseAdornerForTextboxSelectionRendering=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Borde        |
| Versión | 4.7.2       |
| Tipo    | Redestinación |
