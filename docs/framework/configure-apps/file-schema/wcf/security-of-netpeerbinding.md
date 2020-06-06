---
title: <security> de <netPeerBinding>
ms.date: 03/30/2017
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
ms.openlocfilehash: 3d1ac85073c44f683fe0c054737c5ec7ed1cbf52
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738660"
---
# <a name="security-of-netpeerbinding"></a><span data-ttu-id="b57cc-102">\<security> de \<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="b57cc-102">\<security> of \<netPeerBinding></span></span>
<span data-ttu-id="b57cc-103">Define la configuración de seguridad de [\<netPeerTcpBinding>](netpeertcpbinding.md) , incluido el tipo de autenticación utilizado y la seguridad utilizada para el transporte del mensaje.</span><span class="sxs-lookup"><span data-stu-id="b57cc-103">Defines the security settings of the [\<netPeerTcpBinding>](netpeertcpbinding.md), including the type of authentication used and the security used for the message transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="b57cc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b57cc-104">Syntax</span></span>  
  
```xml  
<netPeerBinding>
  <binding>
    <security mode="Message/None/Transport//TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b57cc-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b57cc-105">Attributes and Elements</span></span>  
 <span data-ttu-id="b57cc-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b57cc-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b57cc-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="b57cc-107">Attributes</span></span>  
  
|<span data-ttu-id="b57cc-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="b57cc-108">Attribute</span></span>|<span data-ttu-id="b57cc-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="b57cc-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b57cc-110">mode</span><span class="sxs-lookup"><span data-stu-id="b57cc-110">mode</span></span>|<span data-ttu-id="b57cc-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="b57cc-111">Optional.</span></span> <span data-ttu-id="b57cc-112">Especifica el tipo de seguridad utilizado por pares configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="b57cc-112">Specifies the type of security used by peers configured with this binding.</span></span> <span data-ttu-id="b57cc-113">El valor predeterminado es `Message`.</span><span class="sxs-lookup"><span data-stu-id="b57cc-113">The default value is `Message`.</span></span> <span data-ttu-id="b57cc-114">Este atributo es del tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="b57cc-114">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="b57cc-115">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="b57cc-115">mode Attribute</span></span>  
  
|<span data-ttu-id="b57cc-116">Value</span><span class="sxs-lookup"><span data-stu-id="b57cc-116">Value</span></span>|<span data-ttu-id="b57cc-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="b57cc-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b57cc-118">Message</span><span class="sxs-lookup"><span data-stu-id="b57cc-118">Message</span></span>|<span data-ttu-id="b57cc-119">La seguridad SOAP proporciona autenticación, integridad y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="b57cc-119">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|<span data-ttu-id="b57cc-120">None</span><span class="sxs-lookup"><span data-stu-id="b57cc-120">None</span></span>|<span data-ttu-id="b57cc-121">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="b57cc-121">Security is disabled.</span></span>|  
|<span data-ttu-id="b57cc-122">Transporte</span><span class="sxs-lookup"><span data-stu-id="b57cc-122">Transport</span></span>|<span data-ttu-id="b57cc-123">La seguridad se proporciona utilizando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b57cc-123">Security is provided using HTTPS.</span></span>|  
|<span data-ttu-id="b57cc-124">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="b57cc-124">TransportWithMessageCredential</span></span>|<span data-ttu-id="b57cc-125">HTTPS proporciona autenticación y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="b57cc-125">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="b57cc-126">Los mensajes SOAP proporcionan tipos de credencial enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="b57cc-126">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b57cc-127">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b57cc-127">Child Elements</span></span>  
  
|<span data-ttu-id="b57cc-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="b57cc-128">Element</span></span>|<span data-ttu-id="b57cc-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="b57cc-129">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-netpeertcpbinding.md)|<span data-ttu-id="b57cc-130">Define el tipo de transporte para mensajes seguros enviados por pares configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="b57cc-130">Defines the transport type for secured messages sent by peers configured with this binding.</span></span> <span data-ttu-id="b57cc-131">Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="b57cc-131">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b57cc-132">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b57cc-132">Parent Elements</span></span>  
  
|<span data-ttu-id="b57cc-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="b57cc-133">Element</span></span>|<span data-ttu-id="b57cc-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="b57cc-134">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="b57cc-135">Define todas las funciones de enlace de [\<netPeerTcpBinding>](netpeertcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="b57cc-135">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b57cc-136">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b57cc-136">Remarks</span></span>  
 <span data-ttu-id="b57cc-137">La seguridad puede ser específica de los mensajes o del transporte.</span><span class="sxs-lookup"><span data-stu-id="b57cc-137">Security can be either message- or transport-specific.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b57cc-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b57cc-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.PeerSecuritySettings>
- [<span data-ttu-id="b57cc-139">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="b57cc-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="b57cc-140">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="b57cc-140">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="b57cc-141">Enlaces</span><span class="sxs-lookup"><span data-stu-id="b57cc-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b57cc-142">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="b57cc-142">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="b57cc-143">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="b57cc-143">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
