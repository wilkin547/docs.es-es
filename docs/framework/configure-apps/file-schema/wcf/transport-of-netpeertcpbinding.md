---
title: <transport> de <netPeerTcpBinding>
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 157637615abafbd5913e4d90b702bb0224d5f121
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204879"
---
# <a name="transport-of-netpeertcpbinding"></a><span data-ttu-id="26005-102">\<transporte > de \<netPeerTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="26005-102">\<transport> of \<netPeerTcpBinding></span></span>
<span data-ttu-id="26005-103">Especifica la configuración de seguridad de nivel de transporte cuando se usa el [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="26005-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>  
  
 <span data-ttu-id="26005-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="26005-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="26005-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="26005-105">\<bindings></span></span>  
<span data-ttu-id="26005-106">\<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="26005-106">\<netPeerTcpBinding></span></span>  
<span data-ttu-id="26005-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="26005-107">\<binding></span></span>  
<span data-ttu-id="26005-108">\<security></span><span class="sxs-lookup"><span data-stu-id="26005-108">\<security></span></span>  
<span data-ttu-id="26005-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="26005-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26005-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="26005-110">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>
  <binding>
    <security>
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="26005-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="26005-111">Attributes and Elements</span></span>  
 <span data-ttu-id="26005-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="26005-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="26005-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="26005-113">Attributes</span></span>  
  
|<span data-ttu-id="26005-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="26005-114">Attribute</span></span>|<span data-ttu-id="26005-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="26005-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="26005-116">credentialType</span><span class="sxs-lookup"><span data-stu-id="26005-116">credentialType</span></span>|<span data-ttu-id="26005-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="26005-117">Optional.</span></span> <span data-ttu-id="26005-118">Especifica el tipo de credenciales utilizado para comprobar mensajes enviados con el transporte del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="26005-118">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="26005-119">Este atributo es del tipo <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="26005-119">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="26005-120">Atributo credentialType</span><span class="sxs-lookup"><span data-stu-id="26005-120">credentialType Attribute</span></span>  
  
|<span data-ttu-id="26005-121">Valor</span><span class="sxs-lookup"><span data-stu-id="26005-121">Value</span></span>|<span data-ttu-id="26005-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="26005-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="26005-123">Certificado</span><span class="sxs-lookup"><span data-stu-id="26005-123">Certificate</span></span>|<span data-ttu-id="26005-124">La autenticación del transporte de canal del mismo nivel requiere un certificado X509.</span><span class="sxs-lookup"><span data-stu-id="26005-124">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="26005-125">Contraseña</span><span class="sxs-lookup"><span data-stu-id="26005-125">Password</span></span>|<span data-ttu-id="26005-126">La autenticación del transporte de canal del mismo nivel requiere una contraseña correcta.</span><span class="sxs-lookup"><span data-stu-id="26005-126">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="26005-127">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="26005-127">Child Elements</span></span>  
 <span data-ttu-id="26005-128">Ninguna</span><span class="sxs-lookup"><span data-stu-id="26005-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="26005-129">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="26005-129">Parent Elements</span></span>  
  
|<span data-ttu-id="26005-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="26005-130">Element</span></span>|<span data-ttu-id="26005-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="26005-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="26005-132">\<security></span><span class="sxs-lookup"><span data-stu-id="26005-132">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|<span data-ttu-id="26005-133">Define la configuración de seguridad para el [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="26005-133">Defines the security settings for the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="26005-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="26005-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- [<span data-ttu-id="26005-135">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="26005-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="26005-136">Enlaces</span><span class="sxs-lookup"><span data-stu-id="26005-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="26005-137">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="26005-137">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="26005-138">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="26005-138">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="26005-139">\<binding></span><span class="sxs-lookup"><span data-stu-id="26005-139">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
