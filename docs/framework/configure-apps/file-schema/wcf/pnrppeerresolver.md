---
title: '&lt;pnrpPeerResolver&gt;'
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: cefd46d7810149264f9c431a212da0f3f51f8186
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54577651"
---
# <a name="ltpnrppeerresolvergt"></a><span data-ttu-id="97a93-102">&lt;pnrpPeerResolver&gt;</span><span class="sxs-lookup"><span data-stu-id="97a93-102">&lt;pnrpPeerResolver&gt;</span></span>
<span data-ttu-id="97a93-103">Especifica que la resolución de PNRP (Protocolo de resolución de nombres de mismo nivel) será utilizada como resolución.</span><span class="sxs-lookup"><span data-stu-id="97a93-103">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="97a93-104">Este elemento es opcional porque PNRP es la resolución predeterminada.</span><span class="sxs-lookup"><span data-stu-id="97a93-104">This element is optional because PNRP is the default resolver.</span></span>  
  
 <span data-ttu-id="97a93-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="97a93-105">\<system.serviceModel></span></span>  
<span data-ttu-id="97a93-106">\<bindings></span><span class="sxs-lookup"><span data-stu-id="97a93-106">\<bindings></span></span>  
<span data-ttu-id="97a93-107">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="97a93-107">\<customBinding></span></span>  
<span data-ttu-id="97a93-108">\<binding></span><span class="sxs-lookup"><span data-stu-id="97a93-108">\<binding></span></span>  
<span data-ttu-id="97a93-109">\<pnrpResolver></span><span class="sxs-lookup"><span data-stu-id="97a93-109">\<pnrpResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97a93-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="97a93-110">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="97a93-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="97a93-111">Attributes and Elements</span></span>  
 <span data-ttu-id="97a93-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="97a93-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="97a93-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="97a93-113">Attributes</span></span>  
  
|<span data-ttu-id="97a93-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="97a93-114">Attribute</span></span>|<span data-ttu-id="97a93-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="97a93-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="97a93-116">resolverType</span><span class="sxs-lookup"><span data-stu-id="97a93-116">resolverType</span></span>|<span data-ttu-id="97a93-117">Una cadena que especifica la resolución que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="97a93-117">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="97a93-118">Este atributo es opcional.</span><span class="sxs-lookup"><span data-stu-id="97a93-118">This attribute is optional.</span></span> <span data-ttu-id="97a93-119">Si no se establece, o si está establecido en una cadena vacía, se utiliza PNRP.</span><span class="sxs-lookup"><span data-stu-id="97a93-119">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="97a93-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="97a93-120">Child Elements</span></span>  
 <span data-ttu-id="97a93-121">Ninguna</span><span class="sxs-lookup"><span data-stu-id="97a93-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="97a93-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="97a93-122">Parent Elements</span></span>  
  
|<span data-ttu-id="97a93-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="97a93-123">Element</span></span>|<span data-ttu-id="97a93-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="97a93-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="97a93-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="97a93-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="97a93-126">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="97a93-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="97a93-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="97a93-127">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="see-also"></a><span data-ttu-id="97a93-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="97a93-128">See also</span></span>
- <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>
- <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="97a93-129">Enlaces</span><span class="sxs-lookup"><span data-stu-id="97a93-129">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="97a93-130">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="97a93-130">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="97a93-131">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="97a93-131">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="97a93-132">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="97a93-132">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="97a93-133">Resoluciones del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="97a93-133">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
