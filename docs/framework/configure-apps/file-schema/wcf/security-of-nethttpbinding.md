---
title: <security> de <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: dc41f6f7-cabc-4a64-9fa0-ceabf861b348
ms.openlocfilehash: 97c52fa4f062ed0c65d5b1a8ca47a1439ab04cf5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736482"
---
# <a name="security-of-nethttpbinding"></a><span data-ttu-id="2b7c0-102">\<security> de \<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="2b7c0-102">\<security> of \<netHttpBinding></span></span>

<span data-ttu-id="2b7c0-103">Define las capacidades de seguridad de [\<netHttpBinding>](nethttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="2b7c0-103">Defines the security capabilities of the [\<netHttpBinding>](nethttpbinding.md).</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  

## <a name="syntax"></a><span data-ttu-id="2b7c0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2b7c0-104">Syntax</span></span>

```xml
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2b7c0-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2b7c0-105">Attributes and elements</span></span>

<span data-ttu-id="2b7c0-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2b7c0-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="2b7c0-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="2b7c0-107">Attributes</span></span>

|<span data-ttu-id="2b7c0-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="2b7c0-108">Attribute</span></span>|<span data-ttu-id="2b7c0-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="2b7c0-109">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="2b7c0-110">mode</span><span class="sxs-lookup"><span data-stu-id="2b7c0-110">mode</span></span>|<span data-ttu-id="2b7c0-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="2b7c0-111">Optional.</span></span> <span data-ttu-id="2b7c0-112">Especifica el tipo de seguridad que se utiliza.</span><span class="sxs-lookup"><span data-stu-id="2b7c0-112">Specifies the type of security that is used.</span></span> <span data-ttu-id="2b7c0-113">De manera predeterminada, es `None`.</span><span class="sxs-lookup"><span data-stu-id="2b7c0-113">The default is `None`.</span></span> <span data-ttu-id="2b7c0-114">Este atributo es del tipo <xref:System.ServiceModel.BasicHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="2b7c0-114">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|

## <a name="mode-attribute"></a><span data-ttu-id="2b7c0-115">atributo de modo</span><span class="sxs-lookup"><span data-stu-id="2b7c0-115">mode attribute</span></span>

|<span data-ttu-id="2b7c0-116">Value</span><span class="sxs-lookup"><span data-stu-id="2b7c0-116">Value</span></span>|<span data-ttu-id="2b7c0-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="2b7c0-117">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="2b7c0-118">None</span><span class="sxs-lookup"><span data-stu-id="2b7c0-118">None</span></span>|<span data-ttu-id="2b7c0-119">: Los mensajes no están protegidos durante la transferencia.</span><span class="sxs-lookup"><span data-stu-id="2b7c0-119">-   Messages are not secured during transfer.</span></span>|
|<span data-ttu-id="2b7c0-120">Transporte</span><span class="sxs-lookup"><span data-stu-id="2b7c0-120">Transport</span></span>|<span data-ttu-id="2b7c0-121">La seguridad se proporciona utilizando transporte HTTPS.</span><span class="sxs-lookup"><span data-stu-id="2b7c0-121">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="2b7c0-122">Los mensajes SOAP están protegidos mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="2b7c0-122">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="2b7c0-123">El servicio se autentica al cliente utilizando el certificado X.509 del servicio.</span><span class="sxs-lookup"><span data-stu-id="2b7c0-123">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="2b7c0-124">El cliente se autentica utilizando el ClientCredentialType proporcionado.</span><span class="sxs-lookup"><span data-stu-id="2b7c0-124">The client is authenticated using the ClientCredentialType supplied.</span></span>|
|<span data-ttu-id="2b7c0-125">Message</span><span class="sxs-lookup"><span data-stu-id="2b7c0-125">Message</span></span>|<span data-ttu-id="2b7c0-126">La seguridad se proporciona mediante la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="2b7c0-126">Security is provided using SOAP message security.</span></span> <span data-ttu-id="2b7c0-127">De forma predeterminada, el cuerpo se cifra y firma.</span><span class="sxs-lookup"><span data-stu-id="2b7c0-127">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="2b7c0-128">Para este enlace, el sistema requiere que el certificado de servidor se proporcione al cliente fuera de la banda.</span><span class="sxs-lookup"><span data-stu-id="2b7c0-128">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="2b7c0-129">El único `ClientCredentialType` válido para este enlace es `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="2b7c0-129">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|
|<span data-ttu-id="2b7c0-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="2b7c0-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="2b7c0-131">La seguridad de transporte proporciona integridad, confidencialidad y autenticación del servidor.</span><span class="sxs-lookup"><span data-stu-id="2b7c0-131">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="2b7c0-132">La autenticación del cliente se proporciona por medio de la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="2b7c0-132">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="2b7c0-133">Este modo es pertinente cuando el usuario está autenticando utilizando el nombre de usuario/contraseña y existe una implementación del HTTP existente para proteger la transferencia del mensaje.</span><span class="sxs-lookup"><span data-stu-id="2b7c0-133">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|
|<span data-ttu-id="2b7c0-134">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="2b7c0-134">TransportCredentialOnly</span></span>|<span data-ttu-id="2b7c0-135">Este modo no proporciona integridad del mensaje y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="2b7c0-135">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="2b7c0-136">Proporciona la autenticación del cliente basada en http.</span><span class="sxs-lookup"><span data-stu-id="2b7c0-136">It provides http-based client authentication.</span></span> <span data-ttu-id="2b7c0-137">Este modo se debe utilizar con precaución.</span><span class="sxs-lookup"><span data-stu-id="2b7c0-137">This mode should be used with caution.</span></span> <span data-ttu-id="2b7c0-138">Se debe usar en entornos en los que la seguridad de transporte se proporciona por otros medios (como IPSec) y la infraestructura de WCF proporciona únicamente la autenticación del cliente.</span><span class="sxs-lookup"><span data-stu-id="2b7c0-138">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="2b7c0-139">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2b7c0-139">Child elements</span></span>

|<span data-ttu-id="2b7c0-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="2b7c0-140">Element</span></span>|<span data-ttu-id="2b7c0-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="2b7c0-141">Description</span></span>|
|-------------|-----------------|
|[\<transport>](transport-of-nethttpbinding.md)|<span data-ttu-id="2b7c0-142">Define los valores de seguridad de transporte para un servicio HTTP básico.</span><span class="sxs-lookup"><span data-stu-id="2b7c0-142">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="2b7c0-143">Este elemento corresponde a <xref:System.ServiceModel.HttpTransportSecurity>.</span><span class="sxs-lookup"><span data-stu-id="2b7c0-143">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|
|[\<message>](message-of-nethttpbinding.md)|<span data-ttu-id="2b7c0-144">Define los valores de modo de seguridad para un servicio HTTP básico.</span><span class="sxs-lookup"><span data-stu-id="2b7c0-144">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="2b7c0-145">Este elemento corresponde a <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span><span class="sxs-lookup"><span data-stu-id="2b7c0-145">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="2b7c0-146">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2b7c0-146">Parent elements</span></span>

|<span data-ttu-id="2b7c0-147">Elemento</span><span class="sxs-lookup"><span data-stu-id="2b7c0-147">Element</span></span>|<span data-ttu-id="2b7c0-148">Descripción</span><span class="sxs-lookup"><span data-stu-id="2b7c0-148">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="2b7c0-149">binding</span><span class="sxs-lookup"><span data-stu-id="2b7c0-149">binding</span></span>|<span data-ttu-id="2b7c0-150">Elemento de enlace de [\<basicHttpBinding>](basichttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="2b7c0-150">The binding element of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|

## <a name="remarks"></a><span data-ttu-id="2b7c0-151">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2b7c0-151">Remarks</span></span>

 <span data-ttu-id="2b7c0-152">De forma predeterminada, no se protege el mensaje SOAP y no se autentica el cliente.</span><span class="sxs-lookup"><span data-stu-id="2b7c0-152">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="2b7c0-153">Este elemento le permite establecer la configuración de seguridad adicional para el elemento `netHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="2b7c0-153">This element enables you to configure additional security settings for the `netHttpBinding` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="2b7c0-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2b7c0-154">See also</span></span>

- <xref:System.ServiceModel.NetHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetHttpBindingElement.Security%2A>  
- [<span data-ttu-id="2b7c0-155">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="2b7c0-155">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="2b7c0-156">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="2b7c0-156">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="2b7c0-157">Enlaces</span><span class="sxs-lookup"><span data-stu-id="2b7c0-157">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="2b7c0-158">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="2b7c0-158">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="2b7c0-159">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="2b7c0-159">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
