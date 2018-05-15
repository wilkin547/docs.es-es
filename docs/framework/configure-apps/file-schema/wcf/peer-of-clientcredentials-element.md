---
title: '&lt;peer&gt; de &lt;clientCredentials&gt; (elemento)'
ms.date: 03/30/2017
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
ms.openlocfilehash: 9d64f682f67dcc7c4f0c0f1600938f8ff9ac0dd6
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltpeergt-of-ltclientcredentialsgt-element"></a><span data-ttu-id="9a672-102">&lt;peer&gt; de &lt;clientCredentials&gt; (elemento)</span><span class="sxs-lookup"><span data-stu-id="9a672-102">&lt;peer&gt; of &lt;clientCredentials&gt; Element</span></span>
<span data-ttu-id="9a672-103">Especifica las credenciales usadas al autenticar clientes punto a punto.</span><span class="sxs-lookup"><span data-stu-id="9a672-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="9a672-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9a672-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9a672-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="9a672-105">\<behaviors></span></span>  
<span data-ttu-id="9a672-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="9a672-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="9a672-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="9a672-107">\<behavior></span></span>  
<span data-ttu-id="9a672-108">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="9a672-108">\<clientCredentials></span></span>  
<span data-ttu-id="9a672-109">\<punto ></span><span class="sxs-lookup"><span data-stu-id="9a672-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a672-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9a672-110">Syntax</span></span>  
  
```xml  
<peer>  
  <certificate/>  
  <peerAuthentication/>  
  <messageSenderAuthentication/>  
</peer>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9a672-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9a672-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9a672-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9a672-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9a672-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="9a672-113">Attributes</span></span>  
 <span data-ttu-id="9a672-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9a672-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9a672-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9a672-115">Child Elements</span></span>  
  
|<span data-ttu-id="9a672-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="9a672-116">Element</span></span>|<span data-ttu-id="9a672-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="9a672-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9a672-118">\<certificado ></span><span class="sxs-lookup"><span data-stu-id="9a672-118">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)|<span data-ttu-id="9a672-119">Especifica un certificado X.509 que se va a usar para firmar y cifrar los mensajes para los clientes punto a punto.</span><span class="sxs-lookup"><span data-stu-id="9a672-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="9a672-120">.</span><span class="sxs-lookup"><span data-stu-id="9a672-120">.</span></span>|  
|[<span data-ttu-id="9a672-121">\<peerAuthentication ></span><span class="sxs-lookup"><span data-stu-id="9a672-121">\<peerAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication-element.md)|<span data-ttu-id="9a672-122">Especifica las opciones de autenticación para clientes punto a punto.</span><span class="sxs-lookup"><span data-stu-id="9a672-122">Specifies authentication options for peer clients.</span></span>|  
|[<span data-ttu-id="9a672-123">\<messageSenderAuthentication ></span><span class="sxs-lookup"><span data-stu-id="9a672-123">\<messageSenderAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication-element.md)|<span data-ttu-id="9a672-124">Especifica las opciones de autenticación para los remitentes del mensaje.</span><span class="sxs-lookup"><span data-stu-id="9a672-124">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9a672-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9a672-125">Parent Elements</span></span>  
  
|<span data-ttu-id="9a672-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="9a672-126">Element</span></span>|<span data-ttu-id="9a672-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="9a672-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9a672-128">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="9a672-128">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="9a672-129">Especifica las credenciales usadas para autenticar un cliente a un servicio.</span><span class="sxs-lookup"><span data-stu-id="9a672-129">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a672-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9a672-130">Remarks</span></span>  
 <span data-ttu-id="9a672-131">Este elemento de configuración especifica las credenciales que un nodo del mismo nivel utiliza para autenticarse en otros nodos de la malla, así como los valores de autenticación que un nodo del mismo nivel utiliza para autenticar otros nodos entre pares.</span><span class="sxs-lookup"><span data-stu-id="9a672-131">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="9a672-132">Para obtener más información, consulte [autenticación de mensajes del canal del mismo nivel](http://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95) y [las aplicaciones de canal del mismo nivel de protección de](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).</span><span class="sxs-lookup"><span data-stu-id="9a672-132">For more information, see [Peer Channel Message Authentication](http://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95) and [Securing Peer Channel Applications](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a672-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a672-133">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>  
 <xref:System.ServiceModel.Security.PeerCredential>  
 [<span data-ttu-id="9a672-134">Conexión de redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="9a672-134">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="9a672-135">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="9a672-135">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="9a672-136">Autenticación de mensajes del canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="9a672-136">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="9a672-137">Canal del mismo nivel de autenticación personalizada</span><span class="sxs-lookup"><span data-stu-id="9a672-137">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="9a672-138">Protección de las aplicaciones de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="9a672-138">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)  
 [<span data-ttu-id="9a672-139">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="9a672-139">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
