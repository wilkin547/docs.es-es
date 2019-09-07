---
title: <issuerMetadata>
ms.date: 03/30/2017
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
ms.openlocfilehash: a28223127f7987a80bdf12d2dcf42878f717a377
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397893"
---
# <a name="issuermetadata"></a><span data-ttu-id="0f9b7-101">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="0f9b7-101">\<issuerMetadata></span></span>

<span data-ttu-id="0f9b7-102">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0f9b7-102">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0f9b7-103">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="0f9b7-103">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="0f9b7-104">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enlaces**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="0f9b7-104">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="0f9b7-105">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> wsFederationHttpBinding**](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="0f9b7-105">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="0f9b7-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de enlace**</span><span class="sxs-lookup"><span data-stu-id="0f9b7-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="0f9b7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguridad**](security-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="0f9b7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="0f9b7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de mensajes**](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="0f9b7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="0f9b7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> issuerMetadata**</span><span class="sxs-lookup"><span data-stu-id="0f9b7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerMetadata>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f9b7-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0f9b7-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0f9b7-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0f9b7-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0f9b7-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0f9b7-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="0f9b7-113">Attributes</span></span>  
  
|<span data-ttu-id="0f9b7-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="0f9b7-114">Attribute</span></span>|<span data-ttu-id="0f9b7-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0f9b7-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0f9b7-116">dirección</span><span class="sxs-lookup"><span data-stu-id="0f9b7-116">address</span></span>|<span data-ttu-id="0f9b7-117">El atributo `string` es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-117">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="0f9b7-118">Especifica la dirección del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-118">Specifies the address of the endpoint.</span></span> <span data-ttu-id="0f9b7-119">La dirección debe ser un URI absoluto.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-119">The address must be an absolute URI.</span></span> <span data-ttu-id="0f9b7-120">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-120">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0f9b7-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0f9b7-121">Child Elements</span></span>  
  
|<span data-ttu-id="0f9b7-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="0f9b7-122">Element</span></span>|<span data-ttu-id="0f9b7-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0f9b7-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0f9b7-124">\<headers></span><span class="sxs-lookup"><span data-stu-id="0f9b7-124">\<headers></span></span>](headers-element.md)|<span data-ttu-id="0f9b7-125">Una colección de encabezados de dirección.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-125">A collection of address headers.</span></span>|  
|[<span data-ttu-id="0f9b7-126">\<identity></span><span class="sxs-lookup"><span data-stu-id="0f9b7-126">\<identity></span></span>](identity.md)|<span data-ttu-id="0f9b7-127">Una identidad que habilita la autenticación de un punto de conexión por otros puntos de conexión que intercambian mensajes con él.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-127">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0f9b7-128">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0f9b7-128">Parent Elements</span></span>  
  
|<span data-ttu-id="0f9b7-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="0f9b7-129">Element</span></span>|<span data-ttu-id="0f9b7-130">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0f9b7-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0f9b7-131">\<message></span><span class="sxs-lookup"><span data-stu-id="0f9b7-131">\<message></span></span>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="0f9b7-132">Define la configuración para la seguridad del nivel de mensaje para [ \<](wsfederationhttpbinding.md) el elemento > de wsFederationHttpBinding.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-132">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0f9b7-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f9b7-133">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>
- [<span data-ttu-id="0f9b7-134">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="0f9b7-134">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="0f9b7-135">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="0f9b7-135">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="0f9b7-136">Funcionalidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="0f9b7-136">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="0f9b7-137">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="0f9b7-137">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
