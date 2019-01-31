---
title: <issuedTokenAuthentication> de <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 5c2e288f-f603-4d13-839a-0fd6d1981bec
ms.openlocfilehash: c195791250831897b8bc9d09782d17609272e146
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55260295"
---
# <a name="issuedtokenauthentication-of-servicecredentials"></a><span data-ttu-id="eda5d-102">\<issuedTokenAuthentication > de \<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="eda5d-102">\<issuedTokenAuthentication> of \<serviceCredentials></span></span>
<span data-ttu-id="eda5d-103">Especifica un token personalizado emitido como una credencial de servicio.</span><span class="sxs-lookup"><span data-stu-id="eda5d-103">Specifies a custom token issued as a service credential.</span></span>  
  
 <span data-ttu-id="eda5d-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="eda5d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="eda5d-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="eda5d-105">\<behaviors></span></span>  
<span data-ttu-id="eda5d-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="eda5d-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="eda5d-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="eda5d-107">\<behavior></span></span>  
<span data-ttu-id="eda5d-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="eda5d-108">\<serviceCredentials></span></span>  
<span data-ttu-id="eda5d-109">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="eda5d-109">\<issuedTokenAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eda5d-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eda5d-110">Syntax</span></span>  
  
```xml  
<issuedTokenAuthentication allowUntrustedRsaIssuers="Boolean"
                           audienceUriMode="Always/BearerKeyOnly/Never"
                           customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                           certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                           revocationMode="NoCheck/Online/Offline"
                           samlSerializer="String"
                           trustedStoreLocation="CurrentUser/LocalMachine">
  <allowedAudienceUris>
    <add allowedAudienceUri="String" />
  </allowedAudienceUris>
  <knownCertificates>
    <add findValue="String"
         storeLocation="CurrentUser/LocalMachine"
         storeName=" CurrentUser/LocalMachine"
         x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
  </knownCertificates>
</issuedTokenAuthentication>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eda5d-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="eda5d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="eda5d-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="eda5d-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eda5d-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="eda5d-113">Attributes</span></span>  
  
|<span data-ttu-id="eda5d-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="eda5d-114">Attribute</span></span>|<span data-ttu-id="eda5d-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="eda5d-115">Description</span></span>|  
|---------------|-----------------|  
|`allowedAudienceUris`|<span data-ttu-id="eda5d-116">Obtiene el conjunto de los URI de destino para los que el token de seguridad <xref:System.IdentityModel.Tokens.SamlSecurityToken> se puede destinar con el fin de que una instancia de <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> lo considere válido.</span><span class="sxs-lookup"><span data-stu-id="eda5d-116">Gets the set of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span> <span data-ttu-id="eda5d-117">Para obtener más información sobre cómo usar este atributo, vea <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>.</span><span class="sxs-lookup"><span data-stu-id="eda5d-117">For more information on using this attribute, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>.</span></span>|  
|`allowUntrustedRsaIssuers`|<span data-ttu-id="eda5d-118">Un valor booleano que especifica si se permiten emisores de certificados de RSA que no son de confianza.</span><span class="sxs-lookup"><span data-stu-id="eda5d-118">A Boolean value that specifies if untrusted RSA certificate issuers are allowed.</span></span><br /><br /> <span data-ttu-id="eda5d-119">Las entidades emisoras de certificados (CA) firman los certificados para comprobar la autenticidad.</span><span class="sxs-lookup"><span data-stu-id="eda5d-119">Certificates are signed by certification authorities (CAs) to verify authenticity.</span></span> <span data-ttu-id="eda5d-120">Un emisor que no es de confianza es una CA de la cual no se especifica que sea de confianza para firmar certificados.</span><span class="sxs-lookup"><span data-stu-id="eda5d-120">An untrusted issuer is a CA that is not specified to be trusted to sign certificates.</span></span>|  
|`audienceUriMode`|<span data-ttu-id="eda5d-121">Obtiene un valor que especifica si se debería validar <xref:System.IdentityModel.Tokens.SamlSecurityToken> del token de seguridad <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition>.</span><span class="sxs-lookup"><span data-stu-id="eda5d-121">Gets a value that specifies whether the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token's <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> should be validated.</span></span> <span data-ttu-id="eda5d-122">Este valor es del tipo <xref:System.IdentityModel.Selectors.AudienceUriMode>.</span><span class="sxs-lookup"><span data-stu-id="eda5d-122">This value is of type <xref:System.IdentityModel.Selectors.AudienceUriMode>.</span></span> <span data-ttu-id="eda5d-123">Para obtener más información sobre cómo usar este atributo, vea <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="eda5d-123">For more information on using this attribute, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="eda5d-124">Especifica el modo de validación del certificado.</span><span class="sxs-lookup"><span data-stu-id="eda5d-124">Sets the certificate validation mode.</span></span> <span data-ttu-id="eda5d-125">Uno de los valores válidos de <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="eda5d-125">One of the valid values of <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="eda5d-126">Si se establece en `Custom`, también debe proporcionarse un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="eda5d-126">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="eda5d-127">De manera predeterminada, es `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="eda5d-127">The default is `ChainTrust`.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="eda5d-128">Cadena opcional.</span><span class="sxs-lookup"><span data-stu-id="eda5d-128">Optional string.</span></span> <span data-ttu-id="eda5d-129">Tipo y ensamblado utilizados para validar un tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="eda5d-129">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="eda5d-130">Se debe establecer este atributo cuando `certificateValidationMode` está establecido en `Custom`.</span><span class="sxs-lookup"><span data-stu-id="eda5d-130">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`revocationMode`|<span data-ttu-id="eda5d-131">Establece el modo de revocación que especifica si se produce una comprobación de revocación, y si se realiza en línea o sin conexión.</span><span class="sxs-lookup"><span data-stu-id="eda5d-131">Sets the revocation mode that specifies whether a revocation check occurs, and if it is performed online or offline.</span></span> <span data-ttu-id="eda5d-132">Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span><span class="sxs-lookup"><span data-stu-id="eda5d-132">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span>|  
|`samlSerializer`|<span data-ttu-id="eda5d-133">Un atributo de cadena opcional que especifica el tipo de SamlSerializer que se usa para la credencial del servicio.</span><span class="sxs-lookup"><span data-stu-id="eda5d-133">An optional string attribute that specifies the type of SamlSerializer that is used for the service credential.</span></span> <span data-ttu-id="eda5d-134">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="eda5d-134">The default is an empty string.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="eda5d-135">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="eda5d-135">Optional enumeration.</span></span> <span data-ttu-id="eda5d-136">Una de las dos ubicaciones de almacenamiento del sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="eda5d-136">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eda5d-137">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="eda5d-137">Child Elements</span></span>  
  
