---
title: <custom>
ms.date: 03/30/2017
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
ms.openlocfilehash: b5cc522604fa7aca8ca6eae787520265b36fef6f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925953"
---
# <a name="custom"></a><span data-ttu-id="40b49-101">\<custom></span><span class="sxs-lookup"><span data-stu-id="40b49-101">\<custom></span></span>
<span data-ttu-id="40b49-102">Especifica la configuración concreta para un servicio de resolución del mismo nivel personalizado.</span><span class="sxs-lookup"><span data-stu-id="40b49-102">Specifies settings for a custom peer resolver service.</span></span>  
  
<span data-ttu-id="40b49-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="40b49-103">\<system.serviceModel></span></span>  
<span data-ttu-id="40b49-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="40b49-104">\<bindings></span></span>  
<span data-ttu-id="40b49-105">\<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="40b49-105">\<netPeerBinding></span></span>  
<span data-ttu-id="40b49-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="40b49-106">\<binding></span></span>  
<span data-ttu-id="40b49-107">\<resolver></span><span class="sxs-lookup"><span data-stu-id="40b49-107">\<resolver></span></span>  
<span data-ttu-id="40b49-108">\<custom></span><span class="sxs-lookup"><span data-stu-id="40b49-108">\<custom></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40b49-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="40b49-109">Syntax</span></span>  
  
```xml  
<custom address="Uri"
        resolverType="String">
  <headers/>
  <identity/>
</custom>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="40b49-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="40b49-110">Attributes and Elements</span></span>  
 <span data-ttu-id="40b49-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="40b49-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="40b49-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="40b49-112">Attributes</span></span>  
  
|<span data-ttu-id="40b49-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="40b49-113">Attribute</span></span>|<span data-ttu-id="40b49-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="40b49-114">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="40b49-115">Un URI que especifica la dirección de extremo del nodo del mismo nivel que hospeda el servicio de resolución del mismo nivel personalizado.</span><span class="sxs-lookup"><span data-stu-id="40b49-115">A URI that specifies the endpoint address of the peer node that hosts the custom peer resolver service.</span></span>|  
|`resolverType`|<span data-ttu-id="40b49-116">Una cadena que especifica el tipo de servicio de resolución del mismo nivel personalizado.</span><span class="sxs-lookup"><span data-stu-id="40b49-116">A string that specifies the type of the custom peer resolver service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="40b49-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="40b49-117">Child Elements</span></span>  
  
|<span data-ttu-id="40b49-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="40b49-118">Element</span></span>|<span data-ttu-id="40b49-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="40b49-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="40b49-120">\<identity></span><span class="sxs-lookup"><span data-stu-id="40b49-120">\<identity></span></span>](identity.md)|<span data-ttu-id="40b49-121">Especifica la identidad para las resoluciones del mismo nivel personalizadas configuradas con este elemento.</span><span class="sxs-lookup"><span data-stu-id="40b49-121">Specifies the identity for custom peer resolvers configured with this element.</span></span> <span data-ttu-id="40b49-122">Este elemento es del tipo <xref:System.ServiceModel.Configuration.IdentityElement>.</span><span class="sxs-lookup"><span data-stu-id="40b49-122">This element is of type <xref:System.ServiceModel.Configuration.IdentityElement>.</span></span>|  
|[<span data-ttu-id="40b49-123">\<headers></span><span class="sxs-lookup"><span data-stu-id="40b49-123">\<headers></span></span>](headers-element.md)|<span data-ttu-id="40b49-124">Una colección de encabezado de dirección usada para mensajes SOAP administrados por la resolución del mismo nivel personalizada.</span><span class="sxs-lookup"><span data-stu-id="40b49-124">A collection of address header used for SOAP messages handled by the custom peer resolver.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="40b49-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="40b49-125">Parent Elements</span></span>  
  
|<span data-ttu-id="40b49-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="40b49-126">Element</span></span>|<span data-ttu-id="40b49-127">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="40b49-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="40b49-128">\<resolver></span><span class="sxs-lookup"><span data-stu-id="40b49-128">\<resolver></span></span>](resolver.md)|<span data-ttu-id="40b49-129">Una resolución del mismo nivel que se usa para resolver un Id. de malla del mismo nivel como un conjunto de direcciones del nodo del mismo nivel que representa varios nodos que participan en la malla.</span><span class="sxs-lookup"><span data-stu-id="40b49-129">A peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40b49-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="40b49-130">Remarks</span></span>  
 <span data-ttu-id="40b49-131">Este elemento define la configuración básica para un servicio de la resolución del mismo nivel personalizado, incluso la dirección de extremo del igual que hospeda el servicio y cualquier configuración obligatoria concreta.</span><span class="sxs-lookup"><span data-stu-id="40b49-131">This element defines the basic settings for a custom peer resolver service, including the endpoint address of the peer hosting the service and any specific binding settings.</span></span> <span data-ttu-id="40b49-132">Para obtener más información sobre cómo crear un solucionador personalizado, vea [Agregar un solucionador personalizado a una aplicación de PeerChannel](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="40b49-132">For more information on creating a custom resolver, see [Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40b49-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="40b49-133">See also</span></span>

- <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>
- <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>
- <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>
- <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>
- [<span data-ttu-id="40b49-134">Resoluciones del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="40b49-134">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="40b49-135">[Adición de un solucionador personalizado a una aplicación de PeerChannel](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="40b49-135">[Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span></span>
