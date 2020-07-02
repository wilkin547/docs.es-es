---
ms.openlocfilehash: 9b734fe960165b6d4b97b861cb3e8f31979f25c5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621382"
---
### <a name="remove-ssl3-from-the-wcf-transportdefaults"></a><span data-ttu-id="d610f-101">Se quita Ssl3 de TransportDefaults de WCF</span><span class="sxs-lookup"><span data-stu-id="d610f-101">Remove Ssl3 from the WCF TransportDefaults</span></span>

#### <a name="details"></a><span data-ttu-id="d610f-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="d610f-102">Details</span></span>

<span data-ttu-id="d610f-103">Al usar NetTcp con seguridad de transporte y un tipo de credencial de certificado, el protocolo SSL 3 ya no es el protocolo predeterminado para negociar una conexión segura.</span><span class="sxs-lookup"><span data-stu-id="d610f-103">When using NetTcp with transport security and a credential type of certificate, the SSL 3 protocol is no longer a default protocol used for negotiating a secure connection.</span></span> <span data-ttu-id="d610f-104">En la mayoría de los casos no debería afectar a las aplicaciones existentes, porque TLS 1.0 siempre se ha incluido en la lista de protocolos para NetTcp.</span><span class="sxs-lookup"><span data-stu-id="d610f-104">In most cases there should be no impact to existing apps as TLS 1.0 has always been included in the protocol list for NetTcp.</span></span> <span data-ttu-id="d610f-105">Todos los clientes deberían poder negociar una conexión usando como mínimo TLS1.0.</span><span class="sxs-lookup"><span data-stu-id="d610f-105">All existing clients should be able to negotiate a connection using at least TLS1.0.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d610f-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="d610f-106">Suggestion</span></span>

<span data-ttu-id="d610f-107">Si se requiere Ssl3, use uno de los mecanismos de configuración siguientes para agregarlo a la lista de protocolos negociados.</span><span class="sxs-lookup"><span data-stu-id="d610f-107">If Ssl3 is required, use one of the following configuration mechanisms to add Ssl3 to the list of negotiated protocols.</span></span><ul><li><xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols></li><li><xref:System.ServiceModel.TcpTransportSecurity.SslProtocols></li><li>[<](~/docs/framework/configure-apps/file-schema/wcf/transport-of-nettcpbinding.md)</li><li><span data-ttu-id="d610f-108">[sección &lt;sslStreamSecurity&gt; de &lt;customBinding&gt;]~/docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)</span><span class="sxs-lookup"><span data-stu-id="d610f-108">[&lt;sslStreamSecurity&gt; section of &lt;customBinding&gt;]~/docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)</span></span></li></ul>

| <span data-ttu-id="d610f-109">Nombre</span><span class="sxs-lookup"><span data-stu-id="d610f-109">Name</span></span>    | <span data-ttu-id="d610f-110">Valor</span><span class="sxs-lookup"><span data-stu-id="d610f-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d610f-111">Ámbito</span><span class="sxs-lookup"><span data-stu-id="d610f-111">Scope</span></span>   |<span data-ttu-id="d610f-112">Borde</span><span class="sxs-lookup"><span data-stu-id="d610f-112">Edge</span></span>|
|<span data-ttu-id="d610f-113">Versión</span><span class="sxs-lookup"><span data-stu-id="d610f-113">Version</span></span>|<span data-ttu-id="d610f-114">4.6.2</span><span class="sxs-lookup"><span data-stu-id="d610f-114">4.6.2</span></span>|
|<span data-ttu-id="d610f-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="d610f-115">Type</span></span>|<span data-ttu-id="d610f-116">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="d610f-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d610f-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="d610f-117">Affected APIs</span></span>

-<xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols?displayProperty=nameWithType></li><li><xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType></li></ul>|
