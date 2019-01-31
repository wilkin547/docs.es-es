---
title: <add> de <issuerChannelBehaviors>
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: 65c76cba696ae388d6184eaaa70a1f2f5a301e1c
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271803"
---
# <a name="add-of-issuerchannelbehaviors"></a><span data-ttu-id="9e135-102">\<Agregar > de \<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="9e135-102">\<add> of \<issuerChannelBehaviors></span></span>
<span data-ttu-id="9e135-103">Agrega un comportamiento del punto de conexión que se va a usar al comunicar con STS.</span><span class="sxs-lookup"><span data-stu-id="9e135-103">Adds an endpoint behavior to be used when communicating with an STS.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e135-104">Si cualquier comportamiento de extremo contiene un [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elemento, se producirá una excepción.</span><span class="sxs-lookup"><span data-stu-id="9e135-104">If any endpoint behavior contains a [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element, an exception will be thrown.</span></span>  
  
 <span data-ttu-id="9e135-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9e135-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="9e135-106">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="9e135-106">\<behaviors></span></span>  
<span data-ttu-id="9e135-107">sección endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="9e135-107">endpointBehaviors section</span></span>  
<span data-ttu-id="9e135-108">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="9e135-108">\<behavior></span></span>  
<span data-ttu-id="9e135-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="9e135-109">\<clientCredentials></span></span>  
<span data-ttu-id="9e135-110">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="9e135-110">\<issuedToken></span></span>  
<span data-ttu-id="9e135-111">\<issuerChannelBehaviors > elemento</span><span class="sxs-lookup"><span data-stu-id="9e135-111">\<issuerChannelBehaviors> Element</span></span>  
<span data-ttu-id="9e135-112">\<add></span><span class="sxs-lookup"><span data-stu-id="9e135-112">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e135-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9e135-113">Syntax</span></span>  
  
```xml  
<add issuerAddress="string"
     behaviorConfiguraton="string" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9e135-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9e135-114">Attributes and Elements</span></span>  
 <span data-ttu-id="9e135-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9e135-115">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9e135-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="9e135-116">Attributes</span></span>  
  
|<span data-ttu-id="9e135-117">Atributo</span><span class="sxs-lookup"><span data-stu-id="9e135-117">Attribute</span></span>|<span data-ttu-id="9e135-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="9e135-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9e135-119">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="9e135-119">issuerAddress</span></span>|<span data-ttu-id="9e135-120">El URI del emisor del token seguridad con el que se va a comunicar.</span><span class="sxs-lookup"><span data-stu-id="9e135-120">The URI of the security token issuer to communicate with.</span></span>|  
|<span data-ttu-id="9e135-121">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="9e135-121">behaviorConfiguration</span></span>|<span data-ttu-id="9e135-122">El nombre de un comportamiento del punto de conexión definido en el mismo archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="9e135-122">The name of an endpoint behavior defined in the same configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9e135-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9e135-123">Child Elements</span></span>  
 <span data-ttu-id="9e135-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9e135-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9e135-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9e135-125">Parent Elements</span></span>  
  
|<span data-ttu-id="9e135-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="9e135-126">Element</span></span>|<span data-ttu-id="9e135-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="9e135-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9e135-128">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="9e135-128">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|<span data-ttu-id="9e135-129">Contiene una colección de comportamientos de extremo de cliente de Windows Communication Foundation (WCF) que se usará al comunicarse con los servicios de Token de servicio especificado.</span><span class="sxs-lookup"><span data-stu-id="9e135-129">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e135-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9e135-130">Remarks</span></span>  
 <span data-ttu-id="9e135-131">`issuerAddress` contiene el URI del Servicio de token de seguridad con el que el cliente desea comunicarse.</span><span class="sxs-lookup"><span data-stu-id="9e135-131">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="9e135-132">`behaviorConfiguration` apunta a un comportamiento de extremo que utiliza la aplicación en los canales creados por Windows Communication Foundation (WCF) para obtener los tokens emitidos desde los servicios de Token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9e135-132">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by Windows Communication Foundation (WCF) to get the issued tokens from the Security Token Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e135-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e135-133">See also</span></span>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="9e135-134">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="9e135-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="9e135-135">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="9e135-135">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="9e135-136">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="9e135-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="9e135-137">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="9e135-137">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="9e135-138">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="9e135-138">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="9e135-139">Cómo: Crear a un cliente federado</span><span class="sxs-lookup"><span data-stu-id="9e135-139">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="9e135-140">Cómo: Configurar a un emisor Local</span><span class="sxs-lookup"><span data-stu-id="9e135-140">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="9e135-141">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="9e135-141">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="9e135-142">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="9e135-142">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)
