---
title: <peer> de <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: b134e21d-e5b5-458e-9309-626dbf8db4ed
ms.openlocfilehash: ca97be7b1ab562382895fea4f1d1fc716151b70b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397640"
---
# <a name="peer-of-servicecredentials"></a><span data-ttu-id="1f7c7-102">\<> del mismo \<nivel de serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="1f7c7-102">\<peer> of \<serviceCredentials></span></span>
<span data-ttu-id="1f7c7-103">Especifica las credenciales actuales de un nodo del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="1f7c7-103">Specifies the current credentials for a peer node.</span></span>  
  
<span data-ttu-id="1f7c7-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1f7c7-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1f7c7-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="1f7c7-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="1f7c7-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="1f7c7-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="1f7c7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="1f7c7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="1f7c7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="1f7c7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="1f7c7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de serviceCredentials**](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="1f7c7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="1f7c7-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> del mismo nivel**</span><span class="sxs-lookup"><span data-stu-id="1f7c7-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f7c7-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1f7c7-111">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1f7c7-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1f7c7-112">Attributes and Elements</span></span>  
 <span data-ttu-id="1f7c7-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1f7c7-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1f7c7-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="1f7c7-114">Attributes</span></span>  
 <span data-ttu-id="1f7c7-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1f7c7-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1f7c7-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1f7c7-116">Child Elements</span></span>  
  
|<span data-ttu-id="1f7c7-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="1f7c7-117">Element</span></span>|<span data-ttu-id="1f7c7-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="1f7c7-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1f7c7-119">\<certificate></span><span class="sxs-lookup"><span data-stu-id="1f7c7-119">\<certificate></span></span>](certificate-of-peer.md)|<span data-ttu-id="1f7c7-120">Especifica un certificado X.509 que se va a usar para firmar y cifrar los mensajes para los servicios punto a punto.</span><span class="sxs-lookup"><span data-stu-id="1f7c7-120">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer services.</span></span> <span data-ttu-id="1f7c7-121">.</span><span class="sxs-lookup"><span data-stu-id="1f7c7-121">.</span></span>|  
|[<span data-ttu-id="1f7c7-122">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="1f7c7-122">\<messageSenderAuthentication></span></span>](messagesenderauthentication.md)|<span data-ttu-id="1f7c7-123">Especifica las opciones de autenticación para los remitentes del mensaje.</span><span class="sxs-lookup"><span data-stu-id="1f7c7-123">Specifies authentication options for message senders.</span></span>|  
|[<span data-ttu-id="1f7c7-124">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="1f7c7-124">\<peerAuthentication></span></span>](peerauthentication.md)|<span data-ttu-id="1f7c7-125">Especifica las opciones de autenticación para los servicios del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="1f7c7-125">Specifies authentication options for peer services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1f7c7-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1f7c7-126">Parent Elements</span></span>  
  
|<span data-ttu-id="1f7c7-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="1f7c7-127">Element</span></span>|<span data-ttu-id="1f7c7-128">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="1f7c7-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1f7c7-129">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="1f7c7-129">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="1f7c7-130">Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.</span><span class="sxs-lookup"><span data-stu-id="1f7c7-130">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1f7c7-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f7c7-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="1f7c7-132">Conexión de redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="1f7c7-132">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="1f7c7-133">[Autenticación de mensajes de canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="1f7c7-133">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="1f7c7-134">[Autenticación personalizada de canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="1f7c7-134">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="1f7c7-135">Protección de las aplicaciones de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="1f7c7-135">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="1f7c7-136">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="1f7c7-136">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
