---
ms.openlocfilehash: 9baca45de1c8994f610815e84fdee8ba3930eb04
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496640"
---
### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a><span data-ttu-id="fdb67-101">El valor predeterminado de MsmqSecureHashAlgorithm de WCF ahora es SHA256</span><span class="sxs-lookup"><span data-stu-id="fdb67-101">WCF MsmqSecureHashAlgorithm default value is now SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="fdb67-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="fdb67-102">Details</span></span>

<span data-ttu-id="fdb67-103">A partir de .NET Framework 4.7.1, el algoritmo de firma de mensajes predeterminado de WCF para los mensajes de Msmq es SHA256.</span><span class="sxs-lookup"><span data-stu-id="fdb67-103">Starting with the .NET Framework 4.7.1, the default message signing algorithm in WCF for Msmq messages is SHA256.</span></span> <span data-ttu-id="fdb67-104">En .NET Framework 4.7 y versiones anteriores, el algoritmo de firma de mensajes predeterminado es SHA1.</span><span class="sxs-lookup"><span data-stu-id="fdb67-104">In the .NET Framework 4.7 and earlier versions, the default message signing algorithm is SHA1.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="fdb67-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="fdb67-105">Suggestion</span></span>

<span data-ttu-id="fdb67-106">Si tiene problemas de compatibilidad con este cambio en .NET Framework 4.7.1 o una versión posterior, puede excluirlo mediante la adición de la línea siguiente a la sección <code>&lt;runtime&gt;</code> del archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="fdb67-106">If you run into compatibility issues with this change on the .NET Framework 4.7.1 or later, you can opt-out the change by adding the following line to the <code>&lt;runtime&gt;</code>section of your app.config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="fdb67-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="fdb67-107">Name</span></span>    | <span data-ttu-id="fdb67-108">Valor</span><span class="sxs-lookup"><span data-stu-id="fdb67-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="fdb67-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="fdb67-109">Scope</span></span>   |<span data-ttu-id="fdb67-110">Secundaria</span><span class="sxs-lookup"><span data-stu-id="fdb67-110">Minor</span></span>|
|<span data-ttu-id="fdb67-111">Versión</span><span class="sxs-lookup"><span data-stu-id="fdb67-111">Version</span></span>|<span data-ttu-id="fdb67-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="fdb67-112">4.7.1</span></span>|
|<span data-ttu-id="fdb67-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="fdb67-113">Type</span></span>|<span data-ttu-id="fdb67-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="fdb67-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="fdb67-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="fdb67-115">Affected APIs</span></span>

<span data-ttu-id="fdb67-116">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="fdb67-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
