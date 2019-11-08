---
title: <message> elemento de <wsFederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9d710389-d9d8-4454-9bf2-da4ccda31cec
ms.openlocfilehash: 8e0903dd1313e68e2de65730e129079199ebe2f2
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738987"
---
# <a name="message-element-of-wsfederationhttpbinding"></a><span data-ttu-id="aaa4b-102">\<mensaje > elemento de \<wsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="aaa4b-102">\<message> element of \<wsFederationHttpBinding></span></span>
<span data-ttu-id="aaa4b-103">Define la configuración para la seguridad de nivel de mensaje para el [\<wsFederationHttpBinding >](wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="aaa4b-103">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>  
  
<span data-ttu-id="aaa4b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="aaa4b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="aaa4b-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="aaa4b-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="aaa4b-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**enlaces**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="aaa4b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="aaa4b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsFederationHttpBinding**](wsfederationhttpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="aaa4b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="aaa4b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**enlace** ></span><span class="sxs-lookup"><span data-stu-id="aaa4b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="aaa4b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**seguridad**](security-of-wsfederationhttpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="aaa4b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="aaa4b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**mensaje** ></span><span class="sxs-lookup"><span data-stu-id="aaa4b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aaa4b-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aaa4b-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aaa4b-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="aaa4b-112">Attributes and Elements</span></span>  
 <span data-ttu-id="aaa4b-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="aaa4b-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aaa4b-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="aaa4b-114">Attributes</span></span>  
  
|<span data-ttu-id="aaa4b-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="aaa4b-115">Attribute</span></span>|<span data-ttu-id="aaa4b-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="aaa4b-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aaa4b-117">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="aaa4b-117">algorithmSuite</span></span>|<span data-ttu-id="aaa4b-118">Establece el cifrado de mensajes y los algoritmos de encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="aaa4b-118">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="aaa4b-119">Vea la tabla de "atributo algorithmSuite" para ver los valores válidos de este atributo.</span><span class="sxs-lookup"><span data-stu-id="aaa4b-119">See the "algorithmSuite attribute" table for valid values of this attribute.</span></span> <span data-ttu-id="aaa4b-120">El valor predeterminado es `Basic256`.</span><span class="sxs-lookup"><span data-stu-id="aaa4b-120">The default value is `Basic256`.</span></span><br /><br /> <span data-ttu-id="aaa4b-121">Este atributo es del tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="aaa4b-121">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span> <span data-ttu-id="aaa4b-122">Estos algoritmos se asignan a los indicados en la especificación Lenguaje de directiva de seguridad (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="aaa4b-122">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span>|  
|<span data-ttu-id="aaa4b-123">issuedKeyType</span><span class="sxs-lookup"><span data-stu-id="aaa4b-123">issuedKeyType</span></span>|<span data-ttu-id="aaa4b-124">Especifica el tipo de clave que se va a emitir.</span><span class="sxs-lookup"><span data-stu-id="aaa4b-124">Specifies the type of key to be issued.</span></span> <span data-ttu-id="aaa4b-125">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="aaa4b-125">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="aaa4b-126">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="aaa4b-126">-   SymmetricKey</span></span><br /><span data-ttu-id="aaa4b-127">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="aaa4b-127">-   PublicKey</span></span><br /><br /> <span data-ttu-id="aaa4b-128">De manera predeterminada, es `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="aaa4b-128">The default is `SymmetricKey`.</span></span> <span data-ttu-id="aaa4b-129">Este atributo es del tipo <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="aaa4b-129">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|<span data-ttu-id="aaa4b-130">issuedTokenType</span><span class="sxs-lookup"><span data-stu-id="aaa4b-130">issuedTokenType</span></span>|<span data-ttu-id="aaa4b-131">Una cadena que contiene un URI que especifica el tipo de token que se va a emitir.</span><span class="sxs-lookup"><span data-stu-id="aaa4b-131">A string that contains a URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="aaa4b-132">De manera predeterminada, es `null`.</span><span class="sxs-lookup"><span data-stu-id="aaa4b-132">The default is `null`.</span></span>|  
|<span data-ttu-id="aaa4b-133">negotiateServiceCredential</span><span class="sxs-lookup"><span data-stu-id="aaa4b-133">negotiateServiceCredential</span></span>|<span data-ttu-id="aaa4b-134">Un valor booleano que especifica si la credencial del servicio se debería intercambiar como parte de negociación o estar disponible fuera de la banda.</span><span class="sxs-lookup"><span data-stu-id="aaa4b-134">A Boolean value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="aaa4b-135">El valor predeterminado es `true`, que significa que se negocia la credencial del servicio.</span><span class="sxs-lookup"><span data-stu-id="aaa4b-135">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="aaa4b-136">atributo algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="aaa4b-136">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="aaa4b-137">Valor</span><span class="sxs-lookup"><span data-stu-id="aaa4b-137">Value</span></span>|<span data-ttu-id="aaa4b-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="aaa4b-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="aaa4b-139">Basic128</span><span class="sxs-lookup"><span data-stu-id="aaa4b-139">Basic128</span></span>|<span data-ttu-id="aaa4b-140">Utilice el cifrado Basic128, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="aaa4b-140">Use Basic128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="aaa4b-141">Basic192</span><span class="sxs-lookup"><span data-stu-id="aaa4b-141">Basic192</span></span>|<span data-ttu-id="aaa4b-142">Utilice el cifrado Basic192, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="aaa4b-142">Use Basic192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="aaa4b-143">Basic256</span><span class="sxs-lookup"><span data-stu-id="aaa4b-143">Basic256</span></span>|<span data-ttu-id="aaa4b-144">Utilice el cifrado Basic256, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="aaa4b-144">Use Basic256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="aaa4b-145">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="aaa4b-145">Basic256Rsa15</span></span>|<span data-ttu-id="aaa4b-146">Utilice Basic256 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="aaa4b-146">Use Basic256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="aaa4b-147">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="aaa4b-147">Basic192Rsa15</span></span>|<span data-ttu-id="aaa4b-148">Utilice Basic192 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="aaa4b-148">Use Basic192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="aaa4b-149">TripleDes</span><span class="sxs-lookup"><span data-stu-id="aaa4b-149">TripleDes</span></span>|<span data-ttu-id="aaa4b-150">Utilice el cifrado TripleDes, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="aaa4b-150">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="aaa4b-151">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="aaa4b-151">Basic128Rsa15</span></span>|<span data-ttu-id="aaa4b-152">Utilice Basic128 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="aaa4b-152">Use Basic128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="aaa4b-153">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="aaa4b-153">TripleDesRsa15</span></span>|<span data-ttu-id="aaa4b-154">Utilice el cifrado TripleDes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="aaa4b-154">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="aaa4b-155">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="aaa4b-155">Basic128Sha256</span></span>|<span data-ttu-id="aaa4b-156">Utilice Basic128 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="aaa4b-156">Use Basic128 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="aaa4b-157">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="aaa4b-157">Basic192Sha256</span></span>|<span data-ttu-id="aaa4b-158">Utilice Basic192 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="aaa4b-158">Use Basic192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="aaa4b-159">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="aaa4b-159">Basic256Sha256</span></span>|<span data-ttu-id="aaa4b-160">Utilice Basic256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="aaa4b-160">Use Basic256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="aaa4b-161">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="aaa4b-161">TripleDesSha256</span></span>|<span data-ttu-id="aaa4b-162">Utilice TripleDes para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="aaa4b-162">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="aaa4b-163">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="aaa4b-163">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="aaa4b-164">Utilice Basic128 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="aaa4b-164">Use Basic128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="aaa4b-165">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="aaa4b-165">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="aaa4b-166">Utilice Aes192 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="aaa4b-166">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="aaa4b-167">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="aaa4b-167">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="aaa4b-168">Utilice Basic256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="aaa4b-168">Use Basic256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="aaa4b-169">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="aaa4b-169">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="aaa4b-170">Utilice TripleDes para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="aaa4b-170">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aaa4b-171">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="aaa4b-171">Child Elements</span></span>  
  
|<span data-ttu-id="aaa4b-172">Elemento</span><span class="sxs-lookup"><span data-stu-id="aaa4b-172">Element</span></span>|<span data-ttu-id="aaa4b-173">Descripción</span><span class="sxs-lookup"><span data-stu-id="aaa4b-173">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aaa4b-174">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="aaa4b-174">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)|<span data-ttu-id="aaa4b-175">Especifica una colección de tipos de demanda para este enlace.</span><span class="sxs-lookup"><span data-stu-id="aaa4b-175">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="aaa4b-176">Cada elemento es del tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="aaa4b-176">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|<span data-ttu-id="aaa4b-177">issuer</span><span class="sxs-lookup"><span data-stu-id="aaa4b-177">issuer</span></span>|<span data-ttu-id="aaa4b-178">Especifica un punto de conexión que emite un token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="aaa4b-178">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="aaa4b-179">Este elemento es del tipo <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="aaa4b-179">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|<span data-ttu-id="aaa4b-180">issuerMetadata</span><span class="sxs-lookup"><span data-stu-id="aaa4b-180">issuerMetadata</span></span>|<span data-ttu-id="aaa4b-181">Especifica la dirección del extremo del emisor.</span><span class="sxs-lookup"><span data-stu-id="aaa4b-181">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="aaa4b-182">\<tokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="aaa4b-182">\<tokenRequestParameters></span></span>](tokenrequestparameters.md)|<span data-ttu-id="aaa4b-183">Una colección de parámetros de solicitud de token.</span><span class="sxs-lookup"><span data-stu-id="aaa4b-183">A collection of token request parameters.</span></span> <span data-ttu-id="aaa4b-184">Cada parámetro es un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="aaa4b-184">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aaa4b-185">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="aaa4b-185">Parent Elements</span></span>  
  
|<span data-ttu-id="aaa4b-186">Elemento</span><span class="sxs-lookup"><span data-stu-id="aaa4b-186">Element</span></span>|<span data-ttu-id="aaa4b-187">Descripción</span><span class="sxs-lookup"><span data-stu-id="aaa4b-187">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aaa4b-188">\<La ></span><span class="sxs-lookup"><span data-stu-id="aaa4b-188">\<security></span></span>](security-of-wsfederationhttpbinding.md)|<span data-ttu-id="aaa4b-189">Define la configuración de seguridad de un enlace.</span><span class="sxs-lookup"><span data-stu-id="aaa4b-189">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aaa4b-190">Vea también</span><span class="sxs-lookup"><span data-stu-id="aaa4b-190">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="aaa4b-191">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="aaa4b-191">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="aaa4b-192">Enlaces</span><span class="sxs-lookup"><span data-stu-id="aaa4b-192">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="aaa4b-193">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="aaa4b-193">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="aaa4b-194">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="aaa4b-194">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="aaa4b-195">\<> de enlace</span><span class="sxs-lookup"><span data-stu-id="aaa4b-195">\<binding></span></span>](bindings.md)
