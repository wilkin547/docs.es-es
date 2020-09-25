---
title: <message> elemento de <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 52cd941d-e230-4c82-8b29-333a7d20eca8
ms.openlocfilehash: d71bce5e94568bdad3c52226fa1029a1dd87bfd9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204923"
---
# <a name="message-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="e1ce9-102">\<message> elemento de \<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="e1ce9-102">\<message> element of \<ws2007FederationHttpBinding></span></span>

<span data-ttu-id="e1ce9-103">Define la configuración para la seguridad del nivel de mensaje para el [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="e1ce9-103">Defines settings for the message-level security for the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007FederationHttpBinding>**](ws2007federationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-element-of-ws2007federationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  
  
## <a name="syntax"></a><span data-ttu-id="e1ce9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e1ce9-104">Syntax</span></span>  
  
```xml  
<ws2007FederationBinding>
  <binding>
    <security>
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey"
               negotiateServiceCredential="Boolean">
        <claimTypeRequirements>
          <add claimType="URI"
               isOptional="Boolean" />
        </claimTypeRequirements>
        <issuer address="Uri">
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
                                  x509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
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
</ws2007FederationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e1ce9-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e1ce9-105">Attributes and Elements</span></span>  

 <span data-ttu-id="e1ce9-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e1ce9-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e1ce9-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="e1ce9-107">Attributes</span></span>  
  
|<span data-ttu-id="e1ce9-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="e1ce9-108">Attribute</span></span>|<span data-ttu-id="e1ce9-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="e1ce9-109">Description</span></span>|  
|---------------|-----------------|  
|`algorithmSuite`|<span data-ttu-id="e1ce9-110">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e1ce9-110">Optional.</span></span> <span data-ttu-id="e1ce9-111">Establece el cifrado de mensajes, la firma y los algoritmos del ajuste de clave.</span><span class="sxs-lookup"><span data-stu-id="e1ce9-111">Sets the message encryption, signature, and key-wrap algorithms.</span></span> <span data-ttu-id="e1ce9-112">La clase <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> determina los algoritmos y los tamaños de clave.</span><span class="sxs-lookup"><span data-stu-id="e1ce9-112">The algorithms and the key sizes are determined by the <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> class.</span></span> <span data-ttu-id="e1ce9-113">Estos algoritmos se asignan a los que se indican en la especificación Security Policy Language (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="e1ce9-113">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="e1ce9-114">En la siguiente tabla se enumeran los posibles valores.</span><span class="sxs-lookup"><span data-stu-id="e1ce9-114">See the following table for possible values.</span></span> <span data-ttu-id="e1ce9-115">El valor predeterminado es Basic256.</span><span class="sxs-lookup"><span data-stu-id="e1ce9-115">The default value is Basic256.</span></span>|  
|`issuedKeyType`|<span data-ttu-id="e1ce9-116">Especifica el tipo de clave que se va a emitir.</span><span class="sxs-lookup"><span data-stu-id="e1ce9-116">Specifies the type of key to be issued.</span></span> <span data-ttu-id="e1ce9-117">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e1ce9-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e1ce9-118">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="e1ce9-118">-   SymmetricKey</span></span><br /><span data-ttu-id="e1ce9-119">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="e1ce9-119">-   PublicKey</span></span><br /><span data-ttu-id="e1ce9-120">-BearerKey</span><span class="sxs-lookup"><span data-stu-id="e1ce9-120">-   BearerKey</span></span><br /><br /> <span data-ttu-id="e1ce9-121">El valor predeterminado es SymmetricKey.</span><span class="sxs-lookup"><span data-stu-id="e1ce9-121">The default is SymmetricKey.</span></span> <span data-ttu-id="e1ce9-122">Este atributo es del tipo <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="e1ce9-122">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|`issuedTokenType`|<span data-ttu-id="e1ce9-123">Un URI que especifica el tipo de token que se va a emitir.</span><span class="sxs-lookup"><span data-stu-id="e1ce9-123">A URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="e1ce9-124">El valor predeterminado es `null`.</span><span class="sxs-lookup"><span data-stu-id="e1ce9-124">The default is `null`.</span></span>|  
|`negotiateServiceCredential`|<span data-ttu-id="e1ce9-125">Un valor que especifica si la credencial del servicio se debería intercambiar como parte de negociación o estar disponible fuera de la banda.</span><span class="sxs-lookup"><span data-stu-id="e1ce9-125">A value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="e1ce9-126">El valor predeterminado es `true`, que significa que se negocia la credencial del servicio.</span><span class="sxs-lookup"><span data-stu-id="e1ce9-126">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="e1ce9-127">atributo algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="e1ce9-127">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="e1ce9-128">Value</span><span class="sxs-lookup"><span data-stu-id="e1ce9-128">Value</span></span>|<span data-ttu-id="e1ce9-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="e1ce9-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e1ce9-130">Basic128</span><span class="sxs-lookup"><span data-stu-id="e1ce9-130">Basic128</span></span>|<span data-ttu-id="e1ce9-131">Utilice el cifrado Aes128, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="e1ce9-131">Use Aes128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e1ce9-132">Basic192</span><span class="sxs-lookup"><span data-stu-id="e1ce9-132">Basic192</span></span>|<span data-ttu-id="e1ce9-133">Utilice el cifrado Aes192, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="e1ce9-133">Use Aes192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e1ce9-134">Basic256</span><span class="sxs-lookup"><span data-stu-id="e1ce9-134">Basic256</span></span>|<span data-ttu-id="e1ce9-135">Utilice el cifrado Aes256, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el cifrado de claves.</span><span class="sxs-lookup"><span data-stu-id="e1ce9-135">Use Aes256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e1ce9-136">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="e1ce9-136">Basic256Rsa15</span></span>|<span data-ttu-id="e1ce9-137">Utilice Aes256 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="e1ce9-137">Use Aes256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="e1ce9-138">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="e1ce9-138">Basic192Rsa15</span></span>|<span data-ttu-id="e1ce9-139">Utilice Aes192 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="e1ce9-139">Use Aes192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="e1ce9-140">TripleDes</span><span class="sxs-lookup"><span data-stu-id="e1ce9-140">TripleDes</span></span>|<span data-ttu-id="e1ce9-141">Utilice el cifrado TripleDes, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="e1ce9-141">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e1ce9-142">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="e1ce9-142">Basic128Rsa15</span></span>|<span data-ttu-id="e1ce9-143">Utilice Aes128 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="e1ce9-143">Use Aes128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="e1ce9-144">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="e1ce9-144">TripleDesRsa15</span></span>|<span data-ttu-id="e1ce9-145">Utilice el cifrado TripleDes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="e1ce9-145">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="e1ce9-146">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="e1ce9-146">Basic128Sha256</span></span>|<span data-ttu-id="e1ce9-147">Utilice Aes256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="e1ce9-147">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e1ce9-148">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="e1ce9-148">Basic192Sha256</span></span>|<span data-ttu-id="e1ce9-149">Utilice Aes192 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="e1ce9-149">Use Aes192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e1ce9-150">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="e1ce9-150">Basic256Sha256</span></span>|<span data-ttu-id="e1ce9-151">Utilice Aes256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="e1ce9-151">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e1ce9-152">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="e1ce9-152">TripleDesSha256</span></span>|<span data-ttu-id="e1ce9-153">Utilice TripleDes para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="e1ce9-153">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e1ce9-154">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="e1ce9-154">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="e1ce9-155">Utilice Aes128 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="e1ce9-155">Use Aes128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="e1ce9-156">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="e1ce9-156">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="e1ce9-157">Utilice Aes192 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="e1ce9-157">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="e1ce9-158">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="e1ce9-158">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="e1ce9-159">Utilice Aes256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="e1ce9-159">Use Aes256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="e1ce9-160">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="e1ce9-160">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="e1ce9-161">Utilice TripleDes para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="e1ce9-161">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e1ce9-162">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e1ce9-162">Child Elements</span></span>  
  
|<span data-ttu-id="e1ce9-163">Elemento</span><span class="sxs-lookup"><span data-stu-id="e1ce9-163">Element</span></span>|<span data-ttu-id="e1ce9-164">Descripción</span><span class="sxs-lookup"><span data-stu-id="e1ce9-164">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-element.md)|<span data-ttu-id="e1ce9-165">Especifica una colección de tipos de demanda para este enlace.</span><span class="sxs-lookup"><span data-stu-id="e1ce9-165">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="e1ce9-166">Cada elemento es del tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="e1ce9-166">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|[\<issuer>](issuer.md)|<span data-ttu-id="e1ce9-167">Especifica un punto de conexión que emite un token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e1ce9-167">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="e1ce9-168">Este elemento es del tipo <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="e1ce9-168">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|[\<issuerMetadata>](issuermetadata.md)|<span data-ttu-id="e1ce9-169">Especifica la dirección del extremo del emisor.</span><span class="sxs-lookup"><span data-stu-id="e1ce9-169">Specifies the endpoint address of the issuer.</span></span>|  
|[\<tokenRequestParameters>](tokenrequestparameters.md)|<span data-ttu-id="e1ce9-170">Una colección de parámetros de solicitud de token.</span><span class="sxs-lookup"><span data-stu-id="e1ce9-170">A collection of token request parameters.</span></span> <span data-ttu-id="e1ce9-171">Cada parámetro es un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="e1ce9-171">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e1ce9-172">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e1ce9-172">Parent Elements</span></span>  
  
|<span data-ttu-id="e1ce9-173">Elemento</span><span class="sxs-lookup"><span data-stu-id="e1ce9-173">Element</span></span>|<span data-ttu-id="e1ce9-174">Descripción</span><span class="sxs-lookup"><span data-stu-id="e1ce9-174">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-element-of-ws2007federationhttpbinding.md)|<span data-ttu-id="e1ce9-175">Define la configuración de seguridad de un enlace.</span><span class="sxs-lookup"><span data-stu-id="e1ce9-175">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e1ce9-176">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e1ce9-176">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="e1ce9-177">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="e1ce9-177">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="e1ce9-178">Enlaces</span><span class="sxs-lookup"><span data-stu-id="e1ce9-178">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e1ce9-179">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="e1ce9-179">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e1ce9-180">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="e1ce9-180">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
