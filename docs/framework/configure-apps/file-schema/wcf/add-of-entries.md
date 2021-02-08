---
description: 'Más información sobre: <add> de <entries>'
title: <add> de <entries>
ms.date: 03/30/2017
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
ms.openlocfilehash: 0be24fb9d2327d411368dd05afc21156dfaf3d3a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803976"
---
# <a name="add-of-entries"></a><span data-ttu-id="e7199-103">\<add> de \<entries></span><span class="sxs-lookup"><span data-stu-id="e7199-103">\<add> of \<entries></span></span>

<span data-ttu-id="e7199-104">Representa una entrada de enrutamiento que asigna un filtro a un extremo de cliente que se definió previamente.</span><span class="sxs-lookup"><span data-stu-id="e7199-104">Represents a routing entry that maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="e7199-105">Los mensajes que coincidan con este filtro se enviarán a este destino.</span><span class="sxs-lookup"><span data-stu-id="e7199-105">Messages matching this filter will be sent to this destination.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTable>**](filtertable.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<entries>**](entries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="e7199-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e7199-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e7199-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e7199-107">Attributes and Elements</span></span>  

 <span data-ttu-id="e7199-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e7199-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e7199-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="e7199-109">Attributes</span></span>  
  
|<span data-ttu-id="e7199-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="e7199-110">Attribute</span></span>|<span data-ttu-id="e7199-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7199-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e7199-112">backupList</span><span class="sxs-lookup"><span data-stu-id="e7199-112">backupList</span></span>|<span data-ttu-id="e7199-113">Cadena que especifica una referencia a una lista auxiliar de puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="e7199-113">A string that specifies a reference to a backup list of endpoints.</span></span>|  
|<span data-ttu-id="e7199-114">endpoint</span><span class="sxs-lookup"><span data-stu-id="e7199-114">endpoint</span></span>|<span data-ttu-id="e7199-115">Cadena que especifica una referencia a un extremo de cliente que recibirá mensajes que coincidan con el filtro especificado por el atributo `filterName`.</span><span class="sxs-lookup"><span data-stu-id="e7199-115">A string that specifies a reference to a client endpoint that will receive messages that match the filter specified by the `filterName` attribute.</span></span>|  
|<span data-ttu-id="e7199-116">filterName</span><span class="sxs-lookup"><span data-stu-id="e7199-116">filterName</span></span>|<span data-ttu-id="e7199-117">Cadena que especifica una referencia a un elemento de filtro.</span><span class="sxs-lookup"><span data-stu-id="e7199-117">A string that specifies a reference to a filter element.</span></span>|  
|<span data-ttu-id="e7199-118">priority</span><span class="sxs-lookup"><span data-stu-id="e7199-118">priority</span></span>|<span data-ttu-id="e7199-119">Entero que especifica la prioridad de esta entrada.</span><span class="sxs-lookup"><span data-stu-id="e7199-119">An integer that specifies the priority of this entry.</span></span><br /><br /> <span data-ttu-id="e7199-120">Las entradas en la tabla de enrutamiento se evaluarán según la prioridad, siendo 0 la prioridad más baja.</span><span class="sxs-lookup"><span data-stu-id="e7199-120">Entries in the routing table will be evaluated based on priority, with 0 being the lowest priority.</span></span> <span data-ttu-id="e7199-121">Todas las entradas para una prioridad concreta se evalúan simultáneamente; si no se encuentra ninguna entrada coincidente para la prioridad actual, se evaluará el nivel de prioridad siguiente.</span><span class="sxs-lookup"><span data-stu-id="e7199-121">All entries for a specific priority are evaluated simultaneously, if no matching entry is found for the current priority, the next priority level will be evaluated.</span></span><br /><br /> <span data-ttu-id="e7199-122">Este valor es opcional.</span><span class="sxs-lookup"><span data-stu-id="e7199-122">This value is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e7199-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e7199-123">Child Elements</span></span>  

 <span data-ttu-id="e7199-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e7199-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e7199-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e7199-125">Parent Elements</span></span>  
  
|<span data-ttu-id="e7199-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="e7199-126">Element</span></span>|<span data-ttu-id="e7199-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7199-127">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="e7199-128">Sección de configuración que contiene entradas de asignación de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="e7199-128">A configuration section that contains routing mapping entries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e7199-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7199-129">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
