---
ms.openlocfilehash: 81b104d8e5a9ccc8e790c3b16e4837cfa0c0def5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859055"
---
### <a name="serialport-background-thread-exceptions"></a>Excepciones de subprocesos en segundo plano SerialPort

|   |   |
|---|---|
|Detalles|Los subprocesos en segundo plano creados con secuencias <xref:System.IO.Ports.SerialPort> ya no finalizan el proceso cuando se inician excepciones del sistema operativo. <br/>En las aplicaciones destinadas a .NET Framework 4.7 y versiones anteriores, un proceso se termina cuando se inicia una excepción del sistema operativo en un subproceso en segundo plano creado con una secuencia <xref:System.IO.Ports.SerialPort>. <br/>En las aplicaciones destinadas a .NET Framework 4.7.1 o una versión posterior, los subprocesos en segundo plano esperan eventos del sistema operativo relacionados con el puerto serie activo y pueden dejar de funcionar en algunos casos, como la eliminación repentina del puerto serie.|
|Sugerencia|Para las aplicaciones que tienen como destino .NET Framework 4.7.1, se puede rechazar el control de excepciones si no es adecuado si se agrega lo siguiente a la sección <code>&lt;runtime&gt;</code> del archivo <code>app.config</code>:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.Ports.DoNotCatchSerialStreamThreadExceptions=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Para las aplicaciones que tienen como destino versiones anteriores de .NET Framework, pero que se ejecutan en .NET Framework 4.7.1 o versiones posteriores, se puede incluir el control de excepciones si se agrega lo siguiente a la sección <code>&lt;runtime&gt;</code> del archivo <code>app.config</code>:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.Ports.DoNotCatchSerialStreamThreadExceptions=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Ámbito|Secundaria|
|Versión|4.7.1|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.IO.Ports.SerialPort?displayProperty=nameWithType></li></ul>|