|<span data-ttu-id="eda5d-138">Elemento</span><span class="sxs-lookup"><span data-stu-id="eda5d-138">Element</span></span>|<span data-ttu-id="eda5d-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="eda5d-139">Description</span></span>|  
|-------------|-----------------|  
|`knownCertificates`|<span data-ttu-id="eda5d-140">Especifica una colección de elementos <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement> que indican emisores de confianza para la credencial del servicio.</span><span class="sxs-lookup"><span data-stu-id="eda5d-140">Specifies a collection of <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement> elements that specifies trusted issuers for the service credential.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="eda5d-141">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="eda5d-141">Parent Elements</span></span>  
  
|<span data-ttu-id="eda5d-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="eda5d-142">Element</span></span>|<span data-ttu-id="eda5d-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="eda5d-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eda5d-144">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="eda5d-144">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="eda5d-145">Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.</span><span class="sxs-lookup"><span data-stu-id="eda5d-145">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eda5d-146">Comentarios</span><span class="sxs-lookup"><span data-stu-id="eda5d-146">Remarks</span></span>  
 <span data-ttu-id="eda5d-147">El escenario del token emitido tiene tres etapas.</span><span class="sxs-lookup"><span data-stu-id="eda5d-147">The issued token scenario has three stages.</span></span> <span data-ttu-id="eda5d-148">En la primera fase, un cliente intenta tener acceso a un servicio se conoce un *servicio de token seguro*.</span><span class="sxs-lookup"><span data-stu-id="eda5d-148">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="eda5d-149">El servicio de token seguro autentica, a continuación, al cliente y como consecuencia el cliente emite un token, normalmente un token del lenguaje de marcado de aserción de seguridad (SAML).</span><span class="sxs-lookup"><span data-stu-id="eda5d-149">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="eda5d-150">El cliente vuelve a continuación al servicio con el token.</span><span class="sxs-lookup"><span data-stu-id="eda5d-150">The client then returns to the service with the token.</span></span> <span data-ttu-id="eda5d-151">El servicio examina el token para los datos que permite al servicio autenticar el token y, por consiguiente, al cliente.</span><span class="sxs-lookup"><span data-stu-id="eda5d-151">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="eda5d-152">Para autenticar el token, el servicio debe conocer el certificado que usa el servicio de token seguro.</span><span class="sxs-lookup"><span data-stu-id="eda5d-152">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="eda5d-153">Este elemento es el repositorio para todos los certificados de servicio de token seguro.</span><span class="sxs-lookup"><span data-stu-id="eda5d-153">This element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="eda5d-154">Para agregar certificados, use el [ \<knownCertificates >](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="eda5d-154">To add certificates, use the [\<knownCertificates>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span></span> <span data-ttu-id="eda5d-155">Insertar un [ \<Agregar >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) para cada certificado, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="eda5d-155">Insert an [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
```xml  
<issuedTokenAuthentication>
  <knownCertificates>
    <add findValue="www.contoso.com"
         storeLocation="LocalMachine"
         storeName="My"
         X509FindType="FindBySubjectName" />
  </knownCertificates>
</issuedTokenAuthentication>
```  
  
 <span data-ttu-id="eda5d-156">De forma predeterminada, los certificados se deben obtener a partir de un servicio de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="eda5d-156">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="eda5d-157">Estos certificados "conocidos" garantizan que solo los clientes legítimos pueden obtener acceso a un servicio.</span><span class="sxs-lookup"><span data-stu-id="eda5d-157">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="eda5d-158">Para obtener más información sobre el uso de este elemento de configuración, vea [Cómo: Configurar las credenciales en un servicio de federación](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="eda5d-158">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eda5d-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="eda5d-159">See also</span></span>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.IssuedTokenAuthentication%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.IssuedTokenAuthentication%2A>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>
- [<span data-ttu-id="eda5d-160">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="eda5d-160">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="eda5d-161">Cómo: Configurar las credenciales en un servicio de federación</span><span class="sxs-lookup"><span data-stu-id="eda5d-161">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
