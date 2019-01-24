---
title: '&lt;timeOuts&gt;'
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: 42f4db1d954834cbfa3c526328cca45443751506
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54629663"
---
# <a name="lttimeoutsgt"></a><span data-ttu-id="44d54-102">&lt;timeOuts&gt;</span><span class="sxs-lookup"><span data-stu-id="44d54-102">&lt;timeOuts&gt;</span></span>
<span data-ttu-id="44d54-103">Representa un elemento de configuración que especifica el intervalo de tiempo permitido para que el host del servicio abra o cierre.</span><span class="sxs-lookup"><span data-stu-id="44d54-103">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
 <span data-ttu-id="44d54-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="44d54-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="44d54-105">\<client></span><span class="sxs-lookup"><span data-stu-id="44d54-105">\<client></span></span>  
<span data-ttu-id="44d54-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="44d54-106">\<endpoint></span></span>  
<span data-ttu-id="44d54-107">\<host ></span><span class="sxs-lookup"><span data-stu-id="44d54-107">\<host></span></span>  
<span data-ttu-id="44d54-108">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="44d54-108">\<timeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44d54-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="44d54-109">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="44d54-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="44d54-110">Attributes and Elements</span></span>  
 <span data-ttu-id="44d54-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="44d54-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="44d54-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="44d54-112">Attributes</span></span>  
  
|<span data-ttu-id="44d54-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="44d54-113">Attribute</span></span>|<span data-ttu-id="44d54-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="44d54-114">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="44d54-115">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo permitido para que el host del servicio se cierre.</span><span class="sxs-lookup"><span data-stu-id="44d54-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="44d54-116">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo permitido para que el host del servicio se abra.</span><span class="sxs-lookup"><span data-stu-id="44d54-116">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="44d54-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="44d54-117">Child Elements</span></span>  
 <span data-ttu-id="44d54-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="44d54-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="44d54-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="44d54-119">Parent Elements</span></span>  
  
|<span data-ttu-id="44d54-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="44d54-120">Element</span></span>|<span data-ttu-id="44d54-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="44d54-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="44d54-122">\<host></span><span class="sxs-lookup"><span data-stu-id="44d54-122">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="44d54-123">Un elemento de configuración que especifica valores para un host de servicio.</span><span class="sxs-lookup"><span data-stu-id="44d54-123">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="44d54-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="44d54-124">See also</span></span>
- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="44d54-125">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="44d54-125">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
