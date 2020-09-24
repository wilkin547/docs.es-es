---
title: <add> de <scopes>
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: 1f5b5ea621614880286181c7584863ea024b3d04
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149015"
---
# <a name="add-of-scopes"></a><span data-ttu-id="ae1ea-102">\<add> de \<scopes></span><span class="sxs-lookup"><span data-stu-id="ae1ea-102">\<add> of \<scopes></span></span>

<span data-ttu-id="ae1ea-103">Agrega un Uri de ámbito personalizado que se puede utilizar para filtrar los extremos de servicio durante la consulta.</span><span class="sxs-lookup"><span data-stu-id="ae1ea-103">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointDiscovery>**](endpointdiscovery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<scopes>**](scopes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="ae1ea-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ae1ea-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ae1ea-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ae1ea-105">Attributes and Elements</span></span>  

 <span data-ttu-id="ae1ea-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ae1ea-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ae1ea-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="ae1ea-107">Attributes</span></span>  
  
|<span data-ttu-id="ae1ea-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="ae1ea-108">Attribute</span></span>|<span data-ttu-id="ae1ea-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="ae1ea-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ae1ea-110">scope</span><span class="sxs-lookup"><span data-stu-id="ae1ea-110">scope</span></span>|<span data-ttu-id="ae1ea-111">URI que contiene información sobre el ámbito del punto de conexión que se puede usar en los criterios de coincidencia para buscar los servicios.</span><span class="sxs-lookup"><span data-stu-id="ae1ea-111">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ae1ea-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ae1ea-112">Child Elements</span></span>  

 <span data-ttu-id="ae1ea-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ae1ea-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ae1ea-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ae1ea-114">Parent Elements</span></span>  
  
|<span data-ttu-id="ae1ea-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="ae1ea-115">Element</span></span>|<span data-ttu-id="ae1ea-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="ae1ea-116">Description</span></span>|  
|-------------|-----------------|  
|[\<scopes>](scopes.md)|<span data-ttu-id="ae1ea-117">Contiene una colección de elementos de configuración que especifican URI del ámbito personalizado que se pueden usar para filtrar puntos de conexión de servicio durante la consulta.</span><span class="sxs-lookup"><span data-stu-id="ae1ea-117">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ae1ea-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae1ea-118">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
