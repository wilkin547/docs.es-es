---
title: '&lt;add&gt; de &lt;scopes&gt;'
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: 961fb3e388e3ae756bd7511ea6c65df6dd2a1486
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54705578"
---
# <a name="ltaddgt-of-ltscopesgt"></a><span data-ttu-id="5caa6-102">&lt;add&gt; de &lt;scopes&gt;</span><span class="sxs-lookup"><span data-stu-id="5caa6-102">&lt;add&gt; of &lt;scopes&gt;</span></span>
<span data-ttu-id="5caa6-103">Agrega un Uri de ámbito personalizado que se puede utilizar para filtrar los puntos de conexión de servicio durante la consulta.</span><span class="sxs-lookup"><span data-stu-id="5caa6-103">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="5caa6-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5caa6-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5caa6-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="5caa6-105">\<behaviors></span></span>  
<span data-ttu-id="5caa6-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="5caa6-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="5caa6-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="5caa6-107">\<behavior></span></span>  
<span data-ttu-id="5caa6-108">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="5caa6-108">\<endpointDiscovery></span></span>  
<span data-ttu-id="5caa6-109">\<scopes></span><span class="sxs-lookup"><span data-stu-id="5caa6-109">\<scopes></span></span>  
<span data-ttu-id="5caa6-110">\<add></span><span class="sxs-lookup"><span data-stu-id="5caa6-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5caa6-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5caa6-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5caa6-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5caa6-112">Attributes and Elements</span></span>  
 <span data-ttu-id="5caa6-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5caa6-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5caa6-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="5caa6-114">Attributes</span></span>  
  
|<span data-ttu-id="5caa6-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="5caa6-115">Attribute</span></span>|<span data-ttu-id="5caa6-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="5caa6-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5caa6-117">ámbito</span><span class="sxs-lookup"><span data-stu-id="5caa6-117">scope</span></span>|<span data-ttu-id="5caa6-118">URI que contiene información sobre el ámbito del punto de conexión que se puede usar en los criterios de coincidencia para buscar los servicios.</span><span class="sxs-lookup"><span data-stu-id="5caa6-118">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5caa6-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5caa6-119">Child Elements</span></span>  
 <span data-ttu-id="5caa6-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5caa6-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5caa6-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5caa6-121">Parent Elements</span></span>  
  
|<span data-ttu-id="5caa6-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="5caa6-122">Element</span></span>|<span data-ttu-id="5caa6-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="5caa6-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5caa6-124">\<scopes></span><span class="sxs-lookup"><span data-stu-id="5caa6-124">\<scopes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|<span data-ttu-id="5caa6-125">Contiene una colección de elementos de configuración que especifican URI del ámbito personalizado que se pueden usar para filtrar puntos de conexión de servicio durante la consulta.</span><span class="sxs-lookup"><span data-stu-id="5caa6-125">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5caa6-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="5caa6-126">See also</span></span>
- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
