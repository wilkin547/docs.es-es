---
title: <peer> del <clientCredentials> elemento
ms.date: 03/30/2017
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
ms.openlocfilehash: 75d8543d7db5eee1345d54f934fc89c9593b85ac
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186996"
---
# <a name="peer-of-clientcredentials-element"></a><span data-ttu-id="acb95-102">\<peer> del \<clientCredentials> elemento</span><span class="sxs-lookup"><span data-stu-id="acb95-102">\<peer> of \<clientCredentials> Element</span></span>

<span data-ttu-id="acb95-103">Especifica las credenciales usadas al autenticar clientes punto a punto.</span><span class="sxs-lookup"><span data-stu-id="acb95-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peer>**  
  
## <a name="syntax"></a><span data-ttu-id="acb95-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="acb95-104">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="acb95-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="acb95-105">Attributes and Elements</span></span>  

 <span data-ttu-id="acb95-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="acb95-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="acb95-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="acb95-107">Attributes</span></span>  

 <span data-ttu-id="acb95-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="acb95-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="acb95-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="acb95-109">Child Elements</span></span>  
  
|<span data-ttu-id="acb95-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="acb95-110">Element</span></span>|<span data-ttu-id="acb95-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="acb95-111">Description</span></span>|  
|-------------|-----------------|  
|[\<certificate>](certificate-element.md)|<span data-ttu-id="acb95-112">Especifica un certificado X.509 que se va a usar para firmar y cifrar los mensajes para los clientes punto a punto.</span><span class="sxs-lookup"><span data-stu-id="acb95-112">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="acb95-113">.</span><span class="sxs-lookup"><span data-stu-id="acb95-113">.</span></span>|  
|[\<peerAuthentication>](peerauthentication-element.md)|<span data-ttu-id="acb95-114">Especifica las opciones de autenticación para clientes punto a punto.</span><span class="sxs-lookup"><span data-stu-id="acb95-114">Specifies authentication options for peer clients.</span></span>|  
|[\<messageSenderAuthentication>](messagesenderauthentication-element.md)|<span data-ttu-id="acb95-115">Especifica las opciones de autenticación para los remitentes del mensaje.</span><span class="sxs-lookup"><span data-stu-id="acb95-115">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="acb95-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="acb95-116">Parent Elements</span></span>  
  
|<span data-ttu-id="acb95-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="acb95-117">Element</span></span>|<span data-ttu-id="acb95-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="acb95-118">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="acb95-119">Especifica las credenciales usadas para autenticar un cliente a un servicio.</span><span class="sxs-lookup"><span data-stu-id="acb95-119">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="acb95-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="acb95-120">Remarks</span></span>  

 <span data-ttu-id="acb95-121">Este elemento de configuración especifica las credenciales que un nodo del mismo nivel utiliza para autenticarse en otros nodos de la malla, así como los valores de autenticación que un nodo del mismo nivel utiliza para autenticar otros nodos entre pares.</span><span class="sxs-lookup"><span data-stu-id="acb95-121">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="acb95-122">Para obtener más información, consulte [autenticación de mensajes de canal del mismo nivel](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) y [protección de aplicaciones de canal del mismo nivel](../../../wcf/feature-details/securing-peer-channel-applications.md).</span><span class="sxs-lookup"><span data-stu-id="acb95-122">For more information, see [Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) and [Securing Peer Channel Applications](../../../wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acb95-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="acb95-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="acb95-124">Redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="acb95-124">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="acb95-125">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="acb95-125">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- <span data-ttu-id="acb95-126">[Autenticación del mensaje del canal del mismo nivel](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="acb95-126">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="acb95-127">[Autenticación personalizada de canal del mismo nivel](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="acb95-127">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="acb95-128">Protección de las aplicaciones de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="acb95-128">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="acb95-129">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="acb95-129">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
