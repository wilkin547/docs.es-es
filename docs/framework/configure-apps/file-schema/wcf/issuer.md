---
title: '&lt;Emisor&gt;'
ms.date: 03/30/2017
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
ms.openlocfilehash: 638b206f5372a654eca68d2f6ebb69bb0ac9e241
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltissuergt"></a><span data-ttu-id="06590-102">&lt;Emisor&gt;</span><span class="sxs-lookup"><span data-stu-id="06590-102">&lt;issuer&gt;</span></span>
<span data-ttu-id="06590-103">Especifica el servicio de token de seguridad (STS) que emite los tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="06590-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="06590-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="06590-104">\<system.serviceModel></span></span>  
<span data-ttu-id="06590-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="06590-105">\<bindings></span></span>  
<span data-ttu-id="06590-106">\<wsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="06590-106">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="06590-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="06590-107">\<binding></span></span>  
<span data-ttu-id="06590-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="06590-108">\<security></span></span>  
<span data-ttu-id="06590-109">\<mensaje ></span><span class="sxs-lookup"><span data-stu-id="06590-109">\<message></span></span>  
<span data-ttu-id="06590-110">\<emisor ></span><span class="sxs-lookup"><span data-stu-id="06590-110">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06590-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="06590-111">Syntax</span></span>  
  
```xml  
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
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="06590-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="06590-112">Attributes and Elements</span></span>  
 <span data-ttu-id="06590-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="06590-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="06590-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="06590-114">Attributes</span></span>  
  
|<span data-ttu-id="06590-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="06590-115">Attribute</span></span>|<span data-ttu-id="06590-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="06590-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="06590-117">address</span><span class="sxs-lookup"><span data-stu-id="06590-117">address</span></span>|<span data-ttu-id="06590-118">Cadena necesaria.</span><span class="sxs-lookup"><span data-stu-id="06590-118">Required string.</span></span> <span data-ttu-id="06590-119">La dirección URL del STS.</span><span class="sxs-lookup"><span data-stu-id="06590-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="06590-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="06590-120">Child Elements</span></span>  
  
|<span data-ttu-id="06590-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="06590-121">Element</span></span>|<span data-ttu-id="06590-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="06590-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="06590-123">\<encabezados ></span><span class="sxs-lookup"><span data-stu-id="06590-123">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="06590-124">Una colección de encabezados de dirección para los puntos de conexión que el generador puede crear.</span><span class="sxs-lookup"><span data-stu-id="06590-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="06590-125">\<identidad ></span><span class="sxs-lookup"><span data-stu-id="06590-125">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="06590-126">Al utilizar un token emitido, especifica valores que permiten al cliente autenticar el servidor.</span><span class="sxs-lookup"><span data-stu-id="06590-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="06590-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="06590-127">Parent Elements</span></span>  
  
|<span data-ttu-id="06590-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="06590-128">Element</span></span>|<span data-ttu-id="06590-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="06590-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="06590-130">\<mensaje ></span><span class="sxs-lookup"><span data-stu-id="06590-130">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="06590-131">Define la configuración de la seguridad de nivel de mensaje para la [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="06590-131">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="06590-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="06590-132">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>  
 [<span data-ttu-id="06590-133">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="06590-133">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="06590-134">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="06590-134">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="06590-135">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="06590-135">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="06590-136">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="06590-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="06590-137">Funcionalidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="06590-137">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="06590-138">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="06590-138">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
