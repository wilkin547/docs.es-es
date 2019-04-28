---
title: <add> de <issuerChannelBehaviors>
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: 5c9937cb6302a194228461f3e2e06ecdf4d43269
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673620"
---
# <a name="add-of-issuerchannelbehaviors"></a><span data-ttu-id="5164a-102">\<Agregar > de \<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="5164a-102">\<add> of \<issuerChannelBehaviors></span></span>

<span data-ttu-id="5164a-103">Agrega un comportamiento del punto de conexión que se va a usar al comunicar con STS.</span><span class="sxs-lookup"><span data-stu-id="5164a-103">Adds an endpoint behavior to be used when communicating with an STS.</span></span>

> [!NOTE]
> <span data-ttu-id="5164a-104">Si cualquier comportamiento de extremo contiene un [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elemento, se producirá una excepción.</span><span class="sxs-lookup"><span data-stu-id="5164a-104">If any endpoint behavior contains a [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element, an exception will be thrown.</span></span>

<span data-ttu-id="5164a-105">\<system.ServiceModel>\\</span><span class="sxs-lookup"><span data-stu-id="5164a-105">\<system.ServiceModel>\\</span></span>
<span data-ttu-id="5164a-106">\<comportamientos > \\</span><span class="sxs-lookup"><span data-stu-id="5164a-106">\<behaviors>\\</span></span>
<span data-ttu-id="5164a-107">sección endpointBehaviors \<comportamiento > \\</span><span class="sxs-lookup"><span data-stu-id="5164a-107">endpointBehaviors section \<behavior>\\</span></span>
<span data-ttu-id="5164a-108">\<clientCredentials>\\</span><span class="sxs-lookup"><span data-stu-id="5164a-108">\<clientCredentials>\\</span></span>
<span data-ttu-id="5164a-109">\<issuedToken>\\</span><span class="sxs-lookup"><span data-stu-id="5164a-109">\<issuedToken>\\</span></span>
<span data-ttu-id="5164a-110">\<issuerChannelBehaviors > Element\\</span><span class="sxs-lookup"><span data-stu-id="5164a-110">\<issuerChannelBehaviors> Element\\</span></span>
<span data-ttu-id="5164a-111">\<add></span><span class="sxs-lookup"><span data-stu-id="5164a-111">\<add></span></span>

## <a name="syntax"></a><span data-ttu-id="5164a-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5164a-112">Syntax</span></span>

```xml
<add issuerAddress="string"
     behaviorConfiguration="string" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5164a-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5164a-113">Attributes and Elements</span></span>

<span data-ttu-id="5164a-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5164a-114">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="5164a-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="5164a-115">Attributes</span></span>

|<span data-ttu-id="5164a-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="5164a-116">Attribute</span></span>|<span data-ttu-id="5164a-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="5164a-117">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="5164a-118">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="5164a-118">issuerAddress</span></span>|<span data-ttu-id="5164a-119">El URI del emisor del token seguridad con el que se va a comunicar.</span><span class="sxs-lookup"><span data-stu-id="5164a-119">The URI of the security token issuer to communicate with.</span></span>|
|<span data-ttu-id="5164a-120">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="5164a-120">behaviorConfiguration</span></span>|<span data-ttu-id="5164a-121">El nombre de un comportamiento del extremo definido en el mismo archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="5164a-121">The name of an endpoint behavior defined in the same configuration file.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="5164a-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5164a-122">Child Elements</span></span>

<span data-ttu-id="5164a-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5164a-123">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="5164a-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5164a-124">Parent Elements</span></span>

|<span data-ttu-id="5164a-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="5164a-125">Element</span></span>|<span data-ttu-id="5164a-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="5164a-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5164a-127">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="5164a-127">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|<span data-ttu-id="5164a-128">Contiene una colección de comportamientos de extremo de cliente de Windows Communication Foundation (WCF) que se usará al comunicarse con los servicios de Token de servicio especificado.</span><span class="sxs-lookup"><span data-stu-id="5164a-128">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5164a-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5164a-129">Remarks</span></span>

<span data-ttu-id="5164a-130">`issuerAddress` contiene el URI del Servicio de token de seguridad con el que el cliente desea comunicarse.</span><span class="sxs-lookup"><span data-stu-id="5164a-130">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="5164a-131">`behaviorConfiguration` apunta a un comportamiento de extremo que utiliza la aplicación en los canales creados por Windows Communication Foundation (WCF) para obtener los tokens emitidos desde los servicios de Token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5164a-131">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by Windows Communication Foundation (WCF) to get the issued tokens from the Security Token Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="5164a-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="5164a-132">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="5164a-133">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="5164a-133">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="5164a-134">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="5164a-134">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="5164a-135">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="5164a-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="5164a-136">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="5164a-136">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="5164a-137">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="5164a-137">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="5164a-138">Cómo: Crear a un cliente federado</span><span class="sxs-lookup"><span data-stu-id="5164a-138">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="5164a-139">Cómo: Configurar a un emisor Local</span><span class="sxs-lookup"><span data-stu-id="5164a-139">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="5164a-140">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="5164a-140">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="5164a-141">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="5164a-141">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)
