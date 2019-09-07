---
title: <peerAuthentication> (Elemento)
ms.date: 03/30/2017
ms.assetid: 09a8a9ff-e395-42f6-8ceb-9d44bdc1cbe1
ms.openlocfilehash: 4c29c84a2cc56a890c8273e410ba31b5f3900732
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400081"
---
# <a name="peerauthentication-element"></a><span data-ttu-id="f11a4-102">\<peerAuthentication >, elemento</span><span class="sxs-lookup"><span data-stu-id="f11a4-102">\<peerAuthentication> Element</span></span>
<span data-ttu-id="f11a4-103">Especifica las opciones de autenticación de clientes punto a punto.</span><span class="sxs-lookup"><span data-stu-id="f11a4-103">Specifies authentication options for peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="f11a4-104">Para obtener más información sobre la programación punto a punto, vea [redes punto a punto](../../../wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="f11a4-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
<span data-ttu-id="f11a4-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f11a4-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f11a4-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="f11a4-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f11a4-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="f11a4-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="f11a4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="f11a4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="f11a4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="f11a4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="f11a4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="f11a4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="f11a4-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> del mismo nivel**](peer-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="f11a4-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="f11a4-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> peerAuthentication**</span><span class="sxs-lookup"><span data-stu-id="f11a4-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peerAuthentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f11a4-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f11a4-113">Syntax</span></span>  
  
```xml  
<peerAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                    certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                    revocationMode="NoCheck/Online/Offline"
                    trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f11a4-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f11a4-114">Attributes and Elements</span></span>  
 <span data-ttu-id="f11a4-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f11a4-115">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f11a4-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="f11a4-116">Attributes</span></span>  
  
|<span data-ttu-id="f11a4-117">Atributo</span><span class="sxs-lookup"><span data-stu-id="f11a4-117">Attribute</span></span>|<span data-ttu-id="f11a4-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f11a4-118">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="f11a4-119">Cadena opcional.</span><span class="sxs-lookup"><span data-stu-id="f11a4-119">Optional string.</span></span> <span data-ttu-id="f11a4-120">Tipo y ensamblado utilizados para validar un tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="f11a4-120">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="f11a4-121">Se debe establecer este atributo cuando `certificateValidationMode` está establecido en `Custom`.</span><span class="sxs-lookup"><span data-stu-id="f11a4-121">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="f11a4-122">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="f11a4-122">Optional enumeration.</span></span> <span data-ttu-id="f11a4-123">Especifica uno de los tres modos utilizados para validar las credenciales.</span><span class="sxs-lookup"><span data-stu-id="f11a4-123">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="f11a4-124">Si se establece en `Custom`, también debe proporcionarse un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="f11a4-124">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="f11a4-125">El valor predeterminado es `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="f11a4-125">The default is `ChainTrust`.</span></span>|  
|`revocationMode`|<span data-ttu-id="f11a4-126">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="f11a4-126">Optional enumeration.</span></span> <span data-ttu-id="f11a4-127">Uno de los modos utilizados para comprobar listas de certificados revocadas (CRL).</span><span class="sxs-lookup"><span data-stu-id="f11a4-127">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="f11a4-128">El valor predeterminado es `Online`.</span><span class="sxs-lookup"><span data-stu-id="f11a4-128">The default is `Online`.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="f11a4-129">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="f11a4-129">Optional enumeration.</span></span> <span data-ttu-id="f11a4-130">Una de las dos ubicaciones de almacenamiento del sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="f11a4-130">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="f11a4-131">Se utiliza este valor cuando un certificado del servicio se negocia al cliente.</span><span class="sxs-lookup"><span data-stu-id="f11a4-131">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="f11a4-132">La validación se realiza en el almacén de **personas de confianza** en la ubicación de almacén especificada.</span><span class="sxs-lookup"><span data-stu-id="f11a4-132">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="f11a4-133">El valor predeterminado es `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="f11a4-133">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="f11a4-134">Atributo customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="f11a4-134">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="f11a4-135">Value</span><span class="sxs-lookup"><span data-stu-id="f11a4-135">Value</span></span>|<span data-ttu-id="f11a4-136">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f11a4-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f11a4-137">string</span><span class="sxs-lookup"><span data-stu-id="f11a4-137">String</span></span>|<span data-ttu-id="f11a4-138">Especifica el nombre de tipo y el ensamblado y otros datos utilizados para buscar el tipo.</span><span class="sxs-lookup"><span data-stu-id="f11a4-138">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="f11a4-139">Como mínimo, se requieren un espacio de nombres y un nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="f11a4-139">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="f11a4-140">La información opcionales incluye: nombre de ensamblado, número de versión, referencia cultural y token de clave pública.</span><span class="sxs-lookup"><span data-stu-id="f11a4-140">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="f11a4-141">Atributo certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="f11a4-141">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="f11a4-142">Valor</span><span class="sxs-lookup"><span data-stu-id="f11a4-142">Value</span></span>|<span data-ttu-id="f11a4-143">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f11a4-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f11a4-144">Enumeración</span><span class="sxs-lookup"><span data-stu-id="f11a4-144">Enumeration</span></span>|<span data-ttu-id="f11a4-145">Uno de los siguientes valores: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="f11a4-145">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="f11a4-146">El valor predeterminado es `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="f11a4-146">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="f11a4-147">Para obtener más información, consulte [trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="f11a4-147">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="f11a4-148">Atributo revocationMode</span><span class="sxs-lookup"><span data-stu-id="f11a4-148">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="f11a4-149">Value</span><span class="sxs-lookup"><span data-stu-id="f11a4-149">Value</span></span>|<span data-ttu-id="f11a4-150">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f11a4-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f11a4-151">Enumeración</span><span class="sxs-lookup"><span data-stu-id="f11a4-151">Enumeration</span></span>|<span data-ttu-id="f11a4-152">Uno de los siguientes valores: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="f11a4-152">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="f11a4-153">El valor predeterminado es `Online`.</span><span class="sxs-lookup"><span data-stu-id="f11a4-153">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="f11a4-154">Para obtener más información, consulte [trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="f11a4-154">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="f11a4-155">Atributo trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="f11a4-155">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="f11a4-156">Valor</span><span class="sxs-lookup"><span data-stu-id="f11a4-156">Value</span></span>|<span data-ttu-id="f11a4-157">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f11a4-157">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f11a4-158">Enumeración</span><span class="sxs-lookup"><span data-stu-id="f11a4-158">Enumeration</span></span>|<span data-ttu-id="f11a4-159">Uno de los siguientes valores: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="f11a4-159">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="f11a4-160">El valor predeterminado es `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="f11a4-160">The default is `CurrentUser`.</span></span> <span data-ttu-id="f11a4-161">Si la aplicación cliente se está ejecutando bajo una cuenta del sistema, entonces el certificado está normalmente bajo `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="f11a4-161">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="f11a4-162">Si la aplicación cliente se está ejecutando en una cuenta de usuario, entonces el certificado se encuentra normalmente en `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="f11a4-162">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f11a4-163">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f11a4-163">Child Elements</span></span>  
 <span data-ttu-id="f11a4-164">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f11a4-164">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f11a4-165">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f11a4-165">Parent Elements</span></span>  
  
|<span data-ttu-id="f11a4-166">Elemento</span><span class="sxs-lookup"><span data-stu-id="f11a4-166">Element</span></span>|<span data-ttu-id="f11a4-167">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f11a4-167">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f11a4-168">\<peer></span><span class="sxs-lookup"><span data-stu-id="f11a4-168">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="f11a4-169">Especifica una credencial utilizada para autenticar el cliente a un servicio del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="f11a4-169">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f11a4-170">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f11a4-170">Remarks</span></span>  
 <span data-ttu-id="f11a4-171">El elemento `<authentication>` corresponde a la clase <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>.</span><span class="sxs-lookup"><span data-stu-id="f11a4-171">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="f11a4-172">Este elemento especifica un validador, que se invoca durante la autenticación entre vecinos en la malla.</span><span class="sxs-lookup"><span data-stu-id="f11a4-172">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="f11a4-173">Cuando un nuevo par intenta establecer una conexión de vecino, pasa su propia credencial al par que responde.</span><span class="sxs-lookup"><span data-stu-id="f11a4-173">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="f11a4-174">El validador del contestador se invoca para comprobar la credencial de la parte remota.</span><span class="sxs-lookup"><span data-stu-id="f11a4-174">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="f11a4-175">Cuando una conexión del mismo nivel se establece en la malla, se autentican ambos pares mutuamente, lo que significa que se invocan los validadores en ambos extremos.</span><span class="sxs-lookup"><span data-stu-id="f11a4-175">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f11a4-176">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f11a4-176">Example</span></span>  
 <span data-ttu-id="f11a4-177">El código siguiente establece el modo de validación de certificados en `PeerOrChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="f11a4-177">The following code sets the certificate validation mode to `PeerOrChainTrust`.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <peer>
          <certificate findValue="www.contoso.com"
                       storeLocation="LocalMachine"
                       x509FindType="FindByIssuerName" />
          <peerAuthentication certificateValidationMode="PeerOrChainTrust" />
          <messageSenderAuthentication certificateValidationMode="None" />
        </peer>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="f11a4-178">Vea también</span><span class="sxs-lookup"><span data-stu-id="f11a4-178">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="f11a4-179">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="f11a4-179">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="f11a4-180">Conexión de redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="f11a4-180">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="f11a4-181">[Autenticación de mensajes de canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="f11a4-181">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="f11a4-182">[Autenticación personalizada de canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="f11a4-182">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="f11a4-183">Protección de las aplicaciones de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="f11a4-183">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
