---
title: <entries>
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: 5561cf61cef2258ec61bd32770538add1c69f5c1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59201798"
---
# <a name="entries"></a><span data-ttu-id="90485-101">\<entries></span><span class="sxs-lookup"><span data-stu-id="90485-101">\<entries></span></span>
<span data-ttu-id="90485-102">Una entrada del enrutamiento que contiene las asignaciones entre los filtros del enrutamiento y los extremos de destino a los que enviar mensajes cuando coincida el filtro.</span><span class="sxs-lookup"><span data-stu-id="90485-102">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="90485-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="90485-103">\<system.serviceModel></span></span>  
<span data-ttu-id="90485-104">\<routing></span><span class="sxs-lookup"><span data-stu-id="90485-104">\<routing></span></span>  
<span data-ttu-id="90485-105">\<routingTables></span><span class="sxs-lookup"><span data-stu-id="90485-105">\<routingTables></span></span>  
<span data-ttu-id="90485-106">\<table></span><span class="sxs-lookup"><span data-stu-id="90485-106">\<table></span></span>  
<span data-ttu-id="90485-107">\<entries></span><span class="sxs-lookup"><span data-stu-id="90485-107">\<entries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90485-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="90485-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="90485-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="90485-109">Attributes and Elements</span></span>  
 <span data-ttu-id="90485-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="90485-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="90485-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="90485-111">Attributes</span></span>  
 <span data-ttu-id="90485-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="90485-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="90485-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="90485-113">Child Elements</span></span>  
  
|<span data-ttu-id="90485-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="90485-114">Element</span></span>|<span data-ttu-id="90485-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="90485-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="90485-116">\<filters></span><span class="sxs-lookup"><span data-stu-id="90485-116">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="90485-117">Asigna un filtro a un punto de conexión de cliente que se definió previamente.</span><span class="sxs-lookup"><span data-stu-id="90485-117">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="90485-118">Los mensajes que coincidan con este filtro se enviarán a este destino.</span><span class="sxs-lookup"><span data-stu-id="90485-118">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="90485-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="90485-119">Parent Elements</span></span>  
  
|<span data-ttu-id="90485-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="90485-120">Element</span></span>|<span data-ttu-id="90485-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="90485-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="90485-122">\<routing></span><span class="sxs-lookup"><span data-stu-id="90485-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="90485-123">Sección de configuración que contiene una tabla de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="90485-123">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="90485-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="90485-124">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
