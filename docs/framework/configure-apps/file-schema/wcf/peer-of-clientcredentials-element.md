---
title: '&lt;peer&gt; de &lt;clientCredentials&gt; (elemento)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c3479b52c6e06b7b9ebd69d46780e8dca70d2ef7
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="ltpeergt-of-ltclientcredentialsgt-element"></a><span data-ttu-id="185ed-102">&lt;peer&gt; de &lt;clientCredentials&gt; (elemento)</span><span class="sxs-lookup"><span data-stu-id="185ed-102">&lt;peer&gt; of &lt;clientCredentials&gt; Element</span></span>
<span data-ttu-id="185ed-103">Especifica las credenciales usadas al autenticar clientes punto a punto.</span><span class="sxs-lookup"><span data-stu-id="185ed-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="185ed-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="185ed-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="185ed-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="185ed-105">\<behaviors></span></span>  
<span data-ttu-id="185ed-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="185ed-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="185ed-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="185ed-107">\<behavior></span></span>  
<span data-ttu-id="185ed-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="185ed-108">\<clientCredentials></span></span>  
<span data-ttu-id="185ed-109">\<punto ></span><span class="sxs-lookup"><span data-stu-id="185ed-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="185ed-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="185ed-110">Syntax</span></span>  
  
```xml  
<peer>  
  <certificate/>  
  <peerAuthentication/>  
  <messageSenderAuthentication/>  
</peer>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="185ed-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="185ed-111">Attributes and Elements</span></span>  
 <span data-ttu-id="185ed-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="185ed-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="185ed-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="185ed-113">Attributes</span></span>  
 <span data-ttu-id="185ed-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="185ed-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="185ed-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="185ed-115">Child Elements</span></span>  
  
|<span data-ttu-id="185ed-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="185ed-116">Element</span></span>|<span data-ttu-id="185ed-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="185ed-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="185ed-118">\<certificate></span><span class="sxs-lookup"><span data-stu-id="185ed-118">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)|<span data-ttu-id="185ed-119">Especifica un certificado X.509 que se va a usar para firmar y cifrar los mensajes para los clientes punto a punto.</span><span class="sxs-lookup"><span data-stu-id="185ed-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="185ed-120">.</span><span class="sxs-lookup"><span data-stu-id="185ed-120">.</span></span>|  
|[<span data-ttu-id="185ed-121">\<peerAuthentication ></span><span class="sxs-lookup"><span data-stu-id="185ed-121">\<peerAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication-element.md)|<span data-ttu-id="185ed-122">Especifica las opciones de autenticación para clientes punto a punto.</span><span class="sxs-lookup"><span data-stu-id="185ed-122">Specifies authentication options for peer clients.</span></span>|  
|[<span data-ttu-id="185ed-123">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="185ed-123">\<messageSenderAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication-element.md)|<span data-ttu-id="185ed-124">Especifica las opciones de autenticación para los remitentes del mensaje.</span><span class="sxs-lookup"><span data-stu-id="185ed-124">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="185ed-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="185ed-125">Parent Elements</span></span>  
  
|<span data-ttu-id="185ed-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="185ed-126">Element</span></span>|<span data-ttu-id="185ed-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="185ed-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="185ed-128">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="185ed-128">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="185ed-129">Especifica las credenciales usadas para autenticar un cliente a un servicio.</span><span class="sxs-lookup"><span data-stu-id="185ed-129">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="185ed-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="185ed-130">Remarks</span></span>  
 <span data-ttu-id="185ed-131">Este elemento de configuración especifica las credenciales que un nodo del mismo nivel utiliza para autenticarse en otros nodos de la malla, así como los valores de autenticación que un nodo del mismo nivel utiliza para autenticar otros nodos entre pares.</span><span class="sxs-lookup"><span data-stu-id="185ed-131">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="185ed-132">Para obtener más información, consulte [autenticación de mensajes del canal del mismo nivel](http://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95) y [las aplicaciones de canal del mismo nivel de protección de](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).</span><span class="sxs-lookup"><span data-stu-id="185ed-132">For more information, see [Peer Channel Message Authentication](http://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95) and [Securing Peer Channel Applications](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="185ed-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="185ed-133">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>  
 <xref:System.ServiceModel.Security.PeerCredential>  
 [<span data-ttu-id="185ed-134">Conexión de redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="185ed-134">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="185ed-135">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="185ed-135">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="185ed-136">Autenticación de mensajes del canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="185ed-136">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="185ed-137">Canal del mismo nivel de autenticación personalizada</span><span class="sxs-lookup"><span data-stu-id="185ed-137">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="185ed-138">Protección de las aplicaciones de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="185ed-138">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)  
 [<span data-ttu-id="185ed-139">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="185ed-139">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
