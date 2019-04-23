---
ms.openlocfilehash: ce8e162e11802de1b06bfbc63d5c55de67ef23df
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59805129"
---
### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a><span data-ttu-id="aed73-101">El valor predeterminado de MsmqSecureHashAlgorithm de WCF ahora es SHA256</span><span class="sxs-lookup"><span data-stu-id="aed73-101">WCF MsmqSecureHashAlgorithm default value is now SHA256</span></span>

|   |   |
|---|---|
|<span data-ttu-id="aed73-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="aed73-102">Details</span></span>|<span data-ttu-id="aed73-103">A partir de .NET Framework 4.7.1, el algoritmo de firma de mensajes predeterminado de WCF para los mensajes de Msmq es SHA256.</span><span class="sxs-lookup"><span data-stu-id="aed73-103">Starting with the .NET Framework 4.7.1, the default message signing algorithm in WCF for Msmq messages is SHA256.</span></span> <span data-ttu-id="aed73-104">En .NET Framework 4.7 y versiones anteriores, el algoritmo de firma de mensajes predeterminado es SHA1.</span><span class="sxs-lookup"><span data-stu-id="aed73-104">In the .NET Framework 4.7 and earlier versions, the default message signing algorithm is SHA1.</span></span>|
|<span data-ttu-id="aed73-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="aed73-105">Suggestion</span></span>|<span data-ttu-id="aed73-106">Si tiene problemas de compatibilidad con este cambio en .NET Framework 4.7.1 o una versión posterior, puede excluirlo mediante la adición de la línea siguiente a la sección <code>&lt;runtime&gt;</code> del archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="aed73-106">If you run into compatibility issues with this change on the .NET Framework 4.7.1 or later, you can opt-out the change by adding the following line to the <code>&lt;runtime&gt;</code>section of your app.config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="aed73-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="aed73-107">Scope</span></span>|<span data-ttu-id="aed73-108">Secundaria</span><span class="sxs-lookup"><span data-stu-id="aed73-108">Minor</span></span>|
|<span data-ttu-id="aed73-109">Versión</span><span class="sxs-lookup"><span data-stu-id="aed73-109">Version</span></span>|<span data-ttu-id="aed73-110">4.7.1</span><span class="sxs-lookup"><span data-stu-id="aed73-110">4.7.1</span></span>|
|<span data-ttu-id="aed73-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="aed73-111">Type</span></span>|<span data-ttu-id="aed73-112">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="aed73-112">Runtime</span></span>|
