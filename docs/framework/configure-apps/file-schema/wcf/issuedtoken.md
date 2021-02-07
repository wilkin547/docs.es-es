---
description: 'Más información acerca de: <issuedToken>'
title: <issuedToken>
ms.date: 03/30/2017
ms.assetid: b6eae4b7-a6cd-4e1a-b0f6-f407022550b0
ms.openlocfilehash: aa7486a621d5a6e6900f67300792e29ce2538257
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725693"
---
# \<issuedToken>

<span data-ttu-id="d32f1-102">Especifica un token personalizado usado para autenticar un cliente en un servicio.</span><span class="sxs-lookup"><span data-stu-id="d32f1-102">Specifies a custom token used to authenticate a client to a service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuedToken>**  
  
## <a name="syntax"></a><span data-ttu-id="d32f1-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d32f1-103">Syntax</span></span>  
  
```xml  
<issuedToken cacheIssuedTokens="Boolean"
             defaultKeyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"
             issuedTokenRenewalThresholdPercentage = "0 to 100"
             issuerChannelBehaviors="String"
             localIssuerChannelBehaviors="String"
             maxIssuedTokenCachingTime="TimeSpan">
</issuedToken>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d32f1-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d32f1-104">Attributes and Elements</span></span>  

 <span data-ttu-id="d32f1-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d32f1-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d32f1-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="d32f1-106">Attributes</span></span>  
  
|<span data-ttu-id="d32f1-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="d32f1-107">Attribute</span></span>|<span data-ttu-id="d32f1-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="d32f1-108">Description</span></span>|  
|---------------|-----------------|  
|`cacheIssuedTokens`|<span data-ttu-id="d32f1-109">Atributo booleano opcional que especifica si los tokens están almacenados en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="d32f1-109">Optional Boolean attribute that specifies whether tokens are cached.</span></span> <span data-ttu-id="d32f1-110">De manera predeterminada, es `true`.</span><span class="sxs-lookup"><span data-stu-id="d32f1-110">The default is `true`.</span></span>|  
|`defaultKeyEntropyMode`|<span data-ttu-id="d32f1-111">Atributo de cadena opcional que especifica los valores aleatorios (entropías) que se usan para las operaciones del protocolo en enlace.</span><span class="sxs-lookup"><span data-stu-id="d32f1-111">Optional string attribute that specifies which random values (entropies) are used for handshake operations.</span></span> <span data-ttu-id="d32f1-112">Los valores incluyen `ClientEntropy`, `ServerEntropy` y `CombinedEntropy`. El valor predeterminado es `CombinedEntropy`.</span><span class="sxs-lookup"><span data-stu-id="d32f1-112">Values include `ClientEntropy`, `ServerEntropy`, and `CombinedEntropy`, The default is `CombinedEntropy`.</span></span> <span data-ttu-id="d32f1-113">Este atributo es del tipo <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.</span><span class="sxs-lookup"><span data-stu-id="d32f1-113">This attribute is of type <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.</span></span>|  
|`issuedTokenRenewalThresholdPercentage`|<span data-ttu-id="d32f1-114">Atributo de entero opcional que especifica el porcentaje de un intervalo de tiempo válido (proporcionado por el emisor del token) que puede pasar antes de que se renueve un token.</span><span class="sxs-lookup"><span data-stu-id="d32f1-114">Optional integer attribute that specifies the percentage of a valid time frame (supplied by the token issuer) that can pass before a token is renewed.</span></span> <span data-ttu-id="d32f1-115">Los valores van de 0 a 100.</span><span class="sxs-lookup"><span data-stu-id="d32f1-115">Values are from 0 to 100.</span></span> <span data-ttu-id="d32f1-116">El valor predeterminado es 60, que especifica el 60% de los pasos de tiempo antes de intentar una renovación.</span><span class="sxs-lookup"><span data-stu-id="d32f1-116">The default is 60, which specifies 60% of the time passes before a renewal is attempted.</span></span>|  
|`issuerChannelBehaviors`|<span data-ttu-id="d32f1-117">Atributo opcional que especifica los comportamientos del canal que se va a usar al comunicar con el emisor.</span><span class="sxs-lookup"><span data-stu-id="d32f1-117">Optional attribute that specifies the channel behaviors to use when communicating with the issuer.</span></span>|  
|`localIssuerChannelBehaviors`|<span data-ttu-id="d32f1-118">Atributo opcional que especifica los comportamientos del canal que se va a usar al comunicar con el emisor local.</span><span class="sxs-lookup"><span data-stu-id="d32f1-118">Optional attribute that specifies the channel behaviors to use when communicating with the local issuer.</span></span>|  
|`maxIssuedTokenCachingTime`|<span data-ttu-id="d32f1-119">Atributo Timespan opcional que especifica la duración que los tokens emitidos están almacenados en memoria caché cuando el emisor del token (un STS) no especifica una hora.</span><span class="sxs-lookup"><span data-stu-id="d32f1-119">Optional Timespan attribute that specifies the duration that issued tokens are cached when the token issuer (an STS) does not specify a time.</span></span> <span data-ttu-id="d32f1-120">El valor predeterminado es "10675199.02:48:05.4775807".</span><span class="sxs-lookup"><span data-stu-id="d32f1-120">The default is "10675199.02:48:05.4775807."</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d32f1-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d32f1-121">Child Elements</span></span>  
  
|<span data-ttu-id="d32f1-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="d32f1-122">Element</span></span>|<span data-ttu-id="d32f1-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="d32f1-123">Description</span></span>|  
|-------------|-----------------|  
|[\<localIssuer>](localissuer.md)|<span data-ttu-id="d32f1-124">Especifica la dirección del emisor local del token y el enlace usado para comunicarse con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="d32f1-124">Specifies the address of the local issuer of the token and the binding used to communicate with the endpoint.</span></span>|  
|[\<issuerChannelBehaviors>](issuerchannelbehaviors-element.md)|<span data-ttu-id="d32f1-125">Especifica los comportamientos del punto de conexión que se va a usar al ponerse en contacto con un emisor local.</span><span class="sxs-lookup"><span data-stu-id="d32f1-125">Specifies the endpoint behaviors to use when contacting a local issuer.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d32f1-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d32f1-126">Parent Elements</span></span>  
  
|<span data-ttu-id="d32f1-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="d32f1-127">Element</span></span>|<span data-ttu-id="d32f1-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="d32f1-128">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="d32f1-129">Especifica las credenciales usadas para autenticar un cliente a un servicio.</span><span class="sxs-lookup"><span data-stu-id="d32f1-129">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d32f1-130">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d32f1-130">Remarks</span></span>  

 <span data-ttu-id="d32f1-131">Un token emitido es un tipo de credencial personalizado usado, por ejemplo, al autenticar con un servicio de token seguro (STS) en un escenario aliado.</span><span class="sxs-lookup"><span data-stu-id="d32f1-131">An issued token is a custom credential type used, for example, when authenticating with a Secure Token Service (STS) in a federated scenario.</span></span> <span data-ttu-id="d32f1-132">De forma predeterminada, el token es un token de SAML.</span><span class="sxs-lookup"><span data-stu-id="d32f1-132">By default, the token is a SAML token.</span></span> <span data-ttu-id="d32f1-133">Para obtener más información, vea [Federación y tokens emitidos](../../../wcf/feature-details/federation-and-issued-tokens.md), y [Federación y tokens emitidos](../../../wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="d32f1-133">For more information, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md), and [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="d32f1-134">Esta sección contiene los elementos utilizados para configurar un emisor local de tokens, o los comportamientos utilizados con un servicio de token seguro.</span><span class="sxs-lookup"><span data-stu-id="d32f1-134">This section contains the elements used to configure a local issuer of tokens, or behaviors used with an security token service.</span></span> <span data-ttu-id="d32f1-135">Para obtener instrucciones sobre cómo configurar un cliente para utilizar un emisor local, consulte [How to: Configure a local issuer](../../../wcf/feature-details/how-to-configure-a-local-issuer.md).</span><span class="sxs-lookup"><span data-stu-id="d32f1-135">For instructions on configuring a client to use a local issuer, see [How to: Configure a Local Issuer](../../../wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d32f1-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="d32f1-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.IssuedToken%2A>
- <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [<span data-ttu-id="d32f1-137">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="d32f1-137">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="d32f1-138">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="d32f1-138">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="d32f1-139">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="d32f1-139">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="d32f1-140">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="d32f1-140">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="d32f1-141">Procedimiento para crear un cliente federado</span><span class="sxs-lookup"><span data-stu-id="d32f1-141">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="d32f1-142">Procedimiento para configurar un emisor local</span><span class="sxs-lookup"><span data-stu-id="d32f1-142">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="d32f1-143">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="d32f1-143">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
