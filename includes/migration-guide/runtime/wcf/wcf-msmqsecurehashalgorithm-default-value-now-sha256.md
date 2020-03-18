---
ms.openlocfilehash: ce8e162e11802de1b06bfbc63d5c55de67ef23df
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "67857272"
---
### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a><span data-ttu-id="cf785-101">El valor predeterminado de MsmqSecureHashAlgorithm de WCF ahora es SHA256</span><span class="sxs-lookup"><span data-stu-id="cf785-101">WCF MsmqSecureHashAlgorithm default value is now SHA256</span></span>

|   |   |
|---|---|
|<span data-ttu-id="cf785-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="cf785-102">Details</span></span>|<span data-ttu-id="cf785-103">A partir de .NET Framework 4.7.1, el algoritmo de firma de mensajes predeterminado de WCF para los mensajes de Msmq es SHA256.</span><span class="sxs-lookup"><span data-stu-id="cf785-103">Starting with the .NET Framework 4.7.1, the default message signing algorithm in WCF for Msmq messages is SHA256.</span></span> <span data-ttu-id="cf785-104">En .NET Framework 4.7 y versiones anteriores, el algoritmo de firma de mensajes predeterminado es SHA1.</span><span class="sxs-lookup"><span data-stu-id="cf785-104">In the .NET Framework 4.7 and earlier versions, the default message signing algorithm is SHA1.</span></span>|
|<span data-ttu-id="cf785-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="cf785-105">Suggestion</span></span>|<span data-ttu-id="cf785-106">Si tiene problemas de compatibilidad con este cambio en .NET Framework 4.7.1 o una versión posterior, puede excluirlo mediante la adición de la línea siguiente a la sección <code>&lt;runtime&gt;</code> del archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="cf785-106">If you run into compatibility issues with this change on the .NET Framework 4.7.1 or later, you can opt-out the change by adding the following line to the <code>&lt;runtime&gt;</code>section of your app.config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="cf785-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="cf785-107">Scope</span></span>|<span data-ttu-id="cf785-108">Secundaria</span><span class="sxs-lookup"><span data-stu-id="cf785-108">Minor</span></span>|
|<span data-ttu-id="cf785-109">Versión</span><span class="sxs-lookup"><span data-stu-id="cf785-109">Version</span></span>|<span data-ttu-id="cf785-110">4.7.1</span><span class="sxs-lookup"><span data-stu-id="cf785-110">4.7.1</span></span>|
|<span data-ttu-id="cf785-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="cf785-111">Type</span></span>|<span data-ttu-id="cf785-112">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="cf785-112">Runtime</span></span>|
