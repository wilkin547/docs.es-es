---
title: <security> de <basicHttpBinding>
ms.date: 03/30/2017
ms.assetid: 6432708d-5465-4bd9-bfc2-466742db99cb
ms.openlocfilehash: c8e4f2d000a155eecd2a6c7faaaf4af525b24ca3
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738706"
---
# <a name="security-of-basichttpbinding"></a><span data-ttu-id="8a469-102">\<> de seguridad de \<basicHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="8a469-102">\<security> of \<basicHttpBinding></span></span>
<span data-ttu-id="8a469-103">Define las capacidades de seguridad del [> de\<basicHttpBinding](basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="8a469-103">Defines the security capabilities of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>  
  
<span data-ttu-id="8a469-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8a469-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8a469-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="8a469-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8a469-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**enlaces**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="8a469-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="8a469-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**basicHttpBinding**](basichttpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="8a469-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<basicHttpBinding>**](basichttpbinding.md)</span></span>\
<span data-ttu-id="8a469-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**enlace** ></span><span class="sxs-lookup"><span data-stu-id="8a469-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="8a469-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**seguridad** ></span><span class="sxs-lookup"><span data-stu-id="8a469-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a469-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8a469-110">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8a469-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8a469-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8a469-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8a469-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8a469-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="8a469-113">Attributes</span></span>  
  
|<span data-ttu-id="8a469-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="8a469-114">Attribute</span></span>|<span data-ttu-id="8a469-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a469-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8a469-116">modo</span><span class="sxs-lookup"><span data-stu-id="8a469-116">mode</span></span>|<span data-ttu-id="8a469-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="8a469-117">Optional.</span></span> <span data-ttu-id="8a469-118">Especifica el tipo de seguridad que se utiliza.</span><span class="sxs-lookup"><span data-stu-id="8a469-118">Specifies the type of security that is used.</span></span> <span data-ttu-id="8a469-119">De manera predeterminada, es `None`.</span><span class="sxs-lookup"><span data-stu-id="8a469-119">The default is `None`.</span></span> <span data-ttu-id="8a469-120">Este atributo es del tipo <xref:System.ServiceModel.BasicHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="8a469-120">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="8a469-121">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="8a469-121">mode Attribute</span></span>  
  
|<span data-ttu-id="8a469-122">Valor</span><span class="sxs-lookup"><span data-stu-id="8a469-122">Value</span></span>|<span data-ttu-id="8a469-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a469-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8a469-124">Ninguno</span><span class="sxs-lookup"><span data-stu-id="8a469-124">None</span></span>|<span data-ttu-id="8a469-125">: Los mensajes no están protegidos durante la transferencia.</span><span class="sxs-lookup"><span data-stu-id="8a469-125">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="8a469-126">Transporte</span><span class="sxs-lookup"><span data-stu-id="8a469-126">Transport</span></span>|<span data-ttu-id="8a469-127">La seguridad se proporciona utilizando transporte HTTPS.</span><span class="sxs-lookup"><span data-stu-id="8a469-127">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="8a469-128">Los mensajes SOAP se protegen utilizando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="8a469-128">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="8a469-129">El servicio se autentica al cliente utilizando el certificado X.509 del servicio.</span><span class="sxs-lookup"><span data-stu-id="8a469-129">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="8a469-130">El cliente se autentica utilizando el ClientCredentialType proporcionado.</span><span class="sxs-lookup"><span data-stu-id="8a469-130">The client is authenticated using the ClientCredentialType supplied.</span></span> <span data-ttu-id="8a469-131">Vea el [> de transporte de\<](transport-of-basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="8a469-131">See the [\<transport>](transport-of-basichttpbinding.md).</span></span>|  
|<span data-ttu-id="8a469-132">Mensaje</span><span class="sxs-lookup"><span data-stu-id="8a469-132">Message</span></span>|<span data-ttu-id="8a469-133">La seguridad se proporciona mediante la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="8a469-133">Security is provided using SOAP message security.</span></span> <span data-ttu-id="8a469-134">De forma predeterminada, el cuerpo se cifra y firma.</span><span class="sxs-lookup"><span data-stu-id="8a469-134">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="8a469-135">Para este enlace, el sistema requiere que el certificado de servidor se proporcione al cliente fuera de la banda.</span><span class="sxs-lookup"><span data-stu-id="8a469-135">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="8a469-136">El único `ClientCredentialType` válido para este enlace es `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="8a469-136">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|  
|<span data-ttu-id="8a469-137">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="8a469-137">TransportWithMessageCredential</span></span>|<span data-ttu-id="8a469-138">La seguridad de transporte proporciona integridad, confidencialidad y autenticación del servidor.</span><span class="sxs-lookup"><span data-stu-id="8a469-138">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="8a469-139">La autenticación del cliente se proporciona por medio de la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="8a469-139">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="8a469-140">Este modo es pertinente cuando el usuario está autenticando utilizando el nombre de usuario/contraseña y existe una implementación del HTTP existente para proteger la transferencia del mensaje.</span><span class="sxs-lookup"><span data-stu-id="8a469-140">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|  
|<span data-ttu-id="8a469-141">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="8a469-141">TransportCredentialOnly</span></span>|<span data-ttu-id="8a469-142">Este modo no proporciona integridad del mensaje y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="8a469-142">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="8a469-143">Proporciona la autenticación del cliente basada en http.</span><span class="sxs-lookup"><span data-stu-id="8a469-143">It provides http-based client authentication.</span></span> <span data-ttu-id="8a469-144">Este modo se debe utilizar con precaución.</span><span class="sxs-lookup"><span data-stu-id="8a469-144">This mode should be used with caution.</span></span> <span data-ttu-id="8a469-145">Se debe usar en entornos en los que la seguridad de transporte se proporciona por otros medios (como IPSec) y la infraestructura de WCF proporciona únicamente la autenticación del cliente.</span><span class="sxs-lookup"><span data-stu-id="8a469-145">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8a469-146">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8a469-146">Child Elements</span></span>  
  
|<span data-ttu-id="8a469-147">Elemento</span><span class="sxs-lookup"><span data-stu-id="8a469-147">Element</span></span>|<span data-ttu-id="8a469-148">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a469-148">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8a469-149">> de transporte de \<</span><span class="sxs-lookup"><span data-stu-id="8a469-149">\<transport></span></span>](transport-of-basichttpbinding.md)|<span data-ttu-id="8a469-150">Define los valores de seguridad de transporte para un servicio HTTP básico.</span><span class="sxs-lookup"><span data-stu-id="8a469-150">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="8a469-151">Este elemento corresponde a <xref:System.ServiceModel.HttpTransportSecurity>.</span><span class="sxs-lookup"><span data-stu-id="8a469-151">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|  
|[<span data-ttu-id="8a469-152">\<> de mensaje</span><span class="sxs-lookup"><span data-stu-id="8a469-152">\<message></span></span>](message-of-basichttpbinding.md)|<span data-ttu-id="8a469-153">Define los valores de modo de seguridad para un servicio HTTP básico.</span><span class="sxs-lookup"><span data-stu-id="8a469-153">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="8a469-154">Este elemento corresponde a <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span><span class="sxs-lookup"><span data-stu-id="8a469-154">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8a469-155">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8a469-155">Parent Elements</span></span>  
  
|<span data-ttu-id="8a469-156">Elemento</span><span class="sxs-lookup"><span data-stu-id="8a469-156">Element</span></span>|<span data-ttu-id="8a469-157">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a469-157">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8a469-158">enlace</span><span class="sxs-lookup"><span data-stu-id="8a469-158">binding</span></span>|<span data-ttu-id="8a469-159">Elemento de enlace del [> de\<basicHttpBinding](basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="8a469-159">The binding element of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a469-160">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8a469-160">Remarks</span></span>  
 <span data-ttu-id="8a469-161">De forma predeterminada, no se protege el mensaje SOAP y no se autentica el cliente.</span><span class="sxs-lookup"><span data-stu-id="8a469-161">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="8a469-162">Este elemento le permite establecer la configuración de seguridad adicional para el elemento `basicHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="8a469-162">This element enables you to configure additional security settings for the `basicHttpBinding` element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a469-163">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a469-163">See also</span></span>

- <xref:System.ServiceModel.BasicHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="8a469-164">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="8a469-164">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="8a469-165">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="8a469-165">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="8a469-166">Enlaces</span><span class="sxs-lookup"><span data-stu-id="8a469-166">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="8a469-167">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="8a469-167">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="8a469-168">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="8a469-168">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="8a469-169">\<> de enlace</span><span class="sxs-lookup"><span data-stu-id="8a469-169">\<binding></span></span>](bindings.md)
