---
ms.openlocfilehash: 4bc8db52efdfe483acb4f6b6e33c4fa7716e0b79
ms.sourcegitcommit: 261e0c98a111357692b3b63c596edf0cacf72991
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2020
ms.locfileid: "90770833"
---
### <a name="svctraceviewer-combobox-high-contrast-change"></a>Cambio de contraste alto de ComboBox svcTraceViewer

#### <a name="details"></a>Detalles

En la [herramienta Service Trace Viewer de Microsoft](~/docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md), los controles ComboBox no se mostraban en el color correcto en ciertos temas de contraste alto. El problema se ha corregido en .NET Framework 4.7.2. Sin embargo, debido a los requisitos de compatibilidad con versiones anteriores del SDK de .NET Framework, la corrección no era visible para los clientes de forma predeterminada. .NET 4.8 manifiesta este cambio agregando los siguientes [modificadores de configuración AppContext](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) al archivo svcTraceViewer.exe.config:

```xml
<AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
```

#### <a name="suggestion"></a>Sugerencia

Si no quiere que se produzca el cambio de comportamiento de contraste alto, puede deshabilitarlo mediante la eliminación de la siguiente sección del archivo svcTraceViewer.exe.config:

```xml
<AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
```

| NOMBRE    | Valor   |
|:--------|:--------|
| Ámbito   | Borde    |
| Versión | 4.8     |
| Tipo    | Tiempo de ejecución |

#### <a name="affected-apis"></a>API afectadas

No detectable a través del análisis de la API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
