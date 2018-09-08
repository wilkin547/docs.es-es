---
title: '&lt;security&gt; de &lt;webHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 52146fa08ec63ef63fa996cdc09f9185b9f42e02
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44138336"
---
# <a name="ltsecuritygt-of-ltwebhttpbindinggt"></a><span data-ttu-id="fb9e4-102">&lt;security&gt; de &lt;webHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="fb9e4-102">&lt;security&gt; of &lt;webHttpBinding&gt;</span></span>
<span data-ttu-id="fb9e4-103">Especifica los requisitos de seguridad para un extremo configurado con un [ \<wsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="fb9e4-103">Specifies the security requirements for an endpoint configured with a [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>  
  
 <span data-ttu-id="fb9e4-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fb9e4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="fb9e4-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="fb9e4-105">\<bindings></span></span>  
<span data-ttu-id="fb9e4-106">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="fb9e4-106">\<webHttpBinding></span></span>  
<span data-ttu-id="fb9e4-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="fb9e4-107">\<binding></span></span>  
<span data-ttu-id="fb9e4-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="fb9e4-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb9e4-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fb9e4-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fb9e4-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fb9e4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fb9e4-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fb9e4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fb9e4-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="fb9e4-112">Attributes</span></span>  
  
|<span data-ttu-id="fb9e4-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="fb9e4-113">Attribute</span></span>|<span data-ttu-id="fb9e4-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="fb9e4-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fb9e4-115">modo</span><span class="sxs-lookup"><span data-stu-id="fb9e4-115">mode</span></span>|<span data-ttu-id="fb9e4-116">Especifica si un extremo usa la seguridad a nivel de transporte o no usa ninguna.</span><span class="sxs-lookup"><span data-stu-id="fb9e4-116">Specifies whether transport-level security or no security is used by an endpoint.</span></span> <span data-ttu-id="fb9e4-117">De manera predeterminada, es `None`.</span><span class="sxs-lookup"><span data-stu-id="fb9e4-117">The default is `None`.</span></span> <span data-ttu-id="fb9e4-118">Este atributo es del tipo <xref:System.ServiceModel.WebHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="fb9e4-118">This attribute is of type <xref:System.ServiceModel.WebHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="fb9e4-119">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="fb9e4-119">Mode Attribute</span></span>  
  
|<span data-ttu-id="fb9e4-120">Valor</span><span class="sxs-lookup"><span data-stu-id="fb9e4-120">Value</span></span>|<span data-ttu-id="fb9e4-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="fb9e4-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fb9e4-122">Ninguna</span><span class="sxs-lookup"><span data-stu-id="fb9e4-122">None</span></span>|<span data-ttu-id="fb9e4-123">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="fb9e4-123">Security is disabled.</span></span>|  
|<span data-ttu-id="fb9e4-124">Transporte</span><span class="sxs-lookup"><span data-stu-id="fb9e4-124">Transport</span></span>|<span data-ttu-id="fb9e4-125">La seguridad se proporciona utilizando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="fb9e4-125">Security is provided using HTTPS.</span></span> <span data-ttu-id="fb9e4-126">El servicio necesita ser configurado con certificados SSL.</span><span class="sxs-lookup"><span data-stu-id="fb9e4-126">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="fb9e4-127">El mensaje se protege completamente utilizando HTTPS y el servicio se autentica por el cliente usando el certificado SSL del servicio.</span><span class="sxs-lookup"><span data-stu-id="fb9e4-127">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="fb9e4-128">La autenticación del cliente se controla mediante el `ClientCredentialType` atributo de la [ \<transporte >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="fb9e4-128">The client authentication is controlled through the `ClientCredentialType` attribute of the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md).</span></span>|  
|<span data-ttu-id="fb9e4-129">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="fb9e4-129">TransportCredentialOnly</span></span>|<span data-ttu-id="fb9e4-130">Este modo no proporciona integridad del mensaje y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="fb9e4-130">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="fb9e4-131">Proporciona la autenticación del cliente basada en HTTP.</span><span class="sxs-lookup"><span data-stu-id="fb9e4-131">It provides HTTP-based client authentication.</span></span> <span data-ttu-id="fb9e4-132">Este modo se debe utilizar con precaución.</span><span class="sxs-lookup"><span data-stu-id="fb9e4-132">This mode should be used with caution.</span></span> <span data-ttu-id="fb9e4-133">Se debe usar en entornos donde la seguridad de transporte se proporciona por otros medios (por ejemplo, IPSec) y la infraestructura de WCF proporciona sólo la autenticación de cliente.</span><span class="sxs-lookup"><span data-stu-id="fb9e4-133">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fb9e4-134">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fb9e4-134">Child Elements</span></span>  
  
|<span data-ttu-id="fb9e4-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="fb9e4-135">Element</span></span>|<span data-ttu-id="fb9e4-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="fb9e4-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fb9e4-137">\<transporte ></span><span class="sxs-lookup"><span data-stu-id="fb9e4-137">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md)|<span data-ttu-id="fb9e4-138">Define la configuración de seguridad para el transporte.</span><span class="sxs-lookup"><span data-stu-id="fb9e4-138">Defines the transport security settings.</span></span> <span data-ttu-id="fb9e4-139">Este elemento corresponde al tipo <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="fb9e4-139">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fb9e4-140">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fb9e4-140">Parent Elements</span></span>  
  
|<span data-ttu-id="fb9e4-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="fb9e4-141">Element</span></span>|<span data-ttu-id="fb9e4-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="fb9e4-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fb9e4-143">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="fb9e4-143">\<webHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)|<span data-ttu-id="fb9e4-144">Un elemento de enlace que se usa para configurar los puntos de conexión para que responden a solicitudes HTTP en lugar de los mensajes SOAP de los servicios Web de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="fb9e4-144">A binding element that is used to configure endpoints for Windows Communication Foundation (WCF) Web services that respond to HTTP requests instead of SOAP messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fb9e4-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb9e4-145">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WebHttpBindingElement>  
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>  
 <xref:System.ServiceModel.WebHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.WebHttpSecurity>  
 [<span data-ttu-id="fb9e4-146">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="fb9e4-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="fb9e4-147">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="fb9e4-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="fb9e4-148">Enlaces</span><span class="sxs-lookup"><span data-stu-id="fb9e4-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="fb9e4-149">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="fb9e4-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="fb9e4-150">Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="fb9e4-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="fb9e4-151">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="fb9e4-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="fb9e4-152">Modelo de programación de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="fb9e4-152">WCF Web HTTP Programming Model</span></span>](../../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
