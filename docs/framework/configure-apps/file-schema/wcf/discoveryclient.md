---
title: '&lt;DiscoveryClient&gt;'
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: 9aef599ebf8068a383fd093b126a6bde1670b291
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151404"
---
# <a name="ltdiscoveryclientgt"></a><span data-ttu-id="5dee1-102">&lt;DiscoveryClient&gt;</span><span class="sxs-lookup"><span data-stu-id="5dee1-102">&lt;discoveryClient&gt;</span></span>
<span data-ttu-id="5dee1-103">Elemento de configuración para crear un enlace personalizado que habilita una aplicación cliente para buscar automáticamente un servicio detectable y encontrar su dirección en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5dee1-103">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="5dee1-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5dee1-104">\<system.serviceModel></span></span>  
<span data-ttu-id="5dee1-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="5dee1-105">\<bindings></span></span>  
<span data-ttu-id="5dee1-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="5dee1-106">\<customBinding></span></span>  
<span data-ttu-id="5dee1-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="5dee1-107">\<binding></span></span>  
<span data-ttu-id="5dee1-108">\<discoveryClient ></span><span class="sxs-lookup"><span data-stu-id="5dee1-108">\<discoveryClient></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5dee1-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5dee1-109">Syntax</span></span>  
  
```xml  
<discoveryClient discoveryEndpoint="String">
  <findCriteria duration="TimeSpan"
                maxResults="Integer"
                scopeMatchBy="Uri">
    <contractTypeNames>
      <add name="String"
           namespace="String" />
    </contractTypeNames>
    <extensions />
    <scopes>
      <add scope="URI"/>
    </scopes>
  </findCriteria>
</discoveryClient>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5dee1-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5dee1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5dee1-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5dee1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5dee1-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="5dee1-112">Attributes</span></span>  
  
|<span data-ttu-id="5dee1-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="5dee1-113">Attribute</span></span>|<span data-ttu-id="5dee1-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="5dee1-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5dee1-115">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="5dee1-115">discoveryEndpoint</span></span>|<span data-ttu-id="5dee1-116">Cadena que contiene el nombre del punto de conexión de la detección que habilita una aplicación cliente para buscar un servicio detectable automáticamente y encontrar su dirección en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5dee1-116">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5dee1-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5dee1-117">Child Elements</span></span>  
  
|<span data-ttu-id="5dee1-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="5dee1-118">Element</span></span>|<span data-ttu-id="5dee1-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="5dee1-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5dee1-120">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="5dee1-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="5dee1-121">Elemento de configuración que proporciona un conjunto de criterios utilizado por una aplicación cliente para buscar un servicio de detección.</span><span class="sxs-lookup"><span data-stu-id="5dee1-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="5dee1-122">Los criterios pueden agruparse en criterios de búsqueda (que especifican qué servicios está buscando) y encuentra criterios de finalización (cuánto tiempo debe durar la búsqueda).</span><span class="sxs-lookup"><span data-stu-id="5dee1-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5dee1-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5dee1-123">Parent Elements</span></span>  
  
|<span data-ttu-id="5dee1-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="5dee1-124">Element</span></span>|<span data-ttu-id="5dee1-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="5dee1-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5dee1-126">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="5dee1-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="5dee1-127">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="5dee1-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5dee1-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="5dee1-128">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>  
 <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
