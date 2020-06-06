---
title: <issuer>
ms.date: 03/30/2017
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
ms.openlocfilehash: 74f5f2fc1a0fa1ffbbb510e4e700c33a13d02ab3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397911"
---
# \<issuer>
<span data-ttu-id="994cf-101">Especifica el servicio de token de seguridad (STS) que emite los tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="994cf-101">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuer>**  
  
## <a name="syntax"></a><span data-ttu-id="994cf-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="994cf-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="994cf-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="994cf-103">Attributes and Elements</span></span>  
 <span data-ttu-id="994cf-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="994cf-104">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="994cf-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="994cf-105">Attributes</span></span>  
  
|<span data-ttu-id="994cf-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="994cf-106">Attribute</span></span>|<span data-ttu-id="994cf-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="994cf-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="994cf-108">address</span><span class="sxs-lookup"><span data-stu-id="994cf-108">address</span></span>|<span data-ttu-id="994cf-109">Cadena necesaria.</span><span class="sxs-lookup"><span data-stu-id="994cf-109">Required string.</span></span> <span data-ttu-id="994cf-110">La dirección URL del STS.</span><span class="sxs-lookup"><span data-stu-id="994cf-110">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="994cf-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="994cf-111">Child Elements</span></span>  
  
|<span data-ttu-id="994cf-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="994cf-112">Element</span></span>|<span data-ttu-id="994cf-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="994cf-113">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|<span data-ttu-id="994cf-114">Una colección de encabezados de dirección para los puntos de conexión que el generador puede crear.</span><span class="sxs-lookup"><span data-stu-id="994cf-114">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="994cf-115">Al utilizar un token emitido, especifica valores que permiten al cliente autenticar el servidor.</span><span class="sxs-lookup"><span data-stu-id="994cf-115">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="994cf-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="994cf-116">Parent Elements</span></span>  
  
|<span data-ttu-id="994cf-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="994cf-117">Element</span></span>|<span data-ttu-id="994cf-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="994cf-118">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="994cf-119">Define la configuración para la seguridad del nivel de mensaje para el [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="994cf-119">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="994cf-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="994cf-120">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- [<span data-ttu-id="994cf-121">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="994cf-121">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="994cf-122">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="994cf-122">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="994cf-123">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="994cf-123">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="994cf-124">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="994cf-124">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="994cf-125">Capacidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="994cf-125">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="994cf-126">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="994cf-126">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
