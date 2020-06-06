---
title: <add> de <scopes>
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: bcde6b18c34dccf1716c809dddeb45b1b4da90f0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398306"
---
# <a name="add-of-scopes"></a><span data-ttu-id="f76e9-102">\<add> de \<scopes></span><span class="sxs-lookup"><span data-stu-id="f76e9-102">\<add> of \<scopes></span></span>
<span data-ttu-id="f76e9-103">Agrega un Uri de ámbito personalizado que se puede utilizar para filtrar los extremos de servicio durante la consulta.</span><span class="sxs-lookup"><span data-stu-id="f76e9-103">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointDiscovery>**](endpointdiscovery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<scopes>**](scopes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="f76e9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f76e9-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f76e9-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f76e9-105">Attributes and Elements</span></span>  
 <span data-ttu-id="f76e9-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f76e9-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f76e9-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="f76e9-107">Attributes</span></span>  
  
|<span data-ttu-id="f76e9-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="f76e9-108">Attribute</span></span>|<span data-ttu-id="f76e9-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="f76e9-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f76e9-110">scope</span><span class="sxs-lookup"><span data-stu-id="f76e9-110">scope</span></span>|<span data-ttu-id="f76e9-111">URI que contiene información sobre el ámbito del punto de conexión que se puede usar en los criterios de coincidencia para buscar los servicios.</span><span class="sxs-lookup"><span data-stu-id="f76e9-111">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f76e9-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f76e9-112">Child Elements</span></span>  
 <span data-ttu-id="f76e9-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f76e9-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f76e9-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f76e9-114">Parent Elements</span></span>  
  
|<span data-ttu-id="f76e9-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="f76e9-115">Element</span></span>|<span data-ttu-id="f76e9-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="f76e9-116">Description</span></span>|  
|-------------|-----------------|  
|[\<scopes>](scopes.md)|<span data-ttu-id="f76e9-117">Contiene una colección de elementos de configuración que especifican URI del ámbito personalizado que se pueden usar para filtrar puntos de conexión de servicio durante la consulta.</span><span class="sxs-lookup"><span data-stu-id="f76e9-117">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f76e9-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f76e9-118">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
