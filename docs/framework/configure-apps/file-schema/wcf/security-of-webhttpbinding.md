---
title: '&lt;security&gt; de &lt;webHttpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
caps.latest.revision: "9"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: dc7edf528f509c725672036329989f9b7a9bfec2
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="ltsecuritygt-of-ltwebhttpbindinggt"></a><span data-ttu-id="9b209-102">&lt;security&gt; de &lt;webHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="9b209-102">&lt;security&gt; of &lt;webHttpBinding&gt;</span></span>
<span data-ttu-id="9b209-103">Especifica los requisitos de seguridad para un extremo configurado con un [ \<wsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="9b209-103">Specifies the security requirements for an endpoint configured with a [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>  
  
 <span data-ttu-id="9b209-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9b209-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9b209-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="9b209-105">\<bindings></span></span>  
<span data-ttu-id="9b209-106">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="9b209-106">\<webHttpBinding></span></span>  
<span data-ttu-id="9b209-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="9b209-107">\<binding></span></span>  
<span data-ttu-id="9b209-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="9b209-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b209-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9b209-109">Syntax</span></span>  
  
```xml  
<system.ServiceModel>  
    <bindings>  
        <webHttpBinding>  
            <binding name = "string">  
              <security mode="None/Transport/TransportCredentialOnly">  
                                    <transport clientCredentialType =   
                                     "Basic/Certificate/Digest/None/Ntlm/Windows"  
                                     proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
                                     realm="string" />  
              </security>  
        </webHttpBinding>  
    </bindings>  
</system.ServiceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b209-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9b209-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9b209-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9b209-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b209-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="9b209-112">Attributes</span></span>  
  
|<span data-ttu-id="9b209-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="9b209-113">Attribute</span></span>|<span data-ttu-id="9b209-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="9b209-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9b209-115">modo</span><span class="sxs-lookup"><span data-stu-id="9b209-115">mode</span></span>|<span data-ttu-id="9b209-116">Especifica si un extremo usa la seguridad a nivel de transporte o no usa ninguna.</span><span class="sxs-lookup"><span data-stu-id="9b209-116">Specifies whether transport-level security or no security is used by an endpoint.</span></span> <span data-ttu-id="9b209-117">De manera predeterminada, es `None`.</span><span class="sxs-lookup"><span data-stu-id="9b209-117">The default is `None`.</span></span> <span data-ttu-id="9b209-118">Este atributo es del tipo <xref:System.ServiceModel.WebHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="9b209-118">This attribute is of type <xref:System.ServiceModel.WebHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="9b209-119">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="9b209-119">Mode Attribute</span></span>  
  
|<span data-ttu-id="9b209-120">Valor</span><span class="sxs-lookup"><span data-stu-id="9b209-120">Value</span></span>|<span data-ttu-id="9b209-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="9b209-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9b209-122">Ninguna</span><span class="sxs-lookup"><span data-stu-id="9b209-122">None</span></span>|<span data-ttu-id="9b209-123">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="9b209-123">Security is disabled.</span></span>|  
|<span data-ttu-id="9b209-124">Transporte</span><span class="sxs-lookup"><span data-stu-id="9b209-124">Transport</span></span>|<span data-ttu-id="9b209-125">La seguridad se proporciona utilizando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="9b209-125">Security is provided using HTTPS.</span></span> <span data-ttu-id="9b209-126">El servicio necesita ser configurado con certificados SSL.</span><span class="sxs-lookup"><span data-stu-id="9b209-126">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="9b209-127">El mensaje se protege completamente utilizando HTTPS y el servicio se autentica por el cliente usando el certificado SSL del servicio.</span><span class="sxs-lookup"><span data-stu-id="9b209-127">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="9b209-128">La autenticación del cliente se controla mediante la `ClientCredentialType` atributo de la [ \<transporte >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="9b209-128">The client authentication is controlled through the `ClientCredentialType` attribute of the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md).</span></span>|  
|<span data-ttu-id="9b209-129">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="9b209-129">TransportCredentialOnly</span></span>|<span data-ttu-id="9b209-130">Este modo no proporciona integridad del mensaje y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="9b209-130">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="9b209-131">Proporciona la autenticación del cliente basada en HTTP.</span><span class="sxs-lookup"><span data-stu-id="9b209-131">It provides HTTP-based client authentication.</span></span> <span data-ttu-id="9b209-132">Este modo se debe utilizar con precaución.</span><span class="sxs-lookup"><span data-stu-id="9b209-132">This mode should be used with caution.</span></span> <span data-ttu-id="9b209-133">Se debería utilizar en entornos donde otros recursos (como IPSec) están proporcionando la seguridad de transporte y la infraestructura [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] proporciona sólo la autenticación del cliente.</span><span class="sxs-lookup"><span data-stu-id="9b209-133">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9b209-134">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9b209-134">Child Elements</span></span>  
  
|<span data-ttu-id="9b209-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="9b209-135">Element</span></span>|<span data-ttu-id="9b209-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="9b209-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9b209-137">\<transport></span><span class="sxs-lookup"><span data-stu-id="9b209-137">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md)|<span data-ttu-id="9b209-138">Define la configuración de seguridad para el transporte.</span><span class="sxs-lookup"><span data-stu-id="9b209-138">Defines the transport security settings.</span></span> <span data-ttu-id="9b209-139">Este elemento corresponde al tipo <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="9b209-139">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9b209-140">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9b209-140">Parent Elements</span></span>  
  
|<span data-ttu-id="9b209-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="9b209-141">Element</span></span>|<span data-ttu-id="9b209-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="9b209-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9b209-143">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="9b209-143">\<webHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)|<span data-ttu-id="9b209-144">Un elemento de enlace que se usa para configurar extremos para los servicios Web de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] que responden a las solicitudes HTTP en lugar de a mensajes SOAP.</span><span class="sxs-lookup"><span data-stu-id="9b209-144">A binding element that is used to configure endpoints for [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] Web services that respond to HTTP requests instead of SOAP messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9b209-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b209-145">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WebHttpBindingElement>  
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>  
 <xref:System.ServiceModel.WebHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.WebHttpSecurity>  
 [<span data-ttu-id="9b209-146">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="9b209-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="9b209-147">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="9b209-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="9b209-148">Enlaces</span><span class="sxs-lookup"><span data-stu-id="9b209-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="9b209-149">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="9b209-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="9b209-150">Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="9b209-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="9b209-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="9b209-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="9b209-152">Modelo de programación de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="9b209-152">WCF Web HTTP Programming Model</span></span>](../../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
