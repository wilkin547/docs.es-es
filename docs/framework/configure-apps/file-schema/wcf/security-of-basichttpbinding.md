---
title: <security> de <basicHttpBinding>
ms.date: 03/30/2017
ms.assetid: 6432708d-5465-4bd9-bfc2-466742db99cb
ms.openlocfilehash: 00a933892376c2dc9771752beaf76d4994554968
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399891"
---
# <a name="security-of-basichttpbinding"></a><span data-ttu-id="a2b8a-102">\<> de seguridad \<de basicHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="a2b8a-102">\<security> of \<basicHttpBinding></span></span>
<span data-ttu-id="a2b8a-103">Define las capacidades de seguridad del [ \<> basicHttpBinding](basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="a2b8a-103">Defines the security capabilities of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>  
  
<span data-ttu-id="a2b8a-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a2b8a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a2b8a-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a2b8a-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a2b8a-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enlaces**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="a2b8a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="a2b8a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> basicHttpBinding**](basichttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="a2b8a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<basicHttpBinding>**](basichttpbinding.md)</span></span>\
<span data-ttu-id="a2b8a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de enlace**</span><span class="sxs-lookup"><span data-stu-id="a2b8a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="a2b8a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de seguridad**</span><span class="sxs-lookup"><span data-stu-id="a2b8a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2b8a-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a2b8a-110">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a2b8a-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a2b8a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a2b8a-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a2b8a-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a2b8a-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="a2b8a-113">Attributes</span></span>  
  
|<span data-ttu-id="a2b8a-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="a2b8a-114">Attribute</span></span>|<span data-ttu-id="a2b8a-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a2b8a-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a2b8a-116">modo</span><span class="sxs-lookup"><span data-stu-id="a2b8a-116">mode</span></span>|<span data-ttu-id="a2b8a-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="a2b8a-117">Optional.</span></span> <span data-ttu-id="a2b8a-118">Especifica el tipo de seguridad que se utiliza.</span><span class="sxs-lookup"><span data-stu-id="a2b8a-118">Specifies the type of security that is used.</span></span> <span data-ttu-id="a2b8a-119">El valor predeterminado es `None`.</span><span class="sxs-lookup"><span data-stu-id="a2b8a-119">The default is `None`.</span></span> <span data-ttu-id="a2b8a-120">Este atributo es del tipo <xref:System.ServiceModel.BasicHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="a2b8a-120">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="a2b8a-121">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="a2b8a-121">mode Attribute</span></span>  
  
