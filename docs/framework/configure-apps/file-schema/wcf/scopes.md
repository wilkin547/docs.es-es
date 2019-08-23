---
title: <scopes>
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: dd6513930798e9e1ab263f75c9350511c2dcdcd5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69935184"
---
# <a name="scopes"></a><span data-ttu-id="1aeb9-101">\<ámbitos ></span><span class="sxs-lookup"><span data-stu-id="1aeb9-101">\<scopes></span></span>
<span data-ttu-id="1aeb9-102">Contiene una colección de elementos de configuración que especifican URI del ámbito personalizado que se pueden usar para filtrar puntos de conexión de servicio durante la consulta.</span><span class="sxs-lookup"><span data-stu-id="1aeb9-102">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="1aeb9-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1aeb9-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="1aeb9-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="1aeb9-104">\<behaviors></span></span>  
<span data-ttu-id="1aeb9-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="1aeb9-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="1aeb9-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="1aeb9-106">\<behavior></span></span>  
<span data-ttu-id="1aeb9-107">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="1aeb9-107">\<endpointDiscovery></span></span>  
<span data-ttu-id="1aeb9-108">\<ámbitos ></span><span class="sxs-lookup"><span data-stu-id="1aeb9-108">\<scopes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1aeb9-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1aeb9-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1aeb9-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1aeb9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1aeb9-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1aeb9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1aeb9-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="1aeb9-112">Attributes</span></span>  
 <span data-ttu-id="1aeb9-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1aeb9-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1aeb9-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1aeb9-114">Child Elements</span></span>  
  
|<span data-ttu-id="1aeb9-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="1aeb9-115">Attribute</span></span>|<span data-ttu-id="1aeb9-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="1aeb9-116">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="1aeb9-117">\<add></span><span class="sxs-lookup"><span data-stu-id="1aeb9-117">\<add></span></span>](add-of-scopes.md)|<span data-ttu-id="1aeb9-118">Agrega la información sobre el ámbito del extremo que se puede usar en los criterios de coincidencia para buscar los servicios.</span><span class="sxs-lookup"><span data-stu-id="1aeb9-118">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1aeb9-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1aeb9-119">Parent Elements</span></span>  
  
|<span data-ttu-id="1aeb9-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="1aeb9-120">Element</span></span>|<span data-ttu-id="1aeb9-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="1aeb9-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1aeb9-122">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="1aeb9-122">\<endpointDiscovery></span></span>](endpointdiscovery.md)|<span data-ttu-id="1aeb9-123">Especifica las distintas configuraciones de detección para un punto de conexión, como su detectabilidad, ámbitos y cualquier extensión personalizada a sus metadatos.</span><span class="sxs-lookup"><span data-stu-id="1aeb9-123">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1aeb9-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="1aeb9-124">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
