---
title: <filter>
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: 68de255b9f11dc4377159d1cc3efa575633db316
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918896"
---
# <a name="filter"></a><span data-ttu-id="61ff5-101">\<filter></span><span class="sxs-lookup"><span data-stu-id="61ff5-101">\<filter></span></span>

<span data-ttu-id="61ff5-102">Define un filtro de enrutamiento, que determina el tipo de Windows Communication Foundation (WCF<xref:System.ServiceModel.Dispatcher.MessageFilter> ) que se va a usar al evaluar los mensajes entrantes, así como cualquier dato o parámetro auxiliar requerido por el filtro.</span><span class="sxs-lookup"><span data-stu-id="61ff5-102">Defines a routing filter, which determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

<span data-ttu-id="61ff5-103">\<system.serviceModel> \<routing> \<filters> \<filter></span><span class="sxs-lookup"><span data-stu-id="61ff5-103">\<system.serviceModel> \<routing> \<filters> \<filter></span></span>
  
## <a name="syntax"></a><span data-ttu-id="61ff5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="61ff5-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="61ff5-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="61ff5-105">Attributes and elements</span></span>

<span data-ttu-id="61ff5-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="61ff5-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="61ff5-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="61ff5-107">Attributes</span></span>

| <span data-ttu-id="61ff5-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="61ff5-108">Attribute</span></span>  | <span data-ttu-id="61ff5-109">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="61ff5-109">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="61ff5-110">customType</span><span class="sxs-lookup"><span data-stu-id="61ff5-110">customType</span></span> | <span data-ttu-id="61ff5-111">Cadena que contiene el nombre de tipo completo del tipo personalizado que se va a usar como filtro.</span><span class="sxs-lookup"><span data-stu-id="61ff5-111">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="61ff5-112">Si `filterType` está establecido en `custom`, este atributo contiene el nombre de tipo completo de la clase que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="61ff5-112">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="61ff5-113">`filterData`también puede contener valores que se van a usar durante la evaluación del filtro de tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="61ff5-113">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="61ff5-114">filterData</span><span class="sxs-lookup"><span data-stu-id="61ff5-114">filterData</span></span> | <span data-ttu-id="61ff5-115">Cadena que contiene los datos del filtro.</span><span class="sxs-lookup"><span data-stu-id="61ff5-115">A string containing the filter data.</span></span> <span data-ttu-id="61ff5-116">Para obtener más información sobre cómo especificar este atributo, vea <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="61ff5-116">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="61ff5-117">filterType</span><span class="sxs-lookup"><span data-stu-id="61ff5-117">filterType</span></span> | <span data-ttu-id="61ff5-118">Cadena que contiene el tipo de filtro.</span><span class="sxs-lookup"><span data-stu-id="61ff5-118">A string containing the filter type.</span></span> <span data-ttu-id="61ff5-119">Este atributo es del tipo <xref:System.ServiceModel.Routing.Configuration.FilterType>.</span><span class="sxs-lookup"><span data-stu-id="61ff5-119">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="61ff5-120">Para obtener más información sobre su funcionamiento con el atributo `filterData`, vea <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="61ff5-120">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="61ff5-121">Nombre</span><span class="sxs-lookup"><span data-stu-id="61ff5-121">name</span></span>       | <span data-ttu-id="61ff5-122">Cadena que contiene el nombre único de este elemento de filtro.</span><span class="sxs-lookup"><span data-stu-id="61ff5-122">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="61ff5-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="61ff5-123">Child elements</span></span>

<span data-ttu-id="61ff5-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="61ff5-124">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="61ff5-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="61ff5-125">Parent elements</span></span>

| <span data-ttu-id="61ff5-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="61ff5-126">Element</span></span> | <span data-ttu-id="61ff5-127">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="61ff5-127">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="61ff5-128">\<> de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="61ff5-128">\<routing></span></span>](routing.md) | <span data-ttu-id="61ff5-129">Sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de Windows Communication Foundation<xref:System.ServiceModel.Dispatcher.MessageFilter> (WCF) que se va a usar al evaluar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="61ff5-129">A configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="61ff5-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="61ff5-130">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>
