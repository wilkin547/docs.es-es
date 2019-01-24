---
title: '&lt;transport&gt; de &lt;peerTransport&gt;'
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: d02bb1cb4c20ab7dc482001ea7ce21180394eee7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54716588"
---
# <a name="lttransportgt-of-ltpeertransportgt"></a><span data-ttu-id="6c460-102">&lt;transport&gt; de &lt;peerTransport&gt;</span><span class="sxs-lookup"><span data-stu-id="6c460-102">&lt;transport&gt; of &lt;peerTransport&gt;</span></span>
<span data-ttu-id="6c460-103">Especifica el tipo de transporte para mensajes seguros enviados por pares configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="6c460-103">Specifies the transport type for secured messages sent by peers configured with this binding.</span></span>  
  
 <span data-ttu-id="6c460-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6c460-104">\<system.serviceModel></span></span>  
<span data-ttu-id="6c460-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="6c460-105">\<bindings></span></span>  
<span data-ttu-id="6c460-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="6c460-106">\<customBinding></span></span>  
<span data-ttu-id="6c460-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="6c460-107">\<binding></span></span>  
<span data-ttu-id="6c460-108">\<peerTransport></span><span class="sxs-lookup"><span data-stu-id="6c460-108">\<peerTransport></span></span>  
<span data-ttu-id="6c460-109">\<security></span><span class="sxs-lookup"><span data-stu-id="6c460-109">\<security></span></span>  
<span data-ttu-id="6c460-110">\<transport></span><span class="sxs-lookup"><span data-stu-id="6c460-110">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c460-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6c460-111">Syntax</span></span>  
  
```xml  
<security>
  <transport credentialType="Certificate/Password" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6c460-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6c460-112">Attributes and Elements</span></span>  
 <span data-ttu-id="6c460-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6c460-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6c460-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="6c460-114">Attributes</span></span>  
  
|<span data-ttu-id="6c460-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="6c460-115">Attribute</span></span>|<span data-ttu-id="6c460-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="6c460-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6c460-117">credentialType</span><span class="sxs-lookup"><span data-stu-id="6c460-117">credentialType</span></span>|<span data-ttu-id="6c460-118">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6c460-118">Optional.</span></span> <span data-ttu-id="6c460-119">Especifica el tipo de credenciales utilizado para comprobar mensajes enviados con el transporte del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="6c460-119">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="6c460-120">Este atributo es del tipo <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="6c460-120">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="6c460-121">Atributo credentialType</span><span class="sxs-lookup"><span data-stu-id="6c460-121">credentialType Attribute</span></span>  
  
|<span data-ttu-id="6c460-122">Valor</span><span class="sxs-lookup"><span data-stu-id="6c460-122">Value</span></span>|<span data-ttu-id="6c460-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="6c460-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6c460-124">Certificado</span><span class="sxs-lookup"><span data-stu-id="6c460-124">Certificate</span></span>|<span data-ttu-id="6c460-125">La autenticación del transporte de canal del mismo nivel requiere un certificado X509.</span><span class="sxs-lookup"><span data-stu-id="6c460-125">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="6c460-126">Contraseña</span><span class="sxs-lookup"><span data-stu-id="6c460-126">Password</span></span>|<span data-ttu-id="6c460-127">La autenticación del transporte de canal del mismo nivel requiere una contraseña correcta.</span><span class="sxs-lookup"><span data-stu-id="6c460-127">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6c460-128">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6c460-128">Child Elements</span></span>  
 <span data-ttu-id="6c460-129">Ninguna</span><span class="sxs-lookup"><span data-stu-id="6c460-129">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6c460-130">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6c460-130">Parent Elements</span></span>  
  
|<span data-ttu-id="6c460-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="6c460-131">Element</span></span>|<span data-ttu-id="6c460-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="6c460-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c460-133">\<security></span><span class="sxs-lookup"><span data-stu-id="6c460-133">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)|<span data-ttu-id="6c460-134">Define la configuración de seguridad de un transporte del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="6c460-134">Defines the security settings for a peer transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c460-135">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6c460-135">Remarks</span></span>  
 <span data-ttu-id="6c460-136">Este elemento se establece únicamente si el atributo de modo de [ \<seguridad >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md) está establecido en `Transport` o `TransportWithMessageCredential`.</span><span class="sxs-lookup"><span data-stu-id="6c460-136">This element is set only if the mode attribute of [\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md) is set to `Transport` or `TransportWithMessageCredential`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c460-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c460-137">See also</span></span>
- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="6c460-138">Seguridad de transporte</span><span class="sxs-lookup"><span data-stu-id="6c460-138">Transport Security</span></span>](../../../../../docs/framework/wcf/feature-details/transport-security.md)
- [<span data-ttu-id="6c460-139">Transportes</span><span class="sxs-lookup"><span data-stu-id="6c460-139">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="6c460-140">Elección del transporte</span><span class="sxs-lookup"><span data-stu-id="6c460-140">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="6c460-141">Enlaces</span><span class="sxs-lookup"><span data-stu-id="6c460-141">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="6c460-142">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="6c460-142">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="6c460-143">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="6c460-143">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="6c460-144">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="6c460-144">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
