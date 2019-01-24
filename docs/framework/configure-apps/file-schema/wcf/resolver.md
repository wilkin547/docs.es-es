---
title: '&lt;resolver&gt;'
ms.date: 03/30/2017
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
ms.openlocfilehash: 2a3e0de2bb5d2ed022f53aa5e498f338eaf56ca8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54578606"
---
# <a name="ltresolvergt"></a><span data-ttu-id="42592-102">&lt;resolver&gt;</span><span class="sxs-lookup"><span data-stu-id="42592-102">&lt;resolver&gt;</span></span>
<span data-ttu-id="42592-103">Especifica una resolución del mismo nivel que se utiliza para resolver un id. de malla del mismo nivel como un conjunto de direcciones del nodo del mismo nivel que representa varios nodos que participan en la malla.</span><span class="sxs-lookup"><span data-stu-id="42592-103">Specifies a peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>  
  
 <span data-ttu-id="42592-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="42592-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="42592-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="42592-105">\<bindings></span></span>  
<span data-ttu-id="42592-106">\<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="42592-106">\<netPeerBinding></span></span>  
<span data-ttu-id="42592-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="42592-107">\<binding></span></span>  
<span data-ttu-id="42592-108">\<resolver></span><span class="sxs-lookup"><span data-stu-id="42592-108">\<resolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42592-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42592-109">Syntax</span></span>  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"
          referralPolicy="DoNotShare/Service/Share">
</resolver>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="42592-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="42592-110">Attributes and Elements</span></span>  
 <span data-ttu-id="42592-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="42592-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="42592-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="42592-112">Attributes</span></span>  
  
|<span data-ttu-id="42592-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="42592-113">Attribute</span></span>|<span data-ttu-id="42592-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="42592-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="42592-115">Una cadena que especifica si la instancia de la resolución del mismo nivel asociada con este servicio es específica del PNRP, una resolución personalizada o si se determina de manera automática.</span><span class="sxs-lookup"><span data-stu-id="42592-115">A string that specifies whether the peer resolver instance associated with this service is either PNRP-specific, a custom resolver, or automatically determined.</span></span> <span data-ttu-id="42592-116">Este atributo es del tipo <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span><span class="sxs-lookup"><span data-stu-id="42592-116">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span></span>|  
|`referralPolicy`|<span data-ttu-id="42592-117">Una cadena que especifica la manera en que las referencias se comparten entre pares.</span><span class="sxs-lookup"><span data-stu-id="42592-117">A string that specifies the way referrals are shared among peers.</span></span> <span data-ttu-id="42592-118">Este atributo es del tipo <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span><span class="sxs-lookup"><span data-stu-id="42592-118">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="42592-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="42592-119">Child Elements</span></span>  
  
|<span data-ttu-id="42592-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="42592-120">Element</span></span>|<span data-ttu-id="42592-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="42592-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="42592-122">\<headers></span><span class="sxs-lookup"><span data-stu-id="42592-122">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|<span data-ttu-id="42592-123">Especifica la configuración concreta para un servicio de resolución del mismo nivel personalizado.</span><span class="sxs-lookup"><span data-stu-id="42592-123">Specifies settings for a custom peer resolver service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="42592-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="42592-124">Parent Elements</span></span>  
  
|<span data-ttu-id="42592-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="42592-125">Element</span></span>|<span data-ttu-id="42592-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="42592-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="42592-127">\<binding></span><span class="sxs-lookup"><span data-stu-id="42592-127">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="42592-128">Define todas las capacidades de enlace de la [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="42592-128">Defines all binding capabilities of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42592-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="42592-129">Remarks</span></span>  
 <span data-ttu-id="42592-130">Una resolución de nombres del mismo nivel es un servicio de descubrimiento utilizado por los canales del mismo nivel para buscar nodos del mismo nivel que participen en una malla del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="42592-130">A peer name resolver is a discovery service used by peer channels to find peer nodes that participate in a peer mesh.</span></span> <span data-ttu-id="42592-131">También se utiliza para "registrar" un nodo con una malla del mismo nivel, el mecanismo por el que se conoce el nodo del mismo nivel y está disponible en la malla del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="42592-131">It is also used to "register" a node with a peer mesh, the mechanism by which the peer node becomes known and available from the peer mesh.</span></span> <span data-ttu-id="42592-132">Para obtener más información sobre resoluciones del mismo nivel, consulte [resoluciones del mismo nivel](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md).</span><span class="sxs-lookup"><span data-stu-id="42592-132">For more information on peer resolvers, see [Peer Resolvers](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42592-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="42592-133">See also</span></span>
- <xref:System.ServiceModel.PeerResolver>
- <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>
- <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>
- <xref:System.ServiceModel.Configuration.PeerResolverElement>
- [<span data-ttu-id="42592-134">Resoluciones del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="42592-134">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
- [<span data-ttu-id="42592-135">Adición de un solucionador personalizado a una aplicación PeerChannel</span><span class="sxs-lookup"><span data-stu-id="42592-135">Adding a Custom Resolver to a PeerChannel Application</span></span>](https://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419)
