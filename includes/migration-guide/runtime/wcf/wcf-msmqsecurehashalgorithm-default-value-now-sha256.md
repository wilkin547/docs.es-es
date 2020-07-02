---
ms.openlocfilehash: ccdf232d743c9e270b6ed21f698998eb95a97399
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621385"
---
### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a><span data-ttu-id="57ca3-101">El valor predeterminado de MsmqSecureHashAlgorithm de WCF ahora es SHA256</span><span class="sxs-lookup"><span data-stu-id="57ca3-101">WCF MsmqSecureHashAlgorithm default value is now SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="57ca3-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="57ca3-102">Details</span></span>

<span data-ttu-id="57ca3-103">A partir de .NET Framework 4.7.1, el algoritmo de firma de mensajes predeterminado de WCF para los mensajes de Msmq es SHA256.</span><span class="sxs-lookup"><span data-stu-id="57ca3-103">Starting with the .NET Framework 4.7.1, the default message signing algorithm in WCF for Msmq messages is SHA256.</span></span> <span data-ttu-id="57ca3-104">En .NET Framework 4.7 y versiones anteriores, el algoritmo de firma de mensajes predeterminado es SHA1.</span><span class="sxs-lookup"><span data-stu-id="57ca3-104">In the .NET Framework 4.7 and earlier versions, the default message signing algorithm is SHA1.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="57ca3-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="57ca3-105">Suggestion</span></span>

<span data-ttu-id="57ca3-106">Si tiene problemas de compatibilidad con este cambio en .NET Framework 4.7.1 o una versión posterior, puede excluirlo mediante la adición de la línea siguiente a la sección <code>&lt;runtime&gt;</code> del archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="57ca3-106">If you run into compatibility issues with this change on the .NET Framework 4.7.1 or later, you can opt-out the change by adding the following line to the <code>&lt;runtime&gt;</code>section of your app.config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="57ca3-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="57ca3-107">Name</span></span>    | <span data-ttu-id="57ca3-108">Valor</span><span class="sxs-lookup"><span data-stu-id="57ca3-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="57ca3-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="57ca3-109">Scope</span></span>   |<span data-ttu-id="57ca3-110">Secundaria</span><span class="sxs-lookup"><span data-stu-id="57ca3-110">Minor</span></span>|
|<span data-ttu-id="57ca3-111">Versión</span><span class="sxs-lookup"><span data-stu-id="57ca3-111">Version</span></span>|<span data-ttu-id="57ca3-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="57ca3-112">4.7.1</span></span>|
|<span data-ttu-id="57ca3-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="57ca3-113">Type</span></span>|<span data-ttu-id="57ca3-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="57ca3-114">Runtime</span></span>|
