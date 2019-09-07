---
title: <security> de <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 8658b162-2ddf-4162-a869-aa517a42288a
ms.openlocfilehash: f7a4ef98637a7c966665fdd02ad26929bd4ba6ac
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399727"
---
# <a name="security-of-wshttpbinding"></a><span data-ttu-id="a05cd-102">\<> de seguridad \<de WSHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="a05cd-102">\<security> of \<wsHttpBinding></span></span>
<span data-ttu-id="a05cd-103">Representa las funciones de seguridad del [ \<> wsHttpBinding](wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="a05cd-103">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md).</span></span>  
  
<span data-ttu-id="a05cd-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a05cd-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a05cd-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a05cd-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a05cd-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enlaces**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="a05cd-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="a05cd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsHttpBinding >** ](wshttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="a05cd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsHttpBinding>**](wshttpbinding.md)</span></span>\
<span data-ttu-id="a05cd-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de enlace**</span><span class="sxs-lookup"><span data-stu-id="a05cd-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="a05cd-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de seguridad**</span><span class="sxs-lookup"><span data-stu-id="a05cd-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a05cd-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a05cd-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a05cd-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a05cd-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a05cd-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a05cd-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a05cd-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="a05cd-113">Attributes</span></span>  
  
|<span data-ttu-id="a05cd-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="a05cd-114">Attribute</span></span>|<span data-ttu-id="a05cd-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a05cd-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a05cd-116">modo</span><span class="sxs-lookup"><span data-stu-id="a05cd-116">mode</span></span>|<span data-ttu-id="a05cd-117">Opta.</span><span class="sxs-lookup"><span data-stu-id="a05cd-117">-   Optional.</span></span> <span data-ttu-id="a05cd-118">Especifica el tipo de seguridad que se aplica.</span><span class="sxs-lookup"><span data-stu-id="a05cd-118">Specifies the type of security that is applied.</span></span> <span data-ttu-id="a05cd-119">El valor predeterminado es `Message`.</span><span class="sxs-lookup"><span data-stu-id="a05cd-119">The default is `Message`.</span></span><br /><span data-ttu-id="a05cd-120">: Este atributo es del tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="a05cd-120">-   This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="a05cd-121">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="a05cd-121">Mode Attribute</span></span>  
  
|<span data-ttu-id="a05cd-122">Valor</span><span class="sxs-lookup"><span data-stu-id="a05cd-122">Value</span></span>|<span data-ttu-id="a05cd-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a05cd-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a05cd-124">None</span><span class="sxs-lookup"><span data-stu-id="a05cd-124">None</span></span>|<span data-ttu-id="a05cd-125">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="a05cd-125">Security is disabled.</span></span>|  
|<span data-ttu-id="a05cd-126">Transporte</span><span class="sxs-lookup"><span data-stu-id="a05cd-126">Transport</span></span>|<span data-ttu-id="a05cd-127">La seguridad se proporciona utilizando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a05cd-127">Security is provided using HTTPS.</span></span> <span data-ttu-id="a05cd-128">El servicio necesita ser configurado con certificados SSL.</span><span class="sxs-lookup"><span data-stu-id="a05cd-128">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="a05cd-129">El mensaje se protege completamente utilizando HTTPS y es autenticado por el cliente utilizando el Certificado SSL del servicio.</span><span class="sxs-lookup"><span data-stu-id="a05cd-129">The message is entirely secured using HTTPS and is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="a05cd-130">La autenticación del cliente se controla a través del atributo `ClientCredentials`.</span><span class="sxs-lookup"><span data-stu-id="a05cd-130">The client authentication is controlled through the `ClientCredentials` attribute.</span></span> <span data-ttu-id="a05cd-131">del > de [ transporte.\<](transport-of-wshttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="a05cd-131">of the [\<transport>](transport-of-wshttpbinding.md).</span></span>|  
|<span data-ttu-id="a05cd-132">Message</span><span class="sxs-lookup"><span data-stu-id="a05cd-132">Message</span></span>|<span data-ttu-id="a05cd-133">La seguridad se proporciona mediante la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="a05cd-133">Security is provided using SOAP message security.</span></span> <span data-ttu-id="a05cd-134">De forma predeterminada, el cuerpo SOAP se cifra y firma.</span><span class="sxs-lookup"><span data-stu-id="a05cd-134">By default, the SOAP body is Encrypted and Signed.</span></span> <span data-ttu-id="a05cd-135">Este modo proporciona una variedad de características, como si las credenciales del servicio están disponibles para el cliente fuera de la banda, el conjunto de algoritmos que se utiliza y qué nivel de protección se aplica al cuerpo del mensaje a través de la propiedad Security.Message.</span><span class="sxs-lookup"><span data-stu-id="a05cd-135">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the Security.Message property.</span></span> <span data-ttu-id="a05cd-136">Se realiza la autenticación del cliente una vez por sesión y los resultados de autenticación están almacenados en memoria caché durante la duración de la sesión.</span><span class="sxs-lookup"><span data-stu-id="a05cd-136">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="a05cd-137">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="a05cd-137">TransportWithMessageCredential</span></span>|<span data-ttu-id="a05cd-138">En este modo, HTTPS proporciona integridad, confidencialidad y autenticación de servidor y la seguridad del mensaje SOAP proporciona la autenticación del cliente.</span><span class="sxs-lookup"><span data-stu-id="a05cd-138">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="a05cd-139">De manera predeterminada, se realiza la autenticación del cliente una vez por sesión y los resultados de autenticación están almacenados en la memoria caché durante la duración de la sesión.</span><span class="sxs-lookup"><span data-stu-id="a05cd-139">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a05cd-140">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a05cd-140">Child Elements</span></span>  
  
