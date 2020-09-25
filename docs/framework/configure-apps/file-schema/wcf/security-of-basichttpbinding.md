---
title: <security> de <basicHttpBinding>
ms.date: 03/30/2017
ms.assetid: 6432708d-5465-4bd9-bfc2-466742db99cb
ms.openlocfilehash: 6144e5448526d7f2a7c89693f70f71a7f26c4a22
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183668"
---
# <a name="security-of-basichttpbinding"></a><span data-ttu-id="b70fa-102">\<security> de \<basicHttpBinding></span><span class="sxs-lookup"><span data-stu-id="b70fa-102">\<security> of \<basicHttpBinding></span></span>

<span data-ttu-id="b70fa-103">Define las capacidades de seguridad de [\<basicHttpBinding>](basichttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="b70fa-103">Defines the security capabilities of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<basicHttpBinding>**](basichttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="b70fa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b70fa-104">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b70fa-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b70fa-105">Attributes and Elements</span></span>  

 <span data-ttu-id="b70fa-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b70fa-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b70fa-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="b70fa-107">Attributes</span></span>  
  
|<span data-ttu-id="b70fa-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="b70fa-108">Attribute</span></span>|<span data-ttu-id="b70fa-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="b70fa-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b70fa-110">mode</span><span class="sxs-lookup"><span data-stu-id="b70fa-110">mode</span></span>|<span data-ttu-id="b70fa-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="b70fa-111">Optional.</span></span> <span data-ttu-id="b70fa-112">Especifica el tipo de seguridad que se utiliza.</span><span class="sxs-lookup"><span data-stu-id="b70fa-112">Specifies the type of security that is used.</span></span> <span data-ttu-id="b70fa-113">El valor predeterminado es `None`.</span><span class="sxs-lookup"><span data-stu-id="b70fa-113">The default is `None`.</span></span> <span data-ttu-id="b70fa-114">Este atributo es del tipo <xref:System.ServiceModel.BasicHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="b70fa-114">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="b70fa-115">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="b70fa-115">mode Attribute</span></span>  
  
|<span data-ttu-id="b70fa-116">Value</span><span class="sxs-lookup"><span data-stu-id="b70fa-116">Value</span></span>|<span data-ttu-id="b70fa-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="b70fa-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b70fa-118">None</span><span class="sxs-lookup"><span data-stu-id="b70fa-118">None</span></span>|<span data-ttu-id="b70fa-119">: Los mensajes no están protegidos durante la transferencia.</span><span class="sxs-lookup"><span data-stu-id="b70fa-119">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="b70fa-120">Transporte</span><span class="sxs-lookup"><span data-stu-id="b70fa-120">Transport</span></span>|<span data-ttu-id="b70fa-121">La seguridad se proporciona utilizando transporte HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b70fa-121">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="b70fa-122">Los mensajes SOAP están protegidos mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b70fa-122">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="b70fa-123">El servicio se autentica al cliente utilizando el certificado X.509 del servicio.</span><span class="sxs-lookup"><span data-stu-id="b70fa-123">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="b70fa-124">El cliente se autentica utilizando el ClientCredentialType proporcionado.</span><span class="sxs-lookup"><span data-stu-id="b70fa-124">The client is authenticated using the ClientCredentialType supplied.</span></span> <span data-ttu-id="b70fa-125">Vea [\<transport>](transport-of-basichttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="b70fa-125">See the [\<transport>](transport-of-basichttpbinding.md).</span></span>|  
|<span data-ttu-id="b70fa-126">Mensaje</span><span class="sxs-lookup"><span data-stu-id="b70fa-126">Message</span></span>|<span data-ttu-id="b70fa-127">La seguridad se proporciona mediante la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="b70fa-127">Security is provided using SOAP message security.</span></span> <span data-ttu-id="b70fa-128">De forma predeterminada, el cuerpo se cifra y firma.</span><span class="sxs-lookup"><span data-stu-id="b70fa-128">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="b70fa-129">Para este enlace, el sistema requiere que el certificado de servidor se proporcione al cliente fuera de la banda.</span><span class="sxs-lookup"><span data-stu-id="b70fa-129">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="b70fa-130">El único `ClientCredentialType` válido para este enlace es `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="b70fa-130">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|  
|<span data-ttu-id="b70fa-131">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="b70fa-131">TransportWithMessageCredential</span></span>|<span data-ttu-id="b70fa-132">La seguridad de transporte proporciona integridad, confidencialidad y autenticación del servidor.</span><span class="sxs-lookup"><span data-stu-id="b70fa-132">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="b70fa-133">La autenticación del cliente se proporciona por medio de la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="b70fa-133">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="b70fa-134">Este modo es pertinente cuando el usuario está autenticando utilizando el nombre de usuario/contraseña y existe una implementación del HTTP existente para proteger la transferencia del mensaje.</span><span class="sxs-lookup"><span data-stu-id="b70fa-134">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|  
|<span data-ttu-id="b70fa-135">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="b70fa-135">TransportCredentialOnly</span></span>|<span data-ttu-id="b70fa-136">Este modo no proporciona integridad del mensaje y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="b70fa-136">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="b70fa-137">Proporciona la autenticación del cliente basada en http.</span><span class="sxs-lookup"><span data-stu-id="b70fa-137">It provides http-based client authentication.</span></span> <span data-ttu-id="b70fa-138">Este modo se debe utilizar con precaución.</span><span class="sxs-lookup"><span data-stu-id="b70fa-138">This mode should be used with caution.</span></span> <span data-ttu-id="b70fa-139">Se debe usar en entornos en los que la seguridad de transporte se proporciona por otros medios (como IPSec) y la infraestructura de WCF proporciona únicamente la autenticación del cliente.</span><span class="sxs-lookup"><span data-stu-id="b70fa-139">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b70fa-140">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b70fa-140">Child Elements</span></span>  
  
|<span data-ttu-id="b70fa-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="b70fa-141">Element</span></span>|<span data-ttu-id="b70fa-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="b70fa-142">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-basichttpbinding.md)|<span data-ttu-id="b70fa-143">Define los valores de seguridad de transporte para un servicio HTTP básico.</span><span class="sxs-lookup"><span data-stu-id="b70fa-143">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="b70fa-144">Este elemento corresponde a <xref:System.ServiceModel.HttpTransportSecurity>.</span><span class="sxs-lookup"><span data-stu-id="b70fa-144">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|  
|[\<message>](message-of-basichttpbinding.md)|<span data-ttu-id="b70fa-145">Define los valores de modo de seguridad para un servicio HTTP básico.</span><span class="sxs-lookup"><span data-stu-id="b70fa-145">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="b70fa-146">Este elemento corresponde a <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span><span class="sxs-lookup"><span data-stu-id="b70fa-146">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b70fa-147">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b70fa-147">Parent Elements</span></span>  
  
|<span data-ttu-id="b70fa-148">Elemento</span><span class="sxs-lookup"><span data-stu-id="b70fa-148">Element</span></span>|<span data-ttu-id="b70fa-149">Descripción</span><span class="sxs-lookup"><span data-stu-id="b70fa-149">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b70fa-150">binding</span><span class="sxs-lookup"><span data-stu-id="b70fa-150">binding</span></span>|<span data-ttu-id="b70fa-151">Elemento de enlace de [\<basicHttpBinding>](basichttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="b70fa-151">The binding element of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b70fa-152">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b70fa-152">Remarks</span></span>  

 <span data-ttu-id="b70fa-153">De forma predeterminada, no se protege el mensaje SOAP y no se autentica el cliente.</span><span class="sxs-lookup"><span data-stu-id="b70fa-153">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="b70fa-154">Este elemento le permite establecer la configuración de seguridad adicional para el elemento `basicHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="b70fa-154">This element enables you to configure additional security settings for the `basicHttpBinding` element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b70fa-155">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b70fa-155">See also</span></span>

- <xref:System.ServiceModel.BasicHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="b70fa-156">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="b70fa-156">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="b70fa-157">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="b70fa-157">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="b70fa-158">Enlaces</span><span class="sxs-lookup"><span data-stu-id="b70fa-158">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b70fa-159">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="b70fa-159">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="b70fa-160">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="b70fa-160">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
