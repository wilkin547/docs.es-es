---
title: '&lt;custom&gt;'
ms.date: 03/30/2017
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
ms.openlocfilehash: 5180b8866d8b0155a8683ab9cb6135c26f696929
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54734992"
---
# <a name="ltcustomgt"></a><span data-ttu-id="aeb89-102">&lt;custom&gt;</span><span class="sxs-lookup"><span data-stu-id="aeb89-102">&lt;custom&gt;</span></span>
<span data-ttu-id="aeb89-103">Especifica la configuración concreta para un servicio de resolución del mismo nivel personalizado.</span><span class="sxs-lookup"><span data-stu-id="aeb89-103">Specifies settings for a custom peer resolver service.</span></span>  
  
<span data-ttu-id="aeb89-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="aeb89-104">\<system.serviceModel></span></span>  
<span data-ttu-id="aeb89-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="aeb89-105">\<bindings></span></span>  
<span data-ttu-id="aeb89-106">\<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="aeb89-106">\<netPeerBinding></span></span>  
<span data-ttu-id="aeb89-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="aeb89-107">\<binding></span></span>  
<span data-ttu-id="aeb89-108">\<resolver></span><span class="sxs-lookup"><span data-stu-id="aeb89-108">\<resolver></span></span>  
<span data-ttu-id="aeb89-109">\<custom></span><span class="sxs-lookup"><span data-stu-id="aeb89-109">\<custom></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aeb89-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aeb89-110">Syntax</span></span>  
  
```xml  
<custom address="Uri"
        resolverType="String">
  <headers/>
  <identity/>
</custom>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aeb89-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="aeb89-111">Attributes and Elements</span></span>  
 <span data-ttu-id="aeb89-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="aeb89-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aeb89-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="aeb89-113">Attributes</span></span>  
  
|<span data-ttu-id="aeb89-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="aeb89-114">Attribute</span></span>|<span data-ttu-id="aeb89-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="aeb89-115">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="aeb89-116">Un URI que especifica la dirección de extremo del nodo de iguales que hospeda el servicio de resolución del mismo nivel personalizado.</span><span class="sxs-lookup"><span data-stu-id="aeb89-116">A URI that specifies the endpoint address of the peer node that hosts the custom peer resolver service.</span></span>|  
|`resolverType`|<span data-ttu-id="aeb89-117">Una cadena que especifica el tipo de servicio de resolución del mismo nivel personalizado.</span><span class="sxs-lookup"><span data-stu-id="aeb89-117">A string that specifies the type of the custom peer resolver service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aeb89-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="aeb89-118">Child Elements</span></span>  
  
|<span data-ttu-id="aeb89-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="aeb89-119">Element</span></span>|<span data-ttu-id="aeb89-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="aeb89-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aeb89-121">\<identity></span><span class="sxs-lookup"><span data-stu-id="aeb89-121">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="aeb89-122">Especifica la identidad para las resoluciones del mismo nivel personalizadas configuradas con este elemento.</span><span class="sxs-lookup"><span data-stu-id="aeb89-122">Specifies the identity for custom peer resolvers configured with this element.</span></span> <span data-ttu-id="aeb89-123">Este elemento es del tipo <xref:System.ServiceModel.Configuration.IdentityElement>.</span><span class="sxs-lookup"><span data-stu-id="aeb89-123">This element is of type <xref:System.ServiceModel.Configuration.IdentityElement>.</span></span>|  
|[<span data-ttu-id="aeb89-124">\<headers></span><span class="sxs-lookup"><span data-stu-id="aeb89-124">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="aeb89-125">Una colección de encabezado de dirección usada para mensajes SOAP administrados por la resolución del mismo nivel personalizada.</span><span class="sxs-lookup"><span data-stu-id="aeb89-125">A collection of address header used for SOAP messages handled by the custom peer resolver.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aeb89-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="aeb89-126">Parent Elements</span></span>  
  
|<span data-ttu-id="aeb89-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="aeb89-127">Element</span></span>|<span data-ttu-id="aeb89-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="aeb89-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aeb89-129">\<resolver></span><span class="sxs-lookup"><span data-stu-id="aeb89-129">\<resolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/resolver.md)|<span data-ttu-id="aeb89-130">Una resolución del mismo nivel que se usa para resolver un Id. de malla del mismo nivel como un conjunto de direcciones del nodo del mismo nivel que representa varios nodos que participan en la malla.</span><span class="sxs-lookup"><span data-stu-id="aeb89-130">A peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aeb89-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="aeb89-131">Remarks</span></span>  
 <span data-ttu-id="aeb89-132">Este elemento define la configuración básica para un servicio de la resolución del mismo nivel personalizado, incluso la dirección de punto de conexión del igual que hospeda el servicio y cualquier configuración de enlace concreta.</span><span class="sxs-lookup"><span data-stu-id="aeb89-132">This element defines the basic settings for a custom peer resolver service, including the endpoint address of the peer hosting the service and any specific binding settings.</span></span> <span data-ttu-id="aeb89-133">Para obtener más información sobre la creación de un solucionador personalizado, consulte [agregando un solucionador personalizado a una aplicación PeerChannel](https://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419).</span><span class="sxs-lookup"><span data-stu-id="aeb89-133">For more information on creating a custom resolver, see [Adding a Custom Resolver to a PeerChannel Application](https://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aeb89-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="aeb89-134">See also</span></span>
- <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>
- <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>
- <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>
- <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>
- [<span data-ttu-id="aeb89-135">Resoluciones del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="aeb89-135">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
- [<span data-ttu-id="aeb89-136">Adición de un solucionador personalizado a una aplicación PeerChannel</span><span class="sxs-lookup"><span data-stu-id="aeb89-136">Adding a Custom Resolver to a PeerChannel Application</span></span>](https://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419)
