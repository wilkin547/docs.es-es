---
title: <issuerMetadata>
ms.date: 03/30/2017
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
ms.openlocfilehash: bf512c427637ca65a7271ec8300a373a38632108
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913515"
---
# <a name="issuermetadata"></a><span data-ttu-id="65a6d-101">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="65a6d-101">\<issuerMetadata></span></span>
<span data-ttu-id="65a6d-102">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="65a6d-102">\<system.serviceModel></span></span>  
<span data-ttu-id="65a6d-103">\<bindings></span><span class="sxs-lookup"><span data-stu-id="65a6d-103">\<bindings></span></span>  
<span data-ttu-id="65a6d-104">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="65a6d-104">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="65a6d-105">\<binding></span><span class="sxs-lookup"><span data-stu-id="65a6d-105">\<binding></span></span>  
<span data-ttu-id="65a6d-106">\<> de seguridad</span><span class="sxs-lookup"><span data-stu-id="65a6d-106">\<security></span></span>  
<span data-ttu-id="65a6d-107">\<message></span><span class="sxs-lookup"><span data-stu-id="65a6d-107">\<message></span></span>  
<span data-ttu-id="65a6d-108">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="65a6d-108">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65a6d-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="65a6d-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="65a6d-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="65a6d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="65a6d-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="65a6d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="65a6d-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="65a6d-112">Attributes</span></span>  
  
|<span data-ttu-id="65a6d-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="65a6d-113">Attribute</span></span>|<span data-ttu-id="65a6d-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="65a6d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="65a6d-115">dirección</span><span class="sxs-lookup"><span data-stu-id="65a6d-115">address</span></span>|<span data-ttu-id="65a6d-116">El atributo `string` es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="65a6d-116">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="65a6d-117">Especifica la dirección del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="65a6d-117">Specifies the address of the endpoint.</span></span> <span data-ttu-id="65a6d-118">La dirección debe ser un URI absoluto.</span><span class="sxs-lookup"><span data-stu-id="65a6d-118">The address must be an absolute URI.</span></span> <span data-ttu-id="65a6d-119">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="65a6d-119">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="65a6d-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="65a6d-120">Child Elements</span></span>  
  
|<span data-ttu-id="65a6d-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="65a6d-121">Element</span></span>|<span data-ttu-id="65a6d-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="65a6d-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="65a6d-123">\<headers></span><span class="sxs-lookup"><span data-stu-id="65a6d-123">\<headers></span></span>](headers-element.md)|<span data-ttu-id="65a6d-124">Una colección de encabezados de dirección.</span><span class="sxs-lookup"><span data-stu-id="65a6d-124">A collection of address headers.</span></span>|  
|[<span data-ttu-id="65a6d-125">\<identity></span><span class="sxs-lookup"><span data-stu-id="65a6d-125">\<identity></span></span>](identity.md)|<span data-ttu-id="65a6d-126">Una identidad que habilita la autenticación de un punto de conexión por otros puntos de conexión que intercambian mensajes con él.</span><span class="sxs-lookup"><span data-stu-id="65a6d-126">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="65a6d-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="65a6d-127">Parent Elements</span></span>  
  
|<span data-ttu-id="65a6d-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="65a6d-128">Element</span></span>|<span data-ttu-id="65a6d-129">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="65a6d-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="65a6d-130">\<message></span><span class="sxs-lookup"><span data-stu-id="65a6d-130">\<message></span></span>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="65a6d-131">Define la configuración para la seguridad del nivel de mensaje para [ \<](wsfederationhttpbinding.md) el elemento > de wsFederationHttpBinding.</span><span class="sxs-lookup"><span data-stu-id="65a6d-131">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="65a6d-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="65a6d-132">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>
- [<span data-ttu-id="65a6d-133">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="65a6d-133">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="65a6d-134">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="65a6d-134">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="65a6d-135">Funcionalidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="65a6d-135">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="65a6d-136">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="65a6d-136">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
