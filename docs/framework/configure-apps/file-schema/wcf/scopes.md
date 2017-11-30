---
title: "&lt;ámbitos&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6b35696cbecb0badf397d6d48e7c97aae3d0232e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltscopesgt"></a><span data-ttu-id="fd30b-102">&lt;ámbitos&gt;</span><span class="sxs-lookup"><span data-stu-id="fd30b-102">&lt;scopes&gt;</span></span>
<span data-ttu-id="fd30b-103">Contiene una colección de elementos de configuración que especifican URI del ámbito personalizado que se pueden usar para filtrar puntos de conexión de servicio durante la consulta.</span><span class="sxs-lookup"><span data-stu-id="fd30b-103">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="fd30b-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="fd30b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="fd30b-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="fd30b-105">\<behaviors></span></span>  
<span data-ttu-id="fd30b-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="fd30b-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="fd30b-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="fd30b-107">\<behavior></span></span>  
<span data-ttu-id="fd30b-108">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="fd30b-108">\<endpointDiscovery></span></span>  
<span data-ttu-id="fd30b-109">\<ámbitos ></span><span class="sxs-lookup"><span data-stu-id="fd30b-109">\<scopes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd30b-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fd30b-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fd30b-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fd30b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="fd30b-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fd30b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fd30b-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="fd30b-113">Attributes</span></span>  
 <span data-ttu-id="fd30b-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="fd30b-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fd30b-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fd30b-115">Child Elements</span></span>  
  
|<span data-ttu-id="fd30b-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="fd30b-116">Attribute</span></span>|<span data-ttu-id="fd30b-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="fd30b-117">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="fd30b-118">\<add></span><span class="sxs-lookup"><span data-stu-id="fd30b-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopes.md)|<span data-ttu-id="fd30b-119">Agrega la información sobre el ámbito del punto de conexión que se puede usar en los criterios de coincidencia para buscar los servicios.</span><span class="sxs-lookup"><span data-stu-id="fd30b-119">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fd30b-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fd30b-120">Parent Elements</span></span>  
  
|<span data-ttu-id="fd30b-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="fd30b-121">Element</span></span>|<span data-ttu-id="fd30b-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="fd30b-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fd30b-123">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="fd30b-123">\<endpointDiscovery></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|<span data-ttu-id="fd30b-124">Especifica las distintas configuraciones de detección para un punto de conexión, como su detectabilidad, ámbitos y cualquier extensión personalizada a sus metadatos.</span><span class="sxs-lookup"><span data-stu-id="fd30b-124">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fd30b-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd30b-125">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
