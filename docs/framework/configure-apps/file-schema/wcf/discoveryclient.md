---
title: <discoveryClient>
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: 71305720cad0206ec3dabb1863e2f1cd72eb85f0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73739037"
---
# \<discoveryClient>
<span data-ttu-id="815fa-101">Elemento de configuración para crear un enlace personalizado que habilita una aplicación cliente para buscar automáticamente un servicio detectable y encontrar su dirección en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="815fa-101">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryClient>**  
  
## <a name="syntax"></a><span data-ttu-id="815fa-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="815fa-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="815fa-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="815fa-103">Attributes and Elements</span></span>  
 <span data-ttu-id="815fa-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="815fa-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="815fa-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="815fa-105">Attributes</span></span>  
  
|<span data-ttu-id="815fa-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="815fa-106">Attribute</span></span>|<span data-ttu-id="815fa-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="815fa-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="815fa-108">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="815fa-108">discoveryEndpoint</span></span>|<span data-ttu-id="815fa-109">Cadena que contiene el nombre del punto de conexión de la detección que habilita una aplicación cliente para buscar un servicio detectable automáticamente y encontrar su dirección en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="815fa-109">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="815fa-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="815fa-110">Child Elements</span></span>  
  
|<span data-ttu-id="815fa-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="815fa-111">Element</span></span>|<span data-ttu-id="815fa-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="815fa-112">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="815fa-113">Elemento de configuración que proporciona un conjunto de criterios utilizado por una aplicación cliente para buscar un servicio de detección.</span><span class="sxs-lookup"><span data-stu-id="815fa-113">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="815fa-114">Los criterios pueden agruparse en criterios de búsqueda (que especifican qué servicios está buscando) y en criterios de finalización de búsqueda (cuánto tiempo debería durar la búsqueda).</span><span class="sxs-lookup"><span data-stu-id="815fa-114">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="815fa-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="815fa-115">Parent Elements</span></span>  
  
|<span data-ttu-id="815fa-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="815fa-116">Element</span></span>|<span data-ttu-id="815fa-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="815fa-117">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="815fa-118">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="815fa-118">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="815fa-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="815fa-119">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
