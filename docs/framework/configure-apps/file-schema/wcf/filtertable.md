---
title: '&lt;filterTable&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 96425604fab8f70456ea1e0d97efb2c3bf843224
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltfiltertablegt"></a><span data-ttu-id="99472-102">&lt;filterTable&gt;</span><span class="sxs-lookup"><span data-stu-id="99472-102">&lt;filterTable&gt;</span></span>
<span data-ttu-id="99472-103">Representa una tabla de enrutamiento que contiene una lista de filtros para evaluar los mensajes con respecto a y el punto de conexión de cliente para enrutar mensajes a si el filtro se evalúa como true.</span><span class="sxs-lookup"><span data-stu-id="99472-103">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
 <span data-ttu-id="99472-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="99472-104">\<system.serviceModel></span></span>  
<span data-ttu-id="99472-105">\<enrutamiento ></span><span class="sxs-lookup"><span data-stu-id="99472-105">\<routing></span></span>  
<span data-ttu-id="99472-106">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="99472-106">\<routingTables></span></span>  
<span data-ttu-id="99472-107">\<tabla ></span><span class="sxs-lookup"><span data-stu-id="99472-107">\<table></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99472-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="99472-108">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="99472-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="99472-109">Attributes and Elements</span></span>  
 <span data-ttu-id="99472-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="99472-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99472-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="99472-111">Attributes</span></span>  
  
|<span data-ttu-id="99472-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="99472-112">Element</span></span>|<span data-ttu-id="99472-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="99472-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="99472-114">name</span><span class="sxs-lookup"><span data-stu-id="99472-114">name</span></span>|<span data-ttu-id="99472-115">Cadena que contiene el nombre exclusivo de este elemento de configuración.</span><span class="sxs-lookup"><span data-stu-id="99472-115">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="99472-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="99472-116">Child Elements</span></span>  
  
|<span data-ttu-id="99472-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="99472-117">Element</span></span>|<span data-ttu-id="99472-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="99472-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99472-119">\<filtros ></span><span class="sxs-lookup"><span data-stu-id="99472-119">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="99472-120">Asignaciones entre los filtros de enrutamiento y los puntos de conexión de destino a los que enviar mensajes cuando el filtro coincide.</span><span class="sxs-lookup"><span data-stu-id="99472-120">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="99472-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="99472-121">Parent Elements</span></span>  
  
|<span data-ttu-id="99472-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="99472-122">Element</span></span>|<span data-ttu-id="99472-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="99472-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99472-124">\<enrutamiento ></span><span class="sxs-lookup"><span data-stu-id="99472-124">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="99472-125">Sección de configuración que contiene tablas de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="99472-125">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="99472-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="99472-126">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>    
