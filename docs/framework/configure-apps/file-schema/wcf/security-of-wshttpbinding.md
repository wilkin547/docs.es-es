---
title: <security> de <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 8658b162-2ddf-4162-a869-aa517a42288a
ms.openlocfilehash: b66b5228cab9dbc35502a13a2d0fe56ce4c6a18d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738584"
---
# <a name="security-of-wshttpbinding"></a><span data-ttu-id="c9140-102">\<security> de \<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="c9140-102">\<security> of \<wsHttpBinding></span></span>
<span data-ttu-id="c9140-103">Representa las capacidades de seguridad de [\<wsHttpBinding>](wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="c9140-103">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsHttpBinding>**](wshttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="c9140-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c9140-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c9140-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c9140-105">Attributes and Elements</span></span>  
 <span data-ttu-id="c9140-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c9140-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c9140-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="c9140-107">Attributes</span></span>  
  
|<span data-ttu-id="c9140-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="c9140-108">Attribute</span></span>|<span data-ttu-id="c9140-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="c9140-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c9140-110">mode</span><span class="sxs-lookup"><span data-stu-id="c9140-110">mode</span></span>|<span data-ttu-id="c9140-111">Opta.</span><span class="sxs-lookup"><span data-stu-id="c9140-111">-   Optional.</span></span> <span data-ttu-id="c9140-112">Especifica el tipo de seguridad que se aplica.</span><span class="sxs-lookup"><span data-stu-id="c9140-112">Specifies the type of security that is applied.</span></span> <span data-ttu-id="c9140-113">De manera predeterminada, es `Message`.</span><span class="sxs-lookup"><span data-stu-id="c9140-113">The default is `Message`.</span></span><br /><span data-ttu-id="c9140-114">: Este atributo es del tipo <xref:System.ServiceModel.SecurityMode> .</span><span class="sxs-lookup"><span data-stu-id="c9140-114">-   This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="c9140-115">Atributo mode</span><span class="sxs-lookup"><span data-stu-id="c9140-115">Mode Attribute</span></span>  
  
|<span data-ttu-id="c9140-116">Value</span><span class="sxs-lookup"><span data-stu-id="c9140-116">Value</span></span>|<span data-ttu-id="c9140-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="c9140-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c9140-118">None</span><span class="sxs-lookup"><span data-stu-id="c9140-118">None</span></span>|<span data-ttu-id="c9140-119">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="c9140-119">Security is disabled.</span></span>|  
|<span data-ttu-id="c9140-120">Transporte</span><span class="sxs-lookup"><span data-stu-id="c9140-120">Transport</span></span>|<span data-ttu-id="c9140-121">La seguridad se proporciona utilizando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c9140-121">Security is provided using HTTPS.</span></span> <span data-ttu-id="c9140-122">El servicio necesita ser configurado con certificados SSL.</span><span class="sxs-lookup"><span data-stu-id="c9140-122">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="c9140-123">El mensaje se protege completamente utilizando HTTPS y es autenticado por el cliente utilizando el Certificado SSL del servicio.</span><span class="sxs-lookup"><span data-stu-id="c9140-123">The message is entirely secured using HTTPS and is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="c9140-124">La autenticación del cliente se controla a través del atributo `ClientCredentials`.</span><span class="sxs-lookup"><span data-stu-id="c9140-124">The client authentication is controlled through the `ClientCredentials` attribute.</span></span> <span data-ttu-id="c9140-125">del [\<transport>](transport-of-wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="c9140-125">of the [\<transport>](transport-of-wshttpbinding.md).</span></span>|  
|<span data-ttu-id="c9140-126">Message</span><span class="sxs-lookup"><span data-stu-id="c9140-126">Message</span></span>|<span data-ttu-id="c9140-127">La seguridad se proporciona mediante la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="c9140-127">Security is provided using SOAP message security.</span></span> <span data-ttu-id="c9140-128">De forma predeterminada, el cuerpo SOAP se cifra y firma.</span><span class="sxs-lookup"><span data-stu-id="c9140-128">By default, the SOAP body is Encrypted and Signed.</span></span> <span data-ttu-id="c9140-129">Este modo proporciona una variedad de características, como si las credenciales del servicio están disponibles para el cliente fuera de la banda, el conjunto de algoritmos que se utiliza y qué nivel de protección se aplica al cuerpo del mensaje a través de la propiedad Security.Message.</span><span class="sxs-lookup"><span data-stu-id="c9140-129">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the Security.Message property.</span></span> <span data-ttu-id="c9140-130">Se realiza la autenticación del cliente una vez por sesión y los resultados de autenticación están almacenados en memoria caché durante la duración de la sesión.</span><span class="sxs-lookup"><span data-stu-id="c9140-130">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="c9140-131">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="c9140-131">TransportWithMessageCredential</span></span>|<span data-ttu-id="c9140-132">En este modo, HTTPS proporciona integridad, confidencialidad y autenticación de servidor y la seguridad del mensaje SOAP proporciona la autenticación del cliente.</span><span class="sxs-lookup"><span data-stu-id="c9140-132">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="c9140-133">De manera predeterminada, se realiza la autenticación del cliente una vez por sesión y los resultados de autenticación están almacenados en la memoria caché durante la duración de la sesión.</span><span class="sxs-lookup"><span data-stu-id="c9140-133">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c9140-134">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c9140-134">Child Elements</span></span>  
  
|<span data-ttu-id="c9140-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="c9140-135">Element</span></span>|<span data-ttu-id="c9140-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="c9140-136">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-wshttpbinding.md)|<span data-ttu-id="c9140-137">Define la configuración de seguridad para el transporte.</span><span class="sxs-lookup"><span data-stu-id="c9140-137">Defines the transport security settings.</span></span> <span data-ttu-id="c9140-138">Este elemento corresponde al tipo <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="c9140-138">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
|[\<message>](message-of-wshttpbinding.md)|<span data-ttu-id="c9140-139">Define la configuración de seguridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="c9140-139">Defines the security settings for the message.</span></span> <span data-ttu-id="c9140-140">Este elemento corresponde al tipo <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="c9140-140">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c9140-141">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c9140-141">Parent Elements</span></span>  
  
|<span data-ttu-id="c9140-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="c9140-142">Element</span></span>|<span data-ttu-id="c9140-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="c9140-143">Description</span></span>|  
|-------------|-----------------|  
|[\<wsHttpBinding>](wshttpbinding.md)|<span data-ttu-id="c9140-144">Un enlace seguro para las aplicaciones de transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="c9140-144">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9140-145">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c9140-145">Remarks</span></span>  
 <span data-ttu-id="c9140-146">La clase WSHttpBinding está diseñada para la interoperación con servicios que implementan las especificaciones de WS-\*.</span><span class="sxs-lookup"><span data-stu-id="c9140-146">The WSHttpBinding class is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="c9140-147">La seguridad de transporte para este enlace es Capa de sockets seguros (SSL) sobre HTTP o HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c9140-147">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9140-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c9140-148">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- [<span data-ttu-id="c9140-149">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="c9140-149">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="c9140-150">Enlaces</span><span class="sxs-lookup"><span data-stu-id="c9140-150">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c9140-151">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="c9140-151">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="c9140-152">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="c9140-152">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
