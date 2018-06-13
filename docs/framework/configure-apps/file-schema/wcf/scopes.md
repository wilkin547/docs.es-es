---
title: '&lt;Ámbitos&gt;'
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: 7e2dda0d0def4d1f90bf1b4dbf54f18983355222
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32749626"
---
# <a name="ltscopesgt"></a><span data-ttu-id="3e983-102">&lt;Ámbitos&gt;</span><span class="sxs-lookup"><span data-stu-id="3e983-102">&lt;scopes&gt;</span></span>
<span data-ttu-id="3e983-103">Contiene una colección de elementos de configuración que especifican URI del ámbito personalizado que se pueden usar para filtrar puntos de conexión de servicio durante la consulta.</span><span class="sxs-lookup"><span data-stu-id="3e983-103">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="3e983-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3e983-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="3e983-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="3e983-105">\<behaviors></span></span>  
<span data-ttu-id="3e983-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="3e983-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="3e983-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="3e983-107">\<behavior></span></span>  
<span data-ttu-id="3e983-108">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="3e983-108">\<endpointDiscovery></span></span>  
<span data-ttu-id="3e983-109">\<ámbitos ></span><span class="sxs-lookup"><span data-stu-id="3e983-109">\<scopes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e983-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3e983-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3e983-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3e983-111">Attributes and Elements</span></span>  
 <span data-ttu-id="3e983-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3e983-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3e983-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="3e983-113">Attributes</span></span>  
 <span data-ttu-id="3e983-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3e983-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3e983-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3e983-115">Child Elements</span></span>  
  
|<span data-ttu-id="3e983-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="3e983-116">Attribute</span></span>|<span data-ttu-id="3e983-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="3e983-117">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="3e983-118">\<add></span><span class="sxs-lookup"><span data-stu-id="3e983-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopes.md)|<span data-ttu-id="3e983-119">Agrega la información sobre el ámbito del punto de conexión que se puede usar en los criterios de coincidencia para buscar los servicios.</span><span class="sxs-lookup"><span data-stu-id="3e983-119">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3e983-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3e983-120">Parent Elements</span></span>  
  
|<span data-ttu-id="3e983-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="3e983-121">Element</span></span>|<span data-ttu-id="3e983-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="3e983-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3e983-123">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="3e983-123">\<endpointDiscovery></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|<span data-ttu-id="3e983-124">Especifica las distintas configuraciones de detección para un punto de conexión, como su detectabilidad, ámbitos y cualquier extensión personalizada a sus metadatos.</span><span class="sxs-lookup"><span data-stu-id="3e983-124">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3e983-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e983-125">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
