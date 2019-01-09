---
title: '&lt;issuerMetadata&gt;'
ms.date: 03/30/2017
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
ms.openlocfilehash: 38fa373212464a7dc919c2f364524a391db17d43
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149363"
---
# <a name="ltissuermetadatagt"></a><span data-ttu-id="70d23-102">&lt;issuerMetadata&gt;</span><span class="sxs-lookup"><span data-stu-id="70d23-102">&lt;issuerMetadata&gt;</span></span>
<span data-ttu-id="70d23-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="70d23-103">\<system.serviceModel></span></span>  
<span data-ttu-id="70d23-104">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="70d23-104">\<bindings></span></span>  
<span data-ttu-id="70d23-105">\<wsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="70d23-105">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="70d23-106">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="70d23-106">\<binding></span></span>  
<span data-ttu-id="70d23-107">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="70d23-107">\<security></span></span>  
<span data-ttu-id="70d23-108">\<mensaje ></span><span class="sxs-lookup"><span data-stu-id="70d23-108">\<message></span></span>  
<span data-ttu-id="70d23-109">\<issuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="70d23-109">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70d23-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="70d23-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="70d23-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="70d23-111">Attributes and Elements</span></span>  
 <span data-ttu-id="70d23-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="70d23-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="70d23-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="70d23-113">Attributes</span></span>  
  
|<span data-ttu-id="70d23-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="70d23-114">Attribute</span></span>|<span data-ttu-id="70d23-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="70d23-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="70d23-116">address</span><span class="sxs-lookup"><span data-stu-id="70d23-116">address</span></span>|<span data-ttu-id="70d23-117">El atributo `string` es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="70d23-117">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="70d23-118">Especifica la dirección del extremo.</span><span class="sxs-lookup"><span data-stu-id="70d23-118">Specifies the address of the endpoint.</span></span> <span data-ttu-id="70d23-119">La dirección debe ser un URI absoluto.</span><span class="sxs-lookup"><span data-stu-id="70d23-119">The address must be an absolute URI.</span></span> <span data-ttu-id="70d23-120">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="70d23-120">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="70d23-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="70d23-121">Child Elements</span></span>  
  
|<span data-ttu-id="70d23-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="70d23-122">Element</span></span>|<span data-ttu-id="70d23-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="70d23-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="70d23-124">\<encabezados ></span><span class="sxs-lookup"><span data-stu-id="70d23-124">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="70d23-125">Una colección de encabezados de dirección.</span><span class="sxs-lookup"><span data-stu-id="70d23-125">A collection of address headers.</span></span>|  
|[<span data-ttu-id="70d23-126">\<identidad ></span><span class="sxs-lookup"><span data-stu-id="70d23-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="70d23-127">Una identidad que habilita la autenticación de un punto de conexión por otros puntos de conexión que intercambian mensajes con él.</span><span class="sxs-lookup"><span data-stu-id="70d23-127">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="70d23-128">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="70d23-128">Parent Elements</span></span>  
  
|<span data-ttu-id="70d23-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="70d23-129">Element</span></span>|<span data-ttu-id="70d23-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="70d23-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="70d23-131">\<mensaje ></span><span class="sxs-lookup"><span data-stu-id="70d23-131">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="70d23-132">Define la configuración de la seguridad de nivel de mensaje para el [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="70d23-132">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="70d23-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="70d23-133">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>  
 [<span data-ttu-id="70d23-134">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="70d23-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="70d23-135">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="70d23-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="70d23-136">Funcionalidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="70d23-136">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="70d23-137">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="70d23-137">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
