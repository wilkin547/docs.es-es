---
title: <filterTable>
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: 4e5c7d56e35afe3001f4c70064adbfef7702c720
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673217"
---
# <a name="filtertable"></a><span data-ttu-id="44620-101">\<filterTable></span><span class="sxs-lookup"><span data-stu-id="44620-101">\<filterTable></span></span>
<span data-ttu-id="44620-102">Representa una tabla de enrutamiento que contiene una lista de filtros para evaluar los mensajes y el punto de conexión de cliente para enrutar mensajes a si el filtro se evalúa como true.</span><span class="sxs-lookup"><span data-stu-id="44620-102">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
 <span data-ttu-id="44620-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="44620-103">\<system.serviceModel></span></span>  
<span data-ttu-id="44620-104">\<routing></span><span class="sxs-lookup"><span data-stu-id="44620-104">\<routing></span></span>  
<span data-ttu-id="44620-105">\<routingTables></span><span class="sxs-lookup"><span data-stu-id="44620-105">\<routingTables></span></span>  
<span data-ttu-id="44620-106">\<table></span><span class="sxs-lookup"><span data-stu-id="44620-106">\<table></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44620-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="44620-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="44620-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="44620-108">Attributes and Elements</span></span>  
 <span data-ttu-id="44620-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="44620-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="44620-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="44620-110">Attributes</span></span>  
  
|<span data-ttu-id="44620-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="44620-111">Element</span></span>|<span data-ttu-id="44620-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="44620-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="44620-113">name</span><span class="sxs-lookup"><span data-stu-id="44620-113">name</span></span>|<span data-ttu-id="44620-114">Cadena que contiene el nombre exclusivo de este elemento de configuración.</span><span class="sxs-lookup"><span data-stu-id="44620-114">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="44620-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="44620-115">Child Elements</span></span>  
  
|<span data-ttu-id="44620-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="44620-116">Element</span></span>|<span data-ttu-id="44620-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="44620-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="44620-118">\<filters></span><span class="sxs-lookup"><span data-stu-id="44620-118">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="44620-119">Asignaciones entre los filtros de enrutamiento y los puntos de conexión de destino a los que enviar mensajes cuando el filtro coincide.</span><span class="sxs-lookup"><span data-stu-id="44620-119">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="44620-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="44620-120">Parent Elements</span></span>  
  
|<span data-ttu-id="44620-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="44620-121">Element</span></span>|<span data-ttu-id="44620-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="44620-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="44620-123">\<routing></span><span class="sxs-lookup"><span data-stu-id="44620-123">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="44620-124">Sección de configuración que contiene tablas de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="44620-124">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="44620-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="44620-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
