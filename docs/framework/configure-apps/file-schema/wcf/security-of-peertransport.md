---
title: <security> de <peerTransport>
ms.date: 03/30/2017
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
ms.openlocfilehash: 270ca844f586be256b6483653c868d1cc4396657
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399775"
---
# <a name="security-of-peertransport"></a><span data-ttu-id="4dcd6-102">\<> de seguridad \<de peerTransport ></span><span class="sxs-lookup"><span data-stu-id="4dcd6-102">\<security> of \<peerTransport></span></span>
<span data-ttu-id="4dcd6-103">Contiene la configuración de seguridad asociada con un canal del mismo nivel, incluido el tipo de autenticación utilizado y la seguridad utilizada para el transporte del mensaje.</span><span class="sxs-lookup"><span data-stu-id="4dcd6-103">Contains the security settings associated with a peer channel, including the type of authentication used and the security used for the message transport.</span></span>  
  
<span data-ttu-id="4dcd6-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4dcd6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4dcd6-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4dcd6-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4dcd6-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enlaces**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="4dcd6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="4dcd6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="4dcd6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="4dcd6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de enlace**</span><span class="sxs-lookup"><span data-stu-id="4dcd6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="4dcd6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> peerTransport**](peertransport.md)</span><span class="sxs-lookup"><span data-stu-id="4dcd6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peerTransport>**](peertransport.md)</span></span>\
<span data-ttu-id="4dcd6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de seguridad**</span><span class="sxs-lookup"><span data-stu-id="4dcd6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dcd6-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4dcd6-111">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/TransportWithMessageCredential">
  <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4dcd6-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4dcd6-112">Attributes and Elements</span></span>  
 <span data-ttu-id="4dcd6-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4dcd6-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4dcd6-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="4dcd6-114">Attributes</span></span>  
  
|<span data-ttu-id="4dcd6-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="4dcd6-115">Attribute</span></span>|<span data-ttu-id="4dcd6-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4dcd6-116">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="4dcd6-117">Especifica el tipo de seguridad que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="4dcd6-117">Specifies the type of security to be applied.</span></span> <span data-ttu-id="4dcd6-118">El valor predeterminado es Mensaje.</span><span class="sxs-lookup"><span data-stu-id="4dcd6-118">The default value is Message.</span></span> <span data-ttu-id="4dcd6-119">Este atributo es del tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="4dcd6-119">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="4dcd6-120">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="4dcd6-120">mode Attribute</span></span>  
  
|<span data-ttu-id="4dcd6-121">Valor</span><span class="sxs-lookup"><span data-stu-id="4dcd6-121">Value</span></span>|<span data-ttu-id="4dcd6-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4dcd6-122">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="4dcd6-123">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="4dcd6-123">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="4dcd6-124">La seguridad se proporciona utilizando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="4dcd6-124">Security is provided using HTTPS.</span></span>|  
|`Message`|<span data-ttu-id="4dcd6-125">La seguridad SOAP proporciona autenticación, integridad y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="4dcd6-125">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="4dcd6-126">HTTPS proporciona autenticación y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="4dcd6-126">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="4dcd6-127">Los mensajes SOAP proporcionan tipos de credencial enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="4dcd6-127">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4dcd6-128">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4dcd6-128">Child Elements</span></span>  
  
|<span data-ttu-id="4dcd6-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="4dcd6-129">Element</span></span>|<span data-ttu-id="4dcd6-130">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4dcd6-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4dcd6-131">\<> de transporte</span><span class="sxs-lookup"><span data-stu-id="4dcd6-131">\<transport></span></span>](transport-of-peertransport.md)|<span data-ttu-id="4dcd6-132">Define un transporte del mismo nivel para un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="4dcd6-132">Defines a peer transport for a custom binding.</span></span> <span data-ttu-id="4dcd6-133">Este elemento tiene un atributo `clientCredentialType` que especifica las credenciales que se van a usar al interactuar con un servicio.</span><span class="sxs-lookup"><span data-stu-id="4dcd6-133">This element has a `clientCredentialType` attribute that specifies the credentials to be used when interacting with a service.</span></span> <span data-ttu-id="4dcd6-134">Este atributo es del tipo <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="4dcd6-134">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span><br /><br /> <span data-ttu-id="4dcd6-135">Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="4dcd6-135">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4dcd6-136">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4dcd6-136">Parent Elements</span></span>  
  
|<span data-ttu-id="4dcd6-137">Elemento</span><span class="sxs-lookup"><span data-stu-id="4dcd6-137">Element</span></span>|<span data-ttu-id="4dcd6-138">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4dcd6-138">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4dcd6-139">\<peerTransport></span><span class="sxs-lookup"><span data-stu-id="4dcd6-139">\<peerTransport></span></span>](peertransport.md)|<span data-ttu-id="4dcd6-140">Define un transporte del mismo nivel para un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="4dcd6-140">Defines a peer transport for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4dcd6-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="4dcd6-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="4dcd6-142">Seguridad de transporte</span><span class="sxs-lookup"><span data-stu-id="4dcd6-142">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="4dcd6-143">Transportes</span><span class="sxs-lookup"><span data-stu-id="4dcd6-143">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="4dcd6-144">Elección del transporte</span><span class="sxs-lookup"><span data-stu-id="4dcd6-144">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="4dcd6-145">Enlaces</span><span class="sxs-lookup"><span data-stu-id="4dcd6-145">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="4dcd6-146">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="4dcd6-146">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="4dcd6-147">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="4dcd6-147">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="4dcd6-148">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="4dcd6-148">\<customBinding></span></span>](custombinding.md)
