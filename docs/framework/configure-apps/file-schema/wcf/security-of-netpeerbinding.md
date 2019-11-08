---
title: <security> de <netPeerBinding>
ms.date: 03/30/2017
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
ms.openlocfilehash: 3d1ac85073c44f683fe0c054737c5ec7ed1cbf52
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738660"
---
# <a name="security-of-netpeerbinding"></a><span data-ttu-id="7493b-102">\<> de seguridad de \<netPeerBinding ></span><span class="sxs-lookup"><span data-stu-id="7493b-102">\<security> of \<netPeerBinding></span></span>
<span data-ttu-id="7493b-103">Define la configuración de seguridad del [\<netPeerTcpBinding >](netpeertcpbinding.md), incluido el tipo de autenticación utilizado y la seguridad utilizada para el transporte del mensaje.</span><span class="sxs-lookup"><span data-stu-id="7493b-103">Defines the security settings of the [\<netPeerTcpBinding>](netpeertcpbinding.md), including the type of authentication used and the security used for the message transport.</span></span>  
  
<span data-ttu-id="7493b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7493b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7493b-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="7493b-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7493b-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**enlaces**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="7493b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="7493b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netPeerTcpBinding**](netpeertcpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="7493b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)</span></span>\
<span data-ttu-id="7493b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**enlace** ></span><span class="sxs-lookup"><span data-stu-id="7493b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="7493b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**seguridad** ></span><span class="sxs-lookup"><span data-stu-id="7493b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7493b-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7493b-110">Syntax</span></span>  
  
```xml  
<netPeerBinding>
  <binding>
    <security mode="Message/None/Transport//TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7493b-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7493b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="7493b-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7493b-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7493b-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="7493b-113">Attributes</span></span>  
  
|<span data-ttu-id="7493b-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="7493b-114">Attribute</span></span>|<span data-ttu-id="7493b-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="7493b-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7493b-116">modo</span><span class="sxs-lookup"><span data-stu-id="7493b-116">mode</span></span>|<span data-ttu-id="7493b-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="7493b-117">Optional.</span></span> <span data-ttu-id="7493b-118">Especifica el tipo de seguridad utilizado por pares configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="7493b-118">Specifies the type of security used by peers configured with this binding.</span></span> <span data-ttu-id="7493b-119">El valor predeterminado es `Message`.</span><span class="sxs-lookup"><span data-stu-id="7493b-119">The default value is `Message`.</span></span> <span data-ttu-id="7493b-120">Este atributo es del tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="7493b-120">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="7493b-121">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="7493b-121">mode Attribute</span></span>  
  
|<span data-ttu-id="7493b-122">Valor</span><span class="sxs-lookup"><span data-stu-id="7493b-122">Value</span></span>|<span data-ttu-id="7493b-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="7493b-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7493b-124">Mensaje</span><span class="sxs-lookup"><span data-stu-id="7493b-124">Message</span></span>|<span data-ttu-id="7493b-125">La seguridad SOAP proporciona autenticación, integridad y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="7493b-125">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|<span data-ttu-id="7493b-126">Ninguno</span><span class="sxs-lookup"><span data-stu-id="7493b-126">None</span></span>|<span data-ttu-id="7493b-127">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="7493b-127">Security is disabled.</span></span>|  
|<span data-ttu-id="7493b-128">Transporte</span><span class="sxs-lookup"><span data-stu-id="7493b-128">Transport</span></span>|<span data-ttu-id="7493b-129">La seguridad se proporciona utilizando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="7493b-129">Security is provided using HTTPS.</span></span>|  
|<span data-ttu-id="7493b-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="7493b-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="7493b-131">HTTPS proporciona autenticación y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="7493b-131">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="7493b-132">Los mensajes SOAP proporcionan tipos de credencial enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="7493b-132">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7493b-133">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7493b-133">Child Elements</span></span>  
  
|<span data-ttu-id="7493b-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="7493b-134">Element</span></span>|<span data-ttu-id="7493b-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="7493b-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7493b-136">> de transporte de \<</span><span class="sxs-lookup"><span data-stu-id="7493b-136">\<transport></span></span>](transport-of-netpeertcpbinding.md)|<span data-ttu-id="7493b-137">Define el tipo de transporte para mensajes seguros enviados por pares configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="7493b-137">Defines the transport type for secured messages sent by peers configured with this binding.</span></span> <span data-ttu-id="7493b-138">Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="7493b-138">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7493b-139">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7493b-139">Parent Elements</span></span>  
  
|<span data-ttu-id="7493b-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="7493b-140">Element</span></span>|<span data-ttu-id="7493b-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="7493b-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7493b-142">\<> de enlace</span><span class="sxs-lookup"><span data-stu-id="7493b-142">\<binding></span></span>](bindings.md)|<span data-ttu-id="7493b-143">Define todas las funciones de enlace del [\<netPeerTcpBinding >](netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="7493b-143">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7493b-144">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7493b-144">Remarks</span></span>  
 <span data-ttu-id="7493b-145">La seguridad puede ser específica de los mensajes o del transporte.</span><span class="sxs-lookup"><span data-stu-id="7493b-145">Security can be either message- or transport-specific.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7493b-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="7493b-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.PeerSecuritySettings>
- [<span data-ttu-id="7493b-147">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="7493b-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="7493b-148">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="7493b-148">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="7493b-149">Enlaces</span><span class="sxs-lookup"><span data-stu-id="7493b-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="7493b-150">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="7493b-150">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="7493b-151">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="7493b-151">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="7493b-152">\<> de enlace</span><span class="sxs-lookup"><span data-stu-id="7493b-152">\<binding></span></span>](bindings.md)
