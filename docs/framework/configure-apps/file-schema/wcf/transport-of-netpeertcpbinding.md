---
title: <transport> de <netPeerTcpBinding>
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 837d01540fa63579877ab4085bd8034c78f2fbe0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915562"
---
# <a name="transport-of-netpeertcpbinding"></a><span data-ttu-id="66183-102">\<> de transporte \<de > netPeerTcpBinding</span><span class="sxs-lookup"><span data-stu-id="66183-102">\<transport> of \<netPeerTcpBinding></span></span>
<span data-ttu-id="66183-103">Especifica la configuración de seguridad de nivel de transporte al usar el [ \<> netPeerTcpBinding](netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="66183-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>  
  
 <span data-ttu-id="66183-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="66183-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="66183-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="66183-105">\<bindings></span></span>  
<span data-ttu-id="66183-106">\<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="66183-106">\<netPeerTcpBinding></span></span>  
<span data-ttu-id="66183-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="66183-107">\<binding></span></span>  
<span data-ttu-id="66183-108">\<> de seguridad</span><span class="sxs-lookup"><span data-stu-id="66183-108">\<security></span></span>  
<span data-ttu-id="66183-109">\<> de transporte</span><span class="sxs-lookup"><span data-stu-id="66183-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66183-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="66183-110">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>
  <binding>
    <security>
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="66183-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="66183-111">Attributes and Elements</span></span>  
 <span data-ttu-id="66183-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="66183-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="66183-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="66183-113">Attributes</span></span>  
  
|<span data-ttu-id="66183-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="66183-114">Attribute</span></span>|<span data-ttu-id="66183-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="66183-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="66183-116">credentialType</span><span class="sxs-lookup"><span data-stu-id="66183-116">credentialType</span></span>|<span data-ttu-id="66183-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="66183-117">Optional.</span></span> <span data-ttu-id="66183-118">Especifica el tipo de credenciales utilizado para comprobar mensajes enviados con el transporte del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="66183-118">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="66183-119">Este atributo es del tipo <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="66183-119">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="66183-120">Atributo credentialType</span><span class="sxs-lookup"><span data-stu-id="66183-120">credentialType Attribute</span></span>  
  
|<span data-ttu-id="66183-121">Value</span><span class="sxs-lookup"><span data-stu-id="66183-121">Value</span></span>|<span data-ttu-id="66183-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="66183-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="66183-123">Certificate</span><span class="sxs-lookup"><span data-stu-id="66183-123">Certificate</span></span>|<span data-ttu-id="66183-124">La autenticación del transporte de canal del mismo nivel requiere un certificado X509.</span><span class="sxs-lookup"><span data-stu-id="66183-124">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="66183-125">Contraseña</span><span class="sxs-lookup"><span data-stu-id="66183-125">Password</span></span>|<span data-ttu-id="66183-126">La autenticación del transporte de canal del mismo nivel requiere una contraseña correcta.</span><span class="sxs-lookup"><span data-stu-id="66183-126">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="66183-127">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="66183-127">Child Elements</span></span>  
 <span data-ttu-id="66183-128">None</span><span class="sxs-lookup"><span data-stu-id="66183-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="66183-129">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="66183-129">Parent Elements</span></span>  
  
|<span data-ttu-id="66183-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="66183-130">Element</span></span>|<span data-ttu-id="66183-131">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="66183-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="66183-132">\<security></span><span class="sxs-lookup"><span data-stu-id="66183-132">\<security></span></span>](security-of-netpeerbinding.md)|<span data-ttu-id="66183-133">Define la configuración de seguridad para el [ \<> netPeerTcpBinding](netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="66183-133">Defines the security settings for the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="66183-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="66183-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- [<span data-ttu-id="66183-135">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="66183-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="66183-136">Enlaces</span><span class="sxs-lookup"><span data-stu-id="66183-136">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="66183-137">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="66183-137">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="66183-138">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="66183-138">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="66183-139">\<binding></span><span class="sxs-lookup"><span data-stu-id="66183-139">\<binding></span></span>](../../../misc/binding.md)
