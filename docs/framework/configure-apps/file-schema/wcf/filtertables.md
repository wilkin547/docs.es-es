---
title: <filterTables>
ms.date: 03/30/2017
ms.assetid: 41f1ac35-f559-473a-b2c3-8cc83a6a3831
ms.openlocfilehash: c68479737cefe542a10a404a8b31a4820a430ffb
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855202"
---
# <a name="filtertables"></a><span data-ttu-id="c910c-101">\<filterTables></span><span class="sxs-lookup"><span data-stu-id="c910c-101">\<filterTables></span></span>
<span data-ttu-id="c910c-102">Representa una sección de configuración para definir tablas de enrutamiento que contienen las asignaciones entre los filtros de enrutamiento y los extremos de destino a los que enviar mensajes cuando coincida el filtro.</span><span class="sxs-lookup"><span data-stu-id="c910c-102">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
<span data-ttu-id="c910c-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c910c-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c910c-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c910c-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c910c-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enrutamiento**](routing.md)</span><span class="sxs-lookup"><span data-stu-id="c910c-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="c910c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> filterTables**</span><span class="sxs-lookup"><span data-stu-id="c910c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filterTables>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c910c-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c910c-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c910c-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c910c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c910c-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c910c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c910c-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="c910c-110">Attributes</span></span>  
 <span data-ttu-id="c910c-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c910c-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c910c-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c910c-112">Child Elements</span></span>  
  
|<span data-ttu-id="c910c-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="c910c-113">Element</span></span>|<span data-ttu-id="c910c-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c910c-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c910c-115">\<filters></span><span class="sxs-lookup"><span data-stu-id="c910c-115">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="c910c-116">Tabla de enrutamiento que contiene las asignaciones entre los filtros de enrutamiento y los puntos de conexión de destino a los que enviar mensajes cuando coincida el filtro.</span><span class="sxs-lookup"><span data-stu-id="c910c-116">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c910c-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c910c-117">Parent Elements</span></span>  
  
|<span data-ttu-id="c910c-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="c910c-118">Element</span></span>|<span data-ttu-id="c910c-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c910c-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c910c-120">\<> de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="c910c-120">\<routing></span></span>](routing.md)|<span data-ttu-id="c910c-121">Sección de configuración que contiene filtros y tablas de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="c910c-121">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c910c-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="c910c-122">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>
