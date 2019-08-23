---
title: Elemento <messageSenderAuthentication>
ms.date: 03/30/2017
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
ms.openlocfilehash: 1e63b6fa93e1abfa87c83da4b5d46f492c59b9bc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931371"
---
# <a name="messagesenderauthentication-element"></a><span data-ttu-id="5ff39-102">\<messageSenderAuthentication >, elemento</span><span class="sxs-lookup"><span data-stu-id="5ff39-102">\<messageSenderAuthentication> element</span></span>
<span data-ttu-id="5ff39-103">Especifica las opciones de autenticación para los remitentes del mensaje punto a punto.</span><span class="sxs-lookup"><span data-stu-id="5ff39-103">Specifies authentication options for peer-to-peer message senders.</span></span>  
  
 <span data-ttu-id="5ff39-104">Para obtener más información sobre la programación punto a punto, vea [redes punto a punto](../../../wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="5ff39-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
 <span data-ttu-id="5ff39-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5ff39-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="5ff39-106">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="5ff39-106">\<behaviors></span></span>  
<span data-ttu-id="5ff39-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="5ff39-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="5ff39-108">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="5ff39-108">\<behavior></span></span>  
<span data-ttu-id="5ff39-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="5ff39-109">\<clientCredentials></span></span>  
<span data-ttu-id="5ff39-110">\<> del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="5ff39-110">\<peer></span></span>  
<span data-ttu-id="5ff39-111">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="5ff39-111">\<messageSenderAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ff39-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5ff39-112">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5ff39-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5ff39-113">Attributes and Elements</span></span>  
 <span data-ttu-id="5ff39-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5ff39-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5ff39-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="5ff39-115">Attributes</span></span>  
  
|<span data-ttu-id="5ff39-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="5ff39-116">Attribute</span></span>|<span data-ttu-id="5ff39-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5ff39-117">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="5ff39-118">Tipo y ensamblado utilizados para validar un tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="5ff39-118">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="5ff39-119">Se debe establecer este atributo cuando `certificateValidationMode` está establecido en `Custom`.</span><span class="sxs-lookup"><span data-stu-id="5ff39-119">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="5ff39-120">Especifica uno de los tres modos utilizados para validar las credenciales.</span><span class="sxs-lookup"><span data-stu-id="5ff39-120">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="5ff39-121">Si se establece en `Custom`, también debe proporcionarse un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="5ff39-121">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`revocationMode`|<span data-ttu-id="5ff39-122">Uno de los modos utilizados para comprobar listas de certificados revocadas (CRL).</span><span class="sxs-lookup"><span data-stu-id="5ff39-122">One of the modes used to check for a revoked certificate lists (CRL).</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="5ff39-123">Una de las dos ubicaciones de almacenamiento del sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="5ff39-123">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="5ff39-124">Se utiliza este valor cuando un certificado del servicio se negocia al cliente.</span><span class="sxs-lookup"><span data-stu-id="5ff39-124">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="5ff39-125">La validación se realiza en el almacén de **personas de confianza** en la ubicación de almacén especificada.</span><span class="sxs-lookup"><span data-stu-id="5ff39-125">Validation is performed against the **Trusted People** store in the specified store location.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="5ff39-126">Atributo customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="5ff39-126">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="5ff39-127">Valor</span><span class="sxs-lookup"><span data-stu-id="5ff39-127">Value</span></span>|<span data-ttu-id="5ff39-128">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5ff39-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5ff39-129">string</span><span class="sxs-lookup"><span data-stu-id="5ff39-129">String</span></span>|<span data-ttu-id="5ff39-130">Opcional.</span><span class="sxs-lookup"><span data-stu-id="5ff39-130">Optional.</span></span> <span data-ttu-id="5ff39-131">Especifica el nombre de tipo y el ensamblado y otros datos utilizados para buscar el tipo.</span><span class="sxs-lookup"><span data-stu-id="5ff39-131">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="5ff39-132">Como mínimo, se requieren un espacio de nombres y un nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="5ff39-132">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="5ff39-133">La información opcionales incluye: nombre de ensamblado, número de versión, referencia cultural y token de clave pública.</span><span class="sxs-lookup"><span data-stu-id="5ff39-133">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="5ff39-134">Atributo certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="5ff39-134">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="5ff39-135">Valor</span><span class="sxs-lookup"><span data-stu-id="5ff39-135">Value</span></span>|<span data-ttu-id="5ff39-136">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5ff39-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5ff39-137">Enumeración</span><span class="sxs-lookup"><span data-stu-id="5ff39-137">Enumeration</span></span>|<span data-ttu-id="5ff39-138">Opcional.</span><span class="sxs-lookup"><span data-stu-id="5ff39-138">Optional.</span></span> <span data-ttu-id="5ff39-139">Uno de los siguientes valores: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="5ff39-139">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="5ff39-140">El valor predeterminado es `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="5ff39-140">The default is `ChainTrust`.</span></span> <span data-ttu-id="5ff39-141">El valor predeterminado es `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="5ff39-141">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="5ff39-142">Para obtener más información, consulte [trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="5ff39-142">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="5ff39-143">Atributo revocationMode</span><span class="sxs-lookup"><span data-stu-id="5ff39-143">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="5ff39-144">Valor</span><span class="sxs-lookup"><span data-stu-id="5ff39-144">Value</span></span>|<span data-ttu-id="5ff39-145">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5ff39-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5ff39-146">Enumeración</span><span class="sxs-lookup"><span data-stu-id="5ff39-146">Enumeration</span></span>|<span data-ttu-id="5ff39-147">Uno de los siguientes valores: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="5ff39-147">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="5ff39-148">El valor predeterminado es `Online`.</span><span class="sxs-lookup"><span data-stu-id="5ff39-148">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="5ff39-149">Para obtener más información, consulte [trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="5ff39-149">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="5ff39-150">Atributo trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="5ff39-150">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="5ff39-151">Value</span><span class="sxs-lookup"><span data-stu-id="5ff39-151">Value</span></span>|<span data-ttu-id="5ff39-152">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5ff39-152">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5ff39-153">Enumeración</span><span class="sxs-lookup"><span data-stu-id="5ff39-153">Enumeration</span></span>|<span data-ttu-id="5ff39-154">Uno de los siguientes valores: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="5ff39-154">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="5ff39-155">El valor predeterminado es `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="5ff39-155">The default is `CurrentUser`.</span></span> <span data-ttu-id="5ff39-156">Si la aplicación cliente se está ejecutando bajo una cuenta del sistema, entonces el certificado está normalmente bajo `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="5ff39-156">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="5ff39-157">Si la aplicación cliente se está ejecutando en una cuenta de usuario, entonces el certificado se encuentra normalmente en `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="5ff39-157">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span> <span data-ttu-id="5ff39-158">El valor predeterminado es `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="5ff39-158">The default is `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5ff39-159">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5ff39-159">Child Elements</span></span>  
 <span data-ttu-id="5ff39-160">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5ff39-160">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5ff39-161">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5ff39-161">Parent Elements</span></span>  
  
|<span data-ttu-id="5ff39-162">Elemento</span><span class="sxs-lookup"><span data-stu-id="5ff39-162">Element</span></span>|<span data-ttu-id="5ff39-163">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5ff39-163">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5ff39-164">\<peer></span><span class="sxs-lookup"><span data-stu-id="5ff39-164">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="5ff39-165">Especifica una credencial utilizada para autenticar el cliente a un servicio del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="5ff39-165">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ff39-166">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5ff39-166">Remarks</span></span>  
 <span data-ttu-id="5ff39-167">Se debe configurar este elemento si se elige la autenticación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="5ff39-167">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="5ff39-168">En el caso de los canales de salida, cada mensaje se firma [ \<](certificate-element.md)con el certificado proporcionado por el > de certificados.</span><span class="sxs-lookup"><span data-stu-id="5ff39-168">For output channels, each message is signed using the certificate provided by [\<certificate>](certificate-element.md).</span></span> <span data-ttu-id="5ff39-169">Todos los mensajes, antes de ser entregados a la aplicación, se comprueban con la credencial de mensaje utilizando el validador especificado por el atributo `customCertificateValidatorType` de este elemento.</span><span class="sxs-lookup"><span data-stu-id="5ff39-169">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="5ff39-170">El validador puede aceptar o rechazar la credencial.</span><span class="sxs-lookup"><span data-stu-id="5ff39-170">The validator can either accept or reject the credential.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ff39-171">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5ff39-171">Example</span></span>  
 <span data-ttu-id="5ff39-172">El código siguiente establece el modo de validación del remitente del mensaje en `PeerOrChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="5ff39-172">The following code sets the message sender validation mode to `PeerOrChainTrust`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5ff39-173">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ff39-173">See also</span></span>

- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="5ff39-174">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="5ff39-174">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="5ff39-175">Conexión de redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="5ff39-175">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="5ff39-176">[Autenticación de mensajes de canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="5ff39-176">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="5ff39-177">[Autenticación personalizada de canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="5ff39-177">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="5ff39-178">Protección de las aplicaciones de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="5ff39-178">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
