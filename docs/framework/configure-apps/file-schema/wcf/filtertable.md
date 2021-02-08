---
description: 'Más información acerca de: <filterTable>'
title: <filterTable>
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: 2051bb0e778e5676f39d91b7d7ba415fd7e523af
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782044"
---
# \<filterTable>

<span data-ttu-id="307e7-102">Representa una tabla de enrutamiento que contiene una lista de filtros con respecto a la cual evaluar los mensajes y el extremo del cliente al que enrutar los mensajes a si el filtro se evalúa como verdadero.</span><span class="sxs-lookup"><span data-stu-id="307e7-102">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filterTable>**  
  
## <a name="syntax"></a><span data-ttu-id="307e7-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="307e7-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="307e7-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="307e7-104">Attributes and Elements</span></span>  

 <span data-ttu-id="307e7-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="307e7-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="307e7-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="307e7-106">Attributes</span></span>  
  
|<span data-ttu-id="307e7-107">Elemento</span><span class="sxs-lookup"><span data-stu-id="307e7-107">Element</span></span>|<span data-ttu-id="307e7-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="307e7-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="307e7-109">name</span><span class="sxs-lookup"><span data-stu-id="307e7-109">name</span></span>|<span data-ttu-id="307e7-110">Cadena que contiene el nombre exclusivo de este elemento de configuración.</span><span class="sxs-lookup"><span data-stu-id="307e7-110">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="307e7-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="307e7-111">Child Elements</span></span>  
  
|<span data-ttu-id="307e7-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="307e7-112">Element</span></span>|<span data-ttu-id="307e7-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="307e7-113">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="307e7-114">Asignaciones entre los filtros de enrutamiento y los puntos de conexión de destino a los que enviar mensajes cuando el filtro coincide.</span><span class="sxs-lookup"><span data-stu-id="307e7-114">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="307e7-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="307e7-115">Parent Elements</span></span>  
  
|<span data-ttu-id="307e7-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="307e7-116">Element</span></span>|<span data-ttu-id="307e7-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="307e7-117">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="307e7-118">Sección de configuración que contiene tablas de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="307e7-118">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="307e7-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="307e7-119">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
