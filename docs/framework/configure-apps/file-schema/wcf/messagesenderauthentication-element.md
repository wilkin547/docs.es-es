---
title: '&lt;messageSenderAuthentication&gt; (elemento)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 20d452a6aa9047032d989d62d6c1121d7edc5ee3
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="ltmessagesenderauthenticationgt-element"></a><span data-ttu-id="a4297-102">&lt;messageSenderAuthentication&gt; (elemento)</span><span class="sxs-lookup"><span data-stu-id="a4297-102">&lt;messageSenderAuthentication&gt; element</span></span>
<span data-ttu-id="a4297-103">Especifica las opciones de autenticación para los remitentes del mensaje punto a punto.</span><span class="sxs-lookup"><span data-stu-id="a4297-103">Specifies authentication options for peer-to-peer message senders.</span></span>  
  
 <span data-ttu-id="a4297-104">Para obtener más información acerca de la programación de punto a punto, vea [redes Peer-to-Peer](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="a4297-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
 <span data-ttu-id="a4297-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a4297-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="a4297-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="a4297-106">\<behaviors></span></span>  
<span data-ttu-id="a4297-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="a4297-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="a4297-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="a4297-108">\<behavior></span></span>  
<span data-ttu-id="a4297-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="a4297-109">\<clientCredentials></span></span>  
<span data-ttu-id="a4297-110">\<punto ></span><span class="sxs-lookup"><span data-stu-id="a4297-110">\<peer></span></span>  
<span data-ttu-id="a4297-111">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="a4297-111">\<messageSenderAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4297-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a4297-112">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication  
customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
revocationMode="NoCheck/Online/Offline"  
trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a4297-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a4297-113">Attributes and Elements</span></span>  
 <span data-ttu-id="a4297-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a4297-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a4297-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="a4297-115">Attributes</span></span>  
  
|<span data-ttu-id="a4297-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="a4297-116">Attribute</span></span>|<span data-ttu-id="a4297-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="a4297-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a4297-118">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="a4297-118">customCertificateValidatorType</span></span>|<span data-ttu-id="a4297-119">Tipo y ensamblado utilizados para validar un tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="a4297-119">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="a4297-120">Se debe establecer este atributo cuando `certificateValidationMode` está establecido en `Custom`.</span><span class="sxs-lookup"><span data-stu-id="a4297-120">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|<span data-ttu-id="a4297-121">certifcateValidationMode</span><span class="sxs-lookup"><span data-stu-id="a4297-121">certifcateValidationMode</span></span>|<span data-ttu-id="a4297-122">Especifica uno de los tres modos utilizados para validar las credenciales.</span><span class="sxs-lookup"><span data-stu-id="a4297-122">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="a4297-123">Si se establece en `Custom`, también debe proporcionarse un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="a4297-123">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|<span data-ttu-id="a4297-124">revocationMode</span><span class="sxs-lookup"><span data-stu-id="a4297-124">revocationMode</span></span>|<span data-ttu-id="a4297-125">Uno de los modos utilizados para comprobar listas de certificados revocadas (CRL).</span><span class="sxs-lookup"><span data-stu-id="a4297-125">One of the modes used to check for a revoked certificate lists (CRL).</span></span>|  
|<span data-ttu-id="a4297-126">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="a4297-126">trustedStoreLocation</span></span>|<span data-ttu-id="a4297-127">Una de las dos ubicaciones de almacenamiento del sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="a4297-127">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="a4297-128">Se utiliza este valor cuando un certificado del servicio se negocia al cliente.</span><span class="sxs-lookup"><span data-stu-id="a4297-128">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="a4297-129">Validación se realiza contra el **personas de confianza** almacenar en la ubicación del almacén especificado.</span><span class="sxs-lookup"><span data-stu-id="a4297-129">Validation is performed against the **Trusted People** store in the specified store location.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="a4297-130">Atributo customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="a4297-130">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="a4297-131">Valor</span><span class="sxs-lookup"><span data-stu-id="a4297-131">Value</span></span>|<span data-ttu-id="a4297-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="a4297-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a4297-133">String</span><span class="sxs-lookup"><span data-stu-id="a4297-133">String</span></span>|<span data-ttu-id="a4297-134">Opcional.</span><span class="sxs-lookup"><span data-stu-id="a4297-134">Optional.</span></span> <span data-ttu-id="a4297-135">Especifica el nombre de tipo y el ensamblado y otros datos utilizados para buscar el tipo.</span><span class="sxs-lookup"><span data-stu-id="a4297-135">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="a4297-136">Como mínimo, se requieren un espacio de nombres y un nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="a4297-136">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="a4297-137">La información opcionales incluye: nombre de ensamblado, número de versión, referencia cultural y token de clave pública.</span><span class="sxs-lookup"><span data-stu-id="a4297-137">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="a4297-138">Atributo certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="a4297-138">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="a4297-139">Valor</span><span class="sxs-lookup"><span data-stu-id="a4297-139">Value</span></span>|<span data-ttu-id="a4297-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="a4297-140">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a4297-141">Enumeración</span><span class="sxs-lookup"><span data-stu-id="a4297-141">Enumeration</span></span>|<span data-ttu-id="a4297-142">Opcional.</span><span class="sxs-lookup"><span data-stu-id="a4297-142">Optional.</span></span> <span data-ttu-id="a4297-143">Uno de los siguientes valores: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="a4297-143">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="a4297-144">De manera predeterminada, es `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="a4297-144">The default is `ChainTrust`.</span></span> <span data-ttu-id="a4297-145">De manera predeterminada, es `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="a4297-145">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="a4297-146">Para obtener más información, consulte [trabajar con certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="a4297-146">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="a4297-147">Atributo revocationMode</span><span class="sxs-lookup"><span data-stu-id="a4297-147">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="a4297-148">Valor</span><span class="sxs-lookup"><span data-stu-id="a4297-148">Value</span></span>|<span data-ttu-id="a4297-149">Descripción</span><span class="sxs-lookup"><span data-stu-id="a4297-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a4297-150">Enumeración</span><span class="sxs-lookup"><span data-stu-id="a4297-150">Enumeration</span></span>|<span data-ttu-id="a4297-151">Uno de los siguientes valores: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="a4297-151">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="a4297-152">De manera predeterminada, es `Online`.</span><span class="sxs-lookup"><span data-stu-id="a4297-152">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="a4297-153">Para obtener más información, consulte [trabajar con certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="a4297-153">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="a4297-154">Atributo trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="a4297-154">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="a4297-155">Valor</span><span class="sxs-lookup"><span data-stu-id="a4297-155">Value</span></span>|<span data-ttu-id="a4297-156">Descripción</span><span class="sxs-lookup"><span data-stu-id="a4297-156">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a4297-157">Enumeración</span><span class="sxs-lookup"><span data-stu-id="a4297-157">Enumeration</span></span>|<span data-ttu-id="a4297-158">Uno de los siguientes valores: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="a4297-158">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="a4297-159">De manera predeterminada, es `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="a4297-159">The default is `CurrentUser`.</span></span> <span data-ttu-id="a4297-160">Si la aplicación cliente se está ejecutando bajo una cuenta del sistema, entonces el certificado está normalmente bajo `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="a4297-160">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="a4297-161">Si la aplicación cliente se está ejecutando en una cuenta de usuario, entonces el certificado se encuentra normalmente en `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="a4297-161">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span> <span data-ttu-id="a4297-162">De manera predeterminada, es `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="a4297-162">The default is `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a4297-163">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a4297-163">Child Elements</span></span>  
 <span data-ttu-id="a4297-164">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a4297-164">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a4297-165">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a4297-165">Parent Elements</span></span>  
  
|<span data-ttu-id="a4297-166">Elemento</span><span class="sxs-lookup"><span data-stu-id="a4297-166">Element</span></span>|<span data-ttu-id="a4297-167">Descripción</span><span class="sxs-lookup"><span data-stu-id="a4297-167">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a4297-168">\<peer></span><span class="sxs-lookup"><span data-stu-id="a4297-168">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="a4297-169">Especifica una credencial utilizada para autenticar el cliente a un servicio del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="a4297-169">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4297-170">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a4297-170">Remarks</span></span>  
 <span data-ttu-id="a4297-171">Se debe configurar este elemento si se elige la autenticación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="a4297-171">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="a4297-172">Para los canales de salida, cada mensaje se firma utilizando el certificado proporcionado por [ \<certificado >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span><span class="sxs-lookup"><span data-stu-id="a4297-172">For output channels, each message is signed using the certificate provided by [\<certificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span></span> <span data-ttu-id="a4297-173">Todos los mensajes, antes de ser entregados a la aplicación, se comprueban con la credencial de mensaje utilizando el validador especificado por el atributo `customCertificateValidatorType` de este elemento.</span><span class="sxs-lookup"><span data-stu-id="a4297-173">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="a4297-174">El validador puede aceptar o rechazar la credencial.</span><span class="sxs-lookup"><span data-stu-id="a4297-174">The validator can either accept or reject the credential.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4297-175">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a4297-175">Example</span></span>  
 <span data-ttu-id="a4297-176">El código siguiente establece el modo de validación del remitente del mensaje en `PeerOrChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="a4297-176">The following code sets the message sender validation mode to `PeerOrChainTrust`.</span></span>  
  
```xml  
<behaviors>  
 <endpointBehaviors>  
  <behavior name="MyEndpointBehavior">  
   <clientCredentials>  
    <peer>  
      <certificate findValue="www.contoso.com"   
                   storeLocation="LocalMachine"  
                   x509FindType="FindByIssuerName" />  
        <messageSenderAuthentication   
          certificateValidationMode="PeerOrChainTrust" />  
       <messageSenderAuthentication certificateValidationMode="None" />  
    </peer>  
   </clientCredentials>  
  </behavior>  
 </endpointBehaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a4297-177">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4297-177">See Also</span></span>  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>  
 <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>  
 [<span data-ttu-id="a4297-178">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="a4297-178">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="a4297-179">Conexión de redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="a4297-179">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="a4297-180">Autenticación de mensajes del canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="a4297-180">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="a4297-181">Canal del mismo nivel de autenticación personalizada</span><span class="sxs-lookup"><span data-stu-id="a4297-181">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="a4297-182">Protección de las aplicaciones de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="a4297-182">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
