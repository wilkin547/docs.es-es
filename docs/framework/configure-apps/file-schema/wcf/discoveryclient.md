---
title: <discoveryClient>
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: a5ea10601732021af578c17d4f5c5ab69c98f17a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59128445"
---
# <a name="discoveryclient"></a><span data-ttu-id="68c84-101">\<discoveryClient></span><span class="sxs-lookup"><span data-stu-id="68c84-101">\<discoveryClient></span></span>
<span data-ttu-id="68c84-102">Elemento de configuración para crear un enlace personalizado que habilita una aplicación cliente para buscar automáticamente un servicio detectable y encontrar su dirección en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="68c84-102">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="68c84-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="68c84-103">\<system.serviceModel></span></span>  
<span data-ttu-id="68c84-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="68c84-104">\<bindings></span></span>  
<span data-ttu-id="68c84-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="68c84-105">\<customBinding></span></span>  
<span data-ttu-id="68c84-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="68c84-106">\<binding></span></span>  
<span data-ttu-id="68c84-107">\<discoveryClient></span><span class="sxs-lookup"><span data-stu-id="68c84-107">\<discoveryClient></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68c84-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="68c84-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="68c84-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="68c84-109">Attributes and Elements</span></span>  
 <span data-ttu-id="68c84-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="68c84-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="68c84-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="68c84-111">Attributes</span></span>  
  
|<span data-ttu-id="68c84-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="68c84-112">Attribute</span></span>|<span data-ttu-id="68c84-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="68c84-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="68c84-114">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="68c84-114">discoveryEndpoint</span></span>|<span data-ttu-id="68c84-115">Cadena que contiene el nombre del punto de conexión de la detección que habilita una aplicación cliente para buscar un servicio detectable automáticamente y encontrar su dirección en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="68c84-115">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="68c84-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="68c84-116">Child Elements</span></span>  
  
|<span data-ttu-id="68c84-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="68c84-117">Element</span></span>|<span data-ttu-id="68c84-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="68c84-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="68c84-119">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="68c84-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="68c84-120">Elemento de configuración que proporciona un conjunto de criterios utilizado por una aplicación cliente para buscar un servicio de detección.</span><span class="sxs-lookup"><span data-stu-id="68c84-120">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="68c84-121">Los criterios pueden agruparse en criterios de búsqueda (que especifican qué servicios está buscando) y encuentra criterios de finalización (cuánto tiempo debe durar la búsqueda).</span><span class="sxs-lookup"><span data-stu-id="68c84-121">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="68c84-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="68c84-122">Parent Elements</span></span>  
  
|<span data-ttu-id="68c84-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="68c84-123">Element</span></span>|<span data-ttu-id="68c84-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="68c84-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="68c84-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="68c84-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="68c84-126">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="68c84-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="68c84-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="68c84-127">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
