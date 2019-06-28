---
title: Elemento <messageSenderAuthentication>
ms.date: 03/30/2017
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
ms.openlocfilehash: 804c280bcdb0fecc87f71121b7d95b5fd0268de9
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423123"
---
# <a name="messagesenderauthentication-element"></a><span data-ttu-id="a581c-102">\<messageSenderAuthentication > elemento</span><span class="sxs-lookup"><span data-stu-id="a581c-102">\<messageSenderAuthentication> element</span></span>
<span data-ttu-id="a581c-103">Especifica las opciones de autenticación para los remitentes del mensaje punto a punto.</span><span class="sxs-lookup"><span data-stu-id="a581c-103">Specifies authentication options for peer-to-peer message senders.</span></span>  
  
 <span data-ttu-id="a581c-104">Para obtener más información acerca de la programación de punto a punto, vea [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="a581c-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
 <span data-ttu-id="a581c-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a581c-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="a581c-106">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="a581c-106">\<behaviors></span></span>  
<span data-ttu-id="a581c-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="a581c-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="a581c-108">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="a581c-108">\<behavior></span></span>  
<span data-ttu-id="a581c-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="a581c-109">\<clientCredentials></span></span>  
<span data-ttu-id="a581c-110">\<peer></span><span class="sxs-lookup"><span data-stu-id="a581c-110">\<peer></span></span>  
<span data-ttu-id="a581c-111">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="a581c-111">\<messageSenderAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a581c-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a581c-112">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a581c-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a581c-113">Attributes and Elements</span></span>  
 <span data-ttu-id="a581c-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a581c-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a581c-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="a581c-115">Attributes</span></span>  
  
|<span data-ttu-id="a581c-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="a581c-116">Attribute</span></span>|<span data-ttu-id="a581c-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="a581c-117">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="a581c-118">Tipo y ensamblado utilizados para validar un tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="a581c-118">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="a581c-119">Se debe establecer este atributo cuando `certificateValidationMode` está establecido en `Custom`.</span><span class="sxs-lookup"><span data-stu-id="a581c-119">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="a581c-120">Especifica uno de los tres modos utilizados para validar las credenciales.</span><span class="sxs-lookup"><span data-stu-id="a581c-120">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="a581c-121">Si se establece en `Custom`, también debe proporcionarse un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="a581c-121">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`revocationMode`|<span data-ttu-id="a581c-122">Uno de los modos utilizados para comprobar listas de certificados revocadas (CRL).</span><span class="sxs-lookup"><span data-stu-id="a581c-122">One of the modes used to check for a revoked certificate lists (CRL).</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="a581c-123">Una de las dos ubicaciones de almacenamiento del sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="a581c-123">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="a581c-124">Se utiliza este valor cuando un certificado del servicio se negocia al cliente.</span><span class="sxs-lookup"><span data-stu-id="a581c-124">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="a581c-125">Se realiza la validación contra el **personas de confianza** almacenar en la ubicación del almacén especificado.</span><span class="sxs-lookup"><span data-stu-id="a581c-125">Validation is performed against the **Trusted People** store in the specified store location.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="a581c-126">Atributo customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="a581c-126">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="a581c-127">Valor</span><span class="sxs-lookup"><span data-stu-id="a581c-127">Value</span></span>|<span data-ttu-id="a581c-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="a581c-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a581c-129">String</span><span class="sxs-lookup"><span data-stu-id="a581c-129">String</span></span>|<span data-ttu-id="a581c-130">Opcional.</span><span class="sxs-lookup"><span data-stu-id="a581c-130">Optional.</span></span> <span data-ttu-id="a581c-131">Especifica el nombre de tipo y el ensamblado y otros datos utilizados para buscar el tipo.</span><span class="sxs-lookup"><span data-stu-id="a581c-131">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="a581c-132">Como mínimo, se requieren un espacio de nombres y un nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="a581c-132">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="a581c-133">La información opcionales incluye: nombre de ensamblado, número de versión, referencia cultural y token de clave pública.</span><span class="sxs-lookup"><span data-stu-id="a581c-133">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="a581c-134">Atributo certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="a581c-134">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="a581c-135">Valor</span><span class="sxs-lookup"><span data-stu-id="a581c-135">Value</span></span>|<span data-ttu-id="a581c-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="a581c-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a581c-137">Enumeración</span><span class="sxs-lookup"><span data-stu-id="a581c-137">Enumeration</span></span>|<span data-ttu-id="a581c-138">Opcional.</span><span class="sxs-lookup"><span data-stu-id="a581c-138">Optional.</span></span> <span data-ttu-id="a581c-139">Uno de los siguientes valores: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="a581c-139">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="a581c-140">De manera predeterminada, es `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="a581c-140">The default is `ChainTrust`.</span></span> <span data-ttu-id="a581c-141">De manera predeterminada, es `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="a581c-141">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="a581c-142">Para obtener más información, consulte [trabajar con certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="a581c-142">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="a581c-143">Atributo revocationMode</span><span class="sxs-lookup"><span data-stu-id="a581c-143">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="a581c-144">Valor</span><span class="sxs-lookup"><span data-stu-id="a581c-144">Value</span></span>|<span data-ttu-id="a581c-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="a581c-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a581c-146">Enumeración</span><span class="sxs-lookup"><span data-stu-id="a581c-146">Enumeration</span></span>|<span data-ttu-id="a581c-147">Uno de los siguientes valores: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="a581c-147">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="a581c-148">De manera predeterminada, es `Online`.</span><span class="sxs-lookup"><span data-stu-id="a581c-148">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="a581c-149">Para obtener más información, consulte [trabajar con certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="a581c-149">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="a581c-150">Atributo trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="a581c-150">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="a581c-151">Valor</span><span class="sxs-lookup"><span data-stu-id="a581c-151">Value</span></span>|<span data-ttu-id="a581c-152">Descripción</span><span class="sxs-lookup"><span data-stu-id="a581c-152">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a581c-153">Enumeración</span><span class="sxs-lookup"><span data-stu-id="a581c-153">Enumeration</span></span>|<span data-ttu-id="a581c-154">Uno de los siguientes valores: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="a581c-154">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="a581c-155">De manera predeterminada, es `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="a581c-155">The default is `CurrentUser`.</span></span> <span data-ttu-id="a581c-156">Si la aplicación cliente se está ejecutando bajo una cuenta del sistema, entonces el certificado está normalmente bajo `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="a581c-156">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="a581c-157">Si la aplicación cliente se está ejecutando en una cuenta de usuario, entonces el certificado se encuentra normalmente en `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="a581c-157">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span> <span data-ttu-id="a581c-158">De manera predeterminada, es `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="a581c-158">The default is `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a581c-159">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a581c-159">Child Elements</span></span>  
 <span data-ttu-id="a581c-160">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a581c-160">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a581c-161">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a581c-161">Parent Elements</span></span>  
  
|<span data-ttu-id="a581c-162">Elemento</span><span class="sxs-lookup"><span data-stu-id="a581c-162">Element</span></span>|<span data-ttu-id="a581c-163">Descripción</span><span class="sxs-lookup"><span data-stu-id="a581c-163">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a581c-164">\<peer></span><span class="sxs-lookup"><span data-stu-id="a581c-164">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="a581c-165">Especifica una credencial utilizada para autenticar el cliente a un servicio del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="a581c-165">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a581c-166">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a581c-166">Remarks</span></span>  
 <span data-ttu-id="a581c-167">Se debe configurar este elemento si se elige la autenticación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="a581c-167">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="a581c-168">Para los canales de salida, cada mensaje se firma utilizando el certificado proporcionado por [ \<certificado >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span><span class="sxs-lookup"><span data-stu-id="a581c-168">For output channels, each message is signed using the certificate provided by [\<certificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span></span> <span data-ttu-id="a581c-169">Todos los mensajes, antes de ser entregados a la aplicación, se comprueban con la credencial de mensaje utilizando el validador especificado por el atributo `customCertificateValidatorType` de este elemento.</span><span class="sxs-lookup"><span data-stu-id="a581c-169">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="a581c-170">El validador puede aceptar o rechazar la credencial.</span><span class="sxs-lookup"><span data-stu-id="a581c-170">The validator can either accept or reject the credential.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a581c-171">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a581c-171">Example</span></span>  
 <span data-ttu-id="a581c-172">El código siguiente establece el modo de validación del remitente del mensaje en `PeerOrChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="a581c-172">The following code sets the message sender validation mode to `PeerOrChainTrust`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a581c-173">Vea también</span><span class="sxs-lookup"><span data-stu-id="a581c-173">See also</span></span>

- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="a581c-174">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="a581c-174">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="a581c-175">Conexión de redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="a581c-175">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="a581c-176">[Autenticación de mensajes del canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="a581c-176">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="a581c-177">[Canal del mismo nivel de autenticación personalizada](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="a581c-177">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="a581c-178">Protección de las aplicaciones de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="a581c-178">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
