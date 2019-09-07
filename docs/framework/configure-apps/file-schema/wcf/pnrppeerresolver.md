---
title: <pnrpPeerResolver>
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: d7c6c8efa971fb60f0257cc1c74ceda72e31cb84
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400046"
---
# <a name="pnrppeerresolver"></a><span data-ttu-id="43da4-101">\<pnrpPeerResolver></span><span class="sxs-lookup"><span data-stu-id="43da4-101">\<pnrpPeerResolver></span></span>
<span data-ttu-id="43da4-102">Especifica que la resolución de PNRP (Protocolo de resolución de nombres de mismo nivel) será utilizada como resolución.</span><span class="sxs-lookup"><span data-stu-id="43da4-102">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="43da4-103">Este elemento es opcional porque PNRP es la resolución predeterminada.</span><span class="sxs-lookup"><span data-stu-id="43da4-103">This element is optional because PNRP is the default resolver.</span></span>  
  
<span data-ttu-id="43da4-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="43da4-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="43da4-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="43da4-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="43da4-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enlaces**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="43da4-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="43da4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="43da4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="43da4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de enlace**</span><span class="sxs-lookup"><span data-stu-id="43da4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="43da4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> pnrpResolver**</span><span class="sxs-lookup"><span data-stu-id="43da4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<pnrpResolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43da4-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="43da4-110">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="43da4-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="43da4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="43da4-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="43da4-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="43da4-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="43da4-113">Attributes</span></span>  
  
|<span data-ttu-id="43da4-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="43da4-114">Attribute</span></span>|<span data-ttu-id="43da4-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="43da4-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="43da4-116">resolverType</span><span class="sxs-lookup"><span data-stu-id="43da4-116">resolverType</span></span>|<span data-ttu-id="43da4-117">Una cadena que especifica la resolución que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="43da4-117">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="43da4-118">Este atributo es opcional.</span><span class="sxs-lookup"><span data-stu-id="43da4-118">This attribute is optional.</span></span> <span data-ttu-id="43da4-119">Si no se establece, o si está establecido en una cadena vacía, se utiliza PNRP.</span><span class="sxs-lookup"><span data-stu-id="43da4-119">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="43da4-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="43da4-120">Child Elements</span></span>  
 <span data-ttu-id="43da4-121">None</span><span class="sxs-lookup"><span data-stu-id="43da4-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="43da4-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="43da4-122">Parent Elements</span></span>  
  
|<span data-ttu-id="43da4-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="43da4-123">Element</span></span>|<span data-ttu-id="43da4-124">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="43da4-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="43da4-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="43da4-125">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="43da4-126">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="43da4-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="43da4-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="43da4-127">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="see-also"></a><span data-ttu-id="43da4-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="43da4-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>
- <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="43da4-129">Enlaces</span><span class="sxs-lookup"><span data-stu-id="43da4-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="43da4-130">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="43da4-130">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="43da4-131">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="43da4-131">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="43da4-132">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="43da4-132">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="43da4-133">Resoluciones del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="43da4-133">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
