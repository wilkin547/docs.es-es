---
title: '&lt;security&gt; de &lt;netHttpBinding'
ms.date: 03/30/2017
ms.assetid: dc41f6f7-cabc-4a64-9fa0-ceabf861b348
ms.openlocfilehash: 6357593be17c2d008204598d51610fa3dbf77c27
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2018
ms.locfileid: "45664662"
---
# <a name="ltsecuritygt-of-ltnethttpbinding"></a><span data-ttu-id="3c33a-102">&lt;security&gt; de &lt;netHttpBinding</span><span class="sxs-lookup"><span data-stu-id="3c33a-102">&lt;security&gt; of &lt;netHttpBinding</span></span>
<span data-ttu-id="3c33a-103">Define las funciones de seguridad de la [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="3c33a-103">Defines the security capabilities of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>  
  
 <span data-ttu-id="3c33a-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3c33a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="3c33a-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="3c33a-105">\<bindings></span></span>  
<span data-ttu-id="3c33a-106">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="3c33a-106">\<netHttpBinding></span></span>  
<span data-ttu-id="3c33a-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="3c33a-107">\<binding></span></span>  
<span data-ttu-id="3c33a-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="3c33a-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c33a-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3c33a-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3c33a-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3c33a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3c33a-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3c33a-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3c33a-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="3c33a-112">Attributes</span></span>  
  
|<span data-ttu-id="3c33a-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="3c33a-113">Attribute</span></span>|<span data-ttu-id="3c33a-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="3c33a-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3c33a-115">modo</span><span class="sxs-lookup"><span data-stu-id="3c33a-115">mode</span></span>|<span data-ttu-id="3c33a-116">Opcional.</span><span class="sxs-lookup"><span data-stu-id="3c33a-116">Optional.</span></span> <span data-ttu-id="3c33a-117">Especifica el tipo de seguridad que se utiliza.</span><span class="sxs-lookup"><span data-stu-id="3c33a-117">Specifies the type of security that is used.</span></span> <span data-ttu-id="3c33a-118">De manera predeterminada, es `None`.</span><span class="sxs-lookup"><span data-stu-id="3c33a-118">The default is `None`.</span></span> <span data-ttu-id="3c33a-119">Este atributo es del tipo <!--zz <xref:System.ServiceModel.NetHttpSecurityMode> --> `System.ServiceModel.NetHttpSecurityMode`.</span><span class="sxs-lookup"><span data-stu-id="3c33a-119">This attribute is of type <!--zz <xref:System.ServiceModel.NetHttpSecurityMode> -->`System.ServiceModel.NetHttpSecurityMode`.</span></span>|
  
## <a name="mode-attribute"></a><span data-ttu-id="3c33a-120">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="3c33a-120">mode Attribute</span></span>  
  
|<span data-ttu-id="3c33a-121">Valor</span><span class="sxs-lookup"><span data-stu-id="3c33a-121">Value</span></span>|<span data-ttu-id="3c33a-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="3c33a-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3c33a-123">Ninguna</span><span class="sxs-lookup"><span data-stu-id="3c33a-123">None</span></span>|<span data-ttu-id="3c33a-124">-Los mensajes no están protegidos durante la transferencia.</span><span class="sxs-lookup"><span data-stu-id="3c33a-124">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="3c33a-125">Transporte</span><span class="sxs-lookup"><span data-stu-id="3c33a-125">Transport</span></span>|<span data-ttu-id="3c33a-126">La seguridad se proporciona utilizando transporte HTTPS.</span><span class="sxs-lookup"><span data-stu-id="3c33a-126">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="3c33a-127">Los mensajes SOAP se protegen utilizando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="3c33a-127">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="3c33a-128">El servicio se autentica al cliente utilizando el certificado X.509 del servicio.</span><span class="sxs-lookup"><span data-stu-id="3c33a-128">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="3c33a-129">El cliente se autentica utilizando el ClientCredentialType proporcionado.</span><span class="sxs-lookup"><span data-stu-id="3c33a-129">The client is authenticated using the ClientCredentialType supplied.</span></span>|  
|<span data-ttu-id="3c33a-130">Mensaje</span><span class="sxs-lookup"><span data-stu-id="3c33a-130">Message</span></span>|<span data-ttu-id="3c33a-131">La seguridad se proporciona mediante la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="3c33a-131">Security is provided using SOAP message security.</span></span> <span data-ttu-id="3c33a-132">De forma predeterminada, el cuerpo se cifra y firma.</span><span class="sxs-lookup"><span data-stu-id="3c33a-132">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="3c33a-133">Para este enlace, el sistema requiere que el certificado de servidor se proporcione al cliente fuera de la banda.</span><span class="sxs-lookup"><span data-stu-id="3c33a-133">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="3c33a-134">El único `ClientCredentialType` válido para este enlace es `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="3c33a-134">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|  
|<span data-ttu-id="3c33a-135">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="3c33a-135">TransportWithMessageCredential</span></span>|<span data-ttu-id="3c33a-136">La seguridad de transporte proporciona integridad, confidencialidad y autenticación del servidor.</span><span class="sxs-lookup"><span data-stu-id="3c33a-136">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="3c33a-137">La autenticación del cliente se proporciona por medio de la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="3c33a-137">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="3c33a-138">Este modo es pertinente cuando el usuario está autenticando utilizando el nombre de usuario/contraseña y existe una implementación del HTTP existente para proteger la transferencia del mensaje.</span><span class="sxs-lookup"><span data-stu-id="3c33a-138">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|  
|<span data-ttu-id="3c33a-139">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="3c33a-139">TransportCredentialOnly</span></span>|<span data-ttu-id="3c33a-140">Este modo no proporciona integridad del mensaje y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="3c33a-140">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="3c33a-141">Proporciona la autenticación del cliente basada en http.</span><span class="sxs-lookup"><span data-stu-id="3c33a-141">It provides http-based client authentication.</span></span> <span data-ttu-id="3c33a-142">Este modo se debe utilizar con precaución.</span><span class="sxs-lookup"><span data-stu-id="3c33a-142">This mode should be used with caution.</span></span> <span data-ttu-id="3c33a-143">Se debe usar en entornos donde la seguridad de transporte se proporciona por otros medios (por ejemplo, IPSec) y la infraestructura de WCF proporciona sólo la autenticación de cliente.</span><span class="sxs-lookup"><span data-stu-id="3c33a-143">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3c33a-144">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3c33a-144">Child Elements</span></span>  
  
|<span data-ttu-id="3c33a-145">Elemento</span><span class="sxs-lookup"><span data-stu-id="3c33a-145">Element</span></span>|<span data-ttu-id="3c33a-146">Descripción</span><span class="sxs-lookup"><span data-stu-id="3c33a-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3c33a-147">\<transporte ></span><span class="sxs-lookup"><span data-stu-id="3c33a-147">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-nethttpbinding.md)|<span data-ttu-id="3c33a-148">Define los valores de seguridad de transporte para un servicio HTTP básico.</span><span class="sxs-lookup"><span data-stu-id="3c33a-148">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="3c33a-149">Este elemento corresponde a <xref:System.ServiceModel.HttpTransportSecurity>.</span><span class="sxs-lookup"><span data-stu-id="3c33a-149">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|  
|[<span data-ttu-id="3c33a-150">\<mensaje ></span><span class="sxs-lookup"><span data-stu-id="3c33a-150">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-nethttpbinding.md)|<span data-ttu-id="3c33a-151">Define los valores de modo de seguridad para un servicio HTTP básico.</span><span class="sxs-lookup"><span data-stu-id="3c33a-151">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="3c33a-152">Este elemento corresponde a <!--zz <xref:System.ServiceModel.NetHttpMessageSecurity> --> `System.ServiceModel.NetHttpMessageSecurity`.</span><span class="sxs-lookup"><span data-stu-id="3c33a-152">This element corresponds to <!--zz <xref:System.ServiceModel.NetHttpMessageSecurity> --> `System.ServiceModel.NetHttpMessageSecurity`.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3c33a-153">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3c33a-153">Parent Elements</span></span>  
  
|<span data-ttu-id="3c33a-154">Elemento</span><span class="sxs-lookup"><span data-stu-id="3c33a-154">Element</span></span>|<span data-ttu-id="3c33a-155">Descripción</span><span class="sxs-lookup"><span data-stu-id="3c33a-155">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3c33a-156">enlace</span><span class="sxs-lookup"><span data-stu-id="3c33a-156">binding</span></span>|<span data-ttu-id="3c33a-157">El elemento de enlace de la [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="3c33a-157">The binding element of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c33a-158">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3c33a-158">Remarks</span></span>  
 <span data-ttu-id="3c33a-159">De forma predeterminada, no se protege el mensaje SOAP y no se autentica el cliente.</span><span class="sxs-lookup"><span data-stu-id="3c33a-159">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="3c33a-160">Este elemento le permite establecer la configuración de seguridad adicional para el elemento `netHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="3c33a-160">This element enables you to configure additional security settings for the `netHttpBinding` element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c33a-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c33a-161">See Also</span></span>  
 <xref:System.ServiceModel.NetHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetHttpBindingElement.Security%2A>    
 [<span data-ttu-id="3c33a-162">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="3c33a-162">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="3c33a-163">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="3c33a-163">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="3c33a-164">Enlaces</span><span class="sxs-lookup"><span data-stu-id="3c33a-164">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="3c33a-165">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="3c33a-165">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="3c33a-166">Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="3c33a-166">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="3c33a-167">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="3c33a-167">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
