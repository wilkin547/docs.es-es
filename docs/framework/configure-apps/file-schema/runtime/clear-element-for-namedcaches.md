---
title: '&lt;Borrar&gt; (elemento) para &lt;namedCaches&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 0819141b2135a2de99a2801a1888f7b0e1cd19fc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltcleargt-element-for-ltnamedcachesgt"></a><span data-ttu-id="b5a9e-102">&lt;Borrar&gt; (elemento) para &lt;namedCaches&gt;</span><span class="sxs-lookup"><span data-stu-id="b5a9e-102">&lt;clear&gt; Element for &lt;namedCaches&gt;</span></span>
<span data-ttu-id="b5a9e-103">Todos los borra `namedCache` entradas en el `namedCaches` colección de una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="b5a9e-103">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="b5a9e-104">\<System.Runtime.Caching ></span><span class="sxs-lookup"><span data-stu-id="b5a9e-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="b5a9e-105">\<memoryCache ></span><span class="sxs-lookup"><span data-stu-id="b5a9e-105">\<memoryCache></span></span>  
<span data-ttu-id="b5a9e-106">\<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="b5a9e-106">\<namedCaches></span></span>  
<span data-ttu-id="b5a9e-107">\<add></span><span class="sxs-lookup"><span data-stu-id="b5a9e-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5a9e-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b5a9e-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="b5a9e-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="b5a9e-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b5a9e-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b5a9e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b5a9e-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b5a9e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b5a9e-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="b5a9e-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="b5a9e-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b5a9e-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="b5a9e-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b5a9e-114">Parent Elements</span></span>  
  
|<span data-ttu-id="b5a9e-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="b5a9e-115">Element</span></span>|<span data-ttu-id="b5a9e-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="b5a9e-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b5a9e-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="b5a9e-117">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="b5a9e-118">Contiene una colección de valores de configuración para la instancia con nombre <xref:System.Runtime.Caching.MemoryCache> instancias.</span><span class="sxs-lookup"><span data-stu-id="b5a9e-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b5a9e-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b5a9e-119">Remarks</span></span>  
 <span data-ttu-id="b5a9e-120">El `clear` elemento borra todos los `namedCache` las entradas de la colección de caché con nombre de una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="b5a9e-120">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="b5a9e-121">Puede usar el `clear` elemento antes de usar el `add` elemento que se va a agregar una nueva entrada de caché con nombre para estar seguro de que no hay ninguna otra nombrar cachés en la colección.</span><span class="sxs-lookup"><span data-stu-id="b5a9e-121">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5a9e-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5a9e-122">See Also</span></span>  
 [<span data-ttu-id="b5a9e-123">\<namedCaches > Element (Cache Settings)</span><span class="sxs-lookup"><span data-stu-id="b5a9e-123">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
