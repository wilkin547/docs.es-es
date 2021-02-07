---
description: 'Más información acerca de: <peerAuthentication> elemento'
title: <peerAuthentication> (Elemento)
ms.date: 03/30/2017
ms.assetid: 09a8a9ff-e395-42f6-8ceb-9d44bdc1cbe1
ms.openlocfilehash: 887b65a4a2a7da9d545bc25636be0ea6c646f6fb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683728"
---
# <a name="peerauthentication-element"></a><span data-ttu-id="26e8b-103">\<peerAuthentication> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="26e8b-103">\<peerAuthentication> Element</span></span>

<span data-ttu-id="26e8b-104">Especifica las opciones de autenticación de clientes punto a punto.</span><span class="sxs-lookup"><span data-stu-id="26e8b-104">Specifies authentication options for peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="26e8b-105">Para obtener más información sobre la programación punto a punto, vea [redes punto a punto](../../../wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="26e8b-105">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peerAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="26e8b-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="26e8b-106">Syntax</span></span>  
  
```xml  
<peerAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                    certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                    revocationMode="NoCheck/Online/Offline"
                    trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="26e8b-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="26e8b-107">Attributes and Elements</span></span>  

 <span data-ttu-id="26e8b-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="26e8b-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="26e8b-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="26e8b-109">Attributes</span></span>  
  
|<span data-ttu-id="26e8b-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="26e8b-110">Attribute</span></span>|<span data-ttu-id="26e8b-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="26e8b-111">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="26e8b-112">Cadena opcional.</span><span class="sxs-lookup"><span data-stu-id="26e8b-112">Optional string.</span></span> <span data-ttu-id="26e8b-113">Tipo y ensamblado utilizados para validar un tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="26e8b-113">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="26e8b-114">Se debe establecer este atributo cuando `certificateValidationMode` está establecido en `Custom`.</span><span class="sxs-lookup"><span data-stu-id="26e8b-114">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="26e8b-115">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="26e8b-115">Optional enumeration.</span></span> <span data-ttu-id="26e8b-116">Especifica uno de los tres modos utilizados para validar las credenciales.</span><span class="sxs-lookup"><span data-stu-id="26e8b-116">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="26e8b-117">Si se establece en `Custom`, también debe proporcionarse un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="26e8b-117">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="26e8b-118">De manera predeterminada, es `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="26e8b-118">The default is `ChainTrust`.</span></span>|  
|`revocationMode`|<span data-ttu-id="26e8b-119">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="26e8b-119">Optional enumeration.</span></span> <span data-ttu-id="26e8b-120">Uno de los modos utilizados para comprobar listas de certificados revocadas (CRL).</span><span class="sxs-lookup"><span data-stu-id="26e8b-120">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="26e8b-121">De manera predeterminada, es `Online`.</span><span class="sxs-lookup"><span data-stu-id="26e8b-121">The default is `Online`.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="26e8b-122">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="26e8b-122">Optional enumeration.</span></span> <span data-ttu-id="26e8b-123">Una de las dos ubicaciones de almacenamiento del sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="26e8b-123">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="26e8b-124">Se utiliza este valor cuando un certificado del servicio se negocia al cliente.</span><span class="sxs-lookup"><span data-stu-id="26e8b-124">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="26e8b-125">La validación se realiza en el almacén de **personas de confianza** en la ubicación de almacén especificada.</span><span class="sxs-lookup"><span data-stu-id="26e8b-125">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="26e8b-126">De manera predeterminada, es `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="26e8b-126">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="26e8b-127">Atributo customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="26e8b-127">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="26e8b-128">Value</span><span class="sxs-lookup"><span data-stu-id="26e8b-128">Value</span></span>|<span data-ttu-id="26e8b-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="26e8b-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="26e8b-130">String</span><span class="sxs-lookup"><span data-stu-id="26e8b-130">String</span></span>|<span data-ttu-id="26e8b-131">Especifica el nombre de tipo y el ensamblado y otros datos utilizados para buscar el tipo.</span><span class="sxs-lookup"><span data-stu-id="26e8b-131">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="26e8b-132">Como mínimo, se requieren un espacio de nombres y un nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="26e8b-132">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="26e8b-133">La información opcionales incluye: nombre de ensamblado, número de versión, referencia cultural y token de clave pública.</span><span class="sxs-lookup"><span data-stu-id="26e8b-133">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="26e8b-134">Atributo certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="26e8b-134">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="26e8b-135">Value</span><span class="sxs-lookup"><span data-stu-id="26e8b-135">Value</span></span>|<span data-ttu-id="26e8b-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="26e8b-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="26e8b-137">Enumeración</span><span class="sxs-lookup"><span data-stu-id="26e8b-137">Enumeration</span></span>|<span data-ttu-id="26e8b-138">Uno de los siguientes valores: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="26e8b-138">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="26e8b-139">De manera predeterminada, es `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="26e8b-139">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="26e8b-140">Para obtener más información, consulte [trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="26e8b-140">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="26e8b-141">Atributo revocationMode</span><span class="sxs-lookup"><span data-stu-id="26e8b-141">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="26e8b-142">Value</span><span class="sxs-lookup"><span data-stu-id="26e8b-142">Value</span></span>|<span data-ttu-id="26e8b-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="26e8b-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="26e8b-144">Enumeración</span><span class="sxs-lookup"><span data-stu-id="26e8b-144">Enumeration</span></span>|<span data-ttu-id="26e8b-145">Uno de los siguientes valores: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="26e8b-145">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="26e8b-146">De manera predeterminada, es `Online`.</span><span class="sxs-lookup"><span data-stu-id="26e8b-146">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="26e8b-147">Para obtener más información, consulte [trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="26e8b-147">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="26e8b-148">Atributo trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="26e8b-148">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="26e8b-149">Value</span><span class="sxs-lookup"><span data-stu-id="26e8b-149">Value</span></span>|<span data-ttu-id="26e8b-150">Descripción</span><span class="sxs-lookup"><span data-stu-id="26e8b-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="26e8b-151">Enumeración</span><span class="sxs-lookup"><span data-stu-id="26e8b-151">Enumeration</span></span>|<span data-ttu-id="26e8b-152">Puede ser uno de los siguientes valores: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="26e8b-152">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="26e8b-153">De manera predeterminada, es `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="26e8b-153">The default is `CurrentUser`.</span></span> <span data-ttu-id="26e8b-154">Si la aplicación cliente se está ejecutando bajo una cuenta del sistema, entonces el certificado está normalmente bajo `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="26e8b-154">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="26e8b-155">Si la aplicación cliente se está ejecutando en una cuenta de usuario, entonces el certificado se encuentra normalmente en `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="26e8b-155">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="26e8b-156">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="26e8b-156">Child Elements</span></span>  

 <span data-ttu-id="26e8b-157">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="26e8b-157">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="26e8b-158">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="26e8b-158">Parent Elements</span></span>  
  
|<span data-ttu-id="26e8b-159">Elemento</span><span class="sxs-lookup"><span data-stu-id="26e8b-159">Element</span></span>|<span data-ttu-id="26e8b-160">Descripción</span><span class="sxs-lookup"><span data-stu-id="26e8b-160">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-clientcredentials-element.md)|<span data-ttu-id="26e8b-161">Especifica una credencial utilizada para autenticar el cliente a un servicio del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="26e8b-161">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="26e8b-162">Observaciones</span><span class="sxs-lookup"><span data-stu-id="26e8b-162">Remarks</span></span>  

 <span data-ttu-id="26e8b-163">El elemento `<authentication>` corresponde a la clase <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>.</span><span class="sxs-lookup"><span data-stu-id="26e8b-163">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="26e8b-164">Este elemento especifica un validador, que se invoca durante la autenticación entre vecinos en la malla.</span><span class="sxs-lookup"><span data-stu-id="26e8b-164">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="26e8b-165">Cuando un nuevo par intenta establecer una conexión de vecino, pasa su propia credencial al par que responde.</span><span class="sxs-lookup"><span data-stu-id="26e8b-165">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="26e8b-166">El validador del contestador se invoca para comprobar la credencial de la parte remota.</span><span class="sxs-lookup"><span data-stu-id="26e8b-166">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="26e8b-167">Cuando una conexión del mismo nivel se establece en la malla, se autentican ambos pares mutuamente, lo que significa que se invocan los validadores en ambos extremos.</span><span class="sxs-lookup"><span data-stu-id="26e8b-167">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26e8b-168">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="26e8b-168">Example</span></span>  

 <span data-ttu-id="26e8b-169">El código siguiente establece el modo de validación de certificados en `PeerOrChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="26e8b-169">The following code sets the certificate validation mode to `PeerOrChainTrust`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="26e8b-170">Vea también</span><span class="sxs-lookup"><span data-stu-id="26e8b-170">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="26e8b-171">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="26e8b-171">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="26e8b-172">Conexión de redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="26e8b-172">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="26e8b-173">[Autenticación del mensaje del canal del mismo nivel](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="26e8b-173">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="26e8b-174">[Autenticación personalizada de canal del mismo nivel](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="26e8b-174">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="26e8b-175">Protección de las aplicaciones de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="26e8b-175">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
