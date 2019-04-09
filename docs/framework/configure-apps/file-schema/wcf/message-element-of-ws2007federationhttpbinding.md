---
title: <message> elemento de <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 52cd941d-e230-4c82-8b29-333a7d20eca8
ms.openlocfilehash: f05bd90bd2e4c7e1fd606518d9e5cb8d4e5ad974
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092999"
---
# <a name="message-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="71a51-102">\<mensaje > elemento de \<ws2007FederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="71a51-102">\<message> element of \<ws2007FederationHttpBinding></span></span>
<span data-ttu-id="71a51-103">Define la configuración de seguridad de nivel de mensaje para el [ \<ws2007FederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="71a51-103">Defines settings for the message-level security for the [\<ws2007FederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) element.</span></span>  
  
 <span data-ttu-id="71a51-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="71a51-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="71a51-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="71a51-105">\<bindings></span></span>  
<span data-ttu-id="71a51-106">\<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="71a51-106">\<ws2007FederationHttpBinding></span></span>  
<span data-ttu-id="71a51-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="71a51-107">\<binding></span></span>  
<span data-ttu-id="71a51-108">\<security></span><span class="sxs-lookup"><span data-stu-id="71a51-108">\<security></span></span>  
<span data-ttu-id="71a51-109">\<message></span><span class="sxs-lookup"><span data-stu-id="71a51-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71a51-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="71a51-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="71a51-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="71a51-111">Attributes and Elements</span></span>  
 <span data-ttu-id="71a51-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="71a51-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="71a51-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="71a51-113">Attributes</span></span>  
  
|<span data-ttu-id="71a51-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="71a51-114">Attribute</span></span>|<span data-ttu-id="71a51-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="71a51-115">Description</span></span>|  
|---------------|-----------------|  
|`algorithmSuite`|<span data-ttu-id="71a51-116">Opcional.</span><span class="sxs-lookup"><span data-stu-id="71a51-116">Optional.</span></span> <span data-ttu-id="71a51-117">Establece el cifrado de mensajes, la firma y los algoritmos del ajuste de clave.</span><span class="sxs-lookup"><span data-stu-id="71a51-117">Sets the message encryption, signature, and key-wrap algorithms.</span></span> <span data-ttu-id="71a51-118">La clase <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> determina los algoritmos y los tamaños de clave.</span><span class="sxs-lookup"><span data-stu-id="71a51-118">The algorithms and the key sizes are determined by the <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> class.</span></span> <span data-ttu-id="71a51-119">Estos algoritmos se asignan a los indicados en la especificación Lenguaje de directiva de seguridad (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="71a51-119">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="71a51-120">En la siguiente tabla se enumeran los posibles valores.</span><span class="sxs-lookup"><span data-stu-id="71a51-120">See the following table for possible values.</span></span> <span data-ttu-id="71a51-121">El valor predeterminado es Basic256.</span><span class="sxs-lookup"><span data-stu-id="71a51-121">The default value is Basic256.</span></span>|  
|`issuedKeyType`|<span data-ttu-id="71a51-122">Especifica el tipo de clave que se va a emitir.</span><span class="sxs-lookup"><span data-stu-id="71a51-122">Specifies the type of key to be issued.</span></span> <span data-ttu-id="71a51-123">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="71a51-123">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="71a51-124">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="71a51-124">-   SymmetricKey</span></span><br /><span data-ttu-id="71a51-125">-   PublicKey</span><span class="sxs-lookup"><span data-stu-id="71a51-125">-   PublicKey</span></span><br /><span data-ttu-id="71a51-126">-   BearerKey</span><span class="sxs-lookup"><span data-stu-id="71a51-126">-   BearerKey</span></span><br /><br /> <span data-ttu-id="71a51-127">El valor predeterminado es SymmetricKey.</span><span class="sxs-lookup"><span data-stu-id="71a51-127">The default is SymmetricKey.</span></span> <span data-ttu-id="71a51-128">Este atributo es del tipo <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="71a51-128">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|`issuedTokenType`|<span data-ttu-id="71a51-129">Un URI que especifica el tipo de token que se va a emitir.</span><span class="sxs-lookup"><span data-stu-id="71a51-129">A URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="71a51-130">De manera predeterminada, es `null`.</span><span class="sxs-lookup"><span data-stu-id="71a51-130">The default is `null`.</span></span>|  
|`negotiateServiceCredential`|<span data-ttu-id="71a51-131">Un valor que especifica si la credencial del servicio se debería intercambiar como parte de negociación o estar disponible fuera de la banda.</span><span class="sxs-lookup"><span data-stu-id="71a51-131">A value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="71a51-132">El valor predeterminado es `true`, que significa que se negocia la credencial del servicio.</span><span class="sxs-lookup"><span data-stu-id="71a51-132">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="71a51-133">atributo algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="71a51-133">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="71a51-134">Valor</span><span class="sxs-lookup"><span data-stu-id="71a51-134">Value</span></span>|<span data-ttu-id="71a51-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="71a51-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="71a51-136">Basic128</span><span class="sxs-lookup"><span data-stu-id="71a51-136">Basic128</span></span>|<span data-ttu-id="71a51-137">Utilice el cifrado Aes128, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="71a51-137">Use Aes128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="71a51-138">Basic192</span><span class="sxs-lookup"><span data-stu-id="71a51-138">Basic192</span></span>|<span data-ttu-id="71a51-139">Utilice el cifrado Aes192, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="71a51-139">Use Aes192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="71a51-140">Basic256</span><span class="sxs-lookup"><span data-stu-id="71a51-140">Basic256</span></span>|<span data-ttu-id="71a51-141">Utilice el cifrado Aes256, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el cifrado de claves.</span><span class="sxs-lookup"><span data-stu-id="71a51-141">Use Aes256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="71a51-142">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="71a51-142">Basic256Rsa15</span></span>|<span data-ttu-id="71a51-143">Utilice Aes256 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="71a51-143">Use Aes256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="71a51-144">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="71a51-144">Basic192Rsa15</span></span>|<span data-ttu-id="71a51-145">Utilice Aes192 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="71a51-145">Use Aes192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="71a51-146">TripleDes</span><span class="sxs-lookup"><span data-stu-id="71a51-146">TripleDes</span></span>|<span data-ttu-id="71a51-147">Utilice el cifrado TripleDes, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="71a51-147">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="71a51-148">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="71a51-148">Basic128Rsa15</span></span>|<span data-ttu-id="71a51-149">Utilice Aes128 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="71a51-149">Use Aes128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="71a51-150">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="71a51-150">TripleDesRsa15</span></span>|<span data-ttu-id="71a51-151">Utilice el cifrado TripleDes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="71a51-151">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="71a51-152">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="71a51-152">Basic128Sha256</span></span>|<span data-ttu-id="71a51-153">Utilice Aes256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="71a51-153">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="71a51-154">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="71a51-154">Basic192Sha256</span></span>|<span data-ttu-id="71a51-155">Utilice Aes192 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="71a51-155">Use Aes192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="71a51-156">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="71a51-156">Basic256Sha256</span></span>|<span data-ttu-id="71a51-157">Utilice Aes256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="71a51-157">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="71a51-158">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="71a51-158">TripleDesSha256</span></span>|<span data-ttu-id="71a51-159">Utilice TripleDes para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="71a51-159">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="71a51-160">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="71a51-160">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="71a51-161">Utilice Aes128 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="71a51-161">Use Aes128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="71a51-162">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="71a51-162">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="71a51-163">Utilice Aes192 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="71a51-163">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="71a51-164">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="71a51-164">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="71a51-165">Utilice Aes256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="71a51-165">Use Aes256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="71a51-166">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="71a51-166">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="71a51-167">Utilice TripleDes para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="71a51-167">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="71a51-168">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="71a51-168">Child Elements</span></span>  
  
|<span data-ttu-id="71a51-169">Elemento</span><span class="sxs-lookup"><span data-stu-id="71a51-169">Element</span></span>|<span data-ttu-id="71a51-170">Descripción</span><span class="sxs-lookup"><span data-stu-id="71a51-170">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="71a51-171">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="71a51-171">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="71a51-172">Especifica una colección de tipos de demanda para este enlace.</span><span class="sxs-lookup"><span data-stu-id="71a51-172">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="71a51-173">Cada elemento es del tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="71a51-173">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|[<span data-ttu-id="71a51-174">\<issuer></span><span class="sxs-lookup"><span data-stu-id="71a51-174">\<issuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md)|<span data-ttu-id="71a51-175">Especifica un punto de conexión que emite un token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="71a51-175">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="71a51-176">Este elemento es del tipo <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="71a51-176">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|[<span data-ttu-id="71a51-177">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="71a51-177">\<issuerMetadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md)|<span data-ttu-id="71a51-178">Especifica la dirección del extremo del emisor.</span><span class="sxs-lookup"><span data-stu-id="71a51-178">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="71a51-179">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="71a51-179">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="71a51-180">Una colección de parámetros de solicitud de token.</span><span class="sxs-lookup"><span data-stu-id="71a51-180">A collection of token request parameters.</span></span> <span data-ttu-id="71a51-181">Cada parámetro es un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="71a51-181">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="71a51-182">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="71a51-182">Parent Elements</span></span>  
  
|<span data-ttu-id="71a51-183">Elemento</span><span class="sxs-lookup"><span data-stu-id="71a51-183">Element</span></span>|<span data-ttu-id="71a51-184">Descripción</span><span class="sxs-lookup"><span data-stu-id="71a51-184">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="71a51-185">\<security></span><span class="sxs-lookup"><span data-stu-id="71a51-185">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md)|<span data-ttu-id="71a51-186">Define la configuración de seguridad de un enlace.</span><span class="sxs-lookup"><span data-stu-id="71a51-186">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="71a51-187">Vea también</span><span class="sxs-lookup"><span data-stu-id="71a51-187">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="71a51-188">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="71a51-188">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="71a51-189">Enlaces</span><span class="sxs-lookup"><span data-stu-id="71a51-189">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="71a51-190">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="71a51-190">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="71a51-191">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="71a51-191">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="71a51-192">\<binding></span><span class="sxs-lookup"><span data-stu-id="71a51-192">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
