---
title: '&lt;issuerChannelBehaviors&gt; (elemento)'
ms.date: 03/30/2017
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
ms.openlocfilehash: 49a149975e406376a00ddeb43fd30f4c4834a0a0
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146815"
---
# <a name="ltissuerchannelbehaviorsgt-element"></a><span data-ttu-id="bfed4-102">&lt;issuerChannelBehaviors&gt; (elemento)</span><span class="sxs-lookup"><span data-stu-id="bfed4-102">&lt;issuerChannelBehaviors&gt; Element</span></span>
<span data-ttu-id="bfed4-103">Contiene una colección de comportamientos de punto de conexión de cliente de Windows Communication Foundation (WCF) (definido en la configuración) que se usará al comunicarse con los servicios de Token de servicio especificado.</span><span class="sxs-lookup"><span data-stu-id="bfed4-103">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="bfed4-104">Los comportamientos definidos no pueden contener ninguno [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elementos.</span><span class="sxs-lookup"><span data-stu-id="bfed4-104">The defined behaviors cannot include any [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elements.</span></span>  
  
 <span data-ttu-id="bfed4-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="bfed4-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="bfed4-106">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="bfed4-106">\<behaviors></span></span>  
<span data-ttu-id="bfed4-107">sección endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="bfed4-107">endpointBehaviors section</span></span>  
<span data-ttu-id="bfed4-108">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="bfed4-108">\<behavior></span></span>  
<span data-ttu-id="bfed4-109">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="bfed4-109">\<clientCredentials></span></span>  
<span data-ttu-id="bfed4-110">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="bfed4-110">\<issuedToken></span></span>  
<span data-ttu-id="bfed4-111">\<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="bfed4-111">\<issuerChannelBehaviors></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfed4-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bfed4-112">Syntax</span></span>  
  
```xml  
<issuerChannelBehaviors>
  <add behaviorConfiguraton="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bfed4-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bfed4-113">Attributes and Elements</span></span>  
 <span data-ttu-id="bfed4-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="bfed4-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bfed4-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="bfed4-115">Attributes</span></span>  
 <span data-ttu-id="bfed4-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="bfed4-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bfed4-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bfed4-117">Child Elements</span></span>  
  
|<span data-ttu-id="bfed4-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="bfed4-118">Element</span></span>|<span data-ttu-id="bfed4-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="bfed4-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bfed4-120">\<add></span><span class="sxs-lookup"><span data-stu-id="bfed4-120">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-issuerchannelbehaviors.md)|<span data-ttu-id="bfed4-121">Agrega un comportamiento a la colección.</span><span class="sxs-lookup"><span data-stu-id="bfed4-121">Adds a behavior to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bfed4-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bfed4-122">Parent Elements</span></span>  
  
|<span data-ttu-id="bfed4-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="bfed4-123">Element</span></span>|<span data-ttu-id="bfed4-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="bfed4-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bfed4-125">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="bfed4-125">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="bfed4-126">Especifica un token personalizado usado para autenticar un cliente en un servicio.</span><span class="sxs-lookup"><span data-stu-id="bfed4-126">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bfed4-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bfed4-127">Remarks</span></span>  
 <span data-ttu-id="bfed4-128">Use este elemento cuando se deba utilizar un comportamiento (excepto los comportamientos que incluyen elementos `<clientCredentials>`) para comunicar con un servicio.</span><span class="sxs-lookup"><span data-stu-id="bfed4-128">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="bfed4-129">Por ejemplo, si un [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) debe incluirse el elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="bfed4-129">For example, if a [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) behavior element must be included.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfed4-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="bfed4-130">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>  
 [<span data-ttu-id="bfed4-131">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="bfed4-131">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="bfed4-132">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="bfed4-132">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="bfed4-133">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="bfed4-133">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="bfed4-134">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="bfed4-134">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="bfed4-135">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="bfed4-135">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="bfed4-136">Cómo: Crear a un cliente federado</span><span class="sxs-lookup"><span data-stu-id="bfed4-136">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="bfed4-137">Cómo: Configurar a un emisor Local</span><span class="sxs-lookup"><span data-stu-id="bfed4-137">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [<span data-ttu-id="bfed4-138">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="bfed4-138">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
