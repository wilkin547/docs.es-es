---
description: 'Más información sobre: <remove> elemento para <namedCaches>'
title: Elemento <remove> para <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
ms.openlocfilehash: 5b39fc596735d746c52cdb5623962f5b9952fa3e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802467"
---
# <a name="remove-element-for-namedcaches"></a><span data-ttu-id="ec4ed-103">Elemento \<remove> para \<namedCaches></span><span class="sxs-lookup"><span data-stu-id="ec4ed-103">\<remove> Element for \<namedCaches></span></span>

<span data-ttu-id="ec4ed-104">Quita una entrada de caché con nombre de la colección `namedCaches` de una caché en memoria.</span><span class="sxs-lookup"><span data-stu-id="ec4ed-104">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  
  
## <a name="syntax"></a><span data-ttu-id="ec4ed-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ec4ed-105">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="ec4ed-106">Tipo</span><span class="sxs-lookup"><span data-stu-id="ec4ed-106">Type</span></span>  

 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ec4ed-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ec4ed-107">Attributes and Elements</span></span>  

 <span data-ttu-id="ec4ed-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ec4ed-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ec4ed-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="ec4ed-109">Attributes</span></span>  

 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="ec4ed-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ec4ed-110">Child Elements</span></span>  

 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="ec4ed-111">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ec4ed-111">Parent Elements</span></span>  
  
|<span data-ttu-id="ec4ed-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="ec4ed-112">Element</span></span>|<span data-ttu-id="ec4ed-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec4ed-113">Description</span></span>|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|<span data-ttu-id="ec4ed-114">Contiene una colección de valores de configuración para las <xref:System.Runtime.Caching.MemoryCache> instancias con nombre.</span><span class="sxs-lookup"><span data-stu-id="ec4ed-114">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec4ed-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ec4ed-115">Remarks</span></span>  

 <span data-ttu-id="ec4ed-116">El `remove` elemento quita una `namedCache` entrada de la colección de caché con nombre de una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="ec4ed-116">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec4ed-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec4ed-117">See also</span></span>

- [<span data-ttu-id="ec4ed-118">\<namedCaches> (Elemento, configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="ec4ed-118">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
