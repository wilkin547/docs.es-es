---
description: 'Más información acerca de: <issuer>'
title: <issuer>
ms.date: 03/30/2017
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
ms.openlocfilehash: 771fb8d0bee4e78b598bd20c4d99ec5180f9fb1c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725641"
---
# \<issuer>

<span data-ttu-id="3d040-102">Especifica el servicio de token de seguridad (STS) que emite los tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="3d040-102">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuer>**  
  
## <a name="syntax"></a><span data-ttu-id="3d040-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3d040-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3d040-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3d040-104">Attributes and Elements</span></span>  

 <span data-ttu-id="3d040-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3d040-105">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3d040-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="3d040-106">Attributes</span></span>  
  
|<span data-ttu-id="3d040-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="3d040-107">Attribute</span></span>|<span data-ttu-id="3d040-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="3d040-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3d040-109">address</span><span class="sxs-lookup"><span data-stu-id="3d040-109">address</span></span>|<span data-ttu-id="3d040-110">Cadena necesaria.</span><span class="sxs-lookup"><span data-stu-id="3d040-110">Required string.</span></span> <span data-ttu-id="3d040-111">La dirección URL del STS.</span><span class="sxs-lookup"><span data-stu-id="3d040-111">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3d040-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3d040-112">Child Elements</span></span>  
  
|<span data-ttu-id="3d040-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="3d040-113">Element</span></span>|<span data-ttu-id="3d040-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="3d040-114">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|<span data-ttu-id="3d040-115">Una colección de encabezados de dirección para los puntos de conexión que el generador puede crear.</span><span class="sxs-lookup"><span data-stu-id="3d040-115">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="3d040-116">Al utilizar un token emitido, especifica valores que permiten al cliente autenticar el servidor.</span><span class="sxs-lookup"><span data-stu-id="3d040-116">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3d040-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3d040-117">Parent Elements</span></span>  
  
|<span data-ttu-id="3d040-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="3d040-118">Element</span></span>|<span data-ttu-id="3d040-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="3d040-119">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="3d040-120">Define la configuración para la seguridad del nivel de mensaje para el [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="3d040-120">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3d040-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d040-121">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- [<span data-ttu-id="3d040-122">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="3d040-122">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="3d040-123">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="3d040-123">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="3d040-124">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="3d040-124">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="3d040-125">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="3d040-125">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="3d040-126">Capacidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="3d040-126">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="3d040-127">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="3d040-127">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
