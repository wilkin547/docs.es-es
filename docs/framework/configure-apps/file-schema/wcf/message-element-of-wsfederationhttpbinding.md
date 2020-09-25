---
title: <message> elemento de <wsFederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9d710389-d9d8-4454-9bf2-da4ccda31cec
ms.openlocfilehash: ea320b1d97e742d4f90ec55502f3bd429803283d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204897"
---
# <a name="message-element-of-wsfederationhttpbinding"></a><span data-ttu-id="aab06-102">\<message> elemento de \<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="aab06-102">\<message> element of \<wsFederationHttpBinding></span></span>

<span data-ttu-id="aab06-103">Define la configuración para la seguridad de nivel de mensaje para [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="aab06-103">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  
  
## <a name="syntax"></a><span data-ttu-id="aab06-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aab06-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aab06-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="aab06-105">Attributes and Elements</span></span>  

 <span data-ttu-id="aab06-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="aab06-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aab06-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="aab06-107">Attributes</span></span>  
  
|<span data-ttu-id="aab06-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="aab06-108">Attribute</span></span>|<span data-ttu-id="aab06-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="aab06-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aab06-110">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="aab06-110">algorithmSuite</span></span>|<span data-ttu-id="aab06-111">Establece el cifrado de mensajes y los algoritmos de encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="aab06-111">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="aab06-112">Vea la tabla de "atributo algorithmSuite" para ver los valores válidos de este atributo.</span><span class="sxs-lookup"><span data-stu-id="aab06-112">See the "algorithmSuite attribute" table for valid values of this attribute.</span></span> <span data-ttu-id="aab06-113">El valor predeterminado es `Basic256`.</span><span class="sxs-lookup"><span data-stu-id="aab06-113">The default value is `Basic256`.</span></span><br /><br /> <span data-ttu-id="aab06-114">Este atributo es del tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="aab06-114">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span> <span data-ttu-id="aab06-115">Estos algoritmos se asignan a los que se indican en la especificación Security Policy Language (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="aab06-115">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span>|  
|<span data-ttu-id="aab06-116">issuedKeyType</span><span class="sxs-lookup"><span data-stu-id="aab06-116">issuedKeyType</span></span>|<span data-ttu-id="aab06-117">Especifica el tipo de clave que se va a emitir.</span><span class="sxs-lookup"><span data-stu-id="aab06-117">Specifies the type of key to be issued.</span></span> <span data-ttu-id="aab06-118">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="aab06-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="aab06-119">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="aab06-119">-   SymmetricKey</span></span><br /><span data-ttu-id="aab06-120">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="aab06-120">-   PublicKey</span></span><br /><br /> <span data-ttu-id="aab06-121">El valor predeterminado es `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="aab06-121">The default is `SymmetricKey`.</span></span> <span data-ttu-id="aab06-122">Este atributo es del tipo <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="aab06-122">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|<span data-ttu-id="aab06-123">issuedTokenType</span><span class="sxs-lookup"><span data-stu-id="aab06-123">issuedTokenType</span></span>|<span data-ttu-id="aab06-124">Una cadena que contiene un URI que especifica el tipo de token que se va a emitir.</span><span class="sxs-lookup"><span data-stu-id="aab06-124">A string that contains a URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="aab06-125">El valor predeterminado es `null`.</span><span class="sxs-lookup"><span data-stu-id="aab06-125">The default is `null`.</span></span>|  
|<span data-ttu-id="aab06-126">negotiateServiceCredential</span><span class="sxs-lookup"><span data-stu-id="aab06-126">negotiateServiceCredential</span></span>|<span data-ttu-id="aab06-127">Un valor booleano que especifica si la credencial del servicio se debería intercambiar como parte de negociación o estar disponible fuera de la banda.</span><span class="sxs-lookup"><span data-stu-id="aab06-127">A Boolean value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="aab06-128">El valor predeterminado es `true`, que significa que se negocia la credencial del servicio.</span><span class="sxs-lookup"><span data-stu-id="aab06-128">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="aab06-129">atributo algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="aab06-129">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="aab06-130">Value</span><span class="sxs-lookup"><span data-stu-id="aab06-130">Value</span></span>|<span data-ttu-id="aab06-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="aab06-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="aab06-132">Basic128</span><span class="sxs-lookup"><span data-stu-id="aab06-132">Basic128</span></span>|<span data-ttu-id="aab06-133">Utilice el cifrado Basic128, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="aab06-133">Use Basic128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="aab06-134">Basic192</span><span class="sxs-lookup"><span data-stu-id="aab06-134">Basic192</span></span>|<span data-ttu-id="aab06-135">Utilice el cifrado Basic192, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="aab06-135">Use Basic192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="aab06-136">Basic256</span><span class="sxs-lookup"><span data-stu-id="aab06-136">Basic256</span></span>|<span data-ttu-id="aab06-137">Utilice el cifrado Basic256, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="aab06-137">Use Basic256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="aab06-138">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="aab06-138">Basic256Rsa15</span></span>|<span data-ttu-id="aab06-139">Utilice Basic256 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="aab06-139">Use Basic256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="aab06-140">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="aab06-140">Basic192Rsa15</span></span>|<span data-ttu-id="aab06-141">Utilice Basic192 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="aab06-141">Use Basic192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="aab06-142">TripleDes</span><span class="sxs-lookup"><span data-stu-id="aab06-142">TripleDes</span></span>|<span data-ttu-id="aab06-143">Utilice el cifrado TripleDes, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="aab06-143">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="aab06-144">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="aab06-144">Basic128Rsa15</span></span>|<span data-ttu-id="aab06-145">Utilice Basic128 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="aab06-145">Use Basic128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="aab06-146">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="aab06-146">TripleDesRsa15</span></span>|<span data-ttu-id="aab06-147">Utilice el cifrado TripleDes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="aab06-147">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="aab06-148">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="aab06-148">Basic128Sha256</span></span>|<span data-ttu-id="aab06-149">Utilice Basic128 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="aab06-149">Use Basic128 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="aab06-150">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="aab06-150">Basic192Sha256</span></span>|<span data-ttu-id="aab06-151">Utilice Basic192 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="aab06-151">Use Basic192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="aab06-152">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="aab06-152">Basic256Sha256</span></span>|<span data-ttu-id="aab06-153">Utilice Basic256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="aab06-153">Use Basic256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="aab06-154">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="aab06-154">TripleDesSha256</span></span>|<span data-ttu-id="aab06-155">Utilice TripleDes para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="aab06-155">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="aab06-156">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="aab06-156">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="aab06-157">Utilice Basic128 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="aab06-157">Use Basic128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="aab06-158">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="aab06-158">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="aab06-159">Utilice Aes192 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="aab06-159">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="aab06-160">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="aab06-160">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="aab06-161">Utilice Basic256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="aab06-161">Use Basic256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="aab06-162">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="aab06-162">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="aab06-163">Utilice TripleDes para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="aab06-163">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aab06-164">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="aab06-164">Child Elements</span></span>  
  
|<span data-ttu-id="aab06-165">Elemento</span><span class="sxs-lookup"><span data-stu-id="aab06-165">Element</span></span>|<span data-ttu-id="aab06-166">Descripción</span><span class="sxs-lookup"><span data-stu-id="aab06-166">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-element.md)|<span data-ttu-id="aab06-167">Especifica una colección de tipos de demanda para este enlace.</span><span class="sxs-lookup"><span data-stu-id="aab06-167">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="aab06-168">Cada elemento es del tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="aab06-168">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|<span data-ttu-id="aab06-169">issuer</span><span class="sxs-lookup"><span data-stu-id="aab06-169">issuer</span></span>|<span data-ttu-id="aab06-170">Especifica un punto de conexión que emite un token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="aab06-170">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="aab06-171">Este elemento es del tipo <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="aab06-171">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|<span data-ttu-id="aab06-172">issuerMetadata</span><span class="sxs-lookup"><span data-stu-id="aab06-172">issuerMetadata</span></span>|<span data-ttu-id="aab06-173">Especifica la dirección del extremo del emisor.</span><span class="sxs-lookup"><span data-stu-id="aab06-173">Specifies the endpoint address of the issuer.</span></span>|  
|[\<tokenRequestParameters>](tokenrequestparameters.md)|<span data-ttu-id="aab06-174">Una colección de parámetros de solicitud de token.</span><span class="sxs-lookup"><span data-stu-id="aab06-174">A collection of token request parameters.</span></span> <span data-ttu-id="aab06-175">Cada parámetro es un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="aab06-175">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aab06-176">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="aab06-176">Parent Elements</span></span>  
  
|<span data-ttu-id="aab06-177">Elemento</span><span class="sxs-lookup"><span data-stu-id="aab06-177">Element</span></span>|<span data-ttu-id="aab06-178">Descripción</span><span class="sxs-lookup"><span data-stu-id="aab06-178">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-wsfederationhttpbinding.md)|<span data-ttu-id="aab06-179">Define la configuración de seguridad de un enlace.</span><span class="sxs-lookup"><span data-stu-id="aab06-179">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aab06-180">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aab06-180">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="aab06-181">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="aab06-181">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="aab06-182">Enlaces</span><span class="sxs-lookup"><span data-stu-id="aab06-182">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="aab06-183">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="aab06-183">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="aab06-184">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="aab06-184">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
