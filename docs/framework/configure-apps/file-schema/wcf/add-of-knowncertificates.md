---
title: <add> de <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 128aaabe-3f1a-4c3b-b59f-898d0f02910f
ms.openlocfilehash: 29b067e6ec20992084f9ab3bab087222bdd56da2
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400622"
---
# <a name="add-of-knowncertificates"></a><span data-ttu-id="5cb6c-102">\<Agregar > de \<knownCertificates ></span><span class="sxs-lookup"><span data-stu-id="5cb6c-102">\<add> of \<knownCertificates></span></span>
<span data-ttu-id="5cb6c-103">Agrega un certificado X.509 a la colección de certificados conocidos.</span><span class="sxs-lookup"><span data-stu-id="5cb6c-103">Adds an X.509 certificate to the collection of known certificates.</span></span>  
  
<span data-ttu-id="5cb6c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5cb6c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5cb6c-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="5cb6c-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="5cb6c-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="5cb6c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="5cb6c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="5cb6c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="5cb6c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="5cb6c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="5cb6c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de serviceCredentials**](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="5cb6c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="5cb6c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> issuedTokenAuthentication**](issuedtokenauthentication-of-servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="5cb6c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenAuthentication>**](issuedtokenauthentication-of-servicecredentials.md)</span></span>\
<span data-ttu-id="5cb6c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> knownCertificates**](knowncertificates.md)</span><span class="sxs-lookup"><span data-stu-id="5cb6c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<knownCertificates>**](knowncertificates.md)</span></span>\
<span data-ttu-id="5cb6c-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Agregar >**</span><span class="sxs-lookup"><span data-stu-id="5cb6c-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cb6c-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5cb6c-113">Syntax</span></span>  
  
