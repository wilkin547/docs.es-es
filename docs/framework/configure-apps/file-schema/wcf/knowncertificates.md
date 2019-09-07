---
title: <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
ms.openlocfilehash: 23fe19258e09e9e8a5e05a94ccef0e40ee1cb5fd
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400335"
---
# <a name="knowncertificates"></a><span data-ttu-id="bd00a-101">\<> knownCertificates</span><span class="sxs-lookup"><span data-stu-id="bd00a-101">\<knownCertificates></span></span>
<span data-ttu-id="bd00a-102">Representa una colección de certificados X.509 que se proporcionan para autenticar las credenciales de seguridad emitidas desde un Servicio de token de seguridad (STS).</span><span class="sxs-lookup"><span data-stu-id="bd00a-102">Represents a collection of X.509 certificates that are provided to authenticate security credentials issued from a Security Token Service (STS).</span></span>  
  
<span data-ttu-id="bd00a-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bd00a-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bd00a-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="bd00a-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="bd00a-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="bd00a-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="bd00a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="bd00a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="bd00a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="bd00a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="bd00a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de serviceCredentials**](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="bd00a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="bd00a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> issuedTokenAuthentication**](issuedtokenauthentication-of-servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="bd00a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenAuthentication>**](issuedtokenauthentication-of-servicecredentials.md)</span></span>\
<span data-ttu-id="bd00a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> knownCertificates**</span><span class="sxs-lookup"><span data-stu-id="bd00a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<knownCertificates>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd00a-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bd00a-111">Syntax</span></span>  
  
```xml  
<knownCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bd00a-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bd00a-112">Attributes and Elements</span></span>  
 <span data-ttu-id="bd00a-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bd00a-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bd00a-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="bd00a-114">Attributes</span></span>  
 <span data-ttu-id="bd00a-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="bd00a-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bd00a-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bd00a-116">Child Elements</span></span>  
  
|<span data-ttu-id="bd00a-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="bd00a-117">Element</span></span>|<span data-ttu-id="bd00a-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="bd00a-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bd00a-119">\<add></span><span class="sxs-lookup"><span data-stu-id="bd00a-119">\<add></span></span>](add-of-knowncertificates.md)|<span data-ttu-id="bd00a-120">Agrega un certificado X.509 a la colección.</span><span class="sxs-lookup"><span data-stu-id="bd00a-120">Adds an X.509 certificate to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bd00a-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bd00a-121">Parent Elements</span></span>  
  
|<span data-ttu-id="bd00a-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="bd00a-122">Element</span></span>|<span data-ttu-id="bd00a-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="bd00a-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bd00a-124">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="bd00a-124">\<issuedTokenAuthentication></span></span>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="bd00a-125">Especifica un token emitido como una credencial del servicio.</span><span class="sxs-lookup"><span data-stu-id="bd00a-125">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd00a-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bd00a-126">Remarks</span></span>  
 <span data-ttu-id="bd00a-127">El escenario del token emitido tiene tres etapas.</span><span class="sxs-lookup"><span data-stu-id="bd00a-127">The issued token scenario has three stages.</span></span> <span data-ttu-id="bd00a-128">En la primera fase, un cliente que intenta tener acceso a un servicio se conoce como *servicio de token seguro*.</span><span class="sxs-lookup"><span data-stu-id="bd00a-128">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="bd00a-129">El servicio de token seguro autentica, a continuación, al cliente y como consecuencia el cliente emite un token, normalmente un token del lenguaje de marcado de aserción de seguridad (SAML).</span><span class="sxs-lookup"><span data-stu-id="bd00a-129">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="bd00a-130">El cliente vuelve a continuación al servicio con el token.</span><span class="sxs-lookup"><span data-stu-id="bd00a-130">The client then returns to the service with the token.</span></span> <span data-ttu-id="bd00a-131">El servicio examina el token para los datos que permite al servicio autenticar el token y, por consiguiente, al cliente.</span><span class="sxs-lookup"><span data-stu-id="bd00a-131">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="bd00a-132">Para autenticar el token, el servicio debe conocer el certificado que usa el servicio de token seguro.</span><span class="sxs-lookup"><span data-stu-id="bd00a-132">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="bd00a-133">El elemento > issuedTokenAuthentication es el repositorio para cualquier certificado de servicio de token seguro. [ \<](issuedtokenauthentication-of-servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="bd00a-133">The [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="bd00a-134">Para agregar certificados, use el [ \<elemento > de knownCertificates](knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="bd00a-134">To add certificates, use the [\<knownCertificates> element](knowncertificates.md).</span></span> <span data-ttu-id="bd00a-135">Inserte un [ \<> Agregar](add-of-knowncertificates.md) para cada certificado, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="bd00a-135">Insert an [\<add>](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="bd00a-136">De forma predeterminada, los certificados se deben obtener a partir de un servicio de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="bd00a-136">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="bd00a-137">Estos certificados "conocidos" garantizan que solo los clientes legítimos pueden obtener acceso a un servicio.</span><span class="sxs-lookup"><span data-stu-id="bd00a-137">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="bd00a-138">Para revisar las condiciones requeridas para que un cliente sea autenticado por un servicio federado, así como más información sobre el uso de este [elemento de configuración, consulte Cómo: Configure las credenciales](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)en un servicio de Federación.</span><span class="sxs-lookup"><span data-stu-id="bd00a-138">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="bd00a-139">Para obtener más información sobre los escenarios federados, vea [Federación y tokens emitidos](../../../wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="bd00a-139">For more information about federated scenarios, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="bd00a-140">Para obtener un ejemplo en el que se muestra cómo rellenar la colección en la configuración, vea [ \<agregar >](add-of-knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="bd00a-140">For an example that shows how to populate the collection in configuration, see [\<add>](add-of-knowncertificates.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd00a-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd00a-141">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [<span data-ttu-id="bd00a-142">\<add></span><span class="sxs-lookup"><span data-stu-id="bd00a-142">\<add></span></span>](add-of-knowncertificates.md)
- [<span data-ttu-id="bd00a-143">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="bd00a-143">\<issuedTokenAuthentication></span></span>](issuedtokenauthentication-of-servicecredentials.md)
- [<span data-ttu-id="bd00a-144">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="bd00a-144">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="bd00a-145">Cómo: Configurar credenciales en un Servicio de federación</span><span class="sxs-lookup"><span data-stu-id="bd00a-145">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="bd00a-146">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="bd00a-146">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="bd00a-147">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="bd00a-147">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="bd00a-148">\<add></span><span class="sxs-lookup"><span data-stu-id="bd00a-148">\<add></span></span>](add-of-knowncertificates.md)
- [<span data-ttu-id="bd00a-149">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="bd00a-149">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
