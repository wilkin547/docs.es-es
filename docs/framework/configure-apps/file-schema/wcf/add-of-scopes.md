---
title: <add> de <scopes>
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: bcde6b18c34dccf1716c809dddeb45b1b4da90f0
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398306"
---
# <a name="add-of-scopes"></a><span data-ttu-id="2f8ba-102">\<Agregar > de \<ámbitos ></span><span class="sxs-lookup"><span data-stu-id="2f8ba-102">\<add> of \<scopes></span></span>
<span data-ttu-id="2f8ba-103">Agrega un Uri de ámbito personalizado que se puede utilizar para filtrar los extremos de servicio durante la consulta.</span><span class="sxs-lookup"><span data-stu-id="2f8ba-103">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="2f8ba-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2f8ba-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2f8ba-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2f8ba-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2f8ba-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2f8ba-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="2f8ba-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2f8ba-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="2f8ba-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2f8ba-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="2f8ba-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointDiscovery**](endpointdiscovery.md)</span><span class="sxs-lookup"><span data-stu-id="2f8ba-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointDiscovery>**](endpointdiscovery.md)</span></span>\
<span data-ttu-id="2f8ba-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ámbitos >** ](scopes.md)</span><span class="sxs-lookup"><span data-stu-id="2f8ba-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<scopes>**](scopes.md)</span></span>\
<span data-ttu-id="2f8ba-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Agregar >**</span><span class="sxs-lookup"><span data-stu-id="2f8ba-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f8ba-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2f8ba-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2f8ba-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2f8ba-113">Attributes and Elements</span></span>  
 <span data-ttu-id="2f8ba-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2f8ba-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2f8ba-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="2f8ba-115">Attributes</span></span>  
  
|<span data-ttu-id="2f8ba-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="2f8ba-116">Attribute</span></span>|<span data-ttu-id="2f8ba-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="2f8ba-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2f8ba-118">scope</span><span class="sxs-lookup"><span data-stu-id="2f8ba-118">scope</span></span>|<span data-ttu-id="2f8ba-119">URI que contiene información sobre el ámbito del punto de conexión que se puede usar en los criterios de coincidencia para buscar los servicios.</span><span class="sxs-lookup"><span data-stu-id="2f8ba-119">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2f8ba-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2f8ba-120">Child Elements</span></span>  
 <span data-ttu-id="2f8ba-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2f8ba-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2f8ba-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2f8ba-122">Parent Elements</span></span>  
  
|<span data-ttu-id="2f8ba-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="2f8ba-123">Element</span></span>|<span data-ttu-id="2f8ba-124">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="2f8ba-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2f8ba-125">\<scopes></span><span class="sxs-lookup"><span data-stu-id="2f8ba-125">\<scopes></span></span>](scopes.md)|<span data-ttu-id="2f8ba-126">Contiene una colección de elementos de configuración que especifican URI del ámbito personalizado que se pueden usar para filtrar puntos de conexión de servicio durante la consulta.</span><span class="sxs-lookup"><span data-stu-id="2f8ba-126">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2f8ba-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f8ba-127">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
