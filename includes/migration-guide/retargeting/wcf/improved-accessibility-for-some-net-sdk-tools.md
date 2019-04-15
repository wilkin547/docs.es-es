---
ms.openlocfilehash: 0b087fca59d60a086a9ea8b2bb19c09f646c3dfd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236561"
---
### <a name="improved-accessibility-for-some-net-sdk-tools"></a>Mejor accesibilidad para algunas herramientas del SDK de .NET

|   |   |
|---|---|
|Detalles|En el SDK de .NET Framework 4.7.1, se han mejorado las herramientas SvcConfigEditor.exe y SvcTraceViewer.exe mediante la corrección de varios problemas de accesibilidad. La mayoría eran problemas menores como un nombre sin definir o determinados patrones de automatización de la interfaz de usuario que no se implementaban correctamente. Aunque muchos usuarios no eran conscientes de estos valores incorrectos, los clientes que usan tecnologías de asistencia como lectores de pantalla encontrarán estas herramientas del SDK más accesibles. De hecho, estas correcciones cambian algunos comportamientos anteriores, como el orden del foco del teclado. Para obtener todas las correcciones de accesibilidad en estas herramientas, puede agregar lo siguiente al archivo app.config:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Ámbito|Borde|
|Versión|4.7.1|
|Tipo|Redestinación|
