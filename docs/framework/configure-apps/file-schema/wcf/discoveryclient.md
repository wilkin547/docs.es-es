---
title: <discoveryClient>
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: af9cf127652f1e12ae57948f9b4a6a26285af793
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192261"
---
# \<discoveryClient>

<span data-ttu-id="a725b-101">Elemento de configuración para crear un enlace personalizado que habilita una aplicación cliente para buscar automáticamente un servicio detectable y encontrar su dirección en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a725b-101">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryClient>**  
  
## <a name="syntax"></a><span data-ttu-id="a725b-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a725b-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a725b-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a725b-103">Attributes and Elements</span></span>  

 <span data-ttu-id="a725b-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a725b-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a725b-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="a725b-105">Attributes</span></span>  
  
|<span data-ttu-id="a725b-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="a725b-106">Attribute</span></span>|<span data-ttu-id="a725b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a725b-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a725b-108">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="a725b-108">discoveryEndpoint</span></span>|<span data-ttu-id="a725b-109">Cadena que contiene el nombre del punto de conexión de la detección que habilita una aplicación cliente para buscar un servicio detectable automáticamente y encontrar su dirección en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a725b-109">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a725b-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a725b-110">Child Elements</span></span>  
  
|<span data-ttu-id="a725b-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="a725b-111">Element</span></span>|<span data-ttu-id="a725b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a725b-112">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="a725b-113">Elemento de configuración que proporciona un conjunto de criterios utilizado por una aplicación cliente para buscar un servicio de detección.</span><span class="sxs-lookup"><span data-stu-id="a725b-113">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="a725b-114">Los criterios pueden agruparse en criterios de búsqueda (que especifican qué servicios está buscando) y en criterios de finalización de búsqueda (cuánto tiempo debería durar la búsqueda).</span><span class="sxs-lookup"><span data-stu-id="a725b-114">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a725b-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a725b-115">Parent Elements</span></span>  
  
|<span data-ttu-id="a725b-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="a725b-116">Element</span></span>|<span data-ttu-id="a725b-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="a725b-117">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="a725b-118">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="a725b-118">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a725b-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a725b-119">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
