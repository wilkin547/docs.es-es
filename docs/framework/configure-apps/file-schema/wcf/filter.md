---
title: '&lt;Filtro&gt;'
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: f7224eab9f3c21bce9839298b50c52e9da08b6f7
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146412"
---
# <a name="ltfiltergt"></a><span data-ttu-id="5ac9b-102">&lt;Filtro&gt;</span><span class="sxs-lookup"><span data-stu-id="5ac9b-102">&lt;filter&gt;</span></span>

<span data-ttu-id="5ac9b-103">Define un filtro de enrutamiento, que determina el tipo de Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> que se usará al evaluar los mensajes entrantes, como así los datos o los parámetros requeridos por el filtro de apoyo.</span><span class="sxs-lookup"><span data-stu-id="5ac9b-103">Defines a routing filter, which determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

<span data-ttu-id="5ac9b-104">\<system.serviceModel > \<enrutamiento > \<filtros > \<filtro ></span><span class="sxs-lookup"><span data-stu-id="5ac9b-104">\<system.serviceModel> \<routing> \<filters> \<filter></span></span>
  
## <a name="syntax"></a><span data-ttu-id="5ac9b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5ac9b-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5ac9b-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5ac9b-106">Attributes and elements</span></span>

<span data-ttu-id="5ac9b-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5ac9b-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="5ac9b-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="5ac9b-108">Attributes</span></span>

| <span data-ttu-id="5ac9b-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="5ac9b-109">Attribute</span></span>  | <span data-ttu-id="5ac9b-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="5ac9b-110">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="5ac9b-111">customType</span><span class="sxs-lookup"><span data-stu-id="5ac9b-111">customType</span></span> | <span data-ttu-id="5ac9b-112">Cadena que contiene el nombre de tipo completo del tipo personalizado que se va a usar como filtro.</span><span class="sxs-lookup"><span data-stu-id="5ac9b-112">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="5ac9b-113">Si `filterType` está establecido en `custom`, este atributo contiene el nombre de tipo completo de la clase para crear.</span><span class="sxs-lookup"><span data-stu-id="5ac9b-113">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="5ac9b-114">`filterData` También se puede contener valores que se usarán durante la evaluación del filtro de tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="5ac9b-114">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="5ac9b-115">filterData</span><span class="sxs-lookup"><span data-stu-id="5ac9b-115">filterData</span></span> | <span data-ttu-id="5ac9b-116">Cadena que contiene los datos del filtro.</span><span class="sxs-lookup"><span data-stu-id="5ac9b-116">A string containing the filter data.</span></span> <span data-ttu-id="5ac9b-117">Para obtener más información sobre cómo especificar este atributo, vea <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="5ac9b-117">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="5ac9b-118">filterType</span><span class="sxs-lookup"><span data-stu-id="5ac9b-118">filterType</span></span> | <span data-ttu-id="5ac9b-119">Cadena que contiene el tipo de filtro.</span><span class="sxs-lookup"><span data-stu-id="5ac9b-119">A string containing the filter type.</span></span> <span data-ttu-id="5ac9b-120">Este atributo es del tipo <xref:System.ServiceModel.Routing.Configuration.FilterType>.</span><span class="sxs-lookup"><span data-stu-id="5ac9b-120">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="5ac9b-121">Para obtener más información sobre su funcionamiento con el atributo `filterData`, vea <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="5ac9b-121">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="5ac9b-122">name</span><span class="sxs-lookup"><span data-stu-id="5ac9b-122">name</span></span>       | <span data-ttu-id="5ac9b-123">Cadena que contiene el nombre único de este elemento de filtro.</span><span class="sxs-lookup"><span data-stu-id="5ac9b-123">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="5ac9b-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5ac9b-124">Child elements</span></span>

<span data-ttu-id="5ac9b-125">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5ac9b-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="5ac9b-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5ac9b-126">Parent elements</span></span>

| <span data-ttu-id="5ac9b-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="5ac9b-127">Element</span></span> | <span data-ttu-id="5ac9b-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="5ac9b-128">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="5ac9b-129">\<enrutamiento ></span><span class="sxs-lookup"><span data-stu-id="5ac9b-129">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="5ac9b-130">Una sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> que se usará al evaluar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="5ac9b-130">A configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="5ac9b-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ac9b-131">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>    
<xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>   
<xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>   
