---
title: <transport> de <netPeerTcpBinding>
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: f5feca232265cbcad7feff78c0c66e3606c8567e
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55270398"
---
# <a name="transport-of-netpeertcpbinding"></a><span data-ttu-id="bfb6c-102">\<transporte > de \<netPeerTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="bfb6c-102">\<transport> of \<netPeerTcpBinding></span></span>
<span data-ttu-id="bfb6c-103">Especifica la configuración de seguridad de nivel de transporte cuando se usa el [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="bfb6c-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>  
  
 <span data-ttu-id="bfb6c-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="bfb6c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="bfb6c-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="bfb6c-105">\<bindings></span></span>  
<span data-ttu-id="bfb6c-106">\<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="bfb6c-106">\<netPeerTcpBinding></span></span>  
<span data-ttu-id="bfb6c-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="bfb6c-107">\<binding></span></span>  
<span data-ttu-id="bfb6c-108">\<security></span><span class="sxs-lookup"><span data-stu-id="bfb6c-108">\<security></span></span>  
<span data-ttu-id="bfb6c-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="bfb6c-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfb6c-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bfb6c-110">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>
  <binding>
    <security>
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bfb6c-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bfb6c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="bfb6c-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bfb6c-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bfb6c-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="bfb6c-113">Attributes</span></span>  
  
|<span data-ttu-id="bfb6c-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="bfb6c-114">Attribute</span></span>|<span data-ttu-id="bfb6c-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="bfb6c-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bfb6c-116">credentialType</span><span class="sxs-lookup"><span data-stu-id="bfb6c-116">credentialType</span></span>|<span data-ttu-id="bfb6c-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="bfb6c-117">Optional.</span></span> <span data-ttu-id="bfb6c-118">Especifica el tipo de credenciales utilizado para comprobar mensajes enviados con el transporte del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="bfb6c-118">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="bfb6c-119">Este atributo es del tipo <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="bfb6c-119">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="bfb6c-120">Atributo credentialType</span><span class="sxs-lookup"><span data-stu-id="bfb6c-120">credentialType Attribute</span></span>  
  
|<span data-ttu-id="bfb6c-121">Valor</span><span class="sxs-lookup"><span data-stu-id="bfb6c-121">Value</span></span>|<span data-ttu-id="bfb6c-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="bfb6c-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bfb6c-123">Certificado</span><span class="sxs-lookup"><span data-stu-id="bfb6c-123">Certificate</span></span>|<span data-ttu-id="bfb6c-124">La autenticación del transporte de canal del mismo nivel requiere un certificado X509.</span><span class="sxs-lookup"><span data-stu-id="bfb6c-124">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="bfb6c-125">Contraseña</span><span class="sxs-lookup"><span data-stu-id="bfb6c-125">Password</span></span>|<span data-ttu-id="bfb6c-126">La autenticación del transporte de canal del mismo nivel requiere una contraseña correcta.</span><span class="sxs-lookup"><span data-stu-id="bfb6c-126">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bfb6c-127">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bfb6c-127">Child Elements</span></span>  
 <span data-ttu-id="bfb6c-128">Ninguna</span><span class="sxs-lookup"><span data-stu-id="bfb6c-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bfb6c-129">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bfb6c-129">Parent Elements</span></span>  
  
|<span data-ttu-id="bfb6c-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="bfb6c-130">Element</span></span>|<span data-ttu-id="bfb6c-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="bfb6c-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bfb6c-132">\<security></span><span class="sxs-lookup"><span data-stu-id="bfb6c-132">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|<span data-ttu-id="bfb6c-133">Define la configuración de seguridad para el [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="bfb6c-133">Defines the security settings for the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bfb6c-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="bfb6c-134">See also</span></span>
- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- [<span data-ttu-id="bfb6c-135">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="bfb6c-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="bfb6c-136">Enlaces</span><span class="sxs-lookup"><span data-stu-id="bfb6c-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="bfb6c-137">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="bfb6c-137">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="bfb6c-138">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="bfb6c-138">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="bfb6c-139">\<binding></span><span class="sxs-lookup"><span data-stu-id="bfb6c-139">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
