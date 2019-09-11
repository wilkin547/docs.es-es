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
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2019
ms.locfileid: "70893161"
---
# <a name="issuerchannelbehaviors-element"></a><span data-ttu-id="d7911-102">\<issuerChannelBehaviors >, elemento</span><span class="sxs-lookup"><span data-stu-id="d7911-102">\<issuerChannelBehaviors> Element</span></span>

<span data-ttu-id="d7911-103">Contiene una colección de comportamientos de extremo de cliente de Windows Communication Foundation (WCF) (definidos en la configuración) que se usarán al comunicarse con los servicios de token de servicio especificados.</span><span class="sxs-lookup"><span data-stu-id="d7911-103">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="d7911-104">Los comportamientos definidos no pueden incluir [ \<elementos > clientCredentials](clientcredentials.md) .</span><span class="sxs-lookup"><span data-stu-id="d7911-104">The defined behaviors cannot include any [\<clientCredentials>](clientcredentials.md) elements.</span></span>

<span data-ttu-id="d7911-105">[\<configuration>](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d7911-105">[\<configuration>](../configuration-element.md)</span></span>\
<span data-ttu-id="d7911-106">&nbsp;&nbsp;[\<> System. serviceModel](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="d7911-106">&nbsp;&nbsp;[\<system.serviceModel>](system-servicemodel.md)</span></span>\
<span data-ttu-id="d7911-107">&nbsp;&nbsp;&nbsp;&nbsp;[\<comportamientos >](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d7911-107">&nbsp;&nbsp;&nbsp;&nbsp;[\<behaviors>](behaviors.md)</span></span>\
<span data-ttu-id="d7911-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<> endpointBehaviors](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d7911-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<endpointBehaviors>](endpointbehaviors.md)</span></span>\
<span data-ttu-id="d7911-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<comportamiento >](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d7911-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<behavior>](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="d7911-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<clientCredentials >](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="d7911-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<clientCredentials>](clientcredentials.md)</span></span>\
<span data-ttu-id="d7911-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<> issuedToken](issuedtoken.md)</span><span class="sxs-lookup"><span data-stu-id="d7911-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<issuedToken>](issuedtoken.md)</span></span>\
<span data-ttu-id="d7911-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<> issuerChannelBehaviors</span><span class="sxs-lookup"><span data-stu-id="d7911-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<issuerChannelBehaviors></span></span>

## <a name="syntax"></a><span data-ttu-id="d7911-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d7911-113">Syntax</span></span>

```xml
<issuerChannelBehaviors>
  <add behaviorConfiguration="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d7911-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d7911-114">Attributes and elements</span></span>

<span data-ttu-id="d7911-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d7911-115">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="d7911-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="d7911-116">Attributes</span></span>

<span data-ttu-id="d7911-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d7911-117">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d7911-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d7911-118">Child elements</span></span>

|<span data-ttu-id="d7911-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="d7911-119">Element</span></span>|<span data-ttu-id="d7911-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d7911-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d7911-121">\<add></span><span class="sxs-lookup"><span data-stu-id="d7911-121">\<add></span></span>](add-of-issuerchannelbehaviors.md)|<span data-ttu-id="d7911-122">Agrega un comportamiento a la colección.</span><span class="sxs-lookup"><span data-stu-id="d7911-122">Adds a behavior to the collection.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d7911-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d7911-123">Parent elements</span></span>

|<span data-ttu-id="d7911-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="d7911-124">Element</span></span>|<span data-ttu-id="d7911-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d7911-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d7911-126">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="d7911-126">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="d7911-127">Especifica un token personalizado usado para autenticar un cliente en un servicio.</span><span class="sxs-lookup"><span data-stu-id="d7911-127">Specifies a custom token used to authenticate a client to a service.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d7911-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d7911-128">Remarks</span></span>

<span data-ttu-id="d7911-129">Use este elemento cuando se deba utilizar un comportamiento (excepto los comportamientos que incluyen elementos `<clientCredentials>`) para comunicar con un servicio.</span><span class="sxs-lookup"><span data-stu-id="d7911-129">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="d7911-130">Por ejemplo, si se [ \<](datacontractserializer-element.md) debe incluir un elemento de comportamiento dataContractSerializer >.</span><span class="sxs-lookup"><span data-stu-id="d7911-130">For example, if a [\<dataContractSerializer>](datacontractserializer-element.md) behavior element must be included.</span></span>

## <a name="see-also"></a><span data-ttu-id="d7911-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="d7911-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="d7911-132">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="d7911-132">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="d7911-133">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="d7911-133">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="d7911-134">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="d7911-134">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="d7911-135">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="d7911-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="d7911-136">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="d7911-136">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="d7911-137">Cómo: Creación de un cliente federado</span><span class="sxs-lookup"><span data-stu-id="d7911-137">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="d7911-138">Cómo: Configuración de un emisor local</span><span class="sxs-lookup"><span data-stu-id="d7911-138">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="d7911-139">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="d7911-139">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
