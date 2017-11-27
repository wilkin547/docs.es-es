---
title: '&lt;add&gt; de &lt;scopes&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c720d99a5abee00eeb52f91586503e0a8a89027b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltaddgt-of-ltscopesgt"></a><span data-ttu-id="9eca6-102">&lt;add&gt; de &lt;scopes&gt;</span><span class="sxs-lookup"><span data-stu-id="9eca6-102">&lt;add&gt; of &lt;scopes&gt;</span></span>
<span data-ttu-id="9eca6-103">Agrega un Uri de ámbito personalizado que se puede utilizar para filtrar los puntos de conexión de servicio durante la consulta.</span><span class="sxs-lookup"><span data-stu-id="9eca6-103">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="9eca6-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="9eca6-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9eca6-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="9eca6-105">\<behaviors></span></span>  
<span data-ttu-id="9eca6-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="9eca6-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="9eca6-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="9eca6-107">\<behavior></span></span>  
<span data-ttu-id="9eca6-108">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="9eca6-108">\<endpointDiscovery></span></span>  
<span data-ttu-id="9eca6-109">\<ámbitos ></span><span class="sxs-lookup"><span data-stu-id="9eca6-109">\<scopes></span></span>  
<span data-ttu-id="9eca6-110">\<add></span><span class="sxs-lookup"><span data-stu-id="9eca6-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9eca6-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9eca6-111">Syntax</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enable="Boolean">
        <scopes>
          <add scope="URI"/>
        </scopes>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9eca6-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9eca6-112">Attributes and Elements</span></span>  
 <span data-ttu-id="9eca6-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9eca6-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9eca6-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="9eca6-114">Attributes</span></span>  
  
|<span data-ttu-id="9eca6-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="9eca6-115">Attribute</span></span>|<span data-ttu-id="9eca6-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="9eca6-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9eca6-117">ámbito</span><span class="sxs-lookup"><span data-stu-id="9eca6-117">scope</span></span>|<span data-ttu-id="9eca6-118">URI que contiene información sobre el ámbito del punto de conexión que se puede usar en los criterios de coincidencia para buscar los servicios.</span><span class="sxs-lookup"><span data-stu-id="9eca6-118">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9eca6-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9eca6-119">Child Elements</span></span>  
 <span data-ttu-id="9eca6-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9eca6-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9eca6-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9eca6-121">Parent Elements</span></span>  
  
|<span data-ttu-id="9eca6-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="9eca6-122">Element</span></span>|<span data-ttu-id="9eca6-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="9eca6-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9eca6-124">\<ámbitos ></span><span class="sxs-lookup"><span data-stu-id="9eca6-124">\<scopes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|<span data-ttu-id="9eca6-125">Contiene una colección de elementos de configuración que especifican URI del ámbito personalizado que se pueden usar para filtrar puntos de conexión de servicio durante la consulta.</span><span class="sxs-lookup"><span data-stu-id="9eca6-125">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9eca6-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="9eca6-126">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
