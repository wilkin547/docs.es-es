---
title: '&lt;emisor&gt;'
ms.date: 03/30/2017
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
ms.openlocfilehash: d2728bf3613b41ed9f0810207d27d6d67477afd2
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149558"
---
# <a name="ltissuergt"></a><span data-ttu-id="c4162-102">&lt;emisor&gt;</span><span class="sxs-lookup"><span data-stu-id="c4162-102">&lt;issuer&gt;</span></span>
<span data-ttu-id="c4162-103">Especifica el servicio de token de seguridad (STS) que emite los tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c4162-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="c4162-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c4162-104">\<system.serviceModel></span></span>  
<span data-ttu-id="c4162-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="c4162-105">\<bindings></span></span>  
<span data-ttu-id="c4162-106">\<wsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="c4162-106">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="c4162-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="c4162-107">\<binding></span></span>  
<span data-ttu-id="c4162-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="c4162-108">\<security></span></span>  
<span data-ttu-id="c4162-109">\<mensaje ></span><span class="sxs-lookup"><span data-stu-id="c4162-109">\<message></span></span>  
<span data-ttu-id="c4162-110">\<emisor ></span><span class="sxs-lookup"><span data-stu-id="c4162-110">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4162-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c4162-111">Syntax</span></span>  
  
```xml  
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
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c4162-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c4162-112">Attributes and Elements</span></span>  
 <span data-ttu-id="c4162-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c4162-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c4162-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="c4162-114">Attributes</span></span>  
  
|<span data-ttu-id="c4162-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="c4162-115">Attribute</span></span>|<span data-ttu-id="c4162-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="c4162-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c4162-117">address</span><span class="sxs-lookup"><span data-stu-id="c4162-117">address</span></span>|<span data-ttu-id="c4162-118">Cadena necesaria.</span><span class="sxs-lookup"><span data-stu-id="c4162-118">Required string.</span></span> <span data-ttu-id="c4162-119">La dirección URL del STS.</span><span class="sxs-lookup"><span data-stu-id="c4162-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c4162-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c4162-120">Child Elements</span></span>  
  
|<span data-ttu-id="c4162-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="c4162-121">Element</span></span>|<span data-ttu-id="c4162-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="c4162-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c4162-123">\<encabezados ></span><span class="sxs-lookup"><span data-stu-id="c4162-123">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="c4162-124">Una colección de encabezados de dirección para los puntos de conexión que el generador puede crear.</span><span class="sxs-lookup"><span data-stu-id="c4162-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="c4162-125">\<identidad ></span><span class="sxs-lookup"><span data-stu-id="c4162-125">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="c4162-126">Al utilizar un token emitido, especifica valores que permiten al cliente autenticar el servidor.</span><span class="sxs-lookup"><span data-stu-id="c4162-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c4162-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c4162-127">Parent Elements</span></span>  
  
|<span data-ttu-id="c4162-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="c4162-128">Element</span></span>|<span data-ttu-id="c4162-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="c4162-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c4162-130">\<mensaje ></span><span class="sxs-lookup"><span data-stu-id="c4162-130">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="c4162-131">Define la configuración de la seguridad de nivel de mensaje para el [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="c4162-131">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c4162-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4162-132">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>  
 [<span data-ttu-id="c4162-133">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="c4162-133">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="c4162-134">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="c4162-134">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="c4162-135">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="c4162-135">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="c4162-136">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="c4162-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="c4162-137">Funcionalidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="c4162-137">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="c4162-138">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="c4162-138">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
