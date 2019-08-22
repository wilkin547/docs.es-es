---
title: Elemento <clear> para <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
ms.openlocfilehash: a90970e468359714bbbb858f3f300c26b5757a4d
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658858"
---
# <a name="clear-element-for-namedcaches"></a><span data-ttu-id="8021d-102">\<borrar > elemento de \<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="8021d-102">\<clear> Element for \<namedCaches></span></span>
<span data-ttu-id="8021d-103">Borra todas `namedCache` las entradas de la `namedCaches` colección de una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="8021d-103">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="8021d-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="8021d-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="8021d-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="8021d-105">\<memoryCache></span></span>  
<span data-ttu-id="8021d-106">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="8021d-106">\<namedCaches></span></span>  
<span data-ttu-id="8021d-107">\<add></span><span class="sxs-lookup"><span data-stu-id="8021d-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8021d-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8021d-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="Default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="8021d-109">Type</span><span class="sxs-lookup"><span data-stu-id="8021d-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8021d-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8021d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8021d-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8021d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8021d-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="8021d-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="8021d-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8021d-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="8021d-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8021d-114">Parent Elements</span></span>  
  
|<span data-ttu-id="8021d-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="8021d-115">Element</span></span>|<span data-ttu-id="8021d-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="8021d-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8021d-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="8021d-117">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="8021d-118">Contiene una colección de valores de configuración para las <xref:System.Runtime.Caching.MemoryCache> instancias con nombre.</span><span class="sxs-lookup"><span data-stu-id="8021d-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8021d-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8021d-119">Remarks</span></span>  
 <span data-ttu-id="8021d-120">El `clear` elemento borra todas `namedCache` las entradas de la colección de caché con nombre de una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="8021d-120">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="8021d-121">Puede usar el `clear` elemento antes de usar el `add` elemento para agregar una nueva entrada de caché con nombre para estar seguro de que no hay otras memorias caché con nombre en la colección.</span><span class="sxs-lookup"><span data-stu-id="8021d-121">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8021d-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="8021d-122">See also</span></span>

- [<span data-ttu-id="8021d-123">\<namedCaches (elemento > (configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="8021d-123">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
