---
title: '&lt;peerAuthentication&gt; (elemento)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 09a8a9ff-e395-42f6-8ceb-9d44bdc1cbe1
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3cc625f5fdb20505f2e36c5a2d37fca0676bbb37
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltpeerauthenticationgt-element"></a><span data-ttu-id="78570-102">&lt;peerAuthentication&gt; (elemento)</span><span class="sxs-lookup"><span data-stu-id="78570-102">&lt;peerAuthentication&gt; Element</span></span>
<span data-ttu-id="78570-103">Especifica las opciones de autenticación de clientes punto a punto.</span><span class="sxs-lookup"><span data-stu-id="78570-103">Specifies authentication options for peer-to-peer clients.</span></span>  
  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)]<span data-ttu-id="78570-104">Peer-to-peer programación, vea [redes Peer-to-Peer](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="78570-104"> peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
 <span data-ttu-id="78570-105">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="78570-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="78570-106">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="78570-106">\<behaviors></span></span>  
<span data-ttu-id="78570-107">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="78570-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="78570-108">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="78570-108">\<behavior></span></span>  
<span data-ttu-id="78570-109">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="78570-109">\<clientCredentials></span></span>  
<span data-ttu-id="78570-110">\<punto ></span><span class="sxs-lookup"><span data-stu-id="78570-110">\<peer></span></span>  
<span data-ttu-id="78570-111">\<PeerAuthentication ></span><span class="sxs-lookup"><span data-stu-id="78570-111">\<PeerAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78570-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="78570-112">Syntax</span></span>  
  
```xml  
<peerAuthentication  
customCertificateValidatorType = "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
revocationMode="NoCheck/Online/Offline"  
trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="78570-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="78570-113">Attributes and Elements</span></span>  
 <span data-ttu-id="78570-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="78570-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="78570-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="78570-115">Attributes</span></span>  
  
|<span data-ttu-id="78570-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="78570-116">Attribute</span></span>|<span data-ttu-id="78570-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="78570-117">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="78570-118">Cadena opcional.</span><span class="sxs-lookup"><span data-stu-id="78570-118">Optional string.</span></span> <span data-ttu-id="78570-119">Tipo y ensamblado utilizados para validar un tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="78570-119">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="78570-120">Se debe establecer este atributo cuando `certificateValidationMode` está establecido en `Custom`.</span><span class="sxs-lookup"><span data-stu-id="78570-120">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certifcateValidationMode`|<span data-ttu-id="78570-121">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="78570-121">Optional enumeration.</span></span> <span data-ttu-id="78570-122">Especifica uno de los tres modos utilizados para validar las credenciales.</span><span class="sxs-lookup"><span data-stu-id="78570-122">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="78570-123">Si se establece en `Custom`, también debe proporcionarse un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="78570-123">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="78570-124">De manera predeterminada, es `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="78570-124">The default is `ChainTrust`.</span></span>|  
|`revocationMode`|<span data-ttu-id="78570-125">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="78570-125">Optional enumeration.</span></span> <span data-ttu-id="78570-126">Uno de los modos utilizados para comprobar listas de certificados revocadas (CRL).</span><span class="sxs-lookup"><span data-stu-id="78570-126">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="78570-127">De manera predeterminada, es `Online`.</span><span class="sxs-lookup"><span data-stu-id="78570-127">The default is `Online`.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="78570-128">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="78570-128">Optional enumeration.</span></span> <span data-ttu-id="78570-129">Una de las dos ubicaciones de almacenamiento del sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="78570-129">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="78570-130">Se utiliza este valor cuando un certificado del servicio se negocia al cliente.</span><span class="sxs-lookup"><span data-stu-id="78570-130">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="78570-131">Validación se realiza contra el **personas de confianza** almacenar en la ubicación del almacén especificado.</span><span class="sxs-lookup"><span data-stu-id="78570-131">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="78570-132">De manera predeterminada, es `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="78570-132">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="78570-133">Atributo customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="78570-133">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="78570-134">Valor</span><span class="sxs-lookup"><span data-stu-id="78570-134">Value</span></span>|<span data-ttu-id="78570-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="78570-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="78570-136">String</span><span class="sxs-lookup"><span data-stu-id="78570-136">String</span></span>|<span data-ttu-id="78570-137">Especifica el nombre de tipo y el ensamblado y otros datos utilizados para buscar el tipo.</span><span class="sxs-lookup"><span data-stu-id="78570-137">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="78570-138">Como mínimo, se requieren un espacio de nombres y un nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="78570-138">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="78570-139">La información opcionales incluye: nombre de ensamblado, número de versión, referencia cultural y token de clave pública.</span><span class="sxs-lookup"><span data-stu-id="78570-139">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="78570-140">Atributo certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="78570-140">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="78570-141">Valor</span><span class="sxs-lookup"><span data-stu-id="78570-141">Value</span></span>|<span data-ttu-id="78570-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="78570-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="78570-143">Enumeración</span><span class="sxs-lookup"><span data-stu-id="78570-143">Enumeration</span></span>|<span data-ttu-id="78570-144">Uno de los siguientes valores: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="78570-144">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="78570-145">De manera predeterminada, es `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="78570-145">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="78570-146">Para obtener más información, consulte [trabajar con certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="78570-146">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="78570-147">Atributo revocationMode</span><span class="sxs-lookup"><span data-stu-id="78570-147">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="78570-148">Valor</span><span class="sxs-lookup"><span data-stu-id="78570-148">Value</span></span>|<span data-ttu-id="78570-149">Descripción</span><span class="sxs-lookup"><span data-stu-id="78570-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="78570-150">Enumeración</span><span class="sxs-lookup"><span data-stu-id="78570-150">Enumeration</span></span>|<span data-ttu-id="78570-151">Uno de los siguientes valores: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="78570-151">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="78570-152">De manera predeterminada, es `Online`.</span><span class="sxs-lookup"><span data-stu-id="78570-152">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="78570-153">Para obtener más información, consulte [trabajar con certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="78570-153">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="78570-154">Atributo trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="78570-154">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="78570-155">Valor</span><span class="sxs-lookup"><span data-stu-id="78570-155">Value</span></span>|<span data-ttu-id="78570-156">Descripción</span><span class="sxs-lookup"><span data-stu-id="78570-156">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="78570-157">Enumeración</span><span class="sxs-lookup"><span data-stu-id="78570-157">Enumeration</span></span>|<span data-ttu-id="78570-158">Uno de los siguientes valores: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="78570-158">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="78570-159">De manera predeterminada, es `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="78570-159">The default is `CurrentUser`.</span></span> <span data-ttu-id="78570-160">Si la aplicación cliente se está ejecutando bajo una cuenta del sistema, entonces el certificado está normalmente bajo `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="78570-160">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="78570-161">Si la aplicación cliente se está ejecutando en una cuenta de usuario, entonces el certificado se encuentra normalmente en `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="78570-161">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="78570-162">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="78570-162">Child Elements</span></span>  
 <span data-ttu-id="78570-163">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="78570-163">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="78570-164">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="78570-164">Parent Elements</span></span>  
  
|<span data-ttu-id="78570-165">Elemento</span><span class="sxs-lookup"><span data-stu-id="78570-165">Element</span></span>|<span data-ttu-id="78570-166">Descripción</span><span class="sxs-lookup"><span data-stu-id="78570-166">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="78570-167">\<punto ></span><span class="sxs-lookup"><span data-stu-id="78570-167">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="78570-168">Especifica una credencial utilizada para autenticar el cliente a un servicio del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="78570-168">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78570-169">Comentarios</span><span class="sxs-lookup"><span data-stu-id="78570-169">Remarks</span></span>  
 <span data-ttu-id="78570-170">El elemento `<authentication>` corresponde a la clase <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>.</span><span class="sxs-lookup"><span data-stu-id="78570-170">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="78570-171">Este elemento especifica un validador, que se invoca durante la autenticación entre vecinos en la malla.</span><span class="sxs-lookup"><span data-stu-id="78570-171">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="78570-172">Cuando un nuevo par intenta establecer una conexión de vecino, pasa su propia credencial al par que responde.</span><span class="sxs-lookup"><span data-stu-id="78570-172">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="78570-173">El validador del contestador se invoca para comprobar la credencial de la parte remota.</span><span class="sxs-lookup"><span data-stu-id="78570-173">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="78570-174">Cuando una conexión del mismo nivel se establece en la malla, se autentican ambos pares mutuamente, lo que significa que se invocan los validadores en ambos extremos.</span><span class="sxs-lookup"><span data-stu-id="78570-174">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78570-175">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="78570-175">Example</span></span>  
 <span data-ttu-id="78570-176">El código siguiente establece el modo de validación de certificados en `PeerOrChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="78570-176">The following code sets the certificate validation mode to `PeerOrChainTrust`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="78570-177">Vea también</span><span class="sxs-lookup"><span data-stu-id="78570-177">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>  
 <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>  
 [<span data-ttu-id="78570-178">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="78570-178">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="78570-179">Redes de punto a punto</span><span class="sxs-lookup"><span data-stu-id="78570-179">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="78570-180">Autenticación de mensajes del canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="78570-180">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="78570-181">Canal del mismo nivel de autenticación personalizada</span><span class="sxs-lookup"><span data-stu-id="78570-181">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="78570-182">Proteger las aplicaciones de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="78570-182">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
