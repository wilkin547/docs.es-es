---
title: <discoveryClient>
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: f9d7e3a4957d2a8f30724f0bfc04e58a57fc5f7d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919274"
---
# <a name="discoveryclient"></a><span data-ttu-id="ed5ee-101">\<discoveryClient></span><span class="sxs-lookup"><span data-stu-id="ed5ee-101">\<discoveryClient></span></span>
<span data-ttu-id="ed5ee-102">Elemento de configuración para crear un enlace personalizado que habilita una aplicación cliente para buscar automáticamente un servicio detectable y encontrar su dirección en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ed5ee-102">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="ed5ee-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ed5ee-103">\<system.serviceModel></span></span>  
<span data-ttu-id="ed5ee-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="ed5ee-104">\<bindings></span></span>  
<span data-ttu-id="ed5ee-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="ed5ee-105">\<customBinding></span></span>  
<span data-ttu-id="ed5ee-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="ed5ee-106">\<binding></span></span>  
<span data-ttu-id="ed5ee-107">\<discoveryClient></span><span class="sxs-lookup"><span data-stu-id="ed5ee-107">\<discoveryClient></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed5ee-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ed5ee-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ed5ee-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ed5ee-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ed5ee-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ed5ee-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ed5ee-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="ed5ee-111">Attributes</span></span>  
  
|<span data-ttu-id="ed5ee-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="ed5ee-112">Attribute</span></span>|<span data-ttu-id="ed5ee-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ed5ee-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ed5ee-114">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="ed5ee-114">discoveryEndpoint</span></span>|<span data-ttu-id="ed5ee-115">Cadena que contiene el nombre del punto de conexión de la detección que habilita una aplicación cliente para buscar un servicio detectable automáticamente y encontrar su dirección en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ed5ee-115">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ed5ee-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ed5ee-116">Child Elements</span></span>  
  
|<span data-ttu-id="ed5ee-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="ed5ee-117">Element</span></span>|<span data-ttu-id="ed5ee-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ed5ee-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ed5ee-119">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="ed5ee-119">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="ed5ee-120">Elemento de configuración que proporciona un conjunto de criterios utilizado por una aplicación cliente para buscar un servicio de detección.</span><span class="sxs-lookup"><span data-stu-id="ed5ee-120">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="ed5ee-121">Los criterios se pueden agrupar en criterios de búsqueda (especificando qué servicios está buscando) y criterios de finalización de búsqueda (cuánto tiempo debe durar la búsqueda).</span><span class="sxs-lookup"><span data-stu-id="ed5ee-121">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ed5ee-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ed5ee-122">Parent Elements</span></span>  
  
|<span data-ttu-id="ed5ee-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="ed5ee-123">Element</span></span>|<span data-ttu-id="ed5ee-124">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ed5ee-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ed5ee-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="ed5ee-125">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="ed5ee-126">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="ed5ee-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ed5ee-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed5ee-127">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
