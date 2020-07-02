---
ms.openlocfilehash: 60937459b6f18e9abae87ad2dc97c3942325eedc
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620596"
---
### <a name="winrt-stream-adapters-no-long-call-flushasync-automatically-on-close"></a>Los adaptadores de flujo de WinRT no llaman a FlushAsync de manera automática al cerrarse

#### <a name="details"></a>Detalles

En las aplicaciones de Microsoft Store, los adaptadores de secuencia de Windows Runtime ya no llaman al método FlushAsync desde el método Dispose.

#### <a name="suggestion"></a>Sugerencia

Este cambio debe ser transparente. Los desarrolladores pueden restaurar el comportamiento anterior escribiendo código similar al siguiente:<pre><code class="lang-csharp">using (var stream = GetWindowsRuntimeStream() as Stream)&#13;&#10;{&#13;&#10;// do something&#13;&#10;await stream.FlushAsync();&#13;&#10;}&#13;&#10;</code></pre>

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Transparente|
|Versión|4.5.1|
|Tipo|Tiempo de ejecución|
