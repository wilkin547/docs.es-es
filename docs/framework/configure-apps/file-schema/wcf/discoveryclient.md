---
description: 'Más información acerca de: <discoveryClient>'
title: <discoveryClient>
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: d04eee828bb16e56a65c39059665feb745f3006a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754399"
---
# \<discoveryClient>

<span data-ttu-id="05ad1-102">Elemento de configuración para crear un enlace personalizado que habilita una aplicación cliente para buscar automáticamente un servicio detectable y encontrar su dirección en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="05ad1-102">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryClient>**  
  
## <a name="syntax"></a><span data-ttu-id="05ad1-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="05ad1-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="05ad1-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="05ad1-104">Attributes and Elements</span></span>  

 <span data-ttu-id="05ad1-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="05ad1-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="05ad1-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="05ad1-106">Attributes</span></span>  
  
|<span data-ttu-id="05ad1-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="05ad1-107">Attribute</span></span>|<span data-ttu-id="05ad1-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="05ad1-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="05ad1-109">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="05ad1-109">discoveryEndpoint</span></span>|<span data-ttu-id="05ad1-110">Cadena que contiene el nombre del punto de conexión de la detección que habilita una aplicación cliente para buscar un servicio detectable automáticamente y encontrar su dirección en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="05ad1-110">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="05ad1-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="05ad1-111">Child Elements</span></span>  
  
|<span data-ttu-id="05ad1-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="05ad1-112">Element</span></span>|<span data-ttu-id="05ad1-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="05ad1-113">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="05ad1-114">Elemento de configuración que proporciona un conjunto de criterios utilizado por una aplicación cliente para buscar un servicio de detección.</span><span class="sxs-lookup"><span data-stu-id="05ad1-114">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="05ad1-115">Los criterios pueden agruparse en criterios de búsqueda (que especifican qué servicios está buscando) y en criterios de finalización de búsqueda (cuánto tiempo debería durar la búsqueda).</span><span class="sxs-lookup"><span data-stu-id="05ad1-115">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="05ad1-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="05ad1-116">Parent Elements</span></span>  
  
|<span data-ttu-id="05ad1-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="05ad1-117">Element</span></span>|<span data-ttu-id="05ad1-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="05ad1-118">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="05ad1-119">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="05ad1-119">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="05ad1-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="05ad1-120">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
