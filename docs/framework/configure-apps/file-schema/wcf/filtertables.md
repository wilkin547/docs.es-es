---
title: <filterTables>
ms.date: 03/30/2017
ms.assetid: 41f1ac35-f559-473a-b2c3-8cc83a6a3831
ms.openlocfilehash: c68479737cefe542a10a404a8b31a4820a430ffb
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855202"
---
# \<filterTables>
<span data-ttu-id="ea690-101">Representa una sección de configuración para definir tablas de enrutamiento que contienen las asignaciones entre los filtros de enrutamiento y los extremos de destino a los que enviar mensajes cuando coincida el filtro.</span><span class="sxs-lookup"><span data-stu-id="ea690-101">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filterTables>**  
  
## <a name="syntax"></a><span data-ttu-id="ea690-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ea690-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ea690-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ea690-103">Attributes and Elements</span></span>  
 <span data-ttu-id="ea690-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ea690-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ea690-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="ea690-105">Attributes</span></span>  
 <span data-ttu-id="ea690-106">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ea690-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ea690-107">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ea690-107">Child Elements</span></span>  
  
|<span data-ttu-id="ea690-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="ea690-108">Element</span></span>|<span data-ttu-id="ea690-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="ea690-109">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="ea690-110">Tabla de enrutamiento que contiene las asignaciones entre los filtros de enrutamiento y los puntos de conexión de destino a los que enviar mensajes cuando coincida el filtro.</span><span class="sxs-lookup"><span data-stu-id="ea690-110">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ea690-111">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ea690-111">Parent Elements</span></span>  
  
|<span data-ttu-id="ea690-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="ea690-112">Element</span></span>|<span data-ttu-id="ea690-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="ea690-113">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="ea690-114">Sección de configuración que contiene filtros y tablas de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="ea690-114">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ea690-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ea690-115">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>
