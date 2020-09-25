---
title: <security> de <netPeerBinding>
ms.date: 03/30/2017
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
ms.openlocfilehash: 543c57d6b2dba1ff5934b49e0e219cf2e5cad153
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91170030"
---
# <a name="security-of-netpeerbinding"></a><span data-ttu-id="cb7a0-102">\<security> de \<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="cb7a0-102">\<security> of \<netPeerBinding></span></span>

<span data-ttu-id="cb7a0-103">Define la configuración de seguridad de [\<netPeerTcpBinding>](netpeertcpbinding.md) , incluido el tipo de autenticación utilizado y la seguridad utilizada para el transporte del mensaje.</span><span class="sxs-lookup"><span data-stu-id="cb7a0-103">Defines the security settings of the [\<netPeerTcpBinding>](netpeertcpbinding.md), including the type of authentication used and the security used for the message transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="cb7a0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cb7a0-104">Syntax</span></span>  
  
```xml  
<netPeerBinding>
  <binding>
    <security mode="Message/None/Transport//TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cb7a0-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="cb7a0-105">Attributes and Elements</span></span>  

 <span data-ttu-id="cb7a0-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="cb7a0-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cb7a0-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="cb7a0-107">Attributes</span></span>  
  
|<span data-ttu-id="cb7a0-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="cb7a0-108">Attribute</span></span>|<span data-ttu-id="cb7a0-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="cb7a0-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cb7a0-110">mode</span><span class="sxs-lookup"><span data-stu-id="cb7a0-110">mode</span></span>|<span data-ttu-id="cb7a0-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="cb7a0-111">Optional.</span></span> <span data-ttu-id="cb7a0-112">Especifica el tipo de seguridad utilizado por pares configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="cb7a0-112">Specifies the type of security used by peers configured with this binding.</span></span> <span data-ttu-id="cb7a0-113">El valor predeterminado es `Message`.</span><span class="sxs-lookup"><span data-stu-id="cb7a0-113">The default value is `Message`.</span></span> <span data-ttu-id="cb7a0-114">Este atributo es del tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="cb7a0-114">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="cb7a0-115">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="cb7a0-115">mode Attribute</span></span>  
  
|<span data-ttu-id="cb7a0-116">Value</span><span class="sxs-lookup"><span data-stu-id="cb7a0-116">Value</span></span>|<span data-ttu-id="cb7a0-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="cb7a0-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cb7a0-118">Mensaje</span><span class="sxs-lookup"><span data-stu-id="cb7a0-118">Message</span></span>|<span data-ttu-id="cb7a0-119">La seguridad SOAP proporciona autenticación, integridad y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="cb7a0-119">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|<span data-ttu-id="cb7a0-120">None</span><span class="sxs-lookup"><span data-stu-id="cb7a0-120">None</span></span>|<span data-ttu-id="cb7a0-121">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="cb7a0-121">Security is disabled.</span></span>|  
|<span data-ttu-id="cb7a0-122">Transporte</span><span class="sxs-lookup"><span data-stu-id="cb7a0-122">Transport</span></span>|<span data-ttu-id="cb7a0-123">La seguridad se proporciona utilizando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="cb7a0-123">Security is provided using HTTPS.</span></span>|  
|<span data-ttu-id="cb7a0-124">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="cb7a0-124">TransportWithMessageCredential</span></span>|<span data-ttu-id="cb7a0-125">HTTPS proporciona autenticación y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="cb7a0-125">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="cb7a0-126">Los mensajes SOAP proporcionan tipos de credencial enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="cb7a0-126">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cb7a0-127">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="cb7a0-127">Child Elements</span></span>  
  
|<span data-ttu-id="cb7a0-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="cb7a0-128">Element</span></span>|<span data-ttu-id="cb7a0-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="cb7a0-129">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-netpeertcpbinding.md)|<span data-ttu-id="cb7a0-130">Define el tipo de transporte para mensajes seguros enviados por pares configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="cb7a0-130">Defines the transport type for secured messages sent by peers configured with this binding.</span></span> <span data-ttu-id="cb7a0-131">Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="cb7a0-131">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cb7a0-132">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="cb7a0-132">Parent Elements</span></span>  
  
|<span data-ttu-id="cb7a0-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="cb7a0-133">Element</span></span>|<span data-ttu-id="cb7a0-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="cb7a0-134">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="cb7a0-135">Define todas las funciones de enlace de [\<netPeerTcpBinding>](netpeertcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="cb7a0-135">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb7a0-136">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cb7a0-136">Remarks</span></span>  

 <span data-ttu-id="cb7a0-137">La seguridad puede ser específica de los mensajes o del transporte.</span><span class="sxs-lookup"><span data-stu-id="cb7a0-137">Security can be either message- or transport-specific.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb7a0-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cb7a0-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.PeerSecuritySettings>
- [<span data-ttu-id="cb7a0-139">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="cb7a0-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="cb7a0-140">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="cb7a0-140">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="cb7a0-141">Enlaces</span><span class="sxs-lookup"><span data-stu-id="cb7a0-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="cb7a0-142">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="cb7a0-142">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="cb7a0-143">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="cb7a0-143">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
