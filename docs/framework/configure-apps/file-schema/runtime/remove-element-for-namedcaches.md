---
title: Elemento <remove> para <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
ms.openlocfilehash: 053e2776153489dfdd61547fdc039980646ae697
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59229776"
---
# <a name="remove-element-for-namedcaches"></a><span data-ttu-id="36d99-102">\<Quitar > (elemento) para \<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="36d99-102">\<remove> Element for \<namedCaches></span></span>
<span data-ttu-id="36d99-103">Quita una entrada de caché con nombre de la colección `namedCaches` de una caché en memoria.</span><span class="sxs-lookup"><span data-stu-id="36d99-103">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="36d99-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="36d99-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="36d99-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="36d99-105">\<memoryCache></span></span>  
<span data-ttu-id="36d99-106">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="36d99-106">\<namedCaches></span></span>  
<span data-ttu-id="36d99-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="36d99-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36d99-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="36d99-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="36d99-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="36d99-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="36d99-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="36d99-110">Attributes and Elements</span></span>  
 <span data-ttu-id="36d99-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="36d99-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="36d99-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="36d99-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="36d99-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="36d99-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="36d99-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="36d99-114">Parent Elements</span></span>  
  
|<span data-ttu-id="36d99-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="36d99-115">Element</span></span>|<span data-ttu-id="36d99-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="36d99-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36d99-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="36d99-117">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="36d99-118">Contiene una colección de valores de configuración para la instancia con nombre <xref:System.Runtime.Caching.MemoryCache> instancias.</span><span class="sxs-lookup"><span data-stu-id="36d99-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36d99-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="36d99-119">Remarks</span></span>  
 <span data-ttu-id="36d99-120">El `remove` elemento quita un `namedCache` entrada de la colección de caché con nombre de una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="36d99-120">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36d99-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="36d99-121">See also</span></span>

- [<span data-ttu-id="36d99-122">\<namedCaches > elemento (configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="36d99-122">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
