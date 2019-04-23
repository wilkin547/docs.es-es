---
title: <add> de <scopes>
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: c29e47f688118e34fbdb4deb396c930d478f0582
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59187089"
---
# <a name="add-of-scopes"></a><span data-ttu-id="6c506-102">\<Agregar > de \<ámbitos ></span><span class="sxs-lookup"><span data-stu-id="6c506-102">\<add> of \<scopes></span></span>
<span data-ttu-id="6c506-103">Agrega un Uri de ámbito personalizado que se puede utilizar para filtrar los extremos de servicio durante la consulta.</span><span class="sxs-lookup"><span data-stu-id="6c506-103">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="6c506-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="6c506-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="6c506-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="6c506-105">\<behaviors></span></span>  
<span data-ttu-id="6c506-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="6c506-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="6c506-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="6c506-107">\<behavior></span></span>  
<span data-ttu-id="6c506-108">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="6c506-108">\<endpointDiscovery></span></span>  
<span data-ttu-id="6c506-109">\<scopes></span><span class="sxs-lookup"><span data-stu-id="6c506-109">\<scopes></span></span>  
<span data-ttu-id="6c506-110">\<add></span><span class="sxs-lookup"><span data-stu-id="6c506-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c506-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6c506-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6c506-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6c506-112">Attributes and Elements</span></span>  
 <span data-ttu-id="6c506-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6c506-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6c506-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="6c506-114">Attributes</span></span>  
  
|<span data-ttu-id="6c506-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="6c506-115">Attribute</span></span>|<span data-ttu-id="6c506-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="6c506-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6c506-117">ámbito</span><span class="sxs-lookup"><span data-stu-id="6c506-117">scope</span></span>|<span data-ttu-id="6c506-118">URI que contiene información sobre el ámbito del punto de conexión que se puede usar en los criterios de coincidencia para buscar los servicios.</span><span class="sxs-lookup"><span data-stu-id="6c506-118">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6c506-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6c506-119">Child Elements</span></span>  
 <span data-ttu-id="6c506-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6c506-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6c506-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6c506-121">Parent Elements</span></span>  
  
|<span data-ttu-id="6c506-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="6c506-122">Element</span></span>|<span data-ttu-id="6c506-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="6c506-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c506-124">\<scopes></span><span class="sxs-lookup"><span data-stu-id="6c506-124">\<scopes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|<span data-ttu-id="6c506-125">Contiene una colección de elementos de configuración que especifican URI del ámbito personalizado que se pueden usar para filtrar puntos de conexión de servicio durante la consulta.</span><span class="sxs-lookup"><span data-stu-id="6c506-125">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6c506-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c506-126">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
