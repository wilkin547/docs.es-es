---
title: Elemento &lt;message&gt; de &lt;wsFederationHttpBinding&gt;
ms.date: 03/30/2017
ms.assetid: 9d710389-d9d8-4454-9bf2-da4ccda31cec
ms.openlocfilehash: 9614d973319e962655fd5e9c76f8703dab85c009
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54740832"
---
# <a name="ltmessagegt-element-of-ltwsfederationhttpbindinggt"></a><span data-ttu-id="9819f-102">Elemento &lt;message&gt; de &lt;wsFederationHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="9819f-102">&lt;message&gt; element of &lt;wsFederationHttpBinding&gt;</span></span>
<span data-ttu-id="9819f-103">Define la configuración de la seguridad de nivel de mensaje para el [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="9819f-103">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span></span>  
  
 <span data-ttu-id="9819f-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9819f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9819f-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="9819f-105">\<bindings></span></span>  
<span data-ttu-id="9819f-106">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="9819f-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="9819f-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="9819f-107">\<binding></span></span>  
<span data-ttu-id="9819f-108">\<security></span><span class="sxs-lookup"><span data-stu-id="9819f-108">\<security></span></span>  
<span data-ttu-id="9819f-109">\<message></span><span class="sxs-lookup"><span data-stu-id="9819f-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9819f-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9819f-110">Syntax</span></span>  
  
```xml  
<wsFederationBinding>
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
</wsFederationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9819f-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9819f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9819f-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9819f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9819f-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="9819f-113">Attributes</span></span>  
  
|<span data-ttu-id="9819f-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="9819f-114">Attribute</span></span>|<span data-ttu-id="9819f-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="9819f-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9819f-116">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="9819f-116">algorithmSuite</span></span>|<span data-ttu-id="9819f-117">Establece el cifrado de mensajes y los algoritmos de encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="9819f-117">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="9819f-118">Vea la tabla de "atributo algorithmSuite" para ver los valores válidos de este atributo.</span><span class="sxs-lookup"><span data-stu-id="9819f-118">See the "algorithmSuite attribute" table for valid values of this attribute.</span></span> <span data-ttu-id="9819f-119">El valor predeterminado es `Basic256`.</span><span class="sxs-lookup"><span data-stu-id="9819f-119">The default value is `Basic256`.</span></span><br /><br /> <span data-ttu-id="9819f-120">Este atributo es del tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="9819f-120">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span> <span data-ttu-id="9819f-121">Estos algoritmos se asignan a los indicados en la especificación Lenguaje de directiva de seguridad (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="9819f-121">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span>|  
|<span data-ttu-id="9819f-122">issuedKeyType</span><span class="sxs-lookup"><span data-stu-id="9819f-122">issuedKeyType</span></span>|<span data-ttu-id="9819f-123">Especifica el tipo de clave que se va a emitir.</span><span class="sxs-lookup"><span data-stu-id="9819f-123">Specifies the type of key to be issued.</span></span> <span data-ttu-id="9819f-124">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="9819f-124">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="9819f-125">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="9819f-125">-   SymmetricKey</span></span><br /><span data-ttu-id="9819f-126">-   PublicKey</span><span class="sxs-lookup"><span data-stu-id="9819f-126">-   PublicKey</span></span><br /><br /> <span data-ttu-id="9819f-127">De manera predeterminada, es `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="9819f-127">The default is `SymmetricKey`.</span></span> <span data-ttu-id="9819f-128">Este atributo es del tipo <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="9819f-128">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|<span data-ttu-id="9819f-129">issuedTokenType</span><span class="sxs-lookup"><span data-stu-id="9819f-129">issuedTokenType</span></span>|<span data-ttu-id="9819f-130">Una cadena que contiene un URI que especifica el tipo de token que se va a emitir.</span><span class="sxs-lookup"><span data-stu-id="9819f-130">A string that contains a URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="9819f-131">De manera predeterminada, es `null`.</span><span class="sxs-lookup"><span data-stu-id="9819f-131">The default is `null`.</span></span>|  
|<span data-ttu-id="9819f-132">negotiateServiceCredential</span><span class="sxs-lookup"><span data-stu-id="9819f-132">negotiateServiceCredential</span></span>|<span data-ttu-id="9819f-133">Un valor booleano que especifica si la credencial del servicio se debería intercambiar como parte de negociación o estar disponible fuera de la banda.</span><span class="sxs-lookup"><span data-stu-id="9819f-133">A Boolean value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="9819f-134">El valor predeterminado es `true`, que significa que se negocia la credencial del servicio.</span><span class="sxs-lookup"><span data-stu-id="9819f-134">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="9819f-135">atributo algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="9819f-135">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="9819f-136">Valor</span><span class="sxs-lookup"><span data-stu-id="9819f-136">Value</span></span>|<span data-ttu-id="9819f-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="9819f-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9819f-138">Basic128</span><span class="sxs-lookup"><span data-stu-id="9819f-138">Basic128</span></span>|<span data-ttu-id="9819f-139">Utilice el cifrado Basic128, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="9819f-139">Use Basic128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="9819f-140">Basic192</span><span class="sxs-lookup"><span data-stu-id="9819f-140">Basic192</span></span>|<span data-ttu-id="9819f-141">Utilice el cifrado Basic192, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="9819f-141">Use Basic192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="9819f-142">Basic256</span><span class="sxs-lookup"><span data-stu-id="9819f-142">Basic256</span></span>|<span data-ttu-id="9819f-143">Utilice el cifrado Basic256, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="9819f-143">Use Basic256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="9819f-144">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="9819f-144">Basic256Rsa15</span></span>|<span data-ttu-id="9819f-145">Utilice Basic256 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="9819f-145">Use Basic256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="9819f-146">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="9819f-146">Basic192Rsa15</span></span>|<span data-ttu-id="9819f-147">Utilice Basic192 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="9819f-147">Use Basic192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="9819f-148">TripleDes</span><span class="sxs-lookup"><span data-stu-id="9819f-148">TripleDes</span></span>|<span data-ttu-id="9819f-149">Utilice el cifrado TripleDes, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="9819f-149">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="9819f-150">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="9819f-150">Basic128Rsa15</span></span>|<span data-ttu-id="9819f-151">Utilice Basic128 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="9819f-151">Use Basic128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="9819f-152">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="9819f-152">TripleDesRsa15</span></span>|<span data-ttu-id="9819f-153">Utilice el cifrado TripleDes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="9819f-153">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="9819f-154">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="9819f-154">Basic128Sha256</span></span>|<span data-ttu-id="9819f-155">Utilice Basic128 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="9819f-155">Use Basic128 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="9819f-156">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="9819f-156">Basic192Sha256</span></span>|<span data-ttu-id="9819f-157">Utilice Basic192 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="9819f-157">Use Basic192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="9819f-158">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="9819f-158">Basic256Sha256</span></span>|<span data-ttu-id="9819f-159">Utilice Basic256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="9819f-159">Use Basic256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="9819f-160">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="9819f-160">TripleDesSha256</span></span>|<span data-ttu-id="9819f-161">Utilice TripleDes para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="9819f-161">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="9819f-162">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="9819f-162">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="9819f-163">Utilice Basic128 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="9819f-163">Use Basic128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="9819f-164">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="9819f-164">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="9819f-165">Utilice Aes192 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="9819f-165">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="9819f-166">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="9819f-166">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="9819f-167">Utilice Basic256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="9819f-167">Use Basic256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="9819f-168">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="9819f-168">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="9819f-169">Utilice TripleDes para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="9819f-169">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9819f-170">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9819f-170">Child Elements</span></span>  
  
|<span data-ttu-id="9819f-171">Elemento</span><span class="sxs-lookup"><span data-stu-id="9819f-171">Element</span></span>|<span data-ttu-id="9819f-172">Descripción</span><span class="sxs-lookup"><span data-stu-id="9819f-172">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9819f-173">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="9819f-173">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="9819f-174">Especifica una colección de tipos de demanda para este enlace.</span><span class="sxs-lookup"><span data-stu-id="9819f-174">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="9819f-175">Cada elemento es del tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="9819f-175">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|<span data-ttu-id="9819f-176">issuer</span><span class="sxs-lookup"><span data-stu-id="9819f-176">issuer</span></span>|<span data-ttu-id="9819f-177">Especifica un extremo que emite un token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9819f-177">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="9819f-178">Este elemento es del tipo <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="9819f-178">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|<span data-ttu-id="9819f-179">issuerMetadata</span><span class="sxs-lookup"><span data-stu-id="9819f-179">issuerMetadata</span></span>|<span data-ttu-id="9819f-180">Especifica la dirección del punto de conexión del emisor.</span><span class="sxs-lookup"><span data-stu-id="9819f-180">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="9819f-181">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="9819f-181">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="9819f-182">Una colección de parámetros de solicitud de token.</span><span class="sxs-lookup"><span data-stu-id="9819f-182">A collection of token request parameters.</span></span> <span data-ttu-id="9819f-183">Cada parámetro es un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="9819f-183">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9819f-184">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9819f-184">Parent Elements</span></span>  
  
|<span data-ttu-id="9819f-185">Elemento</span><span class="sxs-lookup"><span data-stu-id="9819f-185">Element</span></span>|<span data-ttu-id="9819f-186">Descripción</span><span class="sxs-lookup"><span data-stu-id="9819f-186">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9819f-187">\<security></span><span class="sxs-lookup"><span data-stu-id="9819f-187">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md)|<span data-ttu-id="9819f-188">Define la configuración de seguridad de un enlace.</span><span class="sxs-lookup"><span data-stu-id="9819f-188">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9819f-189">Vea también</span><span class="sxs-lookup"><span data-stu-id="9819f-189">See also</span></span>
- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
 `System.ServiceModel.Configuration.FederatedMessageSecurityElement`
- [<span data-ttu-id="9819f-190">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="9819f-190">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="9819f-191">Enlaces</span><span class="sxs-lookup"><span data-stu-id="9819f-191">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="9819f-192">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="9819f-192">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="9819f-193">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="9819f-193">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="9819f-194">\<binding></span><span class="sxs-lookup"><span data-stu-id="9819f-194">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
