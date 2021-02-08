---
description: 'Más información acerca de: <entries>'
title: <entries>
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: e5aefce4328c341b6d132765c8e726910241aae1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782109"
---
# \<entries>

<span data-ttu-id="af0ab-102">Una entrada del enrutamiento que contiene las asignaciones entre los filtros del enrutamiento y los extremos de destino a los que enviar mensajes cuando coincida el filtro.</span><span class="sxs-lookup"><span data-stu-id="af0ab-102">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTable>**](filtertable.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<entries>**  
  
## <a name="syntax"></a><span data-ttu-id="af0ab-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="af0ab-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af0ab-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="af0ab-104">Attributes and Elements</span></span>  

 <span data-ttu-id="af0ab-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="af0ab-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af0ab-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="af0ab-106">Attributes</span></span>  

 <span data-ttu-id="af0ab-107">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="af0ab-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="af0ab-108">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="af0ab-108">Child Elements</span></span>  
  
|<span data-ttu-id="af0ab-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="af0ab-109">Element</span></span>|<span data-ttu-id="af0ab-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="af0ab-110">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="af0ab-111">Asigna un filtro a un punto de conexión de cliente que se definió previamente.</span><span class="sxs-lookup"><span data-stu-id="af0ab-111">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="af0ab-112">Los mensajes que coincidan con este filtro se enviarán a este destino.</span><span class="sxs-lookup"><span data-stu-id="af0ab-112">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="af0ab-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="af0ab-113">Parent Elements</span></span>  
  
|<span data-ttu-id="af0ab-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="af0ab-114">Element</span></span>|<span data-ttu-id="af0ab-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="af0ab-115">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="af0ab-116">Sección de configuración que contiene una tabla de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="af0ab-116">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="af0ab-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="af0ab-117">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
