---
description: 'Más información sobre: <security> de <netHttpBinding>'
title: <security> de <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: dc41f6f7-cabc-4a64-9fa0-ceabf861b348
ms.openlocfilehash: 70d6363c0ac7fa00d83880ddc8c873548b385a29
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683130"
---
# <a name="security-of-nethttpbinding"></a><span data-ttu-id="98ea0-103">\<security> de \<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="98ea0-103">\<security> of \<netHttpBinding></span></span>

<span data-ttu-id="98ea0-104">Define las capacidades de seguridad de [\<netHttpBinding>](nethttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="98ea0-104">Defines the security capabilities of the [\<netHttpBinding>](nethttpbinding.md).</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  

## <a name="syntax"></a><span data-ttu-id="98ea0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="98ea0-105">Syntax</span></span>

```xml
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="98ea0-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="98ea0-106">Attributes and elements</span></span>

<span data-ttu-id="98ea0-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="98ea0-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="98ea0-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="98ea0-108">Attributes</span></span>

|<span data-ttu-id="98ea0-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="98ea0-109">Attribute</span></span>|<span data-ttu-id="98ea0-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="98ea0-110">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="98ea0-111">mode</span><span class="sxs-lookup"><span data-stu-id="98ea0-111">mode</span></span>|<span data-ttu-id="98ea0-112">Opcional.</span><span class="sxs-lookup"><span data-stu-id="98ea0-112">Optional.</span></span> <span data-ttu-id="98ea0-113">Especifica el tipo de seguridad que se utiliza.</span><span class="sxs-lookup"><span data-stu-id="98ea0-113">Specifies the type of security that is used.</span></span> <span data-ttu-id="98ea0-114">De manera predeterminada, es `None`.</span><span class="sxs-lookup"><span data-stu-id="98ea0-114">The default is `None`.</span></span> <span data-ttu-id="98ea0-115">Este atributo es del tipo <xref:System.ServiceModel.BasicHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="98ea0-115">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|

## <a name="mode-attribute"></a><span data-ttu-id="98ea0-116">atributo de modo</span><span class="sxs-lookup"><span data-stu-id="98ea0-116">mode attribute</span></span>

|<span data-ttu-id="98ea0-117">Value</span><span class="sxs-lookup"><span data-stu-id="98ea0-117">Value</span></span>|<span data-ttu-id="98ea0-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="98ea0-118">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="98ea0-119">None</span><span class="sxs-lookup"><span data-stu-id="98ea0-119">None</span></span>|<span data-ttu-id="98ea0-120">: Los mensajes no están protegidos durante la transferencia.</span><span class="sxs-lookup"><span data-stu-id="98ea0-120">-   Messages are not secured during transfer.</span></span>|
|<span data-ttu-id="98ea0-121">Transporte</span><span class="sxs-lookup"><span data-stu-id="98ea0-121">Transport</span></span>|<span data-ttu-id="98ea0-122">La seguridad se proporciona utilizando transporte HTTPS.</span><span class="sxs-lookup"><span data-stu-id="98ea0-122">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="98ea0-123">Los mensajes SOAP están protegidos mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="98ea0-123">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="98ea0-124">El servicio se autentica al cliente utilizando el certificado X.509 del servicio.</span><span class="sxs-lookup"><span data-stu-id="98ea0-124">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="98ea0-125">El cliente se autentica utilizando el ClientCredentialType proporcionado.</span><span class="sxs-lookup"><span data-stu-id="98ea0-125">The client is authenticated using the ClientCredentialType supplied.</span></span>|
|<span data-ttu-id="98ea0-126">Message</span><span class="sxs-lookup"><span data-stu-id="98ea0-126">Message</span></span>|<span data-ttu-id="98ea0-127">La seguridad se proporciona mediante la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="98ea0-127">Security is provided using SOAP message security.</span></span> <span data-ttu-id="98ea0-128">De forma predeterminada, el cuerpo se cifra y firma.</span><span class="sxs-lookup"><span data-stu-id="98ea0-128">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="98ea0-129">Para este enlace, el sistema requiere que el certificado de servidor se proporcione al cliente fuera de la banda.</span><span class="sxs-lookup"><span data-stu-id="98ea0-129">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="98ea0-130">El único `ClientCredentialType` válido para este enlace es `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="98ea0-130">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|
|<span data-ttu-id="98ea0-131">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="98ea0-131">TransportWithMessageCredential</span></span>|<span data-ttu-id="98ea0-132">La seguridad de transporte proporciona integridad, confidencialidad y autenticación del servidor.</span><span class="sxs-lookup"><span data-stu-id="98ea0-132">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="98ea0-133">La autenticación del cliente se proporciona por medio de la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="98ea0-133">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="98ea0-134">Este modo es pertinente cuando el usuario está autenticando utilizando el nombre de usuario/contraseña y existe una implementación del HTTP existente para proteger la transferencia del mensaje.</span><span class="sxs-lookup"><span data-stu-id="98ea0-134">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|
|<span data-ttu-id="98ea0-135">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="98ea0-135">TransportCredentialOnly</span></span>|<span data-ttu-id="98ea0-136">Este modo no proporciona integridad del mensaje y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="98ea0-136">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="98ea0-137">Proporciona la autenticación del cliente basada en http.</span><span class="sxs-lookup"><span data-stu-id="98ea0-137">It provides http-based client authentication.</span></span> <span data-ttu-id="98ea0-138">Este modo se debe utilizar con precaución.</span><span class="sxs-lookup"><span data-stu-id="98ea0-138">This mode should be used with caution.</span></span> <span data-ttu-id="98ea0-139">Se debe usar en entornos en los que la seguridad de transporte se proporciona por otros medios (como IPSec) y la infraestructura de WCF proporciona únicamente la autenticación del cliente.</span><span class="sxs-lookup"><span data-stu-id="98ea0-139">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="98ea0-140">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="98ea0-140">Child elements</span></span>

|<span data-ttu-id="98ea0-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="98ea0-141">Element</span></span>|<span data-ttu-id="98ea0-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="98ea0-142">Description</span></span>|
|-------------|-----------------|
|[\<transport>](transport-of-nethttpbinding.md)|<span data-ttu-id="98ea0-143">Define los valores de seguridad de transporte para un servicio HTTP básico.</span><span class="sxs-lookup"><span data-stu-id="98ea0-143">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="98ea0-144">Este elemento corresponde a <xref:System.ServiceModel.HttpTransportSecurity>.</span><span class="sxs-lookup"><span data-stu-id="98ea0-144">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|
|[\<message>](message-of-nethttpbinding.md)|<span data-ttu-id="98ea0-145">Define los valores de modo de seguridad para un servicio HTTP básico.</span><span class="sxs-lookup"><span data-stu-id="98ea0-145">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="98ea0-146">Este elemento corresponde a <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span><span class="sxs-lookup"><span data-stu-id="98ea0-146">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="98ea0-147">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="98ea0-147">Parent elements</span></span>

|<span data-ttu-id="98ea0-148">Elemento</span><span class="sxs-lookup"><span data-stu-id="98ea0-148">Element</span></span>|<span data-ttu-id="98ea0-149">Descripción</span><span class="sxs-lookup"><span data-stu-id="98ea0-149">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="98ea0-150">binding</span><span class="sxs-lookup"><span data-stu-id="98ea0-150">binding</span></span>|<span data-ttu-id="98ea0-151">Elemento de enlace de [\<basicHttpBinding>](basichttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="98ea0-151">The binding element of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|

## <a name="remarks"></a><span data-ttu-id="98ea0-152">Observaciones</span><span class="sxs-lookup"><span data-stu-id="98ea0-152">Remarks</span></span>

 <span data-ttu-id="98ea0-153">De forma predeterminada, no se protege el mensaje SOAP y no se autentica el cliente.</span><span class="sxs-lookup"><span data-stu-id="98ea0-153">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="98ea0-154">Este elemento le permite establecer la configuración de seguridad adicional para el elemento `netHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="98ea0-154">This element enables you to configure additional security settings for the `netHttpBinding` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="98ea0-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="98ea0-155">See also</span></span>

- <xref:System.ServiceModel.NetHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetHttpBindingElement.Security%2A>  
- [<span data-ttu-id="98ea0-156">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="98ea0-156">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="98ea0-157">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="98ea0-157">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="98ea0-158">Enlaces</span><span class="sxs-lookup"><span data-stu-id="98ea0-158">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="98ea0-159">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="98ea0-159">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="98ea0-160">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="98ea0-160">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
