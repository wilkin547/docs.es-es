---
title: <security> de <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 8658b162-2ddf-4162-a869-aa517a42288a
ms.openlocfilehash: b66b5228cab9dbc35502a13a2d0fe56ce4c6a18d
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738584"
---
# <a name="security-of-wshttpbinding"></a><span data-ttu-id="edb42-102">\<> de seguridad de \<wsHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="edb42-102">\<security> of \<wsHttpBinding></span></span>
<span data-ttu-id="edb42-103">Representa las capacidades de seguridad de la [\<wsHttpBinding >](wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="edb42-103">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md).</span></span>  
  
<span data-ttu-id="edb42-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="edb42-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="edb42-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="edb42-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="edb42-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**enlaces**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="edb42-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="edb42-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsHttpBinding**](wshttpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="edb42-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsHttpBinding>**](wshttpbinding.md)</span></span>\
<span data-ttu-id="edb42-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**enlace** ></span><span class="sxs-lookup"><span data-stu-id="edb42-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="edb42-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**seguridad** ></span><span class="sxs-lookup"><span data-stu-id="edb42-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edb42-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="edb42-110">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithMessageCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="String"
             defaultClientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             defaultProxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             defaultRealm="String" />
  <message clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           establishSecurityContext="Boolean"
           negotiateServiceCredential="Boolean" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="edb42-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="edb42-111">Attributes and Elements</span></span>  
 <span data-ttu-id="edb42-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="edb42-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="edb42-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="edb42-113">Attributes</span></span>  
  
|<span data-ttu-id="edb42-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="edb42-114">Attribute</span></span>|<span data-ttu-id="edb42-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="edb42-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="edb42-116">modo</span><span class="sxs-lookup"><span data-stu-id="edb42-116">mode</span></span>|<span data-ttu-id="edb42-117">Opta.</span><span class="sxs-lookup"><span data-stu-id="edb42-117">-   Optional.</span></span> <span data-ttu-id="edb42-118">Especifica el tipo de seguridad que se aplica.</span><span class="sxs-lookup"><span data-stu-id="edb42-118">Specifies the type of security that is applied.</span></span> <span data-ttu-id="edb42-119">De manera predeterminada, es `Message`.</span><span class="sxs-lookup"><span data-stu-id="edb42-119">The default is `Message`.</span></span><br /><span data-ttu-id="edb42-120">: Este atributo es del tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="edb42-120">-   This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="edb42-121">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="edb42-121">Mode Attribute</span></span>  
  
