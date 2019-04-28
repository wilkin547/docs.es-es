---
title: <add> de <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 128aaabe-3f1a-4c3b-b59f-898d0f02910f
ms.openlocfilehash: 3eb5bf74f909e6036154b7f5f7c6181b09fefbff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704705"
---
# <a name="add-of-knowncertificates"></a><span data-ttu-id="5f07e-102">\<Agregar > de \<knownCertificates ></span><span class="sxs-lookup"><span data-stu-id="5f07e-102">\<add> of \<knownCertificates></span></span>
<span data-ttu-id="5f07e-103">Agrega un certificado X.509 a la colección de certificados conocidos.</span><span class="sxs-lookup"><span data-stu-id="5f07e-103">Adds an X.509 certificate to the collection of known certificates.</span></span>  
  
 <span data-ttu-id="5f07e-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5f07e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5f07e-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="5f07e-105">\<behaviors></span></span>  
<span data-ttu-id="5f07e-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="5f07e-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="5f07e-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="5f07e-107">\<behavior></span></span>  
<span data-ttu-id="5f07e-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="5f07e-108">\<serviceCredentials></span></span>  
<span data-ttu-id="5f07e-109">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="5f07e-109">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="5f07e-110">\<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="5f07e-110">\<knownCertificates></span></span>  
<span data-ttu-id="5f07e-111">\<add></span><span class="sxs-lookup"><span data-stu-id="5f07e-111">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f07e-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5f07e-112">Syntax</span></span>  
  
