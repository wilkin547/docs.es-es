---
title: <add> de <entries>
ms.date: 03/30/2017
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
ms.openlocfilehash: 156d8b8d9d0eb05efbf306434ab4555a98bc317e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149054"
---
# <a name="add-of-entries"></a><span data-ttu-id="e29a3-102">\<add> de \<entries></span><span class="sxs-lookup"><span data-stu-id="e29a3-102">\<add> of \<entries></span></span>

<span data-ttu-id="e29a3-103">Representa una entrada de enrutamiento que asigna un filtro a un extremo de cliente que se definió previamente.</span><span class="sxs-lookup"><span data-stu-id="e29a3-103">Represents a routing entry that maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="e29a3-104">Los mensajes que coincidan con este filtro se enviarán a este destino.</span><span class="sxs-lookup"><span data-stu-id="e29a3-104">Messages matching this filter will be sent to this destination.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTable>**](filtertable.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<entries>**](entries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="e29a3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e29a3-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e29a3-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e29a3-106">Attributes and Elements</span></span>  

 <span data-ttu-id="e29a3-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e29a3-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e29a3-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="e29a3-108">Attributes</span></span>  
  
|<span data-ttu-id="e29a3-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="e29a3-109">Attribute</span></span>|<span data-ttu-id="e29a3-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="e29a3-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e29a3-111">backupList</span><span class="sxs-lookup"><span data-stu-id="e29a3-111">backupList</span></span>|<span data-ttu-id="e29a3-112">Cadena que especifica una referencia a una lista auxiliar de puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="e29a3-112">A string that specifies a reference to a backup list of endpoints.</span></span>|  
|<span data-ttu-id="e29a3-113">endpoint</span><span class="sxs-lookup"><span data-stu-id="e29a3-113">endpoint</span></span>|<span data-ttu-id="e29a3-114">Cadena que especifica una referencia a un extremo de cliente que recibirá mensajes que coincidan con el filtro especificado por el atributo `filterName`.</span><span class="sxs-lookup"><span data-stu-id="e29a3-114">A string that specifies a reference to a client endpoint that will receive messages that match the filter specified by the `filterName` attribute.</span></span>|  
|<span data-ttu-id="e29a3-115">filterName</span><span class="sxs-lookup"><span data-stu-id="e29a3-115">filterName</span></span>|<span data-ttu-id="e29a3-116">Cadena que especifica una referencia a un elemento de filtro.</span><span class="sxs-lookup"><span data-stu-id="e29a3-116">A string that specifies a reference to a filter element.</span></span>|  
|<span data-ttu-id="e29a3-117">priority</span><span class="sxs-lookup"><span data-stu-id="e29a3-117">priority</span></span>|<span data-ttu-id="e29a3-118">Entero que especifica la prioridad de esta entrada.</span><span class="sxs-lookup"><span data-stu-id="e29a3-118">An integer that specifies the priority of this entry.</span></span><br /><br /> <span data-ttu-id="e29a3-119">Las entradas en la tabla de enrutamiento se evaluarán según la prioridad, siendo 0 la prioridad más baja.</span><span class="sxs-lookup"><span data-stu-id="e29a3-119">Entries in the routing table will be evaluated based on priority, with 0 being the lowest priority.</span></span> <span data-ttu-id="e29a3-120">Todas las entradas para una prioridad concreta se evalúan simultáneamente; si no se encuentra ninguna entrada coincidente para la prioridad actual, se evaluará el nivel de prioridad siguiente.</span><span class="sxs-lookup"><span data-stu-id="e29a3-120">All entries for a specific priority are evaluated simultaneously, if no matching entry is found for the current priority, the next priority level will be evaluated.</span></span><br /><br /> <span data-ttu-id="e29a3-121">Este valor es opcional.</span><span class="sxs-lookup"><span data-stu-id="e29a3-121">This value is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e29a3-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e29a3-122">Child Elements</span></span>  

 <span data-ttu-id="e29a3-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e29a3-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e29a3-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e29a3-124">Parent Elements</span></span>  
  
|<span data-ttu-id="e29a3-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="e29a3-125">Element</span></span>|<span data-ttu-id="e29a3-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="e29a3-126">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="e29a3-127">Sección de configuración que contiene entradas de asignación de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="e29a3-127">A configuration section that contains routing mapping entries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e29a3-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="e29a3-128">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
