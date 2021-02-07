---
description: 'Más información sobre: <add> de <knownCertificates>'
title: <add> de <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 128aaabe-3f1a-4c3b-b59f-898d0f02910f
ms.openlocfilehash: 1669495e6119a35543e39230fc5dcc986ee2dec5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99750291"
---
# <a name="add-of-knowncertificates"></a><span data-ttu-id="3d32d-103">\<add> de \<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="3d32d-103">\<add> of \<knownCertificates></span></span>

<span data-ttu-id="3d32d-104">Agrega un certificado X.509 a la colección de certificados conocidos.</span><span class="sxs-lookup"><span data-stu-id="3d32d-104">Adds an X.509 certificate to the collection of known certificates.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenAuthentication>**](issuedtokenauthentication-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<knownCertificates>**](knowncertificates.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="3d32d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3d32d-105">Syntax</span></span>  
  
```xml  
<knownCertificates>
   <add findValue="String"
      storeLocation="CurrentUser/LocalMachine"
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
      x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3d32d-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3d32d-106">Attributes and Elements</span></span>  

 <span data-ttu-id="3d32d-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3d32d-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3d32d-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="3d32d-108">Attributes</span></span>  
  
|<span data-ttu-id="3d32d-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="3d32d-109">Attribute</span></span>|<span data-ttu-id="3d32d-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="3d32d-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3d32d-111">findValue</span><span class="sxs-lookup"><span data-stu-id="3d32d-111">findValue</span></span>|<span data-ttu-id="3d32d-112">String.</span><span class="sxs-lookup"><span data-stu-id="3d32d-112">String.</span></span> <span data-ttu-id="3d32d-113">Valor que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="3d32d-113">The value to search for.</span></span>|  
|<span data-ttu-id="3d32d-114">storeLocation</span><span class="sxs-lookup"><span data-stu-id="3d32d-114">storeLocation</span></span>|<span data-ttu-id="3d32d-115">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="3d32d-115">Enumeration.</span></span> <span data-ttu-id="3d32d-116">Una de las dos ubicaciones de almacén en que buscar.</span><span class="sxs-lookup"><span data-stu-id="3d32d-116">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="3d32d-117">storeName</span><span class="sxs-lookup"><span data-stu-id="3d32d-117">storeName</span></span>|<span data-ttu-id="3d32d-118">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="3d32d-118">Enumeration.</span></span> <span data-ttu-id="3d32d-119">Uno de los almacenes del sistema en que buscar.</span><span class="sxs-lookup"><span data-stu-id="3d32d-119">One of the system stores to search.</span></span>|  
|<span data-ttu-id="3d32d-120">x509FindType</span><span class="sxs-lookup"><span data-stu-id="3d32d-120">x509FindType</span></span>|<span data-ttu-id="3d32d-121">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="3d32d-121">Enumeration.</span></span> <span data-ttu-id="3d32d-122">Uno de los campos de certificado en que buscar.</span><span class="sxs-lookup"><span data-stu-id="3d32d-122">One of the certificate fields to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="3d32d-123">AtributofindValue</span><span class="sxs-lookup"><span data-stu-id="3d32d-123">findValue Attribute</span></span>  
  
|<span data-ttu-id="3d32d-124">Value</span><span class="sxs-lookup"><span data-stu-id="3d32d-124">Value</span></span>|<span data-ttu-id="3d32d-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="3d32d-125">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3d32d-126">String</span><span class="sxs-lookup"><span data-stu-id="3d32d-126">String</span></span>|<span data-ttu-id="3d32d-127">El valor depende del campo (se especifica por el atributo X509FindType) en que se busca.</span><span class="sxs-lookup"><span data-stu-id="3d32d-127">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="3d32d-128">Por ejemplo, si se busca una huella digital, el valor debe ser una cadena de números hexadecimales.</span><span class="sxs-lookup"><span data-stu-id="3d32d-128">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="3d32d-129">Atributo x509FindType</span><span class="sxs-lookup"><span data-stu-id="3d32d-129">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="3d32d-130">Value</span><span class="sxs-lookup"><span data-stu-id="3d32d-130">Value</span></span>|<span data-ttu-id="3d32d-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="3d32d-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3d32d-132">Enumeración</span><span class="sxs-lookup"><span data-stu-id="3d32d-132">Enumeration</span></span>|<span data-ttu-id="3d32d-133">Los valores incluyen: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="3d32d-133">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="3d32d-134">Atributo storeLocation</span><span class="sxs-lookup"><span data-stu-id="3d32d-134">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="3d32d-135">Value</span><span class="sxs-lookup"><span data-stu-id="3d32d-135">Value</span></span>|<span data-ttu-id="3d32d-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="3d32d-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3d32d-137">Enumeración</span><span class="sxs-lookup"><span data-stu-id="3d32d-137">Enumeration</span></span>|<span data-ttu-id="3d32d-138">CurrentUser o LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="3d32d-138">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="3d32d-139">Atributo storeName</span><span class="sxs-lookup"><span data-stu-id="3d32d-139">storeName Attribute</span></span>  
  
|<span data-ttu-id="3d32d-140">Value</span><span class="sxs-lookup"><span data-stu-id="3d32d-140">Value</span></span>|<span data-ttu-id="3d32d-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="3d32d-141">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3d32d-142">Enumeración</span><span class="sxs-lookup"><span data-stu-id="3d32d-142">Enumeration</span></span>|<span data-ttu-id="3d32d-143">Los valores incluyen: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, y TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="3d32d-143">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3d32d-144">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3d32d-144">Child Elements</span></span>  

 <span data-ttu-id="3d32d-145">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3d32d-145">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3d32d-146">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3d32d-146">Parent Elements</span></span>  
  
|<span data-ttu-id="3d32d-147">Elemento</span><span class="sxs-lookup"><span data-stu-id="3d32d-147">Element</span></span>|<span data-ttu-id="3d32d-148">Descripción</span><span class="sxs-lookup"><span data-stu-id="3d32d-148">Description</span></span>|  
|-------------|-----------------|  
|[\<knownCertificates>](knowncertificates.md)|<span data-ttu-id="3d32d-149">Representa una colección de certificados X.509 que se proporcionan por un servicio de token de seguridad (STS) para la validación de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="3d32d-149">Represents a collection of X.509 certificates that are provided by a Security Token Service (STS) for validation of security tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d32d-150">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3d32d-150">Remarks</span></span>  

 <span data-ttu-id="3d32d-151">El escenario del token emitido tiene tres etapas.</span><span class="sxs-lookup"><span data-stu-id="3d32d-151">The issued token scenario has three stages.</span></span> <span data-ttu-id="3d32d-152">En la primera fase, un cliente que intenta tener acceso a un servicio se conoce como *servicio de token seguro*.</span><span class="sxs-lookup"><span data-stu-id="3d32d-152">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="3d32d-153">El servicio de token seguro autentica, a continuación, al cliente y como consecuencia el cliente emite un token, normalmente un token del lenguaje de marcado de aserción de seguridad (SAML).</span><span class="sxs-lookup"><span data-stu-id="3d32d-153">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="3d32d-154">El cliente vuelve a continuación al servicio con el token.</span><span class="sxs-lookup"><span data-stu-id="3d32d-154">The client then returns to the service with the token.</span></span> <span data-ttu-id="3d32d-155">El servicio examina el token para los datos que permite al servicio autenticar el token y, por consiguiente, al cliente.</span><span class="sxs-lookup"><span data-stu-id="3d32d-155">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="3d32d-156">Para autenticar el token, el servicio debe conocer el certificado que usa el servicio de token seguro.</span><span class="sxs-lookup"><span data-stu-id="3d32d-156">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="3d32d-157">El [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) elemento es el repositorio para cualquier certificado de servicio de token seguro.</span><span class="sxs-lookup"><span data-stu-id="3d32d-157">The [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="3d32d-158">Para agregar certificados, use [\<knownCertificates>](knowncertificates.md) .</span><span class="sxs-lookup"><span data-stu-id="3d32d-158">To add certificates, use the [\<knownCertificates>](knowncertificates.md).</span></span> <span data-ttu-id="3d32d-159">Inserte un [ \<add> \<knownCertificates> elemento Element](add-of-knowncertificates.md) para cada certificado, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="3d32d-159">Insert an [\<add> element \<knownCertificates> Element](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="3d32d-160">De forma predeterminada, los certificados se deben obtener a partir de un servicio de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="3d32d-160">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="3d32d-161">Estos certificados "conocidos" garantizan que solo los clientes legítimos pueden obtener acceso a un servicio.</span><span class="sxs-lookup"><span data-stu-id="3d32d-161">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="3d32d-162">Para revisar las condiciones requeridas para que un cliente sea autenticado por un servicio federado, así como más información sobre el uso de este elemento de configuración, consulte [How to: configure Credentials on a servicio de Federación](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="3d32d-162">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="3d32d-163">Para obtener más información sobre los escenarios federados, vea [Federación y tokens emitidos](../../../wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="3d32d-163">For more information about federated scenarios, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d32d-164">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3d32d-164">Example</span></span>  

 <span data-ttu-id="3d32d-165">En el ejemplo siguiente se agrega el certificado al repositorio para todos los certificados STS.</span><span class="sxs-lookup"><span data-stu-id="3d32d-165">The following example adds certificate to the repository for any STS certificates.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3d32d-166">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d32d-166">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [\<knownCertificates>](knowncertificates.md)
- [<span data-ttu-id="3d32d-167">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="3d32d-167">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="3d32d-168">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="3d32d-168">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="3d32d-169">Procedimiento para configurar las credenciales en un servicio de federación</span><span class="sxs-lookup"><span data-stu-id="3d32d-169">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="3d32d-170">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="3d32d-170">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
