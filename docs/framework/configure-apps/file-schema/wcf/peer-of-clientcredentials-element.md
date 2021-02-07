---
description: 'Más información sobre: <peer> del <clientCredentials> elemento'
title: <peer> del <clientCredentials> elemento
ms.date: 03/30/2017
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
ms.openlocfilehash: 1ff9386ba51dcf6bab6df71bd345cdaa59f18e3a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683793"
---
# <a name="peer-of-clientcredentials-element"></a><span data-ttu-id="cdb90-103">\<peer> del \<clientCredentials> elemento</span><span class="sxs-lookup"><span data-stu-id="cdb90-103">\<peer> of \<clientCredentials> Element</span></span>

<span data-ttu-id="cdb90-104">Especifica las credenciales usadas al autenticar clientes punto a punto.</span><span class="sxs-lookup"><span data-stu-id="cdb90-104">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peer>**  
  
## <a name="syntax"></a><span data-ttu-id="cdb90-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cdb90-105">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cdb90-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="cdb90-106">Attributes and Elements</span></span>  

 <span data-ttu-id="cdb90-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="cdb90-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cdb90-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="cdb90-108">Attributes</span></span>  

 <span data-ttu-id="cdb90-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="cdb90-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cdb90-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="cdb90-110">Child Elements</span></span>  
  
|<span data-ttu-id="cdb90-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="cdb90-111">Element</span></span>|<span data-ttu-id="cdb90-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="cdb90-112">Description</span></span>|  
|-------------|-----------------|  
|[\<certificate>](certificate-element.md)|<span data-ttu-id="cdb90-113">Especifica un certificado X.509 que se va a usar para firmar y cifrar los mensajes para los clientes punto a punto.</span><span class="sxs-lookup"><span data-stu-id="cdb90-113">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="cdb90-114">.</span><span class="sxs-lookup"><span data-stu-id="cdb90-114">.</span></span>|  
|[\<peerAuthentication>](peerauthentication-element.md)|<span data-ttu-id="cdb90-115">Especifica las opciones de autenticación para clientes punto a punto.</span><span class="sxs-lookup"><span data-stu-id="cdb90-115">Specifies authentication options for peer clients.</span></span>|  
|[\<messageSenderAuthentication>](messagesenderauthentication-element.md)|<span data-ttu-id="cdb90-116">Especifica las opciones de autenticación para los remitentes del mensaje.</span><span class="sxs-lookup"><span data-stu-id="cdb90-116">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cdb90-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="cdb90-117">Parent Elements</span></span>  
  
|<span data-ttu-id="cdb90-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="cdb90-118">Element</span></span>|<span data-ttu-id="cdb90-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="cdb90-119">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="cdb90-120">Especifica las credenciales usadas para autenticar un cliente a un servicio.</span><span class="sxs-lookup"><span data-stu-id="cdb90-120">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cdb90-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cdb90-121">Remarks</span></span>  

 <span data-ttu-id="cdb90-122">Este elemento de configuración especifica las credenciales que un nodo del mismo nivel utiliza para autenticarse en otros nodos de la malla, así como los valores de autenticación que un nodo del mismo nivel utiliza para autenticar otros nodos entre pares.</span><span class="sxs-lookup"><span data-stu-id="cdb90-122">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="cdb90-123">Para obtener más información, consulte [autenticación de mensajes de canal del mismo nivel](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) y [protección de aplicaciones de canal del mismo nivel](../../../wcf/feature-details/securing-peer-channel-applications.md).</span><span class="sxs-lookup"><span data-stu-id="cdb90-123">For more information, see [Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) and [Securing Peer Channel Applications](../../../wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdb90-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="cdb90-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="cdb90-125">Conexión de redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="cdb90-125">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="cdb90-126">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="cdb90-126">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- <span data-ttu-id="cdb90-127">[Autenticación del mensaje del canal del mismo nivel](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="cdb90-127">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="cdb90-128">[Autenticación personalizada de canal del mismo nivel](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="cdb90-128">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="cdb90-129">Protección de las aplicaciones de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="cdb90-129">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="cdb90-130">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="cdb90-130">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
