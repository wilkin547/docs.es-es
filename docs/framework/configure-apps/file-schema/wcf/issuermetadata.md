---
description: 'Más información acerca de: <issuerMetadata>'
title: <issuerMetadata>
ms.date: 03/30/2017
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
ms.openlocfilehash: 86671b6b704f5753cf4bd45c2dfd90a368070b22
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725537"
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
  
## <a name="syntax"></a><span data-ttu-id="35681-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="35681-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="35681-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="35681-103">Attributes and Elements</span></span>  

 <span data-ttu-id="35681-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="35681-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="35681-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="35681-105">Attributes</span></span>  
  
|<span data-ttu-id="35681-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="35681-106">Attribute</span></span>|<span data-ttu-id="35681-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="35681-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="35681-108">address</span><span class="sxs-lookup"><span data-stu-id="35681-108">address</span></span>|<span data-ttu-id="35681-109">El atributo `string` es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="35681-109">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="35681-110">Especifica la dirección del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="35681-110">Specifies the address of the endpoint.</span></span> <span data-ttu-id="35681-111">La dirección debe ser un URI absoluto.</span><span class="sxs-lookup"><span data-stu-id="35681-111">The address must be an absolute URI.</span></span> <span data-ttu-id="35681-112">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="35681-112">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="35681-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="35681-113">Child Elements</span></span>  
  
|<span data-ttu-id="35681-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="35681-114">Element</span></span>|<span data-ttu-id="35681-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="35681-115">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|<span data-ttu-id="35681-116">Una colección de encabezados de dirección.</span><span class="sxs-lookup"><span data-stu-id="35681-116">A collection of address headers.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="35681-117">Una identidad que habilita la autenticación de un punto de conexión por otros puntos de conexión que intercambian mensajes con él.</span><span class="sxs-lookup"><span data-stu-id="35681-117">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="35681-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="35681-118">Parent Elements</span></span>  
  
|<span data-ttu-id="35681-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="35681-119">Element</span></span>|<span data-ttu-id="35681-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="35681-120">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="35681-121">Define la configuración para la seguridad del nivel de mensaje para el [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="35681-121">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="35681-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="35681-122">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>
- [<span data-ttu-id="35681-123">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="35681-123">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="35681-124">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="35681-124">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="35681-125">Capacidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="35681-125">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="35681-126">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="35681-126">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
