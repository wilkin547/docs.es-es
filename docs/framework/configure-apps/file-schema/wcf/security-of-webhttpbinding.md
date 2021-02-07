---
description: 'Más información sobre: <security> de <webHttpBinding>'
title: <security> de <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
ms.openlocfilehash: a80a919ef877f01503e5ceaeb4fe7432e46f288c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683052"
---
# <a name="security-of-webhttpbinding"></a><span data-ttu-id="6f43c-103">\<security> de \<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="6f43c-103">\<security> of \<webHttpBinding></span></span>

<span data-ttu-id="6f43c-104">Especifica los requisitos de seguridad para un extremo configurado con [\<webHttpBinding>](webhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="6f43c-104">Specifies the security requirements for an endpoint configured with a [\<webHttpBinding>](webhttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<webHttpBinding>**](webhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="6f43c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6f43c-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6f43c-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6f43c-106">Attributes and Elements</span></span>  

 <span data-ttu-id="6f43c-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6f43c-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6f43c-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="6f43c-108">Attributes</span></span>  
  
|<span data-ttu-id="6f43c-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="6f43c-109">Attribute</span></span>|<span data-ttu-id="6f43c-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="6f43c-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6f43c-111">mode</span><span class="sxs-lookup"><span data-stu-id="6f43c-111">mode</span></span>|<span data-ttu-id="6f43c-112">Especifica si un punto de conexión usa la seguridad a nivel de transporte o no usa ninguna.</span><span class="sxs-lookup"><span data-stu-id="6f43c-112">Specifies whether transport-level security or no security is used by an endpoint.</span></span> <span data-ttu-id="6f43c-113">De manera predeterminada, es `None`.</span><span class="sxs-lookup"><span data-stu-id="6f43c-113">The default is `None`.</span></span> <span data-ttu-id="6f43c-114">Este atributo es del tipo <xref:System.ServiceModel.WebHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="6f43c-114">This attribute is of type <xref:System.ServiceModel.WebHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="6f43c-115">Atributo mode</span><span class="sxs-lookup"><span data-stu-id="6f43c-115">Mode Attribute</span></span>  
  
|<span data-ttu-id="6f43c-116">Value</span><span class="sxs-lookup"><span data-stu-id="6f43c-116">Value</span></span>|<span data-ttu-id="6f43c-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="6f43c-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6f43c-118">None</span><span class="sxs-lookup"><span data-stu-id="6f43c-118">None</span></span>|<span data-ttu-id="6f43c-119">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="6f43c-119">Security is disabled.</span></span>|  
|<span data-ttu-id="6f43c-120">Transporte</span><span class="sxs-lookup"><span data-stu-id="6f43c-120">Transport</span></span>|<span data-ttu-id="6f43c-121">La seguridad se proporciona utilizando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="6f43c-121">Security is provided using HTTPS.</span></span> <span data-ttu-id="6f43c-122">El servicio necesita ser configurado con certificados SSL.</span><span class="sxs-lookup"><span data-stu-id="6f43c-122">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="6f43c-123">El mensaje se protege completamente utilizando HTTPS y el servicio se autentica por el cliente usando el certificado SSL del servicio.</span><span class="sxs-lookup"><span data-stu-id="6f43c-123">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="6f43c-124">La autenticación del cliente se controla a través del `ClientCredentialType` atributo de [\<transport>](transport-of-webhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="6f43c-124">The client authentication is controlled through the `ClientCredentialType` attribute of the [\<transport>](transport-of-webhttpbinding.md).</span></span>|  
|<span data-ttu-id="6f43c-125">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="6f43c-125">TransportCredentialOnly</span></span>|<span data-ttu-id="6f43c-126">Este modo no proporciona integridad del mensaje y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="6f43c-126">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="6f43c-127">Proporciona la autenticación del cliente basada en HTTP.</span><span class="sxs-lookup"><span data-stu-id="6f43c-127">It provides HTTP-based client authentication.</span></span> <span data-ttu-id="6f43c-128">Este modo se debe utilizar con precaución.</span><span class="sxs-lookup"><span data-stu-id="6f43c-128">This mode should be used with caution.</span></span> <span data-ttu-id="6f43c-129">Se debe usar en entornos en los que la seguridad de transporte se proporciona por otros medios (como IPSec) y la infraestructura de WCF proporciona únicamente la autenticación del cliente.</span><span class="sxs-lookup"><span data-stu-id="6f43c-129">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6f43c-130">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6f43c-130">Child Elements</span></span>  
  
|<span data-ttu-id="6f43c-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="6f43c-131">Element</span></span>|<span data-ttu-id="6f43c-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="6f43c-132">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-webhttpbinding.md)|<span data-ttu-id="6f43c-133">Define la configuración de seguridad para el transporte.</span><span class="sxs-lookup"><span data-stu-id="6f43c-133">Defines the transport security settings.</span></span> <span data-ttu-id="6f43c-134">Este elemento corresponde al tipo <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="6f43c-134">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6f43c-135">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6f43c-135">Parent Elements</span></span>  
  
|<span data-ttu-id="6f43c-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="6f43c-136">Element</span></span>|<span data-ttu-id="6f43c-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="6f43c-137">Description</span></span>|  
|-------------|-----------------|  
|[\<webHttpBinding>](webhttpbinding.md)|<span data-ttu-id="6f43c-138">Un elemento de enlace que se utiliza para configurar los extremos de los servicios Web de Windows Communication Foundation (WCF) que responden a las solicitudes HTTP en lugar de a los mensajes SOAP.</span><span class="sxs-lookup"><span data-stu-id="6f43c-138">A binding element that is used to configure endpoints for Windows Communication Foundation (WCF) Web services that respond to HTTP requests instead of SOAP messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6f43c-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f43c-139">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpBindingElement>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.WebHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.WebHttpSecurity>
- [<span data-ttu-id="6f43c-140">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="6f43c-140">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="6f43c-141">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="6f43c-141">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="6f43c-142">Enlaces</span><span class="sxs-lookup"><span data-stu-id="6f43c-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="6f43c-143">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="6f43c-143">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="6f43c-144">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="6f43c-144">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [<span data-ttu-id="6f43c-145">Modelo de programación de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="6f43c-145">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)
