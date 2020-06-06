---
title: <issuerChannelBehaviors> (Elemento)
ms.date: 03/30/2017
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
no-loc:
- <system.serviceModel>
- <behaviors>
- <endpointBehaviors>
- <behavior>
- <clientCredentials>
- <issuedToken>
- <issuerChannelBehaviors>
- <dataContractSerializer>
ms.openlocfilehash: cbbfb9d3b5af47a360aa82cf837cd6749f61b641
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70893161"
---
# <a name="issuerchannelbehaviors-element"></a><span data-ttu-id="222b0-102">\<issuerChannelBehaviors> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="222b0-102">\<issuerChannelBehaviors> Element</span></span>

<span data-ttu-id="222b0-103">Contiene una colección de comportamientos de extremo de cliente de Windows Communication Foundation (WCF) (definidos en la configuración) que se usarán al comunicarse con los servicios de token de servicio especificados.</span><span class="sxs-lookup"><span data-stu-id="222b0-103">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="222b0-104">Los comportamientos definidos no pueden incluir [\<clientCredentials>](clientcredentials.md) elementos.</span><span class="sxs-lookup"><span data-stu-id="222b0-104">The defined behaviors cannot include any [\<clientCredentials>](clientcredentials.md) elements.</span></span>

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;[\<system.serviceModel>](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<behaviors>](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<endpointBehaviors>](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<behavior>](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<clientCredentials>](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<issuedToken>](issuedtoken.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<issuerChannelBehaviors>

## <a name="syntax"></a><span data-ttu-id="222b0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="222b0-105">Syntax</span></span>

```xml
<issuerChannelBehaviors>
  <add behaviorConfiguration="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="222b0-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="222b0-106">Attributes and elements</span></span>

<span data-ttu-id="222b0-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="222b0-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="222b0-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="222b0-108">Attributes</span></span>

<span data-ttu-id="222b0-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="222b0-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="222b0-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="222b0-110">Child elements</span></span>

|<span data-ttu-id="222b0-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="222b0-111">Element</span></span>|<span data-ttu-id="222b0-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="222b0-112">Description</span></span>|
|-------------|-----------------|
|[\<add>](add-of-issuerchannelbehaviors.md)|<span data-ttu-id="222b0-113">Agrega un comportamiento a la colección.</span><span class="sxs-lookup"><span data-stu-id="222b0-113">Adds a behavior to the collection.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="222b0-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="222b0-114">Parent elements</span></span>

|<span data-ttu-id="222b0-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="222b0-115">Element</span></span>|<span data-ttu-id="222b0-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="222b0-116">Description</span></span>|
|-------------|-----------------|
|[\<issuedToken>](issuedtoken.md)|<span data-ttu-id="222b0-117">Especifica un token personalizado usado para autenticar un cliente en un servicio.</span><span class="sxs-lookup"><span data-stu-id="222b0-117">Specifies a custom token used to authenticate a client to a service.</span></span>|

## <a name="remarks"></a><span data-ttu-id="222b0-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="222b0-118">Remarks</span></span>

<span data-ttu-id="222b0-119">Use este elemento cuando se deba utilizar un comportamiento (excepto los comportamientos que incluyen elementos `<clientCredentials>`) para comunicar con un servicio.</span><span class="sxs-lookup"><span data-stu-id="222b0-119">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="222b0-120">Por ejemplo, si [\<dataContractSerializer>](datacontractserializer-element.md) se debe incluir un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="222b0-120">For example, if a [\<dataContractSerializer>](datacontractserializer-element.md) behavior element must be included.</span></span>

## <a name="see-also"></a><span data-ttu-id="222b0-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="222b0-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="222b0-122">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="222b0-122">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="222b0-123">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="222b0-123">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="222b0-124">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="222b0-124">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="222b0-125">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="222b0-125">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="222b0-126">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="222b0-126">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="222b0-127">Procedimiento para crear un cliente federado</span><span class="sxs-lookup"><span data-stu-id="222b0-127">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="222b0-128">Procedimiento para configurar un emisor local</span><span class="sxs-lookup"><span data-stu-id="222b0-128">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="222b0-129">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="222b0-129">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
