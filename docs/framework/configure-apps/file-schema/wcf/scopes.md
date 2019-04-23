---
title: <scopes>
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: 8bc720238ca3039106345783381cd26134fc46b5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59213082"
---
# <a name="scopes"></a><span data-ttu-id="c294c-101">\<scopes></span><span class="sxs-lookup"><span data-stu-id="c294c-101">\<scopes></span></span>
<span data-ttu-id="c294c-102">Contiene una colección de elementos de configuración que especifican URI del ámbito personalizado que se pueden usar para filtrar puntos de conexión de servicio durante la consulta.</span><span class="sxs-lookup"><span data-stu-id="c294c-102">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="c294c-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c294c-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="c294c-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="c294c-104">\<behaviors></span></span>  
<span data-ttu-id="c294c-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="c294c-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="c294c-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="c294c-106">\<behavior></span></span>  
<span data-ttu-id="c294c-107">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="c294c-107">\<endpointDiscovery></span></span>  
<span data-ttu-id="c294c-108">\<scopes></span><span class="sxs-lookup"><span data-stu-id="c294c-108">\<scopes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c294c-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c294c-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c294c-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c294c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c294c-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c294c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c294c-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="c294c-112">Attributes</span></span>  
 <span data-ttu-id="c294c-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c294c-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c294c-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c294c-114">Child Elements</span></span>  
  
|<span data-ttu-id="c294c-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="c294c-115">Attribute</span></span>|<span data-ttu-id="c294c-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="c294c-116">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="c294c-117">\<add></span><span class="sxs-lookup"><span data-stu-id="c294c-117">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopes.md)|<span data-ttu-id="c294c-118">Agrega la información sobre el ámbito del extremo que se puede usar en los criterios de coincidencia para buscar los servicios.</span><span class="sxs-lookup"><span data-stu-id="c294c-118">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c294c-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c294c-119">Parent Elements</span></span>  
  
|<span data-ttu-id="c294c-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="c294c-120">Element</span></span>|<span data-ttu-id="c294c-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="c294c-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c294c-122">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="c294c-122">\<endpointDiscovery></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|<span data-ttu-id="c294c-123">Especifica las distintas configuraciones de detección para un punto de conexión, como su detectabilidad, ámbitos y cualquier extensión personalizada a sus metadatos.</span><span class="sxs-lookup"><span data-stu-id="c294c-123">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c294c-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="c294c-124">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
