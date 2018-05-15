---
title: Elemento &lt;message&gt; de &lt;wsFederationHttpBinding&gt;
ms.date: 03/30/2017
ms.assetid: 9d710389-d9d8-4454-9bf2-da4ccda31cec
ms.openlocfilehash: 24d7370eaadba08d449b886a09cb9903ca0a64c2
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltmessagegt-element-of-ltwsfederationhttpbindinggt"></a><span data-ttu-id="8e59e-102">Elemento &lt;message&gt; de &lt;wsFederationHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="8e59e-102">&lt;message&gt; element of &lt;wsFederationHttpBinding&gt;</span></span>
<span data-ttu-id="8e59e-103">Define la configuración de la seguridad de nivel de mensaje para la [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="8e59e-103">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span></span>  
  
 <span data-ttu-id="8e59e-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8e59e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8e59e-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="8e59e-105">\<bindings></span></span>  
<span data-ttu-id="8e59e-106">\<wsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="8e59e-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="8e59e-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="8e59e-107">\<binding></span></span>  
<span data-ttu-id="8e59e-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="8e59e-108">\<security></span></span>  
<span data-ttu-id="8e59e-109">\<mensaje ></span><span class="sxs-lookup"><span data-stu-id="8e59e-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e59e-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8e59e-110">Syntax</span></span>  
  
```xml  
<wsFederationBinding>  
     <binding >  
         <security>  
         <message   
            algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            issuedTokenType="string"   
            issuedKeyType="SymmetricKey/PublicKey"  
            negotiateServiceCredential="Boolean" >  
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
                              <certificate encodedValue="String"/>  
                                <certificateReference findValue="String"   
                                 isChainIncluded="Boolean"  
                            storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
                                  storeLocation="LocalMachine/CurrentUser"  
                     x509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
                                   <dns value="String"/>  
                                <rsa value="String"/>  
                                <servicePrincipalName value="String"/>  
                                <usePrincipalName value="String"/>  
                              </identity>  
                        </issuer>  
                        <issuerMetadata address=String" >  
               <headers>  
                  <add name="String"  
                       namespace="String" />  
               </headers>  
               <identity>  
                  <certificate encodedValue="String"/>  
                  <certificateReference findValue="String"   
                     isChainIncluded="Boolean"  
                     storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
                     storeLocation="LocalMachine/CurrentUser"  
                     X509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
                  <dns value="String"/>  
                  <rsa value="String"/>  
                  <servicePrincipalName value="String"/>  
                  <usePrincipalName value="String"/>  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8e59e-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8e59e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8e59e-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8e59e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8e59e-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="8e59e-113">Attributes</span></span>  
  
|<span data-ttu-id="8e59e-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="8e59e-114">Attribute</span></span>|<span data-ttu-id="8e59e-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="8e59e-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8e59e-116">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="8e59e-116">algorithmSuite</span></span>|<span data-ttu-id="8e59e-117">Establece el cifrado de mensajes y los algoritmos de encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="8e59e-117">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="8e59e-118">Vea la tabla de "atributo algorithmSuite" para ver los valores válidos de este atributo.</span><span class="sxs-lookup"><span data-stu-id="8e59e-118">See the "algorithmSuite attribute" table for valid values of this attribute.</span></span> <span data-ttu-id="8e59e-119">El valor predeterminado es `Basic256`.</span><span class="sxs-lookup"><span data-stu-id="8e59e-119">The default value is `Basic256`.</span></span><br /><br /> <span data-ttu-id="8e59e-120">Este atributo es del tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="8e59e-120">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span> <span data-ttu-id="8e59e-121">Estos algoritmos se asignan a los indicados en la especificación Lenguaje de directiva de seguridad (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="8e59e-121">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span>|  
|<span data-ttu-id="8e59e-122">issuedKeyType</span><span class="sxs-lookup"><span data-stu-id="8e59e-122">issuedKeyType</span></span>|<span data-ttu-id="8e59e-123">Especifica el tipo de clave que se va a emitir.</span><span class="sxs-lookup"><span data-stu-id="8e59e-123">Specifies the type of key to be issued.</span></span> <span data-ttu-id="8e59e-124">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="8e59e-124">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="8e59e-125">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="8e59e-125">-   SymmetricKey</span></span><br /><span data-ttu-id="8e59e-126">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="8e59e-126">-   PublicKey</span></span><br /><br /> <span data-ttu-id="8e59e-127">De manera predeterminada, es `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="8e59e-127">The default is `SymmetricKey`.</span></span> <span data-ttu-id="8e59e-128">Este atributo es del tipo <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="8e59e-128">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|<span data-ttu-id="8e59e-129">issuedTokenType</span><span class="sxs-lookup"><span data-stu-id="8e59e-129">issuedTokenType</span></span>|<span data-ttu-id="8e59e-130">Una cadena que contiene un URI que especifica el tipo de token que se va a emitir.</span><span class="sxs-lookup"><span data-stu-id="8e59e-130">A string that contains a URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="8e59e-131">De manera predeterminada, es `null`.</span><span class="sxs-lookup"><span data-stu-id="8e59e-131">The default is `null`.</span></span>|  
|<span data-ttu-id="8e59e-132">negotiateServiceCredential</span><span class="sxs-lookup"><span data-stu-id="8e59e-132">negotiateServiceCredential</span></span>|<span data-ttu-id="8e59e-133">Un valor booleano que especifica si la credencial del servicio se debería intercambiar como parte de negociación o estar disponible fuera de la banda.</span><span class="sxs-lookup"><span data-stu-id="8e59e-133">A Boolean value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="8e59e-134">El valor predeterminado es `true`, que significa que se negocia la credencial del servicio.</span><span class="sxs-lookup"><span data-stu-id="8e59e-134">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="8e59e-135">atributo algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="8e59e-135">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="8e59e-136">Valor</span><span class="sxs-lookup"><span data-stu-id="8e59e-136">Value</span></span>|<span data-ttu-id="8e59e-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="8e59e-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8e59e-138">Basic128</span><span class="sxs-lookup"><span data-stu-id="8e59e-138">Basic128</span></span>|<span data-ttu-id="8e59e-139">Utilice el cifrado Basic128, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="8e59e-139">Use Basic128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="8e59e-140">Basic192</span><span class="sxs-lookup"><span data-stu-id="8e59e-140">Basic192</span></span>|<span data-ttu-id="8e59e-141">Utilice el cifrado Basic192, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="8e59e-141">Use Basic192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="8e59e-142">Basic256</span><span class="sxs-lookup"><span data-stu-id="8e59e-142">Basic256</span></span>|<span data-ttu-id="8e59e-143">Utilice el cifrado Basic256, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="8e59e-143">Use Basic256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="8e59e-144">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="8e59e-144">Basic256Rsa15</span></span>|<span data-ttu-id="8e59e-145">Utilice Basic256 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="8e59e-145">Use Basic256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="8e59e-146">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="8e59e-146">Basic192Rsa15</span></span>|<span data-ttu-id="8e59e-147">Utilice Basic192 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="8e59e-147">Use Basic192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="8e59e-148">TripleDes</span><span class="sxs-lookup"><span data-stu-id="8e59e-148">TripleDes</span></span>|<span data-ttu-id="8e59e-149">Utilice el cifrado TripleDes, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="8e59e-149">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="8e59e-150">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="8e59e-150">Basic128Rsa15</span></span>|<span data-ttu-id="8e59e-151">Utilice Basic128 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="8e59e-151">Use Basic128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="8e59e-152">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="8e59e-152">TripleDesRsa15</span></span>|<span data-ttu-id="8e59e-153">Utilice el cifrado TripleDes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="8e59e-153">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="8e59e-154">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="8e59e-154">Basic128Sha256</span></span>|<span data-ttu-id="8e59e-155">Utilice Basic128 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="8e59e-155">Use Basic128 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="8e59e-156">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="8e59e-156">Basic192Sha256</span></span>|<span data-ttu-id="8e59e-157">Utilice Basic192 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="8e59e-157">Use Basic192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="8e59e-158">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="8e59e-158">Basic256Sha256</span></span>|<span data-ttu-id="8e59e-159">Utilice Basic256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="8e59e-159">Use Basic256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="8e59e-160">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="8e59e-160">TripleDesSha256</span></span>|<span data-ttu-id="8e59e-161">Utilice TripleDes para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="8e59e-161">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="8e59e-162">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="8e59e-162">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="8e59e-163">Utilice Basic128 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="8e59e-163">Use Basic128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="8e59e-164">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="8e59e-164">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="8e59e-165">Utilice Aes192 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="8e59e-165">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="8e59e-166">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="8e59e-166">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="8e59e-167">Utilice Basic256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="8e59e-167">Use Basic256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="8e59e-168">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="8e59e-168">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="8e59e-169">Utilice TripleDes para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="8e59e-169">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8e59e-170">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8e59e-170">Child Elements</span></span>  
  
|<span data-ttu-id="8e59e-171">Elemento</span><span class="sxs-lookup"><span data-stu-id="8e59e-171">Element</span></span>|<span data-ttu-id="8e59e-172">Descripción</span><span class="sxs-lookup"><span data-stu-id="8e59e-172">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8e59e-173">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="8e59e-173">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="8e59e-174">Especifica una colección de tipos de demanda para este enlace.</span><span class="sxs-lookup"><span data-stu-id="8e59e-174">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="8e59e-175">Cada elemento es del tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="8e59e-175">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|<span data-ttu-id="8e59e-176">issuer</span><span class="sxs-lookup"><span data-stu-id="8e59e-176">issuer</span></span>|<span data-ttu-id="8e59e-177">Especifica un extremo que emite un token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8e59e-177">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="8e59e-178">Este elemento es del tipo <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="8e59e-178">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|<span data-ttu-id="8e59e-179">issuerMetadata</span><span class="sxs-lookup"><span data-stu-id="8e59e-179">issuerMetadata</span></span>|<span data-ttu-id="8e59e-180">Especifica la dirección del punto de conexión del emisor.</span><span class="sxs-lookup"><span data-stu-id="8e59e-180">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="8e59e-181">\<tokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="8e59e-181">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="8e59e-182">Una colección de parámetros de solicitud de token.</span><span class="sxs-lookup"><span data-stu-id="8e59e-182">A collection of token request parameters.</span></span> <span data-ttu-id="8e59e-183">Cada parámetro es un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="8e59e-183">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8e59e-184">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8e59e-184">Parent Elements</span></span>  
  
|<span data-ttu-id="8e59e-185">Elemento</span><span class="sxs-lookup"><span data-stu-id="8e59e-185">Element</span></span>|<span data-ttu-id="8e59e-186">Descripción</span><span class="sxs-lookup"><span data-stu-id="8e59e-186">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8e59e-187">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="8e59e-187">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md)|<span data-ttu-id="8e59e-188">Define la configuración de seguridad de un enlace.</span><span class="sxs-lookup"><span data-stu-id="8e59e-188">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8e59e-189">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e59e-189">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>  
 <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>  
 <span data-ttu-id="8e59e-190">`System.ServiceModel.Configuration.FederatedMessageSecurityElement` [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)</span><span class="sxs-lookup"><span data-stu-id="8e59e-190">`System.ServiceModel.Configuration.FederatedMessageSecurityElement` [Securing Services and Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)</span></span>  
 [<span data-ttu-id="8e59e-191">Enlaces</span><span class="sxs-lookup"><span data-stu-id="8e59e-191">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="8e59e-192">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="8e59e-192">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="8e59e-193">Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="8e59e-193">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="8e59e-194">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="8e59e-194">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
