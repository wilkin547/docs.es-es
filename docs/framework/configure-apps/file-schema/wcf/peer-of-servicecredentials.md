---
description: 'Más información sobre: <peer> de <serviceCredentials>'
title: <peer> de <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: b134e21d-e5b5-458e-9309-626dbf8db4ed
ms.openlocfilehash: 4d959f5061bb8069623b277219576dbd77ea52c3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683741"
---
# <a name="peer-of-servicecredentials"></a><span data-ttu-id="de04c-103">\<peer> de \<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="de04c-103">\<peer> of \<serviceCredentials></span></span>

<span data-ttu-id="de04c-104">Especifica las credenciales actuales de un nodo del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="de04c-104">Specifies the current credentials for a peer node.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peer>**  
  
## <a name="syntax"></a><span data-ttu-id="de04c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="de04c-105">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="de04c-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="de04c-106">Attributes and Elements</span></span>  

 <span data-ttu-id="de04c-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="de04c-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="de04c-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="de04c-108">Attributes</span></span>  

 <span data-ttu-id="de04c-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="de04c-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="de04c-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="de04c-110">Child Elements</span></span>  
  
|<span data-ttu-id="de04c-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="de04c-111">Element</span></span>|<span data-ttu-id="de04c-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="de04c-112">Description</span></span>|  
|-------------|-----------------|  
|[\<certificate>](certificate-of-peer.md)|<span data-ttu-id="de04c-113">Especifica un certificado X.509 que se va a usar para firmar y cifrar los mensajes para los servicios punto a punto.</span><span class="sxs-lookup"><span data-stu-id="de04c-113">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer services.</span></span> <span data-ttu-id="de04c-114">.</span><span class="sxs-lookup"><span data-stu-id="de04c-114">.</span></span>|  
|[\<messageSenderAuthentication>](messagesenderauthentication.md)|<span data-ttu-id="de04c-115">Especifica las opciones de autenticación para los remitentes del mensaje.</span><span class="sxs-lookup"><span data-stu-id="de04c-115">Specifies authentication options for message senders.</span></span>|  
|[\<peerAuthentication>](peerauthentication.md)|<span data-ttu-id="de04c-116">Especifica las opciones de autenticación para los servicios del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="de04c-116">Specifies authentication options for peer services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="de04c-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="de04c-117">Parent Elements</span></span>  
  
|<span data-ttu-id="de04c-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="de04c-118">Element</span></span>|<span data-ttu-id="de04c-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="de04c-119">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="de04c-120">Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.</span><span class="sxs-lookup"><span data-stu-id="de04c-120">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="de04c-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="de04c-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="de04c-122">Conexión de redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="de04c-122">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="de04c-123">[Autenticación del mensaje del canal del mismo nivel](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="de04c-123">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="de04c-124">[Autenticación personalizada de canal del mismo nivel](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="de04c-124">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="de04c-125">Protección de las aplicaciones de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="de04c-125">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="de04c-126">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="de04c-126">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
