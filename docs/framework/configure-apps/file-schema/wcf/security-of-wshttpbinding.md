---
title: <security> de <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 8658b162-2ddf-4162-a869-aa517a42288a
ms.openlocfilehash: 0de9ade585a2170aa1def9898581aedddc651bd7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57366093"
---
# <a name="security-of-wshttpbinding"></a><span data-ttu-id="91948-102">\<seguridad > de \<wsHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="91948-102">\<security> of \<wsHttpBinding></span></span>
<span data-ttu-id="91948-103">Representa las funciones de seguridad de la [ \<wsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="91948-103">Represents the security capabilities of the [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>  
  
 <span data-ttu-id="91948-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="91948-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="91948-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="91948-105">\<bindings></span></span>  
<span data-ttu-id="91948-106">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="91948-106">\<wsHttpBinding></span></span>  
<span data-ttu-id="91948-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="91948-107">\<binding></span></span>  
<span data-ttu-id="91948-108">\<security></span><span class="sxs-lookup"><span data-stu-id="91948-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91948-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="91948-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91948-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="91948-110">Attributes and Elements</span></span>  
 <span data-ttu-id="91948-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="91948-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91948-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="91948-112">Attributes</span></span>  
  
|<span data-ttu-id="91948-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="91948-113">Attribute</span></span>|<span data-ttu-id="91948-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="91948-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="91948-115">modo</span><span class="sxs-lookup"><span data-stu-id="91948-115">mode</span></span>|<span data-ttu-id="91948-116">-Opcional.</span><span class="sxs-lookup"><span data-stu-id="91948-116">-   Optional.</span></span> <span data-ttu-id="91948-117">Especifica el tipo de seguridad que se aplica.</span><span class="sxs-lookup"><span data-stu-id="91948-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="91948-118">De manera predeterminada, es `Message`.</span><span class="sxs-lookup"><span data-stu-id="91948-118">The default is `Message`.</span></span><br /><span data-ttu-id="91948-119">: Este atributo es del tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="91948-119">-   This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="91948-120">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="91948-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="91948-121">Valor</span><span class="sxs-lookup"><span data-stu-id="91948-121">Value</span></span>|<span data-ttu-id="91948-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="91948-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="91948-123">Ninguna</span><span class="sxs-lookup"><span data-stu-id="91948-123">None</span></span>|<span data-ttu-id="91948-124">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="91948-124">Security is disabled.</span></span>|  
|<span data-ttu-id="91948-125">Transporte</span><span class="sxs-lookup"><span data-stu-id="91948-125">Transport</span></span>|<span data-ttu-id="91948-126">La seguridad se proporciona utilizando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="91948-126">Security is provided using HTTPS.</span></span> <span data-ttu-id="91948-127">El servicio necesita ser configurado con certificados SSL.</span><span class="sxs-lookup"><span data-stu-id="91948-127">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="91948-128">El mensaje se protege completamente utilizando HTTPS y es autenticado por el cliente utilizando el Certificado SSL del servicio.</span><span class="sxs-lookup"><span data-stu-id="91948-128">The message is entirely secured using HTTPS and is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="91948-129">La autenticación del cliente se controla a través del atributo `ClientCredentials`.</span><span class="sxs-lookup"><span data-stu-id="91948-129">The client authentication is controlled through the `ClientCredentials` attribute.</span></span> <span data-ttu-id="91948-130">de la [ \<transporte >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="91948-130">of the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).</span></span>|  
|<span data-ttu-id="91948-131">Mensaje</span><span class="sxs-lookup"><span data-stu-id="91948-131">Message</span></span>|<span data-ttu-id="91948-132">La seguridad se proporciona mediante la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="91948-132">Security is provided using SOAP message security.</span></span> <span data-ttu-id="91948-133">De forma predeterminada, el cuerpo SOAP se cifra y firma.</span><span class="sxs-lookup"><span data-stu-id="91948-133">By default, the SOAP body is Encrypted and Signed.</span></span> <span data-ttu-id="91948-134">Este modo proporciona una variedad de características, como si las credenciales del servicio están disponibles para el cliente fuera de la banda, el conjunto de algoritmos que se utiliza y qué nivel de protección se aplica al cuerpo del mensaje a través de la propiedad Security.Message.</span><span class="sxs-lookup"><span data-stu-id="91948-134">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the Security.Message property.</span></span> <span data-ttu-id="91948-135">Se realiza la autenticación del cliente una vez por sesión y los resultados de autenticación están almacenados en memoria caché durante la duración de la sesión.</span><span class="sxs-lookup"><span data-stu-id="91948-135">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="91948-136">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="91948-136">TransportWithMessageCredential</span></span>|<span data-ttu-id="91948-137">En este modo, HTTPS proporciona integridad, confidencialidad y autenticación de servidor y la seguridad del mensaje SOAP proporciona la autenticación del cliente.</span><span class="sxs-lookup"><span data-stu-id="91948-137">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="91948-138">De manera predeterminada, se realiza la autenticación del cliente una vez por sesión y los resultados de autenticación están almacenados en la memoria caché durante la duración de la sesión.</span><span class="sxs-lookup"><span data-stu-id="91948-138">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="91948-139">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="91948-139">Child Elements</span></span>  
  
|<span data-ttu-id="91948-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="91948-140">Element</span></span>|<span data-ttu-id="91948-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="91948-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="91948-142">\<transport></span><span class="sxs-lookup"><span data-stu-id="91948-142">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md)|<span data-ttu-id="91948-143">Define la configuración de seguridad para el transporte.</span><span class="sxs-lookup"><span data-stu-id="91948-143">Defines the transport security settings.</span></span> <span data-ttu-id="91948-144">Este elemento corresponde al tipo <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="91948-144">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
|[<span data-ttu-id="91948-145">\<message></span><span class="sxs-lookup"><span data-stu-id="91948-145">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md)|<span data-ttu-id="91948-146">Define la configuración de seguridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="91948-146">Defines the security settings for the message.</span></span> <span data-ttu-id="91948-147">Este elemento corresponde al tipo <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="91948-147">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="91948-148">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="91948-148">Parent Elements</span></span>  
  
|<span data-ttu-id="91948-149">Elemento</span><span class="sxs-lookup"><span data-stu-id="91948-149">Element</span></span>|<span data-ttu-id="91948-150">Descripción</span><span class="sxs-lookup"><span data-stu-id="91948-150">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="91948-151">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="91948-151">\<wsHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|<span data-ttu-id="91948-152">Un enlace seguro para las aplicaciones de transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="91948-152">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91948-153">Comentarios</span><span class="sxs-lookup"><span data-stu-id="91948-153">Remarks</span></span>  
 <span data-ttu-id="91948-154">La clase WSHttpBinding está diseñada para la interoperación con servicios que implementan las especificaciones de WS-\*.</span><span class="sxs-lookup"><span data-stu-id="91948-154">The WSHttpBinding class is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="91948-155">La seguridad de transporte para este enlace es Capa de sockets seguros (SSL) sobre HTTP o HTTPS.</span><span class="sxs-lookup"><span data-stu-id="91948-155">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91948-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="91948-156">See also</span></span>
- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- [<span data-ttu-id="91948-157">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="91948-157">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="91948-158">Enlaces</span><span class="sxs-lookup"><span data-stu-id="91948-158">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="91948-159">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="91948-159">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="91948-160">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="91948-160">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="91948-161">\<binding></span><span class="sxs-lookup"><span data-stu-id="91948-161">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
