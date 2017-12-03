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
ms.openlocfilehash: af2095289d5f711733c71238b855c685114d1997
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltfiltergt"></a><span data-ttu-id="1e3b6-102">&lt;filtro&gt;</span><span class="sxs-lookup"><span data-stu-id="1e3b6-102">&lt;filter&gt;</span></span>

<span data-ttu-id="1e3b6-103">Define un filtro del enrutamiento, que determina el tipo de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] de <xref:System.ServiceModel.Dispatcher.MessageFilter> que se va a utilizar al evaluar los mensajes entrantes, así como cualquier dato o parámetro de compatibilidad requerido por el filtro.</span><span class="sxs-lookup"><span data-stu-id="1e3b6-103">Defines a routing filter, which determines the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

<span data-ttu-id="1e3b6-104">\<system.serviceModel > \<enrutamiento > \<filtros > \<filtro ></span><span class="sxs-lookup"><span data-stu-id="1e3b6-104">\<system.serviceModel> \<routing> \<filters> \<filter></span></span>

## <a name="syntax"></a><span data-ttu-id="1e3b6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1e3b6-105">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="1e3b6-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1e3b6-106">Attributes and elements</span></span>

<span data-ttu-id="1e3b6-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1e3b6-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="1e3b6-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="1e3b6-108">Attributes</span></span>

| <span data-ttu-id="1e3b6-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="1e3b6-109">Attribute</span></span>  | <span data-ttu-id="1e3b6-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="1e3b6-110">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="1e3b6-111">customType</span><span class="sxs-lookup"><span data-stu-id="1e3b6-111">customType</span></span> | <span data-ttu-id="1e3b6-112">Cadena que contiene el nombre de tipo completo del tipo personalizado que se va a usar como filtro.</span><span class="sxs-lookup"><span data-stu-id="1e3b6-112">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="1e3b6-113">Si `filterType` se establece en `custom`, este atributo contiene el nombre de tipo completo de la clase para crear.</span><span class="sxs-lookup"><span data-stu-id="1e3b6-113">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="1e3b6-114">`filterData`También se puede contener valores que se usarán durante la evaluación del filtro de tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="1e3b6-114">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="1e3b6-115">filterData</span><span class="sxs-lookup"><span data-stu-id="1e3b6-115">filterData</span></span> | <span data-ttu-id="1e3b6-116">Cadena que contiene los datos del filtro.</span><span class="sxs-lookup"><span data-stu-id="1e3b6-116">A string containing the filter data.</span></span> <span data-ttu-id="1e3b6-117">Para obtener más información sobre cómo especificar este atributo, vea <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="1e3b6-117">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="1e3b6-118">filterType</span><span class="sxs-lookup"><span data-stu-id="1e3b6-118">filterType</span></span> | <span data-ttu-id="1e3b6-119">Cadena que contiene el tipo de filtro.</span><span class="sxs-lookup"><span data-stu-id="1e3b6-119">A string containing the filter type.</span></span> <span data-ttu-id="1e3b6-120">Este atributo es del tipo <xref:System.ServiceModel.Routing.Configuration.FilterType>.</span><span class="sxs-lookup"><span data-stu-id="1e3b6-120">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="1e3b6-121">Para obtener más información sobre su funcionamiento con el atributo `filterData`, vea <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="1e3b6-121">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="1e3b6-122">name</span><span class="sxs-lookup"><span data-stu-id="1e3b6-122">name</span></span>       | <span data-ttu-id="1e3b6-123">Cadena que contiene el nombre único de este elemento de filtro.</span><span class="sxs-lookup"><span data-stu-id="1e3b6-123">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="1e3b6-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1e3b6-124">Child elements</span></span>

<span data-ttu-id="1e3b6-125">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1e3b6-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1e3b6-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1e3b6-126">Parent elements</span></span>

| <span data-ttu-id="1e3b6-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="1e3b6-127">Element</span></span> | <span data-ttu-id="1e3b6-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="1e3b6-128">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="1e3b6-129">\<enrutamiento ></span><span class="sxs-lookup"><span data-stu-id="1e3b6-129">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="1e3b6-130">Sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de [!INCLUDE[ indigo1](../../../../../includes/indigo1-md.md)] de <xref:System.ServiceModel.Dispatcher.MessageFilter> que se va a utilizar al evaluar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="1e3b6-130">A configuration section for defining a set of routing filters, which determine the type of [!INCLUDE[ indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="1e3b6-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e3b6-131">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>    
<xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>   
<xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>   
