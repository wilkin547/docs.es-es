---
title: <security> de <peerTransport>
ms.date: 03/30/2017
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
ms.openlocfilehash: f37c336b0e42993e1eef3f06e2f919705f425a2e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169965"
---
# <a name="security-of-peertransport"></a><span data-ttu-id="2bb35-102">\<security> de \<peerTransport></span><span class="sxs-lookup"><span data-stu-id="2bb35-102">\<security> of \<peerTransport></span></span>

<span data-ttu-id="2bb35-103">Contiene la configuración de seguridad asociada con un canal del mismo nivel, incluido el tipo de autenticación utilizado y la seguridad utilizada para el transporte del mensaje.</span><span class="sxs-lookup"><span data-stu-id="2bb35-103">Contains the security settings associated with a peer channel, including the type of authentication used and the security used for the message transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peerTransport>**](peertransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="2bb35-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2bb35-104">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/TransportWithMessageCredential">
  <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2bb35-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2bb35-105">Attributes and Elements</span></span>  

 <span data-ttu-id="2bb35-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2bb35-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2bb35-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="2bb35-107">Attributes</span></span>  
  
|<span data-ttu-id="2bb35-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="2bb35-108">Attribute</span></span>|<span data-ttu-id="2bb35-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="2bb35-109">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="2bb35-110">Especifica el tipo de seguridad que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="2bb35-110">Specifies the type of security to be applied.</span></span> <span data-ttu-id="2bb35-111">El valor predeterminado es Mensaje.</span><span class="sxs-lookup"><span data-stu-id="2bb35-111">The default value is Message.</span></span> <span data-ttu-id="2bb35-112">Este atributo es del tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="2bb35-112">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="2bb35-113">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="2bb35-113">mode Attribute</span></span>  
  
|<span data-ttu-id="2bb35-114">Value</span><span class="sxs-lookup"><span data-stu-id="2bb35-114">Value</span></span>|<span data-ttu-id="2bb35-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="2bb35-115">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="2bb35-116">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="2bb35-116">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="2bb35-117">La seguridad se proporciona utilizando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="2bb35-117">Security is provided using HTTPS.</span></span>|  
|`Message`|<span data-ttu-id="2bb35-118">La seguridad SOAP proporciona autenticación, integridad y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="2bb35-118">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="2bb35-119">HTTPS proporciona autenticación y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="2bb35-119">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="2bb35-120">Los mensajes SOAP proporcionan tipos de credencial enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="2bb35-120">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2bb35-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2bb35-121">Child Elements</span></span>  
  
|<span data-ttu-id="2bb35-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="2bb35-122">Element</span></span>|<span data-ttu-id="2bb35-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="2bb35-123">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-peertransport.md)|<span data-ttu-id="2bb35-124">Define un transporte del mismo nivel para un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="2bb35-124">Defines a peer transport for a custom binding.</span></span> <span data-ttu-id="2bb35-125">Este elemento tiene un atributo `clientCredentialType` que especifica las credenciales que se van a usar al interactuar con un servicio.</span><span class="sxs-lookup"><span data-stu-id="2bb35-125">This element has a `clientCredentialType` attribute that specifies the credentials to be used when interacting with a service.</span></span> <span data-ttu-id="2bb35-126">Este atributo es del tipo <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="2bb35-126">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span><br /><br /> <span data-ttu-id="2bb35-127">Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="2bb35-127">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2bb35-128">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2bb35-128">Parent Elements</span></span>  
  
|<span data-ttu-id="2bb35-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="2bb35-129">Element</span></span>|<span data-ttu-id="2bb35-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="2bb35-130">Description</span></span>|  
|-------------|-----------------|  
|[\<peerTransport>](peertransport.md)|<span data-ttu-id="2bb35-131">Define un transporte del mismo nivel para un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="2bb35-131">Defines a peer transport for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2bb35-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2bb35-132">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="2bb35-133">Seguridad de transporte</span><span class="sxs-lookup"><span data-stu-id="2bb35-133">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="2bb35-134">Transportes</span><span class="sxs-lookup"><span data-stu-id="2bb35-134">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="2bb35-135">Elección del transporte</span><span class="sxs-lookup"><span data-stu-id="2bb35-135">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="2bb35-136">Enlaces</span><span class="sxs-lookup"><span data-stu-id="2bb35-136">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="2bb35-137">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="2bb35-137">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="2bb35-138">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="2bb35-138">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