|<span data-ttu-id="edb42-122">Valor</span><span class="sxs-lookup"><span data-stu-id="edb42-122">Value</span></span>|<span data-ttu-id="edb42-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="edb42-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="edb42-124">Ninguno</span><span class="sxs-lookup"><span data-stu-id="edb42-124">None</span></span>|<span data-ttu-id="edb42-125">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="edb42-125">Security is disabled.</span></span>|  
|<span data-ttu-id="edb42-126">Transporte</span><span class="sxs-lookup"><span data-stu-id="edb42-126">Transport</span></span>|<span data-ttu-id="edb42-127">La seguridad se proporciona utilizando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="edb42-127">Security is provided using HTTPS.</span></span> <span data-ttu-id="edb42-128">El servicio necesita ser configurado con certificados SSL.</span><span class="sxs-lookup"><span data-stu-id="edb42-128">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="edb42-129">El mensaje se protege completamente utilizando HTTPS y es autenticado por el cliente utilizando el Certificado SSL del servicio.</span><span class="sxs-lookup"><span data-stu-id="edb42-129">The message is entirely secured using HTTPS and is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="edb42-130">La autenticación del cliente se controla a través del atributo `ClientCredentials`.</span><span class="sxs-lookup"><span data-stu-id="edb42-130">The client authentication is controlled through the `ClientCredentials` attribute.</span></span> <span data-ttu-id="edb42-131">del [> de transporte de\<](transport-of-wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="edb42-131">of the [\<transport>](transport-of-wshttpbinding.md).</span></span>|  
|<span data-ttu-id="edb42-132">Mensaje</span><span class="sxs-lookup"><span data-stu-id="edb42-132">Message</span></span>|<span data-ttu-id="edb42-133">La seguridad se proporciona mediante la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="edb42-133">Security is provided using SOAP message security.</span></span> <span data-ttu-id="edb42-134">De forma predeterminada, el cuerpo SOAP se cifra y firma.</span><span class="sxs-lookup"><span data-stu-id="edb42-134">By default, the SOAP body is Encrypted and Signed.</span></span> <span data-ttu-id="edb42-135">Este modo proporciona una variedad de características, como si las credenciales del servicio están disponibles para el cliente fuera de la banda, el conjunto de algoritmos que se utiliza y qué nivel de protección se aplica al cuerpo del mensaje a través de la propiedad Security.Message.</span><span class="sxs-lookup"><span data-stu-id="edb42-135">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the Security.Message property.</span></span> <span data-ttu-id="edb42-136">Se realiza la autenticación del cliente una vez por sesión y los resultados de autenticación están almacenados en memoria caché durante la duración de la sesión.</span><span class="sxs-lookup"><span data-stu-id="edb42-136">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="edb42-137">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="edb42-137">TransportWithMessageCredential</span></span>|<span data-ttu-id="edb42-138">En este modo, HTTPS proporciona integridad, confidencialidad y autenticación de servidor y la seguridad del mensaje SOAP proporciona la autenticación del cliente.</span><span class="sxs-lookup"><span data-stu-id="edb42-138">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="edb42-139">De manera predeterminada, se realiza la autenticación del cliente una vez por sesión y los resultados de autenticación están almacenados en la memoria caché durante la duración de la sesión.</span><span class="sxs-lookup"><span data-stu-id="edb42-139">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="edb42-140">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="edb42-140">Child Elements</span></span>  
  
|<span data-ttu-id="edb42-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="edb42-141">Element</span></span>|<span data-ttu-id="edb42-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="edb42-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="edb42-143">> de transporte de \<</span><span class="sxs-lookup"><span data-stu-id="edb42-143">\<transport></span></span>](transport-of-wshttpbinding.md)|<span data-ttu-id="edb42-144">Define la configuración de seguridad para el transporte.</span><span class="sxs-lookup"><span data-stu-id="edb42-144">Defines the transport security settings.</span></span> <span data-ttu-id="edb42-145">Este elemento corresponde al tipo <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="edb42-145">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
|[<span data-ttu-id="edb42-146">\<> de mensaje</span><span class="sxs-lookup"><span data-stu-id="edb42-146">\<message></span></span>](message-of-wshttpbinding.md)|<span data-ttu-id="edb42-147">Define la configuración de seguridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="edb42-147">Defines the security settings for the message.</span></span> <span data-ttu-id="edb42-148">Este elemento corresponde al tipo <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="edb42-148">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="edb42-149">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="edb42-149">Parent Elements</span></span>  
  
|<span data-ttu-id="edb42-150">Elemento</span><span class="sxs-lookup"><span data-stu-id="edb42-150">Element</span></span>|<span data-ttu-id="edb42-151">Descripción</span><span class="sxs-lookup"><span data-stu-id="edb42-151">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="edb42-152">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="edb42-152">\<wsHttpBinding></span></span>](wshttpbinding.md)|<span data-ttu-id="edb42-153">Un enlace seguro para las aplicaciones de transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="edb42-153">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="edb42-154">Comentarios</span><span class="sxs-lookup"><span data-stu-id="edb42-154">Remarks</span></span>  
 <span data-ttu-id="edb42-155">La clase WSHttpBinding está diseñada para la interoperación con servicios que implementan las especificaciones de WS-\*.</span><span class="sxs-lookup"><span data-stu-id="edb42-155">The WSHttpBinding class is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="edb42-156">La seguridad de transporte para este enlace es Capa de sockets seguros (SSL) sobre HTTP o HTTPS.</span><span class="sxs-lookup"><span data-stu-id="edb42-156">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edb42-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="edb42-157">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- [<span data-ttu-id="edb42-158">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="edb42-158">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="edb42-159">Enlaces</span><span class="sxs-lookup"><span data-stu-id="edb42-159">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="edb42-160">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="edb42-160">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="edb42-161">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="edb42-161">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="edb42-162">\<> de enlace</span><span class="sxs-lookup"><span data-stu-id="edb42-162">\<binding></span></span>](bindings.md)
