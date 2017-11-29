---
title: '&lt;entradas&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9b6d8d1c3797d60b26443e07cc527ea8b86f526e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltentriesgt"></a><span data-ttu-id="e1f20-102">&lt;entradas&gt;</span><span class="sxs-lookup"><span data-stu-id="e1f20-102">&lt;entries&gt;</span></span>
<span data-ttu-id="e1f20-103">Una entrada del enrutamiento que contiene las asignaciones entre los filtros del enrutamiento y los puntos de conexión de destino a los que enviar mensajes cuando coincida el filtro.</span><span class="sxs-lookup"><span data-stu-id="e1f20-103">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="e1f20-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="e1f20-104">\<system.serviceModel></span></span>  
<span data-ttu-id="e1f20-105">\<enrutamiento ></span><span class="sxs-lookup"><span data-stu-id="e1f20-105">\<routing></span></span>  
<span data-ttu-id="e1f20-106">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="e1f20-106">\<routingTables></span></span>  
<span data-ttu-id="e1f20-107">\<tabla ></span><span class="sxs-lookup"><span data-stu-id="e1f20-107">\<table></span></span>  
<span data-ttu-id="e1f20-108">\<las entradas ></span><span class="sxs-lookup"><span data-stu-id="e1f20-108">\<entries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1f20-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e1f20-109">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e1f20-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e1f20-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e1f20-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e1f20-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e1f20-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="e1f20-112">Attributes</span></span>  
 <span data-ttu-id="e1f20-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e1f20-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e1f20-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e1f20-114">Child Elements</span></span>  
  
|<span data-ttu-id="e1f20-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="e1f20-115">Element</span></span>|<span data-ttu-id="e1f20-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="e1f20-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e1f20-117">\<filtros ></span><span class="sxs-lookup"><span data-stu-id="e1f20-117">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="e1f20-118">Asigna un filtro a un punto de conexión de cliente que se definió previamente.</span><span class="sxs-lookup"><span data-stu-id="e1f20-118">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="e1f20-119">Los mensajes que coincidan con este filtro se enviarán a este destino.</span><span class="sxs-lookup"><span data-stu-id="e1f20-119">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e1f20-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e1f20-120">Parent Elements</span></span>  
  
|<span data-ttu-id="e1f20-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="e1f20-121">Element</span></span>|<span data-ttu-id="e1f20-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="e1f20-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e1f20-123">\<enrutamiento ></span><span class="sxs-lookup"><span data-stu-id="e1f20-123">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="e1f20-124">Sección de configuración que contiene una tabla de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="e1f20-124">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e1f20-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1f20-125">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>    
