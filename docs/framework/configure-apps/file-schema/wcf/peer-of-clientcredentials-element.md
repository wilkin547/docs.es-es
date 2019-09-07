---
title: <peer>del <clientCredentials> elemento
ms.date: 03/30/2017
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
ms.openlocfilehash: dce7ef64de1e3eb248e3553c97cbce8e9b205b4c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400096"
---
# <a name="peer-of-clientcredentials-element"></a><span data-ttu-id="97b33-102">\<> del mismo \<nivel de elemento > clientCredentials</span><span class="sxs-lookup"><span data-stu-id="97b33-102">\<peer> of \<clientCredentials> Element</span></span>
<span data-ttu-id="97b33-103">Especifica las credenciales usadas al autenticar clientes punto a punto.</span><span class="sxs-lookup"><span data-stu-id="97b33-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
<span data-ttu-id="97b33-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="97b33-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="97b33-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="97b33-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="97b33-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="97b33-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="97b33-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="97b33-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="97b33-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="97b33-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="97b33-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="97b33-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="97b33-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> del mismo nivel**</span><span class="sxs-lookup"><span data-stu-id="97b33-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97b33-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="97b33-111">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="97b33-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="97b33-112">Attributes and Elements</span></span>  
 <span data-ttu-id="97b33-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="97b33-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="97b33-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="97b33-114">Attributes</span></span>  
 <span data-ttu-id="97b33-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="97b33-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="97b33-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="97b33-116">Child Elements</span></span>  
  
|<span data-ttu-id="97b33-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="97b33-117">Element</span></span>|<span data-ttu-id="97b33-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="97b33-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="97b33-119">\<certificate></span><span class="sxs-lookup"><span data-stu-id="97b33-119">\<certificate></span></span>](certificate-element.md)|<span data-ttu-id="97b33-120">Especifica un certificado X.509 que se va a usar para firmar y cifrar los mensajes para los clientes punto a punto.</span><span class="sxs-lookup"><span data-stu-id="97b33-120">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="97b33-121">.</span><span class="sxs-lookup"><span data-stu-id="97b33-121">.</span></span>|  
|[<span data-ttu-id="97b33-122">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="97b33-122">\<peerAuthentication></span></span>](peerauthentication-element.md)|<span data-ttu-id="97b33-123">Especifica las opciones de autenticación para clientes punto a punto.</span><span class="sxs-lookup"><span data-stu-id="97b33-123">Specifies authentication options for peer clients.</span></span>|  
|[<span data-ttu-id="97b33-124">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="97b33-124">\<messageSenderAuthentication></span></span>](messagesenderauthentication-element.md)|<span data-ttu-id="97b33-125">Especifica las opciones de autenticación para los remitentes del mensaje.</span><span class="sxs-lookup"><span data-stu-id="97b33-125">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="97b33-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="97b33-126">Parent Elements</span></span>  
  
|<span data-ttu-id="97b33-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="97b33-127">Element</span></span>|<span data-ttu-id="97b33-128">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="97b33-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="97b33-129">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="97b33-129">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="97b33-130">Especifica las credenciales usadas para autenticar un cliente a un servicio.</span><span class="sxs-lookup"><span data-stu-id="97b33-130">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97b33-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="97b33-131">Remarks</span></span>  
 <span data-ttu-id="97b33-132">Este elemento de configuración especifica las credenciales que un nodo del mismo nivel utiliza para autenticarse en otros nodos de la malla, así como los valores de autenticación que un nodo del mismo nivel utiliza para autenticar otros nodos entre pares.</span><span class="sxs-lookup"><span data-stu-id="97b33-132">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="97b33-133">Para obtener más información, consulte [autenticación de mensajes de canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) y [protección de aplicaciones de canal del mismo nivel](../../../wcf/feature-details/securing-peer-channel-applications.md).</span><span class="sxs-lookup"><span data-stu-id="97b33-133">For more information, see [Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) and [Securing Peer Channel Applications](../../../wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97b33-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="97b33-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="97b33-135">Conexión de redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="97b33-135">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="97b33-136">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="97b33-136">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- <span data-ttu-id="97b33-137">[Autenticación de mensajes de canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="97b33-137">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="97b33-138">[Autenticación personalizada de canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="97b33-138">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="97b33-139">Protección de las aplicaciones de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="97b33-139">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="97b33-140">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="97b33-140">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
