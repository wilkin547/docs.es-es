---
description: 'Más información acerca de: <issuerChannelBehaviors> elemento'
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
ms.openlocfilehash: 6be79f2ee6afb442a7a399ce49df4ad59dff2db5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725550"
---
# <a name="issuerchannelbehaviors-element"></a><span data-ttu-id="97ef7-103">\::: no-LOC ( <issuerChannelBehaviors> )::: Element</span><span class="sxs-lookup"><span data-stu-id="97ef7-103">\<issuerChannelBehaviors> Element</span></span>

<span data-ttu-id="97ef7-104">Contiene una colección de comportamientos de extremo de cliente de Windows Communication Foundation (WCF) (definidos en la configuración) que se usarán al comunicarse con los servicios de token de servicio especificados.</span><span class="sxs-lookup"><span data-stu-id="97ef7-104">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="97ef7-105">Los comportamientos definidos no pueden incluir los elementos [ \: :: no-LOC ( <clientCredentials> )::](clientcredentials.md) :.</span><span class="sxs-lookup"><span data-stu-id="97ef7-105">The defined behaviors cannot include any [\<clientCredentials>](clientcredentials.md) elements.</span></span>

[\<configuration>](../configuration-element.md)\
<span data-ttu-id="97ef7-106">&nbsp;&nbsp;[\::: no-LOC (<System. serviceModel>):::](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="97ef7-106">&nbsp;&nbsp;[\<system.serviceModel>](system-servicemodel.md)</span></span>\
<span data-ttu-id="97ef7-107">&nbsp;&nbsp;&nbsp;&nbsp;[\::: no-LOC ( <behaviors> ):::](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="97ef7-107">&nbsp;&nbsp;&nbsp;&nbsp;[\<behaviors>](behaviors.md)</span></span>\
<span data-ttu-id="97ef7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\::: no-LOC ( <endpointBehaviors> ):::](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="97ef7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<endpointBehaviors>](endpointbehaviors.md)</span></span>\
<span data-ttu-id="97ef7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\::: no-LOC ( <behavior> ):::](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="97ef7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<behavior>](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="97ef7-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\::: no-LOC ( <clientCredentials> ):::](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="97ef7-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<clientCredentials>](clientcredentials.md)</span></span>\
<span data-ttu-id="97ef7-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\::: no-LOC ( <issuedToken> ):::](issuedtoken.md)</span><span class="sxs-lookup"><span data-stu-id="97ef7-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<issuedToken>](issuedtoken.md)</span></span>\
<span data-ttu-id="97ef7-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\::: no-LOC ( <issuerChannelBehaviors> ):::</span><span class="sxs-lookup"><span data-stu-id="97ef7-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<issuerChannelBehaviors></span></span>

## <a name="syntax"></a><span data-ttu-id="97ef7-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="97ef7-113">Syntax</span></span>

```xml
<issuerChannelBehaviors>
  <add behaviorConfiguration="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="97ef7-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="97ef7-114">Attributes and elements</span></span>

<span data-ttu-id="97ef7-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="97ef7-115">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="97ef7-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="97ef7-116">Attributes</span></span>

<span data-ttu-id="97ef7-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="97ef7-117">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="97ef7-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="97ef7-118">Child elements</span></span>

|<span data-ttu-id="97ef7-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="97ef7-119">Element</span></span>|<span data-ttu-id="97ef7-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="97ef7-120">Description</span></span>|
|-------------|-----------------|
|[\<add>](add-of-issuerchannelbehaviors.md)|<span data-ttu-id="97ef7-121">Agrega un comportamiento a la colección.</span><span class="sxs-lookup"><span data-stu-id="97ef7-121">Adds a behavior to the collection.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="97ef7-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="97ef7-122">Parent elements</span></span>

|<span data-ttu-id="97ef7-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="97ef7-123">Element</span></span>|<span data-ttu-id="97ef7-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="97ef7-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="97ef7-125">\::: no-LOC ( <issuedToken> ):::</span><span class="sxs-lookup"><span data-stu-id="97ef7-125">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="97ef7-126">Especifica un token personalizado usado para autenticar un cliente en un servicio.</span><span class="sxs-lookup"><span data-stu-id="97ef7-126">Specifies a custom token used to authenticate a client to a service.</span></span>|

## <a name="remarks"></a><span data-ttu-id="97ef7-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="97ef7-127">Remarks</span></span>

<span data-ttu-id="97ef7-128">Use este elemento cuando se deba utilizar un comportamiento (excepto los comportamientos que incluyen elementos `<clientCredentials>`) para comunicar con un servicio.</span><span class="sxs-lookup"><span data-stu-id="97ef7-128">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="97ef7-129">Por ejemplo, si se debe incluir un elemento [ \: :: no-LOC ( <dataContractSerializer> ):::](datacontractserializer-element.md) Behavior.</span><span class="sxs-lookup"><span data-stu-id="97ef7-129">For example, if a [\<dataContractSerializer>](datacontractserializer-element.md) behavior element must be included.</span></span>

## <a name="see-also"></a><span data-ttu-id="97ef7-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="97ef7-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="97ef7-131">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="97ef7-131">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="97ef7-132">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="97ef7-132">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="97ef7-133">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="97ef7-133">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="97ef7-134">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="97ef7-134">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="97ef7-135">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="97ef7-135">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="97ef7-136">Procedimiento para crear un cliente federado</span><span class="sxs-lookup"><span data-stu-id="97ef7-136">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="97ef7-137">Procedimiento para configurar un emisor local</span><span class="sxs-lookup"><span data-stu-id="97ef7-137">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="97ef7-138">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="97ef7-138">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
