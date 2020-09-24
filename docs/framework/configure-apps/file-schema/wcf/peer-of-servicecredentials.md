---
title: <peer> de <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: b134e21d-e5b5-458e-9309-626dbf8db4ed
ms.openlocfilehash: 7f6669d3f53a6ee0d189786fa9ca3625fdedd127
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162483"
---
# <a name="peer-of-servicecredentials"></a><span data-ttu-id="87a6c-102">\<peer> de \<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="87a6c-102">\<peer> of \<serviceCredentials></span></span>

<span data-ttu-id="87a6c-103">Especifica las credenciales actuales de un nodo del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="87a6c-103">Specifies the current credentials for a peer node.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peer>**  
  
## <a name="syntax"></a><span data-ttu-id="87a6c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="87a6c-104">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="87a6c-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="87a6c-105">Attributes and Elements</span></span>  

 <span data-ttu-id="87a6c-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="87a6c-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="87a6c-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="87a6c-107">Attributes</span></span>  

 <span data-ttu-id="87a6c-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="87a6c-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="87a6c-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="87a6c-109">Child Elements</span></span>  
  
|<span data-ttu-id="87a6c-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="87a6c-110">Element</span></span>|<span data-ttu-id="87a6c-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="87a6c-111">Description</span></span>|  
|-------------|-----------------|  
|[\<certificate>](certificate-of-peer.md)|<span data-ttu-id="87a6c-112">Especifica un certificado X.509 que se va a usar para firmar y cifrar los mensajes para los servicios punto a punto.</span><span class="sxs-lookup"><span data-stu-id="87a6c-112">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer services.</span></span> <span data-ttu-id="87a6c-113">.</span><span class="sxs-lookup"><span data-stu-id="87a6c-113">.</span></span>|  
|[\<messageSenderAuthentication>](messagesenderauthentication.md)|<span data-ttu-id="87a6c-114">Especifica las opciones de autenticación para los remitentes del mensaje.</span><span class="sxs-lookup"><span data-stu-id="87a6c-114">Specifies authentication options for message senders.</span></span>|  
|[\<peerAuthentication>](peerauthentication.md)|<span data-ttu-id="87a6c-115">Especifica las opciones de autenticación para los servicios del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="87a6c-115">Specifies authentication options for peer services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="87a6c-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="87a6c-116">Parent Elements</span></span>  
  
|<span data-ttu-id="87a6c-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="87a6c-117">Element</span></span>|<span data-ttu-id="87a6c-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="87a6c-118">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="87a6c-119">Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.</span><span class="sxs-lookup"><span data-stu-id="87a6c-119">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="87a6c-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="87a6c-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="87a6c-121">Redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="87a6c-121">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="87a6c-122">[Autenticación del mensaje del canal del mismo nivel](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="87a6c-122">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="87a6c-123">[Autenticación personalizada de canal del mismo nivel](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="87a6c-123">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="87a6c-124">Protección de las aplicaciones de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="87a6c-124">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="87a6c-125">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="87a6c-125">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
