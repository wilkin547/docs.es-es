---
title: Elemento &lt;transport&gt; de &lt;netPeerTcpBinding&gt;
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 2b89ae090d24ff6aad1aae1b39a0a18961bd2537
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44078553"
---
# <a name="lttransportgt-of-ltnetpeertcpbindinggt"></a><span data-ttu-id="31ed4-102">Elemento &lt;transport&gt; de &lt;netPeerTcpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="31ed4-102">&lt;transport&gt; of &lt;netPeerTcpBinding&gt;</span></span>
<span data-ttu-id="31ed4-103">Especifica la configuración de seguridad de nivel de transporte cuando se usa el [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="31ed4-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>  
  
 <span data-ttu-id="31ed4-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="31ed4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="31ed4-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="31ed4-105">\<bindings></span></span>  
<span data-ttu-id="31ed4-106">\<netPeerTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="31ed4-106">\<netPeerTcpBinding></span></span>  
<span data-ttu-id="31ed4-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="31ed4-107">\<binding></span></span>  
<span data-ttu-id="31ed4-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="31ed4-108">\<security></span></span>  
<span data-ttu-id="31ed4-109">\<transporte ></span><span class="sxs-lookup"><span data-stu-id="31ed4-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31ed4-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="31ed4-110">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>  
    <binding>  
        <security>  
            <transport credentialType="Certificate/Password" />  
        </security>         
    </binding>  
</netPeerTcpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="31ed4-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="31ed4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="31ed4-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="31ed4-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="31ed4-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="31ed4-113">Attributes</span></span>  
  
|<span data-ttu-id="31ed4-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="31ed4-114">Attribute</span></span>|<span data-ttu-id="31ed4-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="31ed4-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="31ed4-116">credentialType</span><span class="sxs-lookup"><span data-stu-id="31ed4-116">credentialType</span></span>|<span data-ttu-id="31ed4-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="31ed4-117">Optional.</span></span> <span data-ttu-id="31ed4-118">Especifica el tipo de credenciales utilizado para comprobar mensajes enviados con el transporte del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="31ed4-118">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="31ed4-119">Este atributo es del tipo <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="31ed4-119">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="31ed4-120">Atributo credentialType</span><span class="sxs-lookup"><span data-stu-id="31ed4-120">credentialType Attribute</span></span>  
  
|<span data-ttu-id="31ed4-121">Valor</span><span class="sxs-lookup"><span data-stu-id="31ed4-121">Value</span></span>|<span data-ttu-id="31ed4-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="31ed4-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="31ed4-123">Certificado</span><span class="sxs-lookup"><span data-stu-id="31ed4-123">Certificate</span></span>|<span data-ttu-id="31ed4-124">La autenticación del transporte de canal del mismo nivel requiere un certificado X509.</span><span class="sxs-lookup"><span data-stu-id="31ed4-124">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="31ed4-125">Contraseña</span><span class="sxs-lookup"><span data-stu-id="31ed4-125">Password</span></span>|<span data-ttu-id="31ed4-126">La autenticación del transporte de canal del mismo nivel requiere una contraseña correcta.</span><span class="sxs-lookup"><span data-stu-id="31ed4-126">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="31ed4-127">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="31ed4-127">Child Elements</span></span>  
 <span data-ttu-id="31ed4-128">Ninguna</span><span class="sxs-lookup"><span data-stu-id="31ed4-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="31ed4-129">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="31ed4-129">Parent Elements</span></span>  
  
|<span data-ttu-id="31ed4-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="31ed4-130">Element</span></span>|<span data-ttu-id="31ed4-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="31ed4-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="31ed4-132">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="31ed4-132">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|<span data-ttu-id="31ed4-133">Define la configuración de seguridad para el [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="31ed4-133">Defines the security settings for the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="31ed4-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="31ed4-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.PeerTransportSecuritySettings>  
 [<span data-ttu-id="31ed4-135">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="31ed4-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="31ed4-136">Enlaces</span><span class="sxs-lookup"><span data-stu-id="31ed4-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="31ed4-137">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="31ed4-137">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="31ed4-138">Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="31ed4-138">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="31ed4-139">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="31ed4-139">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
