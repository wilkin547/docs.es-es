---
title: <issuer>
ms.date: 03/30/2017
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
ms.openlocfilehash: 74f5f2fc1a0fa1ffbbb510e4e700c33a13d02ab3
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397911"
---
# <a name="issuer"></a><span data-ttu-id="c4335-101">\<issuer></span><span class="sxs-lookup"><span data-stu-id="c4335-101">\<issuer></span></span>
<span data-ttu-id="c4335-102">Especifica el servicio de token de seguridad (STS) que emite los tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c4335-102">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
<span data-ttu-id="c4335-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c4335-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c4335-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c4335-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c4335-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enlaces**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="c4335-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="c4335-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> wsFederationHttpBinding**](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="c4335-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="c4335-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de enlace**</span><span class="sxs-lookup"><span data-stu-id="c4335-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="c4335-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguridad**](security-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="c4335-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="c4335-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de mensajes**](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="c4335-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="c4335-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> del emisor**</span><span class="sxs-lookup"><span data-stu-id="c4335-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4335-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c4335-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c4335-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c4335-112">Attributes and Elements</span></span>  
 <span data-ttu-id="c4335-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c4335-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c4335-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="c4335-114">Attributes</span></span>  
  
|<span data-ttu-id="c4335-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="c4335-115">Attribute</span></span>|<span data-ttu-id="c4335-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c4335-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c4335-117">dirección</span><span class="sxs-lookup"><span data-stu-id="c4335-117">address</span></span>|<span data-ttu-id="c4335-118">Cadena necesaria.</span><span class="sxs-lookup"><span data-stu-id="c4335-118">Required string.</span></span> <span data-ttu-id="c4335-119">La dirección URL del STS.</span><span class="sxs-lookup"><span data-stu-id="c4335-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c4335-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c4335-120">Child Elements</span></span>  
  
|<span data-ttu-id="c4335-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="c4335-121">Element</span></span>|<span data-ttu-id="c4335-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c4335-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c4335-123">\<headers></span><span class="sxs-lookup"><span data-stu-id="c4335-123">\<headers></span></span>](headers-element.md)|<span data-ttu-id="c4335-124">Una colección de encabezados de dirección para los puntos de conexión que el generador puede crear.</span><span class="sxs-lookup"><span data-stu-id="c4335-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="c4335-125">\<identity></span><span class="sxs-lookup"><span data-stu-id="c4335-125">\<identity></span></span>](identity.md)|<span data-ttu-id="c4335-126">Al utilizar un token emitido, especifica valores que permiten al cliente autenticar el servidor.</span><span class="sxs-lookup"><span data-stu-id="c4335-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c4335-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c4335-127">Parent Elements</span></span>  
  
|<span data-ttu-id="c4335-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="c4335-128">Element</span></span>|<span data-ttu-id="c4335-129">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c4335-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c4335-130">\<message></span><span class="sxs-lookup"><span data-stu-id="c4335-130">\<message></span></span>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="c4335-131">Define la configuración para la seguridad del nivel de mensaje para [ \<](wsfederationhttpbinding.md) el elemento > de wsFederationHttpBinding.</span><span class="sxs-lookup"><span data-stu-id="c4335-131">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c4335-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4335-132">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- [<span data-ttu-id="c4335-133">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="c4335-133">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="c4335-134">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="c4335-134">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="c4335-135">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="c4335-135">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="c4335-136">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="c4335-136">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="c4335-137">Funcionalidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="c4335-137">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="c4335-138">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="c4335-138">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
