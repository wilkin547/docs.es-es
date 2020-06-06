---
title: <filter>
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: 6e78275aaeb202405e327302455d56fa431d7f27
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855249"
---
# \<filter>

<span data-ttu-id="21b82-101">Define un filtro de enrutamiento, que determina el tipo de Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> que se va a usar al evaluar los mensajes entrantes, así como cualquier dato o parámetro auxiliar requerido por el filtro.</span><span class="sxs-lookup"><span data-stu-id="21b82-101">Defines a routing filter, which determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<filters>**](filters-of-routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**  
  
## <a name="syntax"></a><span data-ttu-id="21b82-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="21b82-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="21b82-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="21b82-103">Attributes and elements</span></span>

<span data-ttu-id="21b82-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="21b82-104">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="21b82-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="21b82-105">Attributes</span></span>

| <span data-ttu-id="21b82-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="21b82-106">Attribute</span></span>  | <span data-ttu-id="21b82-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="21b82-107">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="21b82-108">customType</span><span class="sxs-lookup"><span data-stu-id="21b82-108">customType</span></span> | <span data-ttu-id="21b82-109">Cadena que contiene el nombre de tipo completo del tipo personalizado que se va a usar como filtro.</span><span class="sxs-lookup"><span data-stu-id="21b82-109">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="21b82-110">Si `filterType` está establecido en `custom` , este atributo contiene el nombre de tipo completo de la clase que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="21b82-110">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="21b82-111">`filterData`también puede contener valores que se van a usar durante la evaluación del filtro de tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="21b82-111">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="21b82-112">filterData</span><span class="sxs-lookup"><span data-stu-id="21b82-112">filterData</span></span> | <span data-ttu-id="21b82-113">Cadena que contiene los datos del filtro.</span><span class="sxs-lookup"><span data-stu-id="21b82-113">A string containing the filter data.</span></span> <span data-ttu-id="21b82-114">Para obtener más información sobre cómo especificar este atributo, vea <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="21b82-114">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="21b82-115">filterType</span><span class="sxs-lookup"><span data-stu-id="21b82-115">filterType</span></span> | <span data-ttu-id="21b82-116">Cadena que contiene el tipo de filtro.</span><span class="sxs-lookup"><span data-stu-id="21b82-116">A string containing the filter type.</span></span> <span data-ttu-id="21b82-117">Este atributo es del tipo <xref:System.ServiceModel.Routing.Configuration.FilterType>.</span><span class="sxs-lookup"><span data-stu-id="21b82-117">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="21b82-118">Para obtener más información sobre su funcionamiento con el atributo `filterData`, vea <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="21b82-118">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="21b82-119">name</span><span class="sxs-lookup"><span data-stu-id="21b82-119">name</span></span>       | <span data-ttu-id="21b82-120">Cadena que contiene el nombre único de este elemento de filtro.</span><span class="sxs-lookup"><span data-stu-id="21b82-120">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="21b82-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="21b82-121">Child elements</span></span>

<span data-ttu-id="21b82-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="21b82-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="21b82-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="21b82-123">Parent elements</span></span>

| <span data-ttu-id="21b82-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="21b82-124">Element</span></span> | <span data-ttu-id="21b82-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="21b82-125">Description</span></span> |
| ------- | ----------- |
| [\<routing>](routing.md) | <span data-ttu-id="21b82-126">Sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> que se va a usar al evaluar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="21b82-126">A configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="21b82-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="21b82-127">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>
