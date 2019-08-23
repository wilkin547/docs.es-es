---
title: <add> de <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 128aaabe-3f1a-4c3b-b59f-898d0f02910f
ms.openlocfilehash: 939718e8dacca2698b6f71a3bdc1262a5dc3ee20
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926678"
---
# <a name="add-of-knowncertificates"></a><span data-ttu-id="b605c-102">\<Agregar > de \<knownCertificates ></span><span class="sxs-lookup"><span data-stu-id="b605c-102">\<add> of \<knownCertificates></span></span>
<span data-ttu-id="b605c-103">Agrega un certificado X.509 a la colección de certificados conocidos.</span><span class="sxs-lookup"><span data-stu-id="b605c-103">Adds an X.509 certificate to the collection of known certificates.</span></span>  
  
 <span data-ttu-id="b605c-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b605c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b605c-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="b605c-105">\<behaviors></span></span>  
<span data-ttu-id="b605c-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="b605c-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="b605c-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="b605c-107">\<behavior></span></span>  
<span data-ttu-id="b605c-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="b605c-108">\<serviceCredentials></span></span>  
<span data-ttu-id="b605c-109">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="b605c-109">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="b605c-110">\<> knownCertificates</span><span class="sxs-lookup"><span data-stu-id="b605c-110">\<knownCertificates></span></span>  
<span data-ttu-id="b605c-111">\<add></span><span class="sxs-lookup"><span data-stu-id="b605c-111">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b605c-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b605c-112">Syntax</span></span>  
  
