---
description: 'Más información acerca de: <messageSenderAuthentication> elemento'
title: <messageSenderAuthentication> (elemento)
ms.date: 03/30/2017
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
ms.openlocfilehash: 03c1cd626e7c3ad71026c076df3d757419810d74
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749342"
---
# <a name="messagesenderauthentication-element"></a><span data-ttu-id="e6bd9-103">Elemento \<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="e6bd9-103">\<messageSenderAuthentication> element</span></span>

<span data-ttu-id="e6bd9-104">Especifica las opciones de autenticación para los remitentes del mensaje punto a punto.</span><span class="sxs-lookup"><span data-stu-id="e6bd9-104">Specifies authentication options for peer-to-peer message senders.</span></span>  
  
 <span data-ttu-id="e6bd9-105">Para obtener más información sobre la programación punto a punto, vea [redes punto a punto](../../../wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="e6bd9-105">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<messageSenderAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="e6bd9-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e6bd9-106">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e6bd9-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e6bd9-107">Attributes and Elements</span></span>  

 <span data-ttu-id="e6bd9-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e6bd9-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e6bd9-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="e6bd9-109">Attributes</span></span>  
  
|<span data-ttu-id="e6bd9-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="e6bd9-110">Attribute</span></span>|<span data-ttu-id="e6bd9-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="e6bd9-111">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="e6bd9-112">Tipo y ensamblado utilizados para validar un tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="e6bd9-112">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="e6bd9-113">Se debe establecer este atributo cuando `certificateValidationMode` está establecido en `Custom`.</span><span class="sxs-lookup"><span data-stu-id="e6bd9-113">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="e6bd9-114">Especifica uno de los tres modos utilizados para validar las credenciales.</span><span class="sxs-lookup"><span data-stu-id="e6bd9-114">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="e6bd9-115">Si se establece en `Custom`, también debe proporcionarse un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="e6bd9-115">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`revocationMode`|<span data-ttu-id="e6bd9-116">Uno de los modos utilizados para comprobar listas de certificados revocadas (CRL).</span><span class="sxs-lookup"><span data-stu-id="e6bd9-116">One of the modes used to check for a revoked certificate lists (CRL).</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="e6bd9-117">Una de las dos ubicaciones de almacenamiento del sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="e6bd9-117">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="e6bd9-118">Se utiliza este valor cuando un certificado del servicio se negocia al cliente.</span><span class="sxs-lookup"><span data-stu-id="e6bd9-118">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="e6bd9-119">La validación se realiza en el almacén de **personas de confianza** en la ubicación de almacén especificada.</span><span class="sxs-lookup"><span data-stu-id="e6bd9-119">Validation is performed against the **Trusted People** store in the specified store location.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="e6bd9-120">Atributo customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="e6bd9-120">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="e6bd9-121">Value</span><span class="sxs-lookup"><span data-stu-id="e6bd9-121">Value</span></span>|<span data-ttu-id="e6bd9-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="e6bd9-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e6bd9-123">String</span><span class="sxs-lookup"><span data-stu-id="e6bd9-123">String</span></span>|<span data-ttu-id="e6bd9-124">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e6bd9-124">Optional.</span></span> <span data-ttu-id="e6bd9-125">Especifica el nombre de tipo y el ensamblado y otros datos utilizados para buscar el tipo.</span><span class="sxs-lookup"><span data-stu-id="e6bd9-125">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="e6bd9-126">Como mínimo, se requieren un espacio de nombres y un nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="e6bd9-126">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="e6bd9-127">La información opcionales incluye: nombre de ensamblado, número de versión, referencia cultural y token de clave pública.</span><span class="sxs-lookup"><span data-stu-id="e6bd9-127">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="e6bd9-128">Atributo certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="e6bd9-128">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="e6bd9-129">Value</span><span class="sxs-lookup"><span data-stu-id="e6bd9-129">Value</span></span>|<span data-ttu-id="e6bd9-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="e6bd9-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e6bd9-131">Enumeración</span><span class="sxs-lookup"><span data-stu-id="e6bd9-131">Enumeration</span></span>|<span data-ttu-id="e6bd9-132">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e6bd9-132">Optional.</span></span> <span data-ttu-id="e6bd9-133">Uno de los siguientes valores: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="e6bd9-133">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="e6bd9-134">De manera predeterminada, es `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="e6bd9-134">The default is `ChainTrust`.</span></span> <span data-ttu-id="e6bd9-135">De manera predeterminada, es `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="e6bd9-135">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="e6bd9-136">Para obtener más información, consulte [trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="e6bd9-136">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="e6bd9-137">Atributo revocationMode</span><span class="sxs-lookup"><span data-stu-id="e6bd9-137">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="e6bd9-138">Value</span><span class="sxs-lookup"><span data-stu-id="e6bd9-138">Value</span></span>|<span data-ttu-id="e6bd9-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="e6bd9-139">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e6bd9-140">Enumeración</span><span class="sxs-lookup"><span data-stu-id="e6bd9-140">Enumeration</span></span>|<span data-ttu-id="e6bd9-141">Uno de los siguientes valores: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="e6bd9-141">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="e6bd9-142">De manera predeterminada, es `Online`.</span><span class="sxs-lookup"><span data-stu-id="e6bd9-142">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="e6bd9-143">Para obtener más información, consulte [trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="e6bd9-143">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="e6bd9-144">Atributo trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="e6bd9-144">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="e6bd9-145">Value</span><span class="sxs-lookup"><span data-stu-id="e6bd9-145">Value</span></span>|<span data-ttu-id="e6bd9-146">Descripción</span><span class="sxs-lookup"><span data-stu-id="e6bd9-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e6bd9-147">Enumeración</span><span class="sxs-lookup"><span data-stu-id="e6bd9-147">Enumeration</span></span>|<span data-ttu-id="e6bd9-148">Puede ser uno de los siguientes valores: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="e6bd9-148">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="e6bd9-149">De manera predeterminada, es `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="e6bd9-149">The default is `CurrentUser`.</span></span> <span data-ttu-id="e6bd9-150">Si la aplicación cliente se está ejecutando bajo una cuenta del sistema, entonces el certificado está normalmente bajo `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="e6bd9-150">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="e6bd9-151">Si la aplicación cliente se está ejecutando en una cuenta de usuario, entonces el certificado se encuentra normalmente en `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="e6bd9-151">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span> <span data-ttu-id="e6bd9-152">De manera predeterminada, es `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="e6bd9-152">The default is `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e6bd9-153">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e6bd9-153">Child Elements</span></span>  

 <span data-ttu-id="e6bd9-154">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e6bd9-154">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e6bd9-155">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e6bd9-155">Parent Elements</span></span>  
  
|<span data-ttu-id="e6bd9-156">Elemento</span><span class="sxs-lookup"><span data-stu-id="e6bd9-156">Element</span></span>|<span data-ttu-id="e6bd9-157">Descripción</span><span class="sxs-lookup"><span data-stu-id="e6bd9-157">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-clientcredentials-element.md)|<span data-ttu-id="e6bd9-158">Especifica una credencial utilizada para autenticar el cliente a un servicio del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="e6bd9-158">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6bd9-159">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e6bd9-159">Remarks</span></span>  

 <span data-ttu-id="e6bd9-160">Se debe configurar este elemento si se elige la autenticación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="e6bd9-160">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="e6bd9-161">En el caso de los canales de salida, cada mensaje se firma con el certificado proporcionado por [\<certificate>](certificate-element.md) .</span><span class="sxs-lookup"><span data-stu-id="e6bd9-161">For output channels, each message is signed using the certificate provided by [\<certificate>](certificate-element.md).</span></span> <span data-ttu-id="e6bd9-162">Todos los mensajes, antes de ser entregados a la aplicación, se comprueban con la credencial de mensaje utilizando el validador especificado por el atributo `customCertificateValidatorType` de este elemento.</span><span class="sxs-lookup"><span data-stu-id="e6bd9-162">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="e6bd9-163">El validador puede aceptar o rechazar la credencial.</span><span class="sxs-lookup"><span data-stu-id="e6bd9-163">The validator can either accept or reject the credential.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6bd9-164">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e6bd9-164">Example</span></span>  

 <span data-ttu-id="e6bd9-165">El código siguiente establece el modo de validación del remitente del mensaje en `PeerOrChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="e6bd9-165">The following code sets the message sender validation mode to `PeerOrChainTrust`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e6bd9-166">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6bd9-166">See also</span></span>

- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="e6bd9-167">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="e6bd9-167">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="e6bd9-168">Conexión de redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="e6bd9-168">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="e6bd9-169">[Autenticación del mensaje del canal del mismo nivel](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="e6bd9-169">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="e6bd9-170">[Autenticación personalizada de canal del mismo nivel](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="e6bd9-170">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="e6bd9-171">Protección de las aplicaciones de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="e6bd9-171">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
