---
description: 'Más información sobre: <security> de <netPeerBinding>'
title: <security> de <netPeerBinding>
ms.date: 03/30/2017
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
ms.openlocfilehash: f67cfa445a5a605b99783cfd67dd1bae6e17b51e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786842"
---
# <a name="security-of-netpeerbinding"></a><span data-ttu-id="0e129-103">\<security> de \<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="0e129-103">\<security> of \<netPeerBinding></span></span>

<span data-ttu-id="0e129-104">Define la configuración de seguridad de [\<netPeerTcpBinding>](netpeertcpbinding.md) , incluido el tipo de autenticación utilizado y la seguridad utilizada para el transporte del mensaje.</span><span class="sxs-lookup"><span data-stu-id="0e129-104">Defines the security settings of the [\<netPeerTcpBinding>](netpeertcpbinding.md), including the type of authentication used and the security used for the message transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="0e129-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0e129-105">Syntax</span></span>  
  
```xml  
<netPeerBinding>
  <binding>
    <security mode="Message/None/Transport//TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0e129-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0e129-106">Attributes and Elements</span></span>  

 <span data-ttu-id="0e129-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0e129-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0e129-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="0e129-108">Attributes</span></span>  
  
|<span data-ttu-id="0e129-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="0e129-109">Attribute</span></span>|<span data-ttu-id="0e129-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="0e129-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0e129-111">mode</span><span class="sxs-lookup"><span data-stu-id="0e129-111">mode</span></span>|<span data-ttu-id="0e129-112">Opcional.</span><span class="sxs-lookup"><span data-stu-id="0e129-112">Optional.</span></span> <span data-ttu-id="0e129-113">Especifica el tipo de seguridad utilizado por pares configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="0e129-113">Specifies the type of security used by peers configured with this binding.</span></span> <span data-ttu-id="0e129-114">El valor predeterminado es `Message`.</span><span class="sxs-lookup"><span data-stu-id="0e129-114">The default value is `Message`.</span></span> <span data-ttu-id="0e129-115">Este atributo es del tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="0e129-115">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="0e129-116">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="0e129-116">mode Attribute</span></span>  
  
|<span data-ttu-id="0e129-117">Value</span><span class="sxs-lookup"><span data-stu-id="0e129-117">Value</span></span>|<span data-ttu-id="0e129-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="0e129-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0e129-119">Message</span><span class="sxs-lookup"><span data-stu-id="0e129-119">Message</span></span>|<span data-ttu-id="0e129-120">La seguridad SOAP proporciona autenticación, integridad y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="0e129-120">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|<span data-ttu-id="0e129-121">None</span><span class="sxs-lookup"><span data-stu-id="0e129-121">None</span></span>|<span data-ttu-id="0e129-122">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="0e129-122">Security is disabled.</span></span>|  
|<span data-ttu-id="0e129-123">Transporte</span><span class="sxs-lookup"><span data-stu-id="0e129-123">Transport</span></span>|<span data-ttu-id="0e129-124">La seguridad se proporciona utilizando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="0e129-124">Security is provided using HTTPS.</span></span>|  
|<span data-ttu-id="0e129-125">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="0e129-125">TransportWithMessageCredential</span></span>|<span data-ttu-id="0e129-126">HTTPS proporciona autenticación y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="0e129-126">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="0e129-127">Los mensajes SOAP proporcionan tipos de credencial enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="0e129-127">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0e129-128">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0e129-128">Child Elements</span></span>  
  
|<span data-ttu-id="0e129-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="0e129-129">Element</span></span>|<span data-ttu-id="0e129-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="0e129-130">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-netpeertcpbinding.md)|<span data-ttu-id="0e129-131">Define el tipo de transporte para mensajes seguros enviados por pares configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="0e129-131">Defines the transport type for secured messages sent by peers configured with this binding.</span></span> <span data-ttu-id="0e129-132">Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="0e129-132">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0e129-133">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0e129-133">Parent Elements</span></span>  
  
|<span data-ttu-id="0e129-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="0e129-134">Element</span></span>|<span data-ttu-id="0e129-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="0e129-135">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="0e129-136">Define todas las funciones de enlace de [\<netPeerTcpBinding>](netpeertcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="0e129-136">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e129-137">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0e129-137">Remarks</span></span>  

 <span data-ttu-id="0e129-138">La seguridad puede ser específica de los mensajes o del transporte.</span><span class="sxs-lookup"><span data-stu-id="0e129-138">Security can be either message- or transport-specific.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e129-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e129-139">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.PeerSecuritySettings>
- [<span data-ttu-id="0e129-140">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="0e129-140">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="0e129-141">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="0e129-141">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="0e129-142">Enlaces</span><span class="sxs-lookup"><span data-stu-id="0e129-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="0e129-143">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="0e129-143">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="0e129-144">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="0e129-144">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
