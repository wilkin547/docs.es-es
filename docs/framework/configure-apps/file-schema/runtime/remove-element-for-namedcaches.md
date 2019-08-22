---
title: Elemento <remove> para <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
ms.openlocfilehash: e9b126cee83bc8109606d915ea48549beea970c9
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663472"
---
# <a name="remove-element-for-namedcaches"></a><span data-ttu-id="d9fee-102">\<Quite > elemento de \<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="d9fee-102">\<remove> Element for \<namedCaches></span></span>
<span data-ttu-id="d9fee-103">Quita una entrada de caché con nombre de la colección `namedCaches` de una caché en memoria.</span><span class="sxs-lookup"><span data-stu-id="d9fee-103">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="d9fee-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="d9fee-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="d9fee-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="d9fee-105">\<memoryCache></span></span>  
<span data-ttu-id="d9fee-106">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="d9fee-106">\<namedCaches></span></span>  
<span data-ttu-id="d9fee-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="d9fee-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9fee-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d9fee-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="d9fee-109">Type</span><span class="sxs-lookup"><span data-stu-id="d9fee-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d9fee-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d9fee-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d9fee-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d9fee-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d9fee-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="d9fee-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="d9fee-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d9fee-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="d9fee-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d9fee-114">Parent Elements</span></span>  
  
|<span data-ttu-id="d9fee-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="d9fee-115">Element</span></span>|<span data-ttu-id="d9fee-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d9fee-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d9fee-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="d9fee-117">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="d9fee-118">Contiene una colección de valores de configuración para las <xref:System.Runtime.Caching.MemoryCache> instancias con nombre.</span><span class="sxs-lookup"><span data-stu-id="d9fee-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9fee-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d9fee-119">Remarks</span></span>  
 <span data-ttu-id="d9fee-120">El `remove` elemento quita una `namedCache` entrada de la colección de caché con nombre de una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="d9fee-120">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9fee-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9fee-121">See also</span></span>

- [<span data-ttu-id="d9fee-122">\<namedCaches (elemento > (configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="d9fee-122">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
