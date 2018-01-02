---
title: '&lt;filtro&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 186c511cd8a69cef5e30e369641628a10a0972d7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltfiltergt"></a><span data-ttu-id="c871f-102">&lt;filtro&gt;</span><span class="sxs-lookup"><span data-stu-id="c871f-102">&lt;filter&gt;</span></span>

<span data-ttu-id="c871f-103">Define un filtro del enrutamiento, que determina el tipo de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] de <xref:System.ServiceModel.Dispatcher.MessageFilter> que se va a utilizar al evaluar los mensajes entrantes, así como cualquier dato o parámetro de compatibilidad requerido por el filtro.</span><span class="sxs-lookup"><span data-stu-id="c871f-103">Defines a routing filter, which determines the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

<span data-ttu-id="c871f-104">\<system.serviceModel > \<enrutamiento > \<filtros > \<filtro ></span><span class="sxs-lookup"><span data-stu-id="c871f-104">\<system.serviceModel> \<routing> \<filters> \<filter></span></span>

## <a name="syntax"></a><span data-ttu-id="c871f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c871f-105">Syntax</span></span>

```xml
<routing>
  <filters>
    <filter customType="String" 
            filterData="String" 
            filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath" 
            name="String" />
  </filters>
</routing>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c871f-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c871f-106">Attributes and elements</span></span>

<span data-ttu-id="c871f-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c871f-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="c871f-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="c871f-108">Attributes</span></span>

| <span data-ttu-id="c871f-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="c871f-109">Attribute</span></span>  | <span data-ttu-id="c871f-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="c871f-110">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="c871f-111">customType</span><span class="sxs-lookup"><span data-stu-id="c871f-111">customType</span></span> | <span data-ttu-id="c871f-112">Cadena que contiene el nombre de tipo completo del tipo personalizado que se va a usar como filtro.</span><span class="sxs-lookup"><span data-stu-id="c871f-112">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="c871f-113">Si `filterType` se establece en `custom`, este atributo contiene el nombre de tipo completo de la clase para crear.</span><span class="sxs-lookup"><span data-stu-id="c871f-113">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="c871f-114">`filterData`También se puede contener valores que se usarán durante la evaluación del filtro de tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="c871f-114">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="c871f-115">filterData</span><span class="sxs-lookup"><span data-stu-id="c871f-115">filterData</span></span> | <span data-ttu-id="c871f-116">Cadena que contiene los datos del filtro.</span><span class="sxs-lookup"><span data-stu-id="c871f-116">A string containing the filter data.</span></span> <span data-ttu-id="c871f-117">Para obtener más información sobre cómo especificar este atributo, vea <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="c871f-117">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="c871f-118">filterType</span><span class="sxs-lookup"><span data-stu-id="c871f-118">filterType</span></span> | <span data-ttu-id="c871f-119">Cadena que contiene el tipo de filtro.</span><span class="sxs-lookup"><span data-stu-id="c871f-119">A string containing the filter type.</span></span> <span data-ttu-id="c871f-120">Este atributo es del tipo <xref:System.ServiceModel.Routing.Configuration.FilterType>.</span><span class="sxs-lookup"><span data-stu-id="c871f-120">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="c871f-121">Para obtener más información sobre su funcionamiento con el atributo `filterData`, vea <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="c871f-121">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="c871f-122">name</span><span class="sxs-lookup"><span data-stu-id="c871f-122">name</span></span>       | <span data-ttu-id="c871f-123">Cadena que contiene el nombre único de este elemento de filtro.</span><span class="sxs-lookup"><span data-stu-id="c871f-123">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="c871f-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c871f-124">Child elements</span></span>

<span data-ttu-id="c871f-125">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c871f-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c871f-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c871f-126">Parent elements</span></span>

| <span data-ttu-id="c871f-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="c871f-127">Element</span></span> | <span data-ttu-id="c871f-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="c871f-128">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="c871f-129">\<enrutamiento ></span><span class="sxs-lookup"><span data-stu-id="c871f-129">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="c871f-130">Una sección de configuración para definir un conjunto de filtros de enrutamiento, que determina el tipo de [!INCLUDE[ indigo1](../../../../../includes/indigo1-md.md)] <xref:System.ServiceModel.Dispatcher.MessageFilter> que se usará al evaluar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="c871f-130">A configuration section for defining a set of routing filters, which determine the type of [!INCLUDE[ indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="c871f-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="c871f-131">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>    
<xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>   
<xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>   
