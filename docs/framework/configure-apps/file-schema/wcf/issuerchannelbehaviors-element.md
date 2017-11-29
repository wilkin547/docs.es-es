---
title: '&lt;issuerChannelBehaviors&gt; (elemento)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 051525738f0138955358587a8fd25272dfdb9d28
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltissuerchannelbehaviorsgt-element"></a><span data-ttu-id="3852e-102">&lt;issuerChannelBehaviors&gt; (elemento)</span><span class="sxs-lookup"><span data-stu-id="3852e-102">&lt;issuerChannelBehaviors&gt; Element</span></span>
<span data-ttu-id="3852e-103">Contiene una colección de comportamientos de extremo de cliente de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] (definidos en la configuración) que se va a usar al comunicar con los servicios de tokens de servicio especificados.</span><span class="sxs-lookup"><span data-stu-id="3852e-103">Contains a collection of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="3852e-104">Los comportamientos definidos no pueden contener ninguno [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elementos.</span><span class="sxs-lookup"><span data-stu-id="3852e-104">The defined behaviors cannot include any [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elements.</span></span>  
  
 <span data-ttu-id="3852e-105">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="3852e-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="3852e-106">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="3852e-106">\<behaviors></span></span>  
<span data-ttu-id="3852e-107">sección endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="3852e-107">endpointBehaviors section</span></span>  
<span data-ttu-id="3852e-108">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="3852e-108">\<behavior></span></span>  
<span data-ttu-id="3852e-109">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="3852e-109">\<clientCredentials></span></span>  
<span data-ttu-id="3852e-110">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="3852e-110">\<issuedToken></span></span>  
<span data-ttu-id="3852e-111">\<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="3852e-111">\<issuerChannelBehaviors></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3852e-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3852e-112">Syntax</span></span>  
  
```xml  
<issuerChannelBehaviors>  
      <add behaviorConfiguraton="string"  
                issuerAddress="string" />  
</issuerChannelBehaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3852e-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3852e-113">Attributes and Elements</span></span>  
 <span data-ttu-id="3852e-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3852e-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3852e-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="3852e-115">Attributes</span></span>  
 <span data-ttu-id="3852e-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3852e-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3852e-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3852e-117">Child Elements</span></span>  
  
|<span data-ttu-id="3852e-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="3852e-118">Element</span></span>|<span data-ttu-id="3852e-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="3852e-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3852e-120">\<add></span><span class="sxs-lookup"><span data-stu-id="3852e-120">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-issuerchannelbehaviors.md)|<span data-ttu-id="3852e-121">Agrega un comportamiento a la colección.</span><span class="sxs-lookup"><span data-stu-id="3852e-121">Adds a behavior to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3852e-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3852e-122">Parent Elements</span></span>  
  
|<span data-ttu-id="3852e-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="3852e-123">Element</span></span>|<span data-ttu-id="3852e-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="3852e-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3852e-125">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="3852e-125">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="3852e-126">Especifica un token personalizado usado para autenticar un cliente en un servicio.</span><span class="sxs-lookup"><span data-stu-id="3852e-126">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3852e-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3852e-127">Remarks</span></span>  
 <span data-ttu-id="3852e-128">Use este elemento cuando se deba utilizar un comportamiento (excepto los comportamientos que incluyen elementos `<clientCredentials>`) para comunicar con un servicio.</span><span class="sxs-lookup"><span data-stu-id="3852e-128">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="3852e-129">Por ejemplo, si un [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) se debe incluir el elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="3852e-129">For example, if a [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) behavior element must be included.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3852e-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="3852e-130">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>  
 [<span data-ttu-id="3852e-131">Autenticación e identidad de servicio</span><span class="sxs-lookup"><span data-stu-id="3852e-131">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="3852e-132">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="3852e-132">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="3852e-133">Federación y Tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="3852e-133">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="3852e-134">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="3852e-134">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="3852e-135">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="3852e-135">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="3852e-136">Cómo: crear un cliente federado</span><span class="sxs-lookup"><span data-stu-id="3852e-136">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="3852e-137">Cómo: configurar un emisor Local</span><span class="sxs-lookup"><span data-stu-id="3852e-137">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [<span data-ttu-id="3852e-138">Federación y Tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="3852e-138">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