```xml  
<knownCertificates>
   <add findValue="String"
      storeLocation="CurrentUser/LocalMachine"
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
      x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5f07e-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5f07e-113">Attributes and Elements</span></span>  
 <span data-ttu-id="5f07e-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5f07e-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5f07e-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="5f07e-115">Attributes</span></span>  
  
|<span data-ttu-id="5f07e-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="5f07e-116">Attribute</span></span>|<span data-ttu-id="5f07e-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="5f07e-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5f07e-118">findValue</span><span class="sxs-lookup"><span data-stu-id="5f07e-118">findValue</span></span>|<span data-ttu-id="5f07e-119">Cadena.</span><span class="sxs-lookup"><span data-stu-id="5f07e-119">String.</span></span> <span data-ttu-id="5f07e-120">Valor que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="5f07e-120">The value to search for.</span></span>|  
|<span data-ttu-id="5f07e-121">storeLocation</span><span class="sxs-lookup"><span data-stu-id="5f07e-121">storeLocation</span></span>|<span data-ttu-id="5f07e-122">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="5f07e-122">Enumeration.</span></span> <span data-ttu-id="5f07e-123">Una de las dos ubicaciones de almacén en que buscar.</span><span class="sxs-lookup"><span data-stu-id="5f07e-123">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="5f07e-124">storeName</span><span class="sxs-lookup"><span data-stu-id="5f07e-124">storeName</span></span>|<span data-ttu-id="5f07e-125">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="5f07e-125">Enumeration.</span></span> <span data-ttu-id="5f07e-126">Uno de los almacenes del sistema en que buscar.</span><span class="sxs-lookup"><span data-stu-id="5f07e-126">One of the system stores to search.</span></span>|  
|<span data-ttu-id="5f07e-127">x509FindType</span><span class="sxs-lookup"><span data-stu-id="5f07e-127">x509FindType</span></span>|<span data-ttu-id="5f07e-128">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="5f07e-128">Enumeration.</span></span> <span data-ttu-id="5f07e-129">Uno de los campos de certificado en que buscar.</span><span class="sxs-lookup"><span data-stu-id="5f07e-129">One of the certificate fields to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="5f07e-130">AtributofindValue</span><span class="sxs-lookup"><span data-stu-id="5f07e-130">findValue Attribute</span></span>  
  
|<span data-ttu-id="5f07e-131">Valor</span><span class="sxs-lookup"><span data-stu-id="5f07e-131">Value</span></span>|<span data-ttu-id="5f07e-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="5f07e-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5f07e-133">String</span><span class="sxs-lookup"><span data-stu-id="5f07e-133">String</span></span>|<span data-ttu-id="5f07e-134">El valor depende del campo (se especifica por el atributo X509FindType) en que se busca.</span><span class="sxs-lookup"><span data-stu-id="5f07e-134">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="5f07e-135">Por ejemplo, si se busca una huella digital, el valor debe ser una cadena de números hexadecimales.</span><span class="sxs-lookup"><span data-stu-id="5f07e-135">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="5f07e-136">Atributo x509FindType</span><span class="sxs-lookup"><span data-stu-id="5f07e-136">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="5f07e-137">Valor</span><span class="sxs-lookup"><span data-stu-id="5f07e-137">Value</span></span>|<span data-ttu-id="5f07e-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="5f07e-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5f07e-139">Enumeración</span><span class="sxs-lookup"><span data-stu-id="5f07e-139">Enumeration</span></span>|<span data-ttu-id="5f07e-140">Estos valores incluyen: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName , FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="5f07e-140">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="5f07e-141">Atributo storeLocation</span><span class="sxs-lookup"><span data-stu-id="5f07e-141">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="5f07e-142">Valor</span><span class="sxs-lookup"><span data-stu-id="5f07e-142">Value</span></span>|<span data-ttu-id="5f07e-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="5f07e-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5f07e-144">Enumeración</span><span class="sxs-lookup"><span data-stu-id="5f07e-144">Enumeration</span></span>|<span data-ttu-id="5f07e-145">CurrentUser o LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="5f07e-145">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="5f07e-146">Atributo storeName</span><span class="sxs-lookup"><span data-stu-id="5f07e-146">storeName Attribute</span></span>  
  
|<span data-ttu-id="5f07e-147">Valor</span><span class="sxs-lookup"><span data-stu-id="5f07e-147">Value</span></span>|<span data-ttu-id="5f07e-148">Descripción</span><span class="sxs-lookup"><span data-stu-id="5f07e-148">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5f07e-149">Enumeración</span><span class="sxs-lookup"><span data-stu-id="5f07e-149">Enumeration</span></span>|<span data-ttu-id="5f07e-150">Estos valores incluyen: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople y TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="5f07e-150">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5f07e-151">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5f07e-151">Child Elements</span></span>  
 <span data-ttu-id="5f07e-152">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5f07e-152">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5f07e-153">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5f07e-153">Parent Elements</span></span>  
  
|<span data-ttu-id="5f07e-154">Elemento</span><span class="sxs-lookup"><span data-stu-id="5f07e-154">Element</span></span>|<span data-ttu-id="5f07e-155">Descripción</span><span class="sxs-lookup"><span data-stu-id="5f07e-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5f07e-156">\<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="5f07e-156">\<knownCertificates></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md)|<span data-ttu-id="5f07e-157">Representa una colección de certificados X.509 que se proporcionan por un servicio de token de seguridad (STS) para la validación de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5f07e-157">Represents a collection of X.509 certificates that are provided by a Security Token Service (STS) for validation of security tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5f07e-158">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5f07e-158">Remarks</span></span>  
 <span data-ttu-id="5f07e-159">El escenario del token emitido tiene tres etapas.</span><span class="sxs-lookup"><span data-stu-id="5f07e-159">The issued token scenario has three stages.</span></span> <span data-ttu-id="5f07e-160">En la primera fase, un cliente intenta tener acceso a un servicio se conoce un *servicio de token seguro*.</span><span class="sxs-lookup"><span data-stu-id="5f07e-160">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="5f07e-161">El servicio de token seguro autentica, a continuación, al cliente y como consecuencia el cliente emite un token, normalmente un token del lenguaje de marcado de aserción de seguridad (SAML).</span><span class="sxs-lookup"><span data-stu-id="5f07e-161">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="5f07e-162">El cliente vuelve a continuación al servicio con el token.</span><span class="sxs-lookup"><span data-stu-id="5f07e-162">The client then returns to the service with the token.</span></span> <span data-ttu-id="5f07e-163">El servicio examina el token para los datos que permite al servicio autenticar el token y, por consiguiente, al cliente.</span><span class="sxs-lookup"><span data-stu-id="5f07e-163">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="5f07e-164">Para autenticar el token, el servicio debe conocer el certificado que usa el servicio de token seguro.</span><span class="sxs-lookup"><span data-stu-id="5f07e-164">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="5f07e-165">El [ \<issuedTokenAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) elemento es el repositorio de estos certificados, cualquier servicio de token seguro.</span><span class="sxs-lookup"><span data-stu-id="5f07e-165">The [\<issuedTokenAuthentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="5f07e-166">Para agregar certificados, use el [ \<knownCertificates >](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="5f07e-166">To add certificates, use the [\<knownCertificates>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span></span> <span data-ttu-id="5f07e-167">Insertar un [ \<Agregar > elemento \<knownCertificates > elemento](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) para cada certificado, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="5f07e-167">Insert an [\<add> element \<knownCertificates> Element](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="5f07e-168">De forma predeterminada, los certificados se deben obtener a partir de un servicio de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5f07e-168">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="5f07e-169">Estos certificados "conocidos" garantizan que solo los clientes legítimos pueden obtener acceso a un servicio.</span><span class="sxs-lookup"><span data-stu-id="5f07e-169">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="5f07e-170">Para revisar condiciones requeridas para que un cliente se autentique mediante un servicio federado, así como para obtener más información sobre el uso de este elemento de configuración, vea [Cómo: Configurar las credenciales en un servicio de federación](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="5f07e-170">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="5f07e-171">Para obtener más información acerca de los escenarios federados, vea [federación y Tokens emitidos](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="5f07e-171">For more information about federated scenarios, see [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f07e-172">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5f07e-172">Example</span></span>  
 <span data-ttu-id="5f07e-173">En el ejemplo siguiente se agrega el certificado al repositorio para todos los certificados STS.</span><span class="sxs-lookup"><span data-stu-id="5f07e-173">The following example adds certificate to the repository for any STS certificates.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5f07e-174">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f07e-174">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [<span data-ttu-id="5f07e-175">\<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="5f07e-175">\<knownCertificates></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md)
- [<span data-ttu-id="5f07e-176">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="5f07e-176">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="5f07e-177">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="5f07e-177">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="5f07e-178">Cómo: Configurar las credenciales en un servicio de federación</span><span class="sxs-lookup"><span data-stu-id="5f07e-178">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="5f07e-179">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="5f07e-179">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
