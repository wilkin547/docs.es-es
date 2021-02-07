---
description: 'Más información sobre: <security> de <basicHttpBinding>'
title: <security> de <basicHttpBinding>
ms.date: 03/30/2017
ms.assetid: 6432708d-5465-4bd9-bfc2-466742db99cb
ms.openlocfilehash: 92d938d062d56cbb066a1170a9d3b8f3f5ba0186
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683261"
---
# <a name="security-of-basichttpbinding"></a><span data-ttu-id="00311-103">\<security> de \<basicHttpBinding></span><span class="sxs-lookup"><span data-stu-id="00311-103">\<security> of \<basicHttpBinding></span></span>

<span data-ttu-id="00311-104">Define las capacidades de seguridad de [\<basicHttpBinding>](basichttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="00311-104">Defines the security capabilities of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<basicHttpBinding>**](basichttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="00311-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="00311-105">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="00311-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="00311-106">Attributes and Elements</span></span>  

 <span data-ttu-id="00311-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="00311-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="00311-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="00311-108">Attributes</span></span>  
  
|<span data-ttu-id="00311-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="00311-109">Attribute</span></span>|<span data-ttu-id="00311-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="00311-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="00311-111">mode</span><span class="sxs-lookup"><span data-stu-id="00311-111">mode</span></span>|<span data-ttu-id="00311-112">Opcional.</span><span class="sxs-lookup"><span data-stu-id="00311-112">Optional.</span></span> <span data-ttu-id="00311-113">Especifica el tipo de seguridad que se utiliza.</span><span class="sxs-lookup"><span data-stu-id="00311-113">Specifies the type of security that is used.</span></span> <span data-ttu-id="00311-114">De manera predeterminada, es `None`.</span><span class="sxs-lookup"><span data-stu-id="00311-114">The default is `None`.</span></span> <span data-ttu-id="00311-115">Este atributo es del tipo <xref:System.ServiceModel.BasicHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="00311-115">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="00311-116">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="00311-116">mode Attribute</span></span>  
  
|<span data-ttu-id="00311-117">Value</span><span class="sxs-lookup"><span data-stu-id="00311-117">Value</span></span>|<span data-ttu-id="00311-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="00311-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="00311-119">None</span><span class="sxs-lookup"><span data-stu-id="00311-119">None</span></span>|<span data-ttu-id="00311-120">: Los mensajes no están protegidos durante la transferencia.</span><span class="sxs-lookup"><span data-stu-id="00311-120">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="00311-121">Transporte</span><span class="sxs-lookup"><span data-stu-id="00311-121">Transport</span></span>|<span data-ttu-id="00311-122">La seguridad se proporciona utilizando transporte HTTPS.</span><span class="sxs-lookup"><span data-stu-id="00311-122">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="00311-123">Los mensajes SOAP están protegidos mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="00311-123">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="00311-124">El servicio se autentica al cliente utilizando el certificado X.509 del servicio.</span><span class="sxs-lookup"><span data-stu-id="00311-124">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="00311-125">El cliente se autentica utilizando el ClientCredentialType proporcionado.</span><span class="sxs-lookup"><span data-stu-id="00311-125">The client is authenticated using the ClientCredentialType supplied.</span></span> <span data-ttu-id="00311-126">Vea [\<transport>](transport-of-basichttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="00311-126">See the [\<transport>](transport-of-basichttpbinding.md).</span></span>|  
|<span data-ttu-id="00311-127">Message</span><span class="sxs-lookup"><span data-stu-id="00311-127">Message</span></span>|<span data-ttu-id="00311-128">La seguridad se proporciona mediante la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="00311-128">Security is provided using SOAP message security.</span></span> <span data-ttu-id="00311-129">De forma predeterminada, el cuerpo se cifra y firma.</span><span class="sxs-lookup"><span data-stu-id="00311-129">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="00311-130">Para este enlace, el sistema requiere que el certificado de servidor se proporcione al cliente fuera de la banda.</span><span class="sxs-lookup"><span data-stu-id="00311-130">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="00311-131">El único `ClientCredentialType` válido para este enlace es `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="00311-131">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|  
|<span data-ttu-id="00311-132">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="00311-132">TransportWithMessageCredential</span></span>|<span data-ttu-id="00311-133">La seguridad de transporte proporciona integridad, confidencialidad y autenticación del servidor.</span><span class="sxs-lookup"><span data-stu-id="00311-133">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="00311-134">La autenticación del cliente se proporciona por medio de la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="00311-134">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="00311-135">Este modo es pertinente cuando el usuario está autenticando utilizando el nombre de usuario/contraseña y existe una implementación del HTTP existente para proteger la transferencia del mensaje.</span><span class="sxs-lookup"><span data-stu-id="00311-135">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|  
|<span data-ttu-id="00311-136">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="00311-136">TransportCredentialOnly</span></span>|<span data-ttu-id="00311-137">Este modo no proporciona integridad del mensaje y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="00311-137">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="00311-138">Proporciona la autenticación del cliente basada en http.</span><span class="sxs-lookup"><span data-stu-id="00311-138">It provides http-based client authentication.</span></span> <span data-ttu-id="00311-139">Este modo se debe utilizar con precaución.</span><span class="sxs-lookup"><span data-stu-id="00311-139">This mode should be used with caution.</span></span> <span data-ttu-id="00311-140">Se debe usar en entornos en los que la seguridad de transporte se proporciona por otros medios (como IPSec) y la infraestructura de WCF proporciona únicamente la autenticación del cliente.</span><span class="sxs-lookup"><span data-stu-id="00311-140">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="00311-141">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="00311-141">Child Elements</span></span>  
  
|<span data-ttu-id="00311-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="00311-142">Element</span></span>|<span data-ttu-id="00311-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="00311-143">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-basichttpbinding.md)|<span data-ttu-id="00311-144">Define los valores de seguridad de transporte para un servicio HTTP básico.</span><span class="sxs-lookup"><span data-stu-id="00311-144">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="00311-145">Este elemento corresponde a <xref:System.ServiceModel.HttpTransportSecurity>.</span><span class="sxs-lookup"><span data-stu-id="00311-145">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|  
|[\<message>](message-of-basichttpbinding.md)|<span data-ttu-id="00311-146">Define los valores de modo de seguridad para un servicio HTTP básico.</span><span class="sxs-lookup"><span data-stu-id="00311-146">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="00311-147">Este elemento corresponde a <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span><span class="sxs-lookup"><span data-stu-id="00311-147">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="00311-148">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="00311-148">Parent Elements</span></span>  
  
|<span data-ttu-id="00311-149">Elemento</span><span class="sxs-lookup"><span data-stu-id="00311-149">Element</span></span>|<span data-ttu-id="00311-150">Descripción</span><span class="sxs-lookup"><span data-stu-id="00311-150">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="00311-151">binding</span><span class="sxs-lookup"><span data-stu-id="00311-151">binding</span></span>|<span data-ttu-id="00311-152">Elemento de enlace de [\<basicHttpBinding>](basichttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="00311-152">The binding element of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00311-153">Observaciones</span><span class="sxs-lookup"><span data-stu-id="00311-153">Remarks</span></span>  

 <span data-ttu-id="00311-154">De forma predeterminada, no se protege el mensaje SOAP y no se autentica el cliente.</span><span class="sxs-lookup"><span data-stu-id="00311-154">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="00311-155">Este elemento le permite establecer la configuración de seguridad adicional para el elemento `basicHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="00311-155">This element enables you to configure additional security settings for the `basicHttpBinding` element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00311-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="00311-156">See also</span></span>

- <xref:System.ServiceModel.BasicHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="00311-157">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="00311-157">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="00311-158">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="00311-158">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="00311-159">Enlaces</span><span class="sxs-lookup"><span data-stu-id="00311-159">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="00311-160">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="00311-160">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="00311-161">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="00311-161">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
