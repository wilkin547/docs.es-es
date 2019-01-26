---
title: '&lt;quitar&gt; (elemento) para &lt;namedCaches&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
ms.openlocfilehash: ceeef00cb688c725cc595582fb6845b9e3fa9b92
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083397"
---
# <a name="ltremovegt-element-for-ltnamedcachesgt"></a><span data-ttu-id="cd0c4-102">&lt;quitar&gt; (elemento) para &lt;namedCaches&gt;</span><span class="sxs-lookup"><span data-stu-id="cd0c4-102">&lt;remove&gt; Element for &lt;namedCaches&gt;</span></span>
<span data-ttu-id="cd0c4-103">Quita una entrada de caché con nombre de la colección `namedCaches` de una caché en memoria.</span><span class="sxs-lookup"><span data-stu-id="cd0c4-103">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="cd0c4-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="cd0c4-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="cd0c4-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="cd0c4-105">\<memoryCache></span></span>  
<span data-ttu-id="cd0c4-106">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="cd0c4-106">\<namedCaches></span></span>  
<span data-ttu-id="cd0c4-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="cd0c4-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd0c4-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cd0c4-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="cd0c4-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="cd0c4-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cd0c4-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="cd0c4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="cd0c4-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="cd0c4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cd0c4-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="cd0c4-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="cd0c4-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="cd0c4-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="cd0c4-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="cd0c4-114">Parent Elements</span></span>  
  
|<span data-ttu-id="cd0c4-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="cd0c4-115">Element</span></span>|<span data-ttu-id="cd0c4-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="cd0c4-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cd0c4-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="cd0c4-117">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="cd0c4-118">Contiene una colección de valores de configuración para la instancia con nombre <xref:System.Runtime.Caching.MemoryCache> instancias.</span><span class="sxs-lookup"><span data-stu-id="cd0c4-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd0c4-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cd0c4-119">Remarks</span></span>  
 <span data-ttu-id="cd0c4-120">El `remove` elemento quita un `namedCache` entrada de la colección de caché con nombre de una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="cd0c4-120">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd0c4-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="cd0c4-121">See also</span></span>
- [<span data-ttu-id="cd0c4-122">\<namedCaches > elemento (configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="cd0c4-122">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
