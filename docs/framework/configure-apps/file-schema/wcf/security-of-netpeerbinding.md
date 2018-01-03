---
title: Elemento &lt;security&gt; de &lt;netPeerBinding&gt;
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
caps.latest.revision: "14"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: b9228ccbed2b0f612986d59b72c920d57f38f69a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltsecuritygt-of-ltnetpeerbindinggt"></a><span data-ttu-id="fc210-102">Elemento &lt;security&gt; de &lt;netPeerBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="fc210-102">&lt;security&gt; of &lt;netPeerBinding&gt;</span></span>
<span data-ttu-id="fc210-103">Define la configuración de seguridad de la [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md), incluido el tipo de autenticación utiliza y la seguridad para el transporte de mensajes.</span><span class="sxs-lookup"><span data-stu-id="fc210-103">Defines the security settings of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md), including the type of authentication used and the security used for the message transport.</span></span>  
  
 <span data-ttu-id="fc210-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="fc210-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="fc210-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="fc210-105">\<bindings></span></span>  
<span data-ttu-id="fc210-106">\<netPeerBinding ></span><span class="sxs-lookup"><span data-stu-id="fc210-106">\<netPeerBinding></span></span>  
<span data-ttu-id="fc210-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="fc210-107">\<binding></span></span>  
<span data-ttu-id="fc210-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="fc210-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc210-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fc210-109">Syntax</span></span>  
  
```xml  
<netPeerBinding>  
    <binding>  
        <security mode="Message/None/Transport//TransportWithMessageCredential">  
            <transport credentialType="Certificate/Password" />  
        </security>  
    </binding>  
</netPeerBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fc210-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fc210-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fc210-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fc210-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fc210-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="fc210-112">Attributes</span></span>  
  
|<span data-ttu-id="fc210-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="fc210-113">Attribute</span></span>|<span data-ttu-id="fc210-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="fc210-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fc210-115">modo</span><span class="sxs-lookup"><span data-stu-id="fc210-115">mode</span></span>|<span data-ttu-id="fc210-116">Opcional.</span><span class="sxs-lookup"><span data-stu-id="fc210-116">Optional.</span></span> <span data-ttu-id="fc210-117">Especifica el tipo de seguridad utilizado por pares configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="fc210-117">Specifies the type of security used by peers configured with this binding.</span></span> <span data-ttu-id="fc210-118">El valor predeterminado es `Message`.</span><span class="sxs-lookup"><span data-stu-id="fc210-118">The default value is `Message`.</span></span> <span data-ttu-id="fc210-119">Este atributo es del tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="fc210-119">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="fc210-120">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="fc210-120">mode Attribute</span></span>  
  
|<span data-ttu-id="fc210-121">Valor</span><span class="sxs-lookup"><span data-stu-id="fc210-121">Value</span></span>|<span data-ttu-id="fc210-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="fc210-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fc210-123">Mensaje</span><span class="sxs-lookup"><span data-stu-id="fc210-123">Message</span></span>|<span data-ttu-id="fc210-124">La seguridad SOAP proporciona autenticación, integridad y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="fc210-124">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|<span data-ttu-id="fc210-125">Ninguna</span><span class="sxs-lookup"><span data-stu-id="fc210-125">None</span></span>|<span data-ttu-id="fc210-126">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="fc210-126">Security is disabled.</span></span>|  
|<span data-ttu-id="fc210-127">Transporte</span><span class="sxs-lookup"><span data-stu-id="fc210-127">Transport</span></span>|<span data-ttu-id="fc210-128">La seguridad se proporciona utilizando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="fc210-128">Security is provided using HTTPS.</span></span>|  
|<span data-ttu-id="fc210-129">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="fc210-129">TransportWithMessageCredential</span></span>|<span data-ttu-id="fc210-130">HTTPS proporciona autenticación y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="fc210-130">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="fc210-131">Los mensajes SOAP proporcionan tipos de credencial enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="fc210-131">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fc210-132">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fc210-132">Child Elements</span></span>  
  
|<span data-ttu-id="fc210-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="fc210-133">Element</span></span>|<span data-ttu-id="fc210-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="fc210-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fc210-135">\<transporte ></span><span class="sxs-lookup"><span data-stu-id="fc210-135">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netpeertcpbinding.md)|<span data-ttu-id="fc210-136">Define el tipo de transporte para mensajes seguros enviados por pares configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="fc210-136">Defines the transport type for secured messages sent by peers configured with this binding.</span></span> <span data-ttu-id="fc210-137">Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="fc210-137">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fc210-138">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fc210-138">Parent Elements</span></span>  
  
|<span data-ttu-id="fc210-139">Elemento</span><span class="sxs-lookup"><span data-stu-id="fc210-139">Element</span></span>|<span data-ttu-id="fc210-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="fc210-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fc210-141">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="fc210-141">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="fc210-142">Define todas las funcionalidades de enlace de la [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="fc210-142">Defines all binding capabilities of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc210-143">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fc210-143">Remarks</span></span>  
 <span data-ttu-id="fc210-144">La seguridad puede ser específica de los mensajes o del transporte.</span><span class="sxs-lookup"><span data-stu-id="fc210-144">Security can be either message- or transport-specific.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc210-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc210-145">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement>  
 <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>  
 <xref:System.ServiceModel.PeerSecuritySettings>  
 [<span data-ttu-id="fc210-146">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="fc210-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="fc210-147">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="fc210-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="fc210-148">Enlaces</span><span class="sxs-lookup"><span data-stu-id="fc210-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="fc210-149">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="fc210-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="fc210-150">Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="fc210-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="fc210-151">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="fc210-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