|<span data-ttu-id="a2b8a-122">Valor</span><span class="sxs-lookup"><span data-stu-id="a2b8a-122">Value</span></span>|<span data-ttu-id="a2b8a-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a2b8a-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a2b8a-124">None</span><span class="sxs-lookup"><span data-stu-id="a2b8a-124">None</span></span>|<span data-ttu-id="a2b8a-125">: Los mensajes no están protegidos durante la transferencia.</span><span class="sxs-lookup"><span data-stu-id="a2b8a-125">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="a2b8a-126">Transporte</span><span class="sxs-lookup"><span data-stu-id="a2b8a-126">Transport</span></span>|<span data-ttu-id="a2b8a-127">La seguridad se proporciona utilizando transporte HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a2b8a-127">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="a2b8a-128">Los mensajes SOAP se protegen utilizando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a2b8a-128">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="a2b8a-129">El servicio se autentica al cliente utilizando el certificado X.509 del servicio.</span><span class="sxs-lookup"><span data-stu-id="a2b8a-129">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="a2b8a-130">El cliente se autentica utilizando el ClientCredentialType proporcionado.</span><span class="sxs-lookup"><span data-stu-id="a2b8a-130">The client is authenticated using the ClientCredentialType supplied.</span></span> <span data-ttu-id="a2b8a-131">Vea el [ \<> de transporte](transport-of-basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="a2b8a-131">See the [\<transport>](transport-of-basichttpbinding.md).</span></span>|  
|<span data-ttu-id="a2b8a-132">Message</span><span class="sxs-lookup"><span data-stu-id="a2b8a-132">Message</span></span>|<span data-ttu-id="a2b8a-133">La seguridad se proporciona mediante la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="a2b8a-133">Security is provided using SOAP message security.</span></span> <span data-ttu-id="a2b8a-134">De forma predeterminada, el cuerpo se cifra y firma.</span><span class="sxs-lookup"><span data-stu-id="a2b8a-134">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="a2b8a-135">Para este enlace, el sistema requiere que el certificado de servidor se proporcione al cliente fuera de la banda.</span><span class="sxs-lookup"><span data-stu-id="a2b8a-135">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="a2b8a-136">El único `ClientCredentialType` válido para este enlace es `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="a2b8a-136">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|  
|<span data-ttu-id="a2b8a-137">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="a2b8a-137">TransportWithMessageCredential</span></span>|<span data-ttu-id="a2b8a-138">La seguridad de transporte proporciona integridad, confidencialidad y autenticación del servidor.</span><span class="sxs-lookup"><span data-stu-id="a2b8a-138">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="a2b8a-139">La autenticación del cliente se proporciona por medio de la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="a2b8a-139">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="a2b8a-140">Este modo es pertinente cuando el usuario está autenticando utilizando el nombre de usuario/contraseña y existe una implementación del HTTP existente para proteger la transferencia del mensaje.</span><span class="sxs-lookup"><span data-stu-id="a2b8a-140">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|  
|<span data-ttu-id="a2b8a-141">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="a2b8a-141">TransportCredentialOnly</span></span>|<span data-ttu-id="a2b8a-142">Este modo no proporciona integridad del mensaje y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="a2b8a-142">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="a2b8a-143">Proporciona la autenticación del cliente basada en http.</span><span class="sxs-lookup"><span data-stu-id="a2b8a-143">It provides http-based client authentication.</span></span> <span data-ttu-id="a2b8a-144">Este modo se debe utilizar con precaución.</span><span class="sxs-lookup"><span data-stu-id="a2b8a-144">This mode should be used with caution.</span></span> <span data-ttu-id="a2b8a-145">Se debe usar en entornos en los que la seguridad de transporte se proporciona por otros medios (como IPSec) y la infraestructura de WCF proporciona únicamente la autenticación del cliente.</span><span class="sxs-lookup"><span data-stu-id="a2b8a-145">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a2b8a-146">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a2b8a-146">Child Elements</span></span>  
  
|<span data-ttu-id="a2b8a-147">Elemento</span><span class="sxs-lookup"><span data-stu-id="a2b8a-147">Element</span></span>|<span data-ttu-id="a2b8a-148">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a2b8a-148">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a2b8a-149">\<> de transporte</span><span class="sxs-lookup"><span data-stu-id="a2b8a-149">\<transport></span></span>](transport-of-basichttpbinding.md)|<span data-ttu-id="a2b8a-150">Define los valores de seguridad de transporte para un servicio HTTP básico.</span><span class="sxs-lookup"><span data-stu-id="a2b8a-150">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="a2b8a-151">Este elemento corresponde a <xref:System.ServiceModel.HttpTransportSecurity>.</span><span class="sxs-lookup"><span data-stu-id="a2b8a-151">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|  
|[<span data-ttu-id="a2b8a-152">\<message></span><span class="sxs-lookup"><span data-stu-id="a2b8a-152">\<message></span></span>](message-of-basichttpbinding.md)|<span data-ttu-id="a2b8a-153">Define los valores de modo de seguridad para un servicio HTTP básico.</span><span class="sxs-lookup"><span data-stu-id="a2b8a-153">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="a2b8a-154">Este elemento corresponde a <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span><span class="sxs-lookup"><span data-stu-id="a2b8a-154">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a2b8a-155">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a2b8a-155">Parent Elements</span></span>  
  
|<span data-ttu-id="a2b8a-156">Elemento</span><span class="sxs-lookup"><span data-stu-id="a2b8a-156">Element</span></span>|<span data-ttu-id="a2b8a-157">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a2b8a-157">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a2b8a-158">enlace</span><span class="sxs-lookup"><span data-stu-id="a2b8a-158">binding</span></span>|<span data-ttu-id="a2b8a-159">Elemento de enlace del [ \<> basicHttpBinding](basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="a2b8a-159">The binding element of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2b8a-160">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a2b8a-160">Remarks</span></span>  
 <span data-ttu-id="a2b8a-161">De forma predeterminada, no se protege el mensaje SOAP y no se autentica el cliente.</span><span class="sxs-lookup"><span data-stu-id="a2b8a-161">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="a2b8a-162">Este elemento le permite establecer la configuración de seguridad adicional para el elemento `basicHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="a2b8a-162">This element enables you to configure additional security settings for the `basicHttpBinding` element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2b8a-163">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2b8a-163">See also</span></span>

- <xref:System.ServiceModel.BasicHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="a2b8a-164">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="a2b8a-164">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="a2b8a-165">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="a2b8a-165">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="a2b8a-166">Enlaces</span><span class="sxs-lookup"><span data-stu-id="a2b8a-166">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a2b8a-167">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="a2b8a-167">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="a2b8a-168">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="a2b8a-168">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="a2b8a-169">\<binding></span><span class="sxs-lookup"><span data-stu-id="a2b8a-169">\<binding></span></span>](../../../misc/binding.md)
