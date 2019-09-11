---
title: <filterTable>
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: 918a365004efea82f4ef4c8868f6821d4bb6da18
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855195"
---
# <a name="filtertable"></a><span data-ttu-id="c8877-101">\<filterTable></span><span class="sxs-lookup"><span data-stu-id="c8877-101">\<filterTable></span></span>
<span data-ttu-id="c8877-102">Representa una tabla de enrutamiento que contiene una lista de filtros con respecto a la cual evaluar los mensajes y el punto de conexión del cliente al que enrutar los mensajes si el filtro se evalúa como true.</span><span class="sxs-lookup"><span data-stu-id="c8877-102">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
<span data-ttu-id="c8877-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c8877-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c8877-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c8877-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c8877-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enrutamiento**](routing.md)</span><span class="sxs-lookup"><span data-stu-id="c8877-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="c8877-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> filterTables**](filtertables.md)</span><span class="sxs-lookup"><span data-stu-id="c8877-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)</span></span>\
<span data-ttu-id="c8877-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> filterTable**</span><span class="sxs-lookup"><span data-stu-id="c8877-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filterTable>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8877-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c8877-108">Syntax</span></span>  
  
```xml  
<routing>
  <filterTables>
     name="String">
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c8877-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c8877-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c8877-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c8877-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c8877-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="c8877-111">Attributes</span></span>  
  
|<span data-ttu-id="c8877-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="c8877-112">Element</span></span>|<span data-ttu-id="c8877-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c8877-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c8877-114">Nombre</span><span class="sxs-lookup"><span data-stu-id="c8877-114">name</span></span>|<span data-ttu-id="c8877-115">Cadena que contiene el nombre exclusivo de este elemento de configuración.</span><span class="sxs-lookup"><span data-stu-id="c8877-115">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c8877-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c8877-116">Child Elements</span></span>  
  
|<span data-ttu-id="c8877-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="c8877-117">Element</span></span>|<span data-ttu-id="c8877-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c8877-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c8877-119">\<filters></span><span class="sxs-lookup"><span data-stu-id="c8877-119">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="c8877-120">Asignaciones entre los filtros de enrutamiento y los puntos de conexión de destino a los que enviar mensajes cuando el filtro coincide.</span><span class="sxs-lookup"><span data-stu-id="c8877-120">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c8877-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c8877-121">Parent Elements</span></span>  
  
|<span data-ttu-id="c8877-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="c8877-122">Element</span></span>|<span data-ttu-id="c8877-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c8877-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c8877-124">\<> de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="c8877-124">\<routing></span></span>](routing.md)|<span data-ttu-id="c8877-125">Sección de configuración que contiene tablas de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="c8877-125">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c8877-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8877-126">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
