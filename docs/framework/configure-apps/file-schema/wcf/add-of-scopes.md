---
title: '&lt;add&gt; de &lt;scopes&gt;'
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: e2bf649259d6ccb0e55428ab3619fe561d051ff7
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146246"
---
# <a name="ltaddgt-of-ltscopesgt"></a><span data-ttu-id="85814-102">&lt;add&gt; de &lt;scopes&gt;</span><span class="sxs-lookup"><span data-stu-id="85814-102">&lt;add&gt; of &lt;scopes&gt;</span></span>
<span data-ttu-id="85814-103">Agrega un Uri de ámbito personalizado que se puede utilizar para filtrar los puntos de conexión de servicio durante la consulta.</span><span class="sxs-lookup"><span data-stu-id="85814-103">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="85814-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="85814-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="85814-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="85814-105">\<behaviors></span></span>  
<span data-ttu-id="85814-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="85814-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="85814-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="85814-107">\<behavior></span></span>  
<span data-ttu-id="85814-108">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="85814-108">\<endpointDiscovery></span></span>  
<span data-ttu-id="85814-109">\<ámbitos ></span><span class="sxs-lookup"><span data-stu-id="85814-109">\<scopes></span></span>  
<span data-ttu-id="85814-110">\<add></span><span class="sxs-lookup"><span data-stu-id="85814-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85814-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="85814-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="85814-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="85814-112">Attributes and Elements</span></span>  
 <span data-ttu-id="85814-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="85814-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="85814-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="85814-114">Attributes</span></span>  
  
|<span data-ttu-id="85814-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="85814-115">Attribute</span></span>|<span data-ttu-id="85814-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="85814-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="85814-117">ámbito</span><span class="sxs-lookup"><span data-stu-id="85814-117">scope</span></span>|<span data-ttu-id="85814-118">URI que contiene información sobre el ámbito del punto de conexión que se puede usar en los criterios de coincidencia para buscar los servicios.</span><span class="sxs-lookup"><span data-stu-id="85814-118">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="85814-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="85814-119">Child Elements</span></span>  
 <span data-ttu-id="85814-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="85814-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="85814-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="85814-121">Parent Elements</span></span>  
  
|<span data-ttu-id="85814-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="85814-122">Element</span></span>|<span data-ttu-id="85814-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="85814-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="85814-124">\<ámbitos ></span><span class="sxs-lookup"><span data-stu-id="85814-124">\<scopes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|<span data-ttu-id="85814-125">Contiene una colección de elementos de configuración que especifican URI del ámbito personalizado que se pueden usar para filtrar puntos de conexión de servicio durante la consulta.</span><span class="sxs-lookup"><span data-stu-id="85814-125">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="85814-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="85814-126">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
