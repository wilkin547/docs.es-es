---
title: <issuer>
ms.date: 03/30/2017
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
ms.openlocfilehash: 37d935287fa7dfba640c39071295fd660f4db7c1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160828"
---
# <a name="issuer"></a><span data-ttu-id="38124-101">\<issuer></span><span class="sxs-lookup"><span data-stu-id="38124-101">\<issuer></span></span>
<span data-ttu-id="38124-102">Especifica el servicio de token de seguridad (STS) que emite los tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="38124-102">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="38124-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="38124-103">\<system.serviceModel></span></span>  
<span data-ttu-id="38124-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="38124-104">\<bindings></span></span>  
<span data-ttu-id="38124-105">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="38124-105">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="38124-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="38124-106">\<binding></span></span>  
<span data-ttu-id="38124-107">\<security></span><span class="sxs-lookup"><span data-stu-id="38124-107">\<security></span></span>  
<span data-ttu-id="38124-108">\<message></span><span class="sxs-lookup"><span data-stu-id="38124-108">\<message></span></span>  
<span data-ttu-id="38124-109">\<issuer></span><span class="sxs-lookup"><span data-stu-id="38124-109">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38124-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="38124-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="38124-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="38124-111">Attributes and Elements</span></span>  
 <span data-ttu-id="38124-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="38124-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="38124-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="38124-113">Attributes</span></span>  
  
|<span data-ttu-id="38124-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="38124-114">Attribute</span></span>|<span data-ttu-id="38124-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="38124-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="38124-116">dirección</span><span class="sxs-lookup"><span data-stu-id="38124-116">address</span></span>|<span data-ttu-id="38124-117">Cadena necesaria.</span><span class="sxs-lookup"><span data-stu-id="38124-117">Required string.</span></span> <span data-ttu-id="38124-118">La dirección URL del STS.</span><span class="sxs-lookup"><span data-stu-id="38124-118">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="38124-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="38124-119">Child Elements</span></span>  
  
|<span data-ttu-id="38124-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="38124-120">Element</span></span>|<span data-ttu-id="38124-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="38124-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="38124-122">\<headers></span><span class="sxs-lookup"><span data-stu-id="38124-122">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="38124-123">Una colección de encabezados de dirección para los puntos de conexión que el generador puede crear.</span><span class="sxs-lookup"><span data-stu-id="38124-123">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="38124-124">\<identity></span><span class="sxs-lookup"><span data-stu-id="38124-124">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="38124-125">Al utilizar un token emitido, especifica valores que permiten al cliente autenticar el servidor.</span><span class="sxs-lookup"><span data-stu-id="38124-125">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="38124-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="38124-126">Parent Elements</span></span>  
  
|<span data-ttu-id="38124-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="38124-127">Element</span></span>|<span data-ttu-id="38124-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="38124-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="38124-129">\<message></span><span class="sxs-lookup"><span data-stu-id="38124-129">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="38124-130">Define la configuración de la seguridad de nivel de mensaje para el [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="38124-130">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="38124-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="38124-131">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- [<span data-ttu-id="38124-132">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="38124-132">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="38124-133">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="38124-133">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="38124-134">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="38124-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="38124-135">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="38124-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="38124-136">Capacidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="38124-136">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="38124-137">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="38124-137">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
