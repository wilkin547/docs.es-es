---
title: <filter>
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: bff19f106d86c73dea80b8b57bb73442eaa2cf9f
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278790"
---
# <a name="filter"></a><span data-ttu-id="d2a3c-101">\<filter></span><span class="sxs-lookup"><span data-stu-id="d2a3c-101">\<filter></span></span>

<span data-ttu-id="d2a3c-102">Define un filtro de enrutamiento, que determina el tipo de Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> que se usará al evaluar los mensajes entrantes, como así los datos o los parámetros requeridos por el filtro de apoyo.</span><span class="sxs-lookup"><span data-stu-id="d2a3c-102">Defines a routing filter, which determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

<span data-ttu-id="d2a3c-103">\<system.serviceModel> \<routing> \<filters> \<filter></span><span class="sxs-lookup"><span data-stu-id="d2a3c-103">\<system.serviceModel> \<routing> \<filters> \<filter></span></span>
  
## <a name="syntax"></a><span data-ttu-id="d2a3c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d2a3c-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d2a3c-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d2a3c-105">Attributes and elements</span></span>

<span data-ttu-id="d2a3c-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d2a3c-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="d2a3c-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="d2a3c-107">Attributes</span></span>

| <span data-ttu-id="d2a3c-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="d2a3c-108">Attribute</span></span>  | <span data-ttu-id="d2a3c-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="d2a3c-109">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="d2a3c-110">customType</span><span class="sxs-lookup"><span data-stu-id="d2a3c-110">customType</span></span> | <span data-ttu-id="d2a3c-111">Cadena que contiene el nombre de tipo completo del tipo personalizado que se va a usar como filtro.</span><span class="sxs-lookup"><span data-stu-id="d2a3c-111">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="d2a3c-112">Si `filterType` está establecido en `custom`, este atributo contiene el nombre de tipo completo de la clase para crear.</span><span class="sxs-lookup"><span data-stu-id="d2a3c-112">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="d2a3c-113">`filterData` También se puede contener valores que se usarán durante la evaluación del filtro de tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="d2a3c-113">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="d2a3c-114">filterData</span><span class="sxs-lookup"><span data-stu-id="d2a3c-114">filterData</span></span> | <span data-ttu-id="d2a3c-115">Cadena que contiene los datos del filtro.</span><span class="sxs-lookup"><span data-stu-id="d2a3c-115">A string containing the filter data.</span></span> <span data-ttu-id="d2a3c-116">Para obtener más información sobre cómo especificar este atributo, vea <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="d2a3c-116">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="d2a3c-117">filterType</span><span class="sxs-lookup"><span data-stu-id="d2a3c-117">filterType</span></span> | <span data-ttu-id="d2a3c-118">Cadena que contiene el tipo de filtro.</span><span class="sxs-lookup"><span data-stu-id="d2a3c-118">A string containing the filter type.</span></span> <span data-ttu-id="d2a3c-119">Este atributo es del tipo <xref:System.ServiceModel.Routing.Configuration.FilterType>.</span><span class="sxs-lookup"><span data-stu-id="d2a3c-119">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="d2a3c-120">Para obtener más información sobre su funcionamiento con el atributo `filterData`, vea <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="d2a3c-120">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="d2a3c-121">name</span><span class="sxs-lookup"><span data-stu-id="d2a3c-121">name</span></span>       | <span data-ttu-id="d2a3c-122">Cadena que contiene el nombre único de este elemento de filtro.</span><span class="sxs-lookup"><span data-stu-id="d2a3c-122">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="d2a3c-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d2a3c-123">Child elements</span></span>

<span data-ttu-id="d2a3c-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d2a3c-124">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d2a3c-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d2a3c-125">Parent elements</span></span>

| <span data-ttu-id="d2a3c-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="d2a3c-126">Element</span></span> | <span data-ttu-id="d2a3c-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="d2a3c-127">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="d2a3c-128">\<routing></span><span class="sxs-lookup"><span data-stu-id="d2a3c-128">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="d2a3c-129">Una sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> que se usará al evaluar los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="d2a3c-129">A configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="d2a3c-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="d2a3c-130">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>
