---
title: Elemento &lt;message&gt; de &lt;ws2007FederationHttpBinding&gt;
ms.date: 03/30/2017
ms.assetid: 52cd941d-e230-4c82-8b29-333a7d20eca8
ms.openlocfilehash: 3f0dbc3128af812c7fd09eed5acd90ab43ec8351
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "47207262"
---
# <a name="ltmessagegt-element-of-ltws2007federationhttpbindinggt"></a><span data-ttu-id="694e7-102">Elemento &lt;message&gt; de &lt;ws2007FederationHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="694e7-102">&lt;message&gt; element of &lt;ws2007FederationHttpBinding&gt;</span></span>
<span data-ttu-id="694e7-103">Define la configuración de seguridad de nivel de mensaje para el [ \<ws2007FederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="694e7-103">Defines settings for the message-level security for the [\<ws2007FederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) element.</span></span>  
  
 <span data-ttu-id="694e7-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="694e7-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="694e7-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="694e7-105">\<bindings></span></span>  
<span data-ttu-id="694e7-106">\<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="694e7-106">\<ws2007FederationHttpBinding></span></span>  
<span data-ttu-id="694e7-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="694e7-107">\<binding></span></span>  
<span data-ttu-id="694e7-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="694e7-108">\<security></span></span>  
<span data-ttu-id="694e7-109">\<mensaje ></span><span class="sxs-lookup"><span data-stu-id="694e7-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="694e7-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="694e7-110">Syntax</span></span>  
  
```xml  
<ws2007FederationBinding>  
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
</ws2007FederationBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="694e7-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="694e7-111">Attributes and Elements</span></span>  
 <span data-ttu-id="694e7-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="694e7-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="694e7-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="694e7-113">Attributes</span></span>  
  
|<span data-ttu-id="694e7-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="694e7-114">Attribute</span></span>|<span data-ttu-id="694e7-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="694e7-115">Description</span></span>|  
|---------------|-----------------|  
|`algorithmSuite`|<span data-ttu-id="694e7-116">Opcional.</span><span class="sxs-lookup"><span data-stu-id="694e7-116">Optional.</span></span> <span data-ttu-id="694e7-117">Establece el cifrado de mensajes, la firma y los algoritmos del ajuste de clave.</span><span class="sxs-lookup"><span data-stu-id="694e7-117">Sets the message encryption, signature, and key-wrap algorithms.</span></span> <span data-ttu-id="694e7-118">La clase <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> determina los algoritmos y los tamaños de clave.</span><span class="sxs-lookup"><span data-stu-id="694e7-118">The algorithms and the key sizes are determined by the <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> class.</span></span> <span data-ttu-id="694e7-119">Estos algoritmos se asignan a los indicados en la especificación Lenguaje de directiva de seguridad (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="694e7-119">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="694e7-120">En la siguiente tabla se enumeran los posibles valores.</span><span class="sxs-lookup"><span data-stu-id="694e7-120">See the following table for possible values.</span></span> <span data-ttu-id="694e7-121">El valor predeterminado es Basic256.</span><span class="sxs-lookup"><span data-stu-id="694e7-121">The default value is Basic256.</span></span>|  
|`issuedKeyType`|<span data-ttu-id="694e7-122">Especifica el tipo de clave que se va a emitir.</span><span class="sxs-lookup"><span data-stu-id="694e7-122">Specifies the type of key to be issued.</span></span> <span data-ttu-id="694e7-123">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="694e7-123">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="694e7-124">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="694e7-124">-   SymmetricKey</span></span><br /><span data-ttu-id="694e7-125">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="694e7-125">-   PublicKey</span></span><br /><span data-ttu-id="694e7-126">-BearerKey</span><span class="sxs-lookup"><span data-stu-id="694e7-126">-   BearerKey</span></span><br /><br /> <span data-ttu-id="694e7-127">El valor predeterminado es SymmetricKey.</span><span class="sxs-lookup"><span data-stu-id="694e7-127">The default is SymmetricKey.</span></span> <span data-ttu-id="694e7-128">Este atributo es del tipo <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="694e7-128">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|`issuedTokenType`|<span data-ttu-id="694e7-129">Un URI que especifica el tipo de token que se va a emitir.</span><span class="sxs-lookup"><span data-stu-id="694e7-129">A URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="694e7-130">De manera predeterminada, es `null`.</span><span class="sxs-lookup"><span data-stu-id="694e7-130">The default is `null`.</span></span>|  
|`negotiateServiceCredential`|<span data-ttu-id="694e7-131">Un valor que especifica si la credencial del servicio se debería intercambiar como parte de negociación o estar disponible fuera de la banda.</span><span class="sxs-lookup"><span data-stu-id="694e7-131">A value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="694e7-132">El valor predeterminado es `true`, que significa que se negocia la credencial del servicio.</span><span class="sxs-lookup"><span data-stu-id="694e7-132">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="694e7-133">atributo algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="694e7-133">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="694e7-134">Valor</span><span class="sxs-lookup"><span data-stu-id="694e7-134">Value</span></span>|<span data-ttu-id="694e7-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="694e7-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="694e7-136">Basic128</span><span class="sxs-lookup"><span data-stu-id="694e7-136">Basic128</span></span>|<span data-ttu-id="694e7-137">Utilice el cifrado Aes128, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="694e7-137">Use Aes128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="694e7-138">Basic192</span><span class="sxs-lookup"><span data-stu-id="694e7-138">Basic192</span></span>|<span data-ttu-id="694e7-139">Utilice el cifrado Aes192, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="694e7-139">Use Aes192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="694e7-140">Basic256</span><span class="sxs-lookup"><span data-stu-id="694e7-140">Basic256</span></span>|<span data-ttu-id="694e7-141">Utilice el cifrado Aes256, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el cifrado de claves.</span><span class="sxs-lookup"><span data-stu-id="694e7-141">Use Aes256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="694e7-142">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="694e7-142">Basic256Rsa15</span></span>|<span data-ttu-id="694e7-143">Utilice Aes256 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="694e7-143">Use Aes256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="694e7-144">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="694e7-144">Basic192Rsa15</span></span>|<span data-ttu-id="694e7-145">Utilice Aes192 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="694e7-145">Use Aes192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="694e7-146">TripleDes</span><span class="sxs-lookup"><span data-stu-id="694e7-146">TripleDes</span></span>|<span data-ttu-id="694e7-147">Utilice el cifrado TripleDes, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="694e7-147">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="694e7-148">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="694e7-148">Basic128Rsa15</span></span>|<span data-ttu-id="694e7-149">Utilice Aes128 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="694e7-149">Use Aes128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="694e7-150">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="694e7-150">TripleDesRsa15</span></span>|<span data-ttu-id="694e7-151">Utilice el cifrado TripleDes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="694e7-151">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="694e7-152">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="694e7-152">Basic128Sha256</span></span>|<span data-ttu-id="694e7-153">Utilice Aes256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="694e7-153">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="694e7-154">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="694e7-154">Basic192Sha256</span></span>|<span data-ttu-id="694e7-155">Utilice Aes192 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="694e7-155">Use Aes192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="694e7-156">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="694e7-156">Basic256Sha256</span></span>|<span data-ttu-id="694e7-157">Utilice Aes256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="694e7-157">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="694e7-158">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="694e7-158">TripleDesSha256</span></span>|<span data-ttu-id="694e7-159">Utilice TripleDes para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="694e7-159">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="694e7-160">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="694e7-160">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="694e7-161">Utilice Aes128 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="694e7-161">Use Aes128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="694e7-162">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="694e7-162">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="694e7-163">Utilice Aes192 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="694e7-163">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="694e7-164">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="694e7-164">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="694e7-165">Utilice Aes256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="694e7-165">Use Aes256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="694e7-166">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="694e7-166">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="694e7-167">Utilice TripleDes para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="694e7-167">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="694e7-168">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="694e7-168">Child Elements</span></span>  
  
|<span data-ttu-id="694e7-169">Elemento</span><span class="sxs-lookup"><span data-stu-id="694e7-169">Element</span></span>|<span data-ttu-id="694e7-170">Descripción</span><span class="sxs-lookup"><span data-stu-id="694e7-170">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="694e7-171">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="694e7-171">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="694e7-172">Especifica una colección de tipos de demanda para este enlace.</span><span class="sxs-lookup"><span data-stu-id="694e7-172">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="694e7-173">Cada elemento es del tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="694e7-173">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|[<span data-ttu-id="694e7-174">\<emisor ></span><span class="sxs-lookup"><span data-stu-id="694e7-174">\<issuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md)|<span data-ttu-id="694e7-175">Especifica un punto de conexión que emite un token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="694e7-175">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="694e7-176">Este elemento es del tipo <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="694e7-176">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|[<span data-ttu-id="694e7-177">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="694e7-177">\<issuerMetadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md)|<span data-ttu-id="694e7-178">Especifica la dirección del punto de conexión del emisor.</span><span class="sxs-lookup"><span data-stu-id="694e7-178">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="694e7-179">\<tokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="694e7-179">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="694e7-180">Una colección de parámetros de solicitud de token.</span><span class="sxs-lookup"><span data-stu-id="694e7-180">A collection of token request parameters.</span></span> <span data-ttu-id="694e7-181">Cada parámetro es un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="694e7-181">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="694e7-182">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="694e7-182">Parent Elements</span></span>  
  
|<span data-ttu-id="694e7-183">Elemento</span><span class="sxs-lookup"><span data-stu-id="694e7-183">Element</span></span>|<span data-ttu-id="694e7-184">Descripción</span><span class="sxs-lookup"><span data-stu-id="694e7-184">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="694e7-185">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="694e7-185">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md)|<span data-ttu-id="694e7-186">Define la configuración de seguridad de un enlace.</span><span class="sxs-lookup"><span data-stu-id="694e7-186">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="694e7-187">Vea también</span><span class="sxs-lookup"><span data-stu-id="694e7-187">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>  
 <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>  
 <span data-ttu-id="694e7-188">`System.ServiceModel.Configuration.FederatedMessageSecurityElement` [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)</span><span class="sxs-lookup"><span data-stu-id="694e7-188">`System.ServiceModel.Configuration.FederatedMessageSecurityElement` [Securing Services and Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)</span></span>  
 [<span data-ttu-id="694e7-189">Enlaces</span><span class="sxs-lookup"><span data-stu-id="694e7-189">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="694e7-190">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="694e7-190">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="694e7-191">Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="694e7-191">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="694e7-192">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="694e7-192">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
