---
title: <security> de <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: fdda0ff7-b462-4e26-af52-e87ddab71945
ms.openlocfilehash: ab5969da6a2d7cb59c057fd5bb909add6b6398a4
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399785"
---
# <a name="security-of-ws2007httpbinding"></a><span data-ttu-id="f0eb8-102">\<> de seguridad \<de ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="f0eb8-102">\<security> of \<ws2007HttpBinding></span></span>
<span data-ttu-id="f0eb8-103">Representa la configuración de seguridad utilizada con [ \<](ws2007httpbinding.md) el elemento > de ws2007HttpBinding.</span><span class="sxs-lookup"><span data-stu-id="f0eb8-103">Represents the security settings used with the [\<ws2007HttpBinding>](ws2007httpbinding.md) element.</span></span>  
  
<span data-ttu-id="f0eb8-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f0eb8-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f0eb8-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="f0eb8-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f0eb8-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enlaces**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="f0eb8-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="f0eb8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> ws2007HttpBinding**](ws2007httpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="f0eb8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007HttpBinding>**](ws2007httpbinding.md)</span></span>\
<span data-ttu-id="f0eb8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de enlace**</span><span class="sxs-lookup"><span data-stu-id="f0eb8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="f0eb8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de seguridad**</span><span class="sxs-lookup"><span data-stu-id="f0eb8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0eb8-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f0eb8-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f0eb8-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f0eb8-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f0eb8-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f0eb8-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f0eb8-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="f0eb8-113">Attributes</span></span>  
  
|<span data-ttu-id="f0eb8-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="f0eb8-114">Attribute</span></span>|<span data-ttu-id="f0eb8-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f0eb8-115">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="f0eb8-116">Opta.</span><span class="sxs-lookup"><span data-stu-id="f0eb8-116">-   Optional.</span></span> <span data-ttu-id="f0eb8-117">Especifica el tipo de seguridad que se aplica.</span><span class="sxs-lookup"><span data-stu-id="f0eb8-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="f0eb8-118">El valor predeterminado es `Message`.</span><span class="sxs-lookup"><span data-stu-id="f0eb8-118">The default is `Message`.</span></span><br /><br /> <span data-ttu-id="f0eb8-119">Este atributo es del tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="f0eb8-119">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="f0eb8-120">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="f0eb8-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="f0eb8-121">Valor</span><span class="sxs-lookup"><span data-stu-id="f0eb8-121">Value</span></span>|<span data-ttu-id="f0eb8-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f0eb8-122">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="f0eb8-123">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="f0eb8-123">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="f0eb8-124">La seguridad se proporciona utilizando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="f0eb8-124">Security is provided using HTTPS.</span></span> <span data-ttu-id="f0eb8-125">El servicio se debe configurar con certificados de Capa de sockets seguros (SSL).</span><span class="sxs-lookup"><span data-stu-id="f0eb8-125">The service must be configured with Secure Sockets Layer (SSL) certificates.</span></span> <span data-ttu-id="f0eb8-126">El mensaje se protege completamente utilizando HTTPS y el servicio se autentica por el cliente usando el certificado SSL del servicio.</span><span class="sxs-lookup"><span data-stu-id="f0eb8-126">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="f0eb8-127">La autenticación del cliente se controla a `ClientCredentials` través del atributo [ \<](transport-of-ws2007httpbinding.md) del elemento > de transporte.</span><span class="sxs-lookup"><span data-stu-id="f0eb8-127">The client authentication is controlled through the `ClientCredentials` attribute of the [\<transport>](transport-of-ws2007httpbinding.md) element.</span></span>|  
|`Message`|<span data-ttu-id="f0eb8-128">La seguridad se proporciona mediante la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="f0eb8-128">Security is provided using SOAP message security.</span></span> <span data-ttu-id="f0eb8-129">De forma predeterminada, el cuerpo SOAP se cifra y firma.</span><span class="sxs-lookup"><span data-stu-id="f0eb8-129">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="f0eb8-130">Este modo ofrece diversas características, como si las credenciales del servicio están disponibles para el cliente fuera de la banda, el conjunto de algoritmos que se van a usar y qué nivel de protección se aplica al cuerpo del mensaje a través de <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span><span class="sxs-lookup"><span data-stu-id="f0eb8-130">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span></span> <span data-ttu-id="f0eb8-131">Se realiza la autenticación del cliente una vez por cada sesión y los resultados de autenticación están almacenados en memoria caché durante la duración de la sesión.</span><span class="sxs-lookup"><span data-stu-id="f0eb8-131">Client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="f0eb8-132">En este modo, HTTPS proporciona integridad, confidencialidad y autenticación de servidor y la seguridad del mensaje SOAP proporciona la autenticación del cliente.</span><span class="sxs-lookup"><span data-stu-id="f0eb8-132">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="f0eb8-133">De manera predeterminada, se realiza la autenticación del cliente una vez por cada sesión y los resultados de autenticación están almacenados en la memoria caché durante la duración de la sesión.</span><span class="sxs-lookup"><span data-stu-id="f0eb8-133">By default, client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f0eb8-134">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f0eb8-134">Child Elements</span></span>  
  
|<span data-ttu-id="f0eb8-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="f0eb8-135">Element</span></span>|<span data-ttu-id="f0eb8-136">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f0eb8-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f0eb8-137">\<> de transporte</span><span class="sxs-lookup"><span data-stu-id="f0eb8-137">\<transport></span></span>](transport-of-ws2007httpbinding.md)|<span data-ttu-id="f0eb8-138">Define la configuración de seguridad para el transporte.</span><span class="sxs-lookup"><span data-stu-id="f0eb8-138">Defines the transport security settings.</span></span> <span data-ttu-id="f0eb8-139">Este elemento corresponde al tipo <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="f0eb8-139">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span> <span data-ttu-id="f0eb8-140">Esta configuración se aplica sólo cuando el modo se establece en Transporte.</span><span class="sxs-lookup"><span data-stu-id="f0eb8-140">These settings are applied only when the mode is set to Transport.</span></span>|  
|[<span data-ttu-id="f0eb8-141">\<message></span><span class="sxs-lookup"><span data-stu-id="f0eb8-141">\<message></span></span>](message-of-ws2007httpbinding.md)|<span data-ttu-id="f0eb8-142">Define la configuración de seguridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="f0eb8-142">Defines the security settings for the message.</span></span> <span data-ttu-id="f0eb8-143">Este elemento corresponde al tipo <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="f0eb8-143">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span> <span data-ttu-id="f0eb8-144">Esta configuración no se aplica cuando el modo se establece en Transporte.</span><span class="sxs-lookup"><span data-stu-id="f0eb8-144">These settings are not applied when the mode is set to Transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f0eb8-145">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f0eb8-145">Parent Elements</span></span>  
  
