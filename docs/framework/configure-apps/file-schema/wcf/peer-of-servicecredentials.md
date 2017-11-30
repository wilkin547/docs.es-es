---
title: '&lt;peer&gt; de &lt;serviceCredentials&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b134e21d-e5b5-458e-9309-626dbf8db4ed
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a3af8c07e86b7ccdf5443a666626b523914a2c45
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltpeergt-of-ltservicecredentialsgt"></a><span data-ttu-id="b69b5-102">&lt;peer&gt; de &lt;serviceCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="b69b5-102">&lt;peer&gt; of &lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="b69b5-103">Especifica las credenciales actuales de un nodo del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="b69b5-103">Specifies the current credentials for a peer node.</span></span>  
  
 <span data-ttu-id="b69b5-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="b69b5-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b69b5-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="b69b5-105">\<behaviors></span></span>  
<span data-ttu-id="b69b5-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="b69b5-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="b69b5-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="b69b5-107">\<behavior></span></span>  
<span data-ttu-id="b69b5-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="b69b5-108">\<serviceCredentials></span></span>  
<span data-ttu-id="b69b5-109">\<punto ></span><span class="sxs-lookup"><span data-stu-id="b69b5-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b69b5-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b69b5-110">Syntax</span></span>  
  
```xml  
<peer>  
  <certificate/>  
  <peerAuthentication/>  
  <messageSenderAuthentication/>  
</peer>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b69b5-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b69b5-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b69b5-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b69b5-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b69b5-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="b69b5-113">Attributes</span></span>  
 <span data-ttu-id="b69b5-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b69b5-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b69b5-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b69b5-115">Child Elements</span></span>  
  
|<span data-ttu-id="b69b5-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="b69b5-116">Element</span></span>|<span data-ttu-id="b69b5-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="b69b5-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b69b5-118">\<certificado ></span><span class="sxs-lookup"><span data-stu-id="b69b5-118">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-of-peer.md)|<span data-ttu-id="b69b5-119">Especifica un certificado X.509 que se va a usar para firmar y cifrar los mensajes para los servicios punto a punto.</span><span class="sxs-lookup"><span data-stu-id="b69b5-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer services.</span></span> <span data-ttu-id="b69b5-120">.</span><span class="sxs-lookup"><span data-stu-id="b69b5-120">.</span></span>|  
|[<span data-ttu-id="b69b5-121">\<messageSenderAuthentication ></span><span class="sxs-lookup"><span data-stu-id="b69b5-121">\<messageSenderAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication.md)|<span data-ttu-id="b69b5-122">Especifica las opciones de autenticación para los remitentes del mensaje.</span><span class="sxs-lookup"><span data-stu-id="b69b5-122">Specifies authentication options for message senders.</span></span>|  
|[<span data-ttu-id="b69b5-123">\<peerAuthentication ></span><span class="sxs-lookup"><span data-stu-id="b69b5-123">\<peerAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication.md)|<span data-ttu-id="b69b5-124">Especifica las opciones de autenticación para los servicios del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="b69b5-124">Specifies authentication options for peer services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b69b5-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b69b5-125">Parent Elements</span></span>  
  
|<span data-ttu-id="b69b5-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="b69b5-126">Element</span></span>|<span data-ttu-id="b69b5-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="b69b5-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b69b5-128">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="b69b5-128">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="b69b5-129">Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.</span><span class="sxs-lookup"><span data-stu-id="b69b5-129">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b69b5-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="b69b5-130">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.Peer%2A>  
 <xref:System.ServiceModel.Description.ServiceCredentials.Peer%2A>  
 <xref:System.ServiceModel.Security.PeerCredential>  
 [<span data-ttu-id="b69b5-131">Redes de punto a punto</span><span class="sxs-lookup"><span data-stu-id="b69b5-131">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="b69b5-132">Autenticación de mensajes del canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="b69b5-132">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="b69b5-133">Canal del mismo nivel de autenticación personalizada</span><span class="sxs-lookup"><span data-stu-id="b69b5-133">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="b69b5-134">Proteger las aplicaciones de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="b69b5-134">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)  
 [<span data-ttu-id="b69b5-135">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="b69b5-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
