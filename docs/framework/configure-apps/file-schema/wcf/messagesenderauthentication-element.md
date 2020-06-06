---
title: <messageSenderAuthentication> (elemento)
ms.date: 03/30/2017
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
ms.openlocfilehash: bab0e50d7feba3ea55d505be07cfa41427a5cbbc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397785"
---
# <a name="messagesenderauthentication-element"></a><span data-ttu-id="72d2c-102">Elemento \<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="72d2c-102">\<messageSenderAuthentication> element</span></span>
<span data-ttu-id="72d2c-103">Especifica las opciones de autenticación para los remitentes del mensaje punto a punto.</span><span class="sxs-lookup"><span data-stu-id="72d2c-103">Specifies authentication options for peer-to-peer message senders.</span></span>  
  
 <span data-ttu-id="72d2c-104">Para obtener más información sobre la programación punto a punto, vea [redes punto a punto](../../../wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="72d2c-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<messageSenderAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="72d2c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="72d2c-105">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="72d2c-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="72d2c-106">Attributes and Elements</span></span>  
 <span data-ttu-id="72d2c-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="72d2c-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="72d2c-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="72d2c-108">Attributes</span></span>  
  
|<span data-ttu-id="72d2c-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="72d2c-109">Attribute</span></span>|<span data-ttu-id="72d2c-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="72d2c-110">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="72d2c-111">Tipo y ensamblado utilizados para validar un tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="72d2c-111">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="72d2c-112">Se debe establecer este atributo cuando `certificateValidationMode` está establecido en `Custom`.</span><span class="sxs-lookup"><span data-stu-id="72d2c-112">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="72d2c-113">Especifica uno de los tres modos utilizados para validar las credenciales.</span><span class="sxs-lookup"><span data-stu-id="72d2c-113">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="72d2c-114">Si se establece en `Custom`, también debe proporcionarse un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="72d2c-114">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`revocationMode`|<span data-ttu-id="72d2c-115">Uno de los modos utilizados para comprobar listas de certificados revocadas (CRL).</span><span class="sxs-lookup"><span data-stu-id="72d2c-115">One of the modes used to check for a revoked certificate lists (CRL).</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="72d2c-116">Una de las dos ubicaciones de almacenamiento del sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="72d2c-116">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="72d2c-117">Se utiliza este valor cuando un certificado del servicio se negocia al cliente.</span><span class="sxs-lookup"><span data-stu-id="72d2c-117">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="72d2c-118">La validación se realiza en el almacén de **personas de confianza** en la ubicación de almacén especificada.</span><span class="sxs-lookup"><span data-stu-id="72d2c-118">Validation is performed against the **Trusted People** store in the specified store location.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="72d2c-119">Atributo customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="72d2c-119">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="72d2c-120">Value</span><span class="sxs-lookup"><span data-stu-id="72d2c-120">Value</span></span>|<span data-ttu-id="72d2c-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="72d2c-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="72d2c-122">String</span><span class="sxs-lookup"><span data-stu-id="72d2c-122">String</span></span>|<span data-ttu-id="72d2c-123">Opcional.</span><span class="sxs-lookup"><span data-stu-id="72d2c-123">Optional.</span></span> <span data-ttu-id="72d2c-124">Especifica el nombre de tipo y el ensamblado y otros datos utilizados para buscar el tipo.</span><span class="sxs-lookup"><span data-stu-id="72d2c-124">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="72d2c-125">Como mínimo, se requieren un espacio de nombres y un nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="72d2c-125">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="72d2c-126">La información opcionales incluye: nombre de ensamblado, número de versión, referencia cultural y token de clave pública.</span><span class="sxs-lookup"><span data-stu-id="72d2c-126">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="72d2c-127">Atributo certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="72d2c-127">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="72d2c-128">Value</span><span class="sxs-lookup"><span data-stu-id="72d2c-128">Value</span></span>|<span data-ttu-id="72d2c-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="72d2c-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="72d2c-130">Enumeración</span><span class="sxs-lookup"><span data-stu-id="72d2c-130">Enumeration</span></span>|<span data-ttu-id="72d2c-131">Opcional.</span><span class="sxs-lookup"><span data-stu-id="72d2c-131">Optional.</span></span> <span data-ttu-id="72d2c-132">Uno de los siguientes valores: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="72d2c-132">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="72d2c-133">De manera predeterminada, es `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="72d2c-133">The default is `ChainTrust`.</span></span> <span data-ttu-id="72d2c-134">De manera predeterminada, es `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="72d2c-134">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="72d2c-135">Para obtener más información, consulte [trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="72d2c-135">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="72d2c-136">Atributo revocationMode</span><span class="sxs-lookup"><span data-stu-id="72d2c-136">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="72d2c-137">Value</span><span class="sxs-lookup"><span data-stu-id="72d2c-137">Value</span></span>|<span data-ttu-id="72d2c-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="72d2c-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="72d2c-139">Enumeración</span><span class="sxs-lookup"><span data-stu-id="72d2c-139">Enumeration</span></span>|<span data-ttu-id="72d2c-140">Uno de los siguientes valores: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="72d2c-140">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="72d2c-141">De manera predeterminada, es `Online`.</span><span class="sxs-lookup"><span data-stu-id="72d2c-141">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="72d2c-142">Para obtener más información, consulte [trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="72d2c-142">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="72d2c-143">Atributo trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="72d2c-143">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="72d2c-144">Value</span><span class="sxs-lookup"><span data-stu-id="72d2c-144">Value</span></span>|<span data-ttu-id="72d2c-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="72d2c-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="72d2c-146">Enumeración</span><span class="sxs-lookup"><span data-stu-id="72d2c-146">Enumeration</span></span>|<span data-ttu-id="72d2c-147">Puede ser uno de los siguientes valores: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="72d2c-147">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="72d2c-148">De manera predeterminada, es `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="72d2c-148">The default is `CurrentUser`.</span></span> <span data-ttu-id="72d2c-149">Si la aplicación cliente se está ejecutando bajo una cuenta del sistema, entonces el certificado está normalmente bajo `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="72d2c-149">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="72d2c-150">Si la aplicación cliente se está ejecutando en una cuenta de usuario, entonces el certificado se encuentra normalmente en `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="72d2c-150">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span> <span data-ttu-id="72d2c-151">De manera predeterminada, es `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="72d2c-151">The default is `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="72d2c-152">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="72d2c-152">Child Elements</span></span>  
 <span data-ttu-id="72d2c-153">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="72d2c-153">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="72d2c-154">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="72d2c-154">Parent Elements</span></span>  
  
|<span data-ttu-id="72d2c-155">Elemento</span><span class="sxs-lookup"><span data-stu-id="72d2c-155">Element</span></span>|<span data-ttu-id="72d2c-156">Descripción</span><span class="sxs-lookup"><span data-stu-id="72d2c-156">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-clientcredentials-element.md)|<span data-ttu-id="72d2c-157">Especifica una credencial utilizada para autenticar el cliente a un servicio del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="72d2c-157">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72d2c-158">Comentarios</span><span class="sxs-lookup"><span data-stu-id="72d2c-158">Remarks</span></span>  
 <span data-ttu-id="72d2c-159">Se debe configurar este elemento si se elige la autenticación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="72d2c-159">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="72d2c-160">En el caso de los canales de salida, cada mensaje se firma con el certificado proporcionado por [\<certificate>](certificate-element.md) .</span><span class="sxs-lookup"><span data-stu-id="72d2c-160">For output channels, each message is signed using the certificate provided by [\<certificate>](certificate-element.md).</span></span> <span data-ttu-id="72d2c-161">Todos los mensajes, antes de ser entregados a la aplicación, se comprueban con la credencial de mensaje utilizando el validador especificado por el atributo `customCertificateValidatorType` de este elemento.</span><span class="sxs-lookup"><span data-stu-id="72d2c-161">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="72d2c-162">El validador puede aceptar o rechazar la credencial.</span><span class="sxs-lookup"><span data-stu-id="72d2c-162">The validator can either accept or reject the credential.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72d2c-163">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="72d2c-163">Example</span></span>  
 <span data-ttu-id="72d2c-164">El código siguiente establece el modo de validación del remitente del mensaje en `PeerOrChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="72d2c-164">The following code sets the message sender validation mode to `PeerOrChainTrust`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="72d2c-165">Consulte también</span><span class="sxs-lookup"><span data-stu-id="72d2c-165">See also</span></span>

- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="72d2c-166">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="72d2c-166">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="72d2c-167">Conexión de redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="72d2c-167">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="72d2c-168">[Autenticación del mensaje del canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="72d2c-168">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="72d2c-169">[Autenticación personalizada de canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="72d2c-169">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="72d2c-170">Protección de las aplicaciones de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="72d2c-170">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
