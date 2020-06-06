---
title: <issuerMetadata>
ms.date: 03/30/2017
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
ms.openlocfilehash: a28223127f7987a80bdf12d2dcf42878f717a377
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397893"
---
# \<issuerMetadata>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerMetadata>**  
  
## <a name="syntax"></a><span data-ttu-id="a47c2-101">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a47c2-101">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a47c2-102">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a47c2-102">Attributes and Elements</span></span>  
 <span data-ttu-id="a47c2-103">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a47c2-103">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a47c2-104">Atributos</span><span class="sxs-lookup"><span data-stu-id="a47c2-104">Attributes</span></span>  
  
|<span data-ttu-id="a47c2-105">Atributo</span><span class="sxs-lookup"><span data-stu-id="a47c2-105">Attribute</span></span>|<span data-ttu-id="a47c2-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a47c2-106">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a47c2-107">address</span><span class="sxs-lookup"><span data-stu-id="a47c2-107">address</span></span>|<span data-ttu-id="a47c2-108">El atributo `string` es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="a47c2-108">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="a47c2-109">Especifica la dirección del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="a47c2-109">Specifies the address of the endpoint.</span></span> <span data-ttu-id="a47c2-110">La dirección debe ser un URI absoluto.</span><span class="sxs-lookup"><span data-stu-id="a47c2-110">The address must be an absolute URI.</span></span> <span data-ttu-id="a47c2-111">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="a47c2-111">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a47c2-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a47c2-112">Child Elements</span></span>  
  
|<span data-ttu-id="a47c2-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="a47c2-113">Element</span></span>|<span data-ttu-id="a47c2-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="a47c2-114">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|<span data-ttu-id="a47c2-115">Una colección de encabezados de dirección.</span><span class="sxs-lookup"><span data-stu-id="a47c2-115">A collection of address headers.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="a47c2-116">Una identidad que habilita la autenticación de un punto de conexión por otros puntos de conexión que intercambian mensajes con él.</span><span class="sxs-lookup"><span data-stu-id="a47c2-116">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a47c2-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a47c2-117">Parent Elements</span></span>  
  
|<span data-ttu-id="a47c2-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="a47c2-118">Element</span></span>|<span data-ttu-id="a47c2-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="a47c2-119">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="a47c2-120">Define la configuración para la seguridad del nivel de mensaje para el [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="a47c2-120">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a47c2-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a47c2-121">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>
- [<span data-ttu-id="a47c2-122">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="a47c2-122">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="a47c2-123">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="a47c2-123">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="a47c2-124">Capacidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="a47c2-124">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="a47c2-125">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="a47c2-125">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
