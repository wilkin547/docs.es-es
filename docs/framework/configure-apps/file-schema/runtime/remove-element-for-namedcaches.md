---
title: <remove> (elemento) para <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
ms.openlocfilehash: 053e2776153489dfdd61547fdc039980646ae697
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59229776"
---
# <a name="remove-element-for-namedcaches"></a><span data-ttu-id="c56f5-102">\<Quitar > (elemento) para \<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="c56f5-102">\<remove> Element for \<namedCaches></span></span>
<span data-ttu-id="c56f5-103">Quita una entrada de caché con nombre de la colección `namedCaches` de una caché en memoria.</span><span class="sxs-lookup"><span data-stu-id="c56f5-103">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="c56f5-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="c56f5-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="c56f5-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="c56f5-105">\<memoryCache></span></span>  
<span data-ttu-id="c56f5-106">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="c56f5-106">\<namedCaches></span></span>  
<span data-ttu-id="c56f5-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="c56f5-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c56f5-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c56f5-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="c56f5-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="c56f5-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c56f5-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c56f5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c56f5-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c56f5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c56f5-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="c56f5-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="c56f5-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c56f5-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="c56f5-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c56f5-114">Parent Elements</span></span>  
  
|<span data-ttu-id="c56f5-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="c56f5-115">Element</span></span>|<span data-ttu-id="c56f5-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="c56f5-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c56f5-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="c56f5-117">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="c56f5-118">Contiene una colección de valores de configuración para la instancia con nombre <xref:System.Runtime.Caching.MemoryCache> instancias.</span><span class="sxs-lookup"><span data-stu-id="c56f5-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c56f5-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c56f5-119">Remarks</span></span>  
 <span data-ttu-id="c56f5-120">El `remove` elemento quita un `namedCache` entrada de la colección de caché con nombre de una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="c56f5-120">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c56f5-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="c56f5-121">See also</span></span>

- [<span data-ttu-id="c56f5-122">\<namedCaches > elemento (configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="c56f5-122">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
