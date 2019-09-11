---
title: <add> de <entries>
ms.date: 03/30/2017
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
ms.openlocfilehash: 23b0a825ea593f85ade870d5b93367571eaa3ec0
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850512"
---
# <a name="add-of-entries"></a><span data-ttu-id="a99de-102">\<Agregar > de \<entradas ></span><span class="sxs-lookup"><span data-stu-id="a99de-102">\<add> of \<entries></span></span>
<span data-ttu-id="a99de-103">Representa una entrada de enrutamiento que asigna un filtro a un extremo de cliente que se definió previamente.</span><span class="sxs-lookup"><span data-stu-id="a99de-103">Represents a routing entry that maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="a99de-104">Los mensajes que coincidan con este filtro se enviarán a este destino.</span><span class="sxs-lookup"><span data-stu-id="a99de-104">Messages matching this filter will be sent to this destination.</span></span>  
  
<span data-ttu-id="a99de-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a99de-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a99de-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a99de-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a99de-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enrutamiento**](routing.md)</span><span class="sxs-lookup"><span data-stu-id="a99de-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="a99de-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> filterTables**](filtertables.md)</span><span class="sxs-lookup"><span data-stu-id="a99de-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)</span></span>\
<span data-ttu-id="a99de-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> filterTable**](filtertable.md)</span><span class="sxs-lookup"><span data-stu-id="a99de-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTable>**](filtertable.md)</span></span>\
<span data-ttu-id="a99de-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<entradas >** ](entries.md)</span><span class="sxs-lookup"><span data-stu-id="a99de-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<entries>**](entries.md)</span></span>\
<span data-ttu-id="a99de-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Agregar >**</span><span class="sxs-lookup"><span data-stu-id="a99de-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a99de-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a99de-112">Syntax</span></span>  
  
```xml  
<routing>
  <filterTables>
    <filterTable name="String">
      <entries>
        <add backupList="String"
             endpointName="String"
             filterName="String"
             priority="Integer" />
      </entries>
    </filterTable>
  </filterTables>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a99de-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a99de-113">Attributes and Elements</span></span>  
 <span data-ttu-id="a99de-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a99de-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a99de-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="a99de-115">Attributes</span></span>  
  
|<span data-ttu-id="a99de-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="a99de-116">Attribute</span></span>|<span data-ttu-id="a99de-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a99de-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a99de-118">backupList</span><span class="sxs-lookup"><span data-stu-id="a99de-118">backupList</span></span>|<span data-ttu-id="a99de-119">Cadena que especifica una referencia a una lista auxiliar de puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="a99de-119">A string that specifies a reference to a backup list of endpoints.</span></span>|  
|<span data-ttu-id="a99de-120">endpoint</span><span class="sxs-lookup"><span data-stu-id="a99de-120">endpoint</span></span>|<span data-ttu-id="a99de-121">Cadena que especifica una referencia a un extremo de cliente que recibirá mensajes que coincidan con el filtro especificado por el atributo `filterName`.</span><span class="sxs-lookup"><span data-stu-id="a99de-121">A string that specifies a reference to a client endpoint that will receive messages that match the filter specified by the `filterName` attribute.</span></span>|  
|<span data-ttu-id="a99de-122">filterName</span><span class="sxs-lookup"><span data-stu-id="a99de-122">filterName</span></span>|<span data-ttu-id="a99de-123">Cadena que especifica una referencia a un elemento de filtro.</span><span class="sxs-lookup"><span data-stu-id="a99de-123">A string that specifies a reference to a filter element.</span></span>|  
|<span data-ttu-id="a99de-124">prioridad</span><span class="sxs-lookup"><span data-stu-id="a99de-124">priority</span></span>|<span data-ttu-id="a99de-125">Entero que especifica la prioridad de esta entrada.</span><span class="sxs-lookup"><span data-stu-id="a99de-125">An integer that specifies the priority of this entry.</span></span><br /><br /> <span data-ttu-id="a99de-126">Las entradas en la tabla de enrutamiento se evaluarán según la prioridad, siendo 0 la prioridad más baja.</span><span class="sxs-lookup"><span data-stu-id="a99de-126">Entries in the routing table will be evaluated based on priority, with 0 being the lowest priority.</span></span> <span data-ttu-id="a99de-127">Todas las entradas para una prioridad concreta se evalúan simultáneamente; si no se encuentra ninguna entrada coincidente para la prioridad actual, se evaluará el nivel de prioridad siguiente.</span><span class="sxs-lookup"><span data-stu-id="a99de-127">All entries for a specific priority are evaluated simultaneously, if no matching entry is found for the current priority, the next priority level will be evaluated.</span></span><br /><br /> <span data-ttu-id="a99de-128">Este valor es opcional.</span><span class="sxs-lookup"><span data-stu-id="a99de-128">This value is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a99de-129">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a99de-129">Child Elements</span></span>  
 <span data-ttu-id="a99de-130">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a99de-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a99de-131">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a99de-131">Parent Elements</span></span>  
  
|<span data-ttu-id="a99de-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="a99de-132">Element</span></span>|<span data-ttu-id="a99de-133">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a99de-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a99de-134">\<> de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="a99de-134">\<routing></span></span>](routing.md)|<span data-ttu-id="a99de-135">Sección de configuración que contiene entradas de asignación de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="a99de-135">A configuration section that contains routing mapping entries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a99de-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="a99de-136">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
