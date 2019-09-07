---
title: <discoveryClient>
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: 5e586437e3b269d361c254744e820ee8e8c0ca0a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400395"
---
# <a name="discoveryclient"></a><span data-ttu-id="4f887-101">\<discoveryClient></span><span class="sxs-lookup"><span data-stu-id="4f887-101">\<discoveryClient></span></span>
<span data-ttu-id="4f887-102">Elemento de configuración para crear un enlace personalizado que habilita una aplicación cliente para buscar automáticamente un servicio detectable y encontrar su dirección en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4f887-102">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="4f887-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4f887-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4f887-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4f887-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4f887-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enlaces**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="4f887-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="4f887-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="4f887-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="4f887-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de enlace**</span><span class="sxs-lookup"><span data-stu-id="4f887-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="4f887-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> discoveryClient**</span><span class="sxs-lookup"><span data-stu-id="4f887-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryClient>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f887-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4f887-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4f887-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4f887-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4f887-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4f887-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4f887-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="4f887-112">Attributes</span></span>  
  
|<span data-ttu-id="4f887-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="4f887-113">Attribute</span></span>|<span data-ttu-id="4f887-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4f887-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4f887-115">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="4f887-115">discoveryEndpoint</span></span>|<span data-ttu-id="4f887-116">Cadena que contiene el nombre del punto de conexión de la detección que habilita una aplicación cliente para buscar un servicio detectable automáticamente y encontrar su dirección en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4f887-116">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4f887-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4f887-117">Child Elements</span></span>  
  
|<span data-ttu-id="4f887-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="4f887-118">Element</span></span>|<span data-ttu-id="4f887-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4f887-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4f887-120">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="4f887-120">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="4f887-121">Elemento de configuración que proporciona un conjunto de criterios utilizado por una aplicación cliente para buscar un servicio de detección.</span><span class="sxs-lookup"><span data-stu-id="4f887-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="4f887-122">Los criterios se pueden agrupar en criterios de búsqueda (especificando qué servicios está buscando) y criterios de finalización de búsqueda (cuánto tiempo debe durar la búsqueda).</span><span class="sxs-lookup"><span data-stu-id="4f887-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4f887-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4f887-123">Parent Elements</span></span>  
  
|<span data-ttu-id="4f887-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="4f887-124">Element</span></span>|<span data-ttu-id="4f887-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4f887-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4f887-126">\<binding></span><span class="sxs-lookup"><span data-stu-id="4f887-126">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="4f887-127">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="4f887-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4f887-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f887-128">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
