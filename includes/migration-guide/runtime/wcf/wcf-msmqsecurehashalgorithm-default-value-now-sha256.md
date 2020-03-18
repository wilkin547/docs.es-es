---
ms.openlocfilehash: ce8e162e11802de1b06bfbc63d5c55de67ef23df
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "67857272"
---
### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a>El valor predeterminado de MsmqSecureHashAlgorithm de WCF ahora es SHA256

|   |   |
|---|---|
|Detalles|A partir de .NET Framework 4.7.1, el algoritmo de firma de mensajes predeterminado de WCF para los mensajes de Msmq es SHA256. En .NET Framework 4.7 y versiones anteriores, el algoritmo de firma de mensajes predeterminado es SHA1.|
|Sugerencia|Si tiene problemas de compatibilidad con este cambio en .NET Framework 4.7.1 o una versión posterior, puede excluirlo mediante la adición de la línea siguiente a la sección <code>&lt;runtime&gt;</code> del archivo app.config:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Ámbito|Secundaria|
|Versión|4.7.1|
|Tipo|Tiempo de ejecución|
