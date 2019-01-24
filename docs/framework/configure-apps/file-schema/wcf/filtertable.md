---
title: '&lt;filterTable&gt;'
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: 83339eebef9a4f1b7f69e0bd1dd16b8278a68258
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54534610"
---
# <a name="ltfiltertablegt"></a><span data-ttu-id="b7cc3-102">&lt;filterTable&gt;</span><span class="sxs-lookup"><span data-stu-id="b7cc3-102">&lt;filterTable&gt;</span></span>
<span data-ttu-id="b7cc3-103">Representa una tabla de enrutamiento que contiene una lista de filtros para evaluar los mensajes y el punto de conexión de cliente para enrutar mensajes a si el filtro se evalúa como true.</span><span class="sxs-lookup"><span data-stu-id="b7cc3-103">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
 <span data-ttu-id="b7cc3-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b7cc3-104">\<system.serviceModel></span></span>  
<span data-ttu-id="b7cc3-105">\<routing></span><span class="sxs-lookup"><span data-stu-id="b7cc3-105">\<routing></span></span>  
<span data-ttu-id="b7cc3-106">\<routingTables></span><span class="sxs-lookup"><span data-stu-id="b7cc3-106">\<routingTables></span></span>  
<span data-ttu-id="b7cc3-107">\<table></span><span class="sxs-lookup"><span data-stu-id="b7cc3-107">\<table></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7cc3-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b7cc3-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b7cc3-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b7cc3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b7cc3-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b7cc3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b7cc3-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="b7cc3-111">Attributes</span></span>  
  
|<span data-ttu-id="b7cc3-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="b7cc3-112">Element</span></span>|<span data-ttu-id="b7cc3-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7cc3-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b7cc3-114">name</span><span class="sxs-lookup"><span data-stu-id="b7cc3-114">name</span></span>|<span data-ttu-id="b7cc3-115">Cadena que contiene el nombre exclusivo de este elemento de configuración.</span><span class="sxs-lookup"><span data-stu-id="b7cc3-115">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b7cc3-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b7cc3-116">Child Elements</span></span>  
  
|<span data-ttu-id="b7cc3-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="b7cc3-117">Element</span></span>|<span data-ttu-id="b7cc3-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7cc3-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b7cc3-119">\<filters></span><span class="sxs-lookup"><span data-stu-id="b7cc3-119">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="b7cc3-120">Asignaciones entre los filtros de enrutamiento y los puntos de conexión de destino a los que enviar mensajes cuando el filtro coincide.</span><span class="sxs-lookup"><span data-stu-id="b7cc3-120">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b7cc3-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b7cc3-121">Parent Elements</span></span>  
  
|<span data-ttu-id="b7cc3-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="b7cc3-122">Element</span></span>|<span data-ttu-id="b7cc3-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7cc3-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b7cc3-124">\<routing></span><span class="sxs-lookup"><span data-stu-id="b7cc3-124">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="b7cc3-125">Sección de configuración que contiene tablas de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="b7cc3-125">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b7cc3-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7cc3-126">See also</span></span>
- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
