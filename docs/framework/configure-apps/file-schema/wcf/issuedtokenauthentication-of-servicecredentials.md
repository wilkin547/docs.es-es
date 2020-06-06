---
title: <issuedTokenAuthentication> de <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 5c2e288f-f603-4d13-839a-0fd6d1981bec
ms.openlocfilehash: 6d468a27ee05fb4dd8cf087d10e5d170783d3454
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400357"
---
# <a name="issuedtokenauthentication-of-servicecredentials"></a><span data-ttu-id="44b0b-102">\<issuedTokenAuthentication> de \<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="44b0b-102">\<issuedTokenAuthentication> of \<serviceCredentials></span></span>
<span data-ttu-id="44b0b-103">Especifica un token personalizado emitido como una credencial de servicio.</span><span class="sxs-lookup"><span data-stu-id="44b0b-103">Specifies a custom token issued as a service credential.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuedTokenAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="44b0b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="44b0b-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="44b0b-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="44b0b-105">Attributes and Elements</span></span>  
 <span data-ttu-id="44b0b-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="44b0b-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="44b0b-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="44b0b-107">Attributes</span></span>  
  
|<span data-ttu-id="44b0b-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="44b0b-108">Attribute</span></span>|<span data-ttu-id="44b0b-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="44b0b-109">Description</span></span>|  
|---------------|-----------------|  
|`allowedAudienceUris`|<span data-ttu-id="44b0b-110">Obtiene el conjunto de los URI de destino para los que el token de seguridad <xref:System.IdentityModel.Tokens.SamlSecurityToken> se puede destinar con el fin de que una instancia de <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> lo considere válido.</span><span class="sxs-lookup"><span data-stu-id="44b0b-110">Gets the set of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span> <span data-ttu-id="44b0b-111">Para obtener más información sobre cómo usar este atributo, vea <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>.</span><span class="sxs-lookup"><span data-stu-id="44b0b-111">For more information on using this attribute, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>.</span></span>|  
|`allowUntrustedRsaIssuers`|<span data-ttu-id="44b0b-112">Un valor booleano que especifica si se permiten emisores de certificados de RSA que no son de confianza.</span><span class="sxs-lookup"><span data-stu-id="44b0b-112">A Boolean value that specifies if untrusted RSA certificate issuers are allowed.</span></span><br /><br /> <span data-ttu-id="44b0b-113">Las entidades emisoras de certificados (CA) firman los certificados para comprobar la autenticidad.</span><span class="sxs-lookup"><span data-stu-id="44b0b-113">Certificates are signed by certification authorities (CAs) to verify authenticity.</span></span> <span data-ttu-id="44b0b-114">Un emisor que no es de confianza es una CA de la cual no se especifica que sea de confianza para firmar certificados.</span><span class="sxs-lookup"><span data-stu-id="44b0b-114">An untrusted issuer is a CA that is not specified to be trusted to sign certificates.</span></span>|  
|`audienceUriMode`|<span data-ttu-id="44b0b-115">Obtiene un valor que especifica si se debería validar <xref:System.IdentityModel.Tokens.SamlSecurityToken> del token de seguridad <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition>.</span><span class="sxs-lookup"><span data-stu-id="44b0b-115">Gets a value that specifies whether the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token's <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> should be validated.</span></span> <span data-ttu-id="44b0b-116">Este valor es del tipo <xref:System.IdentityModel.Selectors.AudienceUriMode>.</span><span class="sxs-lookup"><span data-stu-id="44b0b-116">This value is of type <xref:System.IdentityModel.Selectors.AudienceUriMode>.</span></span> <span data-ttu-id="44b0b-117">Para obtener más información sobre cómo usar este atributo, vea <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="44b0b-117">For more information on using this attribute, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="44b0b-118">Especifica el modo de validación del certificado.</span><span class="sxs-lookup"><span data-stu-id="44b0b-118">Sets the certificate validation mode.</span></span> <span data-ttu-id="44b0b-119">Uno de los valores válidos de <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="44b0b-119">One of the valid values of <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="44b0b-120">Si se establece en `Custom`, también debe proporcionarse un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="44b0b-120">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="44b0b-121">De manera predeterminada, es `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="44b0b-121">The default is `ChainTrust`.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="44b0b-122">Cadena opcional.</span><span class="sxs-lookup"><span data-stu-id="44b0b-122">Optional string.</span></span> <span data-ttu-id="44b0b-123">Tipo y ensamblado utilizados para validar un tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="44b0b-123">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="44b0b-124">Se debe establecer este atributo cuando `certificateValidationMode` está establecido en `Custom`.</span><span class="sxs-lookup"><span data-stu-id="44b0b-124">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`revocationMode`|<span data-ttu-id="44b0b-125">Establece el modo de revocación que especifica si se produce una comprobación de revocación, y si se realiza en línea o sin conexión.</span><span class="sxs-lookup"><span data-stu-id="44b0b-125">Sets the revocation mode that specifies whether a revocation check occurs, and if it is performed online or offline.</span></span> <span data-ttu-id="44b0b-126">Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span><span class="sxs-lookup"><span data-stu-id="44b0b-126">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span>|  
|`samlSerializer`|<span data-ttu-id="44b0b-127">Un atributo de cadena opcional que especifica el tipo de SamlSerializer que se usa para la credencial del servicio.</span><span class="sxs-lookup"><span data-stu-id="44b0b-127">An optional string attribute that specifies the type of SamlSerializer that is used for the service credential.</span></span> <span data-ttu-id="44b0b-128">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="44b0b-128">The default is an empty string.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="44b0b-129">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="44b0b-129">Optional enumeration.</span></span> <span data-ttu-id="44b0b-130">Una de las dos ubicaciones de almacenamiento del sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="44b0b-130">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="44b0b-131">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="44b0b-131">Child Elements</span></span>  
  
