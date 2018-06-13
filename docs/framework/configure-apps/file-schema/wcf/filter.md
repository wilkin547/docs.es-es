---
title: '&lt;Filtro&gt;'
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: 93d47fc6b25a75eedae43cd70582abc863a74e6c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32747215"
---
# <a name="ltfiltergt"></a><span data-ttu-id="c30bf-102">&lt;Filtro&gt;</span><span class="sxs-lookup"><span data-stu-id="c30bf-102">&lt;filter&gt;</span></span>

<span data-ttu-id="c30bf-103">Define un filtro del enrutamiento, que determina el tipo de Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> que se usará al evaluar los mensajes entrantes, como también los datos o los parámetros requeridos por el filtro de apoyo.</span><span class="sxs-lookup"><span data-stu-id="c30bf-103">Defines a routing filter, which determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

<span data-ttu-id="c30bf-104">\<system.serviceModel > \<enrutamiento > \<filtros > \<filtro ></span><span class="sxs-lookup"><span data-stu-id="c30bf-104">\<system.serviceModel> \<routing> \<filters> \<filter></span></span>

## <a name="syntax"></a><span data-ttu-id="c30bf-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c30bf-105">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="c30bf-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c30bf-106">Attributes and elements</span></span>

<span data-ttu-id="c30bf-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c30bf-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="c30bf-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="c30bf-108">Attributes</span></span>

| <span data-ttu-id="c30bf-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="c30bf-109">Attribute</span></span>  | <span data-ttu-id="c30bf-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="c30bf-110">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="c30bf-111">customType</span><span class="sxs-lookup"><span data-stu-id="c30bf-111">customType</span></span> | <span data-ttu-id="c30bf-112">Cadena que contiene el nombre de tipo completo del tipo personalizado que se va a usar como filtro.</span><span class="sxs-lookup"><span data-stu-id="c30bf-112">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="c30bf-113">Si `filterType` se establece en `custom`, este atributo contiene el nombre de tipo completo de la clase para crear.</span><span class="sxs-lookup"><span data-stu-id="c30bf-113">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="c30bf-114">`filterData` También se puede contener valores que se usarán durante la evaluación del filtro de tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="c30bf-114">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="c30bf-115">filterData</span><span class="sxs-lookup"><span data-stu-id="c30bf-115">filterData</span></span> | <span data-ttu-id="c30bf-116">Cadena que contiene los datos del filtro.</span><span class="sxs-lookup"><span data-stu-id="c30bf-116">A string containing the filter data.</span></span> <span data-ttu-id="c30bf-117">Para obtener más información sobre cómo especificar este atributo, vea <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="c30bf-117">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="c30bf-118">filterType</span><span class="sxs-lookup"><span data-stu-id="c30bf-118">filterType</span></span> | <span data-ttu-id="c30bf-119">Cadena que contiene el tipo de filtro.</span><span class="sxs-lookup"><span data-stu-id="c30bf-119">A string containing the filter type.</span></span> <span data-ttu-id="c30bf-120">Este atributo es del tipo <xref:System.ServiceModel.Routing.Configuration.FilterType>.</span><span class="sxs-lookup"><span data-stu-id="c30bf-120">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="c30bf-121">Para obtener más información sobre su funcionamiento con el atributo `filterData`, vea <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="c30bf-121">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="c30bf-122">name</span><span class="sxs-lookup"><span data-stu-id="c30bf-122">name</span></span>       | <span data-ttu-id="c30bf-123">Cadena que contiene el nombre único de este elemento de filtro.</span><span class="sxs-lookup"><span data-stu-id="c30bf-123">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="c30bf-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c30bf-124">Child elements</span></span>

<span data-ttu-id="c30bf-125">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c30bf-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c30bf-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c30bf-126">Parent elements</span></span>

| <span data-ttu-id="c30bf-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="c30bf-127">Element</span></span> | <span data-ttu-id="c30bf-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="c30bf-128">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="c30bf-129">\<enrutamiento ></span><span class="sxs-lookup"><span data-stu-id="c30bf-129">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="c30bf-130">Una sección de configuración para definir un conjunto de filtros de enrutamiento, que determina el tipo de Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> que se usará al evaluar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="c30bf-130">A configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="c30bf-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="c30bf-131">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>    
<xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>   
<xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>   
