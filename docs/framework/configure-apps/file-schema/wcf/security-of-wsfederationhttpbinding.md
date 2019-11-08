---
title: <security> de <wsFederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: a8e5e854-b8dc-4921-843d-34b6a4a6a8ba
ms.openlocfilehash: ea029444cee331a235c7a2fc140b4321d7530063
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736331"
---
# <a name="security-of-wsfederationhttpbinding"></a><span data-ttu-id="67a7a-102">\<> de seguridad de \<wsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="67a7a-102">\<security> of \<wsFederationHttpBinding></span></span>
<span data-ttu-id="67a7a-103">Define la configuración de seguridad del [\<wsFederationHttpBinding >](wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="67a7a-103">Defines the security settings of the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>  
  
<span data-ttu-id="67a7a-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="67a7a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="67a7a-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="67a7a-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="67a7a-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**enlaces**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="67a7a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="67a7a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsFederationHttpBinding**](wsfederationhttpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="67a7a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="67a7a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**enlace** ></span><span class="sxs-lookup"><span data-stu-id="67a7a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="67a7a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**seguridad** ></span><span class="sxs-lookup"><span data-stu-id="67a7a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67a7a-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="67a7a-110">Syntax</span></span>  
  
```xml  
<wsFederationBinding>
  <binding>
    <security mode="None/Message/TransportWithMessageCredential">
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey"
               negotiateServiceCredential="Boolean">
        <claimTypeRequirements>
          <add claimType="URI"
               isOptional="Boolean" />
        </claimTypeRequirements>
        <issuer address="Uri" >
          <headers>
            <add name="String"
                 namespace="String" />
          </headers>
          <identity>
            <certificate encodedValue="String" />
            <certificateReference findValue="String"
                                  isChainIncluded="Boolean"
                                  storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                                  storeLocation="LocalMachine/CurrentUser"
                                  X509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
            <dns value="String" />
            <rsa value="String" />
            <servicePrincipalName value="String" />
            <usePrincipalName value="String" />
          </identity>
        </issuer>
        <issuerMetadata address="String">
          <headers>
            <add name="String"
                 namespace="String" />
          </headers>
          <identity>
            <certificate encodedValue="String" />
            <certificateReference findValue="String"
                                  isChainIncluded="Boolean"
                                  storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                                  storeLocation="LocalMachine/CurrentUser"
                                  X509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
            <dns value="String" />
            <rsa value="String" />
            <servicePrincipalName value="String" />
            <usePrincipalName value="String" />
          </identity>
        </issuerMetadata>
        <tokenRequestParameters>
          <xmlElement>
          </xmlElement>
        </tokenRequestParameters>
      </message>
    </security>
  </binding>
</wsFederationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="67a7a-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="67a7a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="67a7a-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="67a7a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="67a7a-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="67a7a-113">Attributes</span></span>  
  
|<span data-ttu-id="67a7a-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="67a7a-114">Attribute</span></span>|<span data-ttu-id="67a7a-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="67a7a-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="67a7a-116">Modo</span><span class="sxs-lookup"><span data-stu-id="67a7a-116">Mode</span></span>|<span data-ttu-id="67a7a-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="67a7a-117">Optional.</span></span> <span data-ttu-id="67a7a-118">Especifica el tipo de seguridad que se aplica.</span><span class="sxs-lookup"><span data-stu-id="67a7a-118">Specifies the type of security that is applied.</span></span> <span data-ttu-id="67a7a-119">El valor predeterminado es `Message`.</span><span class="sxs-lookup"><span data-stu-id="67a7a-119">The default value is `Message`.</span></span> <span data-ttu-id="67a7a-120">Este atributo es del tipo <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="67a7a-120">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="67a7a-121">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="67a7a-121">Mode Attribute</span></span>  
  
|<span data-ttu-id="67a7a-122">Valor</span><span class="sxs-lookup"><span data-stu-id="67a7a-122">Value</span></span>|<span data-ttu-id="67a7a-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="67a7a-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="67a7a-124">Ninguno</span><span class="sxs-lookup"><span data-stu-id="67a7a-124">None</span></span>|<span data-ttu-id="67a7a-125">El mensaje SOAP no es seguro durante la transferencia.</span><span class="sxs-lookup"><span data-stu-id="67a7a-125">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="67a7a-126">Mensaje</span><span class="sxs-lookup"><span data-stu-id="67a7a-126">Message</span></span>|<span data-ttu-id="67a7a-127">La integridad, confidencialidad, autenticación de servidor y autenticación del cliente se proporciona mediante la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="67a7a-127">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="67a7a-128">De forma predeterminada, el cuerpo se cifra y firma.</span><span class="sxs-lookup"><span data-stu-id="67a7a-128">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="67a7a-129">El servicio necesita ser configurado con un certificado.</span><span class="sxs-lookup"><span data-stu-id="67a7a-129">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="67a7a-130">La autenticación del cliente está basada en el token emitido al cliente por un servicio de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="67a7a-130">Client authentication is based on the token issued to the client by a security token service</span></span>|  
|<span data-ttu-id="67a7a-131">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="67a7a-131">TransportWithMessageCredential</span></span>|<span data-ttu-id="67a7a-132">HTTPS proporciona integridad, confidencialidad y autenticación del servidor.</span><span class="sxs-lookup"><span data-stu-id="67a7a-132">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="67a7a-133">El servicio necesita ser configurado con un certificado.</span><span class="sxs-lookup"><span data-stu-id="67a7a-133">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="67a7a-134">La autenticación del cliente se proporciona por medio de la seguridad del mensaje SOAP y está basada en el token emitido al cliente por un servicio de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="67a7a-134">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="67a7a-135">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="67a7a-135">Child Elements</span></span>  
  
|<span data-ttu-id="67a7a-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="67a7a-136">Element</span></span>|<span data-ttu-id="67a7a-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="67a7a-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="67a7a-138">\<> de mensaje</span><span class="sxs-lookup"><span data-stu-id="67a7a-138">\<message></span></span>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="67a7a-139">Define la configuración de seguridad del nivel del mensaje.</span><span class="sxs-lookup"><span data-stu-id="67a7a-139">Defines the settings for the message-level security.</span></span> <span data-ttu-id="67a7a-140">Este elemento es del tipo <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="67a7a-140">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="67a7a-141">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="67a7a-141">Parent Elements</span></span>  
  
|<span data-ttu-id="67a7a-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="67a7a-142">Element</span></span>|<span data-ttu-id="67a7a-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="67a7a-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="67a7a-144">\<> de enlace</span><span class="sxs-lookup"><span data-stu-id="67a7a-144">\<binding></span></span>](bindings.md)|<span data-ttu-id="67a7a-145">Define todas las funciones de enlace del [\<wsDualHttpBinding >](wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="67a7a-145">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="67a7a-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="67a7a-146">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="67a7a-147">Creación de un WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="67a7a-147">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="67a7a-148">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="67a7a-148">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="67a7a-149">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="67a7a-149">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="67a7a-150">Enlaces</span><span class="sxs-lookup"><span data-stu-id="67a7a-150">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="67a7a-151">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="67a7a-151">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="67a7a-152">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="67a7a-152">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="67a7a-153">\<> de enlace</span><span class="sxs-lookup"><span data-stu-id="67a7a-153">\<binding></span></span>](bindings.md)
