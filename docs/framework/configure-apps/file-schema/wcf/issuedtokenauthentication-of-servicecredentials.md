---
description: 'Más información sobre: <issuedTokenAuthentication> de <serviceCredentials>'
title: <issuedTokenAuthentication> de <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 5c2e288f-f603-4d13-839a-0fd6d1981bec
ms.openlocfilehash: 62c60cc467217312c349ecdbe8e98b04dd022ddf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725680"
---
# <a name="issuedtokenauthentication-of-servicecredentials"></a><span data-ttu-id="1c21f-103">\<issuedTokenAuthentication> de \<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="1c21f-103">\<issuedTokenAuthentication> of \<serviceCredentials></span></span>

<span data-ttu-id="1c21f-104">Especifica un token personalizado emitido como una credencial de servicio.</span><span class="sxs-lookup"><span data-stu-id="1c21f-104">Specifies a custom token issued as a service credential.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuedTokenAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="1c21f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1c21f-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1c21f-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1c21f-106">Attributes and Elements</span></span>  

 <span data-ttu-id="1c21f-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1c21f-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1c21f-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="1c21f-108">Attributes</span></span>  
  
|<span data-ttu-id="1c21f-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="1c21f-109">Attribute</span></span>|<span data-ttu-id="1c21f-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="1c21f-110">Description</span></span>|  
|---------------|-----------------|  
|`allowedAudienceUris`|<span data-ttu-id="1c21f-111">Obtiene el conjunto de los URI de destino para los que el token de seguridad <xref:System.IdentityModel.Tokens.SamlSecurityToken> se puede destinar con el fin de que una instancia de <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> lo considere válido.</span><span class="sxs-lookup"><span data-stu-id="1c21f-111">Gets the set of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span> <span data-ttu-id="1c21f-112">Para obtener más información sobre cómo usar este atributo, vea <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>.</span><span class="sxs-lookup"><span data-stu-id="1c21f-112">For more information on using this attribute, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>.</span></span>|  
|`allowUntrustedRsaIssuers`|<span data-ttu-id="1c21f-113">Un valor booleano que especifica si se permiten emisores de certificados de RSA que no son de confianza.</span><span class="sxs-lookup"><span data-stu-id="1c21f-113">A Boolean value that specifies if untrusted RSA certificate issuers are allowed.</span></span><br /><br /> <span data-ttu-id="1c21f-114">Las entidades emisoras de certificados (CA) firman los certificados para comprobar la autenticidad.</span><span class="sxs-lookup"><span data-stu-id="1c21f-114">Certificates are signed by certification authorities (CAs) to verify authenticity.</span></span> <span data-ttu-id="1c21f-115">Un emisor que no es de confianza es una CA de la cual no se especifica que sea de confianza para firmar certificados.</span><span class="sxs-lookup"><span data-stu-id="1c21f-115">An untrusted issuer is a CA that is not specified to be trusted to sign certificates.</span></span>|  
|`audienceUriMode`|<span data-ttu-id="1c21f-116">Obtiene un valor que especifica si se debería validar <xref:System.IdentityModel.Tokens.SamlSecurityToken> del token de seguridad <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition>.</span><span class="sxs-lookup"><span data-stu-id="1c21f-116">Gets a value that specifies whether the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token's <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> should be validated.</span></span> <span data-ttu-id="1c21f-117">Este valor es del tipo <xref:System.IdentityModel.Selectors.AudienceUriMode>.</span><span class="sxs-lookup"><span data-stu-id="1c21f-117">This value is of type <xref:System.IdentityModel.Selectors.AudienceUriMode>.</span></span> <span data-ttu-id="1c21f-118">Para obtener más información sobre cómo usar este atributo, vea <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="1c21f-118">For more information on using this attribute, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="1c21f-119">Especifica el modo de validación del certificado.</span><span class="sxs-lookup"><span data-stu-id="1c21f-119">Sets the certificate validation mode.</span></span> <span data-ttu-id="1c21f-120">Uno de los valores válidos de <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="1c21f-120">One of the valid values of <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="1c21f-121">Si se establece en `Custom`, también debe proporcionarse un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="1c21f-121">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="1c21f-122">De manera predeterminada, es `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="1c21f-122">The default is `ChainTrust`.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="1c21f-123">Cadena opcional.</span><span class="sxs-lookup"><span data-stu-id="1c21f-123">Optional string.</span></span> <span data-ttu-id="1c21f-124">Tipo y ensamblado utilizados para validar un tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="1c21f-124">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="1c21f-125">Se debe establecer este atributo cuando `certificateValidationMode` está establecido en `Custom`.</span><span class="sxs-lookup"><span data-stu-id="1c21f-125">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`revocationMode`|<span data-ttu-id="1c21f-126">Establece el modo de revocación que especifica si se produce una comprobación de revocación, y si se realiza en línea o sin conexión.</span><span class="sxs-lookup"><span data-stu-id="1c21f-126">Sets the revocation mode that specifies whether a revocation check occurs, and if it is performed online or offline.</span></span> <span data-ttu-id="1c21f-127">Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span><span class="sxs-lookup"><span data-stu-id="1c21f-127">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span>|  
|`samlSerializer`|<span data-ttu-id="1c21f-128">Un atributo de cadena opcional que especifica el tipo de SamlSerializer que se usa para la credencial del servicio.</span><span class="sxs-lookup"><span data-stu-id="1c21f-128">An optional string attribute that specifies the type of SamlSerializer that is used for the service credential.</span></span> <span data-ttu-id="1c21f-129">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="1c21f-129">The default is an empty string.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="1c21f-130">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="1c21f-130">Optional enumeration.</span></span> <span data-ttu-id="1c21f-131">Una de las dos ubicaciones de almacenamiento del sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="1c21f-131">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1c21f-132">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1c21f-132">Child Elements</span></span>  
  
