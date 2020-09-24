---
title: <issuer>
ms.date: 03/30/2017
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
ms.openlocfilehash: 9e92bbcacf529a97e1ae936e93e38c98eab19cab
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157270"
---
# \<issuer>

<span data-ttu-id="48cb4-101">Especifica el servicio de token de seguridad (STS) que emite los tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="48cb4-101">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuer>**  
  
## <a name="syntax"></a><span data-ttu-id="48cb4-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="48cb4-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="48cb4-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="48cb4-103">Attributes and Elements</span></span>  

 <span data-ttu-id="48cb4-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="48cb4-104">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="48cb4-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="48cb4-105">Attributes</span></span>  
  
|<span data-ttu-id="48cb4-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="48cb4-106">Attribute</span></span>|<span data-ttu-id="48cb4-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="48cb4-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="48cb4-108">address</span><span class="sxs-lookup"><span data-stu-id="48cb4-108">address</span></span>|<span data-ttu-id="48cb4-109">Cadena necesaria.</span><span class="sxs-lookup"><span data-stu-id="48cb4-109">Required string.</span></span> <span data-ttu-id="48cb4-110">La dirección URL del STS.</span><span class="sxs-lookup"><span data-stu-id="48cb4-110">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="48cb4-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="48cb4-111">Child Elements</span></span>  
  
|<span data-ttu-id="48cb4-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="48cb4-112">Element</span></span>|<span data-ttu-id="48cb4-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="48cb4-113">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|<span data-ttu-id="48cb4-114">Una colección de encabezados de dirección para los puntos de conexión que el generador puede crear.</span><span class="sxs-lookup"><span data-stu-id="48cb4-114">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="48cb4-115">Al utilizar un token emitido, especifica valores que permiten al cliente autenticar el servidor.</span><span class="sxs-lookup"><span data-stu-id="48cb4-115">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="48cb4-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="48cb4-116">Parent Elements</span></span>  
  
|<span data-ttu-id="48cb4-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="48cb4-117">Element</span></span>|<span data-ttu-id="48cb4-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="48cb4-118">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="48cb4-119">Define la configuración para la seguridad del nivel de mensaje para el [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="48cb4-119">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="48cb4-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="48cb4-120">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- [<span data-ttu-id="48cb4-121">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="48cb4-121">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="48cb4-122">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="48cb4-122">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="48cb4-123">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="48cb4-123">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="48cb4-124">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="48cb4-124">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="48cb4-125">Capacidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="48cb4-125">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="48cb4-126">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="48cb4-126">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
