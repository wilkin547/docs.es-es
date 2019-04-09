---
title: <issuedToken>
ms.date: 03/30/2017
ms.assetid: b6eae4b7-a6cd-4e1a-b0f6-f407022550b0
ms.openlocfilehash: 83061b283c9430af7bcda9cbc832811fa805ed4c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59104954"
---
# <a name="issuedtoken"></a><span data-ttu-id="13447-101">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="13447-101">\<issuedToken></span></span>
<span data-ttu-id="13447-102">Especifica un token personalizado usado para autenticar un cliente en un servicio.</span><span class="sxs-lookup"><span data-stu-id="13447-102">Specifies a custom token used to authenticate a client to a service.</span></span>  
  
 <span data-ttu-id="13447-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="13447-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="13447-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="13447-104">\<behaviors></span></span>  
<span data-ttu-id="13447-105">sección endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="13447-105">endpointBehaviors section</span></span>  
<span data-ttu-id="13447-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="13447-106">\<behavior></span></span>  
<span data-ttu-id="13447-107">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="13447-107">\<clientCredentials></span></span>  
<span data-ttu-id="13447-108">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="13447-108">\<issuedToken></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13447-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="13447-109">Syntax</span></span>  
  
```xml  
<issuedToken cacheIssuedTokens="Boolean"
             defaultKeyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"
             issuedTokenRenewalThresholdPercentage = "0 to 100"
             issuerChannelBehaviors="String"
             localIssuerChannelBehaviors="String"
             maxIssuedTokenCachingTime="TimeSpan">
</issuedToken>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="13447-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="13447-110">Attributes and Elements</span></span>  
 <span data-ttu-id="13447-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="13447-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="13447-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="13447-112">Attributes</span></span>  
  
|<span data-ttu-id="13447-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="13447-113">Attribute</span></span>|<span data-ttu-id="13447-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="13447-114">Description</span></span>|  
|---------------|-----------------|  
|`cacheIssuedTokens`|<span data-ttu-id="13447-115">Atributo booleano opcional que especifica si los tokens están almacenados en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="13447-115">Optional Boolean attribute that specifies whether tokens are cached.</span></span> <span data-ttu-id="13447-116">De manera predeterminada, es `true`.</span><span class="sxs-lookup"><span data-stu-id="13447-116">The default is `true`.</span></span>|  
|`defaultKeyEntropyMode`|<span data-ttu-id="13447-117">Atributo de cadena opcional que especifica los valores aleatorios (entropías) que se usan para las operaciones del protocolo en enlace.</span><span class="sxs-lookup"><span data-stu-id="13447-117">Optional string attribute that specifies which random values (entropies) are used for handshake operations.</span></span> <span data-ttu-id="13447-118">Los valores incluyen `ClientEntropy`, `ServerEntropy` y `CombinedEntropy`. El valor predeterminado es `CombinedEntropy`.</span><span class="sxs-lookup"><span data-stu-id="13447-118">Values include `ClientEntropy`, `ServerEntropy`, and `CombinedEntropy`, The default is `CombinedEntropy`.</span></span> <span data-ttu-id="13447-119">Este atributo es del tipo <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.</span><span class="sxs-lookup"><span data-stu-id="13447-119">This attribute is of type <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.</span></span>|  
|`issuedTokenRenewalThresholdPercentage`|<span data-ttu-id="13447-120">Atributo de entero opcional que especifica el porcentaje de un intervalo de tiempo válido (proporcionado por el emisor del token) que puede pasar antes de que se renueve un token.</span><span class="sxs-lookup"><span data-stu-id="13447-120">Optional integer attribute that specifies the percentage of a valid time frame (supplied by the token issuer) that can pass before a token is renewed.</span></span> <span data-ttu-id="13447-121">Los valores van de 0 a 100.</span><span class="sxs-lookup"><span data-stu-id="13447-121">Values are from 0 to 100.</span></span> <span data-ttu-id="13447-122">El valor predeterminado es 60, que especifica el 60% de los pasos de tiempo antes de intentar una renovación.</span><span class="sxs-lookup"><span data-stu-id="13447-122">The default is 60, which specifies 60% of the time passes before a renewal is attempted.</span></span>|  
|`issuerChannelBehaviors`|<span data-ttu-id="13447-123">Atributo opcional que especifica los comportamientos del canal que se va a usar al comunicar con el emisor.</span><span class="sxs-lookup"><span data-stu-id="13447-123">Optional attribute that specifies the channel behaviors to use when communicating with the issuer.</span></span>|  
|`localIssuerChannelBehaviors`|<span data-ttu-id="13447-124">Atributo opcional que especifica los comportamientos del canal que se va a usar al comunicar con el emisor local.</span><span class="sxs-lookup"><span data-stu-id="13447-124">Optional attribute that specifies the channel behaviors to use when communicating with the local issuer.</span></span>|  
|`maxIssuedTokenCachingTime`|<span data-ttu-id="13447-125">Atributo Timespan opcional que especifica la duración que los tokens emitidos están almacenados en memoria caché cuando el emisor del token (un STS) no especifica una hora.</span><span class="sxs-lookup"><span data-stu-id="13447-125">Optional Timespan attribute that specifies the duration that issued tokens are cached when the token issuer (an STS) does not specify a time.</span></span> <span data-ttu-id="13447-126">El valor predeterminado es "10675199.02:48:05.4775807".</span><span class="sxs-lookup"><span data-stu-id="13447-126">The default is "10675199.02:48:05.4775807."</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="13447-127">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="13447-127">Child Elements</span></span>  
  
|<span data-ttu-id="13447-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="13447-128">Element</span></span>|<span data-ttu-id="13447-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="13447-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="13447-130">\<localIssuer></span><span class="sxs-lookup"><span data-stu-id="13447-130">\<localIssuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md)|<span data-ttu-id="13447-131">Especifica la dirección del emisor local del token y el enlace usado para comunicarse con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="13447-131">Specifies the address of the local issuer of the token and the binding used to communicate with the endpoint.</span></span>|  
|[<span data-ttu-id="13447-132">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="13447-132">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|<span data-ttu-id="13447-133">Especifica los comportamientos del punto de conexión que se va a usar al ponerse en contacto con un emisor local.</span><span class="sxs-lookup"><span data-stu-id="13447-133">Specifies the endpoint behaviors to use when contacting a local issuer.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="13447-134">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="13447-134">Parent Elements</span></span>  
  
|<span data-ttu-id="13447-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="13447-135">Element</span></span>|<span data-ttu-id="13447-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="13447-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="13447-137">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="13447-137">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="13447-138">Especifica las credenciales usadas para autenticar un cliente a un servicio.</span><span class="sxs-lookup"><span data-stu-id="13447-138">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13447-139">Comentarios</span><span class="sxs-lookup"><span data-stu-id="13447-139">Remarks</span></span>  
 <span data-ttu-id="13447-140">Un token emitido es un tipo de credencial personalizado usado, por ejemplo, al autenticar con un servicio de token seguro (STS) en un escenario aliado.</span><span class="sxs-lookup"><span data-stu-id="13447-140">An issued token is a custom credential type used, for example, when authenticating with a Secure Token Service (STS) in a federated scenario.</span></span> <span data-ttu-id="13447-141">De forma predeterminada, el token es un token de SAML.</span><span class="sxs-lookup"><span data-stu-id="13447-141">By default, the token is a SAML token.</span></span> <span data-ttu-id="13447-142">Para obtener más información, consulte [federación y Tokens emitidos](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="13447-142">For more information, see [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span> <span data-ttu-id="13447-143">y [federación y Tokens emitidos](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="13447-143">and [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="13447-144">Esta sección contiene los elementos utilizados para configurar un emisor local de tokens, o los comportamientos utilizados con un servicio de token seguro.</span><span class="sxs-lookup"><span data-stu-id="13447-144">This section contains the elements used to configure a local issuer of tokens, or behaviors used with an security token service.</span></span> <span data-ttu-id="13447-145">Para que obtener instrucciones sobre cómo configurar un cliente para utilizar un emisor local, vea [Cómo: Configurar un emisor Local](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span><span class="sxs-lookup"><span data-stu-id="13447-145">For instructions on configuring a client to use a local issuer, see [How to: Configure a Local Issuer](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13447-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="13447-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.IssuedToken%2A>
- <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [<span data-ttu-id="13447-147">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="13447-147">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="13447-148">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="13447-148">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="13447-149">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="13447-149">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="13447-150">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="13447-150">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="13447-151">Filtrar para crear un cliente federado</span><span class="sxs-lookup"><span data-stu-id="13447-151">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="13447-152">Filtrar para configurar un emisor local</span><span class="sxs-lookup"><span data-stu-id="13447-152">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="13447-153">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="13447-153">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
