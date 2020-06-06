---
title: <message>elemento de<ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 52cd941d-e230-4c82-8b29-333a7d20eca8
ms.openlocfilehash: dde763687dbc62d6fb342a21a4c614208f28d7e8
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738999"
---
# <a name="message-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="55f67-102">\<message>elemento de\<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="55f67-102">\<message> element of \<ws2007FederationHttpBinding></span></span>
<span data-ttu-id="55f67-103">Define la configuración para la seguridad del nivel de mensaje para el [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="55f67-103">Defines settings for the message-level security for the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007FederationHttpBinding>**](ws2007federationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-element-of-ws2007federationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  
  
## <a name="syntax"></a><span data-ttu-id="55f67-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="55f67-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="55f67-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="55f67-105">Attributes and Elements</span></span>  
 <span data-ttu-id="55f67-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="55f67-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="55f67-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="55f67-107">Attributes</span></span>  
  
|<span data-ttu-id="55f67-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="55f67-108">Attribute</span></span>|<span data-ttu-id="55f67-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="55f67-109">Description</span></span>|  
|---------------|-----------------|  
|`algorithmSuite`|<span data-ttu-id="55f67-110">Opcional.</span><span class="sxs-lookup"><span data-stu-id="55f67-110">Optional.</span></span> <span data-ttu-id="55f67-111">Establece el cifrado de mensajes, la firma y los algoritmos del ajuste de clave.</span><span class="sxs-lookup"><span data-stu-id="55f67-111">Sets the message encryption, signature, and key-wrap algorithms.</span></span> <span data-ttu-id="55f67-112">La clase <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> determina los algoritmos y los tamaños de clave.</span><span class="sxs-lookup"><span data-stu-id="55f67-112">The algorithms and the key sizes are determined by the <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> class.</span></span> <span data-ttu-id="55f67-113">Estos algoritmos se asignan a los que se indican en la especificación Security Policy Language (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="55f67-113">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="55f67-114">En la siguiente tabla se enumeran los posibles valores.</span><span class="sxs-lookup"><span data-stu-id="55f67-114">See the following table for possible values.</span></span> <span data-ttu-id="55f67-115">El valor predeterminado es Basic256.</span><span class="sxs-lookup"><span data-stu-id="55f67-115">The default value is Basic256.</span></span>|  
|`issuedKeyType`|<span data-ttu-id="55f67-116">Especifica el tipo de clave que se va a emitir.</span><span class="sxs-lookup"><span data-stu-id="55f67-116">Specifies the type of key to be issued.</span></span> <span data-ttu-id="55f67-117">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="55f67-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="55f67-118">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="55f67-118">-   SymmetricKey</span></span><br /><span data-ttu-id="55f67-119">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="55f67-119">-   PublicKey</span></span><br /><span data-ttu-id="55f67-120">-BearerKey</span><span class="sxs-lookup"><span data-stu-id="55f67-120">-   BearerKey</span></span><br /><br /> <span data-ttu-id="55f67-121">El valor predeterminado es SymmetricKey.</span><span class="sxs-lookup"><span data-stu-id="55f67-121">The default is SymmetricKey.</span></span> <span data-ttu-id="55f67-122">Este atributo es del tipo <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="55f67-122">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|`issuedTokenType`|<span data-ttu-id="55f67-123">Un URI que especifica el tipo de token que se va a emitir.</span><span class="sxs-lookup"><span data-stu-id="55f67-123">A URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="55f67-124">De manera predeterminada, es `null`.</span><span class="sxs-lookup"><span data-stu-id="55f67-124">The default is `null`.</span></span>|  
|`negotiateServiceCredential`|<span data-ttu-id="55f67-125">Un valor que especifica si la credencial del servicio se debería intercambiar como parte de negociación o estar disponible fuera de la banda.</span><span class="sxs-lookup"><span data-stu-id="55f67-125">A value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="55f67-126">El valor predeterminado es `true`, que significa que se negocia la credencial del servicio.</span><span class="sxs-lookup"><span data-stu-id="55f67-126">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="55f67-127">atributo algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="55f67-127">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="55f67-128">Value</span><span class="sxs-lookup"><span data-stu-id="55f67-128">Value</span></span>|<span data-ttu-id="55f67-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="55f67-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="55f67-130">Basic128</span><span class="sxs-lookup"><span data-stu-id="55f67-130">Basic128</span></span>|<span data-ttu-id="55f67-131">Utilice el cifrado Aes128, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="55f67-131">Use Aes128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="55f67-132">Basic192</span><span class="sxs-lookup"><span data-stu-id="55f67-132">Basic192</span></span>|<span data-ttu-id="55f67-133">Utilice el cifrado Aes192, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="55f67-133">Use Aes192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="55f67-134">Basic256</span><span class="sxs-lookup"><span data-stu-id="55f67-134">Basic256</span></span>|<span data-ttu-id="55f67-135">Utilice el cifrado Aes256, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el cifrado de claves.</span><span class="sxs-lookup"><span data-stu-id="55f67-135">Use Aes256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="55f67-136">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="55f67-136">Basic256Rsa15</span></span>|<span data-ttu-id="55f67-137">Utilice Aes256 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="55f67-137">Use Aes256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="55f67-138">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="55f67-138">Basic192Rsa15</span></span>|<span data-ttu-id="55f67-139">Utilice Aes192 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="55f67-139">Use Aes192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="55f67-140">TripleDes</span><span class="sxs-lookup"><span data-stu-id="55f67-140">TripleDes</span></span>|<span data-ttu-id="55f67-141">Utilice el cifrado TripleDes, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="55f67-141">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="55f67-142">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="55f67-142">Basic128Rsa15</span></span>|<span data-ttu-id="55f67-143">Utilice Aes128 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="55f67-143">Use Aes128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="55f67-144">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="55f67-144">TripleDesRsa15</span></span>|<span data-ttu-id="55f67-145">Utilice el cifrado TripleDes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="55f67-145">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="55f67-146">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="55f67-146">Basic128Sha256</span></span>|<span data-ttu-id="55f67-147">Utilice Aes256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="55f67-147">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="55f67-148">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="55f67-148">Basic192Sha256</span></span>|<span data-ttu-id="55f67-149">Utilice Aes192 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="55f67-149">Use Aes192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="55f67-150">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="55f67-150">Basic256Sha256</span></span>|<span data-ttu-id="55f67-151">Utilice Aes256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="55f67-151">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="55f67-152">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="55f67-152">TripleDesSha256</span></span>|<span data-ttu-id="55f67-153">Utilice TripleDes para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="55f67-153">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="55f67-154">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="55f67-154">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="55f67-155">Utilice Aes128 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="55f67-155">Use Aes128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="55f67-156">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="55f67-156">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="55f67-157">Utilice Aes192 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="55f67-157">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="55f67-158">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="55f67-158">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="55f67-159">Utilice Aes256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="55f67-159">Use Aes256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="55f67-160">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="55f67-160">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="55f67-161">Utilice TripleDes para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="55f67-161">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="55f67-162">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="55f67-162">Child Elements</span></span>  
  
|<span data-ttu-id="55f67-163">Elemento</span><span class="sxs-lookup"><span data-stu-id="55f67-163">Element</span></span>|<span data-ttu-id="55f67-164">Descripción</span><span class="sxs-lookup"><span data-stu-id="55f67-164">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-element.md)|<span data-ttu-id="55f67-165">Especifica una colección de tipos de demanda para este enlace.</span><span class="sxs-lookup"><span data-stu-id="55f67-165">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="55f67-166">Cada elemento es del tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="55f67-166">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|[\<issuer>](issuer.md)|<span data-ttu-id="55f67-167">Especifica un punto de conexión que emite un token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="55f67-167">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="55f67-168">Este elemento es del tipo <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="55f67-168">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|[\<issuerMetadata>](issuermetadata.md)|<span data-ttu-id="55f67-169">Especifica la dirección del extremo del emisor.</span><span class="sxs-lookup"><span data-stu-id="55f67-169">Specifies the endpoint address of the issuer.</span></span>|  
|[\<tokenRequestParameters>](tokenrequestparameters.md)|<span data-ttu-id="55f67-170">Una colección de parámetros de solicitud de token.</span><span class="sxs-lookup"><span data-stu-id="55f67-170">A collection of token request parameters.</span></span> <span data-ttu-id="55f67-171">Cada parámetro es un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="55f67-171">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="55f67-172">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="55f67-172">Parent Elements</span></span>  
  
|<span data-ttu-id="55f67-173">Elemento</span><span class="sxs-lookup"><span data-stu-id="55f67-173">Element</span></span>|<span data-ttu-id="55f67-174">Descripción</span><span class="sxs-lookup"><span data-stu-id="55f67-174">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-element-of-ws2007federationhttpbinding.md)|<span data-ttu-id="55f67-175">Define la configuración de seguridad de un enlace.</span><span class="sxs-lookup"><span data-stu-id="55f67-175">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="55f67-176">Consulte también</span><span class="sxs-lookup"><span data-stu-id="55f67-176">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="55f67-177">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="55f67-177">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="55f67-178">Enlaces</span><span class="sxs-lookup"><span data-stu-id="55f67-178">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="55f67-179">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="55f67-179">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="55f67-180">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="55f67-180">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
