---
title: <filter>
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: 6e78275aaeb202405e327302455d56fa431d7f27
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855249"
---
# <a name="filter"></a><span data-ttu-id="6ea49-101">\<filter></span><span class="sxs-lookup"><span data-stu-id="6ea49-101">\<filter></span></span>

<span data-ttu-id="6ea49-102">Define un filtro de enrutamiento, que determina el tipo de Windows Communication Foundation (WCF<xref:System.ServiceModel.Dispatcher.MessageFilter> ) que se va a usar al evaluar los mensajes entrantes, así como cualquier dato o parámetro auxiliar requerido por el filtro.</span><span class="sxs-lookup"><span data-stu-id="6ea49-102">Defines a routing filter, which determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

<span data-ttu-id="6ea49-103">[ **\<system.serviceModel>** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="6ea49-103">[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="6ea49-104">&nbsp;&nbsp;[ **\<> de enrutamiento**](routing.md)</span><span class="sxs-lookup"><span data-stu-id="6ea49-104">&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="6ea49-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de filtros**](filters-of-routing.md)</span><span class="sxs-lookup"><span data-stu-id="6ea49-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<filters>**](filters-of-routing.md)</span></span>\
<span data-ttu-id="6ea49-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<filtrar >**</span><span class="sxs-lookup"><span data-stu-id="6ea49-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ea49-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6ea49-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6ea49-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6ea49-108">Attributes and elements</span></span>

<span data-ttu-id="6ea49-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6ea49-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="6ea49-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="6ea49-110">Attributes</span></span>

| <span data-ttu-id="6ea49-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="6ea49-111">Attribute</span></span>  | <span data-ttu-id="6ea49-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="6ea49-112">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="6ea49-113">customType</span><span class="sxs-lookup"><span data-stu-id="6ea49-113">customType</span></span> | <span data-ttu-id="6ea49-114">Cadena que contiene el nombre de tipo completo del tipo personalizado que se va a usar como filtro.</span><span class="sxs-lookup"><span data-stu-id="6ea49-114">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="6ea49-115">Si `filterType` está establecido en `custom`, este atributo contiene el nombre de tipo completo de la clase que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="6ea49-115">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="6ea49-116">`filterData`también puede contener valores que se van a usar durante la evaluación del filtro de tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="6ea49-116">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="6ea49-117">filterData</span><span class="sxs-lookup"><span data-stu-id="6ea49-117">filterData</span></span> | <span data-ttu-id="6ea49-118">Cadena que contiene los datos del filtro.</span><span class="sxs-lookup"><span data-stu-id="6ea49-118">A string containing the filter data.</span></span> <span data-ttu-id="6ea49-119">Para obtener más información sobre cómo especificar este atributo, vea <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="6ea49-119">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="6ea49-120">filterType</span><span class="sxs-lookup"><span data-stu-id="6ea49-120">filterType</span></span> | <span data-ttu-id="6ea49-121">Cadena que contiene el tipo de filtro.</span><span class="sxs-lookup"><span data-stu-id="6ea49-121">A string containing the filter type.</span></span> <span data-ttu-id="6ea49-122">Este atributo es del tipo <xref:System.ServiceModel.Routing.Configuration.FilterType>.</span><span class="sxs-lookup"><span data-stu-id="6ea49-122">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="6ea49-123">Para obtener más información sobre su funcionamiento con el atributo `filterData`, vea <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="6ea49-123">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="6ea49-124">name</span><span class="sxs-lookup"><span data-stu-id="6ea49-124">name</span></span>       | <span data-ttu-id="6ea49-125">Cadena que contiene el nombre único de este elemento de filtro.</span><span class="sxs-lookup"><span data-stu-id="6ea49-125">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="6ea49-126">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6ea49-126">Child elements</span></span>

<span data-ttu-id="6ea49-127">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6ea49-127">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6ea49-128">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6ea49-128">Parent elements</span></span>

| <span data-ttu-id="6ea49-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="6ea49-129">Element</span></span> | <span data-ttu-id="6ea49-130">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="6ea49-130">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="6ea49-131">\<> de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="6ea49-131">\<routing></span></span>](routing.md) | <span data-ttu-id="6ea49-132">Sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de Windows Communication Foundation<xref:System.ServiceModel.Dispatcher.MessageFilter> (WCF) que se va a usar al evaluar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="6ea49-132">A configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="6ea49-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ea49-133">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>
