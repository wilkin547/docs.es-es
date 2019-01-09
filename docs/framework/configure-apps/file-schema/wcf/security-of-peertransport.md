---
title: '&lt;security&gt; de &lt;peerTransport&gt;'
ms.date: 03/30/2017
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
ms.openlocfilehash: 901a1d0b29fa6ea7d9e520b379dc7c7ff1d1e522
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151961"
---
# <a name="ltsecuritygt-of-ltpeertransportgt"></a><span data-ttu-id="28005-102">&lt;security&gt; de &lt;peerTransport&gt;</span><span class="sxs-lookup"><span data-stu-id="28005-102">&lt;security&gt; of &lt;peerTransport&gt;</span></span>
<span data-ttu-id="28005-103">Contiene la configuración de seguridad asociada con un canal del mismo nivel, incluido el tipo de autenticación utilizado y la seguridad utilizada para el transporte del mensaje.</span><span class="sxs-lookup"><span data-stu-id="28005-103">Contains the security settings associated with a peer channel, including the type of authentication used and the security used for the message transport.</span></span>  
  
 <span data-ttu-id="28005-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="28005-104">\<system.serviceModel></span></span>  
<span data-ttu-id="28005-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="28005-105">\<bindings></span></span>  
<span data-ttu-id="28005-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="28005-106">\<customBinding></span></span>  
<span data-ttu-id="28005-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="28005-107">\<binding></span></span>  
<span data-ttu-id="28005-108">\<peerTransport ></span><span class="sxs-lookup"><span data-stu-id="28005-108">\<peerTransport></span></span>  
<span data-ttu-id="28005-109">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="28005-109">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28005-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="28005-110">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/TransportWithMessageCredential">
  <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="28005-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="28005-111">Attributes and Elements</span></span>  
 <span data-ttu-id="28005-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="28005-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="28005-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="28005-113">Attributes</span></span>  
  
|<span data-ttu-id="28005-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="28005-114">Attribute</span></span>|<span data-ttu-id="28005-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="28005-115">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="28005-116">Especifica el tipo de seguridad que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="28005-116">Specifies the type of security to be applied.</span></span> <span data-ttu-id="28005-117">El valor predeterminado es Mensaje.</span><span class="sxs-lookup"><span data-stu-id="28005-117">The default value is Message.</span></span> <span data-ttu-id="28005-118">Este atributo es del tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="28005-118">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="28005-119">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="28005-119">mode Attribute</span></span>  
  
|<span data-ttu-id="28005-120">Valor</span><span class="sxs-lookup"><span data-stu-id="28005-120">Value</span></span>|<span data-ttu-id="28005-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="28005-121">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="28005-122">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="28005-122">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="28005-123">La seguridad se proporciona utilizando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="28005-123">Security is provided using HTTPS.</span></span>|  
|`Message`|<span data-ttu-id="28005-124">La seguridad SOAP proporciona autenticación, integridad y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="28005-124">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="28005-125">HTTPS proporciona autenticación y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="28005-125">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="28005-126">Los mensajes SOAP proporcionan tipos de credencial enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="28005-126">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="28005-127">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="28005-127">Child Elements</span></span>  
  
|<span data-ttu-id="28005-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="28005-128">Element</span></span>|<span data-ttu-id="28005-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="28005-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="28005-130">\<transporte ></span><span class="sxs-lookup"><span data-stu-id="28005-130">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-peertransport.md)|<span data-ttu-id="28005-131">Define un transporte del mismo nivel para un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="28005-131">Defines a peer transport for a custom binding.</span></span> <span data-ttu-id="28005-132">Este elemento tiene un atributo `clientCredentialType` que especifica las credenciales que se van a usar al interactuar con un servicio.</span><span class="sxs-lookup"><span data-stu-id="28005-132">This element has a `clientCredentialType` attribute that specifies the credentials to be used when interacting with a service.</span></span> <span data-ttu-id="28005-133">Este atributo es del tipo <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="28005-133">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span><br /><br /> <span data-ttu-id="28005-134">Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="28005-134">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="28005-135">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="28005-135">Parent Elements</span></span>  
  
|<span data-ttu-id="28005-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="28005-136">Element</span></span>|<span data-ttu-id="28005-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="28005-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="28005-138">\<peerTransport ></span><span class="sxs-lookup"><span data-stu-id="28005-138">\<peerTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peertransport.md)|<span data-ttu-id="28005-139">Define un transporte del mismo nivel para un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="28005-139">Defines a peer transport for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="28005-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="28005-140">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="28005-141">Seguridad de transporte</span><span class="sxs-lookup"><span data-stu-id="28005-141">Transport Security</span></span>](../../../../../docs/framework/wcf/feature-details/transport-security.md)  
 [<span data-ttu-id="28005-142">Transportes</span><span class="sxs-lookup"><span data-stu-id="28005-142">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [<span data-ttu-id="28005-143">Elección del transporte</span><span class="sxs-lookup"><span data-stu-id="28005-143">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [<span data-ttu-id="28005-144">Enlaces</span><span class="sxs-lookup"><span data-stu-id="28005-144">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="28005-145">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="28005-145">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="28005-146">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="28005-146">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="28005-147">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="28005-147">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
