---
title: <messageSenderAuthentication> elemento
ms.date: 03/30/2017
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
ms.openlocfilehash: 410fffd541926b9a2e75c04d26a2a1e08a262939
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135063"
---
# <a name="messagesenderauthentication-element"></a><span data-ttu-id="384dc-102">\<messageSenderAuthentication > elemento</span><span class="sxs-lookup"><span data-stu-id="384dc-102">\<messageSenderAuthentication> element</span></span>
<span data-ttu-id="384dc-103">Especifica las opciones de autenticación para los remitentes del mensaje punto a punto.</span><span class="sxs-lookup"><span data-stu-id="384dc-103">Specifies authentication options for peer-to-peer message senders.</span></span>  
  
 <span data-ttu-id="384dc-104">Para obtener más información acerca de la programación de punto a punto, vea [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="384dc-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
 <span data-ttu-id="384dc-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="384dc-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="384dc-106">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="384dc-106">\<behaviors></span></span>  
<span data-ttu-id="384dc-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="384dc-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="384dc-108">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="384dc-108">\<behavior></span></span>  
<span data-ttu-id="384dc-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="384dc-109">\<clientCredentials></span></span>  
<span data-ttu-id="384dc-110">\<peer></span><span class="sxs-lookup"><span data-stu-id="384dc-110">\<peer></span></span>  
<span data-ttu-id="384dc-111">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="384dc-111">\<messageSenderAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="384dc-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="384dc-112">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="384dc-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="384dc-113">Attributes and Elements</span></span>  
 <span data-ttu-id="384dc-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="384dc-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="384dc-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="384dc-115">Attributes</span></span>  
  
|<span data-ttu-id="384dc-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="384dc-116">Attribute</span></span>|<span data-ttu-id="384dc-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="384dc-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="384dc-118">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="384dc-118">customCertificateValidatorType</span></span>|<span data-ttu-id="384dc-119">Tipo y ensamblado utilizados para validar un tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="384dc-119">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="384dc-120">Se debe establecer este atributo cuando `certificateValidationMode` está establecido en `Custom`.</span><span class="sxs-lookup"><span data-stu-id="384dc-120">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|<span data-ttu-id="384dc-121">certifcateValidationMode</span><span class="sxs-lookup"><span data-stu-id="384dc-121">certifcateValidationMode</span></span>|<span data-ttu-id="384dc-122">Especifica uno de los tres modos utilizados para validar las credenciales.</span><span class="sxs-lookup"><span data-stu-id="384dc-122">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="384dc-123">Si se establece en `Custom`, también debe proporcionarse un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="384dc-123">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|<span data-ttu-id="384dc-124">revocationMode</span><span class="sxs-lookup"><span data-stu-id="384dc-124">revocationMode</span></span>|<span data-ttu-id="384dc-125">Uno de los modos utilizados para comprobar listas de certificados revocadas (CRL).</span><span class="sxs-lookup"><span data-stu-id="384dc-125">One of the modes used to check for a revoked certificate lists (CRL).</span></span>|  
|<span data-ttu-id="384dc-126">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="384dc-126">trustedStoreLocation</span></span>|<span data-ttu-id="384dc-127">Una de las dos ubicaciones de almacenamiento del sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="384dc-127">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="384dc-128">Se utiliza este valor cuando un certificado del servicio se negocia al cliente.</span><span class="sxs-lookup"><span data-stu-id="384dc-128">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="384dc-129">Se realiza la validación contra el **personas de confianza** almacenar en la ubicación del almacén especificado.</span><span class="sxs-lookup"><span data-stu-id="384dc-129">Validation is performed against the **Trusted People** store in the specified store location.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="384dc-130">Atributo customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="384dc-130">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="384dc-131">Valor</span><span class="sxs-lookup"><span data-stu-id="384dc-131">Value</span></span>|<span data-ttu-id="384dc-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="384dc-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="384dc-133">String</span><span class="sxs-lookup"><span data-stu-id="384dc-133">String</span></span>|<span data-ttu-id="384dc-134">Opcional.</span><span class="sxs-lookup"><span data-stu-id="384dc-134">Optional.</span></span> <span data-ttu-id="384dc-135">Especifica el nombre de tipo y el ensamblado y otros datos utilizados para buscar el tipo.</span><span class="sxs-lookup"><span data-stu-id="384dc-135">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="384dc-136">Como mínimo, se requieren un espacio de nombres y un nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="384dc-136">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="384dc-137">La información opcionales incluye: nombre de ensamblado, número de versión, referencia cultural y token de clave pública.</span><span class="sxs-lookup"><span data-stu-id="384dc-137">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="384dc-138">Atributo certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="384dc-138">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="384dc-139">Valor</span><span class="sxs-lookup"><span data-stu-id="384dc-139">Value</span></span>|<span data-ttu-id="384dc-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="384dc-140">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="384dc-141">Enumeración</span><span class="sxs-lookup"><span data-stu-id="384dc-141">Enumeration</span></span>|<span data-ttu-id="384dc-142">Opcional.</span><span class="sxs-lookup"><span data-stu-id="384dc-142">Optional.</span></span> <span data-ttu-id="384dc-143">Uno de los siguientes valores: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="384dc-143">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="384dc-144">De manera predeterminada, es `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="384dc-144">The default is `ChainTrust`.</span></span> <span data-ttu-id="384dc-145">De manera predeterminada, es `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="384dc-145">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="384dc-146">Para obtener más información, consulte [trabajar con certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="384dc-146">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="384dc-147">Atributo revocationMode</span><span class="sxs-lookup"><span data-stu-id="384dc-147">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="384dc-148">Valor</span><span class="sxs-lookup"><span data-stu-id="384dc-148">Value</span></span>|<span data-ttu-id="384dc-149">Descripción</span><span class="sxs-lookup"><span data-stu-id="384dc-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="384dc-150">Enumeración</span><span class="sxs-lookup"><span data-stu-id="384dc-150">Enumeration</span></span>|<span data-ttu-id="384dc-151">Uno de los siguientes valores: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="384dc-151">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="384dc-152">De manera predeterminada, es `Online`.</span><span class="sxs-lookup"><span data-stu-id="384dc-152">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="384dc-153">Para obtener más información, consulte [trabajar con certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="384dc-153">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="384dc-154">Atributo trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="384dc-154">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="384dc-155">Valor</span><span class="sxs-lookup"><span data-stu-id="384dc-155">Value</span></span>|<span data-ttu-id="384dc-156">Descripción</span><span class="sxs-lookup"><span data-stu-id="384dc-156">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="384dc-157">Enumeración</span><span class="sxs-lookup"><span data-stu-id="384dc-157">Enumeration</span></span>|<span data-ttu-id="384dc-158">Uno de los siguientes valores: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="384dc-158">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="384dc-159">De manera predeterminada, es `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="384dc-159">The default is `CurrentUser`.</span></span> <span data-ttu-id="384dc-160">Si la aplicación cliente se está ejecutando bajo una cuenta del sistema, entonces el certificado está normalmente bajo `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="384dc-160">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="384dc-161">Si la aplicación cliente se está ejecutando en una cuenta de usuario, entonces el certificado se encuentra normalmente en `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="384dc-161">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span> <span data-ttu-id="384dc-162">De manera predeterminada, es `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="384dc-162">The default is `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="384dc-163">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="384dc-163">Child Elements</span></span>  
 <span data-ttu-id="384dc-164">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="384dc-164">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="384dc-165">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="384dc-165">Parent Elements</span></span>  
  
|<span data-ttu-id="384dc-166">Elemento</span><span class="sxs-lookup"><span data-stu-id="384dc-166">Element</span></span>|<span data-ttu-id="384dc-167">Descripción</span><span class="sxs-lookup"><span data-stu-id="384dc-167">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="384dc-168">\<peer></span><span class="sxs-lookup"><span data-stu-id="384dc-168">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="384dc-169">Especifica una credencial utilizada para autenticar el cliente a un servicio del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="384dc-169">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="384dc-170">Comentarios</span><span class="sxs-lookup"><span data-stu-id="384dc-170">Remarks</span></span>  
 <span data-ttu-id="384dc-171">Se debe configurar este elemento si se elige la autenticación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="384dc-171">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="384dc-172">Para los canales de salida, cada mensaje se firma utilizando el certificado proporcionado por [ \<certificado >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span><span class="sxs-lookup"><span data-stu-id="384dc-172">For output channels, each message is signed using the certificate provided by [\<certificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span></span> <span data-ttu-id="384dc-173">Todos los mensajes, antes de ser entregados a la aplicación, se comprueban con la credencial de mensaje utilizando el validador especificado por el atributo `customCertificateValidatorType` de este elemento.</span><span class="sxs-lookup"><span data-stu-id="384dc-173">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="384dc-174">El validador puede aceptar o rechazar la credencial.</span><span class="sxs-lookup"><span data-stu-id="384dc-174">The validator can either accept or reject the credential.</span></span>  
  
## <a name="example"></a><span data-ttu-id="384dc-175">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="384dc-175">Example</span></span>  
 <span data-ttu-id="384dc-176">El código siguiente establece el modo de validación del remitente del mensaje en `PeerOrChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="384dc-176">The following code sets the message sender validation mode to `PeerOrChainTrust`.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <peer>
          <certificate findValue="www.contoso.com"
                       storeLocation="LocalMachine"
                       x509FindType="FindByIssuerName" />
          <messageSenderAuthentication certificateValidationMode="PeerOrChainTrust" />
          <messageSenderAuthentication certificateValidationMode="None" />
        </peer>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="384dc-177">Vea también</span><span class="sxs-lookup"><span data-stu-id="384dc-177">See also</span></span>

- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="384dc-178">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="384dc-178">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="384dc-179">Conexión de redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="384dc-179">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="384dc-180">Autenticación del mensaje del canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="384dc-180">Peer Channel Message Authentication</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))
- [<span data-ttu-id="384dc-181">Autenticación personalizada de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="384dc-181">Peer Channel Custom Authentication</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))
- [<span data-ttu-id="384dc-182">Protección de las aplicaciones de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="384dc-182">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
