---
title: '&lt;resolución&gt;'
ms.date: 03/30/2017
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
ms.openlocfilehash: f29c34f53a8bdaee4b30c72bb5d764ae3935fe7a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltresolvergt"></a><span data-ttu-id="cff88-102">&lt;resolución&gt;</span><span class="sxs-lookup"><span data-stu-id="cff88-102">&lt;resolver&gt;</span></span>
<span data-ttu-id="cff88-103">Especifica una resolución del mismo nivel que se utiliza para resolver un id. de malla del mismo nivel como un conjunto de direcciones del nodo del mismo nivel que representa varios nodos que participan en la malla.</span><span class="sxs-lookup"><span data-stu-id="cff88-103">Specifies a peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>  
  
 <span data-ttu-id="cff88-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="cff88-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="cff88-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="cff88-105">\<bindings></span></span>  
<span data-ttu-id="cff88-106">\<netPeerBinding ></span><span class="sxs-lookup"><span data-stu-id="cff88-106">\<netPeerBinding></span></span>  
<span data-ttu-id="cff88-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="cff88-107">\<binding></span></span>  
<span data-ttu-id="cff88-108">\<resolución ></span><span class="sxs-lookup"><span data-stu-id="cff88-108">\<resolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cff88-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cff88-109">Syntax</span></span>  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"  
   referralPolicy="DoNotShare/Service/Share">  
</resolver>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cff88-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="cff88-110">Attributes and Elements</span></span>  
 <span data-ttu-id="cff88-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="cff88-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cff88-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="cff88-112">Attributes</span></span>  
  
|<span data-ttu-id="cff88-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="cff88-113">Attribute</span></span>|<span data-ttu-id="cff88-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="cff88-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="cff88-115">Una cadena que especifica si la instancia de la resolución del mismo nivel asociada con este servicio es específica del PNRP, una resolución personalizada o si se determina de manera automática.</span><span class="sxs-lookup"><span data-stu-id="cff88-115">A string that specifies whether the peer resolver instance associated with this service is either PNRP-specific, a custom resolver, or automatically determined.</span></span> <span data-ttu-id="cff88-116">Este atributo es del tipo <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span><span class="sxs-lookup"><span data-stu-id="cff88-116">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span></span>|  
|`referralPolicy`|<span data-ttu-id="cff88-117">Una cadena que especifica la manera en que las referencias se comparten entre pares.</span><span class="sxs-lookup"><span data-stu-id="cff88-117">A string that specifies the way referrals are shared among peers.</span></span> <span data-ttu-id="cff88-118">Este atributo es del tipo <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span><span class="sxs-lookup"><span data-stu-id="cff88-118">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cff88-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="cff88-119">Child Elements</span></span>  
  
|<span data-ttu-id="cff88-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="cff88-120">Element</span></span>|<span data-ttu-id="cff88-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="cff88-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cff88-122">\<encabezados ></span><span class="sxs-lookup"><span data-stu-id="cff88-122">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|<span data-ttu-id="cff88-123">Especifica la configuración concreta para un servicio de resolución del mismo nivel personalizado.</span><span class="sxs-lookup"><span data-stu-id="cff88-123">Specifies settings for a custom peer resolver service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cff88-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="cff88-124">Parent Elements</span></span>  
  
|<span data-ttu-id="cff88-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="cff88-125">Element</span></span>|<span data-ttu-id="cff88-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="cff88-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cff88-127">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="cff88-127">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="cff88-128">Define todas las funcionalidades de enlace de la [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="cff88-128">Defines all binding capabilities of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cff88-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cff88-129">Remarks</span></span>  
 <span data-ttu-id="cff88-130">Una resolución de nombres del mismo nivel es un servicio de descubrimiento utilizado por los canales del mismo nivel para buscar nodos del mismo nivel que participen en una malla del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="cff88-130">A peer name resolver is a discovery service used by peer channels to find peer nodes that participate in a peer mesh.</span></span> <span data-ttu-id="cff88-131">También se utiliza para "registrar" un nodo con una malla del mismo nivel, el mecanismo por el que se conoce el nodo del mismo nivel y está disponible en la malla del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="cff88-131">It is also used to "register" a node with a peer mesh, the mechanism by which the peer node becomes known and available from the peer mesh.</span></span> <span data-ttu-id="cff88-132">Para obtener más información sobre resoluciones del mismo nivel, consulte [resoluciones del mismo nivel](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md).</span><span class="sxs-lookup"><span data-stu-id="cff88-132">For more information on peer resolvers, see [Peer Resolvers](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cff88-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="cff88-133">See Also</span></span>  
 <xref:System.ServiceModel.PeerResolver>  
 <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>  
 <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>  
 <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>  
 <xref:System.ServiceModel.Configuration.PeerResolverElement>  
 [<span data-ttu-id="cff88-134">Resoluciones del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="cff88-134">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)  
 [<span data-ttu-id="cff88-135">Agregar a un solucionador personalizado a una aplicación de PeerChannel</span><span class="sxs-lookup"><span data-stu-id="cff88-135">Adding a Custom Resolver to a PeerChannel Application</span></span>](http://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419)
