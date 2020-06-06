---
title: <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
ms.openlocfilehash: 23fe19258e09e9e8a5e05a94ccef0e40ee1cb5fd
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400335"
---
# \<knownCertificates>
<span data-ttu-id="7e6f9-101">Representa una colección de certificados X.509 que se proporcionan para autenticar las credenciales de seguridad emitidas desde un Servicio de token de seguridad (STS).</span><span class="sxs-lookup"><span data-stu-id="7e6f9-101">Represents a collection of X.509 certificates that are provided to authenticate security credentials issued from a Security Token Service (STS).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenAuthentication>**](issuedtokenauthentication-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<knownCertificates>**  
  
## <a name="syntax"></a><span data-ttu-id="7e6f9-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7e6f9-102">Syntax</span></span>  
  
```xml  
<knownCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7e6f9-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7e6f9-103">Attributes and Elements</span></span>  
 <span data-ttu-id="7e6f9-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7e6f9-104">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7e6f9-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="7e6f9-105">Attributes</span></span>  
 <span data-ttu-id="7e6f9-106">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7e6f9-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7e6f9-107">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7e6f9-107">Child Elements</span></span>  
  
|<span data-ttu-id="7e6f9-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="7e6f9-108">Element</span></span>|<span data-ttu-id="7e6f9-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="7e6f9-109">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-knowncertificates.md)|<span data-ttu-id="7e6f9-110">Agrega un certificado X.509 a la colección.</span><span class="sxs-lookup"><span data-stu-id="7e6f9-110">Adds an X.509 certificate to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7e6f9-111">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7e6f9-111">Parent Elements</span></span>  
  
|<span data-ttu-id="7e6f9-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="7e6f9-112">Element</span></span>|<span data-ttu-id="7e6f9-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="7e6f9-113">Description</span></span>|  
|-------------|-----------------|  
|[\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="7e6f9-114">Especifica un token emitido como una credencial del servicio.</span><span class="sxs-lookup"><span data-stu-id="7e6f9-114">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e6f9-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7e6f9-115">Remarks</span></span>  
 <span data-ttu-id="7e6f9-116">El escenario del token emitido tiene tres etapas.</span><span class="sxs-lookup"><span data-stu-id="7e6f9-116">The issued token scenario has three stages.</span></span> <span data-ttu-id="7e6f9-117">En la primera fase, un cliente que intenta tener acceso a un servicio se conoce como *servicio de token seguro*.</span><span class="sxs-lookup"><span data-stu-id="7e6f9-117">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="7e6f9-118">El servicio de token seguro autentica, a continuación, al cliente y como consecuencia el cliente emite un token, normalmente un token del lenguaje de marcado de aserción de seguridad (SAML).</span><span class="sxs-lookup"><span data-stu-id="7e6f9-118">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="7e6f9-119">El cliente vuelve a continuación al servicio con el token.</span><span class="sxs-lookup"><span data-stu-id="7e6f9-119">The client then returns to the service with the token.</span></span> <span data-ttu-id="7e6f9-120">El servicio examina el token para los datos que permite al servicio autenticar el token y, por consiguiente, al cliente.</span><span class="sxs-lookup"><span data-stu-id="7e6f9-120">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="7e6f9-121">Para autenticar el token, el servicio debe conocer el certificado que usa el servicio de token seguro.</span><span class="sxs-lookup"><span data-stu-id="7e6f9-121">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="7e6f9-122">El [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) elemento es el repositorio para cualquier certificado de servicio de token seguro.</span><span class="sxs-lookup"><span data-stu-id="7e6f9-122">The [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="7e6f9-123">Para agregar certificados, utilice el [ \<knownCertificates> elemento](knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="7e6f9-123">To add certificates, use the [\<knownCertificates> element](knowncertificates.md).</span></span> <span data-ttu-id="7e6f9-124">Inserte un [\<add>](add-of-knowncertificates.md) para cada certificado, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="7e6f9-124">Insert an [\<add>](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="7e6f9-125">De forma predeterminada, los certificados se deben obtener a partir de un servicio de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="7e6f9-125">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="7e6f9-126">Estos certificados "conocidos" garantizan que solo los clientes legítimos pueden obtener acceso a un servicio.</span><span class="sxs-lookup"><span data-stu-id="7e6f9-126">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="7e6f9-127">Para revisar las condiciones requeridas para que un cliente sea autenticado por un servicio federado, así como más información sobre el uso de este elemento de configuración, consulte [How to: configure Credentials on a servicio de Federación](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="7e6f9-127">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="7e6f9-128">Para obtener más información sobre los escenarios federados, vea [Federación y tokens emitidos](../../../wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="7e6f9-128">For more information about federated scenarios, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="7e6f9-129">Para obtener un ejemplo en el que se muestra cómo rellenar la colección en la configuración, vea [\<add>](add-of-knowncertificates.md) .</span><span class="sxs-lookup"><span data-stu-id="7e6f9-129">For an example that shows how to populate the collection in configuration, see [\<add>](add-of-knowncertificates.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e6f9-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7e6f9-130">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [\<add>](add-of-knowncertificates.md)
- [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)
- [<span data-ttu-id="7e6f9-131">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="7e6f9-131">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="7e6f9-132">Procedimiento para configurar las credenciales en un servicio de federación</span><span class="sxs-lookup"><span data-stu-id="7e6f9-132">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="7e6f9-133">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="7e6f9-133">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="7e6f9-134">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="7e6f9-134">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [\<add>](add-of-knowncertificates.md)
- [<span data-ttu-id="7e6f9-135">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="7e6f9-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
