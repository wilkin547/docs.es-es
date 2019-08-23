---
title: <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
ms.openlocfilehash: 1210e6282a7dd6c40198693d4948a89efe841d59
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913528"
---
# <a name="knowncertificates"></a><span data-ttu-id="f9922-101">\<> knownCertificates</span><span class="sxs-lookup"><span data-stu-id="f9922-101">\<knownCertificates></span></span>
<span data-ttu-id="f9922-102">Representa una colección de certificados X.509 que se proporcionan para autenticar las credenciales de seguridad emitidas desde un Servicio de token de seguridad (STS).</span><span class="sxs-lookup"><span data-stu-id="f9922-102">Represents a collection of X.509 certificates that are provided to authenticate security credentials issued from a Security Token Service (STS).</span></span>  
  
 <span data-ttu-id="f9922-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f9922-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="f9922-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="f9922-104">\<behaviors></span></span>  
<span data-ttu-id="f9922-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="f9922-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="f9922-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="f9922-106">\<behavior></span></span>  
<span data-ttu-id="f9922-107">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="f9922-107">\<serviceCredentials></span></span>  
<span data-ttu-id="f9922-108">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="f9922-108">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="f9922-109">\<> knownCertificates</span><span class="sxs-lookup"><span data-stu-id="f9922-109">\<knownCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9922-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f9922-110">Syntax</span></span>  
  
```xml  
<knownCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f9922-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f9922-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f9922-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f9922-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f9922-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="f9922-113">Attributes</span></span>  
 <span data-ttu-id="f9922-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f9922-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f9922-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f9922-115">Child Elements</span></span>  
  
|<span data-ttu-id="f9922-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="f9922-116">Element</span></span>|<span data-ttu-id="f9922-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f9922-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f9922-118">\<add></span><span class="sxs-lookup"><span data-stu-id="f9922-118">\<add></span></span>](add-of-knowncertificates.md)|<span data-ttu-id="f9922-119">Agrega un certificado X.509 a la colección.</span><span class="sxs-lookup"><span data-stu-id="f9922-119">Adds an X.509 certificate to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f9922-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f9922-120">Parent Elements</span></span>  
  
|<span data-ttu-id="f9922-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="f9922-121">Element</span></span>|<span data-ttu-id="f9922-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f9922-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f9922-123">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="f9922-123">\<issuedTokenAuthentication></span></span>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="f9922-124">Especifica un token emitido como una credencial del servicio.</span><span class="sxs-lookup"><span data-stu-id="f9922-124">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9922-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f9922-125">Remarks</span></span>  
 <span data-ttu-id="f9922-126">El escenario del token emitido tiene tres etapas.</span><span class="sxs-lookup"><span data-stu-id="f9922-126">The issued token scenario has three stages.</span></span> <span data-ttu-id="f9922-127">En la primera fase, un cliente que intenta tener acceso a un servicio se conoce como *servicio de token seguro*.</span><span class="sxs-lookup"><span data-stu-id="f9922-127">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="f9922-128">El servicio de token seguro autentica, a continuación, al cliente y como consecuencia el cliente emite un token, normalmente un token del lenguaje de marcado de aserción de seguridad (SAML).</span><span class="sxs-lookup"><span data-stu-id="f9922-128">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="f9922-129">El cliente vuelve a continuación al servicio con el token.</span><span class="sxs-lookup"><span data-stu-id="f9922-129">The client then returns to the service with the token.</span></span> <span data-ttu-id="f9922-130">El servicio examina el token para los datos que permite al servicio autenticar el token y, por consiguiente, al cliente.</span><span class="sxs-lookup"><span data-stu-id="f9922-130">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="f9922-131">Para autenticar el token, el servicio debe conocer el certificado que usa el servicio de token seguro.</span><span class="sxs-lookup"><span data-stu-id="f9922-131">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="f9922-132">El elemento > issuedTokenAuthentication es el repositorio para cualquier certificado de servicio de token seguro. [ \<](issuedtokenauthentication-of-servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="f9922-132">The [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="f9922-133">Para agregar certificados, use el [ \<elemento > de knownCertificates](knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="f9922-133">To add certificates, use the [\<knownCertificates> element](knowncertificates.md).</span></span> <span data-ttu-id="f9922-134">Inserte un [ \<> Agregar](add-of-knowncertificates.md) para cada certificado, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f9922-134">Insert an [\<add>](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="f9922-135">De forma predeterminada, los certificados se deben obtener a partir de un servicio de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f9922-135">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="f9922-136">Estos certificados "conocidos" garantizan que solo los clientes legítimos pueden obtener acceso a un servicio.</span><span class="sxs-lookup"><span data-stu-id="f9922-136">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="f9922-137">Para revisar las condiciones requeridas para que un cliente sea autenticado por un servicio federado, así como más información sobre el uso de este [elemento de configuración, consulte Cómo: Configure las credenciales](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)en un servicio de Federación.</span><span class="sxs-lookup"><span data-stu-id="f9922-137">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="f9922-138">Para obtener más información sobre los escenarios federados, vea [Federación y tokens emitidos](../../../wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="f9922-138">For more information about federated scenarios, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="f9922-139">Para obtener un ejemplo en el que se muestra cómo rellenar la colección en la configuración, vea [ \<agregar >](add-of-knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="f9922-139">For an example that shows how to populate the collection in configuration, see [\<add>](add-of-knowncertificates.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9922-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9922-140">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [<span data-ttu-id="f9922-141">\<add></span><span class="sxs-lookup"><span data-stu-id="f9922-141">\<add></span></span>](add-of-knowncertificates.md)
- [<span data-ttu-id="f9922-142">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="f9922-142">\<issuedTokenAuthentication></span></span>](issuedtokenauthentication-of-servicecredentials.md)
- [<span data-ttu-id="f9922-143">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="f9922-143">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="f9922-144">Cómo: Configurar credenciales en un Servicio de federación</span><span class="sxs-lookup"><span data-stu-id="f9922-144">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="f9922-145">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="f9922-145">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="f9922-146">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="f9922-146">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="f9922-147">\<add></span><span class="sxs-lookup"><span data-stu-id="f9922-147">\<add></span></span>](add-of-knowncertificates.md)
- [<span data-ttu-id="f9922-148">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="f9922-148">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
