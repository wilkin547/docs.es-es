---
title: '&lt;issuerMetadata&gt;'
ms.date: 03/30/2017
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
ms.openlocfilehash: 22e30e0962ec8d2eb0f7e52f4db143fba9bbf703
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491563"
---
# <a name="ltissuermetadatagt"></a><span data-ttu-id="be76b-102">&lt;issuerMetadata&gt;</span><span class="sxs-lookup"><span data-stu-id="be76b-102">&lt;issuerMetadata&gt;</span></span>
<span data-ttu-id="be76b-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="be76b-103">\<system.serviceModel></span></span>  
<span data-ttu-id="be76b-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="be76b-104">\<bindings></span></span>  
<span data-ttu-id="be76b-105">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="be76b-105">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="be76b-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="be76b-106">\<binding></span></span>  
<span data-ttu-id="be76b-107">\<security></span><span class="sxs-lookup"><span data-stu-id="be76b-107">\<security></span></span>  
<span data-ttu-id="be76b-108">\<message></span><span class="sxs-lookup"><span data-stu-id="be76b-108">\<message></span></span>  
<span data-ttu-id="be76b-109">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="be76b-109">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be76b-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="be76b-110">Syntax</span></span>  
  
```xml  
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
                          x509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
    <dns value="String" />
    <rsa value="String" />
    <servicePrincipalName value="String" />
    <usePrincipalName value="String" />
  </identity>
</issuerMetadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="be76b-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="be76b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="be76b-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="be76b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="be76b-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="be76b-113">Attributes</span></span>  
  
|<span data-ttu-id="be76b-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="be76b-114">Attribute</span></span>|<span data-ttu-id="be76b-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="be76b-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="be76b-116">address</span><span class="sxs-lookup"><span data-stu-id="be76b-116">address</span></span>|<span data-ttu-id="be76b-117">El atributo `string` es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="be76b-117">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="be76b-118">Especifica la dirección del extremo.</span><span class="sxs-lookup"><span data-stu-id="be76b-118">Specifies the address of the endpoint.</span></span> <span data-ttu-id="be76b-119">La dirección debe ser un URI absoluto.</span><span class="sxs-lookup"><span data-stu-id="be76b-119">The address must be an absolute URI.</span></span> <span data-ttu-id="be76b-120">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="be76b-120">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="be76b-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="be76b-121">Child Elements</span></span>  
  
|<span data-ttu-id="be76b-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="be76b-122">Element</span></span>|<span data-ttu-id="be76b-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="be76b-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="be76b-124">\<headers></span><span class="sxs-lookup"><span data-stu-id="be76b-124">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="be76b-125">Una colección de encabezados de dirección.</span><span class="sxs-lookup"><span data-stu-id="be76b-125">A collection of address headers.</span></span>|  
|[<span data-ttu-id="be76b-126">\<identity></span><span class="sxs-lookup"><span data-stu-id="be76b-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="be76b-127">Una identidad que habilita la autenticación de un punto de conexión por otros puntos de conexión que intercambian mensajes con él.</span><span class="sxs-lookup"><span data-stu-id="be76b-127">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="be76b-128">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="be76b-128">Parent Elements</span></span>  
  
|<span data-ttu-id="be76b-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="be76b-129">Element</span></span>|<span data-ttu-id="be76b-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="be76b-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="be76b-131">\<message></span><span class="sxs-lookup"><span data-stu-id="be76b-131">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="be76b-132">Define la configuración de la seguridad de nivel de mensaje para el [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="be76b-132">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="be76b-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="be76b-133">See also</span></span>
- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>
- [<span data-ttu-id="be76b-134">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="be76b-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="be76b-135">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="be76b-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="be76b-136">Funcionalidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="be76b-136">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="be76b-137">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="be76b-137">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
