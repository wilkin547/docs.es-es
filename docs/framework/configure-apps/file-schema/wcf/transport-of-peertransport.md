---
title: <transport> de <peerTransport>
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: 5dbc55db25c0c49d72ec2cd8dd1041a3f8705d8e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940645"
---
# <a name="transport-of-peertransport"></a><span data-ttu-id="3c30a-102">\<> de transporte \<de > peerTransport</span><span class="sxs-lookup"><span data-stu-id="3c30a-102">\<transport> of \<peerTransport></span></span>
<span data-ttu-id="3c30a-103">Especifica el tipo de transporte para mensajes seguros enviados por pares configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="3c30a-103">Specifies the transport type for secured messages sent by peers configured with this binding.</span></span>  
  
 <span data-ttu-id="3c30a-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3c30a-104">\<system.serviceModel></span></span>  
<span data-ttu-id="3c30a-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="3c30a-105">\<bindings></span></span>  
<span data-ttu-id="3c30a-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="3c30a-106">\<customBinding></span></span>  
<span data-ttu-id="3c30a-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="3c30a-107">\<binding></span></span>  
<span data-ttu-id="3c30a-108">\<peerTransport></span><span class="sxs-lookup"><span data-stu-id="3c30a-108">\<peerTransport></span></span>  
<span data-ttu-id="3c30a-109">\<> de seguridad</span><span class="sxs-lookup"><span data-stu-id="3c30a-109">\<security></span></span>  
<span data-ttu-id="3c30a-110">\<> de transporte</span><span class="sxs-lookup"><span data-stu-id="3c30a-110">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c30a-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3c30a-111">Syntax</span></span>  
  
```xml  
<security>
  <transport credentialType="Certificate/Password" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3c30a-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3c30a-112">Attributes and Elements</span></span>  
 <span data-ttu-id="3c30a-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3c30a-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3c30a-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="3c30a-114">Attributes</span></span>  
  
|<span data-ttu-id="3c30a-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="3c30a-115">Attribute</span></span>|<span data-ttu-id="3c30a-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3c30a-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3c30a-117">credentialType</span><span class="sxs-lookup"><span data-stu-id="3c30a-117">credentialType</span></span>|<span data-ttu-id="3c30a-118">Opcional.</span><span class="sxs-lookup"><span data-stu-id="3c30a-118">Optional.</span></span> <span data-ttu-id="3c30a-119">Especifica el tipo de credenciales utilizado para comprobar mensajes enviados con el transporte del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="3c30a-119">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="3c30a-120">Este atributo es del tipo <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="3c30a-120">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="3c30a-121">Atributo credentialType</span><span class="sxs-lookup"><span data-stu-id="3c30a-121">credentialType Attribute</span></span>  
  
|<span data-ttu-id="3c30a-122">Value</span><span class="sxs-lookup"><span data-stu-id="3c30a-122">Value</span></span>|<span data-ttu-id="3c30a-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3c30a-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3c30a-124">Certificate</span><span class="sxs-lookup"><span data-stu-id="3c30a-124">Certificate</span></span>|<span data-ttu-id="3c30a-125">La autenticación del transporte de canal del mismo nivel requiere un certificado X509.</span><span class="sxs-lookup"><span data-stu-id="3c30a-125">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="3c30a-126">Contraseña</span><span class="sxs-lookup"><span data-stu-id="3c30a-126">Password</span></span>|<span data-ttu-id="3c30a-127">La autenticación del transporte de canal del mismo nivel requiere una contraseña correcta.</span><span class="sxs-lookup"><span data-stu-id="3c30a-127">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3c30a-128">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3c30a-128">Child Elements</span></span>  
 <span data-ttu-id="3c30a-129">None</span><span class="sxs-lookup"><span data-stu-id="3c30a-129">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3c30a-130">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3c30a-130">Parent Elements</span></span>  
  
|<span data-ttu-id="3c30a-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="3c30a-131">Element</span></span>|<span data-ttu-id="3c30a-132">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3c30a-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3c30a-133">\<security></span><span class="sxs-lookup"><span data-stu-id="3c30a-133">\<security></span></span>](security-of-peertransport.md)|<span data-ttu-id="3c30a-134">Define la configuración de seguridad de un transporte del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="3c30a-134">Defines the security settings for a peer transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c30a-135">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3c30a-135">Remarks</span></span>  
 <span data-ttu-id="3c30a-136">Este elemento se establece solo si el atributo de modo del [ \<> de seguridad](security-of-peertransport.md) se establece en `Transport` o `TransportWithMessageCredential`.</span><span class="sxs-lookup"><span data-stu-id="3c30a-136">This element is set only if the mode attribute of [\<security>](security-of-peertransport.md) is set to `Transport` or `TransportWithMessageCredential`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c30a-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c30a-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="3c30a-138">Seguridad de transporte</span><span class="sxs-lookup"><span data-stu-id="3c30a-138">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="3c30a-139">Transportes</span><span class="sxs-lookup"><span data-stu-id="3c30a-139">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="3c30a-140">Elección del transporte</span><span class="sxs-lookup"><span data-stu-id="3c30a-140">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="3c30a-141">Enlaces</span><span class="sxs-lookup"><span data-stu-id="3c30a-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="3c30a-142">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="3c30a-142">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="3c30a-143">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="3c30a-143">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="3c30a-144">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="3c30a-144">\<customBinding></span></span>](custombinding.md)
