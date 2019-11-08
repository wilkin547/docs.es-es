---
title: <security> de <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
ms.openlocfilehash: 77009dc950a608da9e0db3a7d09be67e1ed46137
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738639"
---
# <a name="security-of-webhttpbinding"></a><span data-ttu-id="44ff1-102">\<> de seguridad de \<webHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="44ff1-102">\<security> of \<webHttpBinding></span></span>
<span data-ttu-id="44ff1-103">Especifica los requisitos de seguridad para un extremo configurado con un [\<webHttpBinding >](webhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="44ff1-103">Specifies the security requirements for an endpoint configured with a [\<webHttpBinding>](webhttpbinding.md).</span></span>  
  
<span data-ttu-id="44ff1-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="44ff1-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="44ff1-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="44ff1-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="44ff1-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**enlaces**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="44ff1-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="44ff1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**webHttpBinding**](webhttpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="44ff1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<webHttpBinding>**](webhttpbinding.md)</span></span>\
<span data-ttu-id="44ff1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**enlace** ></span><span class="sxs-lookup"><span data-stu-id="44ff1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="44ff1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**seguridad** ></span><span class="sxs-lookup"><span data-stu-id="44ff1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44ff1-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="44ff1-110">Syntax</span></span>  
  
```xml  
<system.ServiceModel>
  <bindings>
    <webHttpBinding>
      <binding name = "String">
        <security mode="None/Transport/TransportCredentialOnly">
          <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
                     proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
                     realm="String" />
        </security>
      </binding>
    </webHttpBinding>
  </bindings>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="44ff1-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="44ff1-111">Attributes and Elements</span></span>  
 <span data-ttu-id="44ff1-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="44ff1-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="44ff1-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="44ff1-113">Attributes</span></span>  
  
|<span data-ttu-id="44ff1-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="44ff1-114">Attribute</span></span>|<span data-ttu-id="44ff1-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="44ff1-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="44ff1-116">modo</span><span class="sxs-lookup"><span data-stu-id="44ff1-116">mode</span></span>|<span data-ttu-id="44ff1-117">Especifica si un punto de conexión usa la seguridad a nivel de transporte o no usa ninguna.</span><span class="sxs-lookup"><span data-stu-id="44ff1-117">Specifies whether transport-level security or no security is used by an endpoint.</span></span> <span data-ttu-id="44ff1-118">De manera predeterminada, es `None`.</span><span class="sxs-lookup"><span data-stu-id="44ff1-118">The default is `None`.</span></span> <span data-ttu-id="44ff1-119">Este atributo es del tipo <xref:System.ServiceModel.WebHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="44ff1-119">This attribute is of type <xref:System.ServiceModel.WebHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="44ff1-120">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="44ff1-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="44ff1-121">Valor</span><span class="sxs-lookup"><span data-stu-id="44ff1-121">Value</span></span>|<span data-ttu-id="44ff1-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="44ff1-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="44ff1-123">Ninguno</span><span class="sxs-lookup"><span data-stu-id="44ff1-123">None</span></span>|<span data-ttu-id="44ff1-124">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="44ff1-124">Security is disabled.</span></span>|  
|<span data-ttu-id="44ff1-125">Transporte</span><span class="sxs-lookup"><span data-stu-id="44ff1-125">Transport</span></span>|<span data-ttu-id="44ff1-126">La seguridad se proporciona utilizando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="44ff1-126">Security is provided using HTTPS.</span></span> <span data-ttu-id="44ff1-127">El servicio necesita ser configurado con certificados SSL.</span><span class="sxs-lookup"><span data-stu-id="44ff1-127">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="44ff1-128">El mensaje se protege completamente utilizando HTTPS y el servicio se autentica por el cliente usando el certificado SSL del servicio.</span><span class="sxs-lookup"><span data-stu-id="44ff1-128">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="44ff1-129">La autenticación del cliente se controla a través del atributo `ClientCredentialType` del [> de transporte de\<](transport-of-webhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="44ff1-129">The client authentication is controlled through the `ClientCredentialType` attribute of the [\<transport>](transport-of-webhttpbinding.md).</span></span>|  
|<span data-ttu-id="44ff1-130">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="44ff1-130">TransportCredentialOnly</span></span>|<span data-ttu-id="44ff1-131">Este modo no proporciona integridad del mensaje y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="44ff1-131">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="44ff1-132">Proporciona la autenticación del cliente basada en HTTP.</span><span class="sxs-lookup"><span data-stu-id="44ff1-132">It provides HTTP-based client authentication.</span></span> <span data-ttu-id="44ff1-133">Este modo se debe utilizar con precaución.</span><span class="sxs-lookup"><span data-stu-id="44ff1-133">This mode should be used with caution.</span></span> <span data-ttu-id="44ff1-134">Se debe usar en entornos en los que la seguridad de transporte se proporciona por otros medios (como IPSec) y la infraestructura de WCF proporciona únicamente la autenticación del cliente.</span><span class="sxs-lookup"><span data-stu-id="44ff1-134">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="44ff1-135">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="44ff1-135">Child Elements</span></span>  
  
|<span data-ttu-id="44ff1-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="44ff1-136">Element</span></span>|<span data-ttu-id="44ff1-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="44ff1-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="44ff1-138">> de transporte de \<</span><span class="sxs-lookup"><span data-stu-id="44ff1-138">\<transport></span></span>](transport-of-webhttpbinding.md)|<span data-ttu-id="44ff1-139">Define la configuración de seguridad para el transporte.</span><span class="sxs-lookup"><span data-stu-id="44ff1-139">Defines the transport security settings.</span></span> <span data-ttu-id="44ff1-140">Este elemento corresponde al tipo <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="44ff1-140">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="44ff1-141">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="44ff1-141">Parent Elements</span></span>  
  
|<span data-ttu-id="44ff1-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="44ff1-142">Element</span></span>|<span data-ttu-id="44ff1-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="44ff1-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="44ff1-144">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="44ff1-144">\<webHttpBinding></span></span>](webhttpbinding.md)|<span data-ttu-id="44ff1-145">Un elemento de enlace que se utiliza para configurar los extremos de los servicios Web de Windows Communication Foundation (WCF) que responden a las solicitudes HTTP en lugar de a los mensajes SOAP.</span><span class="sxs-lookup"><span data-stu-id="44ff1-145">A binding element that is used to configure endpoints for Windows Communication Foundation (WCF) Web services that respond to HTTP requests instead of SOAP messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="44ff1-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="44ff1-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpBindingElement>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.WebHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.WebHttpSecurity>
- [<span data-ttu-id="44ff1-147">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="44ff1-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="44ff1-148">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="44ff1-148">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="44ff1-149">Enlaces</span><span class="sxs-lookup"><span data-stu-id="44ff1-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="44ff1-150">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="44ff1-150">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="44ff1-151">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="44ff1-151">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="44ff1-152">\<> de enlace</span><span class="sxs-lookup"><span data-stu-id="44ff1-152">\<binding></span></span>](bindings.md)
- [<span data-ttu-id="44ff1-153">Modelo de programación de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="44ff1-153">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)
