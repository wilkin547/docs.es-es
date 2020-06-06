---
title: <add> de <issuerChannelBehaviors>
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: cf7ac2691ad1c641352a8047373ced538b19e983
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398330"
---
# <a name="add-of-issuerchannelbehaviors"></a><span data-ttu-id="0232b-102">\<add> de \<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="0232b-102">\<add> of \<issuerChannelBehaviors></span></span>

<span data-ttu-id="0232b-103">Agrega un comportamiento del punto de conexión que se va a usar al comunicar con STS.</span><span class="sxs-lookup"><span data-stu-id="0232b-103">Adds an endpoint behavior to be used when communicating with an STS.</span></span>

> [!NOTE]
> <span data-ttu-id="0232b-104">Si algún comportamiento del extremo contiene un [\<clientCredentials>](clientcredentials.md) elemento, se producirá una excepción.</span><span class="sxs-lookup"><span data-stu-id="0232b-104">If any endpoint behavior contains a [\<clientCredentials>](clientcredentials.md) element, an exception will be thrown.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedToken>**](issuedtoken.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuerChannelBehaviors>**](issuerchannelbehaviors-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  

## <a name="syntax"></a><span data-ttu-id="0232b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0232b-105">Syntax</span></span>

```xml
<add issuerAddress="string"
     behaviorConfiguration="string" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0232b-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0232b-106">Attributes and Elements</span></span>

<span data-ttu-id="0232b-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0232b-107">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="0232b-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="0232b-108">Attributes</span></span>

|<span data-ttu-id="0232b-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="0232b-109">Attribute</span></span>|<span data-ttu-id="0232b-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="0232b-110">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="0232b-111">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="0232b-111">issuerAddress</span></span>|<span data-ttu-id="0232b-112">El URI del emisor del token seguridad con el que se va a comunicar.</span><span class="sxs-lookup"><span data-stu-id="0232b-112">The URI of the security token issuer to communicate with.</span></span>|
|<span data-ttu-id="0232b-113">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="0232b-113">behaviorConfiguration</span></span>|<span data-ttu-id="0232b-114">El nombre de un comportamiento del extremo definido en el mismo archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="0232b-114">The name of an endpoint behavior defined in the same configuration file.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="0232b-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0232b-115">Child Elements</span></span>

<span data-ttu-id="0232b-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0232b-116">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0232b-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0232b-117">Parent Elements</span></span>

|<span data-ttu-id="0232b-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="0232b-118">Element</span></span>|<span data-ttu-id="0232b-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="0232b-119">Description</span></span>|
|-------------|-----------------|
|[\<issuerChannelBehaviors>](issuerchannelbehaviors-element.md)|<span data-ttu-id="0232b-120">Contiene una colección de comportamientos de extremo de cliente de Windows Communication Foundation (WCF) que se usarán al comunicarse con los servicios de token de servicio especificados.</span><span class="sxs-lookup"><span data-stu-id="0232b-120">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0232b-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0232b-121">Remarks</span></span>

<span data-ttu-id="0232b-122">`issuerAddress` contiene el URI del Servicio de token de seguridad con el que el cliente desea comunicarse.</span><span class="sxs-lookup"><span data-stu-id="0232b-122">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="0232b-123">`behaviorConfiguration`apunta a un comportamiento del extremo que la aplicación utiliza en los canales creados por Windows Communication Foundation (WCF) para obtener los tokens emitidos a partir de los servicios de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="0232b-123">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by Windows Communication Foundation (WCF) to get the issued tokens from the Security Token Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="0232b-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0232b-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="0232b-125">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="0232b-125">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="0232b-126">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="0232b-126">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="0232b-127">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="0232b-127">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="0232b-128">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="0232b-128">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="0232b-129">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="0232b-129">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="0232b-130">Procedimiento para crear un cliente federado</span><span class="sxs-lookup"><span data-stu-id="0232b-130">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="0232b-131">Procedimiento para configurar un emisor local</span><span class="sxs-lookup"><span data-stu-id="0232b-131">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="0232b-132">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="0232b-132">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [\<issuerChannelBehaviors>](issuerchannelbehaviors-element.md)
