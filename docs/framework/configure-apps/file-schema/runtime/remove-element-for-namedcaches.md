---
title: Elemento <remove> para <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
ms.openlocfilehash: 991ad0eb9c04c27ded4d566115107ac7b47a71e1
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252335"
---
# <a name="remove-element-for-namedcaches"></a><span data-ttu-id="0f612-102">\<Quite > elemento de \<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="0f612-102">\<remove> Element for \<namedCaches></span></span>
<span data-ttu-id="0f612-103">Quita una entrada de caché con nombre de la colección `namedCaches` de una caché en memoria.</span><span class="sxs-lookup"><span data-stu-id="0f612-103">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
<span data-ttu-id="0f612-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0f612-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0f612-105">&nbsp;&nbsp;[ **\<System. Runtime. Caching >** ](system-runtime-caching-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="0f612-105">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span></span>\
<span data-ttu-id="0f612-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<memoryCache >** ](memorycache-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="0f612-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)</span></span>\
<span data-ttu-id="0f612-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<namedCaches >** ](namedcaches-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="0f612-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)</span></span>\
<span data-ttu-id="0f612-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<quitar >**</span><span class="sxs-lookup"><span data-stu-id="0f612-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f612-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0f612-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="0f612-110">Type</span><span class="sxs-lookup"><span data-stu-id="0f612-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0f612-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0f612-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0f612-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0f612-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0f612-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="0f612-113">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="0f612-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0f612-114">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="0f612-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0f612-115">Parent Elements</span></span>  
  
|<span data-ttu-id="0f612-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="0f612-116">Element</span></span>|<span data-ttu-id="0f612-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0f612-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0f612-118">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="0f612-118">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="0f612-119">Contiene una colección de valores de configuración para las <xref:System.Runtime.Caching.MemoryCache> instancias con nombre.</span><span class="sxs-lookup"><span data-stu-id="0f612-119">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f612-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0f612-120">Remarks</span></span>  
 <span data-ttu-id="0f612-121">El `remove` elemento quita una `namedCache` entrada de la colección de caché con nombre de una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="0f612-121">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f612-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f612-122">See also</span></span>

- [<span data-ttu-id="0f612-123">\<namedCaches (elemento > (configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="0f612-123">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
