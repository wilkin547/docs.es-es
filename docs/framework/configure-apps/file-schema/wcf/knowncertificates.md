---
title: '&lt;knownCertificates&gt;'
ms.date: 03/30/2017
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
ms.openlocfilehash: 394ae246ad29a0747f3814b36fae2557b04c235a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltknowncertificatesgt"></a><span data-ttu-id="03953-102">&lt;knownCertificates&gt;</span><span class="sxs-lookup"><span data-stu-id="03953-102">&lt;knownCertificates&gt;</span></span>
<span data-ttu-id="03953-103">Representa una colección de certificados X.509 que se proporcionan para autenticar las credenciales de seguridad emitidas desde un Servicio de token de seguridad (STS).</span><span class="sxs-lookup"><span data-stu-id="03953-103">Represents a collection of X.509 certificates that are provided to authenticate security credentials issued from a Security Token Service (STS).</span></span>  
  
 <span data-ttu-id="03953-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="03953-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="03953-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="03953-105">\<behaviors></span></span>  
<span data-ttu-id="03953-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="03953-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="03953-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="03953-107">\<behavior></span></span>  
<span data-ttu-id="03953-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="03953-108">\<serviceCredentials></span></span>  
<span data-ttu-id="03953-109">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="03953-109">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="03953-110">\<knownCertificates ></span><span class="sxs-lookup"><span data-stu-id="03953-110">\<knownCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03953-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="03953-111">Syntax</span></span>  
  
```xml  
<knownCertificates>   
      <add findValue="String"  
         storeLocation="CurrentUser/LocalMachine"  
          storeName=" CurrentUser/LocalMachine"  
           x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>  
</knownCertificates>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03953-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="03953-112">Attributes and Elements</span></span>  
 <span data-ttu-id="03953-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="03953-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03953-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="03953-114">Attributes</span></span>  
 <span data-ttu-id="03953-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="03953-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="03953-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="03953-116">Child Elements</span></span>  
  
|<span data-ttu-id="03953-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="03953-117">Element</span></span>|<span data-ttu-id="03953-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="03953-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="03953-119">\<add></span><span class="sxs-lookup"><span data-stu-id="03953-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)|<span data-ttu-id="03953-120">Agrega un certificado X.509 a la colección.</span><span class="sxs-lookup"><span data-stu-id="03953-120">Adds an X.509 certificate to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="03953-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="03953-121">Parent Elements</span></span>  
  
|<span data-ttu-id="03953-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="03953-122">Element</span></span>|<span data-ttu-id="03953-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="03953-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="03953-124">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="03953-124">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="03953-125">Especifica un token emitido como una credencial del servicio.</span><span class="sxs-lookup"><span data-stu-id="03953-125">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03953-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="03953-126">Remarks</span></span>  
 <span data-ttu-id="03953-127">El escenario del token emitido tiene tres etapas.</span><span class="sxs-lookup"><span data-stu-id="03953-127">The issued token scenario has three stages.</span></span> <span data-ttu-id="03953-128">En la primera fase, un cliente intenta tener acceso a un servicio se remite a un *del servicio de token seguro*.</span><span class="sxs-lookup"><span data-stu-id="03953-128">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="03953-129">El servicio de token seguro autentica, a continuación, al cliente y como consecuencia el cliente emite un token, normalmente un token del lenguaje de marcado de aserción de seguridad (SAML).</span><span class="sxs-lookup"><span data-stu-id="03953-129">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="03953-130">El cliente vuelve a continuación al servicio con el token.</span><span class="sxs-lookup"><span data-stu-id="03953-130">The client then returns to the service with the token.</span></span> <span data-ttu-id="03953-131">El servicio examina el token para los datos que permite al servicio autenticar el token y, por consiguiente, al cliente.</span><span class="sxs-lookup"><span data-stu-id="03953-131">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="03953-132">Para autenticar el token, el servicio debe conocer el certificado que usa el servicio de token seguro.</span><span class="sxs-lookup"><span data-stu-id="03953-132">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="03953-133">El [ \<issuedTokenAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) elemento es el repositorio para cualquier tales certificados de servicio de token seguro.</span><span class="sxs-lookup"><span data-stu-id="03953-133">The [\<issuedTokenAuthentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="03953-134">Para agregar certificados, use el [ \<knownCertificates > elemento](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="03953-134">To add certificates, use the [\<knownCertificates> element](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span></span> <span data-ttu-id="03953-135">Insertar un [ \<Agregar >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) para cada certificado, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="03953-135">Insert an [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
```xml  
<issuedTokenAuthentication>  
   <knownCertificates>  
      <add findValue="www.contoso.com"   
           storeLocation="LocalMachine" storeName="My"   
           X509FindType="FindBySubjectName" />  
    </knownCertificates>  
</issuedTokenAuthentication>  
```  
  
 <span data-ttu-id="03953-136">De forma predeterminada, los certificados se deben obtener a partir de un servicio de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="03953-136">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="03953-137">Estos certificados "conocidos" garantizan que solo los clientes legítimos pueden obtener acceso a un servicio.</span><span class="sxs-lookup"><span data-stu-id="03953-137">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="03953-138">Para revisar las condiciones requeridas para que un cliente que va a autenticar un servicio federado, así como para obtener más información sobre el uso de este elemento de configuración, vea [Cómo: configurar las credenciales en un servicio de federación](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="03953-138">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="03953-139">Para obtener más información acerca de escenarios federados, consulte [federación y Tokens emitidos](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="03953-139">For more information about federated scenarios, see [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="03953-140">Para obtener un ejemplo que muestra cómo rellenar la colección en la configuración, consulte [ \<Agregar >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="03953-140">For an example that shows how to populate the collection in configuration, see [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03953-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="03953-141">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>  
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>  
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>  
 [<span data-ttu-id="03953-142">\<add></span><span class="sxs-lookup"><span data-stu-id="03953-142">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)  
 [<span data-ttu-id="03953-143">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="03953-143">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)  
 [<span data-ttu-id="03953-144">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="03953-144">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="03953-145">Configuración de las credenciales en un servicio de federación</span><span class="sxs-lookup"><span data-stu-id="03953-145">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 [<span data-ttu-id="03953-146">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="03953-146">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="03953-147">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="03953-147">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="03953-148">\<add></span><span class="sxs-lookup"><span data-stu-id="03953-148">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)  
 [<span data-ttu-id="03953-149">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="03953-149">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
