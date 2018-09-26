---
title: '&lt;Borrar&gt; (elemento) para &lt;namedCaches&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 17043cdd4bcabf2e5e14c7b9c31b8c1747d2c866
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47171951"
---
# <a name="ltcleargt-element-for-ltnamedcachesgt"></a><span data-ttu-id="8a51a-102">&lt;Borrar&gt; (elemento) para &lt;namedCaches&gt;</span><span class="sxs-lookup"><span data-stu-id="8a51a-102">&lt;clear&gt; Element for &lt;namedCaches&gt;</span></span>
<span data-ttu-id="8a51a-103">Todos los borra `namedCache` entradas en el `namedCaches` colección de una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="8a51a-103">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="8a51a-104">\<System.Runtime.Caching ></span><span class="sxs-lookup"><span data-stu-id="8a51a-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="8a51a-105">\<memoryCache ></span><span class="sxs-lookup"><span data-stu-id="8a51a-105">\<memoryCache></span></span>  
<span data-ttu-id="8a51a-106">\<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="8a51a-106">\<namedCaches></span></span>  
<span data-ttu-id="8a51a-107">\<add></span><span class="sxs-lookup"><span data-stu-id="8a51a-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a51a-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8a51a-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="8a51a-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="8a51a-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8a51a-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8a51a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8a51a-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8a51a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8a51a-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="8a51a-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="8a51a-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8a51a-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="8a51a-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8a51a-114">Parent Elements</span></span>  
  
|<span data-ttu-id="8a51a-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="8a51a-115">Element</span></span>|<span data-ttu-id="8a51a-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a51a-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8a51a-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="8a51a-117">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="8a51a-118">Contiene una colección de valores de configuración para la instancia con nombre <xref:System.Runtime.Caching.MemoryCache> instancias.</span><span class="sxs-lookup"><span data-stu-id="8a51a-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a51a-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8a51a-119">Remarks</span></span>  
 <span data-ttu-id="8a51a-120">El `clear` elemento borra todo `namedCache` entradas de la colección de caché con nombre de una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="8a51a-120">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="8a51a-121">Puede usar el `clear` elemento antes de usar el `add` elemento para agregar una nueva entrada de caché con nombre para estar seguro de que hay ninguna otra denominada caché en la colección.</span><span class="sxs-lookup"><span data-stu-id="8a51a-121">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a51a-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a51a-122">See Also</span></span>  
 [<span data-ttu-id="8a51a-123">\<namedCaches > elemento (configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="8a51a-123">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
