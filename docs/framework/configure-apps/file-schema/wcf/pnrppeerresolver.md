---
title: <pnrpPeerResolver>
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: 2404f00b2a3ba03e89c1e21fb25e13cabb8feed3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783284"
---
# <a name="pnrppeerresolver"></a><span data-ttu-id="5b035-101">\<pnrpPeerResolver></span><span class="sxs-lookup"><span data-stu-id="5b035-101">\<pnrpPeerResolver></span></span>
<span data-ttu-id="5b035-102">Especifica que la resolución de PNRP (Protocolo de resolución de nombres de mismo nivel) será utilizada como resolución.</span><span class="sxs-lookup"><span data-stu-id="5b035-102">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="5b035-103">Este elemento es opcional porque PNRP es la resolución predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5b035-103">This element is optional because PNRP is the default resolver.</span></span>  
  
 <span data-ttu-id="5b035-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5b035-104">\<system.serviceModel></span></span>  
<span data-ttu-id="5b035-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="5b035-105">\<bindings></span></span>  
<span data-ttu-id="5b035-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="5b035-106">\<customBinding></span></span>  
<span data-ttu-id="5b035-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="5b035-107">\<binding></span></span>  
<span data-ttu-id="5b035-108">\<pnrpResolver></span><span class="sxs-lookup"><span data-stu-id="5b035-108">\<pnrpResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b035-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5b035-109">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5b035-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5b035-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5b035-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5b035-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5b035-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="5b035-112">Attributes</span></span>  
  
|<span data-ttu-id="5b035-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="5b035-113">Attribute</span></span>|<span data-ttu-id="5b035-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="5b035-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5b035-115">resolverType</span><span class="sxs-lookup"><span data-stu-id="5b035-115">resolverType</span></span>|<span data-ttu-id="5b035-116">Una cadena que especifica la resolución que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="5b035-116">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="5b035-117">Este atributo es opcional.</span><span class="sxs-lookup"><span data-stu-id="5b035-117">This attribute is optional.</span></span> <span data-ttu-id="5b035-118">Si no se establece, o si está establecido en una cadena vacía, se utiliza PNRP.</span><span class="sxs-lookup"><span data-stu-id="5b035-118">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5b035-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5b035-119">Child Elements</span></span>  
 <span data-ttu-id="5b035-120">Ninguna</span><span class="sxs-lookup"><span data-stu-id="5b035-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5b035-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5b035-121">Parent Elements</span></span>  
  
|<span data-ttu-id="5b035-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="5b035-122">Element</span></span>|<span data-ttu-id="5b035-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="5b035-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5b035-124">\<binding></span><span class="sxs-lookup"><span data-stu-id="5b035-124">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="5b035-125">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="5b035-125">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5b035-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5b035-126">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="see-also"></a><span data-ttu-id="5b035-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b035-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>
- <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="5b035-128">Enlaces</span><span class="sxs-lookup"><span data-stu-id="5b035-128">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="5b035-129">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="5b035-129">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="5b035-130">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="5b035-130">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="5b035-131">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="5b035-131">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="5b035-132">Resoluciones del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="5b035-132">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
