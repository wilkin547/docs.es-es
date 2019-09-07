---
title: <issuedToken>
ms.date: 03/30/2017
ms.assetid: b6eae4b7-a6cd-4e1a-b0f6-f407022550b0
ms.openlocfilehash: b5ab3c3ad070499d686ea74b9fd459e89f380cfa
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397961"
---
# <a name="issuedtoken"></a><span data-ttu-id="21795-101">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="21795-101">\<issuedToken></span></span>
<span data-ttu-id="21795-102">Especifica un token personalizado usado para autenticar un cliente en un servicio.</span><span class="sxs-lookup"><span data-stu-id="21795-102">Specifies a custom token used to authenticate a client to a service.</span></span>  
  
<span data-ttu-id="21795-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="21795-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="21795-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="21795-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="21795-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="21795-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="21795-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="21795-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="21795-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="21795-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="21795-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="21795-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="21795-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> issuedToken**</span><span class="sxs-lookup"><span data-stu-id="21795-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuedToken>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21795-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="21795-110">Syntax</span></span>  
  
```xml  
<issuedToken cacheIssuedTokens="Boolean"
             defaultKeyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"
             issuedTokenRenewalThresholdPercentage = "0 to 100"
             issuerChannelBehaviors="String"
             localIssuerChannelBehaviors="String"
             maxIssuedTokenCachingTime="TimeSpan">
</issuedToken>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="21795-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="21795-111">Attributes and Elements</span></span>  
 <span data-ttu-id="21795-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="21795-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="21795-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="21795-113">Attributes</span></span>  
  
|<span data-ttu-id="21795-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="21795-114">Attribute</span></span>|<span data-ttu-id="21795-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="21795-115">Description</span></span>|  
|---------------|-----------------|  
|`cacheIssuedTokens`|<span data-ttu-id="21795-116">Atributo booleano opcional que especifica si los tokens están almacenados en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="21795-116">Optional Boolean attribute that specifies whether tokens are cached.</span></span> <span data-ttu-id="21795-117">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="21795-117">The default is `true`.</span></span>|  
|`defaultKeyEntropyMode`|<span data-ttu-id="21795-118">Atributo de cadena opcional que especifica los valores aleatorios (entropías) que se usan para las operaciones del protocolo en enlace.</span><span class="sxs-lookup"><span data-stu-id="21795-118">Optional string attribute that specifies which random values (entropies) are used for handshake operations.</span></span> <span data-ttu-id="21795-119">Los valores incluyen `ClientEntropy`, `ServerEntropy` y `CombinedEntropy`. El valor predeterminado es `CombinedEntropy`.</span><span class="sxs-lookup"><span data-stu-id="21795-119">Values include `ClientEntropy`, `ServerEntropy`, and `CombinedEntropy`, The default is `CombinedEntropy`.</span></span> <span data-ttu-id="21795-120">Este atributo es del tipo <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.</span><span class="sxs-lookup"><span data-stu-id="21795-120">This attribute is of type <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.</span></span>|  
|`issuedTokenRenewalThresholdPercentage`|<span data-ttu-id="21795-121">Atributo de entero opcional que especifica el porcentaje de un intervalo de tiempo válido (proporcionado por el emisor del token) que puede pasar antes de que se renueve un token.</span><span class="sxs-lookup"><span data-stu-id="21795-121">Optional integer attribute that specifies the percentage of a valid time frame (supplied by the token issuer) that can pass before a token is renewed.</span></span> <span data-ttu-id="21795-122">Los valores van de 0 a 100.</span><span class="sxs-lookup"><span data-stu-id="21795-122">Values are from 0 to 100.</span></span> <span data-ttu-id="21795-123">El valor predeterminado es 60, que especifica el 60% de los pasos de tiempo antes de intentar una renovación.</span><span class="sxs-lookup"><span data-stu-id="21795-123">The default is 60, which specifies 60% of the time passes before a renewal is attempted.</span></span>|  
|`issuerChannelBehaviors`|<span data-ttu-id="21795-124">Atributo opcional que especifica los comportamientos del canal que se va a usar al comunicar con el emisor.</span><span class="sxs-lookup"><span data-stu-id="21795-124">Optional attribute that specifies the channel behaviors to use when communicating with the issuer.</span></span>|  
|`localIssuerChannelBehaviors`|<span data-ttu-id="21795-125">Atributo opcional que especifica los comportamientos del canal que se va a usar al comunicar con el emisor local.</span><span class="sxs-lookup"><span data-stu-id="21795-125">Optional attribute that specifies the channel behaviors to use when communicating with the local issuer.</span></span>|  
|`maxIssuedTokenCachingTime`|<span data-ttu-id="21795-126">Atributo Timespan opcional que especifica la duración que los tokens emitidos están almacenados en memoria caché cuando el emisor del token (un STS) no especifica una hora.</span><span class="sxs-lookup"><span data-stu-id="21795-126">Optional Timespan attribute that specifies the duration that issued tokens are cached when the token issuer (an STS) does not specify a time.</span></span> <span data-ttu-id="21795-127">El valor predeterminado es "10675199.02:48:05.4775807".</span><span class="sxs-lookup"><span data-stu-id="21795-127">The default is "10675199.02:48:05.4775807."</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="21795-128">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="21795-128">Child Elements</span></span>  
  
|<span data-ttu-id="21795-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="21795-129">Element</span></span>|<span data-ttu-id="21795-130">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="21795-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="21795-131">\<localIssuer></span><span class="sxs-lookup"><span data-stu-id="21795-131">\<localIssuer></span></span>](localissuer.md)|<span data-ttu-id="21795-132">Especifica la dirección del emisor local del token y el enlace usado para comunicarse con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="21795-132">Specifies the address of the local issuer of the token and the binding used to communicate with the endpoint.</span></span>|  
|[<span data-ttu-id="21795-133">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="21795-133">\<issuerChannelBehaviors></span></span>](issuerchannelbehaviors-element.md)|<span data-ttu-id="21795-134">Especifica los comportamientos del punto de conexión que se va a usar al ponerse en contacto con un emisor local.</span><span class="sxs-lookup"><span data-stu-id="21795-134">Specifies the endpoint behaviors to use when contacting a local issuer.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="21795-135">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="21795-135">Parent Elements</span></span>  
  
|<span data-ttu-id="21795-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="21795-136">Element</span></span>|<span data-ttu-id="21795-137">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="21795-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="21795-138">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="21795-138">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="21795-139">Especifica las credenciales usadas para autenticar un cliente a un servicio.</span><span class="sxs-lookup"><span data-stu-id="21795-139">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21795-140">Comentarios</span><span class="sxs-lookup"><span data-stu-id="21795-140">Remarks</span></span>  
 <span data-ttu-id="21795-141">Un token emitido es un tipo de credencial personalizado usado, por ejemplo, al autenticar con un servicio de token seguro (STS) en un escenario aliado.</span><span class="sxs-lookup"><span data-stu-id="21795-141">An issued token is a custom credential type used, for example, when authenticating with a Secure Token Service (STS) in a federated scenario.</span></span> <span data-ttu-id="21795-142">De forma predeterminada, el token es un token de SAML.</span><span class="sxs-lookup"><span data-stu-id="21795-142">By default, the token is a SAML token.</span></span> <span data-ttu-id="21795-143">Para obtener más información, vea [Federación y tokens emitidos](../../../wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="21795-143">For more information, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span> <span data-ttu-id="21795-144">y [Federación y tokens emitidos](../../../wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="21795-144">and [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="21795-145">Esta sección contiene los elementos utilizados para configurar un emisor local de tokens, o los comportamientos utilizados con un servicio de token seguro.</span><span class="sxs-lookup"><span data-stu-id="21795-145">This section contains the elements used to configure a local issuer of tokens, or behaviors used with an security token service.</span></span> <span data-ttu-id="21795-146">Para obtener instrucciones sobre cómo configurar un cliente para utilizar un emisor local, [consulte Cómo: Configurar un emisor](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)local.</span><span class="sxs-lookup"><span data-stu-id="21795-146">For instructions on configuring a client to use a local issuer, see [How to: Configure a Local Issuer](../../../wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21795-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="21795-147">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.IssuedToken%2A>
- <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [<span data-ttu-id="21795-148">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="21795-148">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="21795-149">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="21795-149">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="21795-150">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="21795-150">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="21795-151">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="21795-151">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="21795-152">Cómo: Creación de un cliente federado</span><span class="sxs-lookup"><span data-stu-id="21795-152">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="21795-153">Cómo: Configuración de un emisor local</span><span class="sxs-lookup"><span data-stu-id="21795-153">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="21795-154">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="21795-154">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
