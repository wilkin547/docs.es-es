---
title: '&lt;add&gt; de &lt;entries&gt;'
ms.date: 03/30/2017
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
ms.openlocfilehash: 082b19cd4515deb19ee7190dfeb8ae04ab834830
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54645371"
---
# <a name="ltaddgt-of-ltentriesgt"></a><span data-ttu-id="99dd1-102">&lt;add&gt; de &lt;entries&gt;</span><span class="sxs-lookup"><span data-stu-id="99dd1-102">&lt;add&gt; of &lt;entries&gt;</span></span>
<span data-ttu-id="99dd1-103">Representa una entrada de enrutamiento que asigna un filtro a un punto de conexión de cliente que se definió previamente.</span><span class="sxs-lookup"><span data-stu-id="99dd1-103">Represents a routing entry that maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="99dd1-104">Los mensajes que coincidan con este filtro se enviarán a este destino.</span><span class="sxs-lookup"><span data-stu-id="99dd1-104">Messages matching this filter will be sent to this destination.</span></span>  
  
 <span data-ttu-id="99dd1-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="99dd1-105">\<system.serviceModel></span></span>  
<span data-ttu-id="99dd1-106">\<routing></span><span class="sxs-lookup"><span data-stu-id="99dd1-106">\<routing></span></span>  
<span data-ttu-id="99dd1-107">\<filterTables></span><span class="sxs-lookup"><span data-stu-id="99dd1-107">\<filterTables></span></span>  
<span data-ttu-id="99dd1-108">\<filterTable></span><span class="sxs-lookup"><span data-stu-id="99dd1-108">\<filterTable></span></span>  
<span data-ttu-id="99dd1-109">\<entries></span><span class="sxs-lookup"><span data-stu-id="99dd1-109">\<entries></span></span>  
<span data-ttu-id="99dd1-110">\<add></span><span class="sxs-lookup"><span data-stu-id="99dd1-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99dd1-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="99dd1-111">Syntax</span></span>  
  
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
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99dd1-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="99dd1-112">Attributes and Elements</span></span>  
 <span data-ttu-id="99dd1-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="99dd1-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99dd1-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="99dd1-114">Attributes</span></span>  
  
|<span data-ttu-id="99dd1-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="99dd1-115">Attribute</span></span>|<span data-ttu-id="99dd1-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="99dd1-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="99dd1-117">backupList</span><span class="sxs-lookup"><span data-stu-id="99dd1-117">backupList</span></span>|<span data-ttu-id="99dd1-118">Cadena que especifica una referencia a una lista auxiliar de extremos.</span><span class="sxs-lookup"><span data-stu-id="99dd1-118">A string that specifies a reference to a backup list of endpoints.</span></span>|  
|<span data-ttu-id="99dd1-119">extremo</span><span class="sxs-lookup"><span data-stu-id="99dd1-119">endpoint</span></span>|<span data-ttu-id="99dd1-120">Cadena que especifica una referencia a un extremo de cliente que recibirá mensajes que coincidan con el filtro especificado por el atributo `filterName`.</span><span class="sxs-lookup"><span data-stu-id="99dd1-120">A string that specifies a reference to a client endpoint that will receive messages that match the filter specified by the `filterName` attribute.</span></span>|  
|<span data-ttu-id="99dd1-121">filterName</span><span class="sxs-lookup"><span data-stu-id="99dd1-121">filterName</span></span>|<span data-ttu-id="99dd1-122">Cadena que especifica una referencia a un elemento de filtro.</span><span class="sxs-lookup"><span data-stu-id="99dd1-122">A string that specifies a reference to a filter element.</span></span>|  
|<span data-ttu-id="99dd1-123">priority</span><span class="sxs-lookup"><span data-stu-id="99dd1-123">priority</span></span>|<span data-ttu-id="99dd1-124">Entero que especifica la prioridad de esta entrada.</span><span class="sxs-lookup"><span data-stu-id="99dd1-124">An integer that specifies the priority of this entry.</span></span><br /><br /> <span data-ttu-id="99dd1-125">Las entradas en la tabla de enrutamiento se evaluarán según la prioridad, siendo 0 la prioridad más baja.</span><span class="sxs-lookup"><span data-stu-id="99dd1-125">Entries in the routing table will be evaluated based on priority, with 0 being the lowest priority.</span></span> <span data-ttu-id="99dd1-126">Todas las entradas para una prioridad concreta se evalúan simultáneamente; si no se encuentra ninguna entrada coincidente para la prioridad actual, se evaluará el nivel de prioridad siguiente.</span><span class="sxs-lookup"><span data-stu-id="99dd1-126">All entries for a specific priority are evaluated simultaneously, if no matching entry is found for the current priority, the next priority level will be evaluated.</span></span><br /><br /> <span data-ttu-id="99dd1-127">Este valor es opcional.</span><span class="sxs-lookup"><span data-stu-id="99dd1-127">This value is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="99dd1-128">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="99dd1-128">Child Elements</span></span>  
 <span data-ttu-id="99dd1-129">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="99dd1-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="99dd1-130">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="99dd1-130">Parent Elements</span></span>  
  
|<span data-ttu-id="99dd1-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="99dd1-131">Element</span></span>|<span data-ttu-id="99dd1-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="99dd1-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99dd1-133">\<routing></span><span class="sxs-lookup"><span data-stu-id="99dd1-133">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="99dd1-134">Sección de configuración que contiene entradas de asignación de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="99dd1-134">A configuration section that contains routing mapping entries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="99dd1-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="99dd1-135">See also</span></span>
- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
