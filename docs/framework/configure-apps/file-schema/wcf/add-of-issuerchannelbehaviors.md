---
title: <add> de <issuerChannelBehaviors>
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: 5c9937cb6302a194228461f3e2e06ecdf4d43269
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377760"
---
# <a name="add-of-issuerchannelbehaviors"></a><span data-ttu-id="3431e-102">\<Agregar > de \<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="3431e-102">\<add> of \<issuerChannelBehaviors></span></span>

<span data-ttu-id="3431e-103">Agrega un comportamiento del punto de conexión que se va a usar al comunicar con STS.</span><span class="sxs-lookup"><span data-stu-id="3431e-103">Adds an endpoint behavior to be used when communicating with an STS.</span></span>

> [!NOTE]
> <span data-ttu-id="3431e-104">Si cualquier comportamiento de extremo contiene un [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elemento, se producirá una excepción.</span><span class="sxs-lookup"><span data-stu-id="3431e-104">If any endpoint behavior contains a [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element, an exception will be thrown.</span></span>

<span data-ttu-id="3431e-105">\<system.ServiceModel>\\</span><span class="sxs-lookup"><span data-stu-id="3431e-105">\<system.ServiceModel>\\</span></span>
<span data-ttu-id="3431e-106">\<comportamientos > \\</span><span class="sxs-lookup"><span data-stu-id="3431e-106">\<behaviors>\\</span></span>
<span data-ttu-id="3431e-107">sección endpointBehaviors \<comportamiento > \\</span><span class="sxs-lookup"><span data-stu-id="3431e-107">endpointBehaviors section \<behavior>\\</span></span>
<span data-ttu-id="3431e-108">\<clientCredentials>\\</span><span class="sxs-lookup"><span data-stu-id="3431e-108">\<clientCredentials>\\</span></span>
<span data-ttu-id="3431e-109">\<issuedToken>\\</span><span class="sxs-lookup"><span data-stu-id="3431e-109">\<issuedToken>\\</span></span>
<span data-ttu-id="3431e-110">\<issuerChannelBehaviors > Element\\</span><span class="sxs-lookup"><span data-stu-id="3431e-110">\<issuerChannelBehaviors> Element\\</span></span>
<span data-ttu-id="3431e-111">\<add></span><span class="sxs-lookup"><span data-stu-id="3431e-111">\<add></span></span>

## <a name="syntax"></a><span data-ttu-id="3431e-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3431e-112">Syntax</span></span>

```xml
<add issuerAddress="string"
     behaviorConfiguration="string" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3431e-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3431e-113">Attributes and Elements</span></span>

<span data-ttu-id="3431e-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3431e-114">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="3431e-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="3431e-115">Attributes</span></span>

|<span data-ttu-id="3431e-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="3431e-116">Attribute</span></span>|<span data-ttu-id="3431e-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="3431e-117">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="3431e-118">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="3431e-118">issuerAddress</span></span>|<span data-ttu-id="3431e-119">El URI del emisor del token seguridad con el que se va a comunicar.</span><span class="sxs-lookup"><span data-stu-id="3431e-119">The URI of the security token issuer to communicate with.</span></span>|
|<span data-ttu-id="3431e-120">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="3431e-120">behaviorConfiguration</span></span>|<span data-ttu-id="3431e-121">El nombre de un comportamiento del extremo definido en el mismo archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="3431e-121">The name of an endpoint behavior defined in the same configuration file.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="3431e-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3431e-122">Child Elements</span></span>

<span data-ttu-id="3431e-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3431e-123">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3431e-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3431e-124">Parent Elements</span></span>

|<span data-ttu-id="3431e-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="3431e-125">Element</span></span>|<span data-ttu-id="3431e-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="3431e-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3431e-127">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="3431e-127">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|<span data-ttu-id="3431e-128">Contiene una colección de comportamientos de extremo de cliente de Windows Communication Foundation (WCF) que se usará al comunicarse con los servicios de Token de servicio especificado.</span><span class="sxs-lookup"><span data-stu-id="3431e-128">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3431e-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3431e-129">Remarks</span></span>

<span data-ttu-id="3431e-130">`issuerAddress` contiene el URI del Servicio de token de seguridad con el que el cliente desea comunicarse.</span><span class="sxs-lookup"><span data-stu-id="3431e-130">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="3431e-131">`behaviorConfiguration` apunta a un comportamiento de extremo que utiliza la aplicación en los canales creados por Windows Communication Foundation (WCF) para obtener los tokens emitidos desde los servicios de Token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="3431e-131">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by Windows Communication Foundation (WCF) to get the issued tokens from the Security Token Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="3431e-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="3431e-132">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="3431e-133">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="3431e-133">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="3431e-134">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="3431e-134">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="3431e-135">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="3431e-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="3431e-136">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="3431e-136">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="3431e-137">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="3431e-137">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="3431e-138">Cómo: Crear a un cliente federado</span><span class="sxs-lookup"><span data-stu-id="3431e-138">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="3431e-139">Cómo: Configurar a un emisor Local</span><span class="sxs-lookup"><span data-stu-id="3431e-139">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="3431e-140">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="3431e-140">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="3431e-141">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="3431e-141">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)