```xml  
<knownCertificates>
   <add findValue="String"
      storeLocation="CurrentUser/LocalMachine"
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
      x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5cb6c-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5cb6c-114">Attributes and Elements</span></span>  
 <span data-ttu-id="5cb6c-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5cb6c-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5cb6c-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="5cb6c-116">Attributes</span></span>  
  
|<span data-ttu-id="5cb6c-117">Atributo</span><span class="sxs-lookup"><span data-stu-id="5cb6c-117">Attribute</span></span>|<span data-ttu-id="5cb6c-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5cb6c-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5cb6c-119">findValue</span><span class="sxs-lookup"><span data-stu-id="5cb6c-119">findValue</span></span>|<span data-ttu-id="5cb6c-120">Cadena.</span><span class="sxs-lookup"><span data-stu-id="5cb6c-120">String.</span></span> <span data-ttu-id="5cb6c-121">Valor que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="5cb6c-121">The value to search for.</span></span>|  
|<span data-ttu-id="5cb6c-122">storeLocation</span><span class="sxs-lookup"><span data-stu-id="5cb6c-122">storeLocation</span></span>|<span data-ttu-id="5cb6c-123">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="5cb6c-123">Enumeration.</span></span> <span data-ttu-id="5cb6c-124">Una de las dos ubicaciones de almacén en que buscar.</span><span class="sxs-lookup"><span data-stu-id="5cb6c-124">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="5cb6c-125">storeName</span><span class="sxs-lookup"><span data-stu-id="5cb6c-125">storeName</span></span>|<span data-ttu-id="5cb6c-126">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="5cb6c-126">Enumeration.</span></span> <span data-ttu-id="5cb6c-127">Uno de los almacenes del sistema en que buscar.</span><span class="sxs-lookup"><span data-stu-id="5cb6c-127">One of the system stores to search.</span></span>|  
|<span data-ttu-id="5cb6c-128">x509FindType</span><span class="sxs-lookup"><span data-stu-id="5cb6c-128">x509FindType</span></span>|<span data-ttu-id="5cb6c-129">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="5cb6c-129">Enumeration.</span></span> <span data-ttu-id="5cb6c-130">Uno de los campos de certificado en que buscar.</span><span class="sxs-lookup"><span data-stu-id="5cb6c-130">One of the certificate fields to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="5cb6c-131">AtributofindValue</span><span class="sxs-lookup"><span data-stu-id="5cb6c-131">findValue Attribute</span></span>  
  
|<span data-ttu-id="5cb6c-132">Valor</span><span class="sxs-lookup"><span data-stu-id="5cb6c-132">Value</span></span>|<span data-ttu-id="5cb6c-133">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5cb6c-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5cb6c-134">string</span><span class="sxs-lookup"><span data-stu-id="5cb6c-134">String</span></span>|<span data-ttu-id="5cb6c-135">El valor depende del campo (se especifica por el atributo X509FindType) en que se busca.</span><span class="sxs-lookup"><span data-stu-id="5cb6c-135">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="5cb6c-136">Por ejemplo, si se busca una huella digital, el valor debe ser una cadena de números hexadecimales.</span><span class="sxs-lookup"><span data-stu-id="5cb6c-136">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="5cb6c-137">Atributo x509FindType</span><span class="sxs-lookup"><span data-stu-id="5cb6c-137">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="5cb6c-138">Valor</span><span class="sxs-lookup"><span data-stu-id="5cb6c-138">Value</span></span>|<span data-ttu-id="5cb6c-139">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5cb6c-139">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5cb6c-140">Enumeración</span><span class="sxs-lookup"><span data-stu-id="5cb6c-140">Enumeration</span></span>|<span data-ttu-id="5cb6c-141">Estos valores incluyen: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName , FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="5cb6c-141">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="5cb6c-142">Atributo storeLocation</span><span class="sxs-lookup"><span data-stu-id="5cb6c-142">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="5cb6c-143">Value</span><span class="sxs-lookup"><span data-stu-id="5cb6c-143">Value</span></span>|<span data-ttu-id="5cb6c-144">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5cb6c-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5cb6c-145">Enumeración</span><span class="sxs-lookup"><span data-stu-id="5cb6c-145">Enumeration</span></span>|<span data-ttu-id="5cb6c-146">CurrentUser o LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="5cb6c-146">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="5cb6c-147">Atributo storeName</span><span class="sxs-lookup"><span data-stu-id="5cb6c-147">storeName Attribute</span></span>  
  
|<span data-ttu-id="5cb6c-148">Value</span><span class="sxs-lookup"><span data-stu-id="5cb6c-148">Value</span></span>|<span data-ttu-id="5cb6c-149">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5cb6c-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5cb6c-150">Enumeración</span><span class="sxs-lookup"><span data-stu-id="5cb6c-150">Enumeration</span></span>|<span data-ttu-id="5cb6c-151">Estos valores incluyen: AddressBook, AuthRoot, CertificateAuthority, no permitido, My, root, TrustedPeople y TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="5cb6c-151">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5cb6c-152">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5cb6c-152">Child Elements</span></span>  
 <span data-ttu-id="5cb6c-153">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5cb6c-153">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5cb6c-154">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5cb6c-154">Parent Elements</span></span>  
  
|<span data-ttu-id="5cb6c-155">Elemento</span><span class="sxs-lookup"><span data-stu-id="5cb6c-155">Element</span></span>|<span data-ttu-id="5cb6c-156">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5cb6c-156">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5cb6c-157">\<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="5cb6c-157">\<knownCertificates></span></span>](knowncertificates.md)|<span data-ttu-id="5cb6c-158">Representa una colección de certificados X.509 que se proporcionan por un servicio de token de seguridad (STS) para la validación de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5cb6c-158">Represents a collection of X.509 certificates that are provided by a Security Token Service (STS) for validation of security tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5cb6c-159">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5cb6c-159">Remarks</span></span>  
 <span data-ttu-id="5cb6c-160">El escenario del token emitido tiene tres etapas.</span><span class="sxs-lookup"><span data-stu-id="5cb6c-160">The issued token scenario has three stages.</span></span> <span data-ttu-id="5cb6c-161">En la primera fase, un cliente que intenta tener acceso a un servicio se conoce como *servicio de token seguro*.</span><span class="sxs-lookup"><span data-stu-id="5cb6c-161">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="5cb6c-162">El servicio de token seguro autentica, a continuación, al cliente y como consecuencia el cliente emite un token, normalmente un token del lenguaje de marcado de aserción de seguridad (SAML).</span><span class="sxs-lookup"><span data-stu-id="5cb6c-162">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="5cb6c-163">El cliente vuelve a continuación al servicio con el token.</span><span class="sxs-lookup"><span data-stu-id="5cb6c-163">The client then returns to the service with the token.</span></span> <span data-ttu-id="5cb6c-164">El servicio examina el token para los datos que permite al servicio autenticar el token y, por consiguiente, al cliente.</span><span class="sxs-lookup"><span data-stu-id="5cb6c-164">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="5cb6c-165">Para autenticar el token, el servicio debe conocer el certificado que usa el servicio de token seguro.</span><span class="sxs-lookup"><span data-stu-id="5cb6c-165">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="5cb6c-166">El elemento > issuedTokenAuthentication es el repositorio para cualquier certificado de servicio de token seguro. [ \<](issuedtokenauthentication-of-servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="5cb6c-166">The [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="5cb6c-167">Para agregar certificados, use el [ \<> knownCertificates](knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="5cb6c-167">To add certificates, use the [\<knownCertificates>](knowncertificates.md).</span></span> <span data-ttu-id="5cb6c-168">Inserte un [ \<elemento Add > \<Element knownCertificates >](add-of-knowncertificates.md) para cada certificado, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="5cb6c-168">Insert an [\<add> element \<knownCertificates> Element](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="5cb6c-169">De forma predeterminada, los certificados se deben obtener a partir de un servicio de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5cb6c-169">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="5cb6c-170">Estos certificados "conocidos" garantizan que solo los clientes legítimos pueden obtener acceso a un servicio.</span><span class="sxs-lookup"><span data-stu-id="5cb6c-170">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="5cb6c-171">Para revisar las condiciones requeridas para que un cliente sea autenticado por un servicio federado, así como más información sobre el uso de este [elemento de configuración, consulte Cómo: Configure las credenciales](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)en un servicio de Federación.</span><span class="sxs-lookup"><span data-stu-id="5cb6c-171">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="5cb6c-172">Para obtener más información sobre los escenarios federados, vea [Federación y tokens emitidos](../../../wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="5cb6c-172">For more information about federated scenarios, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5cb6c-173">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5cb6c-173">Example</span></span>  
 <span data-ttu-id="5cb6c-174">En el ejemplo siguiente se agrega el certificado al repositorio para todos los certificados STS.</span><span class="sxs-lookup"><span data-stu-id="5cb6c-174">The following example adds certificate to the repository for any STS certificates.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5cb6c-175">Vea también</span><span class="sxs-lookup"><span data-stu-id="5cb6c-175">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [<span data-ttu-id="5cb6c-176">\<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="5cb6c-176">\<knownCertificates></span></span>](knowncertificates.md)
- [<span data-ttu-id="5cb6c-177">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="5cb6c-177">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="5cb6c-178">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="5cb6c-178">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="5cb6c-179">Cómo: Configurar credenciales en un Servicio de federación</span><span class="sxs-lookup"><span data-stu-id="5cb6c-179">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="5cb6c-180">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="5cb6c-180">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
