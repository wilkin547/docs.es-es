---
description: 'Más información sobre: <security> de <wsFederationHttpBinding>'
title: <security> de <wsFederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: a8e5e854-b8dc-4921-843d-34b6a4a6a8ba
ms.openlocfilehash: 6c01c7a50b05f1723b3620407eb5e5761bae35cb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786803"
---
# <a name="security-of-wsfederationhttpbinding"></a><span data-ttu-id="cd959-103">\<security> de \<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="cd959-103">\<security> of \<wsFederationHttpBinding></span></span>

<span data-ttu-id="cd959-104">Define la configuración de seguridad de [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="cd959-104">Defines the security settings of the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="cd959-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cd959-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cd959-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="cd959-106">Attributes and Elements</span></span>  

 <span data-ttu-id="cd959-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="cd959-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cd959-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="cd959-108">Attributes</span></span>  
  
|<span data-ttu-id="cd959-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="cd959-109">Attribute</span></span>|<span data-ttu-id="cd959-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="cd959-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cd959-111">Mode</span><span class="sxs-lookup"><span data-stu-id="cd959-111">Mode</span></span>|<span data-ttu-id="cd959-112">Opcional.</span><span class="sxs-lookup"><span data-stu-id="cd959-112">Optional.</span></span> <span data-ttu-id="cd959-113">Especifica el tipo de seguridad que se aplica.</span><span class="sxs-lookup"><span data-stu-id="cd959-113">Specifies the type of security that is applied.</span></span> <span data-ttu-id="cd959-114">El valor predeterminado es `Message`.</span><span class="sxs-lookup"><span data-stu-id="cd959-114">The default value is `Message`.</span></span> <span data-ttu-id="cd959-115">Este atributo es del tipo <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="cd959-115">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="cd959-116">Atributo mode</span><span class="sxs-lookup"><span data-stu-id="cd959-116">Mode Attribute</span></span>  
  
|<span data-ttu-id="cd959-117">Value</span><span class="sxs-lookup"><span data-stu-id="cd959-117">Value</span></span>|<span data-ttu-id="cd959-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="cd959-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cd959-119">None</span><span class="sxs-lookup"><span data-stu-id="cd959-119">None</span></span>|<span data-ttu-id="cd959-120">El mensaje SOAP no es seguro durante la transferencia.</span><span class="sxs-lookup"><span data-stu-id="cd959-120">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="cd959-121">Message</span><span class="sxs-lookup"><span data-stu-id="cd959-121">Message</span></span>|<span data-ttu-id="cd959-122">La integridad, confidencialidad, autenticación de servidor y autenticación del cliente se proporciona mediante la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="cd959-122">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="cd959-123">De forma predeterminada, el cuerpo se cifra y firma.</span><span class="sxs-lookup"><span data-stu-id="cd959-123">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="cd959-124">El servicio necesita ser configurado con un certificado.</span><span class="sxs-lookup"><span data-stu-id="cd959-124">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="cd959-125">La autenticación del cliente está basada en el token emitido al cliente por un servicio de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="cd959-125">Client authentication is based on the token issued to the client by a security token service</span></span>|  
|<span data-ttu-id="cd959-126">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="cd959-126">TransportWithMessageCredential</span></span>|<span data-ttu-id="cd959-127">HTTPS proporciona integridad, confidencialidad y autenticación del servidor.</span><span class="sxs-lookup"><span data-stu-id="cd959-127">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="cd959-128">El servicio necesita ser configurado con un certificado.</span><span class="sxs-lookup"><span data-stu-id="cd959-128">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="cd959-129">La autenticación del cliente se proporciona por medio de la seguridad del mensaje SOAP y está basada en el token emitido al cliente por un servicio de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="cd959-129">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cd959-130">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="cd959-130">Child Elements</span></span>  
  
|<span data-ttu-id="cd959-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="cd959-131">Element</span></span>|<span data-ttu-id="cd959-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="cd959-132">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="cd959-133">Define la configuración de seguridad del nivel del mensaje.</span><span class="sxs-lookup"><span data-stu-id="cd959-133">Defines the settings for the message-level security.</span></span> <span data-ttu-id="cd959-134">Este elemento es del tipo <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="cd959-134">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cd959-135">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="cd959-135">Parent Elements</span></span>  
  
|<span data-ttu-id="cd959-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="cd959-136">Element</span></span>|<span data-ttu-id="cd959-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="cd959-137">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="cd959-138">Define todas las funciones de enlace de [\<wsDualHttpBinding>](wsdualhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="cd959-138">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cd959-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="cd959-139">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="cd959-140">Procedimiento para crear un WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="cd959-140">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="cd959-141">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="cd959-141">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="cd959-142">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="cd959-142">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="cd959-143">Enlaces</span><span class="sxs-lookup"><span data-stu-id="cd959-143">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="cd959-144">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="cd959-144">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="cd959-145">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="cd959-145">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
