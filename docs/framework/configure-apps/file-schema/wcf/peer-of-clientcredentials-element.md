---
title: <peer>del <clientCredentials> elemento
ms.date: 03/30/2017
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
ms.openlocfilehash: dce7ef64de1e3eb248e3553c97cbce8e9b205b4c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400096"
---
# <a name="peer-of-clientcredentials-element"></a><span data-ttu-id="3a6b5-102">\<peer>del \<clientCredentials> elemento</span><span class="sxs-lookup"><span data-stu-id="3a6b5-102">\<peer> of \<clientCredentials> Element</span></span>
<span data-ttu-id="3a6b5-103">Especifica las credenciales usadas al autenticar clientes punto a punto.</span><span class="sxs-lookup"><span data-stu-id="3a6b5-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peer>**  
  
## <a name="syntax"></a><span data-ttu-id="3a6b5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3a6b5-104">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a6b5-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3a6b5-105">Attributes and Elements</span></span>  
 <span data-ttu-id="3a6b5-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3a6b5-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a6b5-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="3a6b5-107">Attributes</span></span>  
 <span data-ttu-id="3a6b5-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3a6b5-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3a6b5-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3a6b5-109">Child Elements</span></span>  
  
|<span data-ttu-id="3a6b5-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="3a6b5-110">Element</span></span>|<span data-ttu-id="3a6b5-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a6b5-111">Description</span></span>|  
|-------------|-----------------|  
|[\<certificate>](certificate-element.md)|<span data-ttu-id="3a6b5-112">Especifica un certificado X.509 que se va a usar para firmar y cifrar los mensajes para los clientes punto a punto.</span><span class="sxs-lookup"><span data-stu-id="3a6b5-112">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="3a6b5-113">.</span><span class="sxs-lookup"><span data-stu-id="3a6b5-113">.</span></span>|  
|[\<peerAuthentication>](peerauthentication-element.md)|<span data-ttu-id="3a6b5-114">Especifica las opciones de autenticación para clientes punto a punto.</span><span class="sxs-lookup"><span data-stu-id="3a6b5-114">Specifies authentication options for peer clients.</span></span>|  
|[\<messageSenderAuthentication>](messagesenderauthentication-element.md)|<span data-ttu-id="3a6b5-115">Especifica las opciones de autenticación para los remitentes del mensaje.</span><span class="sxs-lookup"><span data-stu-id="3a6b5-115">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3a6b5-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3a6b5-116">Parent Elements</span></span>  
  
|<span data-ttu-id="3a6b5-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="3a6b5-117">Element</span></span>|<span data-ttu-id="3a6b5-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a6b5-118">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="3a6b5-119">Especifica las credenciales usadas para autenticar un cliente a un servicio.</span><span class="sxs-lookup"><span data-stu-id="3a6b5-119">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a6b5-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3a6b5-120">Remarks</span></span>  
 <span data-ttu-id="3a6b5-121">Este elemento de configuración especifica las credenciales que un nodo del mismo nivel utiliza para autenticarse en otros nodos de la malla, así como los valores de autenticación que un nodo del mismo nivel utiliza para autenticar otros nodos entre pares.</span><span class="sxs-lookup"><span data-stu-id="3a6b5-121">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="3a6b5-122">Para obtener más información, consulte [autenticación de mensajes de canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) y [protección de aplicaciones de canal del mismo nivel](../../../wcf/feature-details/securing-peer-channel-applications.md).</span><span class="sxs-lookup"><span data-stu-id="3a6b5-122">For more information, see [Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) and [Securing Peer Channel Applications](../../../wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a6b5-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3a6b5-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="3a6b5-124">Conexión de redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="3a6b5-124">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="3a6b5-125">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="3a6b5-125">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- <span data-ttu-id="3a6b5-126">[Autenticación del mensaje del canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="3a6b5-126">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="3a6b5-127">[Autenticación personalizada de canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="3a6b5-127">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="3a6b5-128">Protección de las aplicaciones de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="3a6b5-128">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="3a6b5-129">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="3a6b5-129">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
