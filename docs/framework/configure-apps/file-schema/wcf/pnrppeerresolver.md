---
title: <pnrpPeerResolver>
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: e7e82117304ac133e5e84c0fc36b987560bcef96
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933808"
---
# <a name="pnrppeerresolver"></a><span data-ttu-id="98eff-101">\<pnrpPeerResolver></span><span class="sxs-lookup"><span data-stu-id="98eff-101">\<pnrpPeerResolver></span></span>
<span data-ttu-id="98eff-102">Especifica que la resolución de PNRP (Protocolo de resolución de nombres de mismo nivel) será utilizada como resolución.</span><span class="sxs-lookup"><span data-stu-id="98eff-102">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="98eff-103">Este elemento es opcional porque PNRP es la resolución predeterminada.</span><span class="sxs-lookup"><span data-stu-id="98eff-103">This element is optional because PNRP is the default resolver.</span></span>  
  
 <span data-ttu-id="98eff-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="98eff-104">\<system.serviceModel></span></span>  
<span data-ttu-id="98eff-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="98eff-105">\<bindings></span></span>  
<span data-ttu-id="98eff-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="98eff-106">\<customBinding></span></span>  
<span data-ttu-id="98eff-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="98eff-107">\<binding></span></span>  
<span data-ttu-id="98eff-108">\<pnrpResolver></span><span class="sxs-lookup"><span data-stu-id="98eff-108">\<pnrpResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98eff-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="98eff-109">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="98eff-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="98eff-110">Attributes and Elements</span></span>  
 <span data-ttu-id="98eff-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="98eff-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="98eff-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="98eff-112">Attributes</span></span>  
  
|<span data-ttu-id="98eff-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="98eff-113">Attribute</span></span>|<span data-ttu-id="98eff-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="98eff-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="98eff-115">resolverType</span><span class="sxs-lookup"><span data-stu-id="98eff-115">resolverType</span></span>|<span data-ttu-id="98eff-116">Una cadena que especifica la resolución que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="98eff-116">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="98eff-117">Este atributo es opcional.</span><span class="sxs-lookup"><span data-stu-id="98eff-117">This attribute is optional.</span></span> <span data-ttu-id="98eff-118">Si no se establece, o si está establecido en una cadena vacía, se utiliza PNRP.</span><span class="sxs-lookup"><span data-stu-id="98eff-118">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="98eff-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="98eff-119">Child Elements</span></span>  
 <span data-ttu-id="98eff-120">None</span><span class="sxs-lookup"><span data-stu-id="98eff-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="98eff-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="98eff-121">Parent Elements</span></span>  
  
|<span data-ttu-id="98eff-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="98eff-122">Element</span></span>|<span data-ttu-id="98eff-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="98eff-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="98eff-124">\<binding></span><span class="sxs-lookup"><span data-stu-id="98eff-124">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="98eff-125">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="98eff-125">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="98eff-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="98eff-126">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="see-also"></a><span data-ttu-id="98eff-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="98eff-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>
- <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="98eff-128">Enlaces</span><span class="sxs-lookup"><span data-stu-id="98eff-128">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="98eff-129">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="98eff-129">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="98eff-130">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="98eff-130">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="98eff-131">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="98eff-131">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="98eff-132">Resoluciones del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="98eff-132">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
