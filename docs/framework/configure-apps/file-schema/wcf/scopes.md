---
title: <scopes>
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: 57e9e19025db5e1fa588f073fdf30de09837a25d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399930"
---
# \<scopes>
<span data-ttu-id="4f265-101">Contiene una colección de elementos de configuración que especifican URI del ámbito personalizado que se pueden usar para filtrar puntos de conexión de servicio durante la consulta.</span><span class="sxs-lookup"><span data-stu-id="4f265-101">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointDiscovery>**](endpointdiscovery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<scopes>**  
  
## <a name="syntax"></a><span data-ttu-id="4f265-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4f265-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4f265-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4f265-103">Attributes and Elements</span></span>  
 <span data-ttu-id="4f265-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4f265-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4f265-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="4f265-105">Attributes</span></span>  
 <span data-ttu-id="4f265-106">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4f265-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4f265-107">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4f265-107">Child Elements</span></span>  
  
|<span data-ttu-id="4f265-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="4f265-108">Attribute</span></span>|<span data-ttu-id="4f265-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="4f265-109">Description</span></span>|  
|---------------|-----------------|  
|[\<add>](add-of-scopes.md)|<span data-ttu-id="4f265-110">Agrega la información sobre el ámbito del extremo que se puede usar en los criterios de coincidencia para buscar los servicios.</span><span class="sxs-lookup"><span data-stu-id="4f265-110">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4f265-111">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4f265-111">Parent Elements</span></span>  
  
|<span data-ttu-id="4f265-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="4f265-112">Element</span></span>|<span data-ttu-id="4f265-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="4f265-113">Description</span></span>|  
|-------------|-----------------|  
|[\<endpointDiscovery>](endpointdiscovery.md)|<span data-ttu-id="4f265-114">Especifica las distintas configuraciones de detección para un punto de conexión, como su detectabilidad, ámbitos y cualquier extensión personalizada a sus metadatos.</span><span class="sxs-lookup"><span data-stu-id="4f265-114">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4f265-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4f265-115">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
