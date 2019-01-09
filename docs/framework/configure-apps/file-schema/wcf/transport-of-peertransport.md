---
title: '&lt;transport&gt; de &lt;peerTransport&gt;'
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: c82e91543920522f0ed6232036ec1b5a94189fa8
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54148948"
---
# <a name="lttransportgt-of-ltpeertransportgt"></a><span data-ttu-id="f69ad-102">&lt;transport&gt; de &lt;peerTransport&gt;</span><span class="sxs-lookup"><span data-stu-id="f69ad-102">&lt;transport&gt; of &lt;peerTransport&gt;</span></span>
<span data-ttu-id="f69ad-103">Especifica el tipo de transporte para mensajes seguros enviados por pares configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="f69ad-103">Specifies the transport type for secured messages sent by peers configured with this binding.</span></span>  
  
 <span data-ttu-id="f69ad-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f69ad-104">\<system.serviceModel></span></span>  
<span data-ttu-id="f69ad-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="f69ad-105">\<bindings></span></span>  
<span data-ttu-id="f69ad-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="f69ad-106">\<customBinding></span></span>  
<span data-ttu-id="f69ad-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="f69ad-107">\<binding></span></span>  
<span data-ttu-id="f69ad-108">\<peerTransport ></span><span class="sxs-lookup"><span data-stu-id="f69ad-108">\<peerTransport></span></span>  
<span data-ttu-id="f69ad-109">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="f69ad-109">\<security></span></span>  
<span data-ttu-id="f69ad-110">\<transporte ></span><span class="sxs-lookup"><span data-stu-id="f69ad-110">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f69ad-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f69ad-111">Syntax</span></span>  
  
```xml  
<security>
  <transport credentialType="Certificate/Password" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f69ad-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f69ad-112">Attributes and Elements</span></span>  
 <span data-ttu-id="f69ad-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f69ad-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f69ad-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="f69ad-114">Attributes</span></span>  
  
|<span data-ttu-id="f69ad-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="f69ad-115">Attribute</span></span>|<span data-ttu-id="f69ad-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="f69ad-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f69ad-117">credentialType</span><span class="sxs-lookup"><span data-stu-id="f69ad-117">credentialType</span></span>|<span data-ttu-id="f69ad-118">Opcional.</span><span class="sxs-lookup"><span data-stu-id="f69ad-118">Optional.</span></span> <span data-ttu-id="f69ad-119">Especifica el tipo de credenciales utilizado para comprobar mensajes enviados con el transporte del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="f69ad-119">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="f69ad-120">Este atributo es del tipo <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="f69ad-120">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="f69ad-121">Atributo credentialType</span><span class="sxs-lookup"><span data-stu-id="f69ad-121">credentialType Attribute</span></span>  
  
|<span data-ttu-id="f69ad-122">Valor</span><span class="sxs-lookup"><span data-stu-id="f69ad-122">Value</span></span>|<span data-ttu-id="f69ad-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="f69ad-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f69ad-124">Certificado</span><span class="sxs-lookup"><span data-stu-id="f69ad-124">Certificate</span></span>|<span data-ttu-id="f69ad-125">La autenticación del transporte de canal del mismo nivel requiere un certificado X509.</span><span class="sxs-lookup"><span data-stu-id="f69ad-125">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="f69ad-126">Contraseña</span><span class="sxs-lookup"><span data-stu-id="f69ad-126">Password</span></span>|<span data-ttu-id="f69ad-127">La autenticación del transporte de canal del mismo nivel requiere una contraseña correcta.</span><span class="sxs-lookup"><span data-stu-id="f69ad-127">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f69ad-128">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f69ad-128">Child Elements</span></span>  
 <span data-ttu-id="f69ad-129">Ninguna</span><span class="sxs-lookup"><span data-stu-id="f69ad-129">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f69ad-130">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f69ad-130">Parent Elements</span></span>  
  
|<span data-ttu-id="f69ad-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="f69ad-131">Element</span></span>|<span data-ttu-id="f69ad-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="f69ad-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f69ad-133">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="f69ad-133">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)|<span data-ttu-id="f69ad-134">Define la configuración de seguridad de un transporte del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="f69ad-134">Defines the security settings for a peer transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f69ad-135">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f69ad-135">Remarks</span></span>  
 <span data-ttu-id="f69ad-136">Este elemento se establece únicamente si el atributo de modo de [ \<seguridad >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md) está establecido en `Transport` o `TransportWithMessageCredential`.</span><span class="sxs-lookup"><span data-stu-id="f69ad-136">This element is set only if the mode attribute of [\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md) is set to `Transport` or `TransportWithMessageCredential`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f69ad-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="f69ad-137">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>  
 <xref:System.ServiceModel.PeerTransportSecuritySettings>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="f69ad-138">Seguridad de transporte</span><span class="sxs-lookup"><span data-stu-id="f69ad-138">Transport Security</span></span>](../../../../../docs/framework/wcf/feature-details/transport-security.md)  
 [<span data-ttu-id="f69ad-139">Transportes</span><span class="sxs-lookup"><span data-stu-id="f69ad-139">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [<span data-ttu-id="f69ad-140">Elección del transporte</span><span class="sxs-lookup"><span data-stu-id="f69ad-140">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [<span data-ttu-id="f69ad-141">Enlaces</span><span class="sxs-lookup"><span data-stu-id="f69ad-141">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="f69ad-142">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="f69ad-142">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="f69ad-143">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="f69ad-143">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="f69ad-144">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="f69ad-144">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
