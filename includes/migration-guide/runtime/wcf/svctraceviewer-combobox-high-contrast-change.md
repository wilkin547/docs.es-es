---
ms.openlocfilehash: 06f4186e8f233f5c769dfc5e05d2de5eacd9b053
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622091"
---
### <a name="svctraceviewer-combobox-high-contrast-change"></a>Cambio de contraste alto de ComboBox svcTraceViewer

#### <a name="details"></a>Detalles

En la [herramienta Service Trace Viewer de Microsoft](~/docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md), los controles ComboBox no se mostraban en el color correcto en ciertos temas de contraste alto. El problema se ha corregido en .NET Framework 4.7.2. Sin embargo, debido a los requisitos de compatibilidad con versiones anteriores del SDK de .NET Framework, la corrección no era visible para los clientes de forma predeterminada. .NET 4.8 manifiesta este cambio agregando los siguientes [modificadores de configuración AppContext](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) al archivo svcTraceViewer.exe.config:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot; /&gt;&#13;&#10;</code></pre>

#### <a name="suggestion"></a>Sugerencia

<ul><li>Cómo no participar en el cambio: si no desea que se produzca el cambio de comportamiento de contraste alto, puede deshabilitarlo mediante la eliminación de la siguiente sección del archivo svcTraceViewer.exe.config:</li></ul><pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot; /&gt;&#13;&#10;</code></pre>

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.8|
|Tipo|Tiempo de ejecución|
