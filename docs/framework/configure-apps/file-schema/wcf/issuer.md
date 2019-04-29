---
title: <issuer>
ms.date: 03/30/2017
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
ms.openlocfilehash: 37d935287fa7dfba640c39071295fd660f4db7c1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756265"
---
# <a name="issuer"></a><span data-ttu-id="aed9b-101">\<issuer></span><span class="sxs-lookup"><span data-stu-id="aed9b-101">\<issuer></span></span>
<span data-ttu-id="aed9b-102">Especifica el servicio de token de seguridad (STS) que emite los tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="aed9b-102">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="aed9b-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="aed9b-103">\<system.serviceModel></span></span>  
<span data-ttu-id="aed9b-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="aed9b-104">\<bindings></span></span>  
<span data-ttu-id="aed9b-105">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="aed9b-105">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="aed9b-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="aed9b-106">\<binding></span></span>  
<span data-ttu-id="aed9b-107">\<security></span><span class="sxs-lookup"><span data-stu-id="aed9b-107">\<security></span></span>  
<span data-ttu-id="aed9b-108">\<message></span><span class="sxs-lookup"><span data-stu-id="aed9b-108">\<message></span></span>  
<span data-ttu-id="aed9b-109">\<issuer></span><span class="sxs-lookup"><span data-stu-id="aed9b-109">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aed9b-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aed9b-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aed9b-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="aed9b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="aed9b-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="aed9b-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aed9b-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="aed9b-113">Attributes</span></span>  
  
|<span data-ttu-id="aed9b-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="aed9b-114">Attribute</span></span>|<span data-ttu-id="aed9b-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="aed9b-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aed9b-116">dirección</span><span class="sxs-lookup"><span data-stu-id="aed9b-116">address</span></span>|<span data-ttu-id="aed9b-117">Cadena necesaria.</span><span class="sxs-lookup"><span data-stu-id="aed9b-117">Required string.</span></span> <span data-ttu-id="aed9b-118">La dirección URL del STS.</span><span class="sxs-lookup"><span data-stu-id="aed9b-118">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aed9b-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="aed9b-119">Child Elements</span></span>  
  
|<span data-ttu-id="aed9b-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="aed9b-120">Element</span></span>|<span data-ttu-id="aed9b-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="aed9b-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aed9b-122">\<headers></span><span class="sxs-lookup"><span data-stu-id="aed9b-122">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="aed9b-123">Una colección de encabezados de dirección para los puntos de conexión que el generador puede crear.</span><span class="sxs-lookup"><span data-stu-id="aed9b-123">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="aed9b-124">\<identity></span><span class="sxs-lookup"><span data-stu-id="aed9b-124">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="aed9b-125">Al utilizar un token emitido, especifica valores que permiten al cliente autenticar el servidor.</span><span class="sxs-lookup"><span data-stu-id="aed9b-125">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aed9b-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="aed9b-126">Parent Elements</span></span>  
  
|<span data-ttu-id="aed9b-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="aed9b-127">Element</span></span>|<span data-ttu-id="aed9b-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="aed9b-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aed9b-129">\<message></span><span class="sxs-lookup"><span data-stu-id="aed9b-129">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="aed9b-130">Define la configuración de la seguridad de nivel de mensaje para el [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="aed9b-130">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aed9b-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="aed9b-131">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- [<span data-ttu-id="aed9b-132">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="aed9b-132">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="aed9b-133">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="aed9b-133">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="aed9b-134">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="aed9b-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="aed9b-135">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="aed9b-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="aed9b-136">Funcionalidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="aed9b-136">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="aed9b-137">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="aed9b-137">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
