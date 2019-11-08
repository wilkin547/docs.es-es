---
title: <discoveryClient>
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: 71305720cad0206ec3dabb1863e2f1cd72eb85f0
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739037"
---
# <a name="discoveryclient"></a><span data-ttu-id="fec66-101">\<discoveryClient ></span><span class="sxs-lookup"><span data-stu-id="fec66-101">\<discoveryClient></span></span>
<span data-ttu-id="fec66-102">Elemento de configuración para crear un enlace personalizado que habilita una aplicación cliente para buscar automáticamente un servicio detectable y encontrar su dirección en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="fec66-102">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="fec66-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fec66-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fec66-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="fec66-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="fec66-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**enlaces**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="fec66-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="fec66-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**customBinding**](custombinding.md) ></span><span class="sxs-lookup"><span data-stu-id="fec66-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="fec66-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**enlace** ></span><span class="sxs-lookup"><span data-stu-id="fec66-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="fec66-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<discoveryClient >**</span><span class="sxs-lookup"><span data-stu-id="fec66-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryClient>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fec66-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fec66-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fec66-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fec66-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fec66-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fec66-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fec66-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="fec66-112">Attributes</span></span>  
  
|<span data-ttu-id="fec66-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="fec66-113">Attribute</span></span>|<span data-ttu-id="fec66-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="fec66-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fec66-115">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="fec66-115">discoveryEndpoint</span></span>|<span data-ttu-id="fec66-116">Cadena que contiene el nombre del punto de conexión de la detección que habilita una aplicación cliente para buscar un servicio detectable automáticamente y encontrar su dirección en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="fec66-116">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fec66-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fec66-117">Child Elements</span></span>  
  
|<span data-ttu-id="fec66-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="fec66-118">Element</span></span>|<span data-ttu-id="fec66-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="fec66-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fec66-120">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="fec66-120">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="fec66-121">Elemento de configuración que proporciona un conjunto de criterios utilizado por una aplicación cliente para buscar un servicio de detección.</span><span class="sxs-lookup"><span data-stu-id="fec66-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="fec66-122">Los criterios se pueden agrupar en criterios de búsqueda (especificando qué servicios está buscando) y criterios de finalización de búsqueda (cuánto tiempo debe durar la búsqueda).</span><span class="sxs-lookup"><span data-stu-id="fec66-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fec66-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fec66-123">Parent Elements</span></span>  
  
|<span data-ttu-id="fec66-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="fec66-124">Element</span></span>|<span data-ttu-id="fec66-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="fec66-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fec66-126">\<> de enlace</span><span class="sxs-lookup"><span data-stu-id="fec66-126">\<binding></span></span>](bindings.md)|<span data-ttu-id="fec66-127">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="fec66-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fec66-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="fec66-128">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
