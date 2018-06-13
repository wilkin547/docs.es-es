---
title: Elemento &lt;security&gt; de &lt;basicHttpBinding&gt;
ms.date: 03/30/2017
ms.assetid: 6432708d-5465-4bd9-bfc2-466742db99cb
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: e39d32a9cc689905bed42f56e4f998bbd8c6e038
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33355033"
---
# <a name="ltsecuritygt-of-ltbasichttpbindinggt"></a><span data-ttu-id="62146-102">Elemento &lt;security&gt; de &lt;basicHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="62146-102">&lt;security&gt; of &lt;basicHttpBinding&gt;</span></span>
<span data-ttu-id="62146-103">Define las capacidades de seguridad de la [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="62146-103">Defines the security capabilities of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>  
  
 <span data-ttu-id="62146-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="62146-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="62146-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="62146-105">\<bindings></span></span>  
<span data-ttu-id="62146-106">\<basicHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="62146-106">\<basicHttpBinding></span></span>  
<span data-ttu-id="62146-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="62146-107">\<binding></span></span>  
<span data-ttu-id="62146-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="62146-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62146-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="62146-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">  
   <transport  
      clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
      proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
      realm="string" />  
   <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="62146-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="62146-110">Attributes and Elements</span></span>  
 <span data-ttu-id="62146-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="62146-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="62146-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="62146-112">Attributes</span></span>  
  
|<span data-ttu-id="62146-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="62146-113">Attribute</span></span>|<span data-ttu-id="62146-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="62146-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="62146-115">modo</span><span class="sxs-lookup"><span data-stu-id="62146-115">mode</span></span>|<span data-ttu-id="62146-116">Opcional.</span><span class="sxs-lookup"><span data-stu-id="62146-116">Optional.</span></span> <span data-ttu-id="62146-117">Especifica el tipo de seguridad que se utiliza.</span><span class="sxs-lookup"><span data-stu-id="62146-117">Specifies the type of security that is used.</span></span> <span data-ttu-id="62146-118">De manera predeterminada, es `None`.</span><span class="sxs-lookup"><span data-stu-id="62146-118">The default is `None`.</span></span> <span data-ttu-id="62146-119">Este atributo es del tipo <xref:System.ServiceModel.BasicHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="62146-119">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="62146-120">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="62146-120">mode Attribute</span></span>  
  
|<span data-ttu-id="62146-121">Valor</span><span class="sxs-lookup"><span data-stu-id="62146-121">Value</span></span>|<span data-ttu-id="62146-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="62146-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="62146-123">Ninguna</span><span class="sxs-lookup"><span data-stu-id="62146-123">None</span></span>|<span data-ttu-id="62146-124">-Los mensajes no están protegidos durante la transferencia.</span><span class="sxs-lookup"><span data-stu-id="62146-124">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="62146-125">Transporte</span><span class="sxs-lookup"><span data-stu-id="62146-125">Transport</span></span>|<span data-ttu-id="62146-126">La seguridad se proporciona utilizando transporte HTTPS.</span><span class="sxs-lookup"><span data-stu-id="62146-126">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="62146-127">Los mensajes SOAP se protegen utilizando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="62146-127">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="62146-128">El servicio se autentica al cliente utilizando el certificado X.509 del servicio.</span><span class="sxs-lookup"><span data-stu-id="62146-128">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="62146-129">El cliente se autentica utilizando el ClientCredentialType proporcionado.</span><span class="sxs-lookup"><span data-stu-id="62146-129">The client is authenticated using the ClientCredentialType supplied.</span></span> <span data-ttu-id="62146-130">Consulte la [ \<transporte >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="62146-130">See the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md).</span></span>|  
|<span data-ttu-id="62146-131">Mensaje</span><span class="sxs-lookup"><span data-stu-id="62146-131">Message</span></span>|<span data-ttu-id="62146-132">La seguridad se proporciona mediante la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="62146-132">Security is provided using SOAP message security.</span></span> <span data-ttu-id="62146-133">De forma predeterminada, el cuerpo se cifra y firma.</span><span class="sxs-lookup"><span data-stu-id="62146-133">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="62146-134">Para este enlace, el sistema requiere que el certificado de servidor se proporcione al cliente fuera de la banda.</span><span class="sxs-lookup"><span data-stu-id="62146-134">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="62146-135">El único `ClientCredentialType` válido para este enlace es `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="62146-135">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|  
|<span data-ttu-id="62146-136">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="62146-136">TransportWithMessageCredential</span></span>|<span data-ttu-id="62146-137">La seguridad de transporte proporciona integridad, confidencialidad y autenticación del servidor.</span><span class="sxs-lookup"><span data-stu-id="62146-137">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="62146-138">La autenticación del cliente se proporciona por medio de la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="62146-138">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="62146-139">Este modo es pertinente cuando el usuario está autenticando utilizando el nombre de usuario/contraseña y existe una implementación del HTTP existente para proteger la transferencia del mensaje.</span><span class="sxs-lookup"><span data-stu-id="62146-139">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|  
|<span data-ttu-id="62146-140">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="62146-140">TransportCredentialOnly</span></span>|<span data-ttu-id="62146-141">Este modo no proporciona integridad del mensaje y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="62146-141">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="62146-142">Proporciona la autenticación del cliente basada en http.</span><span class="sxs-lookup"><span data-stu-id="62146-142">It provides http-based client authentication.</span></span> <span data-ttu-id="62146-143">Este modo se debe utilizar con precaución.</span><span class="sxs-lookup"><span data-stu-id="62146-143">This mode should be used with caution.</span></span> <span data-ttu-id="62146-144">Se debe usar en entornos donde la seguridad de transporte es proporcionada por otros medios (como IPSec) y la infraestructura de WCF proporciona sólo la autenticación del cliente.</span><span class="sxs-lookup"><span data-stu-id="62146-144">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="62146-145">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="62146-145">Child Elements</span></span>  
  
|<span data-ttu-id="62146-146">Elemento</span><span class="sxs-lookup"><span data-stu-id="62146-146">Element</span></span>|<span data-ttu-id="62146-147">Descripción</span><span class="sxs-lookup"><span data-stu-id="62146-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="62146-148">\<transporte ></span><span class="sxs-lookup"><span data-stu-id="62146-148">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md)|<span data-ttu-id="62146-149">Define los valores de seguridad de transporte para un servicio HTTP básico.</span><span class="sxs-lookup"><span data-stu-id="62146-149">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="62146-150">Este elemento corresponde a <xref:System.ServiceModel.HttpTransportSecurity>.</span><span class="sxs-lookup"><span data-stu-id="62146-150">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|  
|[<span data-ttu-id="62146-151">\<mensaje ></span><span class="sxs-lookup"><span data-stu-id="62146-151">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-basichttpbinding.md)|<span data-ttu-id="62146-152">Define los valores de modo de seguridad para un servicio HTTP básico.</span><span class="sxs-lookup"><span data-stu-id="62146-152">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="62146-153">Este elemento corresponde a <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span><span class="sxs-lookup"><span data-stu-id="62146-153">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="62146-154">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="62146-154">Parent Elements</span></span>  
  
|<span data-ttu-id="62146-155">Elemento</span><span class="sxs-lookup"><span data-stu-id="62146-155">Element</span></span>|<span data-ttu-id="62146-156">Descripción</span><span class="sxs-lookup"><span data-stu-id="62146-156">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="62146-157">enlace</span><span class="sxs-lookup"><span data-stu-id="62146-157">binding</span></span>|<span data-ttu-id="62146-158">El elemento de enlace de la [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="62146-158">The binding element of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62146-159">Comentarios</span><span class="sxs-lookup"><span data-stu-id="62146-159">Remarks</span></span>  
 <span data-ttu-id="62146-160">De forma predeterminada, no se protege el mensaje SOAP y no se autentica el cliente.</span><span class="sxs-lookup"><span data-stu-id="62146-160">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="62146-161">Este elemento le permite establecer la configuración de seguridad adicional para el elemento `basicHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="62146-161">This element enables you to configure additional security settings for the `basicHttpBinding` element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62146-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="62146-162">See Also</span></span>  
 <xref:System.ServiceModel.BasicHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>  
 <xref:System.ServiceModel.BasicHttpSecurity>  
 [<span data-ttu-id="62146-163">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="62146-163">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="62146-164">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="62146-164">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="62146-165">Enlaces</span><span class="sxs-lookup"><span data-stu-id="62146-165">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="62146-166">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="62146-166">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="62146-167">Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="62146-167">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="62146-168">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="62146-168">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