```xml  
<knownCertificates>
   <add findValue="String"
      storeLocation="CurrentUser/LocalMachine"
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
      x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b605c-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b605c-113">Attributes and Elements</span></span>  
 <span data-ttu-id="b605c-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b605c-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b605c-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="b605c-115">Attributes</span></span>  
  
|<span data-ttu-id="b605c-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="b605c-116">Attribute</span></span>|<span data-ttu-id="b605c-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b605c-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b605c-118">findValue</span><span class="sxs-lookup"><span data-stu-id="b605c-118">findValue</span></span>|<span data-ttu-id="b605c-119">Cadena.</span><span class="sxs-lookup"><span data-stu-id="b605c-119">String.</span></span> <span data-ttu-id="b605c-120">Valor que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="b605c-120">The value to search for.</span></span>|  
|<span data-ttu-id="b605c-121">storeLocation</span><span class="sxs-lookup"><span data-stu-id="b605c-121">storeLocation</span></span>|<span data-ttu-id="b605c-122">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="b605c-122">Enumeration.</span></span> <span data-ttu-id="b605c-123">Una de las dos ubicaciones de almacén en que buscar.</span><span class="sxs-lookup"><span data-stu-id="b605c-123">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="b605c-124">storeName</span><span class="sxs-lookup"><span data-stu-id="b605c-124">storeName</span></span>|<span data-ttu-id="b605c-125">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="b605c-125">Enumeration.</span></span> <span data-ttu-id="b605c-126">Uno de los almacenes del sistema en que buscar.</span><span class="sxs-lookup"><span data-stu-id="b605c-126">One of the system stores to search.</span></span>|  
|<span data-ttu-id="b605c-127">x509FindType</span><span class="sxs-lookup"><span data-stu-id="b605c-127">x509FindType</span></span>|<span data-ttu-id="b605c-128">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="b605c-128">Enumeration.</span></span> <span data-ttu-id="b605c-129">Uno de los campos de certificado en que buscar.</span><span class="sxs-lookup"><span data-stu-id="b605c-129">One of the certificate fields to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="b605c-130">AtributofindValue</span><span class="sxs-lookup"><span data-stu-id="b605c-130">findValue Attribute</span></span>  
  
|<span data-ttu-id="b605c-131">Valor</span><span class="sxs-lookup"><span data-stu-id="b605c-131">Value</span></span>|<span data-ttu-id="b605c-132">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b605c-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b605c-133">string</span><span class="sxs-lookup"><span data-stu-id="b605c-133">String</span></span>|<span data-ttu-id="b605c-134">El valor depende del campo (se especifica por el atributo X509FindType) en que se busca.</span><span class="sxs-lookup"><span data-stu-id="b605c-134">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="b605c-135">Por ejemplo, si se busca una huella digital, el valor debe ser una cadena de números hexadecimales.</span><span class="sxs-lookup"><span data-stu-id="b605c-135">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="b605c-136">Atributo x509FindType</span><span class="sxs-lookup"><span data-stu-id="b605c-136">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="b605c-137">Value</span><span class="sxs-lookup"><span data-stu-id="b605c-137">Value</span></span>|<span data-ttu-id="b605c-138">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b605c-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b605c-139">Enumeración</span><span class="sxs-lookup"><span data-stu-id="b605c-139">Enumeration</span></span>|<span data-ttu-id="b605c-140">Estos valores incluyen: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName , FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="b605c-140">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="b605c-141">Atributo storeLocation</span><span class="sxs-lookup"><span data-stu-id="b605c-141">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="b605c-142">Valor</span><span class="sxs-lookup"><span data-stu-id="b605c-142">Value</span></span>|<span data-ttu-id="b605c-143">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b605c-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b605c-144">Enumeración</span><span class="sxs-lookup"><span data-stu-id="b605c-144">Enumeration</span></span>|<span data-ttu-id="b605c-145">CurrentUser o LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="b605c-145">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="b605c-146">Atributo storeName</span><span class="sxs-lookup"><span data-stu-id="b605c-146">storeName Attribute</span></span>  
  
|<span data-ttu-id="b605c-147">Value</span><span class="sxs-lookup"><span data-stu-id="b605c-147">Value</span></span>|<span data-ttu-id="b605c-148">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b605c-148">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b605c-149">Enumeración</span><span class="sxs-lookup"><span data-stu-id="b605c-149">Enumeration</span></span>|<span data-ttu-id="b605c-150">Estos valores incluyen: AddressBook, AuthRoot, CertificateAuthority, no permitido, My, root, TrustedPeople y TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="b605c-150">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b605c-151">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b605c-151">Child Elements</span></span>  
 <span data-ttu-id="b605c-152">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b605c-152">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b605c-153">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b605c-153">Parent Elements</span></span>  
  
|<span data-ttu-id="b605c-154">Elemento</span><span class="sxs-lookup"><span data-stu-id="b605c-154">Element</span></span>|<span data-ttu-id="b605c-155">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b605c-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b605c-156">\<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="b605c-156">\<knownCertificates></span></span>](knowncertificates.md)|<span data-ttu-id="b605c-157">Representa una colección de certificados X.509 que se proporcionan por un servicio de token de seguridad (STS) para la validación de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b605c-157">Represents a collection of X.509 certificates that are provided by a Security Token Service (STS) for validation of security tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b605c-158">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b605c-158">Remarks</span></span>  
 <span data-ttu-id="b605c-159">El escenario del token emitido tiene tres etapas.</span><span class="sxs-lookup"><span data-stu-id="b605c-159">The issued token scenario has three stages.</span></span> <span data-ttu-id="b605c-160">En la primera fase, un cliente que intenta tener acceso a un servicio se conoce como *servicio de token seguro*.</span><span class="sxs-lookup"><span data-stu-id="b605c-160">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="b605c-161">El servicio de token seguro autentica, a continuación, al cliente y como consecuencia el cliente emite un token, normalmente un token del lenguaje de marcado de aserción de seguridad (SAML).</span><span class="sxs-lookup"><span data-stu-id="b605c-161">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="b605c-162">El cliente vuelve a continuación al servicio con el token.</span><span class="sxs-lookup"><span data-stu-id="b605c-162">The client then returns to the service with the token.</span></span> <span data-ttu-id="b605c-163">El servicio examina el token para los datos que permite al servicio autenticar el token y, por consiguiente, al cliente.</span><span class="sxs-lookup"><span data-stu-id="b605c-163">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="b605c-164">Para autenticar el token, el servicio debe conocer el certificado que usa el servicio de token seguro.</span><span class="sxs-lookup"><span data-stu-id="b605c-164">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="b605c-165">El elemento > issuedTokenAuthentication es el repositorio para cualquier certificado de servicio de token seguro. [ \<](issuedtokenauthentication-of-servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="b605c-165">The [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="b605c-166">Para agregar certificados, use el [ \<> knownCertificates](knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="b605c-166">To add certificates, use the [\<knownCertificates>](knowncertificates.md).</span></span> <span data-ttu-id="b605c-167">Inserte un [ \<elemento Add > \<Element knownCertificates >](add-of-knowncertificates.md) para cada certificado, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="b605c-167">Insert an [\<add> element \<knownCertificates> Element](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="b605c-168">De forma predeterminada, los certificados se deben obtener a partir de un servicio de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b605c-168">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="b605c-169">Estos certificados "conocidos" garantizan que solo los clientes legítimos pueden obtener acceso a un servicio.</span><span class="sxs-lookup"><span data-stu-id="b605c-169">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="b605c-170">Para revisar las condiciones requeridas para que un cliente sea autenticado por un servicio federado, así como más información sobre el uso de este [elemento de configuración, consulte Cómo: Configure las credenciales](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)en un servicio de Federación.</span><span class="sxs-lookup"><span data-stu-id="b605c-170">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="b605c-171">Para obtener más información sobre los escenarios federados, vea [Federación y tokens emitidos](../../../wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="b605c-171">For more information about federated scenarios, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b605c-172">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b605c-172">Example</span></span>  
 <span data-ttu-id="b605c-173">En el ejemplo siguiente se agrega el certificado al repositorio para todos los certificados STS.</span><span class="sxs-lookup"><span data-stu-id="b605c-173">The following example adds certificate to the repository for any STS certificates.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b605c-174">Vea también</span><span class="sxs-lookup"><span data-stu-id="b605c-174">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [<span data-ttu-id="b605c-175">\<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="b605c-175">\<knownCertificates></span></span>](knowncertificates.md)
- [<span data-ttu-id="b605c-176">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="b605c-176">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="b605c-177">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="b605c-177">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="b605c-178">Procedimientos: Configurar credenciales en un Servicio de federación</span><span class="sxs-lookup"><span data-stu-id="b605c-178">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="b605c-179">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="b605c-179">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
