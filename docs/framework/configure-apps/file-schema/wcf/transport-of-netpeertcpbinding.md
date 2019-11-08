---
title: <transport> de <netPeerTcpBinding>
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 49b31a889d192d190125214e89ba09305114eb7f
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73735977"
---
# <a name="transport-of-netpeertcpbinding"></a><span data-ttu-id="d7142-102">\<> de transporte de \<netPeerTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="d7142-102">\<transport> of \<netPeerTcpBinding></span></span>
<span data-ttu-id="d7142-103">Especifica la configuración de seguridad de nivel de transporte cuando se usa el [\<netPeerTcpBinding >](netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="d7142-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>  
  
<span data-ttu-id="d7142-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d7142-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d7142-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="d7142-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="d7142-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**enlaces**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="d7142-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="d7142-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netPeerTcpBinding**](netpeertcpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="d7142-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)</span></span>\
<span data-ttu-id="d7142-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**enlace** ></span><span class="sxs-lookup"><span data-stu-id="d7142-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="d7142-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**seguridad**](security-of-netpeerbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="d7142-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netpeerbinding.md)</span></span>\
<span data-ttu-id="d7142-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**transporte** ></span><span class="sxs-lookup"><span data-stu-id="d7142-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7142-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d7142-111">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>
  <binding>
    <security>
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d7142-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d7142-112">Attributes and Elements</span></span>  
 <span data-ttu-id="d7142-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d7142-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d7142-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="d7142-114">Attributes</span></span>  
  
|<span data-ttu-id="d7142-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="d7142-115">Attribute</span></span>|<span data-ttu-id="d7142-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="d7142-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d7142-117">credentialType</span><span class="sxs-lookup"><span data-stu-id="d7142-117">credentialType</span></span>|<span data-ttu-id="d7142-118">Opcional.</span><span class="sxs-lookup"><span data-stu-id="d7142-118">Optional.</span></span> <span data-ttu-id="d7142-119">Especifica el tipo de credenciales utilizado para comprobar mensajes enviados con el transporte del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="d7142-119">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="d7142-120">Este atributo es del tipo <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="d7142-120">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="d7142-121">Atributo credentialType</span><span class="sxs-lookup"><span data-stu-id="d7142-121">credentialType Attribute</span></span>  
  
|<span data-ttu-id="d7142-122">Valor</span><span class="sxs-lookup"><span data-stu-id="d7142-122">Value</span></span>|<span data-ttu-id="d7142-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="d7142-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d7142-124">Certificado</span><span class="sxs-lookup"><span data-stu-id="d7142-124">Certificate</span></span>|<span data-ttu-id="d7142-125">La autenticación del transporte de canal del mismo nivel requiere un certificado X509.</span><span class="sxs-lookup"><span data-stu-id="d7142-125">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="d7142-126">Contraseña</span><span class="sxs-lookup"><span data-stu-id="d7142-126">Password</span></span>|<span data-ttu-id="d7142-127">La autenticación del transporte de canal del mismo nivel requiere una contraseña correcta.</span><span class="sxs-lookup"><span data-stu-id="d7142-127">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d7142-128">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d7142-128">Child Elements</span></span>  
 <span data-ttu-id="d7142-129">Ninguno</span><span class="sxs-lookup"><span data-stu-id="d7142-129">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d7142-130">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d7142-130">Parent Elements</span></span>  
  
|<span data-ttu-id="d7142-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="d7142-131">Element</span></span>|<span data-ttu-id="d7142-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="d7142-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d7142-133">\<La ></span><span class="sxs-lookup"><span data-stu-id="d7142-133">\<security></span></span>](security-of-netpeerbinding.md)|<span data-ttu-id="d7142-134">Define la configuración de seguridad para el [\<netPeerTcpBinding >](netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="d7142-134">Defines the security settings for the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d7142-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="d7142-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- [<span data-ttu-id="d7142-136">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="d7142-136">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="d7142-137">Enlaces</span><span class="sxs-lookup"><span data-stu-id="d7142-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d7142-138">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="d7142-138">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="d7142-139">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="d7142-139">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="d7142-140">\<> de enlace</span><span class="sxs-lookup"><span data-stu-id="d7142-140">\<binding></span></span>](bindings.md)
