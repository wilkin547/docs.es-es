---
title: <resolver>
ms.date: 03/30/2017
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
ms.openlocfilehash: 0dc667f392595d895bd4f2773ab69777d7369446
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738743"
---
# <a name="resolver"></a><span data-ttu-id="00066-101">Solucionador de \<</span><span class="sxs-lookup"><span data-stu-id="00066-101">\<resolver></span></span>
<span data-ttu-id="00066-102">Especifica una resolución del mismo nivel que se utiliza para resolver un id. de malla del mismo nivel como un conjunto de direcciones del nodo del mismo nivel que representa varios nodos que participan en la malla.</span><span class="sxs-lookup"><span data-stu-id="00066-102">Specifies a peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>  
  
<span data-ttu-id="00066-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="00066-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="00066-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="00066-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="00066-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**enlaces**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="00066-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="00066-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netPeerTcpBinding**](netpeertcpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="00066-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)</span></span>\
<span data-ttu-id="00066-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**enlace** ></span><span class="sxs-lookup"><span data-stu-id="00066-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="00066-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**solucionador** ></span><span class="sxs-lookup"><span data-stu-id="00066-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<resolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00066-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="00066-109">Syntax</span></span>  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"
          referralPolicy="DoNotShare/Service/Share">
</resolver>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="00066-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="00066-110">Attributes and Elements</span></span>  
 <span data-ttu-id="00066-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="00066-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="00066-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="00066-112">Attributes</span></span>  
  
|<span data-ttu-id="00066-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="00066-113">Attribute</span></span>|<span data-ttu-id="00066-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="00066-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="00066-115">Una cadena que especifica si la instancia de la resolución del mismo nivel asociada con este servicio es específica del PNRP, una resolución personalizada o si se determina de manera automática.</span><span class="sxs-lookup"><span data-stu-id="00066-115">A string that specifies whether the peer resolver instance associated with this service is either PNRP-specific, a custom resolver, or automatically determined.</span></span> <span data-ttu-id="00066-116">Este atributo es del tipo <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span><span class="sxs-lookup"><span data-stu-id="00066-116">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span></span>|  
|`referralPolicy`|<span data-ttu-id="00066-117">Una cadena que especifica la manera en que las referencias se comparten entre pares.</span><span class="sxs-lookup"><span data-stu-id="00066-117">A string that specifies the way referrals are shared among peers.</span></span> <span data-ttu-id="00066-118">Este atributo es del tipo <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span><span class="sxs-lookup"><span data-stu-id="00066-118">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="00066-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="00066-119">Child Elements</span></span>  
  
|<span data-ttu-id="00066-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="00066-120">Element</span></span>|<span data-ttu-id="00066-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="00066-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="00066-122">\<encabezados ></span><span class="sxs-lookup"><span data-stu-id="00066-122">\<headers></span></span>](headers.md)|<span data-ttu-id="00066-123">Especifica la configuración concreta para un servicio de resolución del mismo nivel personalizado.</span><span class="sxs-lookup"><span data-stu-id="00066-123">Specifies settings for a custom peer resolver service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="00066-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="00066-124">Parent Elements</span></span>  
  
|<span data-ttu-id="00066-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="00066-125">Element</span></span>|<span data-ttu-id="00066-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="00066-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="00066-127">\<> de enlace</span><span class="sxs-lookup"><span data-stu-id="00066-127">\<binding></span></span>](bindings.md)|<span data-ttu-id="00066-128">Define todas las funciones de enlace del [\<netPeerTcpBinding >](netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="00066-128">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00066-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="00066-129">Remarks</span></span>  
 <span data-ttu-id="00066-130">Una resolución de nombres del mismo nivel es un servicio de descubrimiento utilizado por los canales del mismo nivel para buscar nodos del mismo nivel que participen en una malla del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="00066-130">A peer name resolver is a discovery service used by peer channels to find peer nodes that participate in a peer mesh.</span></span> <span data-ttu-id="00066-131">También se utiliza para "registrar" un nodo con una malla del mismo nivel, el mecanismo por el que se conoce el nodo del mismo nivel y está disponible en la malla del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="00066-131">It is also used to "register" a node with a peer mesh, the mechanism by which the peer node becomes known and available from the peer mesh.</span></span> <span data-ttu-id="00066-132">Para obtener más información sobre las resoluciones del mismo nivel, consulte [solucionadores del mismo nivel](../../../wcf/feature-details/peer-resolvers.md).</span><span class="sxs-lookup"><span data-stu-id="00066-132">For more information on peer resolvers, see [Peer Resolvers](../../../wcf/feature-details/peer-resolvers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00066-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="00066-133">See also</span></span>

- <xref:System.ServiceModel.PeerResolver>
- <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>
- <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>
- <xref:System.ServiceModel.Configuration.PeerResolverElement>
- [<span data-ttu-id="00066-134">Resoluciones del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="00066-134">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="00066-135">[Adición de un solucionador personalizado a una aplicación de PeerChannel](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="00066-135">[Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span></span>
