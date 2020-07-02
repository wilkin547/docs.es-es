---
ms.openlocfilehash: ccdf232d743c9e270b6ed21f698998eb95a97399
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621385"
---
### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a>El valor predeterminado de MsmqSecureHashAlgorithm de WCF ahora es SHA256

#### <a name="details"></a>Detalles

A partir de .NET Framework 4.7.1, el algoritmo de firma de mensajes predeterminado de WCF para los mensajes de Msmq es SHA256. En .NET Framework 4.7 y versiones anteriores, el algoritmo de firma de mensajes predeterminado es SHA1.

#### <a name="suggestion"></a>Sugerencia

Si tiene problemas de compatibilidad con este cambio en .NET Framework 4.7.1 o una versión posterior, puede excluirlo mediante la adición de la línea siguiente a la sección <code>&lt;runtime&gt;</code> del archivo app.config:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Secundaria|
|Versión|4.7.1|
|Tipo|Tiempo de ejecución|
