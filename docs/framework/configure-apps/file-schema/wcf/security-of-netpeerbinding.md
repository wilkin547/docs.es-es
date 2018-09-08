---
title: Elemento &lt;security&gt; de &lt;netPeerBinding&gt;
ms.date: 03/30/2017
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 45000554226fcde753041fca283bfc8b1eeba5ce
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44196574"
---
# <a name="ltsecuritygt-of-ltnetpeerbindinggt"></a><span data-ttu-id="8482c-102">Elemento &lt;security&gt; de &lt;netPeerBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="8482c-102">&lt;security&gt; of &lt;netPeerBinding&gt;</span></span>
<span data-ttu-id="8482c-103">Define la configuración de seguridad de la [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md), incluido el tipo de autenticación utilizado y la seguridad utilizada para el transporte de mensajes.</span><span class="sxs-lookup"><span data-stu-id="8482c-103">Defines the security settings of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md), including the type of authentication used and the security used for the message transport.</span></span>  
  
 <span data-ttu-id="8482c-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8482c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8482c-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="8482c-105">\<bindings></span></span>  
<span data-ttu-id="8482c-106">\<netPeerBinding ></span><span class="sxs-lookup"><span data-stu-id="8482c-106">\<netPeerBinding></span></span>  
<span data-ttu-id="8482c-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="8482c-107">\<binding></span></span>  
<span data-ttu-id="8482c-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="8482c-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8482c-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8482c-109">Syntax</span></span>  
  
```xml  
<netPeerBinding>  
    <binding>  
        <security mode="Message/None/Transport//TransportWithMessageCredential">  
            <transport credentialType="Certificate/Password" />  
        </security>  
    </binding>  
</netPeerBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8482c-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8482c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8482c-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8482c-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8482c-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="8482c-112">Attributes</span></span>  
  
|<span data-ttu-id="8482c-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="8482c-113">Attribute</span></span>|<span data-ttu-id="8482c-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="8482c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8482c-115">modo</span><span class="sxs-lookup"><span data-stu-id="8482c-115">mode</span></span>|<span data-ttu-id="8482c-116">Opcional.</span><span class="sxs-lookup"><span data-stu-id="8482c-116">Optional.</span></span> <span data-ttu-id="8482c-117">Especifica el tipo de seguridad utilizado por pares configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="8482c-117">Specifies the type of security used by peers configured with this binding.</span></span> <span data-ttu-id="8482c-118">El valor predeterminado es `Message`.</span><span class="sxs-lookup"><span data-stu-id="8482c-118">The default value is `Message`.</span></span> <span data-ttu-id="8482c-119">Este atributo es del tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="8482c-119">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="8482c-120">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="8482c-120">mode Attribute</span></span>  
  
|<span data-ttu-id="8482c-121">Valor</span><span class="sxs-lookup"><span data-stu-id="8482c-121">Value</span></span>|<span data-ttu-id="8482c-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="8482c-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8482c-123">Mensaje</span><span class="sxs-lookup"><span data-stu-id="8482c-123">Message</span></span>|<span data-ttu-id="8482c-124">La seguridad SOAP proporciona autenticación, integridad y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="8482c-124">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|<span data-ttu-id="8482c-125">Ninguna</span><span class="sxs-lookup"><span data-stu-id="8482c-125">None</span></span>|<span data-ttu-id="8482c-126">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="8482c-126">Security is disabled.</span></span>|  
|<span data-ttu-id="8482c-127">Transporte</span><span class="sxs-lookup"><span data-stu-id="8482c-127">Transport</span></span>|<span data-ttu-id="8482c-128">La seguridad se proporciona utilizando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="8482c-128">Security is provided using HTTPS.</span></span>|  
|<span data-ttu-id="8482c-129">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="8482c-129">TransportWithMessageCredential</span></span>|<span data-ttu-id="8482c-130">HTTPS proporciona autenticación y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="8482c-130">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="8482c-131">Los mensajes SOAP proporcionan tipos de credencial enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="8482c-131">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8482c-132">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8482c-132">Child Elements</span></span>  
  
|<span data-ttu-id="8482c-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="8482c-133">Element</span></span>|<span data-ttu-id="8482c-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="8482c-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8482c-135">\<transporte ></span><span class="sxs-lookup"><span data-stu-id="8482c-135">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netpeertcpbinding.md)|<span data-ttu-id="8482c-136">Define el tipo de transporte para mensajes seguros enviados por pares configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="8482c-136">Defines the transport type for secured messages sent by peers configured with this binding.</span></span> <span data-ttu-id="8482c-137">Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="8482c-137">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8482c-138">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8482c-138">Parent Elements</span></span>  
  
|<span data-ttu-id="8482c-139">Elemento</span><span class="sxs-lookup"><span data-stu-id="8482c-139">Element</span></span>|<span data-ttu-id="8482c-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="8482c-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8482c-141">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="8482c-141">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="8482c-142">Define todas las capacidades de enlace de la [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="8482c-142">Defines all binding capabilities of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8482c-143">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8482c-143">Remarks</span></span>  
 <span data-ttu-id="8482c-144">La seguridad puede ser específica de los mensajes o del transporte.</span><span class="sxs-lookup"><span data-stu-id="8482c-144">Security can be either message- or transport-specific.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8482c-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="8482c-145">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement>  
 <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>  
 <xref:System.ServiceModel.PeerSecuritySettings>  
 [<span data-ttu-id="8482c-146">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="8482c-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="8482c-147">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="8482c-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="8482c-148">Enlaces</span><span class="sxs-lookup"><span data-stu-id="8482c-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="8482c-149">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="8482c-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="8482c-150">Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="8482c-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="8482c-151">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="8482c-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
