---
title: <entries>
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: ffe2538fa2c3cb680285cfaa68c975c0f9d4b1bd
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855279"
---
# <a name="entries"></a><span data-ttu-id="fb2ea-101">\<entradas ></span><span class="sxs-lookup"><span data-stu-id="fb2ea-101">\<entries></span></span>
<span data-ttu-id="fb2ea-102">Una entrada del enrutamiento que contiene las asignaciones entre los filtros del enrutamiento y los extremos de destino a los que enviar mensajes cuando coincida el filtro.</span><span class="sxs-lookup"><span data-stu-id="fb2ea-102">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
<span data-ttu-id="fb2ea-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fb2ea-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fb2ea-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="fb2ea-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="fb2ea-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enrutamiento**](routing.md)</span><span class="sxs-lookup"><span data-stu-id="fb2ea-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="fb2ea-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> filterTables**](filtertables.md)</span><span class="sxs-lookup"><span data-stu-id="fb2ea-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)</span></span>\
<span data-ttu-id="fb2ea-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> filterTable**](filtertable.md)</span><span class="sxs-lookup"><span data-stu-id="fb2ea-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTable>**](filtertable.md)</span></span>\
<span data-ttu-id="fb2ea-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<entradas >**</span><span class="sxs-lookup"><span data-stu-id="fb2ea-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<entries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb2ea-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fb2ea-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fb2ea-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fb2ea-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fb2ea-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fb2ea-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fb2ea-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="fb2ea-112">Attributes</span></span>  
 <span data-ttu-id="fb2ea-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="fb2ea-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fb2ea-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fb2ea-114">Child Elements</span></span>  
  
|<span data-ttu-id="fb2ea-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="fb2ea-115">Element</span></span>|<span data-ttu-id="fb2ea-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="fb2ea-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fb2ea-117">\<filters></span><span class="sxs-lookup"><span data-stu-id="fb2ea-117">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="fb2ea-118">Asigna un filtro a un punto de conexión de cliente que se definió previamente.</span><span class="sxs-lookup"><span data-stu-id="fb2ea-118">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="fb2ea-119">Los mensajes que coincidan con este filtro se enviarán a este destino.</span><span class="sxs-lookup"><span data-stu-id="fb2ea-119">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fb2ea-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fb2ea-120">Parent Elements</span></span>  
  
|<span data-ttu-id="fb2ea-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="fb2ea-121">Element</span></span>|<span data-ttu-id="fb2ea-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="fb2ea-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fb2ea-123">\<> de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="fb2ea-123">\<routing></span></span>](routing.md)|<span data-ttu-id="fb2ea-124">Sección de configuración que contiene una tabla de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="fb2ea-124">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fb2ea-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb2ea-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
