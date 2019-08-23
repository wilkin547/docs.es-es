---
title: <security> de <peerTransport>
ms.date: 03/30/2017
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
ms.openlocfilehash: bdd3b236c9bae198f8027c4ca0c0fa5b70d30342
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936638"
---
# <a name="security-of-peertransport"></a><span data-ttu-id="0a64f-102">\<> de seguridad \<de peerTransport ></span><span class="sxs-lookup"><span data-stu-id="0a64f-102">\<security> of \<peerTransport></span></span>
<span data-ttu-id="0a64f-103">Contiene la configuración de seguridad asociada con un canal del mismo nivel, incluido el tipo de autenticación utilizado y la seguridad utilizada para el transporte del mensaje.</span><span class="sxs-lookup"><span data-stu-id="0a64f-103">Contains the security settings associated with a peer channel, including the type of authentication used and the security used for the message transport.</span></span>  
  
 <span data-ttu-id="0a64f-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0a64f-104">\<system.serviceModel></span></span>  
<span data-ttu-id="0a64f-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="0a64f-105">\<bindings></span></span>  
<span data-ttu-id="0a64f-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="0a64f-106">\<customBinding></span></span>  
<span data-ttu-id="0a64f-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="0a64f-107">\<binding></span></span>  
<span data-ttu-id="0a64f-108">\<peerTransport></span><span class="sxs-lookup"><span data-stu-id="0a64f-108">\<peerTransport></span></span>  
<span data-ttu-id="0a64f-109">\<> de seguridad</span><span class="sxs-lookup"><span data-stu-id="0a64f-109">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a64f-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0a64f-110">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/TransportWithMessageCredential">
  <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0a64f-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0a64f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0a64f-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0a64f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0a64f-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="0a64f-113">Attributes</span></span>  
  
|<span data-ttu-id="0a64f-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="0a64f-114">Attribute</span></span>|<span data-ttu-id="0a64f-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0a64f-115">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="0a64f-116">Especifica el tipo de seguridad que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="0a64f-116">Specifies the type of security to be applied.</span></span> <span data-ttu-id="0a64f-117">El valor predeterminado es Mensaje.</span><span class="sxs-lookup"><span data-stu-id="0a64f-117">The default value is Message.</span></span> <span data-ttu-id="0a64f-118">Este atributo es del tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="0a64f-118">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="0a64f-119">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="0a64f-119">mode Attribute</span></span>  
  
|<span data-ttu-id="0a64f-120">Valor</span><span class="sxs-lookup"><span data-stu-id="0a64f-120">Value</span></span>|<span data-ttu-id="0a64f-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0a64f-121">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="0a64f-122">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="0a64f-122">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="0a64f-123">La seguridad se proporciona utilizando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="0a64f-123">Security is provided using HTTPS.</span></span>|  
|`Message`|<span data-ttu-id="0a64f-124">La seguridad SOAP proporciona autenticación, integridad y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="0a64f-124">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="0a64f-125">HTTPS proporciona autenticación y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="0a64f-125">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="0a64f-126">Los mensajes SOAP proporcionan tipos de credencial enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="0a64f-126">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0a64f-127">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0a64f-127">Child Elements</span></span>  
  
|<span data-ttu-id="0a64f-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="0a64f-128">Element</span></span>|<span data-ttu-id="0a64f-129">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0a64f-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0a64f-130">\<> de transporte</span><span class="sxs-lookup"><span data-stu-id="0a64f-130">\<transport></span></span>](transport-of-peertransport.md)|<span data-ttu-id="0a64f-131">Define un transporte del mismo nivel para un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="0a64f-131">Defines a peer transport for a custom binding.</span></span> <span data-ttu-id="0a64f-132">Este elemento tiene un atributo `clientCredentialType` que especifica las credenciales que se van a usar al interactuar con un servicio.</span><span class="sxs-lookup"><span data-stu-id="0a64f-132">This element has a `clientCredentialType` attribute that specifies the credentials to be used when interacting with a service.</span></span> <span data-ttu-id="0a64f-133">Este atributo es del tipo <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="0a64f-133">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span><br /><br /> <span data-ttu-id="0a64f-134">Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="0a64f-134">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0a64f-135">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0a64f-135">Parent Elements</span></span>  
  
|<span data-ttu-id="0a64f-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="0a64f-136">Element</span></span>|<span data-ttu-id="0a64f-137">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0a64f-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0a64f-138">\<peerTransport></span><span class="sxs-lookup"><span data-stu-id="0a64f-138">\<peerTransport></span></span>](peertransport.md)|<span data-ttu-id="0a64f-139">Define un transporte del mismo nivel para un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="0a64f-139">Defines a peer transport for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0a64f-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a64f-140">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="0a64f-141">Seguridad de transporte</span><span class="sxs-lookup"><span data-stu-id="0a64f-141">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="0a64f-142">Transportes</span><span class="sxs-lookup"><span data-stu-id="0a64f-142">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="0a64f-143">Elección del transporte</span><span class="sxs-lookup"><span data-stu-id="0a64f-143">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="0a64f-144">Enlaces</span><span class="sxs-lookup"><span data-stu-id="0a64f-144">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="0a64f-145">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="0a64f-145">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="0a64f-146">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="0a64f-146">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="0a64f-147">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="0a64f-147">\<customBinding></span></span>](custombinding.md)
