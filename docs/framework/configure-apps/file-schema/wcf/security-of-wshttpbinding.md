---
description: 'Más información sobre: <security> de <wsHttpBinding>'
title: <security> de <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 8658b162-2ddf-4162-a869-aa517a42288a
ms.openlocfilehash: 646d49bd67b2b544ae2616f206bfdeabf7806579
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683065"
---
# <a name="security-of-wshttpbinding"></a><span data-ttu-id="75829-103">\<security> de \<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="75829-103">\<security> of \<wsHttpBinding></span></span>

<span data-ttu-id="75829-104">Representa las capacidades de seguridad de [\<wsHttpBinding>](wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="75829-104">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsHttpBinding>**](wshttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="75829-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="75829-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="75829-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="75829-106">Attributes and Elements</span></span>  

 <span data-ttu-id="75829-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="75829-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="75829-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="75829-108">Attributes</span></span>  
  
|<span data-ttu-id="75829-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="75829-109">Attribute</span></span>|<span data-ttu-id="75829-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="75829-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="75829-111">mode</span><span class="sxs-lookup"><span data-stu-id="75829-111">mode</span></span>|<span data-ttu-id="75829-112">Opta.</span><span class="sxs-lookup"><span data-stu-id="75829-112">-   Optional.</span></span> <span data-ttu-id="75829-113">Especifica el tipo de seguridad que se aplica.</span><span class="sxs-lookup"><span data-stu-id="75829-113">Specifies the type of security that is applied.</span></span> <span data-ttu-id="75829-114">De manera predeterminada, es `Message`.</span><span class="sxs-lookup"><span data-stu-id="75829-114">The default is `Message`.</span></span><br /><span data-ttu-id="75829-115">: Este atributo es del tipo <xref:System.ServiceModel.SecurityMode> .</span><span class="sxs-lookup"><span data-stu-id="75829-115">-   This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="75829-116">Atributo mode</span><span class="sxs-lookup"><span data-stu-id="75829-116">Mode Attribute</span></span>  
  
|<span data-ttu-id="75829-117">Value</span><span class="sxs-lookup"><span data-stu-id="75829-117">Value</span></span>|<span data-ttu-id="75829-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="75829-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="75829-119">None</span><span class="sxs-lookup"><span data-stu-id="75829-119">None</span></span>|<span data-ttu-id="75829-120">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="75829-120">Security is disabled.</span></span>|  
|<span data-ttu-id="75829-121">Transporte</span><span class="sxs-lookup"><span data-stu-id="75829-121">Transport</span></span>|<span data-ttu-id="75829-122">La seguridad se proporciona utilizando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="75829-122">Security is provided using HTTPS.</span></span> <span data-ttu-id="75829-123">El servicio necesita ser configurado con certificados SSL.</span><span class="sxs-lookup"><span data-stu-id="75829-123">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="75829-124">El mensaje se protege completamente utilizando HTTPS y es autenticado por el cliente utilizando el Certificado SSL del servicio.</span><span class="sxs-lookup"><span data-stu-id="75829-124">The message is entirely secured using HTTPS and is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="75829-125">La autenticación del cliente se controla a través del atributo `ClientCredentials`.</span><span class="sxs-lookup"><span data-stu-id="75829-125">The client authentication is controlled through the `ClientCredentials` attribute.</span></span> <span data-ttu-id="75829-126">del [\<transport>](transport-of-wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="75829-126">of the [\<transport>](transport-of-wshttpbinding.md).</span></span>|  
|<span data-ttu-id="75829-127">Message</span><span class="sxs-lookup"><span data-stu-id="75829-127">Message</span></span>|<span data-ttu-id="75829-128">La seguridad se proporciona mediante la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="75829-128">Security is provided using SOAP message security.</span></span> <span data-ttu-id="75829-129">De forma predeterminada, el cuerpo SOAP se cifra y firma.</span><span class="sxs-lookup"><span data-stu-id="75829-129">By default, the SOAP body is Encrypted and Signed.</span></span> <span data-ttu-id="75829-130">Este modo proporciona una variedad de características, como si las credenciales del servicio están disponibles para el cliente fuera de la banda, el conjunto de algoritmos que se utiliza y qué nivel de protección se aplica al cuerpo del mensaje a través de la propiedad Security.Message.</span><span class="sxs-lookup"><span data-stu-id="75829-130">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the Security.Message property.</span></span> <span data-ttu-id="75829-131">Se realiza la autenticación del cliente una vez por sesión y los resultados de autenticación están almacenados en memoria caché durante la duración de la sesión.</span><span class="sxs-lookup"><span data-stu-id="75829-131">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="75829-132">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="75829-132">TransportWithMessageCredential</span></span>|<span data-ttu-id="75829-133">En este modo, HTTPS proporciona integridad, confidencialidad y autenticación de servidor y la seguridad del mensaje SOAP proporciona la autenticación del cliente.</span><span class="sxs-lookup"><span data-stu-id="75829-133">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="75829-134">De manera predeterminada, se realiza la autenticación del cliente una vez por sesión y los resultados de autenticación están almacenados en la memoria caché durante la duración de la sesión.</span><span class="sxs-lookup"><span data-stu-id="75829-134">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="75829-135">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="75829-135">Child Elements</span></span>  
  
|<span data-ttu-id="75829-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="75829-136">Element</span></span>|<span data-ttu-id="75829-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="75829-137">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-wshttpbinding.md)|<span data-ttu-id="75829-138">Define la configuración de seguridad para el transporte.</span><span class="sxs-lookup"><span data-stu-id="75829-138">Defines the transport security settings.</span></span> <span data-ttu-id="75829-139">Este elemento corresponde al tipo <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="75829-139">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
|[\<message>](message-of-wshttpbinding.md)|<span data-ttu-id="75829-140">Define la configuración de seguridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="75829-140">Defines the security settings for the message.</span></span> <span data-ttu-id="75829-141">Este elemento corresponde al tipo <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="75829-141">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="75829-142">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="75829-142">Parent Elements</span></span>  
  
|<span data-ttu-id="75829-143">Elemento</span><span class="sxs-lookup"><span data-stu-id="75829-143">Element</span></span>|<span data-ttu-id="75829-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="75829-144">Description</span></span>|  
|-------------|-----------------|  
|[\<wsHttpBinding>](wshttpbinding.md)|<span data-ttu-id="75829-145">Un enlace seguro para las aplicaciones de transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="75829-145">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75829-146">Observaciones</span><span class="sxs-lookup"><span data-stu-id="75829-146">Remarks</span></span>  

 <span data-ttu-id="75829-147">La clase WSHttpBinding está diseñada para la interoperación con servicios que implementan las especificaciones de WS-\*.</span><span class="sxs-lookup"><span data-stu-id="75829-147">The WSHttpBinding class is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="75829-148">La seguridad de transporte para este enlace es Capa de sockets seguros (SSL) sobre HTTP o HTTPS.</span><span class="sxs-lookup"><span data-stu-id="75829-148">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75829-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="75829-149">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- [<span data-ttu-id="75829-150">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="75829-150">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="75829-151">Enlaces</span><span class="sxs-lookup"><span data-stu-id="75829-151">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="75829-152">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="75829-152">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="75829-153">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="75829-153">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
