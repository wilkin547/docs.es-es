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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b1bd6fd679d3f6440ff685c8cd2646b1fa0a13e2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltentriesgt"></a><span data-ttu-id="b38eb-102">&lt;entradas&gt;</span><span class="sxs-lookup"><span data-stu-id="b38eb-102">&lt;entries&gt;</span></span>
<span data-ttu-id="b38eb-103">Una entrada del enrutamiento que contiene las asignaciones entre los filtros del enrutamiento y los puntos de conexión de destino a los que enviar mensajes cuando coincida el filtro.</span><span class="sxs-lookup"><span data-stu-id="b38eb-103">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="b38eb-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="b38eb-104">\<system.serviceModel></span></span>  
<span data-ttu-id="b38eb-105">\<enrutamiento ></span><span class="sxs-lookup"><span data-stu-id="b38eb-105">\<routing></span></span>  
<span data-ttu-id="b38eb-106">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="b38eb-106">\<routingTables></span></span>  
<span data-ttu-id="b38eb-107">\<tabla ></span><span class="sxs-lookup"><span data-stu-id="b38eb-107">\<table></span></span>  
<span data-ttu-id="b38eb-108">\<las entradas ></span><span class="sxs-lookup"><span data-stu-id="b38eb-108">\<entries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b38eb-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b38eb-109">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b38eb-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b38eb-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b38eb-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b38eb-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b38eb-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="b38eb-112">Attributes</span></span>  
 <span data-ttu-id="b38eb-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b38eb-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b38eb-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b38eb-114">Child Elements</span></span>  
  
|<span data-ttu-id="b38eb-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="b38eb-115">Element</span></span>|<span data-ttu-id="b38eb-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="b38eb-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b38eb-117">\<filtros ></span><span class="sxs-lookup"><span data-stu-id="b38eb-117">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="b38eb-118">Asigna un filtro a un punto de conexión de cliente que se definió previamente.</span><span class="sxs-lookup"><span data-stu-id="b38eb-118">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="b38eb-119">Los mensajes que coincidan con este filtro se enviarán a este destino.</span><span class="sxs-lookup"><span data-stu-id="b38eb-119">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b38eb-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b38eb-120">Parent Elements</span></span>  
  
|<span data-ttu-id="b38eb-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="b38eb-121">Element</span></span>|<span data-ttu-id="b38eb-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="b38eb-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b38eb-123">\<enrutamiento ></span><span class="sxs-lookup"><span data-stu-id="b38eb-123">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="b38eb-124">Sección de configuración que contiene una tabla de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="b38eb-124">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b38eb-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="b38eb-125">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>    
