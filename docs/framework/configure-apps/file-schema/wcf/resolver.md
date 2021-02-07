---
description: 'Más información acerca de: <resolver>'
title: <resolver>
ms.date: 03/30/2017
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
ms.openlocfilehash: 338f9342d1ef14f3d96dada17fb9f6d893c86bee
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683364"
---
# \<resolver>

<span data-ttu-id="aba35-102">Especifica una resolución del mismo nivel que se utiliza para resolver un id. de malla del mismo nivel como un conjunto de direcciones del nodo del mismo nivel que representa varios nodos que participan en la malla.</span><span class="sxs-lookup"><span data-stu-id="aba35-102">Specifies a peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<resolver>**  
  
## <a name="syntax"></a><span data-ttu-id="aba35-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aba35-103">Syntax</span></span>  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"
          referralPolicy="DoNotShare/Service/Share">
</resolver>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aba35-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="aba35-104">Attributes and Elements</span></span>  

 <span data-ttu-id="aba35-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="aba35-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aba35-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="aba35-106">Attributes</span></span>  
  
|<span data-ttu-id="aba35-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="aba35-107">Attribute</span></span>|<span data-ttu-id="aba35-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="aba35-108">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="aba35-109">Una cadena que especifica si la instancia de la resolución del mismo nivel asociada con este servicio es específica del PNRP, una resolución personalizada o si se determina de manera automática.</span><span class="sxs-lookup"><span data-stu-id="aba35-109">A string that specifies whether the peer resolver instance associated with this service is either PNRP-specific, a custom resolver, or automatically determined.</span></span> <span data-ttu-id="aba35-110">Este atributo es del tipo <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span><span class="sxs-lookup"><span data-stu-id="aba35-110">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span></span>|  
|`referralPolicy`|<span data-ttu-id="aba35-111">Una cadena que especifica la manera en que las referencias se comparten entre pares.</span><span class="sxs-lookup"><span data-stu-id="aba35-111">A string that specifies the way referrals are shared among peers.</span></span> <span data-ttu-id="aba35-112">Este atributo es del tipo <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span><span class="sxs-lookup"><span data-stu-id="aba35-112">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aba35-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="aba35-113">Child Elements</span></span>  
  
|<span data-ttu-id="aba35-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="aba35-114">Element</span></span>|<span data-ttu-id="aba35-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="aba35-115">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers.md)|<span data-ttu-id="aba35-116">Especifica la configuración concreta para un servicio de resolución del mismo nivel personalizado.</span><span class="sxs-lookup"><span data-stu-id="aba35-116">Specifies settings for a custom peer resolver service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aba35-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="aba35-117">Parent Elements</span></span>  
  
|<span data-ttu-id="aba35-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="aba35-118">Element</span></span>|<span data-ttu-id="aba35-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="aba35-119">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="aba35-120">Define todas las funciones de enlace de [\<netPeerTcpBinding>](netpeertcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="aba35-120">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aba35-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="aba35-121">Remarks</span></span>  

 <span data-ttu-id="aba35-122">Una resolución de nombres del mismo nivel es un servicio de descubrimiento utilizado por los canales del mismo nivel para buscar nodos del mismo nivel que participen en una malla del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="aba35-122">A peer name resolver is a discovery service used by peer channels to find peer nodes that participate in a peer mesh.</span></span> <span data-ttu-id="aba35-123">También se utiliza para "registrar" un nodo con una malla del mismo nivel, el mecanismo por el que se conoce el nodo del mismo nivel y está disponible en la malla del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="aba35-123">It is also used to "register" a node with a peer mesh, the mechanism by which the peer node becomes known and available from the peer mesh.</span></span> <span data-ttu-id="aba35-124">Para obtener más información sobre las resoluciones del mismo nivel, consulte [solucionadores del mismo nivel](../../../wcf/feature-details/peer-resolvers.md).</span><span class="sxs-lookup"><span data-stu-id="aba35-124">For more information on peer resolvers, see [Peer Resolvers](../../../wcf/feature-details/peer-resolvers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aba35-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="aba35-125">See also</span></span>

- <xref:System.ServiceModel.PeerResolver>
- <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>
- <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>
- <xref:System.ServiceModel.Configuration.PeerResolverElement>
- [<span data-ttu-id="aba35-126">Resoluciones del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="aba35-126">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="aba35-127">[Adición de una resolución personalizada a una aplicación PeerChannel](/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="aba35-127">[Adding a Custom Resolver to a PeerChannel Application](/previous-versions/ms730105(v=vs.90))</span></span>
