---
title: <filterTable>
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: f9e64e667befb70d617574b2a03c3e6bebb2a143
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925600"
---
# <a name="filtertable"></a><span data-ttu-id="0e66c-101">\<filterTable></span><span class="sxs-lookup"><span data-stu-id="0e66c-101">\<filterTable></span></span>
<span data-ttu-id="0e66c-102">Representa una tabla de enrutamiento que contiene una lista de filtros con respecto a la cual evaluar los mensajes y el punto de conexión del cliente al que enrutar los mensajes si el filtro se evalúa como true.</span><span class="sxs-lookup"><span data-stu-id="0e66c-102">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
 <span data-ttu-id="0e66c-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0e66c-103">\<system.serviceModel></span></span>  
<span data-ttu-id="0e66c-104">\<> de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="0e66c-104">\<routing></span></span>  
<span data-ttu-id="0e66c-105">\<routingTables></span><span class="sxs-lookup"><span data-stu-id="0e66c-105">\<routingTables></span></span>  
<span data-ttu-id="0e66c-106">\<> de tabla</span><span class="sxs-lookup"><span data-stu-id="0e66c-106">\<table></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e66c-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0e66c-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0e66c-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0e66c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0e66c-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0e66c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0e66c-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="0e66c-110">Attributes</span></span>  
  
|<span data-ttu-id="0e66c-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="0e66c-111">Element</span></span>|<span data-ttu-id="0e66c-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0e66c-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0e66c-113">name</span><span class="sxs-lookup"><span data-stu-id="0e66c-113">name</span></span>|<span data-ttu-id="0e66c-114">Cadena que contiene el nombre exclusivo de este elemento de configuración.</span><span class="sxs-lookup"><span data-stu-id="0e66c-114">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0e66c-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0e66c-115">Child Elements</span></span>  
  
|<span data-ttu-id="0e66c-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="0e66c-116">Element</span></span>|<span data-ttu-id="0e66c-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0e66c-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0e66c-118">\<filters></span><span class="sxs-lookup"><span data-stu-id="0e66c-118">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="0e66c-119">Asignaciones entre los filtros de enrutamiento y los puntos de conexión de destino a los que enviar mensajes cuando el filtro coincide.</span><span class="sxs-lookup"><span data-stu-id="0e66c-119">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0e66c-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0e66c-120">Parent Elements</span></span>  
  
|<span data-ttu-id="0e66c-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="0e66c-121">Element</span></span>|<span data-ttu-id="0e66c-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0e66c-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0e66c-123">\<> de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="0e66c-123">\<routing></span></span>](routing.md)|<span data-ttu-id="0e66c-124">Sección de configuración que contiene tablas de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="0e66c-124">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0e66c-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e66c-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
