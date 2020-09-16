---
title: <peerAuthentication> (Elemento)
ms.date: 03/30/2017
ms.assetid: 09a8a9ff-e395-42f6-8ceb-9d44bdc1cbe1
ms.openlocfilehash: 093b0c4b6a7fbf54455ec523b52c1f3a9884cfa8
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90536020"
---
# <a name="peerauthentication-element"></a><span data-ttu-id="c14f1-102">\<peerAuthentication> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="c14f1-102">\<peerAuthentication> Element</span></span>
<span data-ttu-id="c14f1-103">Especifica las opciones de autenticación de clientes punto a punto.</span><span class="sxs-lookup"><span data-stu-id="c14f1-103">Specifies authentication options for peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="c14f1-104">Para obtener más información sobre la programación punto a punto, vea [redes punto a punto](../../../wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="c14f1-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peerAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="c14f1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c14f1-105">Syntax</span></span>  
  
```xml  
<peerAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                    certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                    revocationMode="NoCheck/Online/Offline"
                    trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c14f1-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c14f1-106">Attributes and Elements</span></span>  
 <span data-ttu-id="c14f1-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c14f1-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c14f1-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="c14f1-108">Attributes</span></span>  
  
|<span data-ttu-id="c14f1-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="c14f1-109">Attribute</span></span>|<span data-ttu-id="c14f1-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="c14f1-110">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="c14f1-111">Cadena opcional.</span><span class="sxs-lookup"><span data-stu-id="c14f1-111">Optional string.</span></span> <span data-ttu-id="c14f1-112">Tipo y ensamblado utilizados para validar un tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="c14f1-112">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="c14f1-113">Se debe establecer este atributo cuando `certificateValidationMode` está establecido en `Custom`.</span><span class="sxs-lookup"><span data-stu-id="c14f1-113">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="c14f1-114">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="c14f1-114">Optional enumeration.</span></span> <span data-ttu-id="c14f1-115">Especifica uno de los tres modos utilizados para validar las credenciales.</span><span class="sxs-lookup"><span data-stu-id="c14f1-115">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="c14f1-116">Si se establece en `Custom`, también debe proporcionarse un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="c14f1-116">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="c14f1-117">De manera predeterminada, es `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="c14f1-117">The default is `ChainTrust`.</span></span>|  
|`revocationMode`|<span data-ttu-id="c14f1-118">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="c14f1-118">Optional enumeration.</span></span> <span data-ttu-id="c14f1-119">Uno de los modos utilizados para comprobar listas de certificados revocadas (CRL).</span><span class="sxs-lookup"><span data-stu-id="c14f1-119">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="c14f1-120">De manera predeterminada, es `Online`.</span><span class="sxs-lookup"><span data-stu-id="c14f1-120">The default is `Online`.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="c14f1-121">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="c14f1-121">Optional enumeration.</span></span> <span data-ttu-id="c14f1-122">Una de las dos ubicaciones de almacenamiento del sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="c14f1-122">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="c14f1-123">Se utiliza este valor cuando un certificado del servicio se negocia al cliente.</span><span class="sxs-lookup"><span data-stu-id="c14f1-123">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="c14f1-124">La validación se realiza en el almacén de **personas de confianza** en la ubicación de almacén especificada.</span><span class="sxs-lookup"><span data-stu-id="c14f1-124">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="c14f1-125">De manera predeterminada, es `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="c14f1-125">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="c14f1-126">Atributo customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="c14f1-126">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="c14f1-127">Valor</span><span class="sxs-lookup"><span data-stu-id="c14f1-127">Value</span></span>|<span data-ttu-id="c14f1-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="c14f1-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c14f1-129">String</span><span class="sxs-lookup"><span data-stu-id="c14f1-129">String</span></span>|<span data-ttu-id="c14f1-130">Especifica el nombre de tipo y el ensamblado y otros datos utilizados para buscar el tipo.</span><span class="sxs-lookup"><span data-stu-id="c14f1-130">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="c14f1-131">Como mínimo, se requieren un espacio de nombres y un nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="c14f1-131">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="c14f1-132">La información opcionales incluye: nombre de ensamblado, número de versión, referencia cultural y token de clave pública.</span><span class="sxs-lookup"><span data-stu-id="c14f1-132">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="c14f1-133">Atributo certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="c14f1-133">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="c14f1-134">Valor</span><span class="sxs-lookup"><span data-stu-id="c14f1-134">Value</span></span>|<span data-ttu-id="c14f1-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="c14f1-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c14f1-136">Enumeración</span><span class="sxs-lookup"><span data-stu-id="c14f1-136">Enumeration</span></span>|<span data-ttu-id="c14f1-137">Uno de los siguientes valores: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="c14f1-137">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="c14f1-138">De manera predeterminada, es `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="c14f1-138">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="c14f1-139">Para obtener más información, consulte [trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="c14f1-139">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="c14f1-140">Atributo revocationMode</span><span class="sxs-lookup"><span data-stu-id="c14f1-140">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="c14f1-141">Valor</span><span class="sxs-lookup"><span data-stu-id="c14f1-141">Value</span></span>|<span data-ttu-id="c14f1-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="c14f1-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c14f1-143">Enumeración</span><span class="sxs-lookup"><span data-stu-id="c14f1-143">Enumeration</span></span>|<span data-ttu-id="c14f1-144">Uno de los siguientes valores: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="c14f1-144">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="c14f1-145">De manera predeterminada, es `Online`.</span><span class="sxs-lookup"><span data-stu-id="c14f1-145">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="c14f1-146">Para obtener más información, consulte [trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="c14f1-146">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="c14f1-147">Atributo trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="c14f1-147">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="c14f1-148">Valor</span><span class="sxs-lookup"><span data-stu-id="c14f1-148">Value</span></span>|<span data-ttu-id="c14f1-149">Descripción</span><span class="sxs-lookup"><span data-stu-id="c14f1-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c14f1-150">Enumeración</span><span class="sxs-lookup"><span data-stu-id="c14f1-150">Enumeration</span></span>|<span data-ttu-id="c14f1-151">Puede ser uno de los siguientes valores: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="c14f1-151">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="c14f1-152">De manera predeterminada, es `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="c14f1-152">The default is `CurrentUser`.</span></span> <span data-ttu-id="c14f1-153">Si la aplicación cliente se está ejecutando bajo una cuenta del sistema, entonces el certificado está normalmente bajo `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="c14f1-153">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="c14f1-154">Si la aplicación cliente se está ejecutando en una cuenta de usuario, entonces el certificado se encuentra normalmente en `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="c14f1-154">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c14f1-155">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c14f1-155">Child Elements</span></span>  
 <span data-ttu-id="c14f1-156">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c14f1-156">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c14f1-157">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c14f1-157">Parent Elements</span></span>  
  
|<span data-ttu-id="c14f1-158">Elemento</span><span class="sxs-lookup"><span data-stu-id="c14f1-158">Element</span></span>|<span data-ttu-id="c14f1-159">Descripción</span><span class="sxs-lookup"><span data-stu-id="c14f1-159">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-clientcredentials-element.md)|<span data-ttu-id="c14f1-160">Especifica una credencial utilizada para autenticar el cliente a un servicio del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="c14f1-160">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c14f1-161">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c14f1-161">Remarks</span></span>  
 <span data-ttu-id="c14f1-162">El elemento `<authentication>` corresponde a la clase <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>.</span><span class="sxs-lookup"><span data-stu-id="c14f1-162">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="c14f1-163">Este elemento especifica un validador, que se invoca durante la autenticación entre vecinos en la malla.</span><span class="sxs-lookup"><span data-stu-id="c14f1-163">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="c14f1-164">Cuando un nuevo par intenta establecer una conexión de vecino, pasa su propia credencial al par que responde.</span><span class="sxs-lookup"><span data-stu-id="c14f1-164">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="c14f1-165">El validador del contestador se invoca para comprobar la credencial de la parte remota.</span><span class="sxs-lookup"><span data-stu-id="c14f1-165">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="c14f1-166">Cuando una conexión del mismo nivel se establece en la malla, se autentican ambos pares mutuamente, lo que significa que se invocan los validadores en ambos extremos.</span><span class="sxs-lookup"><span data-stu-id="c14f1-166">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c14f1-167">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c14f1-167">Example</span></span>  
 <span data-ttu-id="c14f1-168">El código siguiente establece el modo de validación de certificados en `PeerOrChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="c14f1-168">The following code sets the certificate validation mode to `PeerOrChainTrust`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c14f1-169">Vea también</span><span class="sxs-lookup"><span data-stu-id="c14f1-169">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="c14f1-170">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="c14f1-170">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="c14f1-171">Redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="c14f1-171">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="c14f1-172">[Autenticación del mensaje del canal del mismo nivel](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="c14f1-172">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="c14f1-173">[Autenticación personalizada de canal del mismo nivel](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="c14f1-173">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="c14f1-174">Protección de las aplicaciones de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="c14f1-174">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
