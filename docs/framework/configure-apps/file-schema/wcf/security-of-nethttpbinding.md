---
title: <security> de <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: dc41f6f7-cabc-4a64-9fa0-ceabf861b348
ms.openlocfilehash: 890cee3271c410a921b3a88f78d0705ba8718252
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399855"
---
# <a name="security-of-nethttpbinding"></a><span data-ttu-id="cf517-102">\<> de seguridad \<de netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="cf517-102">\<security> of \<netHttpBinding></span></span>

<span data-ttu-id="cf517-103">Define las capacidades de seguridad de la [ \<> netHttpBinding](nethttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="cf517-103">Defines the security capabilities of the [\<netHttpBinding>](nethttpbinding.md).</span></span>

<span data-ttu-id="cf517-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="cf517-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="cf517-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="cf517-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="cf517-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enlaces**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="cf517-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="cf517-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> netHttpBinding**](nethttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="cf517-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)</span></span>\
<span data-ttu-id="cf517-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de enlace**</span><span class="sxs-lookup"><span data-stu-id="cf517-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="cf517-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de seguridad**</span><span class="sxs-lookup"><span data-stu-id="cf517-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="cf517-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cf517-110">Syntax</span></span>

```xml
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cf517-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="cf517-111">Attributes and elements</span></span>

<span data-ttu-id="cf517-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="cf517-112">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="cf517-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="cf517-113">Attributes</span></span>

|<span data-ttu-id="cf517-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="cf517-114">Attribute</span></span>|<span data-ttu-id="cf517-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="cf517-115">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="cf517-116">modo</span><span class="sxs-lookup"><span data-stu-id="cf517-116">mode</span></span>|<span data-ttu-id="cf517-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="cf517-117">Optional.</span></span> <span data-ttu-id="cf517-118">Especifica el tipo de seguridad que se utiliza.</span><span class="sxs-lookup"><span data-stu-id="cf517-118">Specifies the type of security that is used.</span></span> <span data-ttu-id="cf517-119">El valor predeterminado es `None`.</span><span class="sxs-lookup"><span data-stu-id="cf517-119">The default is `None`.</span></span> <span data-ttu-id="cf517-120">Este atributo es del tipo <xref:System.ServiceModel.BasicHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="cf517-120">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|

## <a name="mode-attribute"></a><span data-ttu-id="cf517-121">atributo de modo</span><span class="sxs-lookup"><span data-stu-id="cf517-121">mode attribute</span></span>

|<span data-ttu-id="cf517-122">Valor</span><span class="sxs-lookup"><span data-stu-id="cf517-122">Value</span></span>|<span data-ttu-id="cf517-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="cf517-123">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="cf517-124">None</span><span class="sxs-lookup"><span data-stu-id="cf517-124">None</span></span>|<span data-ttu-id="cf517-125">: Los mensajes no están protegidos durante la transferencia.</span><span class="sxs-lookup"><span data-stu-id="cf517-125">-   Messages are not secured during transfer.</span></span>|
|<span data-ttu-id="cf517-126">Transporte</span><span class="sxs-lookup"><span data-stu-id="cf517-126">Transport</span></span>|<span data-ttu-id="cf517-127">La seguridad se proporciona utilizando transporte HTTPS.</span><span class="sxs-lookup"><span data-stu-id="cf517-127">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="cf517-128">Los mensajes SOAP se protegen utilizando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="cf517-128">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="cf517-129">El servicio se autentica al cliente utilizando el certificado X.509 del servicio.</span><span class="sxs-lookup"><span data-stu-id="cf517-129">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="cf517-130">El cliente se autentica utilizando el ClientCredentialType proporcionado.</span><span class="sxs-lookup"><span data-stu-id="cf517-130">The client is authenticated using the ClientCredentialType supplied.</span></span>|
|<span data-ttu-id="cf517-131">Message</span><span class="sxs-lookup"><span data-stu-id="cf517-131">Message</span></span>|<span data-ttu-id="cf517-132">La seguridad se proporciona mediante la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="cf517-132">Security is provided using SOAP message security.</span></span> <span data-ttu-id="cf517-133">De forma predeterminada, el cuerpo se cifra y firma.</span><span class="sxs-lookup"><span data-stu-id="cf517-133">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="cf517-134">Para este enlace, el sistema requiere que el certificado de servidor se proporcione al cliente fuera de la banda.</span><span class="sxs-lookup"><span data-stu-id="cf517-134">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="cf517-135">El único `ClientCredentialType` válido para este enlace es `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="cf517-135">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|
|<span data-ttu-id="cf517-136">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="cf517-136">TransportWithMessageCredential</span></span>|<span data-ttu-id="cf517-137">La seguridad de transporte proporciona integridad, confidencialidad y autenticación del servidor.</span><span class="sxs-lookup"><span data-stu-id="cf517-137">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="cf517-138">La autenticación del cliente se proporciona por medio de la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="cf517-138">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="cf517-139">Este modo es pertinente cuando el usuario está autenticando utilizando el nombre de usuario/contraseña y existe una implementación del HTTP existente para proteger la transferencia del mensaje.</span><span class="sxs-lookup"><span data-stu-id="cf517-139">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|
|<span data-ttu-id="cf517-140">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="cf517-140">TransportCredentialOnly</span></span>|<span data-ttu-id="cf517-141">Este modo no proporciona integridad del mensaje y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="cf517-141">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="cf517-142">Proporciona la autenticación del cliente basada en http.</span><span class="sxs-lookup"><span data-stu-id="cf517-142">It provides http-based client authentication.</span></span> <span data-ttu-id="cf517-143">Este modo se debe utilizar con precaución.</span><span class="sxs-lookup"><span data-stu-id="cf517-143">This mode should be used with caution.</span></span> <span data-ttu-id="cf517-144">Se debe usar en entornos en los que la seguridad de transporte se proporciona por otros medios (como IPSec) y la infraestructura de WCF proporciona únicamente la autenticación del cliente.</span><span class="sxs-lookup"><span data-stu-id="cf517-144">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="cf517-145">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="cf517-145">Child elements</span></span>

