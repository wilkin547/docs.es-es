---
title: <resolver>
ms.date: 03/30/2017
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
ms.openlocfilehash: f3d4b049afe55fb9fb80cbad56c49e8ec13e60db
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2019
ms.locfileid: "55758747"
---
# <a name="resolver"></a><span data-ttu-id="d9ec3-101">\<resolver></span><span class="sxs-lookup"><span data-stu-id="d9ec3-101">\<resolver></span></span>
<span data-ttu-id="d9ec3-102">Especifica una resolución del mismo nivel que se utiliza para resolver un id. de malla del mismo nivel como un conjunto de direcciones del nodo del mismo nivel que representa varios nodos que participan en la malla.</span><span class="sxs-lookup"><span data-stu-id="d9ec3-102">Specifies a peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>  
  
 <span data-ttu-id="d9ec3-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d9ec3-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="d9ec3-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="d9ec3-104">\<bindings></span></span>  
<span data-ttu-id="d9ec3-105">\<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="d9ec3-105">\<netPeerBinding></span></span>  
<span data-ttu-id="d9ec3-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="d9ec3-106">\<binding></span></span>  
<span data-ttu-id="d9ec3-107">\<resolver></span><span class="sxs-lookup"><span data-stu-id="d9ec3-107">\<resolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9ec3-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d9ec3-108">Syntax</span></span>  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"
          referralPolicy="DoNotShare/Service/Share">
</resolver>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d9ec3-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d9ec3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d9ec3-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d9ec3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d9ec3-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="d9ec3-111">Attributes</span></span>  
  
|<span data-ttu-id="d9ec3-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="d9ec3-112">Attribute</span></span>|<span data-ttu-id="d9ec3-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="d9ec3-113">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="d9ec3-114">Una cadena que especifica si la instancia de la resolución del mismo nivel asociada con este servicio es específica del PNRP, una resolución personalizada o si se determina de manera automática.</span><span class="sxs-lookup"><span data-stu-id="d9ec3-114">A string that specifies whether the peer resolver instance associated with this service is either PNRP-specific, a custom resolver, or automatically determined.</span></span> <span data-ttu-id="d9ec3-115">Este atributo es del tipo <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span><span class="sxs-lookup"><span data-stu-id="d9ec3-115">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span></span>|  
|`referralPolicy`|<span data-ttu-id="d9ec3-116">Una cadena que especifica la manera en que las referencias se comparten entre pares.</span><span class="sxs-lookup"><span data-stu-id="d9ec3-116">A string that specifies the way referrals are shared among peers.</span></span> <span data-ttu-id="d9ec3-117">Este atributo es del tipo <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span><span class="sxs-lookup"><span data-stu-id="d9ec3-117">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d9ec3-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d9ec3-118">Child Elements</span></span>  
  
|<span data-ttu-id="d9ec3-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="d9ec3-119">Element</span></span>|<span data-ttu-id="d9ec3-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="d9ec3-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d9ec3-121">\<headers></span><span class="sxs-lookup"><span data-stu-id="d9ec3-121">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|<span data-ttu-id="d9ec3-122">Especifica la configuración concreta para un servicio de resolución del mismo nivel personalizado.</span><span class="sxs-lookup"><span data-stu-id="d9ec3-122">Specifies settings for a custom peer resolver service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d9ec3-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d9ec3-123">Parent Elements</span></span>  
  
|<span data-ttu-id="d9ec3-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="d9ec3-124">Element</span></span>|<span data-ttu-id="d9ec3-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="d9ec3-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d9ec3-126">\<binding></span><span class="sxs-lookup"><span data-stu-id="d9ec3-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="d9ec3-127">Define todas las capacidades de enlace de la [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="d9ec3-127">Defines all binding capabilities of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9ec3-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d9ec3-128">Remarks</span></span>  
 <span data-ttu-id="d9ec3-129">Una resolución de nombres del mismo nivel es un servicio de descubrimiento utilizado por los canales del mismo nivel para buscar nodos del mismo nivel que participen en una malla del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="d9ec3-129">A peer name resolver is a discovery service used by peer channels to find peer nodes that participate in a peer mesh.</span></span> <span data-ttu-id="d9ec3-130">También se utiliza para "registrar" un nodo con una malla del mismo nivel, el mecanismo por el que se conoce el nodo del mismo nivel y está disponible en la malla del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="d9ec3-130">It is also used to "register" a node with a peer mesh, the mechanism by which the peer node becomes known and available from the peer mesh.</span></span> <span data-ttu-id="d9ec3-131">Para obtener más información sobre resoluciones del mismo nivel, consulte [resoluciones del mismo nivel](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md).</span><span class="sxs-lookup"><span data-stu-id="d9ec3-131">For more information on peer resolvers, see [Peer Resolvers](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9ec3-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9ec3-132">See also</span></span>
- <xref:System.ServiceModel.PeerResolver>
- <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>
- <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>
- <xref:System.ServiceModel.Configuration.PeerResolverElement>
- [<span data-ttu-id="d9ec3-133">Resoluciones del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="d9ec3-133">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="d9ec3-134">[Adición de un solucionador personalizado a una aplicación PeerChannel](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="d9ec3-134">[Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span></span>
