---
description: 'Más información acerca <message> de: elemento de <ws2007FederationHttpBinding>'
title: <message> elemento de <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 52cd941d-e230-4c82-8b29-333a7d20eca8
ms.openlocfilehash: f9116a5075f30421dfb26adc29ec0b167db33673
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725459"
---
# <a name="message-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="e7793-103">\<message> elemento de \<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="e7793-103">\<message> element of \<ws2007FederationHttpBinding></span></span>

<span data-ttu-id="e7793-104">Define la configuración para la seguridad del nivel de mensaje para el [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="e7793-104">Defines settings for the message-level security for the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007FederationHttpBinding>**](ws2007federationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-element-of-ws2007federationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  
  
## <a name="syntax"></a><span data-ttu-id="e7793-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e7793-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e7793-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e7793-106">Attributes and Elements</span></span>  

 <span data-ttu-id="e7793-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e7793-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e7793-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="e7793-108">Attributes</span></span>  
  
|<span data-ttu-id="e7793-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="e7793-109">Attribute</span></span>|<span data-ttu-id="e7793-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7793-110">Description</span></span>|  
|---------------|-----------------|  
|`algorithmSuite`|<span data-ttu-id="e7793-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e7793-111">Optional.</span></span> <span data-ttu-id="e7793-112">Establece el cifrado de mensajes, la firma y los algoritmos del ajuste de clave.</span><span class="sxs-lookup"><span data-stu-id="e7793-112">Sets the message encryption, signature, and key-wrap algorithms.</span></span> <span data-ttu-id="e7793-113">La clase <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> determina los algoritmos y los tamaños de clave.</span><span class="sxs-lookup"><span data-stu-id="e7793-113">The algorithms and the key sizes are determined by the <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> class.</span></span> <span data-ttu-id="e7793-114">Estos algoritmos se asignan a los que se indican en la especificación Security Policy Language (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="e7793-114">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="e7793-115">En la siguiente tabla se enumeran los posibles valores.</span><span class="sxs-lookup"><span data-stu-id="e7793-115">See the following table for possible values.</span></span> <span data-ttu-id="e7793-116">El valor predeterminado es Basic256.</span><span class="sxs-lookup"><span data-stu-id="e7793-116">The default value is Basic256.</span></span>|  
|`issuedKeyType`|<span data-ttu-id="e7793-117">Especifica el tipo de clave que se va a emitir.</span><span class="sxs-lookup"><span data-stu-id="e7793-117">Specifies the type of key to be issued.</span></span> <span data-ttu-id="e7793-118">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e7793-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e7793-119">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="e7793-119">-   SymmetricKey</span></span><br /><span data-ttu-id="e7793-120">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="e7793-120">-   PublicKey</span></span><br /><span data-ttu-id="e7793-121">-BearerKey</span><span class="sxs-lookup"><span data-stu-id="e7793-121">-   BearerKey</span></span><br /><br /> <span data-ttu-id="e7793-122">El valor predeterminado es SymmetricKey.</span><span class="sxs-lookup"><span data-stu-id="e7793-122">The default is SymmetricKey.</span></span> <span data-ttu-id="e7793-123">Este atributo es del tipo <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="e7793-123">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|`issuedTokenType`|<span data-ttu-id="e7793-124">Un URI que especifica el tipo de token que se va a emitir.</span><span class="sxs-lookup"><span data-stu-id="e7793-124">A URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="e7793-125">De manera predeterminada, es `null`.</span><span class="sxs-lookup"><span data-stu-id="e7793-125">The default is `null`.</span></span>|  
|`negotiateServiceCredential`|<span data-ttu-id="e7793-126">Un valor que especifica si la credencial del servicio se debería intercambiar como parte de negociación o estar disponible fuera de la banda.</span><span class="sxs-lookup"><span data-stu-id="e7793-126">A value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="e7793-127">El valor predeterminado es `true`, que significa que se negocia la credencial del servicio.</span><span class="sxs-lookup"><span data-stu-id="e7793-127">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="e7793-128">atributo algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="e7793-128">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="e7793-129">Value</span><span class="sxs-lookup"><span data-stu-id="e7793-129">Value</span></span>|<span data-ttu-id="e7793-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7793-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e7793-131">Basic128</span><span class="sxs-lookup"><span data-stu-id="e7793-131">Basic128</span></span>|<span data-ttu-id="e7793-132">Utilice el cifrado Aes128, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="e7793-132">Use Aes128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e7793-133">Basic192</span><span class="sxs-lookup"><span data-stu-id="e7793-133">Basic192</span></span>|<span data-ttu-id="e7793-134">Utilice el cifrado Aes192, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="e7793-134">Use Aes192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e7793-135">Basic256</span><span class="sxs-lookup"><span data-stu-id="e7793-135">Basic256</span></span>|<span data-ttu-id="e7793-136">Utilice el cifrado Aes256, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el cifrado de claves.</span><span class="sxs-lookup"><span data-stu-id="e7793-136">Use Aes256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e7793-137">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="e7793-137">Basic256Rsa15</span></span>|<span data-ttu-id="e7793-138">Utilice Aes256 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="e7793-138">Use Aes256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="e7793-139">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="e7793-139">Basic192Rsa15</span></span>|<span data-ttu-id="e7793-140">Utilice Aes192 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="e7793-140">Use Aes192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="e7793-141">TripleDes</span><span class="sxs-lookup"><span data-stu-id="e7793-141">TripleDes</span></span>|<span data-ttu-id="e7793-142">Utilice el cifrado TripleDes, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="e7793-142">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e7793-143">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="e7793-143">Basic128Rsa15</span></span>|<span data-ttu-id="e7793-144">Utilice Aes128 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="e7793-144">Use Aes128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="e7793-145">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="e7793-145">TripleDesRsa15</span></span>|<span data-ttu-id="e7793-146">Utilice el cifrado TripleDes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="e7793-146">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="e7793-147">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="e7793-147">Basic128Sha256</span></span>|<span data-ttu-id="e7793-148">Utilice Aes256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="e7793-148">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e7793-149">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="e7793-149">Basic192Sha256</span></span>|<span data-ttu-id="e7793-150">Utilice Aes192 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="e7793-150">Use Aes192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e7793-151">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="e7793-151">Basic256Sha256</span></span>|<span data-ttu-id="e7793-152">Utilice Aes256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="e7793-152">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e7793-153">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="e7793-153">TripleDesSha256</span></span>|<span data-ttu-id="e7793-154">Utilice TripleDes para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="e7793-154">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e7793-155">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="e7793-155">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="e7793-156">Utilice Aes128 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="e7793-156">Use Aes128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="e7793-157">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="e7793-157">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="e7793-158">Utilice Aes192 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="e7793-158">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="e7793-159">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="e7793-159">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="e7793-160">Utilice Aes256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="e7793-160">Use Aes256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="e7793-161">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="e7793-161">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="e7793-162">Utilice TripleDes para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="e7793-162">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e7793-163">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e7793-163">Child Elements</span></span>  
  
|<span data-ttu-id="e7793-164">Elemento</span><span class="sxs-lookup"><span data-stu-id="e7793-164">Element</span></span>|<span data-ttu-id="e7793-165">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7793-165">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-element.md)|<span data-ttu-id="e7793-166">Especifica una colección de tipos de demanda para este enlace.</span><span class="sxs-lookup"><span data-stu-id="e7793-166">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="e7793-167">Cada elemento es del tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="e7793-167">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|[\<issuer>](issuer.md)|<span data-ttu-id="e7793-168">Especifica un punto de conexión que emite un token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e7793-168">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="e7793-169">Este elemento es del tipo <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="e7793-169">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|[\<issuerMetadata>](issuermetadata.md)|<span data-ttu-id="e7793-170">Especifica la dirección del extremo del emisor.</span><span class="sxs-lookup"><span data-stu-id="e7793-170">Specifies the endpoint address of the issuer.</span></span>|  
|[\<tokenRequestParameters>](tokenrequestparameters.md)|<span data-ttu-id="e7793-171">Una colección de parámetros de solicitud de token.</span><span class="sxs-lookup"><span data-stu-id="e7793-171">A collection of token request parameters.</span></span> <span data-ttu-id="e7793-172">Cada parámetro es un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="e7793-172">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e7793-173">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e7793-173">Parent Elements</span></span>  
  
|<span data-ttu-id="e7793-174">Elemento</span><span class="sxs-lookup"><span data-stu-id="e7793-174">Element</span></span>|<span data-ttu-id="e7793-175">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7793-175">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-element-of-ws2007federationhttpbinding.md)|<span data-ttu-id="e7793-176">Define la configuración de seguridad de un enlace.</span><span class="sxs-lookup"><span data-stu-id="e7793-176">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e7793-177">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7793-177">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="e7793-178">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="e7793-178">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="e7793-179">Enlaces</span><span class="sxs-lookup"><span data-stu-id="e7793-179">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e7793-180">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="e7793-180">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e7793-181">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="e7793-181">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