|<span data-ttu-id="cf517-146">Elemento</span><span class="sxs-lookup"><span data-stu-id="cf517-146">Element</span></span>|<span data-ttu-id="cf517-147">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="cf517-147">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cf517-148">\<> de transporte</span><span class="sxs-lookup"><span data-stu-id="cf517-148">\<transport></span></span>](transport-of-nethttpbinding.md)|<span data-ttu-id="cf517-149">Define los valores de seguridad de transporte para un servicio HTTP básico.</span><span class="sxs-lookup"><span data-stu-id="cf517-149">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="cf517-150">Este elemento corresponde a <xref:System.ServiceModel.HttpTransportSecurity>.</span><span class="sxs-lookup"><span data-stu-id="cf517-150">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|
|[<span data-ttu-id="cf517-151">\<message></span><span class="sxs-lookup"><span data-stu-id="cf517-151">\<message></span></span>](message-of-nethttpbinding.md)|<span data-ttu-id="cf517-152">Define los valores de modo de seguridad para un servicio HTTP básico.</span><span class="sxs-lookup"><span data-stu-id="cf517-152">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="cf517-153">Este elemento corresponde a <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span><span class="sxs-lookup"><span data-stu-id="cf517-153">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="cf517-154">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="cf517-154">Parent elements</span></span>

|<span data-ttu-id="cf517-155">Elemento</span><span class="sxs-lookup"><span data-stu-id="cf517-155">Element</span></span>|<span data-ttu-id="cf517-156">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="cf517-156">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="cf517-157">enlace</span><span class="sxs-lookup"><span data-stu-id="cf517-157">binding</span></span>|<span data-ttu-id="cf517-158">Elemento de enlace del [ \<> basicHttpBinding](basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="cf517-158">The binding element of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|

## <a name="remarks"></a><span data-ttu-id="cf517-159">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cf517-159">Remarks</span></span>

 <span data-ttu-id="cf517-160">De forma predeterminada, no se protege el mensaje SOAP y no se autentica el cliente.</span><span class="sxs-lookup"><span data-stu-id="cf517-160">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="cf517-161">Este elemento le permite establecer la configuración de seguridad adicional para el elemento `netHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="cf517-161">This element enables you to configure additional security settings for the `netHttpBinding` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="cf517-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf517-162">See also</span></span>

- <xref:System.ServiceModel.NetHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetHttpBindingElement.Security%2A>  
- [<span data-ttu-id="cf517-163">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="cf517-163">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="cf517-164">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="cf517-164">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="cf517-165">Enlaces</span><span class="sxs-lookup"><span data-stu-id="cf517-165">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="cf517-166">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="cf517-166">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="cf517-167">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="cf517-167">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="cf517-168">\<binding></span><span class="sxs-lookup"><span data-stu-id="cf517-168">\<binding></span></span>](../../../misc/binding.md)
