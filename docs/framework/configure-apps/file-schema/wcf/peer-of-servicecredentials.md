---
title: <peer> de <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: b134e21d-e5b5-458e-9309-626dbf8db4ed
ms.openlocfilehash: 50415cb9b35d2a2053efa3313a415de518b7e36e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933773"
---
# <a name="peer-of-servicecredentials"></a><span data-ttu-id="194ad-102">\<> del mismo \<nivel de serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="194ad-102">\<peer> of \<serviceCredentials></span></span>
<span data-ttu-id="194ad-103">Especifica las credenciales actuales de un nodo del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="194ad-103">Specifies the current credentials for a peer node.</span></span>  
  
 <span data-ttu-id="194ad-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="194ad-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="194ad-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="194ad-105">\<behaviors></span></span>  
<span data-ttu-id="194ad-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="194ad-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="194ad-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="194ad-107">\<behavior></span></span>  
<span data-ttu-id="194ad-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="194ad-108">\<serviceCredentials></span></span>  
<span data-ttu-id="194ad-109">\<> del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="194ad-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="194ad-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="194ad-110">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="194ad-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="194ad-111">Attributes and Elements</span></span>  
 <span data-ttu-id="194ad-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="194ad-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="194ad-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="194ad-113">Attributes</span></span>  
 <span data-ttu-id="194ad-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="194ad-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="194ad-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="194ad-115">Child Elements</span></span>  
  
|<span data-ttu-id="194ad-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="194ad-116">Element</span></span>|<span data-ttu-id="194ad-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="194ad-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="194ad-118">\<certificate></span><span class="sxs-lookup"><span data-stu-id="194ad-118">\<certificate></span></span>](certificate-of-peer.md)|<span data-ttu-id="194ad-119">Especifica un certificado X.509 que se va a usar para firmar y cifrar los mensajes para los servicios punto a punto.</span><span class="sxs-lookup"><span data-stu-id="194ad-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer services.</span></span> <span data-ttu-id="194ad-120">.</span><span class="sxs-lookup"><span data-stu-id="194ad-120">.</span></span>|  
|[<span data-ttu-id="194ad-121">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="194ad-121">\<messageSenderAuthentication></span></span>](messagesenderauthentication.md)|<span data-ttu-id="194ad-122">Especifica las opciones de autenticación para los remitentes del mensaje.</span><span class="sxs-lookup"><span data-stu-id="194ad-122">Specifies authentication options for message senders.</span></span>|  
|[<span data-ttu-id="194ad-123">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="194ad-123">\<peerAuthentication></span></span>](peerauthentication.md)|<span data-ttu-id="194ad-124">Especifica las opciones de autenticación para los servicios del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="194ad-124">Specifies authentication options for peer services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="194ad-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="194ad-125">Parent Elements</span></span>  
  
|<span data-ttu-id="194ad-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="194ad-126">Element</span></span>|<span data-ttu-id="194ad-127">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="194ad-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="194ad-128">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="194ad-128">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="194ad-129">Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.</span><span class="sxs-lookup"><span data-stu-id="194ad-129">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="194ad-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="194ad-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="194ad-131">Conexión de redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="194ad-131">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="194ad-132">[Autenticación de mensajes de canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="194ad-132">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="194ad-133">[Autenticación personalizada de canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="194ad-133">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="194ad-134">Protección de las aplicaciones de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="194ad-134">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="194ad-135">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="194ad-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
