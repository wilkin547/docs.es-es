---
title: '&lt;peerAuthentication&gt; (elemento)'
ms.date: 03/30/2017
ms.assetid: 09a8a9ff-e395-42f6-8ceb-9d44bdc1cbe1
ms.openlocfilehash: 4fb8cc4989313afa3ef16c90b54e0feae1ccb71d
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2018
ms.locfileid: "45517559"
---
# <a name="ltpeerauthenticationgt-element"></a><span data-ttu-id="2031f-102">&lt;peerAuthentication&gt; (elemento)</span><span class="sxs-lookup"><span data-stu-id="2031f-102">&lt;peerAuthentication&gt; Element</span></span>
<span data-ttu-id="2031f-103">Especifica las opciones de autenticación de clientes punto a punto.</span><span class="sxs-lookup"><span data-stu-id="2031f-103">Specifies authentication options for peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="2031f-104">Para obtener más información acerca de la programación de punto a punto, vea [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="2031f-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
 <span data-ttu-id="2031f-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2031f-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="2031f-106">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="2031f-106">\<behaviors></span></span>  
<span data-ttu-id="2031f-107">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="2031f-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="2031f-108">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="2031f-108">\<behavior></span></span>  
<span data-ttu-id="2031f-109">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="2031f-109">\<clientCredentials></span></span>  
<span data-ttu-id="2031f-110">\<elemento del mismo nivel ></span><span class="sxs-lookup"><span data-stu-id="2031f-110">\<peer></span></span>  
<span data-ttu-id="2031f-111">\<peerAuthentication ></span><span class="sxs-lookup"><span data-stu-id="2031f-111">\<PeerAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2031f-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2031f-112">Syntax</span></span>  
  
```xml  
<peerAuthentication  
customCertificateValidatorType = "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
revocationMode="NoCheck/Online/Offline"  
trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2031f-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2031f-113">Attributes and Elements</span></span>  
 <span data-ttu-id="2031f-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2031f-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2031f-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="2031f-115">Attributes</span></span>  
  
|<span data-ttu-id="2031f-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="2031f-116">Attribute</span></span>|<span data-ttu-id="2031f-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="2031f-117">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="2031f-118">Cadena opcional.</span><span class="sxs-lookup"><span data-stu-id="2031f-118">Optional string.</span></span> <span data-ttu-id="2031f-119">Tipo y ensamblado utilizados para validar un tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="2031f-119">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="2031f-120">Se debe establecer este atributo cuando `certificateValidationMode` está establecido en `Custom`.</span><span class="sxs-lookup"><span data-stu-id="2031f-120">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certifcateValidationMode`|<span data-ttu-id="2031f-121">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="2031f-121">Optional enumeration.</span></span> <span data-ttu-id="2031f-122">Especifica uno de los tres modos utilizados para validar las credenciales.</span><span class="sxs-lookup"><span data-stu-id="2031f-122">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="2031f-123">Si se establece en `Custom`, también debe proporcionarse un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="2031f-123">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="2031f-124">De manera predeterminada, es `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="2031f-124">The default is `ChainTrust`.</span></span>|  
|`revocationMode`|<span data-ttu-id="2031f-125">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="2031f-125">Optional enumeration.</span></span> <span data-ttu-id="2031f-126">Uno de los modos utilizados para comprobar listas de certificados revocadas (CRL).</span><span class="sxs-lookup"><span data-stu-id="2031f-126">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="2031f-127">De manera predeterminada, es `Online`.</span><span class="sxs-lookup"><span data-stu-id="2031f-127">The default is `Online`.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="2031f-128">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="2031f-128">Optional enumeration.</span></span> <span data-ttu-id="2031f-129">Una de las dos ubicaciones de almacenamiento del sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="2031f-129">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="2031f-130">Se utiliza este valor cuando un certificado del servicio se negocia al cliente.</span><span class="sxs-lookup"><span data-stu-id="2031f-130">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="2031f-131">Se realiza la validación contra el **personas de confianza** almacenar en la ubicación del almacén especificado.</span><span class="sxs-lookup"><span data-stu-id="2031f-131">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="2031f-132">De manera predeterminada, es `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="2031f-132">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="2031f-133">Atributo customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="2031f-133">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="2031f-134">Valor</span><span class="sxs-lookup"><span data-stu-id="2031f-134">Value</span></span>|<span data-ttu-id="2031f-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="2031f-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2031f-136">String</span><span class="sxs-lookup"><span data-stu-id="2031f-136">String</span></span>|<span data-ttu-id="2031f-137">Especifica el nombre de tipo y el ensamblado y otros datos utilizados para buscar el tipo.</span><span class="sxs-lookup"><span data-stu-id="2031f-137">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="2031f-138">Como mínimo, se requieren un espacio de nombres y un nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="2031f-138">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="2031f-139">La información opcionales incluye: nombre de ensamblado, número de versión, referencia cultural y token de clave pública.</span><span class="sxs-lookup"><span data-stu-id="2031f-139">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="2031f-140">Atributo certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="2031f-140">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="2031f-141">Valor</span><span class="sxs-lookup"><span data-stu-id="2031f-141">Value</span></span>|<span data-ttu-id="2031f-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="2031f-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2031f-143">Enumeración</span><span class="sxs-lookup"><span data-stu-id="2031f-143">Enumeration</span></span>|<span data-ttu-id="2031f-144">Uno de los siguientes valores: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="2031f-144">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="2031f-145">De manera predeterminada, es `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="2031f-145">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="2031f-146">Para obtener más información, consulte [trabajar con certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="2031f-146">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="2031f-147">Atributo revocationMode</span><span class="sxs-lookup"><span data-stu-id="2031f-147">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="2031f-148">Valor</span><span class="sxs-lookup"><span data-stu-id="2031f-148">Value</span></span>|<span data-ttu-id="2031f-149">Descripción</span><span class="sxs-lookup"><span data-stu-id="2031f-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2031f-150">Enumeración</span><span class="sxs-lookup"><span data-stu-id="2031f-150">Enumeration</span></span>|<span data-ttu-id="2031f-151">Uno de los siguientes valores: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="2031f-151">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="2031f-152">De manera predeterminada, es `Online`.</span><span class="sxs-lookup"><span data-stu-id="2031f-152">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="2031f-153">Para obtener más información, consulte [trabajar con certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="2031f-153">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="2031f-154">Atributo trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="2031f-154">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="2031f-155">Valor</span><span class="sxs-lookup"><span data-stu-id="2031f-155">Value</span></span>|<span data-ttu-id="2031f-156">Descripción</span><span class="sxs-lookup"><span data-stu-id="2031f-156">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2031f-157">Enumeración</span><span class="sxs-lookup"><span data-stu-id="2031f-157">Enumeration</span></span>|<span data-ttu-id="2031f-158">Uno de los siguientes valores: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="2031f-158">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="2031f-159">De manera predeterminada, es `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="2031f-159">The default is `CurrentUser`.</span></span> <span data-ttu-id="2031f-160">Si la aplicación cliente se está ejecutando bajo una cuenta del sistema, entonces el certificado está normalmente bajo `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="2031f-160">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="2031f-161">Si la aplicación cliente se está ejecutando en una cuenta de usuario, entonces el certificado se encuentra normalmente en `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="2031f-161">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2031f-162">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2031f-162">Child Elements</span></span>  
 <span data-ttu-id="2031f-163">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2031f-163">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2031f-164">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2031f-164">Parent Elements</span></span>  
  
|<span data-ttu-id="2031f-165">Elemento</span><span class="sxs-lookup"><span data-stu-id="2031f-165">Element</span></span>|<span data-ttu-id="2031f-166">Descripción</span><span class="sxs-lookup"><span data-stu-id="2031f-166">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2031f-167">\<elemento del mismo nivel ></span><span class="sxs-lookup"><span data-stu-id="2031f-167">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="2031f-168">Especifica una credencial utilizada para autenticar el cliente a un servicio del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="2031f-168">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2031f-169">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2031f-169">Remarks</span></span>  
 <span data-ttu-id="2031f-170">El elemento `<authentication>` corresponde a la clase <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>.</span><span class="sxs-lookup"><span data-stu-id="2031f-170">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="2031f-171">Este elemento especifica un validador, que se invoca durante la autenticación entre vecinos en la malla.</span><span class="sxs-lookup"><span data-stu-id="2031f-171">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="2031f-172">Cuando un nuevo par intenta establecer una conexión de vecino, pasa su propia credencial al par que responde.</span><span class="sxs-lookup"><span data-stu-id="2031f-172">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="2031f-173">El validador del contestador se invoca para comprobar la credencial de la parte remota.</span><span class="sxs-lookup"><span data-stu-id="2031f-173">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="2031f-174">Cuando una conexión del mismo nivel se establece en la malla, se autentican ambos pares mutuamente, lo que significa que se invocan los validadores en ambos extremos.</span><span class="sxs-lookup"><span data-stu-id="2031f-174">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2031f-175">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2031f-175">Example</span></span>  
 <span data-ttu-id="2031f-176">El código siguiente establece el modo de validación de certificados en `PeerOrChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="2031f-176">The following code sets the certificate validation mode to `PeerOrChainTrust`.</span></span>  
  
```xml  
<behaviors>  
 <endpointBehaviors>  
  <behavior name="MyEndpointBehavior">  
   <clientCredentials>  
    <peer>  
     <certificate findValue="www.contoso.com"   
                   storeLocation="LocalMachine"  
                   x509FindType="FindByIssuerName" />  
     <peerAuthentication   
          certificateValidationMode="PeerOrChainTrust" />  
     <messageSenderAuthentication certificateValidationMode="None" />  
    </peer>  
   </clientCredentials>  
  </behavior>  
</endpointBehaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2031f-177">Vea también</span><span class="sxs-lookup"><span data-stu-id="2031f-177">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>  
 <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>  
 [<span data-ttu-id="2031f-178">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="2031f-178">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="2031f-179">Conexión de redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="2031f-179">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="2031f-180">Autenticación de mensajes del canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="2031f-180">Peer Channel Message Authentication</span></span>](https://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="2031f-181">Canal del mismo nivel de autenticación personalizada</span><span class="sxs-lookup"><span data-stu-id="2031f-181">Peer Channel Custom Authentication</span></span>](https://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="2031f-182">Protección de las aplicaciones de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="2031f-182">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
