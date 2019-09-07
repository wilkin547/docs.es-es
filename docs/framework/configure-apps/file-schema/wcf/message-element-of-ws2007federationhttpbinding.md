---
title: <message>elemento de<ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 52cd941d-e230-4c82-8b29-333a7d20eca8
ms.openlocfilehash: b1128bda6068a1fe3d8f5bb5ac29cc349f023b5b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397846"
---
# <a name="message-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="3bb51-102">\<mensaje > elemento de \<ws2007FederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="3bb51-102">\<message> element of \<ws2007FederationHttpBinding></span></span>
<span data-ttu-id="3bb51-103">Define la configuración para la seguridad de nivel de mensaje [ \<](ws2007federationhttpbinding.md) para el elemento > de ws2007FederationHttpBinding.</span><span class="sxs-lookup"><span data-stu-id="3bb51-103">Defines settings for the message-level security for the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
<span data-ttu-id="3bb51-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3bb51-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3bb51-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="3bb51-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="3bb51-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enlaces**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="3bb51-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="3bb51-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> ws2007FederationHttpBinding**](ws2007federationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="3bb51-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007FederationHttpBinding>**](ws2007federationhttpbinding.md)</span></span>\
<span data-ttu-id="3bb51-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de enlace**</span><span class="sxs-lookup"><span data-stu-id="3bb51-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="3bb51-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguridad**](security-element-of-ws2007federationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="3bb51-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-element-of-ws2007federationhttpbinding.md)</span></span>\
<span data-ttu-id="3bb51-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de mensajes**</span><span class="sxs-lookup"><span data-stu-id="3bb51-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bb51-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3bb51-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3bb51-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3bb51-112">Attributes and Elements</span></span>  
 <span data-ttu-id="3bb51-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3bb51-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3bb51-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="3bb51-114">Attributes</span></span>  
  
|<span data-ttu-id="3bb51-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="3bb51-115">Attribute</span></span>|<span data-ttu-id="3bb51-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3bb51-116">Description</span></span>|  
|---------------|-----------------|  
|`algorithmSuite`|<span data-ttu-id="3bb51-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="3bb51-117">Optional.</span></span> <span data-ttu-id="3bb51-118">Establece el cifrado de mensajes, la firma y los algoritmos del ajuste de clave.</span><span class="sxs-lookup"><span data-stu-id="3bb51-118">Sets the message encryption, signature, and key-wrap algorithms.</span></span> <span data-ttu-id="3bb51-119">La clase <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> determina los algoritmos y los tamaños de clave.</span><span class="sxs-lookup"><span data-stu-id="3bb51-119">The algorithms and the key sizes are determined by the <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> class.</span></span> <span data-ttu-id="3bb51-120">Estos algoritmos se asignan a los indicados en la especificación Lenguaje de directiva de seguridad (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="3bb51-120">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="3bb51-121">En la siguiente tabla se enumeran los posibles valores.</span><span class="sxs-lookup"><span data-stu-id="3bb51-121">See the following table for possible values.</span></span> <span data-ttu-id="3bb51-122">El valor predeterminado es Basic256.</span><span class="sxs-lookup"><span data-stu-id="3bb51-122">The default value is Basic256.</span></span>|  
|`issuedKeyType`|<span data-ttu-id="3bb51-123">Especifica el tipo de clave que se va a emitir.</span><span class="sxs-lookup"><span data-stu-id="3bb51-123">Specifies the type of key to be issued.</span></span> <span data-ttu-id="3bb51-124">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="3bb51-124">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="3bb51-125">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="3bb51-125">-   SymmetricKey</span></span><br /><span data-ttu-id="3bb51-126">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="3bb51-126">-   PublicKey</span></span><br /><span data-ttu-id="3bb51-127">-BearerKey</span><span class="sxs-lookup"><span data-stu-id="3bb51-127">-   BearerKey</span></span><br /><br /> <span data-ttu-id="3bb51-128">El valor predeterminado es SymmetricKey.</span><span class="sxs-lookup"><span data-stu-id="3bb51-128">The default is SymmetricKey.</span></span> <span data-ttu-id="3bb51-129">Este atributo es del tipo <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="3bb51-129">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|`issuedTokenType`|<span data-ttu-id="3bb51-130">Un URI que especifica el tipo de token que se va a emitir.</span><span class="sxs-lookup"><span data-stu-id="3bb51-130">A URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="3bb51-131">El valor predeterminado es `null`.</span><span class="sxs-lookup"><span data-stu-id="3bb51-131">The default is `null`.</span></span>|  
|`negotiateServiceCredential`|<span data-ttu-id="3bb51-132">Un valor que especifica si la credencial del servicio se debería intercambiar como parte de negociación o estar disponible fuera de la banda.</span><span class="sxs-lookup"><span data-stu-id="3bb51-132">A value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="3bb51-133">El valor predeterminado es `true`, que significa que se negocia la credencial del servicio.</span><span class="sxs-lookup"><span data-stu-id="3bb51-133">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="3bb51-134">atributo algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="3bb51-134">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="3bb51-135">Value</span><span class="sxs-lookup"><span data-stu-id="3bb51-135">Value</span></span>|<span data-ttu-id="3bb51-136">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3bb51-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3bb51-137">Basic128</span><span class="sxs-lookup"><span data-stu-id="3bb51-137">Basic128</span></span>|<span data-ttu-id="3bb51-138">Utilice el cifrado Aes128, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="3bb51-138">Use Aes128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="3bb51-139">Basic192</span><span class="sxs-lookup"><span data-stu-id="3bb51-139">Basic192</span></span>|<span data-ttu-id="3bb51-140">Utilice el cifrado Aes192, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="3bb51-140">Use Aes192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="3bb51-141">Basic256</span><span class="sxs-lookup"><span data-stu-id="3bb51-141">Basic256</span></span>|<span data-ttu-id="3bb51-142">Utilice el cifrado Aes256, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el cifrado de claves.</span><span class="sxs-lookup"><span data-stu-id="3bb51-142">Use Aes256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="3bb51-143">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="3bb51-143">Basic256Rsa15</span></span>|<span data-ttu-id="3bb51-144">Utilice Aes256 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="3bb51-144">Use Aes256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="3bb51-145">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="3bb51-145">Basic192Rsa15</span></span>|<span data-ttu-id="3bb51-146">Utilice Aes192 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="3bb51-146">Use Aes192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="3bb51-147">TripleDes</span><span class="sxs-lookup"><span data-stu-id="3bb51-147">TripleDes</span></span>|<span data-ttu-id="3bb51-148">Utilice el cifrado TripleDes, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="3bb51-148">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="3bb51-149">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="3bb51-149">Basic128Rsa15</span></span>|<span data-ttu-id="3bb51-150">Utilice Aes128 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="3bb51-150">Use Aes128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="3bb51-151">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="3bb51-151">TripleDesRsa15</span></span>|<span data-ttu-id="3bb51-152">Utilice el cifrado TripleDes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="3bb51-152">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="3bb51-153">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="3bb51-153">Basic128Sha256</span></span>|<span data-ttu-id="3bb51-154">Utilice Aes256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="3bb51-154">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="3bb51-155">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="3bb51-155">Basic192Sha256</span></span>|<span data-ttu-id="3bb51-156">Utilice Aes192 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="3bb51-156">Use Aes192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="3bb51-157">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="3bb51-157">Basic256Sha256</span></span>|<span data-ttu-id="3bb51-158">Utilice Aes256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="3bb51-158">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="3bb51-159">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="3bb51-159">TripleDesSha256</span></span>|<span data-ttu-id="3bb51-160">Utilice TripleDes para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="3bb51-160">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="3bb51-161">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="3bb51-161">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="3bb51-162">Utilice Aes128 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="3bb51-162">Use Aes128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="3bb51-163">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="3bb51-163">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="3bb51-164">Utilice Aes192 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="3bb51-164">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="3bb51-165">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="3bb51-165">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="3bb51-166">Utilice Aes256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="3bb51-166">Use Aes256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="3bb51-167">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="3bb51-167">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="3bb51-168">Utilice TripleDes para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="3bb51-168">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3bb51-169">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3bb51-169">Child Elements</span></span>  
  
