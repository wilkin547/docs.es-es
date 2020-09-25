---
title: <filterTables>
ms.date: 03/30/2017
ms.assetid: 41f1ac35-f559-473a-b2c3-8cc83a6a3831
ms.openlocfilehash: faa26ca108010330475725f83dfd0c6668cfc6b1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178208"
---
# \<filterTables>

<span data-ttu-id="48606-101">Representa una sección de configuración para definir tablas de enrutamiento que contienen las asignaciones entre los filtros de enrutamiento y los extremos de destino a los que enviar mensajes cuando coincida el filtro.</span><span class="sxs-lookup"><span data-stu-id="48606-101">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filterTables>**  
  
## <a name="syntax"></a><span data-ttu-id="48606-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="48606-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="48606-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="48606-103">Attributes and Elements</span></span>  

 <span data-ttu-id="48606-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="48606-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="48606-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="48606-105">Attributes</span></span>  

 <span data-ttu-id="48606-106">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="48606-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="48606-107">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="48606-107">Child Elements</span></span>  
  
|<span data-ttu-id="48606-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="48606-108">Element</span></span>|<span data-ttu-id="48606-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="48606-109">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="48606-110">Tabla de enrutamiento que contiene las asignaciones entre los filtros de enrutamiento y los puntos de conexión de destino a los que enviar mensajes cuando coincida el filtro.</span><span class="sxs-lookup"><span data-stu-id="48606-110">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="48606-111">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="48606-111">Parent Elements</span></span>  
  
|<span data-ttu-id="48606-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="48606-112">Element</span></span>|<span data-ttu-id="48606-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="48606-113">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="48606-114">Sección de configuración que contiene filtros y tablas de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="48606-114">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="48606-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="48606-115">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>
