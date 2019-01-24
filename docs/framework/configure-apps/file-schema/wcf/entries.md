---
title: '&lt;entries&gt;'
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: 33f98cb4b138307622a14463ce5a3008058b6e31
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587065"
---
# <a name="ltentriesgt"></a><span data-ttu-id="65377-102">&lt;entries&gt;</span><span class="sxs-lookup"><span data-stu-id="65377-102">&lt;entries&gt;</span></span>
<span data-ttu-id="65377-103">Una entrada del enrutamiento que contiene las asignaciones entre los filtros del enrutamiento y los puntos de conexión de destino a los que enviar mensajes cuando coincida el filtro.</span><span class="sxs-lookup"><span data-stu-id="65377-103">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="65377-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="65377-104">\<system.serviceModel></span></span>  
<span data-ttu-id="65377-105">\<routing></span><span class="sxs-lookup"><span data-stu-id="65377-105">\<routing></span></span>  
<span data-ttu-id="65377-106">\<routingTables></span><span class="sxs-lookup"><span data-stu-id="65377-106">\<routingTables></span></span>  
<span data-ttu-id="65377-107">\<table></span><span class="sxs-lookup"><span data-stu-id="65377-107">\<table></span></span>  
<span data-ttu-id="65377-108">\<entries></span><span class="sxs-lookup"><span data-stu-id="65377-108">\<entries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65377-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="65377-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="65377-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="65377-110">Attributes and Elements</span></span>  
 <span data-ttu-id="65377-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="65377-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="65377-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="65377-112">Attributes</span></span>  
 <span data-ttu-id="65377-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="65377-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="65377-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="65377-114">Child Elements</span></span>  
  
|<span data-ttu-id="65377-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="65377-115">Element</span></span>|<span data-ttu-id="65377-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="65377-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="65377-117">\<filters></span><span class="sxs-lookup"><span data-stu-id="65377-117">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="65377-118">Asigna un filtro a un punto de conexión de cliente que se definió previamente.</span><span class="sxs-lookup"><span data-stu-id="65377-118">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="65377-119">Los mensajes que coincidan con este filtro se enviarán a este destino.</span><span class="sxs-lookup"><span data-stu-id="65377-119">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="65377-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="65377-120">Parent Elements</span></span>  
  
|<span data-ttu-id="65377-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="65377-121">Element</span></span>|<span data-ttu-id="65377-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="65377-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="65377-123">\<routing></span><span class="sxs-lookup"><span data-stu-id="65377-123">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="65377-124">Sección de configuración que contiene una tabla de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="65377-124">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="65377-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="65377-125">See also</span></span>
- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
