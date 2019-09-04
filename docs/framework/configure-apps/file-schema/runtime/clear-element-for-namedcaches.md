---
title: Elemento <clear> para <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
ms.openlocfilehash: bcc0e23f0c47ad3a98430e36da31d39612caa3c9
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252758"
---
# <a name="clear-element-for-namedcaches"></a><span data-ttu-id="e369d-102">\<borrar > elemento de \<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="e369d-102">\<clear> Element for \<namedCaches></span></span>
<span data-ttu-id="e369d-103">Borra todas `namedCache` las entradas de la `namedCaches` colección de una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="e369d-103">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
<span data-ttu-id="e369d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e369d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e369d-105">&nbsp;&nbsp;[ **\<System. Runtime. Caching >** ](system-runtime-caching-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e369d-105">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span></span>\
<span data-ttu-id="e369d-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<memoryCache >** ](memorycache-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e369d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)</span></span>\
<span data-ttu-id="e369d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<namedCaches >** ](namedcaches-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e369d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)</span></span>\
<span data-ttu-id="e369d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<borrar >**</span><span class="sxs-lookup"><span data-stu-id="e369d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e369d-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e369d-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="Default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="e369d-110">Type</span><span class="sxs-lookup"><span data-stu-id="e369d-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e369d-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e369d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e369d-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e369d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e369d-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="e369d-113">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="e369d-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e369d-114">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="e369d-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e369d-115">Parent Elements</span></span>  
  
|<span data-ttu-id="e369d-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="e369d-116">Element</span></span>|<span data-ttu-id="e369d-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e369d-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e369d-118">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="e369d-118">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="e369d-119">Contiene una colección de valores de configuración para las <xref:System.Runtime.Caching.MemoryCache> instancias con nombre.</span><span class="sxs-lookup"><span data-stu-id="e369d-119">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e369d-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e369d-120">Remarks</span></span>  
 <span data-ttu-id="e369d-121">El `clear` elemento borra todas `namedCache` las entradas de la colección de caché con nombre de una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="e369d-121">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="e369d-122">Puede usar el `clear` elemento antes de usar el `add` elemento para agregar una nueva entrada de caché con nombre para estar seguro de que no hay otras memorias caché con nombre en la colección.</span><span class="sxs-lookup"><span data-stu-id="e369d-122">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e369d-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="e369d-123">See also</span></span>

- [<span data-ttu-id="e369d-124">\<namedCaches (elemento > (configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="e369d-124">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
