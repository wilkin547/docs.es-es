---
title: <scopes>
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: 57e9e19025db5e1fa588f073fdf30de09837a25d
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399930"
---
# <a name="scopes"></a><span data-ttu-id="5d994-101">\<ámbitos ></span><span class="sxs-lookup"><span data-stu-id="5d994-101">\<scopes></span></span>
<span data-ttu-id="5d994-102">Contiene una colección de elementos de configuración que especifican URI del ámbito personalizado que se pueden usar para filtrar puntos de conexión de servicio durante la consulta.</span><span class="sxs-lookup"><span data-stu-id="5d994-102">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="5d994-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5d994-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5d994-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="5d994-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="5d994-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="5d994-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="5d994-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="5d994-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="5d994-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="5d994-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="5d994-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointDiscovery**](endpointdiscovery.md)</span><span class="sxs-lookup"><span data-stu-id="5d994-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointDiscovery>**](endpointdiscovery.md)</span></span>\
<span data-ttu-id="5d994-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<ámbitos >**</span><span class="sxs-lookup"><span data-stu-id="5d994-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<scopes>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d994-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5d994-110">Syntax</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enable="Boolean">
        <scopes>
          <add scope="URI" />
        </scopes>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5d994-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5d994-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5d994-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5d994-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5d994-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="5d994-113">Attributes</span></span>  
 <span data-ttu-id="5d994-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5d994-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5d994-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5d994-115">Child Elements</span></span>  
  
|<span data-ttu-id="5d994-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="5d994-116">Attribute</span></span>|<span data-ttu-id="5d994-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5d994-117">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="5d994-118">\<add></span><span class="sxs-lookup"><span data-stu-id="5d994-118">\<add></span></span>](add-of-scopes.md)|<span data-ttu-id="5d994-119">Agrega la información sobre el ámbito del extremo que se puede usar en los criterios de coincidencia para buscar los servicios.</span><span class="sxs-lookup"><span data-stu-id="5d994-119">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5d994-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5d994-120">Parent Elements</span></span>  
  
|<span data-ttu-id="5d994-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="5d994-121">Element</span></span>|<span data-ttu-id="5d994-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5d994-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d994-123">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="5d994-123">\<endpointDiscovery></span></span>](endpointdiscovery.md)|<span data-ttu-id="5d994-124">Especifica las distintas configuraciones de detección para un punto de conexión, como su detectabilidad, ámbitos y cualquier extensión personalizada a sus metadatos.</span><span class="sxs-lookup"><span data-stu-id="5d994-124">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5d994-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d994-125">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
