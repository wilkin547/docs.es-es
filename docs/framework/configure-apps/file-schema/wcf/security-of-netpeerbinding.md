---
title: <security> de <netPeerBinding>
ms.date: 03/30/2017
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
ms.openlocfilehash: be5ebacec466caf8d8a77bf552f42da1861e77a1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936626"
---
# <a name="security-of-netpeerbinding"></a><span data-ttu-id="93de5-102">\<> de seguridad \<de netPeerBinding ></span><span class="sxs-lookup"><span data-stu-id="93de5-102">\<security> of \<netPeerBinding></span></span>
<span data-ttu-id="93de5-103">Define la configuración de seguridad del [ \<> netPeerTcpBinding](netpeertcpbinding.md), incluido el tipo de autenticación utilizado y la seguridad utilizada para el transporte del mensaje.</span><span class="sxs-lookup"><span data-stu-id="93de5-103">Defines the security settings of the [\<netPeerTcpBinding>](netpeertcpbinding.md), including the type of authentication used and the security used for the message transport.</span></span>  
  
 <span data-ttu-id="93de5-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="93de5-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="93de5-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="93de5-105">\<bindings></span></span>  
<span data-ttu-id="93de5-106">\<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="93de5-106">\<netPeerBinding></span></span>  
<span data-ttu-id="93de5-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="93de5-107">\<binding></span></span>  
<span data-ttu-id="93de5-108">\<> de seguridad</span><span class="sxs-lookup"><span data-stu-id="93de5-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93de5-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="93de5-109">Syntax</span></span>  
  
```xml  
<netPeerBinding>
  <binding>
    <security mode="Message/None/Transport//TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="93de5-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="93de5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="93de5-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="93de5-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="93de5-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="93de5-112">Attributes</span></span>  
  
|<span data-ttu-id="93de5-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="93de5-113">Attribute</span></span>|<span data-ttu-id="93de5-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="93de5-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="93de5-115">modo</span><span class="sxs-lookup"><span data-stu-id="93de5-115">mode</span></span>|<span data-ttu-id="93de5-116">Opcional.</span><span class="sxs-lookup"><span data-stu-id="93de5-116">Optional.</span></span> <span data-ttu-id="93de5-117">Especifica el tipo de seguridad utilizado por pares configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="93de5-117">Specifies the type of security used by peers configured with this binding.</span></span> <span data-ttu-id="93de5-118">El valor predeterminado es `Message`.</span><span class="sxs-lookup"><span data-stu-id="93de5-118">The default value is `Message`.</span></span> <span data-ttu-id="93de5-119">Este atributo es del tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="93de5-119">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="93de5-120">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="93de5-120">mode Attribute</span></span>  
  
|<span data-ttu-id="93de5-121">Valor</span><span class="sxs-lookup"><span data-stu-id="93de5-121">Value</span></span>|<span data-ttu-id="93de5-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="93de5-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="93de5-123">Message</span><span class="sxs-lookup"><span data-stu-id="93de5-123">Message</span></span>|<span data-ttu-id="93de5-124">La seguridad SOAP proporciona autenticación, integridad y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="93de5-124">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|<span data-ttu-id="93de5-125">None</span><span class="sxs-lookup"><span data-stu-id="93de5-125">None</span></span>|<span data-ttu-id="93de5-126">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="93de5-126">Security is disabled.</span></span>|  
|<span data-ttu-id="93de5-127">Transporte</span><span class="sxs-lookup"><span data-stu-id="93de5-127">Transport</span></span>|<span data-ttu-id="93de5-128">La seguridad se proporciona utilizando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="93de5-128">Security is provided using HTTPS.</span></span>|  
|<span data-ttu-id="93de5-129">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="93de5-129">TransportWithMessageCredential</span></span>|<span data-ttu-id="93de5-130">HTTPS proporciona autenticación y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="93de5-130">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="93de5-131">Los mensajes SOAP proporcionan tipos de credencial enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="93de5-131">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="93de5-132">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="93de5-132">Child Elements</span></span>  
  
|<span data-ttu-id="93de5-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="93de5-133">Element</span></span>|<span data-ttu-id="93de5-134">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="93de5-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="93de5-135">\<> de transporte</span><span class="sxs-lookup"><span data-stu-id="93de5-135">\<transport></span></span>](transport-of-netpeertcpbinding.md)|<span data-ttu-id="93de5-136">Define el tipo de transporte para mensajes seguros enviados por pares configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="93de5-136">Defines the transport type for secured messages sent by peers configured with this binding.</span></span> <span data-ttu-id="93de5-137">Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="93de5-137">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="93de5-138">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="93de5-138">Parent Elements</span></span>  
  
|<span data-ttu-id="93de5-139">Elemento</span><span class="sxs-lookup"><span data-stu-id="93de5-139">Element</span></span>|<span data-ttu-id="93de5-140">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="93de5-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="93de5-141">\<binding></span><span class="sxs-lookup"><span data-stu-id="93de5-141">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="93de5-142">Define todas las funciones de enlace del [ \<> netPeerTcpBinding](netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="93de5-142">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93de5-143">Comentarios</span><span class="sxs-lookup"><span data-stu-id="93de5-143">Remarks</span></span>  
 <span data-ttu-id="93de5-144">La seguridad puede ser específica de los mensajes o del transporte.</span><span class="sxs-lookup"><span data-stu-id="93de5-144">Security can be either message- or transport-specific.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93de5-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="93de5-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.PeerSecuritySettings>
- [<span data-ttu-id="93de5-146">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="93de5-146">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="93de5-147">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="93de5-147">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="93de5-148">Enlaces</span><span class="sxs-lookup"><span data-stu-id="93de5-148">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="93de5-149">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="93de5-149">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="93de5-150">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="93de5-150">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="93de5-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="93de5-151">\<binding></span></span>](../../../misc/binding.md)
