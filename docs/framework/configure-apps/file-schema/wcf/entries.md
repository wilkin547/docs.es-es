---
title: <entries>
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: 610ba29ec98f4b1f2a9b1db3542bcb3aefb46457
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925651"
---
# <a name="entries"></a><span data-ttu-id="c61aa-101">\<entradas ></span><span class="sxs-lookup"><span data-stu-id="c61aa-101">\<entries></span></span>
<span data-ttu-id="c61aa-102">Una entrada del enrutamiento que contiene las asignaciones entre los filtros del enrutamiento y los extremos de destino a los que enviar mensajes cuando coincida el filtro.</span><span class="sxs-lookup"><span data-stu-id="c61aa-102">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="c61aa-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c61aa-103">\<system.serviceModel></span></span>  
<span data-ttu-id="c61aa-104">\<> de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="c61aa-104">\<routing></span></span>  
<span data-ttu-id="c61aa-105">\<routingTables></span><span class="sxs-lookup"><span data-stu-id="c61aa-105">\<routingTables></span></span>  
<span data-ttu-id="c61aa-106">\<> de tabla</span><span class="sxs-lookup"><span data-stu-id="c61aa-106">\<table></span></span>  
<span data-ttu-id="c61aa-107">\<entradas ></span><span class="sxs-lookup"><span data-stu-id="c61aa-107">\<entries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c61aa-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c61aa-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c61aa-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c61aa-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c61aa-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c61aa-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c61aa-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="c61aa-111">Attributes</span></span>  
 <span data-ttu-id="c61aa-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c61aa-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c61aa-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c61aa-113">Child Elements</span></span>  
  
|<span data-ttu-id="c61aa-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="c61aa-114">Element</span></span>|<span data-ttu-id="c61aa-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c61aa-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c61aa-116">\<filters></span><span class="sxs-lookup"><span data-stu-id="c61aa-116">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="c61aa-117">Asigna un filtro a un punto de conexión de cliente que se definió previamente.</span><span class="sxs-lookup"><span data-stu-id="c61aa-117">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="c61aa-118">Los mensajes que coincidan con este filtro se enviarán a este destino.</span><span class="sxs-lookup"><span data-stu-id="c61aa-118">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c61aa-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c61aa-119">Parent Elements</span></span>  
  
|<span data-ttu-id="c61aa-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="c61aa-120">Element</span></span>|<span data-ttu-id="c61aa-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c61aa-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c61aa-122">\<> de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="c61aa-122">\<routing></span></span>](routing.md)|<span data-ttu-id="c61aa-123">Sección de configuración que contiene una tabla de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="c61aa-123">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c61aa-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="c61aa-124">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
