---
title: Elemento &lt;message&gt; de &lt;wsFederationHttpBinding&gt;
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d710389-d9d8-4454-9bf2-da4ccda31cec
caps.latest.revision: "28"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7b17a6325b84382d9d22b4da3ccf7e1598dc42df
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltmessagegt-element-of-ltwsfederationhttpbindinggt"></a><span data-ttu-id="5b1d8-102">Elemento &lt;message&gt; de &lt;wsFederationHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="5b1d8-102">&lt;message&gt; element of &lt;wsFederationHttpBinding&gt;</span></span>
<span data-ttu-id="5b1d8-103">Define la configuración de la seguridad de nivel de mensaje para la [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="5b1d8-103">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span></span>  
  
 <span data-ttu-id="5b1d8-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="5b1d8-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5b1d8-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="5b1d8-105">\<bindings></span></span>  
<span data-ttu-id="5b1d8-106">\<wsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="5b1d8-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="5b1d8-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="5b1d8-107">\<binding></span></span>  
<span data-ttu-id="5b1d8-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="5b1d8-108">\<security></span></span>  
<span data-ttu-id="5b1d8-109">\<mensaje ></span><span class="sxs-lookup"><span data-stu-id="5b1d8-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b1d8-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5b1d8-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5b1d8-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5b1d8-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5b1d8-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5b1d8-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="5b1d8-113">Attributes</span></span>  
  
|<span data-ttu-id="5b1d8-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="5b1d8-114">Attribute</span></span>|<span data-ttu-id="5b1d8-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="5b1d8-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5b1d8-116">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="5b1d8-116">algorithmSuite</span></span>|<span data-ttu-id="5b1d8-117">Establece el cifrado de mensajes y los algoritmos de encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-117">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="5b1d8-118">Vea la tabla de "atributo algorithmSuite" para ver los valores válidos de este atributo.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-118">See the "algorithmSuite attribute" table for valid values of this attribute.</span></span> <span data-ttu-id="5b1d8-119">El valor predeterminado es `Basic256`.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-119">The default value is `Basic256`.</span></span><br /><br /> <span data-ttu-id="5b1d8-120">Este atributo es del tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-120">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span> <span data-ttu-id="5b1d8-121">Estos algoritmos se asignan a los indicados en la especificación Lenguaje de directiva de seguridad (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="5b1d8-121">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span>|  
|<span data-ttu-id="5b1d8-122">issuedKeyType</span><span class="sxs-lookup"><span data-stu-id="5b1d8-122">issuedKeyType</span></span>|<span data-ttu-id="5b1d8-123">Especifica el tipo de clave que se va a emitir.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-123">Specifies the type of key to be issued.</span></span> <span data-ttu-id="5b1d8-124">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="5b1d8-124">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5b1d8-125">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="5b1d8-125">-   SymmetricKey</span></span><br /><span data-ttu-id="5b1d8-126">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="5b1d8-126">-   PublicKey</span></span><br /><br /> <span data-ttu-id="5b1d8-127">De manera predeterminada, es `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-127">The default is `SymmetricKey`.</span></span> <span data-ttu-id="5b1d8-128">Este atributo es del tipo <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-128">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|<span data-ttu-id="5b1d8-129">issuedTokenType</span><span class="sxs-lookup"><span data-stu-id="5b1d8-129">issuedTokenType</span></span>|<span data-ttu-id="5b1d8-130">Una cadena que contiene un URI que especifica el tipo de token que se va a emitir.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-130">A string that contains a URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="5b1d8-131">De manera predeterminada, es `null`.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-131">The default is `null`.</span></span>|  
|<span data-ttu-id="5b1d8-132">negotiateServiceCredential</span><span class="sxs-lookup"><span data-stu-id="5b1d8-132">negotiateServiceCredential</span></span>|<span data-ttu-id="5b1d8-133">Un valor booleano que especifica si la credencial del servicio se debería intercambiar como parte de negociación o estar disponible fuera de la banda.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-133">A Boolean value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="5b1d8-134">El valor predeterminado es `true`, que significa que se negocia la credencial del servicio.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-134">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="5b1d8-135">atributo algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="5b1d8-135">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="5b1d8-136">Valor</span><span class="sxs-lookup"><span data-stu-id="5b1d8-136">Value</span></span>|<span data-ttu-id="5b1d8-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="5b1d8-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5b1d8-138">Basic128</span><span class="sxs-lookup"><span data-stu-id="5b1d8-138">Basic128</span></span>|<span data-ttu-id="5b1d8-139">Utilice el cifrado Basic128, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-139">Use Basic128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5b1d8-140">Basic192</span><span class="sxs-lookup"><span data-stu-id="5b1d8-140">Basic192</span></span>|<span data-ttu-id="5b1d8-141">Utilice el cifrado Basic192, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-141">Use Basic192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5b1d8-142">Basic256</span><span class="sxs-lookup"><span data-stu-id="5b1d8-142">Basic256</span></span>|<span data-ttu-id="5b1d8-143">Utilice el cifrado Basic256, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-143">Use Basic256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5b1d8-144">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="5b1d8-144">Basic256Rsa15</span></span>|<span data-ttu-id="5b1d8-145">Utilice Basic256 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-145">Use Basic256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="5b1d8-146">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="5b1d8-146">Basic192Rsa15</span></span>|<span data-ttu-id="5b1d8-147">Utilice Basic192 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-147">Use Basic192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="5b1d8-148">TripleDes</span><span class="sxs-lookup"><span data-stu-id="5b1d8-148">TripleDes</span></span>|<span data-ttu-id="5b1d8-149">Utilice el cifrado TripleDes, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-149">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5b1d8-150">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="5b1d8-150">Basic128Rsa15</span></span>|<span data-ttu-id="5b1d8-151">Utilice Basic128 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-151">Use Basic128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="5b1d8-152">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="5b1d8-152">TripleDesRsa15</span></span>|<span data-ttu-id="5b1d8-153">Utilice el cifrado TripleDes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-153">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="5b1d8-154">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="5b1d8-154">Basic128Sha256</span></span>|<span data-ttu-id="5b1d8-155">Utilice Basic128 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-155">Use Basic128 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5b1d8-156">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="5b1d8-156">Basic192Sha256</span></span>|<span data-ttu-id="5b1d8-157">Utilice Basic192 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-157">Use Basic192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5b1d8-158">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="5b1d8-158">Basic256Sha256</span></span>|<span data-ttu-id="5b1d8-159">Utilice Basic256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-159">Use Basic256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5b1d8-160">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="5b1d8-160">TripleDesSha256</span></span>|<span data-ttu-id="5b1d8-161">Utilice TripleDes para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-161">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5b1d8-162">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="5b1d8-162">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="5b1d8-163">Utilice Basic128 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-163">Use Basic128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="5b1d8-164">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="5b1d8-164">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="5b1d8-165">Utilice Aes192 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-165">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="5b1d8-166">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="5b1d8-166">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="5b1d8-167">Utilice Basic256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-167">Use Basic256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="5b1d8-168">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="5b1d8-168">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="5b1d8-169">Utilice TripleDes para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-169">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5b1d8-170">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5b1d8-170">Child Elements</span></span>  
  
|<span data-ttu-id="5b1d8-171">Elemento</span><span class="sxs-lookup"><span data-stu-id="5b1d8-171">Element</span></span>|<span data-ttu-id="5b1d8-172">Descripción</span><span class="sxs-lookup"><span data-stu-id="5b1d8-172">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5b1d8-173">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="5b1d8-173">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="5b1d8-174">Especifica una colección de tipos de demanda para este enlace.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-174">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="5b1d8-175">Cada elemento es del tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-175">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|<span data-ttu-id="5b1d8-176">issuer</span><span class="sxs-lookup"><span data-stu-id="5b1d8-176">issuer</span></span>|<span data-ttu-id="5b1d8-177">Especifica un extremo que emite un token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-177">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="5b1d8-178">Este elemento es del tipo <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-178">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|<span data-ttu-id="5b1d8-179">issuerMetadata</span><span class="sxs-lookup"><span data-stu-id="5b1d8-179">issuerMetadata</span></span>|<span data-ttu-id="5b1d8-180">Especifica la dirección del punto de conexión del emisor.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-180">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="5b1d8-181">\<tokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="5b1d8-181">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="5b1d8-182">Una colección de parámetros de solicitud de token.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-182">A collection of token request parameters.</span></span> <span data-ttu-id="5b1d8-183">Cada parámetro es un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-183">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5b1d8-184">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5b1d8-184">Parent Elements</span></span>  
  
|<span data-ttu-id="5b1d8-185">Elemento</span><span class="sxs-lookup"><span data-stu-id="5b1d8-185">Element</span></span>|<span data-ttu-id="5b1d8-186">Descripción</span><span class="sxs-lookup"><span data-stu-id="5b1d8-186">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5b1d8-187">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="5b1d8-187">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md)|<span data-ttu-id="5b1d8-188">Define la configuración de seguridad de un enlace.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-188">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5b1d8-189">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b1d8-189">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>  
 <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>  
 <span data-ttu-id="5b1d8-190">`System.ServiceModel.Configuration.FederatedMessageSecurityElement`[Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)</span><span class="sxs-lookup"><span data-stu-id="5b1d8-190">`System.ServiceModel.Configuration.FederatedMessageSecurityElement` [Securing Services and Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)</span></span>  
 [<span data-ttu-id="5b1d8-191">Enlaces</span><span class="sxs-lookup"><span data-stu-id="5b1d8-191">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="5b1d8-192">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="5b1d8-192">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="5b1d8-193">Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="5b1d8-193">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="5b1d8-194">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="5b1d8-194">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
