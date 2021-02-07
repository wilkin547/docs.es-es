---
description: 'Más información acerca de: <filterTables>'
title: <filterTables>
ms.date: 03/30/2017
ms.assetid: 41f1ac35-f559-473a-b2c3-8cc83a6a3831
ms.openlocfilehash: 932d0e162c3fdeba8b166d3adaaa73cc3b5293a9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664592"
---
# \<filterTables>

<span data-ttu-id="a3b5a-102">Representa una sección de configuración para definir tablas de enrutamiento que contienen las asignaciones entre los filtros de enrutamiento y los extremos de destino a los que enviar mensajes cuando coincida el filtro.</span><span class="sxs-lookup"><span data-stu-id="a3b5a-102">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filterTables>**  
  
## <a name="syntax"></a><span data-ttu-id="a3b5a-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a3b5a-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a3b5a-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a3b5a-104">Attributes and Elements</span></span>  

 <span data-ttu-id="a3b5a-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a3b5a-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a3b5a-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="a3b5a-106">Attributes</span></span>  

 <span data-ttu-id="a3b5a-107">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a3b5a-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a3b5a-108">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a3b5a-108">Child Elements</span></span>  
  
|<span data-ttu-id="a3b5a-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="a3b5a-109">Element</span></span>|<span data-ttu-id="a3b5a-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="a3b5a-110">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="a3b5a-111">Tabla de enrutamiento que contiene las asignaciones entre los filtros de enrutamiento y los puntos de conexión de destino a los que enviar mensajes cuando coincida el filtro.</span><span class="sxs-lookup"><span data-stu-id="a3b5a-111">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a3b5a-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a3b5a-112">Parent Elements</span></span>  
  
|<span data-ttu-id="a3b5a-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="a3b5a-113">Element</span></span>|<span data-ttu-id="a3b5a-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="a3b5a-114">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="a3b5a-115">Sección de configuración que contiene filtros y tablas de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="a3b5a-115">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a3b5a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3b5a-116">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>
