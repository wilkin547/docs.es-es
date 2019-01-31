---
title: <security> de <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: dc41f6f7-cabc-4a64-9fa0-ceabf861b348
ms.openlocfilehash: f2750036aa4d3fbe41062ad041e50ff3a4be32b5
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283977"
---
# <a name="security-of-nethttpbinding"></a><span data-ttu-id="41876-102">\<seguridad > de \<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="41876-102">\<security> of \<netHttpBinding></span></span>

<span data-ttu-id="41876-103">Define las funciones de seguridad de la [ \<basicHttpBinding >](basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="41876-103">Defines the security capabilities of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>

<span data-ttu-id="41876-104">\<system.ServiceModel>\\</span><span class="sxs-lookup"><span data-stu-id="41876-104">\<system.ServiceModel>\\</span></span>
<span data-ttu-id="41876-105">\<bindings>\\</span><span class="sxs-lookup"><span data-stu-id="41876-105">\<bindings>\\</span></span>
<span data-ttu-id="41876-106">\<netHttpBinding>\\</span><span class="sxs-lookup"><span data-stu-id="41876-106">\<netHttpBinding>\\</span></span>
<span data-ttu-id="41876-107">\<binding>\\</span><span class="sxs-lookup"><span data-stu-id="41876-107">\<binding>\\</span></span>
<span data-ttu-id="41876-108">\<security></span><span class="sxs-lookup"><span data-stu-id="41876-108">\<security></span></span>

## <a name="syntax"></a><span data-ttu-id="41876-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="41876-109">Syntax</span></span>

```xml
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="41876-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="41876-110">Attributes and elements</span></span>

<span data-ttu-id="41876-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="41876-111">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="41876-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="41876-112">Attributes</span></span>

|<span data-ttu-id="41876-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="41876-113">Attribute</span></span>|<span data-ttu-id="41876-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="41876-114">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="41876-115">modo</span><span class="sxs-lookup"><span data-stu-id="41876-115">mode</span></span>|<span data-ttu-id="41876-116">Opcional.</span><span class="sxs-lookup"><span data-stu-id="41876-116">Optional.</span></span> <span data-ttu-id="41876-117">Especifica el tipo de seguridad que se utiliza.</span><span class="sxs-lookup"><span data-stu-id="41876-117">Specifies the type of security that is used.</span></span> <span data-ttu-id="41876-118">De manera predeterminada, es `None`.</span><span class="sxs-lookup"><span data-stu-id="41876-118">The default is `None`.</span></span> <span data-ttu-id="41876-119">Este atributo es del tipo <xref:System.ServiceModel.BasicHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="41876-119">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|

## <a name="mode-attribute"></a><span data-ttu-id="41876-120">atributo mode</span><span class="sxs-lookup"><span data-stu-id="41876-120">mode attribute</span></span>

|<span data-ttu-id="41876-121">Valor</span><span class="sxs-lookup"><span data-stu-id="41876-121">Value</span></span>|<span data-ttu-id="41876-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="41876-122">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="41876-123">Ninguna</span><span class="sxs-lookup"><span data-stu-id="41876-123">None</span></span>|<span data-ttu-id="41876-124">-Los mensajes no están protegidos durante la transferencia.</span><span class="sxs-lookup"><span data-stu-id="41876-124">-   Messages are not secured during transfer.</span></span>|
|<span data-ttu-id="41876-125">Transporte</span><span class="sxs-lookup"><span data-stu-id="41876-125">Transport</span></span>|<span data-ttu-id="41876-126">La seguridad se proporciona utilizando transporte HTTPS.</span><span class="sxs-lookup"><span data-stu-id="41876-126">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="41876-127">Los mensajes SOAP se protegen utilizando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="41876-127">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="41876-128">El servicio se autentica al cliente utilizando el certificado X.509 del servicio.</span><span class="sxs-lookup"><span data-stu-id="41876-128">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="41876-129">El cliente se autentica utilizando el ClientCredentialType proporcionado.</span><span class="sxs-lookup"><span data-stu-id="41876-129">The client is authenticated using the ClientCredentialType supplied.</span></span>|
|<span data-ttu-id="41876-130">Mensaje</span><span class="sxs-lookup"><span data-stu-id="41876-130">Message</span></span>|<span data-ttu-id="41876-131">La seguridad se proporciona mediante la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="41876-131">Security is provided using SOAP message security.</span></span> <span data-ttu-id="41876-132">De forma predeterminada, el cuerpo se cifra y firma.</span><span class="sxs-lookup"><span data-stu-id="41876-132">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="41876-133">Para este enlace, el sistema requiere que el certificado de servidor se proporcione al cliente fuera de la banda.</span><span class="sxs-lookup"><span data-stu-id="41876-133">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="41876-134">El único `ClientCredentialType` válido para este enlace es `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="41876-134">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|
|<span data-ttu-id="41876-135">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="41876-135">TransportWithMessageCredential</span></span>|<span data-ttu-id="41876-136">La seguridad de transporte proporciona integridad, confidencialidad y autenticación del servidor.</span><span class="sxs-lookup"><span data-stu-id="41876-136">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="41876-137">La autenticación del cliente se proporciona por medio de la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="41876-137">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="41876-138">Este modo es pertinente cuando el usuario está autenticando utilizando el nombre de usuario/contraseña y existe una implementación del HTTP existente para proteger la transferencia del mensaje.</span><span class="sxs-lookup"><span data-stu-id="41876-138">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|
|<span data-ttu-id="41876-139">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="41876-139">TransportCredentialOnly</span></span>|<span data-ttu-id="41876-140">Este modo no proporciona integridad del mensaje y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="41876-140">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="41876-141">Proporciona la autenticación del cliente basada en http.</span><span class="sxs-lookup"><span data-stu-id="41876-141">It provides http-based client authentication.</span></span> <span data-ttu-id="41876-142">Este modo se debe utilizar con precaución.</span><span class="sxs-lookup"><span data-stu-id="41876-142">This mode should be used with caution.</span></span> <span data-ttu-id="41876-143">Se debe usar en entornos donde la seguridad de transporte se proporciona por otros medios (por ejemplo, IPSec) y la infraestructura de WCF proporciona sólo la autenticación de cliente.</span><span class="sxs-lookup"><span data-stu-id="41876-143">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="41876-144">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="41876-144">Child elements</span></span>

|<span data-ttu-id="41876-145">Elemento</span><span class="sxs-lookup"><span data-stu-id="41876-145">Element</span></span>|<span data-ttu-id="41876-146">Descripción</span><span class="sxs-lookup"><span data-stu-id="41876-146">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="41876-147">\<transport></span><span class="sxs-lookup"><span data-stu-id="41876-147">\<transport></span></span>](transport-of-nethttpbinding.md)|<span data-ttu-id="41876-148">Define los valores de seguridad de transporte para un servicio HTTP básico.</span><span class="sxs-lookup"><span data-stu-id="41876-148">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="41876-149">Este elemento corresponde a <xref:System.ServiceModel.HttpTransportSecurity>.</span><span class="sxs-lookup"><span data-stu-id="41876-149">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|
|[<span data-ttu-id="41876-150">\<message></span><span class="sxs-lookup"><span data-stu-id="41876-150">\<message></span></span>](message-of-nethttpbinding.md)|<span data-ttu-id="41876-151">Define los valores de modo de seguridad para un servicio HTTP básico.</span><span class="sxs-lookup"><span data-stu-id="41876-151">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="41876-152">Este elemento corresponde a <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span><span class="sxs-lookup"><span data-stu-id="41876-152">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="41876-153">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="41876-153">Parent elements</span></span>

