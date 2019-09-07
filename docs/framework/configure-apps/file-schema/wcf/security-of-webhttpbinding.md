---
title: <security> de <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
ms.openlocfilehash: 2f0bc97e10fcd72f2f33cc20730320cbbfc42dd8
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399772"
---
# <a name="security-of-webhttpbinding"></a><span data-ttu-id="4e4d6-102">\<> de seguridad \<de webHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="4e4d6-102">\<security> of \<webHttpBinding></span></span>
<span data-ttu-id="4e4d6-103">Especifica los requisitos de seguridad para un extremo configurado con un [ \<> webHttpBinding](webhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="4e4d6-103">Specifies the security requirements for an endpoint configured with a [\<webHttpBinding>](webhttpbinding.md).</span></span>  
  
<span data-ttu-id="4e4d6-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4e4d6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4e4d6-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4e4d6-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4e4d6-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enlaces**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="4e4d6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="4e4d6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<webHttpBinding >** ](webhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="4e4d6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<webHttpBinding>**](webhttpbinding.md)</span></span>\
<span data-ttu-id="4e4d6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de enlace**</span><span class="sxs-lookup"><span data-stu-id="4e4d6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="4e4d6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de seguridad**</span><span class="sxs-lookup"><span data-stu-id="4e4d6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e4d6-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4e4d6-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4e4d6-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4e4d6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="4e4d6-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4e4d6-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4e4d6-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="4e4d6-113">Attributes</span></span>  
  
|<span data-ttu-id="4e4d6-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="4e4d6-114">Attribute</span></span>|<span data-ttu-id="4e4d6-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4e4d6-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4e4d6-116">modo</span><span class="sxs-lookup"><span data-stu-id="4e4d6-116">mode</span></span>|<span data-ttu-id="4e4d6-117">Especifica si un punto de conexión usa la seguridad a nivel de transporte o no usa ninguna.</span><span class="sxs-lookup"><span data-stu-id="4e4d6-117">Specifies whether transport-level security or no security is used by an endpoint.</span></span> <span data-ttu-id="4e4d6-118">El valor predeterminado es `None`.</span><span class="sxs-lookup"><span data-stu-id="4e4d6-118">The default is `None`.</span></span> <span data-ttu-id="4e4d6-119">Este atributo es del tipo <xref:System.ServiceModel.WebHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="4e4d6-119">This attribute is of type <xref:System.ServiceModel.WebHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="4e4d6-120">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="4e4d6-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="4e4d6-121">Valor</span><span class="sxs-lookup"><span data-stu-id="4e4d6-121">Value</span></span>|<span data-ttu-id="4e4d6-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4e4d6-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4e4d6-123">None</span><span class="sxs-lookup"><span data-stu-id="4e4d6-123">None</span></span>|<span data-ttu-id="4e4d6-124">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="4e4d6-124">Security is disabled.</span></span>|  
|<span data-ttu-id="4e4d6-125">Transporte</span><span class="sxs-lookup"><span data-stu-id="4e4d6-125">Transport</span></span>|<span data-ttu-id="4e4d6-126">La seguridad se proporciona utilizando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="4e4d6-126">Security is provided using HTTPS.</span></span> <span data-ttu-id="4e4d6-127">El servicio necesita ser configurado con certificados SSL.</span><span class="sxs-lookup"><span data-stu-id="4e4d6-127">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="4e4d6-128">El mensaje se protege completamente utilizando HTTPS y el servicio se autentica por el cliente usando el certificado SSL del servicio.</span><span class="sxs-lookup"><span data-stu-id="4e4d6-128">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="4e4d6-129">La autenticación del cliente se controla a `ClientCredentialType` través del atributo [ \<del > de transporte](transport-of-webhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="4e4d6-129">The client authentication is controlled through the `ClientCredentialType` attribute of the [\<transport>](transport-of-webhttpbinding.md).</span></span>|  
|<span data-ttu-id="4e4d6-130">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="4e4d6-130">TransportCredentialOnly</span></span>|<span data-ttu-id="4e4d6-131">Este modo no proporciona integridad del mensaje y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="4e4d6-131">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="4e4d6-132">Proporciona la autenticación del cliente basada en HTTP.</span><span class="sxs-lookup"><span data-stu-id="4e4d6-132">It provides HTTP-based client authentication.</span></span> <span data-ttu-id="4e4d6-133">Este modo se debe utilizar con precaución.</span><span class="sxs-lookup"><span data-stu-id="4e4d6-133">This mode should be used with caution.</span></span> <span data-ttu-id="4e4d6-134">Se debe usar en entornos en los que la seguridad de transporte se proporciona por otros medios (como IPSec) y la infraestructura de WCF proporciona únicamente la autenticación del cliente.</span><span class="sxs-lookup"><span data-stu-id="4e4d6-134">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4e4d6-135">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4e4d6-135">Child Elements</span></span>  
  
|<span data-ttu-id="4e4d6-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="4e4d6-136">Element</span></span>|<span data-ttu-id="4e4d6-137">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4e4d6-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4e4d6-138">\<> de transporte</span><span class="sxs-lookup"><span data-stu-id="4e4d6-138">\<transport></span></span>](transport-of-webhttpbinding.md)|<span data-ttu-id="4e4d6-139">Define la configuración de seguridad para el transporte.</span><span class="sxs-lookup"><span data-stu-id="4e4d6-139">Defines the transport security settings.</span></span> <span data-ttu-id="4e4d6-140">Este elemento corresponde al tipo <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="4e4d6-140">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4e4d6-141">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4e4d6-141">Parent Elements</span></span>  
  
|<span data-ttu-id="4e4d6-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="4e4d6-142">Element</span></span>|<span data-ttu-id="4e4d6-143">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4e4d6-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4e4d6-144">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="4e4d6-144">\<webHttpBinding></span></span>](webhttpbinding.md)|<span data-ttu-id="4e4d6-145">Un elemento de enlace que se utiliza para configurar los extremos de los servicios Web de Windows Communication Foundation (WCF) que responden a las solicitudes HTTP en lugar de a los mensajes SOAP.</span><span class="sxs-lookup"><span data-stu-id="4e4d6-145">A binding element that is used to configure endpoints for Windows Communication Foundation (WCF) Web services that respond to HTTP requests instead of SOAP messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4e4d6-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e4d6-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpBindingElement>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.WebHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.WebHttpSecurity>
- [<span data-ttu-id="4e4d6-147">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="4e4d6-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="4e4d6-148">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="4e4d6-148">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="4e4d6-149">Enlaces</span><span class="sxs-lookup"><span data-stu-id="4e4d6-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="4e4d6-150">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="4e4d6-150">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="4e4d6-151">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="4e4d6-151">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="4e4d6-152">\<binding></span><span class="sxs-lookup"><span data-stu-id="4e4d6-152">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="4e4d6-153">Modelo de programación de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="4e4d6-153">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)
