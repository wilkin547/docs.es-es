---
title: <transport> de <peerTransport>
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: 3b2c7716727f58abb81bf4d58b13189ac170cf7c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399287"
---
# <a name="transport-of-peertransport"></a><span data-ttu-id="6143d-102">\<> de transporte \<de > peerTransport</span><span class="sxs-lookup"><span data-stu-id="6143d-102">\<transport> of \<peerTransport></span></span>
<span data-ttu-id="6143d-103">Especifica el tipo de transporte para mensajes seguros enviados por pares configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="6143d-103">Specifies the transport type for secured messages sent by peers configured with this binding.</span></span>  
  
<span data-ttu-id="6143d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6143d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6143d-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="6143d-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="6143d-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enlaces**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="6143d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="6143d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="6143d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="6143d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de enlace**</span><span class="sxs-lookup"><span data-stu-id="6143d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="6143d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> peerTransport**](peertransport.md)</span><span class="sxs-lookup"><span data-stu-id="6143d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peerTransport>**](peertransport.md)</span></span>\
<span data-ttu-id="6143d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguridad**](security-of-peertransport.md)</span><span class="sxs-lookup"><span data-stu-id="6143d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-peertransport.md)</span></span>\
<span data-ttu-id="6143d-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de transporte**</span><span class="sxs-lookup"><span data-stu-id="6143d-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6143d-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6143d-112">Syntax</span></span>  
  
```xml  
<security>
  <transport credentialType="Certificate/Password" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6143d-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6143d-113">Attributes and Elements</span></span>  
 <span data-ttu-id="6143d-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6143d-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6143d-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="6143d-115">Attributes</span></span>  
  
|<span data-ttu-id="6143d-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="6143d-116">Attribute</span></span>|<span data-ttu-id="6143d-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="6143d-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6143d-118">credentialType</span><span class="sxs-lookup"><span data-stu-id="6143d-118">credentialType</span></span>|<span data-ttu-id="6143d-119">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6143d-119">Optional.</span></span> <span data-ttu-id="6143d-120">Especifica el tipo de credenciales utilizado para comprobar mensajes enviados con el transporte del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="6143d-120">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="6143d-121">Este atributo es del tipo <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="6143d-121">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="6143d-122">Atributo credentialType</span><span class="sxs-lookup"><span data-stu-id="6143d-122">credentialType Attribute</span></span>  
  
|<span data-ttu-id="6143d-123">Valor</span><span class="sxs-lookup"><span data-stu-id="6143d-123">Value</span></span>|<span data-ttu-id="6143d-124">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="6143d-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6143d-125">Certificate</span><span class="sxs-lookup"><span data-stu-id="6143d-125">Certificate</span></span>|<span data-ttu-id="6143d-126">La autenticación del transporte de canal del mismo nivel requiere un certificado X509.</span><span class="sxs-lookup"><span data-stu-id="6143d-126">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="6143d-127">Contraseña</span><span class="sxs-lookup"><span data-stu-id="6143d-127">Password</span></span>|<span data-ttu-id="6143d-128">La autenticación del transporte de canal del mismo nivel requiere una contraseña correcta.</span><span class="sxs-lookup"><span data-stu-id="6143d-128">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6143d-129">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6143d-129">Child Elements</span></span>  
 <span data-ttu-id="6143d-130">None</span><span class="sxs-lookup"><span data-stu-id="6143d-130">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6143d-131">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6143d-131">Parent Elements</span></span>  
  
|<span data-ttu-id="6143d-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="6143d-132">Element</span></span>|<span data-ttu-id="6143d-133">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="6143d-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6143d-134">\<security></span><span class="sxs-lookup"><span data-stu-id="6143d-134">\<security></span></span>](security-of-peertransport.md)|<span data-ttu-id="6143d-135">Define la configuración de seguridad de un transporte del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="6143d-135">Defines the security settings for a peer transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6143d-136">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6143d-136">Remarks</span></span>  
 <span data-ttu-id="6143d-137">Este elemento se establece solo si el atributo de modo del [ \<> de seguridad](security-of-peertransport.md) se establece en `Transport` o `TransportWithMessageCredential`.</span><span class="sxs-lookup"><span data-stu-id="6143d-137">This element is set only if the mode attribute of [\<security>](security-of-peertransport.md) is set to `Transport` or `TransportWithMessageCredential`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6143d-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="6143d-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="6143d-139">Seguridad de transporte</span><span class="sxs-lookup"><span data-stu-id="6143d-139">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="6143d-140">Transportes</span><span class="sxs-lookup"><span data-stu-id="6143d-140">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="6143d-141">Elección del transporte</span><span class="sxs-lookup"><span data-stu-id="6143d-141">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="6143d-142">Enlaces</span><span class="sxs-lookup"><span data-stu-id="6143d-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="6143d-143">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="6143d-143">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="6143d-144">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="6143d-144">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="6143d-145">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="6143d-145">\<customBinding></span></span>](custombinding.md)
