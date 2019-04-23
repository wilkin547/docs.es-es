---
ms.openlocfilehash: 3f88c8b80518aa65c082dc3da2d75b5221dd00f0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774096"
---
### <a name="wpf-textboxpasswordbox-text-selection-does-not-follow-system-colors"></a>La selección de texto de TextBox y PasswordBox de WPF no sigue los colores del sistema

|   |   |
|---|---|
|Detalles|En .NET Framework 4.7.1 y versiones anteriores, <code>System.Windows.Controls.TextBox</code> y <code>System.Windows.Controls.PasswordBox</code> de WPF solo podían representar una selección de texto en la capa de adornos. En algunos temas del sistema, esto tapaba el texto, y resultaba difícil de leer.  En .NET Framework 4.7.2 y versiones posteriores, los desarrolladores tienen una opción de habilitar un esquema de representación de la selección que no se basa en los adornos y que alivia este problema.|
|Sugerencia|Un desarrollador que quiera usar este cambio debe establecer correctamente la marca de AppContext siguiente.  Para usar esta característica, la versión instalada de .NET Framework debe ser 4.7.2 o posterior. Para habilitar la selección no basada en los adornos, use la marca de AppContext siguiente.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.Text.UseAdornerForTextboxSelectionRendering=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Ámbito|Borde|
|Versión|4.7.2|
|Tipo|Redestinación|
