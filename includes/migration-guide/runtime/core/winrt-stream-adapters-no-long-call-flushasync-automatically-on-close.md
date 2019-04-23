---
ms.openlocfilehash: 60759e3d03137bb5983703cbf04719ba4946cb6e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59805122"
---
### <a name="winrt-stream-adapters-no-long-call-flushasync-automatically-on-close"></a>Los adaptadores de flujo de WinRT no llaman a FlushAsync de manera automática al cerrarse

|   |   |
|---|---|
|Detalles|En las aplicaciones de Microsoft Store, los adaptadores de secuencia de Windows Runtime ya no llaman al método FlushAsync desde el método Dispose.|
|Sugerencia|Este cambio debe ser transparente. Los desarrolladores pueden restaurar el comportamiento anterior escribiendo código similar al siguiente:<pre><code class="lang-csharp">using (var stream = GetWindowsRuntimeStream() as Stream)&#13;&#10;{&#13;&#10;// do something&#13;&#10;await stream.FlushAsync();&#13;&#10;}&#13;&#10;</code></pre>|
|Ámbito|Transparente|
|Versión|4.5.1|
|Tipo|Tiempo de ejecución|