|<span data-ttu-id="41876-154">Elemento</span><span class="sxs-lookup"><span data-stu-id="41876-154">Element</span></span>|<span data-ttu-id="41876-155">Descripción</span><span class="sxs-lookup"><span data-stu-id="41876-155">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="41876-156">enlace</span><span class="sxs-lookup"><span data-stu-id="41876-156">binding</span></span>|<span data-ttu-id="41876-157">El elemento de enlace de la [ \<basicHttpBinding >](basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="41876-157">The binding element of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|

## <a name="remarks"></a><span data-ttu-id="41876-158">Comentarios</span><span class="sxs-lookup"><span data-stu-id="41876-158">Remarks</span></span>

 <span data-ttu-id="41876-159">De forma predeterminada, no se protege el mensaje SOAP y no se autentica el cliente.</span><span class="sxs-lookup"><span data-stu-id="41876-159">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="41876-160">Este elemento le permite establecer la configuración de seguridad adicional para el elemento `netHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="41876-160">This element enables you to configure additional security settings for the `netHttpBinding` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="41876-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="41876-161">See also</span></span>

- <xref:System.ServiceModel.NetHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetHttpBindingElement.Security%2A>  
- [<span data-ttu-id="41876-162">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="41876-162">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="41876-163">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="41876-163">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="41876-164">Enlaces</span><span class="sxs-lookup"><span data-stu-id="41876-164">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="41876-165">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="41876-165">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="41876-166">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="41876-166">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="41876-167">\<binding></span><span class="sxs-lookup"><span data-stu-id="41876-167">\<binding></span></span>](../../../misc/binding.md)
