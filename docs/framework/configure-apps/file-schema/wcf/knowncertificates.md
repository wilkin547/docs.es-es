---
description: 'Más información acerca de: <knownCertificates>'
title: <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
ms.openlocfilehash: 0180db56c775f4f6f17de8da58781c15a412bc81
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802234"
---
# \<knownCertificates>

<span data-ttu-id="bd076-102">Representa una colección de certificados X.509 que se proporcionan para autenticar las credenciales de seguridad emitidas desde un Servicio de token de seguridad (STS).</span><span class="sxs-lookup"><span data-stu-id="bd076-102">Represents a collection of X.509 certificates that are provided to authenticate security credentials issued from a Security Token Service (STS).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenAuthentication>**](issuedtokenauthentication-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<knownCertificates>**  
  
## <a name="syntax"></a><span data-ttu-id="bd076-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bd076-103">Syntax</span></span>  
  
```xml  
<knownCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bd076-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bd076-104">Attributes and Elements</span></span>  

 <span data-ttu-id="bd076-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bd076-105">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bd076-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="bd076-106">Attributes</span></span>  

 <span data-ttu-id="bd076-107">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="bd076-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bd076-108">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bd076-108">Child Elements</span></span>  
  
|<span data-ttu-id="bd076-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="bd076-109">Element</span></span>|<span data-ttu-id="bd076-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="bd076-110">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-knowncertificates.md)|<span data-ttu-id="bd076-111">Agrega un certificado X.509 a la colección.</span><span class="sxs-lookup"><span data-stu-id="bd076-111">Adds an X.509 certificate to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bd076-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bd076-112">Parent Elements</span></span>  
  
|<span data-ttu-id="bd076-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="bd076-113">Element</span></span>|<span data-ttu-id="bd076-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="bd076-114">Description</span></span>|  
|-------------|-----------------|  
|[\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="bd076-115">Especifica un token emitido como una credencial del servicio.</span><span class="sxs-lookup"><span data-stu-id="bd076-115">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd076-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bd076-116">Remarks</span></span>  

 <span data-ttu-id="bd076-117">El escenario del token emitido tiene tres etapas.</span><span class="sxs-lookup"><span data-stu-id="bd076-117">The issued token scenario has three stages.</span></span> <span data-ttu-id="bd076-118">En la primera fase, un cliente que intenta tener acceso a un servicio se conoce como *servicio de token seguro*.</span><span class="sxs-lookup"><span data-stu-id="bd076-118">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="bd076-119">El servicio de token seguro autentica, a continuación, al cliente y como consecuencia el cliente emite un token, normalmente un token del lenguaje de marcado de aserción de seguridad (SAML).</span><span class="sxs-lookup"><span data-stu-id="bd076-119">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="bd076-120">El cliente vuelve a continuación al servicio con el token.</span><span class="sxs-lookup"><span data-stu-id="bd076-120">The client then returns to the service with the token.</span></span> <span data-ttu-id="bd076-121">El servicio examina el token para los datos que permite al servicio autenticar el token y, por consiguiente, al cliente.</span><span class="sxs-lookup"><span data-stu-id="bd076-121">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="bd076-122">Para autenticar el token, el servicio debe conocer el certificado que usa el servicio de token seguro.</span><span class="sxs-lookup"><span data-stu-id="bd076-122">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="bd076-123">El [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) elemento es el repositorio para cualquier certificado de servicio de token seguro.</span><span class="sxs-lookup"><span data-stu-id="bd076-123">The [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="bd076-124">Para agregar certificados, utilice el [ \<knownCertificates> elemento](knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="bd076-124">To add certificates, use the [\<knownCertificates> element](knowncertificates.md).</span></span> <span data-ttu-id="bd076-125">Inserte un [\<add>](add-of-knowncertificates.md) para cada certificado, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="bd076-125">Insert an [\<add>](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="bd076-126">De forma predeterminada, los certificados se deben obtener a partir de un servicio de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="bd076-126">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="bd076-127">Estos certificados "conocidos" garantizan que solo los clientes legítimos pueden obtener acceso a un servicio.</span><span class="sxs-lookup"><span data-stu-id="bd076-127">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="bd076-128">Para revisar las condiciones requeridas para que un cliente sea autenticado por un servicio federado, así como más información sobre el uso de este elemento de configuración, consulte [How to: configure Credentials on a servicio de Federación](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="bd076-128">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="bd076-129">Para obtener más información sobre los escenarios federados, vea [Federación y tokens emitidos](../../../wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="bd076-129">For more information about federated scenarios, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="bd076-130">Para obtener un ejemplo en el que se muestra cómo rellenar la colección en la configuración, vea [\<add>](add-of-knowncertificates.md) .</span><span class="sxs-lookup"><span data-stu-id="bd076-130">For an example that shows how to populate the collection in configuration, see [\<add>](add-of-knowncertificates.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd076-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd076-131">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [\<add>](add-of-knowncertificates.md)
- [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)
- [<span data-ttu-id="bd076-132">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="bd076-132">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="bd076-133">Procedimiento para configurar las credenciales en un servicio de federación</span><span class="sxs-lookup"><span data-stu-id="bd076-133">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="bd076-134">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="bd076-134">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="bd076-135">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="bd076-135">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [\<add>](add-of-knowncertificates.md)
- [<span data-ttu-id="bd076-136">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="bd076-136">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
