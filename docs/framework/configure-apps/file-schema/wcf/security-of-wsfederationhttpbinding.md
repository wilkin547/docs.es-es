---
title: <security> de <wsFederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: a8e5e854-b8dc-4921-843d-34b6a4a6a8ba
ms.openlocfilehash: 6c07d1ca18837f66548411262b84b9a326f5ec4a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399730"
---
# <a name="security-of-wsfederationhttpbinding"></a><span data-ttu-id="6f500-102">\<> de seguridad \<de wsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="6f500-102">\<security> of \<wsFederationHttpBinding></span></span>
<span data-ttu-id="6f500-103">Define la configuración de seguridad de la [ \<> wsFederationHttpBinding](wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="6f500-103">Defines the security settings of the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>  
  
<span data-ttu-id="6f500-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6f500-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6f500-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="6f500-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="6f500-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enlaces**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="6f500-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="6f500-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> wsFederationHttpBinding**](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="6f500-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="6f500-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de enlace**</span><span class="sxs-lookup"><span data-stu-id="6f500-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="6f500-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de seguridad**</span><span class="sxs-lookup"><span data-stu-id="6f500-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f500-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6f500-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6f500-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6f500-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6f500-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6f500-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6f500-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="6f500-113">Attributes</span></span>  
  
|<span data-ttu-id="6f500-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="6f500-114">Attribute</span></span>|<span data-ttu-id="6f500-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="6f500-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6f500-116">Mode</span><span class="sxs-lookup"><span data-stu-id="6f500-116">Mode</span></span>|<span data-ttu-id="6f500-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6f500-117">Optional.</span></span> <span data-ttu-id="6f500-118">Especifica el tipo de seguridad que se aplica.</span><span class="sxs-lookup"><span data-stu-id="6f500-118">Specifies the type of security that is applied.</span></span> <span data-ttu-id="6f500-119">El valor predeterminado es `Message`.</span><span class="sxs-lookup"><span data-stu-id="6f500-119">The default value is `Message`.</span></span> <span data-ttu-id="6f500-120">Este atributo es del tipo <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="6f500-120">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="6f500-121">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="6f500-121">Mode Attribute</span></span>  
  
|<span data-ttu-id="6f500-122">Valor</span><span class="sxs-lookup"><span data-stu-id="6f500-122">Value</span></span>|<span data-ttu-id="6f500-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="6f500-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6f500-124">None</span><span class="sxs-lookup"><span data-stu-id="6f500-124">None</span></span>|<span data-ttu-id="6f500-125">El mensaje SOAP no es seguro durante la transferencia.</span><span class="sxs-lookup"><span data-stu-id="6f500-125">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="6f500-126">Message</span><span class="sxs-lookup"><span data-stu-id="6f500-126">Message</span></span>|<span data-ttu-id="6f500-127">La integridad, confidencialidad, autenticación de servidor y autenticación del cliente se proporciona mediante la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="6f500-127">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="6f500-128">De forma predeterminada, el cuerpo se cifra y firma.</span><span class="sxs-lookup"><span data-stu-id="6f500-128">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="6f500-129">El servicio necesita ser configurado con un certificado.</span><span class="sxs-lookup"><span data-stu-id="6f500-129">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="6f500-130">La autenticación del cliente está basada en el token emitido al cliente por un servicio de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6f500-130">Client authentication is based on the token issued to the client by a security token service</span></span>|  
|<span data-ttu-id="6f500-131">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="6f500-131">TransportWithMessageCredential</span></span>|<span data-ttu-id="6f500-132">HTTPS proporciona integridad, confidencialidad y autenticación del servidor.</span><span class="sxs-lookup"><span data-stu-id="6f500-132">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="6f500-133">El servicio necesita ser configurado con un certificado.</span><span class="sxs-lookup"><span data-stu-id="6f500-133">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="6f500-134">La autenticación del cliente se proporciona por medio de la seguridad del mensaje SOAP y está basada en el token emitido al cliente por un servicio de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6f500-134">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6f500-135">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6f500-135">Child Elements</span></span>  
  
|<span data-ttu-id="6f500-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="6f500-136">Element</span></span>|<span data-ttu-id="6f500-137">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="6f500-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6f500-138">\<message></span><span class="sxs-lookup"><span data-stu-id="6f500-138">\<message></span></span>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="6f500-139">Define la configuración de seguridad del nivel del mensaje.</span><span class="sxs-lookup"><span data-stu-id="6f500-139">Defines the settings for the message-level security.</span></span> <span data-ttu-id="6f500-140">Este elemento es del tipo <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="6f500-140">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6f500-141">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6f500-141">Parent Elements</span></span>  
  
|<span data-ttu-id="6f500-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="6f500-142">Element</span></span>|<span data-ttu-id="6f500-143">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="6f500-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6f500-144">\<binding></span><span class="sxs-lookup"><span data-stu-id="6f500-144">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="6f500-145">Define todas las funciones de enlace del [ \<> wsDualHttpBinding](wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="6f500-145">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6f500-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f500-146">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="6f500-147">Cómo: Creación de un WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="6f500-147">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="6f500-148">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="6f500-148">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="6f500-149">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="6f500-149">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="6f500-150">Enlaces</span><span class="sxs-lookup"><span data-stu-id="6f500-150">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="6f500-151">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="6f500-151">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="6f500-152">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="6f500-152">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="6f500-153">\<binding></span><span class="sxs-lookup"><span data-stu-id="6f500-153">\<binding></span></span>](../../../misc/binding.md)
