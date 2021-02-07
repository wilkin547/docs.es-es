---
description: 'Más información sobre: <add> de <scopes>'
title: <add> de <scopes>
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: e5582a7599c221e9ac00e03178911290e18ff536
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99750239"
---
# <a name="add-of-scopes"></a><span data-ttu-id="1b3e5-103">\<add> de \<scopes></span><span class="sxs-lookup"><span data-stu-id="1b3e5-103">\<add> of \<scopes></span></span>

<span data-ttu-id="1b3e5-104">Agrega un Uri de ámbito personalizado que se puede utilizar para filtrar los extremos de servicio durante la consulta.</span><span class="sxs-lookup"><span data-stu-id="1b3e5-104">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointDiscovery>**](endpointdiscovery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<scopes>**](scopes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="1b3e5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1b3e5-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1b3e5-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1b3e5-106">Attributes and Elements</span></span>  

 <span data-ttu-id="1b3e5-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1b3e5-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1b3e5-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="1b3e5-108">Attributes</span></span>  
  
|<span data-ttu-id="1b3e5-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="1b3e5-109">Attribute</span></span>|<span data-ttu-id="1b3e5-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="1b3e5-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1b3e5-111">scope</span><span class="sxs-lookup"><span data-stu-id="1b3e5-111">scope</span></span>|<span data-ttu-id="1b3e5-112">URI que contiene información sobre el ámbito del punto de conexión que se puede usar en los criterios de coincidencia para buscar los servicios.</span><span class="sxs-lookup"><span data-stu-id="1b3e5-112">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1b3e5-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1b3e5-113">Child Elements</span></span>  

 <span data-ttu-id="1b3e5-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1b3e5-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1b3e5-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1b3e5-115">Parent Elements</span></span>  
  
|<span data-ttu-id="1b3e5-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="1b3e5-116">Element</span></span>|<span data-ttu-id="1b3e5-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="1b3e5-117">Description</span></span>|  
|-------------|-----------------|  
|[\<scopes>](scopes.md)|<span data-ttu-id="1b3e5-118">Contiene una colección de elementos de configuración que especifican URI del ámbito personalizado que se pueden usar para filtrar puntos de conexión de servicio durante la consulta.</span><span class="sxs-lookup"><span data-stu-id="1b3e5-118">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1b3e5-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b3e5-119">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
