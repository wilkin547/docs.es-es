---
description: 'Más información acerca de: <filter>'
title: <filter>
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: 993d2265ac3a714475e8cbe9e8a2c3f93c46bde2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664683"
---
# \<filter>

<span data-ttu-id="3ca72-102">Define un filtro de enrutamiento, que determina el tipo de Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> que se va a usar al evaluar los mensajes entrantes, así como cualquier dato o parámetro auxiliar requerido por el filtro.</span><span class="sxs-lookup"><span data-stu-id="3ca72-102">Defines a routing filter, which determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<filters>**](filters-of-routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**  
  
## <a name="syntax"></a><span data-ttu-id="3ca72-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3ca72-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3ca72-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3ca72-104">Attributes and elements</span></span>

<span data-ttu-id="3ca72-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3ca72-105">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="3ca72-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="3ca72-106">Attributes</span></span>

| <span data-ttu-id="3ca72-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="3ca72-107">Attribute</span></span>  | <span data-ttu-id="3ca72-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="3ca72-108">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="3ca72-109">customType</span><span class="sxs-lookup"><span data-stu-id="3ca72-109">customType</span></span> | <span data-ttu-id="3ca72-110">Cadena que contiene el nombre de tipo completo del tipo personalizado que se va a usar como filtro.</span><span class="sxs-lookup"><span data-stu-id="3ca72-110">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="3ca72-111">Si `filterType` está establecido en `custom` , este atributo contiene el nombre de tipo completo de la clase que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="3ca72-111">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="3ca72-112">`filterData` también puede contener valores que se van a usar durante la evaluación del filtro de tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="3ca72-112">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="3ca72-113">filterData</span><span class="sxs-lookup"><span data-stu-id="3ca72-113">filterData</span></span> | <span data-ttu-id="3ca72-114">Cadena que contiene los datos del filtro.</span><span class="sxs-lookup"><span data-stu-id="3ca72-114">A string containing the filter data.</span></span> <span data-ttu-id="3ca72-115">Para obtener más información sobre cómo especificar este atributo, vea <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="3ca72-115">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="3ca72-116">filterType</span><span class="sxs-lookup"><span data-stu-id="3ca72-116">filterType</span></span> | <span data-ttu-id="3ca72-117">Cadena que contiene el tipo de filtro.</span><span class="sxs-lookup"><span data-stu-id="3ca72-117">A string containing the filter type.</span></span> <span data-ttu-id="3ca72-118">Este atributo es del tipo <xref:System.ServiceModel.Routing.Configuration.FilterType>.</span><span class="sxs-lookup"><span data-stu-id="3ca72-118">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="3ca72-119">Para obtener más información sobre su funcionamiento con el atributo `filterData`, vea <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="3ca72-119">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="3ca72-120">name</span><span class="sxs-lookup"><span data-stu-id="3ca72-120">name</span></span>       | <span data-ttu-id="3ca72-121">Cadena que contiene el nombre único de este elemento de filtro.</span><span class="sxs-lookup"><span data-stu-id="3ca72-121">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="3ca72-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3ca72-122">Child elements</span></span>

<span data-ttu-id="3ca72-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3ca72-123">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3ca72-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3ca72-124">Parent elements</span></span>

| <span data-ttu-id="3ca72-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="3ca72-125">Element</span></span> | <span data-ttu-id="3ca72-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="3ca72-126">Description</span></span> |
| ------- | ----------- |
| [\<routing>](routing.md) | <span data-ttu-id="3ca72-127">Sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> que se va a usar al evaluar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="3ca72-127">A configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="3ca72-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ca72-128">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>
