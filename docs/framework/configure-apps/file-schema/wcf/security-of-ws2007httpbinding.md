---
title: '&lt;security&gt; de &lt;ws2007HttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: fdda0ff7-b462-4e26-af52-e87ddab71945
ms.openlocfilehash: 6a07fb258a0a7c01293eddaf1eab4f82c4f632cb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54493760"
---
# <a name="ltsecuritygt-of-ltws2007httpbindinggt"></a><span data-ttu-id="c0573-102">&lt;security&gt; de &lt;ws2007HttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="c0573-102">&lt;security&gt; of &lt;ws2007HttpBinding&gt;</span></span>
<span data-ttu-id="c0573-103">Representa la configuración de seguridad utilizada con el [ \<ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="c0573-103">Represents the security settings used with the [\<ws2007HttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) element.</span></span>  
  
 <span data-ttu-id="c0573-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c0573-104">\<system.serviceModel></span></span>  
<span data-ttu-id="c0573-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="c0573-105">\<bindings></span></span>  
<span data-ttu-id="c0573-106">\<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="c0573-106">\<ws2007HttpBinding></span></span>  
<span data-ttu-id="c0573-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="c0573-107">\<binding></span></span>  
<span data-ttu-id="c0573-108">\<security></span><span class="sxs-lookup"><span data-stu-id="c0573-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0573-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c0573-109">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <bindings>
    <ws2007HttpBinding>
      <binding name = "String">
        <security mode="None/Message/Transport/TransportWithMessageCredential">
          <transport>
          </transport>
          <message>
          </message>
        </security>
      </binding>
    </ws2007HttpBinding>
  </bindings>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c0573-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c0573-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c0573-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c0573-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c0573-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="c0573-112">Attributes</span></span>  
  
|<span data-ttu-id="c0573-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="c0573-113">Attribute</span></span>|<span data-ttu-id="c0573-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="c0573-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="c0573-115">-Opcional.</span><span class="sxs-lookup"><span data-stu-id="c0573-115">-   Optional.</span></span> <span data-ttu-id="c0573-116">Especifica el tipo de seguridad que se aplica.</span><span class="sxs-lookup"><span data-stu-id="c0573-116">Specifies the type of security that is applied.</span></span> <span data-ttu-id="c0573-117">De manera predeterminada, es `Message`.</span><span class="sxs-lookup"><span data-stu-id="c0573-117">The default is `Message`.</span></span><br /><br /> <span data-ttu-id="c0573-118">Este atributo es del tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="c0573-118">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="c0573-119">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="c0573-119">Mode Attribute</span></span>  
  
|<span data-ttu-id="c0573-120">Valor</span><span class="sxs-lookup"><span data-stu-id="c0573-120">Value</span></span>|<span data-ttu-id="c0573-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="c0573-121">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="c0573-122">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="c0573-122">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="c0573-123">La seguridad se proporciona utilizando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c0573-123">Security is provided using HTTPS.</span></span> <span data-ttu-id="c0573-124">El servicio se debe configurar con certificados de Capa de sockets seguros (SSL).</span><span class="sxs-lookup"><span data-stu-id="c0573-124">The service must be configured with Secure Sockets Layer (SSL) certificates.</span></span> <span data-ttu-id="c0573-125">El mensaje se protege completamente utilizando HTTPS y el servicio se autentica por el cliente usando el certificado SSL del servicio.</span><span class="sxs-lookup"><span data-stu-id="c0573-125">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="c0573-126">La autenticación del cliente se controla mediante el `ClientCredentials` atributo de la [ \<transporte >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-ws2007httpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="c0573-126">The client authentication is controlled through the `ClientCredentials` attribute of the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-ws2007httpbinding.md) element.</span></span>|  
|`Message`|<span data-ttu-id="c0573-127">La seguridad se proporciona mediante la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="c0573-127">Security is provided using SOAP message security.</span></span> <span data-ttu-id="c0573-128">De forma predeterminada, el cuerpo SOAP se cifra y firma.</span><span class="sxs-lookup"><span data-stu-id="c0573-128">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="c0573-129">Este modo ofrece diversas características, como si las credenciales del servicio están disponibles para el cliente fuera de la banda, el conjunto de algoritmos que se van a usar y qué nivel de protección se aplica al cuerpo del mensaje a través de <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span><span class="sxs-lookup"><span data-stu-id="c0573-129">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span></span> <span data-ttu-id="c0573-130">Se realiza la autenticación del cliente una vez por cada sesión y los resultados de autenticación están almacenados en memoria caché durante la duración de la sesión.</span><span class="sxs-lookup"><span data-stu-id="c0573-130">Client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="c0573-131">En este modo, HTTPS proporciona integridad, confidencialidad y autenticación de servidor y la seguridad del mensaje SOAP proporciona la autenticación del cliente.</span><span class="sxs-lookup"><span data-stu-id="c0573-131">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="c0573-132">De manera predeterminada, se realiza la autenticación del cliente una vez por cada sesión y los resultados de autenticación están almacenados en la memoria caché durante la duración de la sesión.</span><span class="sxs-lookup"><span data-stu-id="c0573-132">By default, client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c0573-133">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c0573-133">Child Elements</span></span>  
  
|<span data-ttu-id="c0573-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="c0573-134">Element</span></span>|<span data-ttu-id="c0573-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="c0573-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c0573-136">\<transport></span><span class="sxs-lookup"><span data-stu-id="c0573-136">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-ws2007httpbinding.md)|<span data-ttu-id="c0573-137">Define la configuración de seguridad para el transporte.</span><span class="sxs-lookup"><span data-stu-id="c0573-137">Defines the transport security settings.</span></span> <span data-ttu-id="c0573-138">Este elemento corresponde al tipo <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="c0573-138">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span> <span data-ttu-id="c0573-139">Esta configuración se aplica sólo cuando el modo se establece en Transporte.</span><span class="sxs-lookup"><span data-stu-id="c0573-139">These settings are applied only when the mode is set to Transport.</span></span>|  
|[<span data-ttu-id="c0573-140">\<message></span><span class="sxs-lookup"><span data-stu-id="c0573-140">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-ws2007httpbinding.md)|<span data-ttu-id="c0573-141">Define la configuración de seguridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="c0573-141">Defines the security settings for the message.</span></span> <span data-ttu-id="c0573-142">Este elemento corresponde al tipo <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="c0573-142">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span> <span data-ttu-id="c0573-143">Esta configuración no se aplica cuando el modo se establece en Transporte.</span><span class="sxs-lookup"><span data-stu-id="c0573-143">These settings are not applied when the mode is set to Transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c0573-144">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c0573-144">Parent Elements</span></span>  
  
|<span data-ttu-id="c0573-145">Elemento</span><span class="sxs-lookup"><span data-stu-id="c0573-145">Element</span></span>|<span data-ttu-id="c0573-146">Descripción</span><span class="sxs-lookup"><span data-stu-id="c0573-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c0573-147">\<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="c0573-147">\<ws2007HttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md)|<span data-ttu-id="c0573-148">Un enlace seguro para las aplicaciones de transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="c0573-148">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0573-149">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c0573-149">Remarks</span></span>  
 <span data-ttu-id="c0573-150">Este elemento está diseñado para la interoperación con servicios que implementan las especificaciones de WS-\*.</span><span class="sxs-lookup"><span data-stu-id="c0573-150">This element is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="c0573-151">La seguridad de transporte para este enlace es Capa de sockets seguros (SSL) sobre HTTP o HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c0573-151">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0573-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0573-152">See also</span></span>
- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="c0573-153">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="c0573-153">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="c0573-154">Enlaces</span><span class="sxs-lookup"><span data-stu-id="c0573-154">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="c0573-155">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="c0573-155">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="c0573-156">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="c0573-156">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="c0573-157">\<binding></span><span class="sxs-lookup"><span data-stu-id="c0573-157">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
