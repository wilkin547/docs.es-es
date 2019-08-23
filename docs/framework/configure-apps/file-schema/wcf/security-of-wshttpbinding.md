---
title: <security> de <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 8658b162-2ddf-4162-a869-aa517a42288a
ms.openlocfilehash: e627a63221d0013c89495d7ff81e02047a03df89
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936508"
---
# <a name="security-of-wshttpbinding"></a><span data-ttu-id="59118-102">\<> de seguridad \<de WSHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="59118-102">\<security> of \<wsHttpBinding></span></span>
<span data-ttu-id="59118-103">Representa las funciones de seguridad del [ \<> wsHttpBinding](wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="59118-103">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md).</span></span>  
  
 <span data-ttu-id="59118-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="59118-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="59118-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="59118-105">\<bindings></span></span>  
<span data-ttu-id="59118-106">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="59118-106">\<wsHttpBinding></span></span>  
<span data-ttu-id="59118-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="59118-107">\<binding></span></span>  
<span data-ttu-id="59118-108">\<> de seguridad</span><span class="sxs-lookup"><span data-stu-id="59118-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59118-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="59118-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59118-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="59118-110">Attributes and Elements</span></span>  
 <span data-ttu-id="59118-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="59118-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59118-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="59118-112">Attributes</span></span>  
  
|<span data-ttu-id="59118-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="59118-113">Attribute</span></span>|<span data-ttu-id="59118-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="59118-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="59118-115">modo</span><span class="sxs-lookup"><span data-stu-id="59118-115">mode</span></span>|<span data-ttu-id="59118-116">Opta.</span><span class="sxs-lookup"><span data-stu-id="59118-116">-   Optional.</span></span> <span data-ttu-id="59118-117">Especifica el tipo de seguridad que se aplica.</span><span class="sxs-lookup"><span data-stu-id="59118-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="59118-118">El valor predeterminado es `Message`.</span><span class="sxs-lookup"><span data-stu-id="59118-118">The default is `Message`.</span></span><br /><span data-ttu-id="59118-119">: Este atributo es del tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="59118-119">-   This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="59118-120">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="59118-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="59118-121">Valor</span><span class="sxs-lookup"><span data-stu-id="59118-121">Value</span></span>|<span data-ttu-id="59118-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="59118-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="59118-123">None</span><span class="sxs-lookup"><span data-stu-id="59118-123">None</span></span>|<span data-ttu-id="59118-124">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="59118-124">Security is disabled.</span></span>|  
|<span data-ttu-id="59118-125">Transporte</span><span class="sxs-lookup"><span data-stu-id="59118-125">Transport</span></span>|<span data-ttu-id="59118-126">La seguridad se proporciona utilizando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="59118-126">Security is provided using HTTPS.</span></span> <span data-ttu-id="59118-127">El servicio necesita ser configurado con certificados SSL.</span><span class="sxs-lookup"><span data-stu-id="59118-127">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="59118-128">El mensaje se protege completamente utilizando HTTPS y es autenticado por el cliente utilizando el Certificado SSL del servicio.</span><span class="sxs-lookup"><span data-stu-id="59118-128">The message is entirely secured using HTTPS and is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="59118-129">La autenticación del cliente se controla a través del atributo `ClientCredentials`.</span><span class="sxs-lookup"><span data-stu-id="59118-129">The client authentication is controlled through the `ClientCredentials` attribute.</span></span> <span data-ttu-id="59118-130">del > de [ transporte.\<](transport-of-wshttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="59118-130">of the [\<transport>](transport-of-wshttpbinding.md).</span></span>|  
|<span data-ttu-id="59118-131">Message</span><span class="sxs-lookup"><span data-stu-id="59118-131">Message</span></span>|<span data-ttu-id="59118-132">La seguridad se proporciona mediante la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="59118-132">Security is provided using SOAP message security.</span></span> <span data-ttu-id="59118-133">De forma predeterminada, el cuerpo SOAP se cifra y firma.</span><span class="sxs-lookup"><span data-stu-id="59118-133">By default, the SOAP body is Encrypted and Signed.</span></span> <span data-ttu-id="59118-134">Este modo proporciona una variedad de características, como si las credenciales del servicio están disponibles para el cliente fuera de la banda, el conjunto de algoritmos que se utiliza y qué nivel de protección se aplica al cuerpo del mensaje a través de la propiedad Security.Message.</span><span class="sxs-lookup"><span data-stu-id="59118-134">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the Security.Message property.</span></span> <span data-ttu-id="59118-135">Se realiza la autenticación del cliente una vez por sesión y los resultados de autenticación están almacenados en memoria caché durante la duración de la sesión.</span><span class="sxs-lookup"><span data-stu-id="59118-135">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="59118-136">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="59118-136">TransportWithMessageCredential</span></span>|<span data-ttu-id="59118-137">En este modo, HTTPS proporciona integridad, confidencialidad y autenticación de servidor y la seguridad del mensaje SOAP proporciona la autenticación del cliente.</span><span class="sxs-lookup"><span data-stu-id="59118-137">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="59118-138">De manera predeterminada, se realiza la autenticación del cliente una vez por sesión y los resultados de autenticación están almacenados en la memoria caché durante la duración de la sesión.</span><span class="sxs-lookup"><span data-stu-id="59118-138">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="59118-139">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="59118-139">Child Elements</span></span>  
  
|<span data-ttu-id="59118-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="59118-140">Element</span></span>|<span data-ttu-id="59118-141">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="59118-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="59118-142">\<> de transporte</span><span class="sxs-lookup"><span data-stu-id="59118-142">\<transport></span></span>](transport-of-wshttpbinding.md)|<span data-ttu-id="59118-143">Define la configuración de seguridad para el transporte.</span><span class="sxs-lookup"><span data-stu-id="59118-143">Defines the transport security settings.</span></span> <span data-ttu-id="59118-144">Este elemento corresponde al tipo <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="59118-144">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
|[<span data-ttu-id="59118-145">\<message></span><span class="sxs-lookup"><span data-stu-id="59118-145">\<message></span></span>](message-of-wshttpbinding.md)|<span data-ttu-id="59118-146">Define la configuración de seguridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="59118-146">Defines the security settings for the message.</span></span> <span data-ttu-id="59118-147">Este elemento corresponde al tipo <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="59118-147">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="59118-148">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="59118-148">Parent Elements</span></span>  
  
