---
description: 'Más información acerca <message> de: elemento de <wsFederationHttpBinding>'
title: <message> elemento de <wsFederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9d710389-d9d8-4454-9bf2-da4ccda31cec
ms.openlocfilehash: 64978902081ec9e5a603804fed3b378da12fe42e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802195"
---
# <a name="message-element-of-wsfederationhttpbinding"></a><span data-ttu-id="133c3-103">\<message> elemento de \<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="133c3-103">\<message> element of \<wsFederationHttpBinding></span></span>

<span data-ttu-id="133c3-104">Define la configuración para la seguridad de nivel de mensaje para [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="133c3-104">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  
  
## <a name="syntax"></a><span data-ttu-id="133c3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="133c3-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="133c3-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="133c3-106">Attributes and Elements</span></span>  

 <span data-ttu-id="133c3-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="133c3-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="133c3-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="133c3-108">Attributes</span></span>  
  
|<span data-ttu-id="133c3-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="133c3-109">Attribute</span></span>|<span data-ttu-id="133c3-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="133c3-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="133c3-111">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="133c3-111">algorithmSuite</span></span>|<span data-ttu-id="133c3-112">Establece el cifrado de mensajes y los algoritmos de encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="133c3-112">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="133c3-113">Vea la tabla de "atributo algorithmSuite" para ver los valores válidos de este atributo.</span><span class="sxs-lookup"><span data-stu-id="133c3-113">See the "algorithmSuite attribute" table for valid values of this attribute.</span></span> <span data-ttu-id="133c3-114">El valor predeterminado es `Basic256`.</span><span class="sxs-lookup"><span data-stu-id="133c3-114">The default value is `Basic256`.</span></span><br /><br /> <span data-ttu-id="133c3-115">Este atributo es del tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="133c3-115">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span> <span data-ttu-id="133c3-116">Estos algoritmos se asignan a los que se indican en la especificación Security Policy Language (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="133c3-116">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span>|  
|<span data-ttu-id="133c3-117">issuedKeyType</span><span class="sxs-lookup"><span data-stu-id="133c3-117">issuedKeyType</span></span>|<span data-ttu-id="133c3-118">Especifica el tipo de clave que se va a emitir.</span><span class="sxs-lookup"><span data-stu-id="133c3-118">Specifies the type of key to be issued.</span></span> <span data-ttu-id="133c3-119">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="133c3-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="133c3-120">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="133c3-120">-   SymmetricKey</span></span><br /><span data-ttu-id="133c3-121">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="133c3-121">-   PublicKey</span></span><br /><br /> <span data-ttu-id="133c3-122">De manera predeterminada, es `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="133c3-122">The default is `SymmetricKey`.</span></span> <span data-ttu-id="133c3-123">Este atributo es del tipo <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="133c3-123">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|<span data-ttu-id="133c3-124">issuedTokenType</span><span class="sxs-lookup"><span data-stu-id="133c3-124">issuedTokenType</span></span>|<span data-ttu-id="133c3-125">Una cadena que contiene un URI que especifica el tipo de token que se va a emitir.</span><span class="sxs-lookup"><span data-stu-id="133c3-125">A string that contains a URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="133c3-126">De manera predeterminada, es `null`.</span><span class="sxs-lookup"><span data-stu-id="133c3-126">The default is `null`.</span></span>|  
|<span data-ttu-id="133c3-127">negotiateServiceCredential</span><span class="sxs-lookup"><span data-stu-id="133c3-127">negotiateServiceCredential</span></span>|<span data-ttu-id="133c3-128">Un valor booleano que especifica si la credencial del servicio se debería intercambiar como parte de negociación o estar disponible fuera de la banda.</span><span class="sxs-lookup"><span data-stu-id="133c3-128">A Boolean value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="133c3-129">El valor predeterminado es `true`, que significa que se negocia la credencial del servicio.</span><span class="sxs-lookup"><span data-stu-id="133c3-129">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="133c3-130">atributo algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="133c3-130">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="133c3-131">Value</span><span class="sxs-lookup"><span data-stu-id="133c3-131">Value</span></span>|<span data-ttu-id="133c3-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="133c3-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="133c3-133">Basic128</span><span class="sxs-lookup"><span data-stu-id="133c3-133">Basic128</span></span>|<span data-ttu-id="133c3-134">Utilice el cifrado Basic128, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="133c3-134">Use Basic128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="133c3-135">Basic192</span><span class="sxs-lookup"><span data-stu-id="133c3-135">Basic192</span></span>|<span data-ttu-id="133c3-136">Utilice el cifrado Basic192, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="133c3-136">Use Basic192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="133c3-137">Basic256</span><span class="sxs-lookup"><span data-stu-id="133c3-137">Basic256</span></span>|<span data-ttu-id="133c3-138">Utilice el cifrado Basic256, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="133c3-138">Use Basic256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="133c3-139">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="133c3-139">Basic256Rsa15</span></span>|<span data-ttu-id="133c3-140">Utilice Basic256 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="133c3-140">Use Basic256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="133c3-141">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="133c3-141">Basic192Rsa15</span></span>|<span data-ttu-id="133c3-142">Utilice Basic192 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="133c3-142">Use Basic192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="133c3-143">TripleDes</span><span class="sxs-lookup"><span data-stu-id="133c3-143">TripleDes</span></span>|<span data-ttu-id="133c3-144">Utilice el cifrado TripleDes, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="133c3-144">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="133c3-145">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="133c3-145">Basic128Rsa15</span></span>|<span data-ttu-id="133c3-146">Utilice Basic128 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="133c3-146">Use Basic128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="133c3-147">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="133c3-147">TripleDesRsa15</span></span>|<span data-ttu-id="133c3-148">Utilice el cifrado TripleDes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="133c3-148">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="133c3-149">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="133c3-149">Basic128Sha256</span></span>|<span data-ttu-id="133c3-150">Utilice Basic128 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="133c3-150">Use Basic128 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="133c3-151">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="133c3-151">Basic192Sha256</span></span>|<span data-ttu-id="133c3-152">Utilice Basic192 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="133c3-152">Use Basic192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="133c3-153">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="133c3-153">Basic256Sha256</span></span>|<span data-ttu-id="133c3-154">Utilice Basic256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="133c3-154">Use Basic256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="133c3-155">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="133c3-155">TripleDesSha256</span></span>|<span data-ttu-id="133c3-156">Utilice TripleDes para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="133c3-156">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="133c3-157">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="133c3-157">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="133c3-158">Utilice Basic128 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="133c3-158">Use Basic128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="133c3-159">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="133c3-159">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="133c3-160">Utilice Aes192 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="133c3-160">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="133c3-161">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="133c3-161">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="133c3-162">Utilice Basic256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="133c3-162">Use Basic256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="133c3-163">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="133c3-163">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="133c3-164">Utilice TripleDes para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="133c3-164">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="133c3-165">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="133c3-165">Child Elements</span></span>  
  
|<span data-ttu-id="133c3-166">Elemento</span><span class="sxs-lookup"><span data-stu-id="133c3-166">Element</span></span>|<span data-ttu-id="133c3-167">Descripción</span><span class="sxs-lookup"><span data-stu-id="133c3-167">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-element.md)|<span data-ttu-id="133c3-168">Especifica una colección de tipos de demanda para este enlace.</span><span class="sxs-lookup"><span data-stu-id="133c3-168">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="133c3-169">Cada elemento es del tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="133c3-169">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|<span data-ttu-id="133c3-170">issuer</span><span class="sxs-lookup"><span data-stu-id="133c3-170">issuer</span></span>|<span data-ttu-id="133c3-171">Especifica un punto de conexión que emite un token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="133c3-171">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="133c3-172">Este elemento es del tipo <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="133c3-172">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|<span data-ttu-id="133c3-173">issuerMetadata</span><span class="sxs-lookup"><span data-stu-id="133c3-173">issuerMetadata</span></span>|<span data-ttu-id="133c3-174">Especifica la dirección del extremo del emisor.</span><span class="sxs-lookup"><span data-stu-id="133c3-174">Specifies the endpoint address of the issuer.</span></span>|  
|[\<tokenRequestParameters>](tokenrequestparameters.md)|<span data-ttu-id="133c3-175">Una colección de parámetros de solicitud de token.</span><span class="sxs-lookup"><span data-stu-id="133c3-175">A collection of token request parameters.</span></span> <span data-ttu-id="133c3-176">Cada parámetro es un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="133c3-176">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="133c3-177">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="133c3-177">Parent Elements</span></span>  
  
|<span data-ttu-id="133c3-178">Elemento</span><span class="sxs-lookup"><span data-stu-id="133c3-178">Element</span></span>|<span data-ttu-id="133c3-179">Descripción</span><span class="sxs-lookup"><span data-stu-id="133c3-179">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-wsfederationhttpbinding.md)|<span data-ttu-id="133c3-180">Define la configuración de seguridad de un enlace.</span><span class="sxs-lookup"><span data-stu-id="133c3-180">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="133c3-181">Vea también</span><span class="sxs-lookup"><span data-stu-id="133c3-181">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="133c3-182">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="133c3-182">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="133c3-183">Enlaces</span><span class="sxs-lookup"><span data-stu-id="133c3-183">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="133c3-184">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="133c3-184">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="133c3-185">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="133c3-185">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
