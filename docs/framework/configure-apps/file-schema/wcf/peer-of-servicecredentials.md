---
title: <peer> de <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: b134e21d-e5b5-458e-9309-626dbf8db4ed
ms.openlocfilehash: 2090e79e6affe8ade6e2e52b94d2c4e1dafe8fa1
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266031"
---
# <a name="peer-of-servicecredentials"></a><span data-ttu-id="fa5aa-102">\<Peer > de \<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="fa5aa-102">\<peer> of \<serviceCredentials></span></span>
<span data-ttu-id="fa5aa-103">Especifica las credenciales actuales de un nodo del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="fa5aa-103">Specifies the current credentials for a peer node.</span></span>  
  
 <span data-ttu-id="fa5aa-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fa5aa-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="fa5aa-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="fa5aa-105">\<behaviors></span></span>  
<span data-ttu-id="fa5aa-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="fa5aa-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="fa5aa-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="fa5aa-107">\<behavior></span></span>  
<span data-ttu-id="fa5aa-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="fa5aa-108">\<serviceCredentials></span></span>  
<span data-ttu-id="fa5aa-109">\<peer></span><span class="sxs-lookup"><span data-stu-id="fa5aa-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa5aa-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fa5aa-110">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fa5aa-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fa5aa-111">Attributes and Elements</span></span>  
 <span data-ttu-id="fa5aa-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fa5aa-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa5aa-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="fa5aa-113">Attributes</span></span>  
 <span data-ttu-id="fa5aa-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="fa5aa-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fa5aa-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fa5aa-115">Child Elements</span></span>  
  
|<span data-ttu-id="fa5aa-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="fa5aa-116">Element</span></span>|<span data-ttu-id="fa5aa-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="fa5aa-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa5aa-118">\<certificate></span><span class="sxs-lookup"><span data-stu-id="fa5aa-118">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-of-peer.md)|<span data-ttu-id="fa5aa-119">Especifica un certificado X.509 que se va a usar para firmar y cifrar los mensajes para los servicios punto a punto.</span><span class="sxs-lookup"><span data-stu-id="fa5aa-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer services.</span></span> <span data-ttu-id="fa5aa-120">.</span><span class="sxs-lookup"><span data-stu-id="fa5aa-120">.</span></span>|  
|[<span data-ttu-id="fa5aa-121">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="fa5aa-121">\<messageSenderAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication.md)|<span data-ttu-id="fa5aa-122">Especifica las opciones de autenticación para los remitentes del mensaje.</span><span class="sxs-lookup"><span data-stu-id="fa5aa-122">Specifies authentication options for message senders.</span></span>|  
|[<span data-ttu-id="fa5aa-123">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="fa5aa-123">\<peerAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication.md)|<span data-ttu-id="fa5aa-124">Especifica las opciones de autenticación para los servicios del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="fa5aa-124">Specifies authentication options for peer services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fa5aa-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fa5aa-125">Parent Elements</span></span>  
  
|<span data-ttu-id="fa5aa-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="fa5aa-126">Element</span></span>|<span data-ttu-id="fa5aa-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="fa5aa-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa5aa-128">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="fa5aa-128">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="fa5aa-129">Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.</span><span class="sxs-lookup"><span data-stu-id="fa5aa-129">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fa5aa-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa5aa-130">See also</span></span>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="fa5aa-131">Conexión de redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="fa5aa-131">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="fa5aa-132">Autenticación de mensajes del canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="fa5aa-132">Peer Channel Message Authentication</span></span>](https://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)
- [<span data-ttu-id="fa5aa-133">Canal del mismo nivel de autenticación personalizada</span><span class="sxs-lookup"><span data-stu-id="fa5aa-133">Peer Channel Custom Authentication</span></span>](https://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)
- [<span data-ttu-id="fa5aa-134">Protección de las aplicaciones de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="fa5aa-134">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="fa5aa-135">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="fa5aa-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