|<span data-ttu-id="59118-149">Elemento</span><span class="sxs-lookup"><span data-stu-id="59118-149">Element</span></span>|<span data-ttu-id="59118-150">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="59118-150">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="59118-151">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="59118-151">\<wsHttpBinding></span></span>](wshttpbinding.md)|<span data-ttu-id="59118-152">Un enlace seguro para las aplicaciones de transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="59118-152">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59118-153">Comentarios</span><span class="sxs-lookup"><span data-stu-id="59118-153">Remarks</span></span>  
 <span data-ttu-id="59118-154">La clase WSHttpBinding está diseñada para la interoperación con servicios que implementan las especificaciones de WS-\*.</span><span class="sxs-lookup"><span data-stu-id="59118-154">The WSHttpBinding class is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="59118-155">La seguridad de transporte para este enlace es Capa de sockets seguros (SSL) sobre HTTP o HTTPS.</span><span class="sxs-lookup"><span data-stu-id="59118-155">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59118-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="59118-156">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- [<span data-ttu-id="59118-157">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="59118-157">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="59118-158">Enlaces</span><span class="sxs-lookup"><span data-stu-id="59118-158">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="59118-159">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="59118-159">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="59118-160">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="59118-160">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="59118-161">\<binding></span><span class="sxs-lookup"><span data-stu-id="59118-161">\<binding></span></span>](../../../misc/binding.md)
