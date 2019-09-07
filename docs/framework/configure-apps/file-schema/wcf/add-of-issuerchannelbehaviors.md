---
title: <add> de <issuerChannelBehaviors>
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: cf7ac2691ad1c641352a8047373ced538b19e983
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398330"
---
# <a name="add-of-issuerchannelbehaviors"></a><span data-ttu-id="f11c4-102">\<Agregar > de \<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="f11c4-102">\<add> of \<issuerChannelBehaviors></span></span>

<span data-ttu-id="f11c4-103">Agrega un comportamiento del punto de conexión que se va a usar al comunicar con STS.</span><span class="sxs-lookup"><span data-stu-id="f11c4-103">Adds an endpoint behavior to be used when communicating with an STS.</span></span>

> [!NOTE]
> <span data-ttu-id="f11c4-104">Si algún comportamiento del punto de conexión contiene un [ \<elemento clientCredentials >](clientcredentials.md) , se producirá una excepción.</span><span class="sxs-lookup"><span data-stu-id="f11c4-104">If any endpoint behavior contains a [\<clientCredentials>](clientcredentials.md) element, an exception will be thrown.</span></span>

<span data-ttu-id="f11c4-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f11c4-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f11c4-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="f11c4-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f11c4-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="f11c4-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="f11c4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="f11c4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="f11c4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="f11c4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="f11c4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="f11c4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="f11c4-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> issuedToken**](issuedtoken.md)</span><span class="sxs-lookup"><span data-stu-id="f11c4-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedToken>**](issuedtoken.md)</span></span>\
<span data-ttu-id="f11c4-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> issuerChannelBehaviors**](issuerchannelbehaviors-element.md)</span><span class="sxs-lookup"><span data-stu-id="f11c4-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuerChannelBehaviors>**](issuerchannelbehaviors-element.md)</span></span>\
<span data-ttu-id="f11c4-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Agregar >**</span><span class="sxs-lookup"><span data-stu-id="f11c4-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="f11c4-114">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f11c4-114">Syntax</span></span>

```xml
<add issuerAddress="string"
     behaviorConfiguration="string" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f11c4-115">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f11c4-115">Attributes and Elements</span></span>

<span data-ttu-id="f11c4-116">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f11c4-116">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="f11c4-117">Atributos</span><span class="sxs-lookup"><span data-stu-id="f11c4-117">Attributes</span></span>

|<span data-ttu-id="f11c4-118">Atributo</span><span class="sxs-lookup"><span data-stu-id="f11c4-118">Attribute</span></span>|<span data-ttu-id="f11c4-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f11c4-119">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="f11c4-120">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="f11c4-120">issuerAddress</span></span>|<span data-ttu-id="f11c4-121">El URI del emisor del token seguridad con el que se va a comunicar.</span><span class="sxs-lookup"><span data-stu-id="f11c4-121">The URI of the security token issuer to communicate with.</span></span>|
|<span data-ttu-id="f11c4-122">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="f11c4-122">behaviorConfiguration</span></span>|<span data-ttu-id="f11c4-123">El nombre de un comportamiento del extremo definido en el mismo archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="f11c4-123">The name of an endpoint behavior defined in the same configuration file.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="f11c4-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f11c4-124">Child Elements</span></span>

<span data-ttu-id="f11c4-125">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f11c4-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f11c4-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f11c4-126">Parent Elements</span></span>

|<span data-ttu-id="f11c4-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="f11c4-127">Element</span></span>|<span data-ttu-id="f11c4-128">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f11c4-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f11c4-129">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="f11c4-129">\<issuerChannelBehaviors></span></span>](issuerchannelbehaviors-element.md)|<span data-ttu-id="f11c4-130">Contiene una colección de comportamientos de extremo de cliente de Windows Communication Foundation (WCF) que se usarán al comunicarse con los servicios de token de servicio especificados.</span><span class="sxs-lookup"><span data-stu-id="f11c4-130">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f11c4-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f11c4-131">Remarks</span></span>

<span data-ttu-id="f11c4-132">`issuerAddress` contiene el URI del Servicio de token de seguridad con el que el cliente desea comunicarse.</span><span class="sxs-lookup"><span data-stu-id="f11c4-132">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="f11c4-133">`behaviorConfiguration`apunta a un comportamiento del extremo que la aplicación utiliza en los canales creados por Windows Communication Foundation (WCF) para obtener los tokens emitidos a partir de los servicios de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f11c4-133">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by Windows Communication Foundation (WCF) to get the issued tokens from the Security Token Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="f11c4-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="f11c4-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="f11c4-135">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="f11c4-135">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="f11c4-136">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="f11c4-136">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="f11c4-137">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="f11c4-137">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="f11c4-138">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="f11c4-138">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="f11c4-139">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="f11c4-139">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="f11c4-140">Procedimientos: Creación de un cliente federado</span><span class="sxs-lookup"><span data-stu-id="f11c4-140">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="f11c4-141">Procedimientos: Configuración de un emisor local</span><span class="sxs-lookup"><span data-stu-id="f11c4-141">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="f11c4-142">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="f11c4-142">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="f11c4-143">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="f11c4-143">\<issuerChannelBehaviors></span></span>](issuerchannelbehaviors-element.md)
