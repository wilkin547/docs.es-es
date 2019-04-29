---
title: <peer> de <clientCredentials> elemento
ms.date: 03/30/2017
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
ms.openlocfilehash: 7074ee992755557d7e5503035c89bdbefd678792
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783383"
---
# <a name="peer-of-clientcredentials-element"></a><span data-ttu-id="f6dc1-102">\<Peer > de \<clientCredentials > elemento</span><span class="sxs-lookup"><span data-stu-id="f6dc1-102">\<peer> of \<clientCredentials> Element</span></span>
<span data-ttu-id="f6dc1-103">Especifica las credenciales usadas al autenticar clientes punto a punto.</span><span class="sxs-lookup"><span data-stu-id="f6dc1-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="f6dc1-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f6dc1-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f6dc1-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="f6dc1-105">\<behaviors></span></span>  
<span data-ttu-id="f6dc1-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="f6dc1-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="f6dc1-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="f6dc1-107">\<behavior></span></span>  
<span data-ttu-id="f6dc1-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="f6dc1-108">\<clientCredentials></span></span>  
<span data-ttu-id="f6dc1-109">\<peer></span><span class="sxs-lookup"><span data-stu-id="f6dc1-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6dc1-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f6dc1-110">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f6dc1-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f6dc1-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f6dc1-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f6dc1-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f6dc1-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="f6dc1-113">Attributes</span></span>  
 <span data-ttu-id="f6dc1-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f6dc1-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f6dc1-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f6dc1-115">Child Elements</span></span>  
  
|<span data-ttu-id="f6dc1-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="f6dc1-116">Element</span></span>|<span data-ttu-id="f6dc1-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="f6dc1-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f6dc1-118">\<certificate></span><span class="sxs-lookup"><span data-stu-id="f6dc1-118">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)|<span data-ttu-id="f6dc1-119">Especifica un certificado X.509 que se va a usar para firmar y cifrar los mensajes para los clientes punto a punto.</span><span class="sxs-lookup"><span data-stu-id="f6dc1-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="f6dc1-120">.</span><span class="sxs-lookup"><span data-stu-id="f6dc1-120">.</span></span>|  
|[<span data-ttu-id="f6dc1-121">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="f6dc1-121">\<peerAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication-element.md)|<span data-ttu-id="f6dc1-122">Especifica las opciones de autenticación para clientes punto a punto.</span><span class="sxs-lookup"><span data-stu-id="f6dc1-122">Specifies authentication options for peer clients.</span></span>|  
|[<span data-ttu-id="f6dc1-123">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="f6dc1-123">\<messageSenderAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication-element.md)|<span data-ttu-id="f6dc1-124">Especifica las opciones de autenticación para los remitentes del mensaje.</span><span class="sxs-lookup"><span data-stu-id="f6dc1-124">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f6dc1-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f6dc1-125">Parent Elements</span></span>  
  
|<span data-ttu-id="f6dc1-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="f6dc1-126">Element</span></span>|<span data-ttu-id="f6dc1-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="f6dc1-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f6dc1-128">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="f6dc1-128">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="f6dc1-129">Especifica las credenciales usadas para autenticar un cliente a un servicio.</span><span class="sxs-lookup"><span data-stu-id="f6dc1-129">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6dc1-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f6dc1-130">Remarks</span></span>  
 <span data-ttu-id="f6dc1-131">Este elemento de configuración especifica las credenciales que un nodo del mismo nivel utiliza para autenticarse en otros nodos de la malla, así como los valores de autenticación que un nodo del mismo nivel utiliza para autenticar otros nodos entre pares.</span><span class="sxs-lookup"><span data-stu-id="f6dc1-131">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="f6dc1-132">Para obtener más información, consulte [autenticación de mensajes del canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) y [proteger aplicaciones de canal del mismo nivel](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).</span><span class="sxs-lookup"><span data-stu-id="f6dc1-132">For more information, see [Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) and [Securing Peer Channel Applications](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6dc1-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6dc1-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="f6dc1-134">Conexión de redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="f6dc1-134">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="f6dc1-135">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="f6dc1-135">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- <span data-ttu-id="f6dc1-136">[Autenticación de mensajes del canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="f6dc1-136">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="f6dc1-137">[Canal del mismo nivel de autenticación personalizada](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="f6dc1-137">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="f6dc1-138">Protección de las aplicaciones de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="f6dc1-138">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="f6dc1-139">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="f6dc1-139">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
