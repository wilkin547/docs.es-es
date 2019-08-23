---
title: <filterTables>
ms.date: 03/30/2017
ms.assetid: 41f1ac35-f559-473a-b2c3-8cc83a6a3831
ms.openlocfilehash: b0a344aa69085d50087eefc746236bc8ceacadaa
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918853"
---
# <a name="filtertables"></a><span data-ttu-id="2bb5e-101">\<filterTables></span><span class="sxs-lookup"><span data-stu-id="2bb5e-101">\<filterTables></span></span>
<span data-ttu-id="2bb5e-102">Representa una sección de configuración para definir tablas de enrutamiento que contienen las asignaciones entre los filtros de enrutamiento y los extremos de destino a los que enviar mensajes cuando coincida el filtro.</span><span class="sxs-lookup"><span data-stu-id="2bb5e-102">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="2bb5e-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2bb5e-103">\<system.serviceModel></span></span>  
<span data-ttu-id="2bb5e-104">\<> de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="2bb5e-104">\<routing></span></span>  
<span data-ttu-id="2bb5e-105">\<routingTables></span><span class="sxs-lookup"><span data-stu-id="2bb5e-105">\<routingTables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bb5e-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2bb5e-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2bb5e-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2bb5e-107">Attributes and Elements</span></span>  
 <span data-ttu-id="2bb5e-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2bb5e-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2bb5e-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="2bb5e-109">Attributes</span></span>  
 <span data-ttu-id="2bb5e-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2bb5e-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2bb5e-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2bb5e-111">Child Elements</span></span>  
  
|<span data-ttu-id="2bb5e-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="2bb5e-112">Element</span></span>|<span data-ttu-id="2bb5e-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="2bb5e-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2bb5e-114">\<filters></span><span class="sxs-lookup"><span data-stu-id="2bb5e-114">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="2bb5e-115">Tabla de enrutamiento que contiene las asignaciones entre los filtros de enrutamiento y los puntos de conexión de destino a los que enviar mensajes cuando coincida el filtro.</span><span class="sxs-lookup"><span data-stu-id="2bb5e-115">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2bb5e-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2bb5e-116">Parent Elements</span></span>  
  
|<span data-ttu-id="2bb5e-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="2bb5e-117">Element</span></span>|<span data-ttu-id="2bb5e-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="2bb5e-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2bb5e-119">\<> de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="2bb5e-119">\<routing></span></span>](routing.md)|<span data-ttu-id="2bb5e-120">Sección de configuración que contiene filtros y tablas de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="2bb5e-120">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2bb5e-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="2bb5e-121">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>
