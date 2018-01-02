---
title: '&lt;add&gt; de &lt;issuerChannelBehaviors&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bf66b3d3b531ae41329aade6a416c330957d83c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltissuerchannelbehaviorsgt"></a><span data-ttu-id="71118-102">&lt;add&gt; de &lt;issuerChannelBehaviors&gt;</span><span class="sxs-lookup"><span data-stu-id="71118-102">&lt;add&gt; of &lt;issuerChannelBehaviors&gt;</span></span>
<span data-ttu-id="71118-103">Agrega un comportamiento del punto de conexión que se va a usar al comunicar con STS.</span><span class="sxs-lookup"><span data-stu-id="71118-103">Adds an endpoint behavior to be used when communicating with an STS.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="71118-104">Si cualquier comportamiento de punto de conexión contiene un [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elemento, se producirá una excepción.</span><span class="sxs-lookup"><span data-stu-id="71118-104">If any endpoint behavior contains a [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element, an exception will be thrown.</span></span>  
  
 <span data-ttu-id="71118-105">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="71118-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="71118-106">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="71118-106">\<behaviors></span></span>  
<span data-ttu-id="71118-107">sección endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="71118-107">endpointBehaviors section</span></span>  
<span data-ttu-id="71118-108">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="71118-108">\<behavior></span></span>  
<span data-ttu-id="71118-109">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="71118-109">\<clientCredentials></span></span>  
<span data-ttu-id="71118-110">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="71118-110">\<issuedToken></span></span>  
<span data-ttu-id="71118-111">\<issuerChannelBehaviors > elemento</span><span class="sxs-lookup"><span data-stu-id="71118-111">\<issuerChannelBehaviors> Element</span></span>  
<span data-ttu-id="71118-112">\<add></span><span class="sxs-lookup"><span data-stu-id="71118-112">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71118-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="71118-113">Syntax</span></span>  
  
```xml  
<add issuerAddress="string"  
     behaviorConfiguraton="string" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="71118-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="71118-114">Attributes and Elements</span></span>  
 <span data-ttu-id="71118-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="71118-115">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="71118-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="71118-116">Attributes</span></span>  
  
|<span data-ttu-id="71118-117">Atributo</span><span class="sxs-lookup"><span data-stu-id="71118-117">Attribute</span></span>|<span data-ttu-id="71118-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="71118-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="71118-119">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="71118-119">issuerAddress</span></span>|<span data-ttu-id="71118-120">El URI del emisor del token seguridad con el que se va a comunicar.</span><span class="sxs-lookup"><span data-stu-id="71118-120">The URI of the security token issuer to communicate with.</span></span>|  
|<span data-ttu-id="71118-121">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="71118-121">behaviorConfiguration</span></span>|<span data-ttu-id="71118-122">El nombre de un comportamiento del punto de conexión definido en el mismo archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="71118-122">The name of an endpoint behavior defined in the same configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="71118-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="71118-123">Child Elements</span></span>  
 <span data-ttu-id="71118-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="71118-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="71118-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="71118-125">Parent Elements</span></span>  
  
|<span data-ttu-id="71118-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="71118-126">Element</span></span>|<span data-ttu-id="71118-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="71118-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="71118-128">\<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="71118-128">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|<span data-ttu-id="71118-129">Contiene una colección de comportamientos del extremo del cliente de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] que se van a usar al comunicar con los servicios de token de servidor especificados.</span><span class="sxs-lookup"><span data-stu-id="71118-129">Contains a collection of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71118-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="71118-130">Remarks</span></span>  
 <span data-ttu-id="71118-131">`issuerAddress` contiene el URI del Servicio de token de seguridad con el que el cliente desea comunicarse.</span><span class="sxs-lookup"><span data-stu-id="71118-131">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="71118-132">`behaviorConfiguration` apunta a un comportamiento de extremo que la aplicación usa en los canales creados por [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] para obtener los tokens emitidos por los Servicios de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="71118-132">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] to get the issued tokens from the Security Token Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71118-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="71118-133">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>  
 [<span data-ttu-id="71118-134">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="71118-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="71118-135">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="71118-135">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="71118-136">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="71118-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="71118-137">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="71118-137">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="71118-138">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="71118-138">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="71118-139">Creación de un cliente federado</span><span class="sxs-lookup"><span data-stu-id="71118-139">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="71118-140">Configuración de un emisor local</span><span class="sxs-lookup"><span data-stu-id="71118-140">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [<span data-ttu-id="71118-141">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="71118-141">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="71118-142">\<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="71118-142">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)
