---
title: <transport> de <peerTransport>
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: 7328d67c4649010dce3e1c866238d1e0067e4990
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157075"
---
# <a name="transport-of-peertransport"></a><span data-ttu-id="3571f-102">\<transport> de \<peerTransport></span><span class="sxs-lookup"><span data-stu-id="3571f-102">\<transport> of \<peerTransport></span></span>

<span data-ttu-id="3571f-103">Especifica el tipo de transporte para mensajes seguros enviados por pares configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="3571f-103">Specifies the transport type for secured messages sent by peers configured with this binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peerTransport>**](peertransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-peertransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="3571f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3571f-104">Syntax</span></span>  
  
```xml  
<security>
  <transport credentialType="Certificate/Password" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3571f-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3571f-105">Attributes and Elements</span></span>  

 <span data-ttu-id="3571f-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3571f-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3571f-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="3571f-107">Attributes</span></span>  
  
|<span data-ttu-id="3571f-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="3571f-108">Attribute</span></span>|<span data-ttu-id="3571f-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="3571f-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3571f-110">credentialType</span><span class="sxs-lookup"><span data-stu-id="3571f-110">credentialType</span></span>|<span data-ttu-id="3571f-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="3571f-111">Optional.</span></span> <span data-ttu-id="3571f-112">Especifica el tipo de credenciales utilizado para comprobar mensajes enviados con el transporte del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="3571f-112">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="3571f-113">Este atributo es del tipo <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="3571f-113">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="3571f-114">Atributo credentialType</span><span class="sxs-lookup"><span data-stu-id="3571f-114">credentialType Attribute</span></span>  
  
|<span data-ttu-id="3571f-115">Valor</span><span class="sxs-lookup"><span data-stu-id="3571f-115">Value</span></span>|<span data-ttu-id="3571f-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="3571f-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3571f-117">Certificado</span><span class="sxs-lookup"><span data-stu-id="3571f-117">Certificate</span></span>|<span data-ttu-id="3571f-118">La autenticación del transporte de canal del mismo nivel requiere un certificado X509.</span><span class="sxs-lookup"><span data-stu-id="3571f-118">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="3571f-119">Contraseña</span><span class="sxs-lookup"><span data-stu-id="3571f-119">Password</span></span>|<span data-ttu-id="3571f-120">La autenticación del transporte de canal del mismo nivel requiere una contraseña correcta.</span><span class="sxs-lookup"><span data-stu-id="3571f-120">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3571f-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3571f-121">Child Elements</span></span>  

 <span data-ttu-id="3571f-122">None</span><span class="sxs-lookup"><span data-stu-id="3571f-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3571f-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3571f-123">Parent Elements</span></span>  
  
|<span data-ttu-id="3571f-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="3571f-124">Element</span></span>|<span data-ttu-id="3571f-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="3571f-125">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-peertransport.md)|<span data-ttu-id="3571f-126">Define la configuración de seguridad de un transporte del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="3571f-126">Defines the security settings for a peer transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3571f-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3571f-127">Remarks</span></span>  

 <span data-ttu-id="3571f-128">Este elemento se establece solo si el atributo de modo de [\<security>](security-of-peertransport.md) se establece en `Transport` o `TransportWithMessageCredential` .</span><span class="sxs-lookup"><span data-stu-id="3571f-128">This element is set only if the mode attribute of [\<security>](security-of-peertransport.md) is set to `Transport` or `TransportWithMessageCredential`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3571f-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="3571f-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="3571f-130">Seguridad de transporte</span><span class="sxs-lookup"><span data-stu-id="3571f-130">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="3571f-131">Transportes</span><span class="sxs-lookup"><span data-stu-id="3571f-131">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="3571f-132">Elección del transporte</span><span class="sxs-lookup"><span data-stu-id="3571f-132">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="3571f-133">Enlaces</span><span class="sxs-lookup"><span data-stu-id="3571f-133">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="3571f-134">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="3571f-134">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="3571f-135">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="3571f-135">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
