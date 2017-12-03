---
title: '&lt;emisor&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 235888aa97238489a51c2ea065efa0575e0d3724
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltissuergt"></a><span data-ttu-id="87443-102">&lt;emisor&gt;</span><span class="sxs-lookup"><span data-stu-id="87443-102">&lt;issuer&gt;</span></span>
<span data-ttu-id="87443-103">Especifica el servicio de token de seguridad (STS) que emite los tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="87443-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="87443-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="87443-104">\<system.serviceModel></span></span>  
<span data-ttu-id="87443-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="87443-105">\<bindings></span></span>  
<span data-ttu-id="87443-106">\<wsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="87443-106">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="87443-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="87443-107">\<binding></span></span>  
<span data-ttu-id="87443-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="87443-108">\<security></span></span>  
<span data-ttu-id="87443-109">\<mensaje ></span><span class="sxs-lookup"><span data-stu-id="87443-109">\<message></span></span>  
<span data-ttu-id="87443-110">\<emisor ></span><span class="sxs-lookup"><span data-stu-id="87443-110">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87443-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="87443-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="87443-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="87443-112">Attributes and Elements</span></span>  
 <span data-ttu-id="87443-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="87443-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="87443-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="87443-114">Attributes</span></span>  
  
|<span data-ttu-id="87443-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="87443-115">Attribute</span></span>|<span data-ttu-id="87443-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="87443-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="87443-117">address</span><span class="sxs-lookup"><span data-stu-id="87443-117">address</span></span>|<span data-ttu-id="87443-118">Cadena necesaria.</span><span class="sxs-lookup"><span data-stu-id="87443-118">Required string.</span></span> <span data-ttu-id="87443-119">La dirección URL del STS.</span><span class="sxs-lookup"><span data-stu-id="87443-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="87443-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="87443-120">Child Elements</span></span>  
  
|<span data-ttu-id="87443-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="87443-121">Element</span></span>|<span data-ttu-id="87443-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="87443-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="87443-123">\<encabezados ></span><span class="sxs-lookup"><span data-stu-id="87443-123">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="87443-124">Una colección de encabezados de dirección para los puntos de conexión que el generador puede crear.</span><span class="sxs-lookup"><span data-stu-id="87443-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="87443-125">\<identidad ></span><span class="sxs-lookup"><span data-stu-id="87443-125">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="87443-126">Al utilizar un token emitido, especifica valores que permiten al cliente autenticar el servidor.</span><span class="sxs-lookup"><span data-stu-id="87443-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="87443-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="87443-127">Parent Elements</span></span>  
  
|<span data-ttu-id="87443-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="87443-128">Element</span></span>|<span data-ttu-id="87443-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="87443-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="87443-130">\<mensaje ></span><span class="sxs-lookup"><span data-stu-id="87443-130">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="87443-131">Define la configuración de la seguridad de nivel de mensaje para la [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="87443-131">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="87443-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="87443-132">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>  
 [<span data-ttu-id="87443-133">Autenticación e identidad de servicio</span><span class="sxs-lookup"><span data-stu-id="87443-133">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="87443-134">Federación y Tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="87443-134">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="87443-135">Autenticación e identidad de servicio</span><span class="sxs-lookup"><span data-stu-id="87443-135">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="87443-136">Federación y Tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="87443-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="87443-137">Capacidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="87443-137">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="87443-138">Federación y Tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="87443-138">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