|<span data-ttu-id="a05cd-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="a05cd-141">Element</span></span>|<span data-ttu-id="a05cd-142">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a05cd-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a05cd-143">\<> de transporte</span><span class="sxs-lookup"><span data-stu-id="a05cd-143">\<transport></span></span>](transport-of-wshttpbinding.md)|<span data-ttu-id="a05cd-144">Define la configuración de seguridad para el transporte.</span><span class="sxs-lookup"><span data-stu-id="a05cd-144">Defines the transport security settings.</span></span> <span data-ttu-id="a05cd-145">Este elemento corresponde al tipo <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="a05cd-145">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
|[<span data-ttu-id="a05cd-146">\<message></span><span class="sxs-lookup"><span data-stu-id="a05cd-146">\<message></span></span>](message-of-wshttpbinding.md)|<span data-ttu-id="a05cd-147">Define la configuración de seguridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="a05cd-147">Defines the security settings for the message.</span></span> <span data-ttu-id="a05cd-148">Este elemento corresponde al tipo <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="a05cd-148">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a05cd-149">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a05cd-149">Parent Elements</span></span>  
  
|<span data-ttu-id="a05cd-150">Elemento</span><span class="sxs-lookup"><span data-stu-id="a05cd-150">Element</span></span>|<span data-ttu-id="a05cd-151">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a05cd-151">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a05cd-152">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="a05cd-152">\<wsHttpBinding></span></span>](wshttpbinding.md)|<span data-ttu-id="a05cd-153">Un enlace seguro para las aplicaciones de transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="a05cd-153">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a05cd-154">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a05cd-154">Remarks</span></span>  
 <span data-ttu-id="a05cd-155">La clase WSHttpBinding está diseñada para la interoperación con servicios que implementan las especificaciones de WS-\*.</span><span class="sxs-lookup"><span data-stu-id="a05cd-155">The WSHttpBinding class is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="a05cd-156">La seguridad de transporte para este enlace es Capa de sockets seguros (SSL) sobre HTTP o HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a05cd-156">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a05cd-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="a05cd-157">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- [<span data-ttu-id="a05cd-158">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="a05cd-158">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="a05cd-159">Enlaces</span><span class="sxs-lookup"><span data-stu-id="a05cd-159">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a05cd-160">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="a05cd-160">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="a05cd-161">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="a05cd-161">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="a05cd-162">\<binding></span><span class="sxs-lookup"><span data-stu-id="a05cd-162">\<binding></span></span>](../../../misc/binding.md)
