---
title: Elemento <messageSenderAuthentication>
ms.date: 03/30/2017
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
ms.openlocfilehash: bab0e50d7feba3ea55d505be07cfa41427a5cbbc
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397785"
---
# <a name="messagesenderauthentication-element"></a><span data-ttu-id="94ade-102">\<messageSenderAuthentication >, elemento</span><span class="sxs-lookup"><span data-stu-id="94ade-102">\<messageSenderAuthentication> element</span></span>
<span data-ttu-id="94ade-103">Especifica las opciones de autenticación para los remitentes del mensaje punto a punto.</span><span class="sxs-lookup"><span data-stu-id="94ade-103">Specifies authentication options for peer-to-peer message senders.</span></span>  
  
 <span data-ttu-id="94ade-104">Para obtener más información sobre la programación punto a punto, vea [redes punto a punto](../../../wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="94ade-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
<span data-ttu-id="94ade-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="94ade-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="94ade-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="94ade-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="94ade-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="94ade-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="94ade-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="94ade-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="94ade-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="94ade-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="94ade-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="94ade-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="94ade-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> del mismo nivel**](peer-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="94ade-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="94ade-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> messageSenderAuthentication**</span><span class="sxs-lookup"><span data-stu-id="94ade-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<messageSenderAuthentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94ade-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="94ade-113">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="94ade-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="94ade-114">Attributes and Elements</span></span>  
 <span data-ttu-id="94ade-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="94ade-115">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="94ade-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="94ade-116">Attributes</span></span>  
  
|<span data-ttu-id="94ade-117">Atributo</span><span class="sxs-lookup"><span data-stu-id="94ade-117">Attribute</span></span>|<span data-ttu-id="94ade-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="94ade-118">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="94ade-119">Tipo y ensamblado utilizados para validar un tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="94ade-119">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="94ade-120">Se debe establecer este atributo cuando `certificateValidationMode` está establecido en `Custom`.</span><span class="sxs-lookup"><span data-stu-id="94ade-120">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="94ade-121">Especifica uno de los tres modos utilizados para validar las credenciales.</span><span class="sxs-lookup"><span data-stu-id="94ade-121">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="94ade-122">Si se establece en `Custom`, también debe proporcionarse un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="94ade-122">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`revocationMode`|<span data-ttu-id="94ade-123">Uno de los modos utilizados para comprobar listas de certificados revocadas (CRL).</span><span class="sxs-lookup"><span data-stu-id="94ade-123">One of the modes used to check for a revoked certificate lists (CRL).</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="94ade-124">Una de las dos ubicaciones de almacenamiento del sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="94ade-124">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="94ade-125">Se utiliza este valor cuando un certificado del servicio se negocia al cliente.</span><span class="sxs-lookup"><span data-stu-id="94ade-125">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="94ade-126">La validación se realiza en el almacén de **personas de confianza** en la ubicación de almacén especificada.</span><span class="sxs-lookup"><span data-stu-id="94ade-126">Validation is performed against the **Trusted People** store in the specified store location.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="94ade-127">Atributo customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="94ade-127">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="94ade-128">Value</span><span class="sxs-lookup"><span data-stu-id="94ade-128">Value</span></span>|<span data-ttu-id="94ade-129">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="94ade-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="94ade-130">string</span><span class="sxs-lookup"><span data-stu-id="94ade-130">String</span></span>|<span data-ttu-id="94ade-131">Opcional.</span><span class="sxs-lookup"><span data-stu-id="94ade-131">Optional.</span></span> <span data-ttu-id="94ade-132">Especifica el nombre de tipo y el ensamblado y otros datos utilizados para buscar el tipo.</span><span class="sxs-lookup"><span data-stu-id="94ade-132">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="94ade-133">Como mínimo, se requieren un espacio de nombres y un nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="94ade-133">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="94ade-134">La información opcionales incluye: nombre de ensamblado, número de versión, referencia cultural y token de clave pública.</span><span class="sxs-lookup"><span data-stu-id="94ade-134">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="94ade-135">Atributo certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="94ade-135">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="94ade-136">Valor</span><span class="sxs-lookup"><span data-stu-id="94ade-136">Value</span></span>|<span data-ttu-id="94ade-137">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="94ade-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="94ade-138">Enumeración</span><span class="sxs-lookup"><span data-stu-id="94ade-138">Enumeration</span></span>|<span data-ttu-id="94ade-139">Opcional.</span><span class="sxs-lookup"><span data-stu-id="94ade-139">Optional.</span></span> <span data-ttu-id="94ade-140">Uno de los siguientes valores: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="94ade-140">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="94ade-141">El valor predeterminado es `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="94ade-141">The default is `ChainTrust`.</span></span> <span data-ttu-id="94ade-142">El valor predeterminado es `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="94ade-142">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="94ade-143">Para obtener más información, consulte [trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="94ade-143">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="94ade-144">Atributo revocationMode</span><span class="sxs-lookup"><span data-stu-id="94ade-144">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="94ade-145">Value</span><span class="sxs-lookup"><span data-stu-id="94ade-145">Value</span></span>|<span data-ttu-id="94ade-146">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="94ade-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="94ade-147">Enumeración</span><span class="sxs-lookup"><span data-stu-id="94ade-147">Enumeration</span></span>|<span data-ttu-id="94ade-148">Uno de los siguientes valores: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="94ade-148">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="94ade-149">El valor predeterminado es `Online`.</span><span class="sxs-lookup"><span data-stu-id="94ade-149">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="94ade-150">Para obtener más información, consulte [trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="94ade-150">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="94ade-151">Atributo trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="94ade-151">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="94ade-152">Value</span><span class="sxs-lookup"><span data-stu-id="94ade-152">Value</span></span>|<span data-ttu-id="94ade-153">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="94ade-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="94ade-154">Enumeración</span><span class="sxs-lookup"><span data-stu-id="94ade-154">Enumeration</span></span>|<span data-ttu-id="94ade-155">Uno de los siguientes valores: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="94ade-155">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="94ade-156">El valor predeterminado es `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="94ade-156">The default is `CurrentUser`.</span></span> <span data-ttu-id="94ade-157">Si la aplicación cliente se está ejecutando bajo una cuenta del sistema, entonces el certificado está normalmente bajo `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="94ade-157">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="94ade-158">Si la aplicación cliente se está ejecutando en una cuenta de usuario, entonces el certificado se encuentra normalmente en `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="94ade-158">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span> <span data-ttu-id="94ade-159">El valor predeterminado es `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="94ade-159">The default is `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="94ade-160">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="94ade-160">Child Elements</span></span>  
 <span data-ttu-id="94ade-161">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="94ade-161">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="94ade-162">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="94ade-162">Parent Elements</span></span>  
  
|<span data-ttu-id="94ade-163">Elemento</span><span class="sxs-lookup"><span data-stu-id="94ade-163">Element</span></span>|<span data-ttu-id="94ade-164">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="94ade-164">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="94ade-165">\<peer></span><span class="sxs-lookup"><span data-stu-id="94ade-165">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="94ade-166">Especifica una credencial utilizada para autenticar el cliente a un servicio del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="94ade-166">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94ade-167">Comentarios</span><span class="sxs-lookup"><span data-stu-id="94ade-167">Remarks</span></span>  
 <span data-ttu-id="94ade-168">Se debe configurar este elemento si se elige la autenticación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="94ade-168">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="94ade-169">En el caso de los canales de salida, cada mensaje se firma [ \<](certificate-element.md)con el certificado proporcionado por el > de certificados.</span><span class="sxs-lookup"><span data-stu-id="94ade-169">For output channels, each message is signed using the certificate provided by [\<certificate>](certificate-element.md).</span></span> <span data-ttu-id="94ade-170">Todos los mensajes, antes de ser entregados a la aplicación, se comprueban con la credencial de mensaje utilizando el validador especificado por el atributo `customCertificateValidatorType` de este elemento.</span><span class="sxs-lookup"><span data-stu-id="94ade-170">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="94ade-171">El validador puede aceptar o rechazar la credencial.</span><span class="sxs-lookup"><span data-stu-id="94ade-171">The validator can either accept or reject the credential.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94ade-172">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="94ade-172">Example</span></span>  
 <span data-ttu-id="94ade-173">El código siguiente establece el modo de validación del remitente del mensaje en `PeerOrChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="94ade-173">The following code sets the message sender validation mode to `PeerOrChainTrust`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="94ade-174">Vea también</span><span class="sxs-lookup"><span data-stu-id="94ade-174">See also</span></span>

- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="94ade-175">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="94ade-175">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="94ade-176">Conexión de redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="94ade-176">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="94ade-177">[Autenticación de mensajes de canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="94ade-177">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="94ade-178">[Autenticación personalizada de canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="94ade-178">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="94ade-179">Protección de las aplicaciones de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="94ade-179">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
