---
title: <filterTable>
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: 918a365004efea82f4ef4c8868f6821d4bb6da18
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855195"
---
# \<filterTable>
<span data-ttu-id="dacef-101">Representa una tabla de enrutamiento que contiene una lista de filtros con respecto a la cual evaluar los mensajes y el extremo del cliente al que enrutar los mensajes a si el filtro se evalúa como verdadero.</span><span class="sxs-lookup"><span data-stu-id="dacef-101">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filterTable>**  
  
## <a name="syntax"></a><span data-ttu-id="dacef-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dacef-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dacef-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="dacef-103">Attributes and Elements</span></span>  
 <span data-ttu-id="dacef-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="dacef-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dacef-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="dacef-105">Attributes</span></span>  
  
|<span data-ttu-id="dacef-106">Elemento</span><span class="sxs-lookup"><span data-stu-id="dacef-106">Element</span></span>|<span data-ttu-id="dacef-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="dacef-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dacef-108">name</span><span class="sxs-lookup"><span data-stu-id="dacef-108">name</span></span>|<span data-ttu-id="dacef-109">Cadena que contiene el nombre exclusivo de este elemento de configuración.</span><span class="sxs-lookup"><span data-stu-id="dacef-109">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dacef-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="dacef-110">Child Elements</span></span>  
  
|<span data-ttu-id="dacef-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="dacef-111">Element</span></span>|<span data-ttu-id="dacef-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="dacef-112">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="dacef-113">Asignaciones entre los filtros de enrutamiento y los puntos de conexión de destino a los que enviar mensajes cuando el filtro coincide.</span><span class="sxs-lookup"><span data-stu-id="dacef-113">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dacef-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="dacef-114">Parent Elements</span></span>  
  
|<span data-ttu-id="dacef-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="dacef-115">Element</span></span>|<span data-ttu-id="dacef-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="dacef-116">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="dacef-117">Sección de configuración que contiene tablas de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="dacef-117">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dacef-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dacef-118">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
