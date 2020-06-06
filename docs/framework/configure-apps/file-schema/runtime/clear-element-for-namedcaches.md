---
title: Elemento <clear> para <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
ms.openlocfilehash: bcc0e23f0c47ad3a98430e36da31d39612caa3c9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252758"
---
# <a name="clear-element-for-namedcaches"></a><span data-ttu-id="34d8c-102">Elemento \<clear> para \<namedCaches></span><span class="sxs-lookup"><span data-stu-id="34d8c-102">\<clear> Element for \<namedCaches></span></span>
<span data-ttu-id="34d8c-103">Borra todas `namedCache` las entradas de la `namedCaches` colección de una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="34d8c-103">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**  
  
## <a name="syntax"></a><span data-ttu-id="34d8c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="34d8c-104">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="Default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="34d8c-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="34d8c-105">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34d8c-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="34d8c-106">Attributes and Elements</span></span>  
 <span data-ttu-id="34d8c-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="34d8c-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34d8c-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="34d8c-108">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="34d8c-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="34d8c-109">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="34d8c-110">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="34d8c-110">Parent Elements</span></span>  
  
|<span data-ttu-id="34d8c-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="34d8c-111">Element</span></span>|<span data-ttu-id="34d8c-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="34d8c-112">Description</span></span>|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|<span data-ttu-id="34d8c-113">Contiene una colección de valores de configuración para las <xref:System.Runtime.Caching.MemoryCache> instancias con nombre.</span><span class="sxs-lookup"><span data-stu-id="34d8c-113">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34d8c-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="34d8c-114">Remarks</span></span>  
 <span data-ttu-id="34d8c-115">El `clear` elemento borra todas `namedCache` las entradas de la colección de caché con nombre de una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="34d8c-115">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="34d8c-116">Puede usar el `clear` elemento antes de usar el `add` elemento para agregar una nueva entrada de caché con nombre para estar seguro de que no hay otras memorias caché con nombre en la colección.</span><span class="sxs-lookup"><span data-stu-id="34d8c-116">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34d8c-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="34d8c-117">See also</span></span>

- [<span data-ttu-id="34d8c-118">\<namedCaches>(Elemento, configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="34d8c-118">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
