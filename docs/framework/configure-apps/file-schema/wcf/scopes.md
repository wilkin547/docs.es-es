---
description: 'Más información acerca de: <scopes>'
title: <scopes>
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: 2df1101beb5b1bc09c2d98eb89a8200303c5b456
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786868"
---
# \<scopes>

<span data-ttu-id="c1f9a-102">Contiene una colección de elementos de configuración que especifican URI del ámbito personalizado que se pueden usar para filtrar puntos de conexión de servicio durante la consulta.</span><span class="sxs-lookup"><span data-stu-id="c1f9a-102">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointDiscovery>**](endpointdiscovery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<scopes>**  
  
## <a name="syntax"></a><span data-ttu-id="c1f9a-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c1f9a-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c1f9a-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c1f9a-104">Attributes and Elements</span></span>  

 <span data-ttu-id="c1f9a-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c1f9a-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c1f9a-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="c1f9a-106">Attributes</span></span>  

 <span data-ttu-id="c1f9a-107">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c1f9a-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c1f9a-108">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c1f9a-108">Child Elements</span></span>  
  
|<span data-ttu-id="c1f9a-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="c1f9a-109">Attribute</span></span>|<span data-ttu-id="c1f9a-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="c1f9a-110">Description</span></span>|  
|---------------|-----------------|  
|[\<add>](add-of-scopes.md)|<span data-ttu-id="c1f9a-111">Agrega la información sobre el ámbito del extremo que se puede usar en los criterios de coincidencia para buscar los servicios.</span><span class="sxs-lookup"><span data-stu-id="c1f9a-111">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c1f9a-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c1f9a-112">Parent Elements</span></span>  
  
|<span data-ttu-id="c1f9a-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="c1f9a-113">Element</span></span>|<span data-ttu-id="c1f9a-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="c1f9a-114">Description</span></span>|  
|-------------|-----------------|  
|[\<endpointDiscovery>](endpointdiscovery.md)|<span data-ttu-id="c1f9a-115">Especifica las distintas configuraciones de detección para un punto de conexión, como su detectabilidad, ámbitos y cualquier extensión personalizada a sus metadatos.</span><span class="sxs-lookup"><span data-stu-id="c1f9a-115">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c1f9a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1f9a-116">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
