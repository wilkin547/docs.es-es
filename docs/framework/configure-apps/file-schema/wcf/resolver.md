---
title: "&lt;resolución&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fc6e919600fbea15937a61eaa65299b3a372caaf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltresolvergt"></a><span data-ttu-id="fbfa0-102">&lt;resolución&gt;</span><span class="sxs-lookup"><span data-stu-id="fbfa0-102">&lt;resolver&gt;</span></span>
<span data-ttu-id="fbfa0-103">Especifica una resolución del mismo nivel que se utiliza para resolver un id. de malla del mismo nivel como un conjunto de direcciones del nodo del mismo nivel que representa varios nodos que participan en la malla.</span><span class="sxs-lookup"><span data-stu-id="fbfa0-103">Specifies a peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>  
  
 <span data-ttu-id="fbfa0-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="fbfa0-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="fbfa0-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="fbfa0-105">\<bindings></span></span>  
<span data-ttu-id="fbfa0-106">\<netPeerBinding ></span><span class="sxs-lookup"><span data-stu-id="fbfa0-106">\<netPeerBinding></span></span>  
<span data-ttu-id="fbfa0-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="fbfa0-107">\<binding></span></span>  
<span data-ttu-id="fbfa0-108">\<resolución ></span><span class="sxs-lookup"><span data-stu-id="fbfa0-108">\<resolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbfa0-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fbfa0-109">Syntax</span></span>  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"  
   referralPolicy="DoNotShare/Service/Share">  
</resolver>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fbfa0-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fbfa0-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fbfa0-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fbfa0-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fbfa0-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="fbfa0-112">Attributes</span></span>  
  
|<span data-ttu-id="fbfa0-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="fbfa0-113">Attribute</span></span>|<span data-ttu-id="fbfa0-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="fbfa0-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="fbfa0-115">Una cadena que especifica si la instancia de la resolución del mismo nivel asociada con este servicio es específica del PNRP, una resolución personalizada o si se determina de manera automática.</span><span class="sxs-lookup"><span data-stu-id="fbfa0-115">A string that specifies whether the peer resolver instance associated with this service is either PNRP-specific, a custom resolver, or automatically determined.</span></span> <span data-ttu-id="fbfa0-116">Este atributo es del tipo <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span><span class="sxs-lookup"><span data-stu-id="fbfa0-116">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span></span>|  
|`referralPolicy`|<span data-ttu-id="fbfa0-117">Una cadena que especifica la manera en que las referencias se comparten entre pares.</span><span class="sxs-lookup"><span data-stu-id="fbfa0-117">A string that specifies the way referrals are shared among peers.</span></span> <span data-ttu-id="fbfa0-118">Este atributo es del tipo <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span><span class="sxs-lookup"><span data-stu-id="fbfa0-118">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fbfa0-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fbfa0-119">Child Elements</span></span>  
  
|<span data-ttu-id="fbfa0-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="fbfa0-120">Element</span></span>|<span data-ttu-id="fbfa0-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="fbfa0-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fbfa0-122">\<encabezados ></span><span class="sxs-lookup"><span data-stu-id="fbfa0-122">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|<span data-ttu-id="fbfa0-123">Especifica la configuración concreta para un servicio de resolución del mismo nivel personalizado.</span><span class="sxs-lookup"><span data-stu-id="fbfa0-123">Specifies settings for a custom peer resolver service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fbfa0-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fbfa0-124">Parent Elements</span></span>  
  
|<span data-ttu-id="fbfa0-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="fbfa0-125">Element</span></span>|<span data-ttu-id="fbfa0-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="fbfa0-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fbfa0-127">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="fbfa0-127">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="fbfa0-128">Define todas las funcionalidades de enlace de la [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="fbfa0-128">Defines all binding capabilities of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fbfa0-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fbfa0-129">Remarks</span></span>  
 <span data-ttu-id="fbfa0-130">Una resolución de nombres del mismo nivel es un servicio de descubrimiento utilizado por los canales del mismo nivel para buscar nodos del mismo nivel que participen en una malla del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="fbfa0-130">A peer name resolver is a discovery service used by peer channels to find peer nodes that participate in a peer mesh.</span></span> <span data-ttu-id="fbfa0-131">También se utiliza para "registrar" un nodo con una malla del mismo nivel, el mecanismo por el que se conoce el nodo del mismo nivel y está disponible en la malla del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="fbfa0-131">It is also used to "register" a node with a peer mesh, the mechanism by which the peer node becomes known and available from the peer mesh.</span></span> <span data-ttu-id="fbfa0-132">Para obtener más información sobre resoluciones del mismo nivel, consulte [resoluciones del mismo nivel](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md).</span><span class="sxs-lookup"><span data-stu-id="fbfa0-132">For more information on peer resolvers, see [Peer Resolvers](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbfa0-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="fbfa0-133">See Also</span></span>  
 <xref:System.ServiceModel.PeerResolver>  
 <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>  
 <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>  
 <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>  
 <xref:System.ServiceModel.Configuration.PeerResolverElement>  
 [<span data-ttu-id="fbfa0-134">Resoluciones del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="fbfa0-134">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)  
 [<span data-ttu-id="fbfa0-135">Agregar a un solucionador personalizado a una aplicación de PeerChannel</span><span class="sxs-lookup"><span data-stu-id="fbfa0-135">Adding a Custom Resolver to a PeerChannel Application</span></span>](http://msdn.microsoft.com/en-us/12aa3787-2962-439c-ad27-46523c8b0419)