|<span data-ttu-id="44b0b-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="44b0b-132">Element</span></span>|<span data-ttu-id="44b0b-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="44b0b-133">Description</span></span>|  
|-------------|-----------------|  
|`knownCertificates`|<span data-ttu-id="44b0b-134">Especifica una colección de elementos <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement> que indican emisores de confianza para la credencial del servicio.</span><span class="sxs-lookup"><span data-stu-id="44b0b-134">Specifies a collection of <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement> elements that specifies trusted issuers for the service credential.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="44b0b-135">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="44b0b-135">Parent Elements</span></span>  
  
|<span data-ttu-id="44b0b-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="44b0b-136">Element</span></span>|<span data-ttu-id="44b0b-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="44b0b-137">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="44b0b-138">Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.</span><span class="sxs-lookup"><span data-stu-id="44b0b-138">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="44b0b-139">Comentarios</span><span class="sxs-lookup"><span data-stu-id="44b0b-139">Remarks</span></span>  
 <span data-ttu-id="44b0b-140">El escenario del token emitido tiene tres etapas.</span><span class="sxs-lookup"><span data-stu-id="44b0b-140">The issued token scenario has three stages.</span></span> <span data-ttu-id="44b0b-141">En la primera fase, un cliente que intenta tener acceso a un servicio se conoce como *servicio de token seguro*.</span><span class="sxs-lookup"><span data-stu-id="44b0b-141">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="44b0b-142">El servicio de token seguro autentica, a continuación, al cliente y como consecuencia el cliente emite un token, normalmente un token del lenguaje de marcado de aserción de seguridad (SAML).</span><span class="sxs-lookup"><span data-stu-id="44b0b-142">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="44b0b-143">El cliente vuelve a continuación al servicio con el token.</span><span class="sxs-lookup"><span data-stu-id="44b0b-143">The client then returns to the service with the token.</span></span> <span data-ttu-id="44b0b-144">El servicio examina el token para los datos que permite al servicio autenticar el token y, por consiguiente, al cliente.</span><span class="sxs-lookup"><span data-stu-id="44b0b-144">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="44b0b-145">Para autenticar el token, el servicio debe conocer el certificado que usa el servicio de token seguro.</span><span class="sxs-lookup"><span data-stu-id="44b0b-145">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="44b0b-146">Este elemento es el repositorio para todos los certificados de servicio de token seguro.</span><span class="sxs-lookup"><span data-stu-id="44b0b-146">This element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="44b0b-147">Para agregar certificados, use [\<knownCertificates>](knowncertificates.md) .</span><span class="sxs-lookup"><span data-stu-id="44b0b-147">To add certificates, use the [\<knownCertificates>](knowncertificates.md).</span></span> <span data-ttu-id="44b0b-148">Inserte un [\<add>](add-of-knowncertificates.md) para cada certificado, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="44b0b-148">Insert an [\<add>](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="44b0b-149">De forma predeterminada, los certificados se deben obtener a partir de un servicio de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="44b0b-149">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="44b0b-150">Estos certificados "conocidos" garantizan que solo los clientes legítimos pueden obtener acceso a un servicio.</span><span class="sxs-lookup"><span data-stu-id="44b0b-150">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="44b0b-151">Para obtener más información sobre el uso de este elemento de configuración, consulte [Cómo: configurar credenciales en un servicio de Federación](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="44b0b-151">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44b0b-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="44b0b-152">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.IssuedTokenAuthentication%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.IssuedTokenAuthentication%2A>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>
- [<span data-ttu-id="44b0b-153">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="44b0b-153">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="44b0b-154">Procedimiento para configurar las credenciales en un servicio de federación</span><span class="sxs-lookup"><span data-stu-id="44b0b-154">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
