---
description: 'Más información sobre: <add> de <issuerChannelBehaviors>'
title: <add> de <issuerChannelBehaviors>
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: ccd8ba015b7a6837c74ce2c051a794d36ce8ceaa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99750304"
---
# <a name="add-of-issuerchannelbehaviors"></a><span data-ttu-id="7f204-103">\<add> de \<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="7f204-103">\<add> of \<issuerChannelBehaviors></span></span>

<span data-ttu-id="7f204-104">Agrega un comportamiento del punto de conexión que se va a usar al comunicar con STS.</span><span class="sxs-lookup"><span data-stu-id="7f204-104">Adds an endpoint behavior to be used when communicating with an STS.</span></span>

> [!NOTE]
> <span data-ttu-id="7f204-105">Si algún comportamiento del extremo contiene un [\<clientCredentials>](clientcredentials.md) elemento, se producirá una excepción.</span><span class="sxs-lookup"><span data-stu-id="7f204-105">If any endpoint behavior contains a [\<clientCredentials>](clientcredentials.md) element, an exception will be thrown.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedToken>**](issuedtoken.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuerChannelBehaviors>**](issuerchannelbehaviors-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  

## <a name="syntax"></a><span data-ttu-id="7f204-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7f204-106">Syntax</span></span>

```xml
<add issuerAddress="string"
     behaviorConfiguration="string" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7f204-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7f204-107">Attributes and Elements</span></span>

<span data-ttu-id="7f204-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7f204-108">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="7f204-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="7f204-109">Attributes</span></span>

|<span data-ttu-id="7f204-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="7f204-110">Attribute</span></span>|<span data-ttu-id="7f204-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="7f204-111">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="7f204-112">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="7f204-112">issuerAddress</span></span>|<span data-ttu-id="7f204-113">El URI del emisor del token seguridad con el que se va a comunicar.</span><span class="sxs-lookup"><span data-stu-id="7f204-113">The URI of the security token issuer to communicate with.</span></span>|
|<span data-ttu-id="7f204-114">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="7f204-114">behaviorConfiguration</span></span>|<span data-ttu-id="7f204-115">El nombre de un comportamiento del extremo definido en el mismo archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="7f204-115">The name of an endpoint behavior defined in the same configuration file.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="7f204-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7f204-116">Child Elements</span></span>

<span data-ttu-id="7f204-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7f204-117">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7f204-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7f204-118">Parent Elements</span></span>

|<span data-ttu-id="7f204-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="7f204-119">Element</span></span>|<span data-ttu-id="7f204-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="7f204-120">Description</span></span>|
|-------------|-----------------|
|[\<issuerChannelBehaviors>](issuerchannelbehaviors-element.md)|<span data-ttu-id="7f204-121">Contiene una colección de comportamientos de extremo de cliente de Windows Communication Foundation (WCF) que se usarán al comunicarse con los servicios de token de servicio especificados.</span><span class="sxs-lookup"><span data-stu-id="7f204-121">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7f204-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7f204-122">Remarks</span></span>

<span data-ttu-id="7f204-123">`issuerAddress` contiene el URI del Servicio de token de seguridad con el que el cliente desea comunicarse.</span><span class="sxs-lookup"><span data-stu-id="7f204-123">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="7f204-124">`behaviorConfiguration` apunta a un comportamiento del extremo que la aplicación utiliza en los canales creados por Windows Communication Foundation (WCF) para obtener los tokens emitidos a partir de los servicios de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="7f204-124">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by Windows Communication Foundation (WCF) to get the issued tokens from the Security Token Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="7f204-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f204-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="7f204-126">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="7f204-126">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="7f204-127">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="7f204-127">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="7f204-128">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="7f204-128">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="7f204-129">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="7f204-129">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="7f204-130">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="7f204-130">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="7f204-131">Procedimiento para crear un cliente federado</span><span class="sxs-lookup"><span data-stu-id="7f204-131">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="7f204-132">Procedimiento para configurar un emisor local</span><span class="sxs-lookup"><span data-stu-id="7f204-132">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="7f204-133">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="7f204-133">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [\<issuerChannelBehaviors>](issuerchannelbehaviors-element.md)
