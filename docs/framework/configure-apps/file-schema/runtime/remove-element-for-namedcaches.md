---
title: '&lt;quitar&gt; (elemento) para &lt;namedCaches&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 6170b59e87948225708c9e697cba1542d756d2f4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltremovegt-element-for-ltnamedcachesgt"></a><span data-ttu-id="8bcaf-102">&lt;quitar&gt; (elemento) para &lt;namedCaches&gt;</span><span class="sxs-lookup"><span data-stu-id="8bcaf-102">&lt;remove&gt; Element for &lt;namedCaches&gt;</span></span>
<span data-ttu-id="8bcaf-103">Quita una entrada de caché con nombre de la colección `namedCaches` de una caché en memoria.</span><span class="sxs-lookup"><span data-stu-id="8bcaf-103">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="8bcaf-104">\<System.Runtime.Caching ></span><span class="sxs-lookup"><span data-stu-id="8bcaf-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="8bcaf-105">\<memoryCache ></span><span class="sxs-lookup"><span data-stu-id="8bcaf-105">\<memoryCache></span></span>  
<span data-ttu-id="8bcaf-106">\<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="8bcaf-106">\<namedCaches></span></span>  
<span data-ttu-id="8bcaf-107">\<Quitar ></span><span class="sxs-lookup"><span data-stu-id="8bcaf-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bcaf-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8bcaf-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="8bcaf-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="8bcaf-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8bcaf-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8bcaf-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8bcaf-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8bcaf-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8bcaf-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="8bcaf-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="8bcaf-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8bcaf-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="8bcaf-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8bcaf-114">Parent Elements</span></span>  
  
|<span data-ttu-id="8bcaf-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="8bcaf-115">Element</span></span>|<span data-ttu-id="8bcaf-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="8bcaf-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8bcaf-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="8bcaf-117">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="8bcaf-118">Contiene una colección de valores de configuración para la instancia con nombre <xref:System.Runtime.Caching.MemoryCache> instancias.</span><span class="sxs-lookup"><span data-stu-id="8bcaf-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8bcaf-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8bcaf-119">Remarks</span></span>  
 <span data-ttu-id="8bcaf-120">El `remove` elemento quita un `namedCache` entrada de la colección de caché con nombre de una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="8bcaf-120">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bcaf-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="8bcaf-121">See Also</span></span>  
 [<span data-ttu-id="8bcaf-122">\<namedCaches > Element (Cache Settings)</span><span class="sxs-lookup"><span data-stu-id="8bcaf-122">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
