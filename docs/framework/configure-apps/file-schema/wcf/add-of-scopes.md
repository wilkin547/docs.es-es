---
title: <add> de <scopes>
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: b190cb72e21d47bdc62aab2daba0f6eea1ee04ac
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926629"
---
# <a name="add-of-scopes"></a><span data-ttu-id="cd798-102">\<Agregar > de \<ámbitos ></span><span class="sxs-lookup"><span data-stu-id="cd798-102">\<add> of \<scopes></span></span>
<span data-ttu-id="cd798-103">Agrega un Uri de ámbito personalizado que se puede utilizar para filtrar los extremos de servicio durante la consulta.</span><span class="sxs-lookup"><span data-stu-id="cd798-103">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="cd798-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="cd798-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="cd798-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="cd798-105">\<behaviors></span></span>  
<span data-ttu-id="cd798-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="cd798-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="cd798-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="cd798-107">\<behavior></span></span>  
<span data-ttu-id="cd798-108">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="cd798-108">\<endpointDiscovery></span></span>  
<span data-ttu-id="cd798-109">\<ámbitos ></span><span class="sxs-lookup"><span data-stu-id="cd798-109">\<scopes></span></span>  
<span data-ttu-id="cd798-110">\<add></span><span class="sxs-lookup"><span data-stu-id="cd798-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd798-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cd798-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cd798-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="cd798-112">Attributes and Elements</span></span>  
 <span data-ttu-id="cd798-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="cd798-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cd798-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="cd798-114">Attributes</span></span>  
  
|<span data-ttu-id="cd798-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="cd798-115">Attribute</span></span>|<span data-ttu-id="cd798-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="cd798-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cd798-117">scope</span><span class="sxs-lookup"><span data-stu-id="cd798-117">scope</span></span>|<span data-ttu-id="cd798-118">URI que contiene información sobre el ámbito del punto de conexión que se puede usar en los criterios de coincidencia para buscar los servicios.</span><span class="sxs-lookup"><span data-stu-id="cd798-118">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cd798-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="cd798-119">Child Elements</span></span>  
 <span data-ttu-id="cd798-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="cd798-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cd798-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="cd798-121">Parent Elements</span></span>  
  
|<span data-ttu-id="cd798-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="cd798-122">Element</span></span>|<span data-ttu-id="cd798-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="cd798-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cd798-124">\<scopes></span><span class="sxs-lookup"><span data-stu-id="cd798-124">\<scopes></span></span>](scopes.md)|<span data-ttu-id="cd798-125">Contiene una colección de elementos de configuración que especifican URI del ámbito personalizado que se pueden usar para filtrar puntos de conexión de servicio durante la consulta.</span><span class="sxs-lookup"><span data-stu-id="cd798-125">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cd798-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="cd798-126">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