|<span data-ttu-id="1c21f-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="1c21f-133">Element</span></span>|<span data-ttu-id="1c21f-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="1c21f-134">Description</span></span>|  
|-------------|-----------------|  
|`knownCertificates`|<span data-ttu-id="1c21f-135">Especifica una colección de elementos <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement> que indican emisores de confianza para la credencial del servicio.</span><span class="sxs-lookup"><span data-stu-id="1c21f-135">Specifies a collection of <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement> elements that specifies trusted issuers for the service credential.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1c21f-136">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1c21f-136">Parent Elements</span></span>  
  
|<span data-ttu-id="1c21f-137">Elemento</span><span class="sxs-lookup"><span data-stu-id="1c21f-137">Element</span></span>|<span data-ttu-id="1c21f-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="1c21f-138">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="1c21f-139">Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.</span><span class="sxs-lookup"><span data-stu-id="1c21f-139">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c21f-140">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1c21f-140">Remarks</span></span>  

 <span data-ttu-id="1c21f-141">El escenario del token emitido tiene tres etapas.</span><span class="sxs-lookup"><span data-stu-id="1c21f-141">The issued token scenario has three stages.</span></span> <span data-ttu-id="1c21f-142">En la primera fase, un cliente que intenta tener acceso a un servicio se conoce como *servicio de token seguro*.</span><span class="sxs-lookup"><span data-stu-id="1c21f-142">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="1c21f-143">El servicio de token seguro autentica, a continuación, al cliente y como consecuencia el cliente emite un token, normalmente un token del lenguaje de marcado de aserción de seguridad (SAML).</span><span class="sxs-lookup"><span data-stu-id="1c21f-143">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="1c21f-144">El cliente vuelve a continuación al servicio con el token.</span><span class="sxs-lookup"><span data-stu-id="1c21f-144">The client then returns to the service with the token.</span></span> <span data-ttu-id="1c21f-145">El servicio examina el token para los datos que permite al servicio autenticar el token y, por consiguiente, al cliente.</span><span class="sxs-lookup"><span data-stu-id="1c21f-145">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="1c21f-146">Para autenticar el token, el servicio debe conocer el certificado que usa el servicio de token seguro.</span><span class="sxs-lookup"><span data-stu-id="1c21f-146">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="1c21f-147">Este elemento es el repositorio para todos los certificados de servicio de token seguro.</span><span class="sxs-lookup"><span data-stu-id="1c21f-147">This element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="1c21f-148">Para agregar certificados, use [\<knownCertificates>](knowncertificates.md) .</span><span class="sxs-lookup"><span data-stu-id="1c21f-148">To add certificates, use the [\<knownCertificates>](knowncertificates.md).</span></span> <span data-ttu-id="1c21f-149">Inserte un [\<add>](add-of-knowncertificates.md) para cada certificado, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="1c21f-149">Insert an [\<add>](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="1c21f-150">De forma predeterminada, los certificados se deben obtener a partir de un servicio de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="1c21f-150">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="1c21f-151">Estos certificados "conocidos" garantizan que solo los clientes legítimos pueden obtener acceso a un servicio.</span><span class="sxs-lookup"><span data-stu-id="1c21f-151">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="1c21f-152">Para obtener más información sobre el uso de este elemento de configuración, consulte [Cómo: configurar credenciales en un servicio de Federación](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="1c21f-152">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c21f-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c21f-153">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.IssuedTokenAuthentication%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.IssuedTokenAuthentication%2A>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>
- [<span data-ttu-id="1c21f-154">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="1c21f-154">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="1c21f-155">Procedimiento para configurar las credenciales en un servicio de federación</span><span class="sxs-lookup"><span data-stu-id="1c21f-155">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
