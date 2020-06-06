---
title: <add> de <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 128aaabe-3f1a-4c3b-b59f-898d0f02910f
ms.openlocfilehash: 29b067e6ec20992084f9ab3bab087222bdd56da2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400622"
---
# <a name="add-of-knowncertificates"></a><span data-ttu-id="ef7a2-102">\<add> de \<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="ef7a2-102">\<add> of \<knownCertificates></span></span>
<span data-ttu-id="ef7a2-103">Agrega un certificado X.509 a la colección de certificados conocidos.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-103">Adds an X.509 certificate to the collection of known certificates.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenAuthentication>**](issuedtokenauthentication-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<knownCertificates>**](knowncertificates.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="ef7a2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ef7a2-104">Syntax</span></span>  
  
```xml  
<knownCertificates>
   <add findValue="String"
      storeLocation="CurrentUser/LocalMachine"
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
      x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ef7a2-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ef7a2-105">Attributes and Elements</span></span>  
 <span data-ttu-id="ef7a2-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ef7a2-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="ef7a2-107">Attributes</span></span>  
  
|<span data-ttu-id="ef7a2-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="ef7a2-108">Attribute</span></span>|<span data-ttu-id="ef7a2-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="ef7a2-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ef7a2-110">findValue</span><span class="sxs-lookup"><span data-stu-id="ef7a2-110">findValue</span></span>|<span data-ttu-id="ef7a2-111">String.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-111">String.</span></span> <span data-ttu-id="ef7a2-112">Valor que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-112">The value to search for.</span></span>|  
|<span data-ttu-id="ef7a2-113">storeLocation</span><span class="sxs-lookup"><span data-stu-id="ef7a2-113">storeLocation</span></span>|<span data-ttu-id="ef7a2-114">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-114">Enumeration.</span></span> <span data-ttu-id="ef7a2-115">Una de las dos ubicaciones de almacén en que buscar.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-115">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="ef7a2-116">storeName</span><span class="sxs-lookup"><span data-stu-id="ef7a2-116">storeName</span></span>|<span data-ttu-id="ef7a2-117">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-117">Enumeration.</span></span> <span data-ttu-id="ef7a2-118">Uno de los almacenes del sistema en que buscar.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-118">One of the system stores to search.</span></span>|  
|<span data-ttu-id="ef7a2-119">x509FindType</span><span class="sxs-lookup"><span data-stu-id="ef7a2-119">x509FindType</span></span>|<span data-ttu-id="ef7a2-120">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-120">Enumeration.</span></span> <span data-ttu-id="ef7a2-121">Uno de los campos de certificado en que buscar.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-121">One of the certificate fields to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="ef7a2-122">AtributofindValue</span><span class="sxs-lookup"><span data-stu-id="ef7a2-122">findValue Attribute</span></span>  
  
|<span data-ttu-id="ef7a2-123">Value</span><span class="sxs-lookup"><span data-stu-id="ef7a2-123">Value</span></span>|<span data-ttu-id="ef7a2-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="ef7a2-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ef7a2-125">String</span><span class="sxs-lookup"><span data-stu-id="ef7a2-125">String</span></span>|<span data-ttu-id="ef7a2-126">El valor depende del campo (se especifica por el atributo X509FindType) en que se busca.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-126">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="ef7a2-127">Por ejemplo, si se busca una huella digital, el valor debe ser una cadena de números hexadecimales.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-127">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="ef7a2-128">Atributo x509FindType</span><span class="sxs-lookup"><span data-stu-id="ef7a2-128">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="ef7a2-129">Value</span><span class="sxs-lookup"><span data-stu-id="ef7a2-129">Value</span></span>|<span data-ttu-id="ef7a2-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="ef7a2-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ef7a2-131">Enumeración</span><span class="sxs-lookup"><span data-stu-id="ef7a2-131">Enumeration</span></span>|<span data-ttu-id="ef7a2-132">Los valores incluyen: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-132">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="ef7a2-133">Atributo storeLocation</span><span class="sxs-lookup"><span data-stu-id="ef7a2-133">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="ef7a2-134">Value</span><span class="sxs-lookup"><span data-stu-id="ef7a2-134">Value</span></span>|<span data-ttu-id="ef7a2-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="ef7a2-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ef7a2-136">Enumeración</span><span class="sxs-lookup"><span data-stu-id="ef7a2-136">Enumeration</span></span>|<span data-ttu-id="ef7a2-137">CurrentUser o LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-137">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="ef7a2-138">Atributo storeName</span><span class="sxs-lookup"><span data-stu-id="ef7a2-138">storeName Attribute</span></span>  
  
|<span data-ttu-id="ef7a2-139">Value</span><span class="sxs-lookup"><span data-stu-id="ef7a2-139">Value</span></span>|<span data-ttu-id="ef7a2-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="ef7a2-140">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ef7a2-141">Enumeración</span><span class="sxs-lookup"><span data-stu-id="ef7a2-141">Enumeration</span></span>|<span data-ttu-id="ef7a2-142">Los valores incluyen: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, y TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-142">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ef7a2-143">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ef7a2-143">Child Elements</span></span>  
 <span data-ttu-id="ef7a2-144">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-144">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ef7a2-145">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ef7a2-145">Parent Elements</span></span>  
  
|<span data-ttu-id="ef7a2-146">Elemento</span><span class="sxs-lookup"><span data-stu-id="ef7a2-146">Element</span></span>|<span data-ttu-id="ef7a2-147">Descripción</span><span class="sxs-lookup"><span data-stu-id="ef7a2-147">Description</span></span>|  
|-------------|-----------------|  
|[\<knownCertificates>](knowncertificates.md)|<span data-ttu-id="ef7a2-148">Representa una colección de certificados X.509 que se proporcionan por un servicio de token de seguridad (STS) para la validación de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-148">Represents a collection of X.509 certificates that are provided by a Security Token Service (STS) for validation of security tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef7a2-149">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ef7a2-149">Remarks</span></span>  
 <span data-ttu-id="ef7a2-150">El escenario del token emitido tiene tres etapas.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-150">The issued token scenario has three stages.</span></span> <span data-ttu-id="ef7a2-151">En la primera fase, un cliente que intenta tener acceso a un servicio se conoce como *servicio de token seguro*.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-151">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="ef7a2-152">El servicio de token seguro autentica, a continuación, al cliente y como consecuencia el cliente emite un token, normalmente un token del lenguaje de marcado de aserción de seguridad (SAML).</span><span class="sxs-lookup"><span data-stu-id="ef7a2-152">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="ef7a2-153">El cliente vuelve a continuación al servicio con el token.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-153">The client then returns to the service with the token.</span></span> <span data-ttu-id="ef7a2-154">El servicio examina el token para los datos que permite al servicio autenticar el token y, por consiguiente, al cliente.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-154">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="ef7a2-155">Para autenticar el token, el servicio debe conocer el certificado que usa el servicio de token seguro.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-155">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="ef7a2-156">El [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) elemento es el repositorio para cualquier certificado de servicio de token seguro.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-156">The [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="ef7a2-157">Para agregar certificados, use [\<knownCertificates>](knowncertificates.md) .</span><span class="sxs-lookup"><span data-stu-id="ef7a2-157">To add certificates, use the [\<knownCertificates>](knowncertificates.md).</span></span> <span data-ttu-id="ef7a2-158">Inserte un [ \<add> \<knownCertificates> elemento Element](add-of-knowncertificates.md) para cada certificado, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-158">Insert an [\<add> element \<knownCertificates> Element](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="ef7a2-159">De forma predeterminada, los certificados se deben obtener a partir de un servicio de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-159">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="ef7a2-160">Estos certificados "conocidos" garantizan que solo los clientes legítimos pueden obtener acceso a un servicio.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-160">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="ef7a2-161">Para revisar las condiciones requeridas para que un cliente sea autenticado por un servicio federado, así como más información sobre el uso de este elemento de configuración, consulte [How to: configure Credentials on a servicio de Federación](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="ef7a2-161">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="ef7a2-162">Para obtener más información sobre los escenarios federados, vea [Federación y tokens emitidos](../../../wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="ef7a2-162">For more information about federated scenarios, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef7a2-163">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ef7a2-163">Example</span></span>  
 <span data-ttu-id="ef7a2-164">En el ejemplo siguiente se agrega el certificado al repositorio para todos los certificados STS.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-164">The following example adds certificate to the repository for any STS certificates.</span></span>  
  
```xml  
<serviceBehaviors>
  <behavior name="myServiceBehavior">
    <serviceCredentials>
      <issuedTokenAuthentication>
        <knownCertificates>
          <add findValue="www.contoso.com"
               storeLocation="LocalMachine"
               storeName="CertificateAuthority"
               x509FindType="FindByIssuerName" />
        </knownCertificates>
      </issuedTokenAuthentication>
    </serviceCredentials>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="ef7a2-165">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ef7a2-165">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [\<knownCertificates>](knowncertificates.md)
- [<span data-ttu-id="ef7a2-166">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="ef7a2-166">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="ef7a2-167">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="ef7a2-167">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="ef7a2-168">Procedimiento para configurar las credenciales en un servicio de federación</span><span class="sxs-lookup"><span data-stu-id="ef7a2-168">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="ef7a2-169">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="ef7a2-169">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
