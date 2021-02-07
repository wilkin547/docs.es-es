---
description: 'Más información sobre: <transport> de <peerTransport>'
title: <transport> de <peerTransport>
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: ba3405c5dfadb513f92ebd537409a3f7b12fa291
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664514"
---
# <a name="transport-of-peertransport"></a><span data-ttu-id="ba3c9-103">\<transport> de \<peerTransport></span><span class="sxs-lookup"><span data-stu-id="ba3c9-103">\<transport> of \<peerTransport></span></span>

<span data-ttu-id="ba3c9-104">Especifica el tipo de transporte para mensajes seguros enviados por pares configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="ba3c9-104">Specifies the transport type for secured messages sent by peers configured with this binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peerTransport>**](peertransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-peertransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="ba3c9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ba3c9-105">Syntax</span></span>  
  
```xml  
<security>
  <transport credentialType="Certificate/Password" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba3c9-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ba3c9-106">Attributes and Elements</span></span>  

 <span data-ttu-id="ba3c9-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ba3c9-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba3c9-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="ba3c9-108">Attributes</span></span>  
  
|<span data-ttu-id="ba3c9-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="ba3c9-109">Attribute</span></span>|<span data-ttu-id="ba3c9-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="ba3c9-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ba3c9-111">credentialType</span><span class="sxs-lookup"><span data-stu-id="ba3c9-111">credentialType</span></span>|<span data-ttu-id="ba3c9-112">Opcional.</span><span class="sxs-lookup"><span data-stu-id="ba3c9-112">Optional.</span></span> <span data-ttu-id="ba3c9-113">Especifica el tipo de credenciales utilizado para comprobar mensajes enviados con el transporte del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="ba3c9-113">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="ba3c9-114">Este atributo es del tipo <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="ba3c9-114">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="ba3c9-115">Atributo credentialType</span><span class="sxs-lookup"><span data-stu-id="ba3c9-115">credentialType Attribute</span></span>  
  
|<span data-ttu-id="ba3c9-116">Value</span><span class="sxs-lookup"><span data-stu-id="ba3c9-116">Value</span></span>|<span data-ttu-id="ba3c9-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="ba3c9-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ba3c9-118">Certificado</span><span class="sxs-lookup"><span data-stu-id="ba3c9-118">Certificate</span></span>|<span data-ttu-id="ba3c9-119">La autenticación del transporte de canal del mismo nivel requiere un certificado X509.</span><span class="sxs-lookup"><span data-stu-id="ba3c9-119">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="ba3c9-120">Contraseña</span><span class="sxs-lookup"><span data-stu-id="ba3c9-120">Password</span></span>|<span data-ttu-id="ba3c9-121">La autenticación del transporte de canal del mismo nivel requiere una contraseña correcta.</span><span class="sxs-lookup"><span data-stu-id="ba3c9-121">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ba3c9-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ba3c9-122">Child Elements</span></span>  

 <span data-ttu-id="ba3c9-123">None</span><span class="sxs-lookup"><span data-stu-id="ba3c9-123">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ba3c9-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ba3c9-124">Parent Elements</span></span>  
  
|<span data-ttu-id="ba3c9-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="ba3c9-125">Element</span></span>|<span data-ttu-id="ba3c9-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="ba3c9-126">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-peertransport.md)|<span data-ttu-id="ba3c9-127">Define la configuración de seguridad de un transporte del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="ba3c9-127">Defines the security settings for a peer transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba3c9-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ba3c9-128">Remarks</span></span>  

 <span data-ttu-id="ba3c9-129">Este elemento se establece solo si el atributo de modo de [\<security>](security-of-peertransport.md) se establece en `Transport` o `TransportWithMessageCredential` .</span><span class="sxs-lookup"><span data-stu-id="ba3c9-129">This element is set only if the mode attribute of [\<security>](security-of-peertransport.md) is set to `Transport` or `TransportWithMessageCredential`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba3c9-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba3c9-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="ba3c9-131">Seguridad de transporte</span><span class="sxs-lookup"><span data-stu-id="ba3c9-131">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="ba3c9-132">Transportes</span><span class="sxs-lookup"><span data-stu-id="ba3c9-132">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="ba3c9-133">Elección del transporte</span><span class="sxs-lookup"><span data-stu-id="ba3c9-133">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="ba3c9-134">Enlaces</span><span class="sxs-lookup"><span data-stu-id="ba3c9-134">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ba3c9-135">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="ba3c9-135">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="ba3c9-136">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="ba3c9-136">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
