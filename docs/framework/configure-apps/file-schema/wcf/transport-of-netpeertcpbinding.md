---
title: Elemento &lt;transport&gt; de &lt;netPeerTcpBinding&gt;
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 2b89ae090d24ff6aad1aae1b39a0a18961bd2537
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43869784"
---
# <a name="lttransportgt-of-ltnetpeertcpbindinggt"></a><span data-ttu-id="fc1d3-102">Elemento &lt;transport&gt; de &lt;netPeerTcpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="fc1d3-102">&lt;transport&gt; of &lt;netPeerTcpBinding&gt;</span></span>
<span data-ttu-id="fc1d3-103">Especifica la configuración de seguridad de nivel de transporte cuando se usa el [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="fc1d3-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>  
  
 <span data-ttu-id="fc1d3-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fc1d3-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="fc1d3-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="fc1d3-105">\<bindings></span></span>  
<span data-ttu-id="fc1d3-106">\<netPeerTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="fc1d3-106">\<netPeerTcpBinding></span></span>  
<span data-ttu-id="fc1d3-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="fc1d3-107">\<binding></span></span>  
<span data-ttu-id="fc1d3-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="fc1d3-108">\<security></span></span>  
<span data-ttu-id="fc1d3-109">\<transporte ></span><span class="sxs-lookup"><span data-stu-id="fc1d3-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc1d3-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fc1d3-110">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>  
    <binding>  
        <security>  
            <transport credentialType="Certificate/Password" />  
        </security>         
    </binding>  
</netPeerTcpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fc1d3-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fc1d3-111">Attributes and Elements</span></span>  
 <span data-ttu-id="fc1d3-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fc1d3-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fc1d3-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="fc1d3-113">Attributes</span></span>  
  
|<span data-ttu-id="fc1d3-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="fc1d3-114">Attribute</span></span>|<span data-ttu-id="fc1d3-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="fc1d3-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fc1d3-116">credentialType</span><span class="sxs-lookup"><span data-stu-id="fc1d3-116">credentialType</span></span>|<span data-ttu-id="fc1d3-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-117">Optional.</span></span> <span data-ttu-id="fc1d3-118">Especifica el tipo de credenciales utilizado para comprobar mensajes enviados con el transporte del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-118">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="fc1d3-119">Este atributo es del tipo <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-119">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="fc1d3-120">Atributo credentialType</span><span class="sxs-lookup"><span data-stu-id="fc1d3-120">credentialType Attribute</span></span>  
  
|<span data-ttu-id="fc1d3-121">Valor</span><span class="sxs-lookup"><span data-stu-id="fc1d3-121">Value</span></span>|<span data-ttu-id="fc1d3-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="fc1d3-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fc1d3-123">Certificado</span><span class="sxs-lookup"><span data-stu-id="fc1d3-123">Certificate</span></span>|<span data-ttu-id="fc1d3-124">La autenticación del transporte de canal del mismo nivel requiere un certificado X509.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-124">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="fc1d3-125">Contraseña</span><span class="sxs-lookup"><span data-stu-id="fc1d3-125">Password</span></span>|<span data-ttu-id="fc1d3-126">La autenticación del transporte de canal del mismo nivel requiere una contraseña correcta.</span><span class="sxs-lookup"><span data-stu-id="fc1d3-126">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fc1d3-127">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fc1d3-127">Child Elements</span></span>  
 <span data-ttu-id="fc1d3-128">Ninguna</span><span class="sxs-lookup"><span data-stu-id="fc1d3-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fc1d3-129">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fc1d3-129">Parent Elements</span></span>  
  
|<span data-ttu-id="fc1d3-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="fc1d3-130">Element</span></span>|<span data-ttu-id="fc1d3-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="fc1d3-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fc1d3-132">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="fc1d3-132">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|<span data-ttu-id="fc1d3-133">Define la configuración de seguridad para el [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="fc1d3-133">Defines the security settings for the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fc1d3-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc1d3-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.PeerTransportSecuritySettings>  
 [<span data-ttu-id="fc1d3-135">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="fc1d3-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="fc1d3-136">Enlaces</span><span class="sxs-lookup"><span data-stu-id="fc1d3-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="fc1d3-137">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="fc1d3-137">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="fc1d3-138">Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="fc1d3-138">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="fc1d3-139">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="fc1d3-139">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
