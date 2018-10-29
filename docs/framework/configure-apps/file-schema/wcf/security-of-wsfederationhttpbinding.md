---
title: Elemento &lt;security&gt; de &lt;wsFederationHttpBinding&gt;
ms.date: 03/30/2017
ms.assetid: a8e5e854-b8dc-4921-843d-34b6a4a6a8ba
ms.openlocfilehash: 9473fa062867383f84ba5931c394f1ac665a74fb
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2018
ms.locfileid: "50199297"
---
# <a name="ltsecuritygt-of-ltwsfederationhttpbindinggt"></a><span data-ttu-id="75470-102">Elemento &lt;security&gt; de &lt;wsFederationHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="75470-102">&lt;security&gt; of &lt;wsFederationHttpBinding&gt;</span></span>
<span data-ttu-id="75470-103">Define la configuración de seguridad de la [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="75470-103">Defines the security settings of the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span></span>  
  
 <span data-ttu-id="75470-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="75470-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="75470-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="75470-105">\<bindings></span></span>  
<span data-ttu-id="75470-106">\<wsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="75470-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="75470-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="75470-107">\<binding></span></span>  
<span data-ttu-id="75470-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="75470-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75470-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="75470-109">Syntax</span></span>  
  
```xml  
<wsFederationBinding>  
    <binding >  
       <security mode="None/Message/TransportWithMessageCredential">  
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
                                   X509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="75470-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="75470-110">Attributes and Elements</span></span>  
 <span data-ttu-id="75470-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="75470-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="75470-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="75470-112">Attributes</span></span>  
  
|<span data-ttu-id="75470-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="75470-113">Attribute</span></span>|<span data-ttu-id="75470-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="75470-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="75470-115">Modo</span><span class="sxs-lookup"><span data-stu-id="75470-115">Mode</span></span>|<span data-ttu-id="75470-116">Opcional.</span><span class="sxs-lookup"><span data-stu-id="75470-116">Optional.</span></span> <span data-ttu-id="75470-117">Especifica el tipo de seguridad que se aplica.</span><span class="sxs-lookup"><span data-stu-id="75470-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="75470-118">El valor predeterminado es `Message`.</span><span class="sxs-lookup"><span data-stu-id="75470-118">The default value is `Message`.</span></span> <span data-ttu-id="75470-119">Este atributo es del tipo <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="75470-119">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="75470-120">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="75470-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="75470-121">Valor</span><span class="sxs-lookup"><span data-stu-id="75470-121">Value</span></span>|<span data-ttu-id="75470-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="75470-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="75470-123">Ninguna</span><span class="sxs-lookup"><span data-stu-id="75470-123">None</span></span>|<span data-ttu-id="75470-124">El mensaje SOAP no es seguro durante la transferencia.</span><span class="sxs-lookup"><span data-stu-id="75470-124">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="75470-125">Mensaje</span><span class="sxs-lookup"><span data-stu-id="75470-125">Message</span></span>|<span data-ttu-id="75470-126">La integridad, confidencialidad, autenticación de servidor y autenticación del cliente se proporciona mediante la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="75470-126">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="75470-127">De forma predeterminada, el cuerpo se cifra y firma.</span><span class="sxs-lookup"><span data-stu-id="75470-127">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="75470-128">El servicio necesita ser configurado con un certificado.</span><span class="sxs-lookup"><span data-stu-id="75470-128">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="75470-129">La autenticación del cliente está basada en el token emitido al cliente por un servicio de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="75470-129">Client authentication is based on the token issued to the client by a security token service</span></span>|  
|<span data-ttu-id="75470-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="75470-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="75470-131">HTTPS proporciona integridad, confidencialidad y autenticación del servidor.</span><span class="sxs-lookup"><span data-stu-id="75470-131">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="75470-132">El servicio necesita ser configurado con un certificado.</span><span class="sxs-lookup"><span data-stu-id="75470-132">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="75470-133">La autenticación del cliente se proporciona por medio de la seguridad del mensaje SOAP y está basada en el token emitido al cliente por un servicio de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="75470-133">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="75470-134">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="75470-134">Child Elements</span></span>  
  
|<span data-ttu-id="75470-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="75470-135">Element</span></span>|<span data-ttu-id="75470-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="75470-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="75470-137">\<mensaje ></span><span class="sxs-lookup"><span data-stu-id="75470-137">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="75470-138">Define la configuración de seguridad del nivel del mensaje.</span><span class="sxs-lookup"><span data-stu-id="75470-138">Defines the settings for the message-level security.</span></span> <span data-ttu-id="75470-139">Este elemento es del tipo <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="75470-139">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="75470-140">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="75470-140">Parent Elements</span></span>  
  
|<span data-ttu-id="75470-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="75470-141">Element</span></span>|<span data-ttu-id="75470-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="75470-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="75470-143">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="75470-143">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="75470-144">Define todas las capacidades de enlace de la [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="75470-144">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="75470-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="75470-145">See Also</span></span>  
 <xref:System.ServiceModel.WSFederationHttpSecurity>  
 <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>  
 [<span data-ttu-id="75470-146">Creación de un WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="75470-146">How to: Create a WSFederationHttpBinding</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)  
 [<span data-ttu-id="75470-147">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="75470-147">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="75470-148">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="75470-148">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="75470-149">Enlaces</span><span class="sxs-lookup"><span data-stu-id="75470-149">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="75470-150">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="75470-150">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="75470-151">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="75470-151">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="75470-152">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="75470-152">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