|<span data-ttu-id="f0eb8-146">Elemento</span><span class="sxs-lookup"><span data-stu-id="f0eb8-146">Element</span></span>|<span data-ttu-id="f0eb8-147">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f0eb8-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f0eb8-148">\<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="f0eb8-148">\<ws2007HttpBinding></span></span>](ws2007httpbinding.md)|<span data-ttu-id="f0eb8-149">Un enlace seguro para las aplicaciones de transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="f0eb8-149">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0eb8-150">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f0eb8-150">Remarks</span></span>  
 <span data-ttu-id="f0eb8-151">Este elemento está diseñado para la interoperación con servicios que implementan las especificaciones de WS-\*.</span><span class="sxs-lookup"><span data-stu-id="f0eb8-151">This element is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="f0eb8-152">La seguridad de transporte para este enlace es Capa de sockets seguros (SSL) sobre HTTP o HTTPS.</span><span class="sxs-lookup"><span data-stu-id="f0eb8-152">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0eb8-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0eb8-153">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="f0eb8-154">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="f0eb8-154">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="f0eb8-155">Enlaces</span><span class="sxs-lookup"><span data-stu-id="f0eb8-155">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f0eb8-156">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="f0eb8-156">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="f0eb8-157">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="f0eb8-157">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="f0eb8-158">\<binding></span><span class="sxs-lookup"><span data-stu-id="f0eb8-158">\<binding></span></span>](../../../misc/binding.md)
