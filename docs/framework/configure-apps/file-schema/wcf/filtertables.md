---
title: '&lt;filterTables&gt;'
ms.date: 03/30/2017
ms.assetid: 41f1ac35-f559-473a-b2c3-8cc83a6a3831
ms.openlocfilehash: d73a3c25dbb4d2de41007149ef5864fcf37ad883
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54573064"
---
# <a name="ltfiltertablesgt"></a><span data-ttu-id="5a5ce-102">&lt;filterTables&gt;</span><span class="sxs-lookup"><span data-stu-id="5a5ce-102">&lt;filterTables&gt;</span></span>
<span data-ttu-id="5a5ce-103">Representa una sección de configuración para definir tablas de enrutamiento que contienen las asignaciones entre los filtros de enrutamiento y los puntos de conexión de destino a los que enviar mensajes cuando coincida el filtro.</span><span class="sxs-lookup"><span data-stu-id="5a5ce-103">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="5a5ce-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5a5ce-104">\<system.serviceModel></span></span>  
<span data-ttu-id="5a5ce-105">\<routing></span><span class="sxs-lookup"><span data-stu-id="5a5ce-105">\<routing></span></span>  
<span data-ttu-id="5a5ce-106">\<routingTables></span><span class="sxs-lookup"><span data-stu-id="5a5ce-106">\<routingTables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a5ce-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5a5ce-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5a5ce-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5a5ce-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5a5ce-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5a5ce-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5a5ce-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="5a5ce-110">Attributes</span></span>  
 <span data-ttu-id="5a5ce-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5a5ce-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5a5ce-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5a5ce-112">Child Elements</span></span>  
  
|<span data-ttu-id="5a5ce-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="5a5ce-113">Element</span></span>|<span data-ttu-id="5a5ce-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="5a5ce-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5a5ce-115">\<filters></span><span class="sxs-lookup"><span data-stu-id="5a5ce-115">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="5a5ce-116">Tabla de enrutamiento que contiene las asignaciones entre los filtros de enrutamiento y los puntos de conexión de destino a los que enviar mensajes cuando coincida el filtro.</span><span class="sxs-lookup"><span data-stu-id="5a5ce-116">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5a5ce-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5a5ce-117">Parent Elements</span></span>  
  
|<span data-ttu-id="5a5ce-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="5a5ce-118">Element</span></span>|<span data-ttu-id="5a5ce-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="5a5ce-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5a5ce-120">\<routing></span><span class="sxs-lookup"><span data-stu-id="5a5ce-120">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="5a5ce-121">Sección de configuración que contiene filtros y tablas de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="5a5ce-121">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5a5ce-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a5ce-122">See also</span></span>
- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>
