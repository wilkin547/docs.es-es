---
title: <peer> de <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: b134e21d-e5b5-458e-9309-626dbf8db4ed
ms.openlocfilehash: d726ab460141b1e373a1cabf770b8958f50319eb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783401"
---
# <a name="peer-of-servicecredentials"></a><span data-ttu-id="1756a-102">\<Peer > de \<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="1756a-102">\<peer> of \<serviceCredentials></span></span>
<span data-ttu-id="1756a-103">Especifica las credenciales actuales de un nodo del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="1756a-103">Specifies the current credentials for a peer node.</span></span>  
  
 <span data-ttu-id="1756a-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1756a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1756a-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="1756a-105">\<behaviors></span></span>  
<span data-ttu-id="1756a-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="1756a-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="1756a-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="1756a-107">\<behavior></span></span>  
<span data-ttu-id="1756a-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="1756a-108">\<serviceCredentials></span></span>  
<span data-ttu-id="1756a-109">\<peer></span><span class="sxs-lookup"><span data-stu-id="1756a-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1756a-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1756a-110">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1756a-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1756a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1756a-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1756a-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1756a-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="1756a-113">Attributes</span></span>  
 <span data-ttu-id="1756a-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1756a-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1756a-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1756a-115">Child Elements</span></span>  
  
|<span data-ttu-id="1756a-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="1756a-116">Element</span></span>|<span data-ttu-id="1756a-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="1756a-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1756a-118">\<certificate></span><span class="sxs-lookup"><span data-stu-id="1756a-118">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-of-peer.md)|<span data-ttu-id="1756a-119">Especifica un certificado X.509 que se va a usar para firmar y cifrar los mensajes para los servicios punto a punto.</span><span class="sxs-lookup"><span data-stu-id="1756a-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer services.</span></span> <span data-ttu-id="1756a-120">.</span><span class="sxs-lookup"><span data-stu-id="1756a-120">.</span></span>|  
|[<span data-ttu-id="1756a-121">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="1756a-121">\<messageSenderAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication.md)|<span data-ttu-id="1756a-122">Especifica las opciones de autenticación para los remitentes del mensaje.</span><span class="sxs-lookup"><span data-stu-id="1756a-122">Specifies authentication options for message senders.</span></span>|  
|[<span data-ttu-id="1756a-123">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="1756a-123">\<peerAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication.md)|<span data-ttu-id="1756a-124">Especifica las opciones de autenticación para los servicios del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="1756a-124">Specifies authentication options for peer services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1756a-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1756a-125">Parent Elements</span></span>  
  
|<span data-ttu-id="1756a-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="1756a-126">Element</span></span>|<span data-ttu-id="1756a-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="1756a-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1756a-128">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="1756a-128">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="1756a-129">Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.</span><span class="sxs-lookup"><span data-stu-id="1756a-129">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1756a-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="1756a-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="1756a-131">Conexión de redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="1756a-131">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="1756a-132">[Autenticación de mensajes del canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="1756a-132">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="1756a-133">[Canal del mismo nivel de autenticación personalizada](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="1756a-133">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="1756a-134">Protección de las aplicaciones de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="1756a-134">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="1756a-135">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="1756a-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
