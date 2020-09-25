---
title: <security> de <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
ms.openlocfilehash: 60b863a0a2a846a60dde2e4b323a305b5096b1cc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169900"
---
# <a name="security-of-webhttpbinding"></a><span data-ttu-id="e20f4-102">\<security> de \<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="e20f4-102">\<security> of \<webHttpBinding></span></span>

<span data-ttu-id="e20f4-103">Especifica los requisitos de seguridad para un extremo configurado con [\<webHttpBinding>](webhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="e20f4-103">Specifies the security requirements for an endpoint configured with a [\<webHttpBinding>](webhttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<webHttpBinding>**](webhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="e20f4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e20f4-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e20f4-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e20f4-105">Attributes and Elements</span></span>  

 <span data-ttu-id="e20f4-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e20f4-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e20f4-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="e20f4-107">Attributes</span></span>  
  
|<span data-ttu-id="e20f4-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="e20f4-108">Attribute</span></span>|<span data-ttu-id="e20f4-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="e20f4-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e20f4-110">mode</span><span class="sxs-lookup"><span data-stu-id="e20f4-110">mode</span></span>|<span data-ttu-id="e20f4-111">Especifica si un punto de conexión usa la seguridad a nivel de transporte o no usa ninguna.</span><span class="sxs-lookup"><span data-stu-id="e20f4-111">Specifies whether transport-level security or no security is used by an endpoint.</span></span> <span data-ttu-id="e20f4-112">El valor predeterminado es `None`.</span><span class="sxs-lookup"><span data-stu-id="e20f4-112">The default is `None`.</span></span> <span data-ttu-id="e20f4-113">Este atributo es del tipo <xref:System.ServiceModel.WebHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="e20f4-113">This attribute is of type <xref:System.ServiceModel.WebHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="e20f4-114">Atributo mode</span><span class="sxs-lookup"><span data-stu-id="e20f4-114">Mode Attribute</span></span>  
  
|<span data-ttu-id="e20f4-115">Value</span><span class="sxs-lookup"><span data-stu-id="e20f4-115">Value</span></span>|<span data-ttu-id="e20f4-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="e20f4-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e20f4-117">None</span><span class="sxs-lookup"><span data-stu-id="e20f4-117">None</span></span>|<span data-ttu-id="e20f4-118">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="e20f4-118">Security is disabled.</span></span>|  
|<span data-ttu-id="e20f4-119">Transporte</span><span class="sxs-lookup"><span data-stu-id="e20f4-119">Transport</span></span>|<span data-ttu-id="e20f4-120">La seguridad se proporciona utilizando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e20f4-120">Security is provided using HTTPS.</span></span> <span data-ttu-id="e20f4-121">El servicio necesita ser configurado con certificados SSL.</span><span class="sxs-lookup"><span data-stu-id="e20f4-121">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="e20f4-122">El mensaje se protege completamente utilizando HTTPS y el servicio se autentica por el cliente usando el certificado SSL del servicio.</span><span class="sxs-lookup"><span data-stu-id="e20f4-122">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="e20f4-123">La autenticación del cliente se controla a través del `ClientCredentialType` atributo de [\<transport>](transport-of-webhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="e20f4-123">The client authentication is controlled through the `ClientCredentialType` attribute of the [\<transport>](transport-of-webhttpbinding.md).</span></span>|  
|<span data-ttu-id="e20f4-124">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="e20f4-124">TransportCredentialOnly</span></span>|<span data-ttu-id="e20f4-125">Este modo no proporciona integridad del mensaje y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="e20f4-125">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="e20f4-126">Proporciona la autenticación del cliente basada en HTTP.</span><span class="sxs-lookup"><span data-stu-id="e20f4-126">It provides HTTP-based client authentication.</span></span> <span data-ttu-id="e20f4-127">Este modo se debe utilizar con precaución.</span><span class="sxs-lookup"><span data-stu-id="e20f4-127">This mode should be used with caution.</span></span> <span data-ttu-id="e20f4-128">Se debe usar en entornos en los que la seguridad de transporte se proporciona por otros medios (como IPSec) y la infraestructura de WCF proporciona únicamente la autenticación del cliente.</span><span class="sxs-lookup"><span data-stu-id="e20f4-128">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e20f4-129">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e20f4-129">Child Elements</span></span>  
  
|<span data-ttu-id="e20f4-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="e20f4-130">Element</span></span>|<span data-ttu-id="e20f4-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="e20f4-131">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-webhttpbinding.md)|<span data-ttu-id="e20f4-132">Define la configuración de seguridad para el transporte.</span><span class="sxs-lookup"><span data-stu-id="e20f4-132">Defines the transport security settings.</span></span> <span data-ttu-id="e20f4-133">Este elemento corresponde al tipo <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="e20f4-133">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e20f4-134">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e20f4-134">Parent Elements</span></span>  
  
|<span data-ttu-id="e20f4-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="e20f4-135">Element</span></span>|<span data-ttu-id="e20f4-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="e20f4-136">Description</span></span>|  
|-------------|-----------------|  
|[\<webHttpBinding>](webhttpbinding.md)|<span data-ttu-id="e20f4-137">Un elemento de enlace que se utiliza para configurar los extremos de los servicios Web de Windows Communication Foundation (WCF) que responden a las solicitudes HTTP en lugar de a los mensajes SOAP.</span><span class="sxs-lookup"><span data-stu-id="e20f4-137">A binding element that is used to configure endpoints for Windows Communication Foundation (WCF) Web services that respond to HTTP requests instead of SOAP messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e20f4-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e20f4-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpBindingElement>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.WebHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.WebHttpSecurity>
- [<span data-ttu-id="e20f4-139">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="e20f4-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="e20f4-140">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="e20f4-140">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="e20f4-141">Enlaces</span><span class="sxs-lookup"><span data-stu-id="e20f4-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e20f4-142">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="e20f4-142">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e20f4-143">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="e20f4-143">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [<span data-ttu-id="e20f4-144">Modelo de programación de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="e20f4-144">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)
