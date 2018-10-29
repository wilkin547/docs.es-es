---
title: Elemento &lt;security&gt; de &lt;netPeerBinding&gt;
ms.date: 03/30/2017
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
ms.openlocfilehash: d32b6426009c403d74ca3a05d3c3ba7be9163cae
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2018
ms.locfileid: "50197332"
---
# <a name="ltsecuritygt-of-ltnetpeerbindinggt"></a><span data-ttu-id="7e761-102">Elemento &lt;security&gt; de &lt;netPeerBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="7e761-102">&lt;security&gt; of &lt;netPeerBinding&gt;</span></span>
<span data-ttu-id="7e761-103">Define la configuración de seguridad de la [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md), incluido el tipo de autenticación utilizado y la seguridad utilizada para el transporte de mensajes.</span><span class="sxs-lookup"><span data-stu-id="7e761-103">Defines the security settings of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md), including the type of authentication used and the security used for the message transport.</span></span>  
  
 <span data-ttu-id="7e761-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="7e761-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7e761-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="7e761-105">\<bindings></span></span>  
<span data-ttu-id="7e761-106">\<netPeerBinding ></span><span class="sxs-lookup"><span data-stu-id="7e761-106">\<netPeerBinding></span></span>  
<span data-ttu-id="7e761-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="7e761-107">\<binding></span></span>  
<span data-ttu-id="7e761-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="7e761-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e761-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7e761-109">Syntax</span></span>  
  
```xml  
<netPeerBinding>  
    <binding>  
        <security mode="Message/None/Transport//TransportWithMessageCredential">  
            <transport credentialType="Certificate/Password" />  
        </security>  
    </binding>  
</netPeerBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7e761-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7e761-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7e761-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7e761-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7e761-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="7e761-112">Attributes</span></span>  
  
|<span data-ttu-id="7e761-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="7e761-113">Attribute</span></span>|<span data-ttu-id="7e761-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="7e761-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7e761-115">modo</span><span class="sxs-lookup"><span data-stu-id="7e761-115">mode</span></span>|<span data-ttu-id="7e761-116">Opcional.</span><span class="sxs-lookup"><span data-stu-id="7e761-116">Optional.</span></span> <span data-ttu-id="7e761-117">Especifica el tipo de seguridad utilizado por pares configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="7e761-117">Specifies the type of security used by peers configured with this binding.</span></span> <span data-ttu-id="7e761-118">El valor predeterminado es `Message`.</span><span class="sxs-lookup"><span data-stu-id="7e761-118">The default value is `Message`.</span></span> <span data-ttu-id="7e761-119">Este atributo es del tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="7e761-119">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="7e761-120">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="7e761-120">mode Attribute</span></span>  
  
|<span data-ttu-id="7e761-121">Valor</span><span class="sxs-lookup"><span data-stu-id="7e761-121">Value</span></span>|<span data-ttu-id="7e761-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="7e761-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7e761-123">Mensaje</span><span class="sxs-lookup"><span data-stu-id="7e761-123">Message</span></span>|<span data-ttu-id="7e761-124">La seguridad SOAP proporciona autenticación, integridad y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="7e761-124">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|<span data-ttu-id="7e761-125">Ninguna</span><span class="sxs-lookup"><span data-stu-id="7e761-125">None</span></span>|<span data-ttu-id="7e761-126">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="7e761-126">Security is disabled.</span></span>|  
|<span data-ttu-id="7e761-127">Transporte</span><span class="sxs-lookup"><span data-stu-id="7e761-127">Transport</span></span>|<span data-ttu-id="7e761-128">La seguridad se proporciona utilizando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="7e761-128">Security is provided using HTTPS.</span></span>|  
|<span data-ttu-id="7e761-129">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="7e761-129">TransportWithMessageCredential</span></span>|<span data-ttu-id="7e761-130">HTTPS proporciona autenticación y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="7e761-130">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="7e761-131">Los mensajes SOAP proporcionan tipos de credencial enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="7e761-131">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7e761-132">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7e761-132">Child Elements</span></span>  
  
|<span data-ttu-id="7e761-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="7e761-133">Element</span></span>|<span data-ttu-id="7e761-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="7e761-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7e761-135">\<transporte ></span><span class="sxs-lookup"><span data-stu-id="7e761-135">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netpeertcpbinding.md)|<span data-ttu-id="7e761-136">Define el tipo de transporte para mensajes seguros enviados por pares configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="7e761-136">Defines the transport type for secured messages sent by peers configured with this binding.</span></span> <span data-ttu-id="7e761-137">Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="7e761-137">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7e761-138">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7e761-138">Parent Elements</span></span>  
  
|<span data-ttu-id="7e761-139">Elemento</span><span class="sxs-lookup"><span data-stu-id="7e761-139">Element</span></span>|<span data-ttu-id="7e761-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="7e761-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7e761-141">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="7e761-141">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="7e761-142">Define todas las capacidades de enlace de la [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="7e761-142">Defines all binding capabilities of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e761-143">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7e761-143">Remarks</span></span>  
 <span data-ttu-id="7e761-144">La seguridad puede ser específica de los mensajes o del transporte.</span><span class="sxs-lookup"><span data-stu-id="7e761-144">Security can be either message- or transport-specific.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e761-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e761-145">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement>  
 <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>  
 <xref:System.ServiceModel.PeerSecuritySettings>  
 [<span data-ttu-id="7e761-146">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="7e761-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="7e761-147">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="7e761-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="7e761-148">Enlaces</span><span class="sxs-lookup"><span data-stu-id="7e761-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="7e761-149">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="7e761-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="7e761-150">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="7e761-150">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="7e761-151">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="7e761-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
