---
ms.openlocfilehash: a5f4047d70276a90c9d72918a2559fd795feb26e
ms.sourcegitcommit: 261e0c98a111357692b3b63c596edf0cacf72991
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2020
ms.locfileid: "90770948"
---
### <a name="remove-ssl3-from-the-wcf-transportdefaults"></a><span data-ttu-id="6e0fa-101">Se quita Ssl3 de TransportDefaults de WCF</span><span class="sxs-lookup"><span data-stu-id="6e0fa-101">Remove Ssl3 from the WCF TransportDefaults</span></span>

#### <a name="details"></a><span data-ttu-id="6e0fa-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="6e0fa-102">Details</span></span>

<span data-ttu-id="6e0fa-103">Al usar NetTcp con seguridad de transporte y un tipo de credencial de certificado, el protocolo SSL 3 ya no es el protocolo predeterminado para negociar una conexión segura.</span><span class="sxs-lookup"><span data-stu-id="6e0fa-103">When using NetTcp with transport security and a credential type of certificate, the SSL 3 protocol is no longer a default protocol used for negotiating a secure connection.</span></span> <span data-ttu-id="6e0fa-104">En la mayoría de los casos no debería afectar a las aplicaciones existentes, porque TLS 1.0 siempre se ha incluido en la lista de protocolos para NetTcp.</span><span class="sxs-lookup"><span data-stu-id="6e0fa-104">In most cases there should be no impact to existing apps as TLS 1.0 has always been included in the protocol list for NetTcp.</span></span> <span data-ttu-id="6e0fa-105">Todos los clientes deberían poder negociar una conexión usando como mínimo TLS1.0.</span><span class="sxs-lookup"><span data-stu-id="6e0fa-105">All existing clients should be able to negotiate a connection using at least TLS1.0.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6e0fa-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="6e0fa-106">Suggestion</span></span>

<span data-ttu-id="6e0fa-107">Si se requiere Ssl3, use uno de los mecanismos de configuración siguientes para agregarlo a la lista de protocolos negociados.</span><span class="sxs-lookup"><span data-stu-id="6e0fa-107">If Ssl3 is required, use one of the following configuration mechanisms to add Ssl3 to the list of negotiated protocols.</span></span>

- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols>
- <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols>
- [<span data-ttu-id="6e0fa-108">\<transport> de \<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="6e0fa-108">\<transport> of \<netTcpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-nettcpbinding.md)
- [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)

| <span data-ttu-id="6e0fa-109">Nombre</span><span class="sxs-lookup"><span data-stu-id="6e0fa-109">Name</span></span>    | <span data-ttu-id="6e0fa-110">Valor</span><span class="sxs-lookup"><span data-stu-id="6e0fa-110">Value</span></span>   |
|:--------|:--------|
| <span data-ttu-id="6e0fa-111">Ámbito</span><span class="sxs-lookup"><span data-stu-id="6e0fa-111">Scope</span></span>   | <span data-ttu-id="6e0fa-112">Borde</span><span class="sxs-lookup"><span data-stu-id="6e0fa-112">Edge</span></span>    |
| <span data-ttu-id="6e0fa-113">Versión</span><span class="sxs-lookup"><span data-stu-id="6e0fa-113">Version</span></span> | <span data-ttu-id="6e0fa-114">4.6.2</span><span class="sxs-lookup"><span data-stu-id="6e0fa-114">4.6.2</span></span>   |
| <span data-ttu-id="6e0fa-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="6e0fa-115">Type</span></span>    | <span data-ttu-id="6e0fa-116">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="6e0fa-116">Runtime</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="6e0fa-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="6e0fa-117">Affected APIs</span></span>

- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols?displayProperty=nameWithType>
- <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols`
- `P:System.ServiceModel.TcpTransportSecurity.SslProtocols`

-->
