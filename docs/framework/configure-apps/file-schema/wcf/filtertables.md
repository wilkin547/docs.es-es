---
title: '&lt;filterTables&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 41f1ac35-f559-473a-b2c3-8cc83a6a3831
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 05c8d3f5ce5a01e5a88f37fce43f3b4f8d260812
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltfiltertablesgt"></a><span data-ttu-id="6af58-102">&lt;filterTables&gt;</span><span class="sxs-lookup"><span data-stu-id="6af58-102">&lt;filterTables&gt;</span></span>
<span data-ttu-id="6af58-103">Representa una sección de configuración para definir tablas de enrutamiento que contienen las asignaciones entre los filtros de enrutamiento y los puntos de conexión de destino a los que enviar mensajes cuando coincida el filtro.</span><span class="sxs-lookup"><span data-stu-id="6af58-103">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="6af58-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="6af58-104">\<system.serviceModel></span></span>  
<span data-ttu-id="6af58-105">\<enrutamiento ></span><span class="sxs-lookup"><span data-stu-id="6af58-105">\<routing></span></span>  
<span data-ttu-id="6af58-106">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="6af58-106">\<routingTables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6af58-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6af58-107">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6af58-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6af58-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6af58-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6af58-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6af58-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="6af58-110">Attributes</span></span>  
 <span data-ttu-id="6af58-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6af58-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6af58-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6af58-112">Child Elements</span></span>  
  
|<span data-ttu-id="6af58-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="6af58-113">Element</span></span>|<span data-ttu-id="6af58-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="6af58-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6af58-115">\<filtros ></span><span class="sxs-lookup"><span data-stu-id="6af58-115">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="6af58-116">Tabla de enrutamiento que contiene las asignaciones entre los filtros de enrutamiento y los puntos de conexión de destino a los que enviar mensajes cuando coincida el filtro.</span><span class="sxs-lookup"><span data-stu-id="6af58-116">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6af58-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6af58-117">Parent Elements</span></span>  
  
|<span data-ttu-id="6af58-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="6af58-118">Element</span></span>|<span data-ttu-id="6af58-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="6af58-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6af58-120">\<enrutamiento ></span><span class="sxs-lookup"><span data-stu-id="6af58-120">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="6af58-121">Sección de configuración que contiene filtros y tablas de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="6af58-121">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6af58-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="6af58-122">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>    
