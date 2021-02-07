---
description: 'Más información sobre: <clear> elemento para <namedCaches>'
title: Elemento <clear> para <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
ms.openlocfilehash: 9d883c102fc76875ce155f353920f730bf9700c4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99719102"
---
# <a name="clear-element-for-namedcaches"></a><span data-ttu-id="e432a-103">Elemento \<clear> para \<namedCaches></span><span class="sxs-lookup"><span data-stu-id="e432a-103">\<clear> Element for \<namedCaches></span></span>

<span data-ttu-id="e432a-104">Borra todas `namedCache` las entradas de la `namedCaches` colección de una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="e432a-104">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**  
  
## <a name="syntax"></a><span data-ttu-id="e432a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e432a-105">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="Default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="e432a-106">Tipo</span><span class="sxs-lookup"><span data-stu-id="e432a-106">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e432a-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e432a-107">Attributes and Elements</span></span>  

 <span data-ttu-id="e432a-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e432a-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e432a-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="e432a-109">Attributes</span></span>  

 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="e432a-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e432a-110">Child Elements</span></span>  

 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="e432a-111">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e432a-111">Parent Elements</span></span>  
  
|<span data-ttu-id="e432a-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="e432a-112">Element</span></span>|<span data-ttu-id="e432a-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="e432a-113">Description</span></span>|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|<span data-ttu-id="e432a-114">Contiene una colección de valores de configuración para las <xref:System.Runtime.Caching.MemoryCache> instancias con nombre.</span><span class="sxs-lookup"><span data-stu-id="e432a-114">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e432a-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e432a-115">Remarks</span></span>  

 <span data-ttu-id="e432a-116">El `clear` elemento borra todas `namedCache` las entradas de la colección de caché con nombre de una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="e432a-116">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="e432a-117">Puede usar el `clear` elemento antes de usar el `add` elemento para agregar una nueva entrada de caché con nombre para estar seguro de que no hay otras memorias caché con nombre en la colección.</span><span class="sxs-lookup"><span data-stu-id="e432a-117">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e432a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e432a-118">See also</span></span>

- [<span data-ttu-id="e432a-119">\<namedCaches> (Elemento, configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="e432a-119">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
