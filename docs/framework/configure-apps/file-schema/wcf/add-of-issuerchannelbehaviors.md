---
title: <add> de <issuerChannelBehaviors>
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: 325d6b8111115384b18547bd11ccec8a4a8af711
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920111"
---
# <a name="add-of-issuerchannelbehaviors"></a><span data-ttu-id="d2fad-102">\<Agregar > de \<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="d2fad-102">\<add> of \<issuerChannelBehaviors></span></span>

<span data-ttu-id="d2fad-103">Agrega un comportamiento del punto de conexión que se va a usar al comunicar con STS.</span><span class="sxs-lookup"><span data-stu-id="d2fad-103">Adds an endpoint behavior to be used when communicating with an STS.</span></span>

> [!NOTE]
> <span data-ttu-id="d2fad-104">Si algún comportamiento del punto de conexión contiene un [ \<elemento clientCredentials >](clientcredentials.md) , se producirá una excepción.</span><span class="sxs-lookup"><span data-stu-id="d2fad-104">If any endpoint behavior contains a [\<clientCredentials>](clientcredentials.md) element, an exception will be thrown.</span></span>

<span data-ttu-id="d2fad-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d2fad-105">\<system.ServiceModel></span></span>\
<span data-ttu-id="d2fad-106">\<comportamientos > </span><span class="sxs-lookup"><span data-stu-id="d2fad-106">\<behaviors></span></span>\
<span data-ttu-id="d2fad-107">comportamiento de \<la sección endpointBehaviors > </span><span class="sxs-lookup"><span data-stu-id="d2fad-107">endpointBehaviors section \<behavior></span></span>\
<span data-ttu-id="d2fad-108">\<clientCredentials > </span><span class="sxs-lookup"><span data-stu-id="d2fad-108">\<clientCredentials></span></span>\
<span data-ttu-id="d2fad-109">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="d2fad-109">\<issuedToken></span></span>\
<span data-ttu-id="d2fad-110">\<issuerChannelBehaviors > elemento </span><span class="sxs-lookup"><span data-stu-id="d2fad-110">\<issuerChannelBehaviors> Element</span></span>\
<span data-ttu-id="d2fad-111">\<add></span><span class="sxs-lookup"><span data-stu-id="d2fad-111">\<add></span></span>

## <a name="syntax"></a><span data-ttu-id="d2fad-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d2fad-112">Syntax</span></span>

```xml
<add issuerAddress="string"
     behaviorConfiguration="string" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d2fad-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d2fad-113">Attributes and Elements</span></span>

<span data-ttu-id="d2fad-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d2fad-114">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="d2fad-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="d2fad-115">Attributes</span></span>

|<span data-ttu-id="d2fad-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="d2fad-116">Attribute</span></span>|<span data-ttu-id="d2fad-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d2fad-117">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="d2fad-118">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="d2fad-118">issuerAddress</span></span>|<span data-ttu-id="d2fad-119">El URI del emisor del token seguridad con el que se va a comunicar.</span><span class="sxs-lookup"><span data-stu-id="d2fad-119">The URI of the security token issuer to communicate with.</span></span>|
|<span data-ttu-id="d2fad-120">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="d2fad-120">behaviorConfiguration</span></span>|<span data-ttu-id="d2fad-121">El nombre de un comportamiento del extremo definido en el mismo archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="d2fad-121">The name of an endpoint behavior defined in the same configuration file.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="d2fad-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d2fad-122">Child Elements</span></span>

<span data-ttu-id="d2fad-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d2fad-123">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d2fad-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d2fad-124">Parent Elements</span></span>

|<span data-ttu-id="d2fad-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="d2fad-125">Element</span></span>|<span data-ttu-id="d2fad-126">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d2fad-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d2fad-127">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="d2fad-127">\<issuerChannelBehaviors></span></span>](issuerchannelbehaviors-element.md)|<span data-ttu-id="d2fad-128">Contiene una colección de comportamientos de extremo de cliente de Windows Communication Foundation (WCF) que se usarán al comunicarse con los servicios de token de servicio especificados.</span><span class="sxs-lookup"><span data-stu-id="d2fad-128">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d2fad-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d2fad-129">Remarks</span></span>

<span data-ttu-id="d2fad-130">`issuerAddress` contiene el URI del Servicio de token de seguridad con el que el cliente desea comunicarse.</span><span class="sxs-lookup"><span data-stu-id="d2fad-130">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="d2fad-131">`behaviorConfiguration`apunta a un comportamiento del extremo que la aplicación utiliza en los canales creados por Windows Communication Foundation (WCF) para obtener los tokens emitidos a partir de los servicios de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="d2fad-131">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by Windows Communication Foundation (WCF) to get the issued tokens from the Security Token Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="d2fad-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="d2fad-132">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="d2fad-133">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="d2fad-133">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="d2fad-134">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="d2fad-134">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="d2fad-135">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="d2fad-135">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="d2fad-136">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="d2fad-136">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="d2fad-137">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="d2fad-137">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="d2fad-138">Cómo: Creación de un cliente federado</span><span class="sxs-lookup"><span data-stu-id="d2fad-138">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="d2fad-139">Cómo: Configuración de un emisor local</span><span class="sxs-lookup"><span data-stu-id="d2fad-139">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="d2fad-140">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="d2fad-140">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="d2fad-141">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="d2fad-141">\<issuerChannelBehaviors></span></span>](issuerchannelbehaviors-element.md)
