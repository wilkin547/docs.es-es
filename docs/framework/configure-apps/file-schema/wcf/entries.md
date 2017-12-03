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
ms.openlocfilehash: ef9c58a9b4ecd6db8b4efe116f6fafba01c3f6f5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltentriesgt"></a><span data-ttu-id="8813f-102">&lt;entradas&gt;</span><span class="sxs-lookup"><span data-stu-id="8813f-102">&lt;entries&gt;</span></span>
<span data-ttu-id="8813f-103">Una entrada del enrutamiento que contiene las asignaciones entre los filtros del enrutamiento y los puntos de conexión de destino a los que enviar mensajes cuando coincida el filtro.</span><span class="sxs-lookup"><span data-stu-id="8813f-103">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="8813f-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="8813f-104">\<system.serviceModel></span></span>  
<span data-ttu-id="8813f-105">\<enrutamiento ></span><span class="sxs-lookup"><span data-stu-id="8813f-105">\<routing></span></span>  
<span data-ttu-id="8813f-106">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="8813f-106">\<routingTables></span></span>  
<span data-ttu-id="8813f-107">\<tabla ></span><span class="sxs-lookup"><span data-stu-id="8813f-107">\<table></span></span>  
<span data-ttu-id="8813f-108">\<las entradas ></span><span class="sxs-lookup"><span data-stu-id="8813f-108">\<entries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8813f-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8813f-109">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8813f-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8813f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8813f-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8813f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8813f-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="8813f-112">Attributes</span></span>  
 <span data-ttu-id="8813f-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="8813f-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8813f-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8813f-114">Child Elements</span></span>  
  
|<span data-ttu-id="8813f-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="8813f-115">Element</span></span>|<span data-ttu-id="8813f-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="8813f-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8813f-117">\<filtros ></span><span class="sxs-lookup"><span data-stu-id="8813f-117">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="8813f-118">Asigna un filtro a un punto de conexión de cliente que se definió previamente.</span><span class="sxs-lookup"><span data-stu-id="8813f-118">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="8813f-119">Los mensajes que coincidan con este filtro se enviarán a este destino.</span><span class="sxs-lookup"><span data-stu-id="8813f-119">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8813f-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8813f-120">Parent Elements</span></span>  
  
|<span data-ttu-id="8813f-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="8813f-121">Element</span></span>|<span data-ttu-id="8813f-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="8813f-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8813f-123">\<enrutamiento ></span><span class="sxs-lookup"><span data-stu-id="8813f-123">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="8813f-124">Sección de configuración que contiene una tabla de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="8813f-124">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8813f-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="8813f-125">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>    
