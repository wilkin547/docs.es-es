---
description: 'Más información sobre: <security> de <peerTransport>'
title: <security> de <peerTransport>
ms.date: 03/30/2017
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
ms.openlocfilehash: 592f886377a2d5f2008be900a9e7586385fb3782
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786829"
---
# <a name="security-of-peertransport"></a><span data-ttu-id="a1408-103">\<security> de \<peerTransport></span><span class="sxs-lookup"><span data-stu-id="a1408-103">\<security> of \<peerTransport></span></span>

<span data-ttu-id="a1408-104">Contiene la configuración de seguridad asociada con un canal del mismo nivel, incluido el tipo de autenticación utilizado y la seguridad utilizada para el transporte del mensaje.</span><span class="sxs-lookup"><span data-stu-id="a1408-104">Contains the security settings associated with a peer channel, including the type of authentication used and the security used for the message transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peerTransport>**](peertransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="a1408-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a1408-105">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/TransportWithMessageCredential">
  <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a1408-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a1408-106">Attributes and Elements</span></span>  

 <span data-ttu-id="a1408-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a1408-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a1408-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="a1408-108">Attributes</span></span>  
  
|<span data-ttu-id="a1408-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="a1408-109">Attribute</span></span>|<span data-ttu-id="a1408-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="a1408-110">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="a1408-111">Especifica el tipo de seguridad que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="a1408-111">Specifies the type of security to be applied.</span></span> <span data-ttu-id="a1408-112">El valor predeterminado es Mensaje.</span><span class="sxs-lookup"><span data-stu-id="a1408-112">The default value is Message.</span></span> <span data-ttu-id="a1408-113">Este atributo es del tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="a1408-113">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="a1408-114">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="a1408-114">mode Attribute</span></span>  
  
|<span data-ttu-id="a1408-115">Value</span><span class="sxs-lookup"><span data-stu-id="a1408-115">Value</span></span>|<span data-ttu-id="a1408-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="a1408-116">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="a1408-117">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="a1408-117">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="a1408-118">La seguridad se proporciona utilizando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a1408-118">Security is provided using HTTPS.</span></span>|  
|`Message`|<span data-ttu-id="a1408-119">La seguridad SOAP proporciona autenticación, integridad y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="a1408-119">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="a1408-120">HTTPS proporciona autenticación y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="a1408-120">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="a1408-121">Los mensajes SOAP proporcionan tipos de credencial enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="a1408-121">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a1408-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a1408-122">Child Elements</span></span>  
  
|<span data-ttu-id="a1408-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="a1408-123">Element</span></span>|<span data-ttu-id="a1408-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="a1408-124">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-peertransport.md)|<span data-ttu-id="a1408-125">Define un transporte del mismo nivel para un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="a1408-125">Defines a peer transport for a custom binding.</span></span> <span data-ttu-id="a1408-126">Este elemento tiene un atributo `clientCredentialType` que especifica las credenciales que se van a usar al interactuar con un servicio.</span><span class="sxs-lookup"><span data-stu-id="a1408-126">This element has a `clientCredentialType` attribute that specifies the credentials to be used when interacting with a service.</span></span> <span data-ttu-id="a1408-127">Este atributo es del tipo <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="a1408-127">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span><br /><br /> <span data-ttu-id="a1408-128">Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="a1408-128">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a1408-129">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a1408-129">Parent Elements</span></span>  
  
|<span data-ttu-id="a1408-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="a1408-130">Element</span></span>|<span data-ttu-id="a1408-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="a1408-131">Description</span></span>|  
|-------------|-----------------|  
|[\<peerTransport>](peertransport.md)|<span data-ttu-id="a1408-132">Define un transporte del mismo nivel para un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="a1408-132">Defines a peer transport for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a1408-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1408-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="a1408-134">Seguridad de transporte</span><span class="sxs-lookup"><span data-stu-id="a1408-134">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="a1408-135">Transportes</span><span class="sxs-lookup"><span data-stu-id="a1408-135">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="a1408-136">Elección del transporte</span><span class="sxs-lookup"><span data-stu-id="a1408-136">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="a1408-137">Enlaces</span><span class="sxs-lookup"><span data-stu-id="a1408-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a1408-138">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="a1408-138">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="a1408-139">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="a1408-139">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