|<span data-ttu-id="3bb51-170">Elemento</span><span class="sxs-lookup"><span data-stu-id="3bb51-170">Element</span></span>|<span data-ttu-id="3bb51-171">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3bb51-171">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3bb51-172">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="3bb51-172">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)|<span data-ttu-id="3bb51-173">Especifica una colección de tipos de demanda para este enlace.</span><span class="sxs-lookup"><span data-stu-id="3bb51-173">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="3bb51-174">Cada elemento es del tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="3bb51-174">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|[<span data-ttu-id="3bb51-175">\<issuer></span><span class="sxs-lookup"><span data-stu-id="3bb51-175">\<issuer></span></span>](issuer.md)|<span data-ttu-id="3bb51-176">Especifica un punto de conexión que emite un token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="3bb51-176">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="3bb51-177">Este elemento es del tipo <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="3bb51-177">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|[<span data-ttu-id="3bb51-178">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="3bb51-178">\<issuerMetadata></span></span>](issuermetadata.md)|<span data-ttu-id="3bb51-179">Especifica la dirección del extremo del emisor.</span><span class="sxs-lookup"><span data-stu-id="3bb51-179">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="3bb51-180">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="3bb51-180">\<tokenRequestParameters></span></span>](tokenrequestparameters.md)|<span data-ttu-id="3bb51-181">Una colección de parámetros de solicitud de token.</span><span class="sxs-lookup"><span data-stu-id="3bb51-181">A collection of token request parameters.</span></span> <span data-ttu-id="3bb51-182">Cada parámetro es un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="3bb51-182">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3bb51-183">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3bb51-183">Parent Elements</span></span>  
  
|<span data-ttu-id="3bb51-184">Elemento</span><span class="sxs-lookup"><span data-stu-id="3bb51-184">Element</span></span>|<span data-ttu-id="3bb51-185">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3bb51-185">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3bb51-186">\<security></span><span class="sxs-lookup"><span data-stu-id="3bb51-186">\<security></span></span>](security-element-of-ws2007federationhttpbinding.md)|<span data-ttu-id="3bb51-187">Define la configuración de seguridad de un enlace.</span><span class="sxs-lookup"><span data-stu-id="3bb51-187">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3bb51-188">Vea también</span><span class="sxs-lookup"><span data-stu-id="3bb51-188">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="3bb51-189">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="3bb51-189">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="3bb51-190">Enlaces</span><span class="sxs-lookup"><span data-stu-id="3bb51-190">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="3bb51-191">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="3bb51-191">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="3bb51-192">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="3bb51-192">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="3bb51-193">\<binding></span><span class="sxs-lookup"><span data-stu-id="3bb51-193">\<binding></span></span>](../../../misc/binding.md)
