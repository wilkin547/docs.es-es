---
title: <peer>del <clientCredentials> elemento
ms.date: 03/30/2017
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
ms.openlocfilehash: 2f1cb5689125e2483a74dcac515beb07abbb7c70
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934032"
---
# <a name="peer-of-clientcredentials-element"></a><span data-ttu-id="23af9-102">\<> del mismo \<nivel de elemento > clientCredentials</span><span class="sxs-lookup"><span data-stu-id="23af9-102">\<peer> of \<clientCredentials> Element</span></span>
<span data-ttu-id="23af9-103">Especifica las credenciales usadas al autenticar clientes punto a punto.</span><span class="sxs-lookup"><span data-stu-id="23af9-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="23af9-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="23af9-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="23af9-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="23af9-105">\<behaviors></span></span>  
<span data-ttu-id="23af9-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="23af9-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="23af9-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="23af9-107">\<behavior></span></span>  
<span data-ttu-id="23af9-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="23af9-108">\<clientCredentials></span></span>  
<span data-ttu-id="23af9-109">\<> del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="23af9-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23af9-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="23af9-110">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="23af9-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="23af9-111">Attributes and Elements</span></span>  
 <span data-ttu-id="23af9-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="23af9-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="23af9-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="23af9-113">Attributes</span></span>  
 <span data-ttu-id="23af9-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="23af9-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="23af9-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="23af9-115">Child Elements</span></span>  
  
|<span data-ttu-id="23af9-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="23af9-116">Element</span></span>|<span data-ttu-id="23af9-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="23af9-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="23af9-118">\<certificate></span><span class="sxs-lookup"><span data-stu-id="23af9-118">\<certificate></span></span>](certificate-element.md)|<span data-ttu-id="23af9-119">Especifica un certificado X.509 que se va a usar para firmar y cifrar los mensajes para los clientes punto a punto.</span><span class="sxs-lookup"><span data-stu-id="23af9-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="23af9-120">.</span><span class="sxs-lookup"><span data-stu-id="23af9-120">.</span></span>|  
|[<span data-ttu-id="23af9-121">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="23af9-121">\<peerAuthentication></span></span>](peerauthentication-element.md)|<span data-ttu-id="23af9-122">Especifica las opciones de autenticación para clientes punto a punto.</span><span class="sxs-lookup"><span data-stu-id="23af9-122">Specifies authentication options for peer clients.</span></span>|  
|[<span data-ttu-id="23af9-123">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="23af9-123">\<messageSenderAuthentication></span></span>](messagesenderauthentication-element.md)|<span data-ttu-id="23af9-124">Especifica las opciones de autenticación para los remitentes del mensaje.</span><span class="sxs-lookup"><span data-stu-id="23af9-124">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="23af9-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="23af9-125">Parent Elements</span></span>  
  
|<span data-ttu-id="23af9-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="23af9-126">Element</span></span>|<span data-ttu-id="23af9-127">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="23af9-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="23af9-128">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="23af9-128">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="23af9-129">Especifica las credenciales usadas para autenticar un cliente a un servicio.</span><span class="sxs-lookup"><span data-stu-id="23af9-129">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23af9-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="23af9-130">Remarks</span></span>  
 <span data-ttu-id="23af9-131">Este elemento de configuración especifica las credenciales que un nodo del mismo nivel utiliza para autenticarse en otros nodos de la malla, así como los valores de autenticación que un nodo del mismo nivel utiliza para autenticar otros nodos entre pares.</span><span class="sxs-lookup"><span data-stu-id="23af9-131">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="23af9-132">Para obtener más información, consulte [autenticación de mensajes de canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) y [protección de aplicaciones de canal del mismo nivel](../../../wcf/feature-details/securing-peer-channel-applications.md).</span><span class="sxs-lookup"><span data-stu-id="23af9-132">For more information, see [Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) and [Securing Peer Channel Applications](../../../wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23af9-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="23af9-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="23af9-134">Conexión de redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="23af9-134">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="23af9-135">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="23af9-135">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- <span data-ttu-id="23af9-136">[Autenticación de mensajes de canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="23af9-136">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="23af9-137">[Autenticación personalizada de canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="23af9-137">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="23af9-138">Protección de las aplicaciones de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="23af9-138">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="23af9-139">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="23af9-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
