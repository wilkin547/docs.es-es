---
title: <entries>
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: d3dae510ac62735138a24b8fb97a8acfffde1a98
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189973"
---
# \<entries>

<span data-ttu-id="0ae1c-101">Una entrada del enrutamiento que contiene las asignaciones entre los filtros del enrutamiento y los extremos de destino a los que enviar mensajes cuando coincida el filtro.</span><span class="sxs-lookup"><span data-stu-id="0ae1c-101">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTable>**](filtertable.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<entries>**  
  
## <a name="syntax"></a><span data-ttu-id="0ae1c-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0ae1c-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0ae1c-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0ae1c-103">Attributes and Elements</span></span>  

 <span data-ttu-id="0ae1c-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0ae1c-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0ae1c-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="0ae1c-105">Attributes</span></span>  

 <span data-ttu-id="0ae1c-106">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0ae1c-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0ae1c-107">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0ae1c-107">Child Elements</span></span>  
  
|<span data-ttu-id="0ae1c-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="0ae1c-108">Element</span></span>|<span data-ttu-id="0ae1c-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="0ae1c-109">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="0ae1c-110">Asigna un filtro a un punto de conexión de cliente que se definió previamente.</span><span class="sxs-lookup"><span data-stu-id="0ae1c-110">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="0ae1c-111">Los mensajes que coincidan con este filtro se enviarán a este destino.</span><span class="sxs-lookup"><span data-stu-id="0ae1c-111">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0ae1c-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0ae1c-112">Parent Elements</span></span>  
  
|<span data-ttu-id="0ae1c-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="0ae1c-113">Element</span></span>|<span data-ttu-id="0ae1c-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="0ae1c-114">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="0ae1c-115">Sección de configuración que contiene una tabla de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="0ae1c-115">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0ae1c-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0ae1c-116">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
