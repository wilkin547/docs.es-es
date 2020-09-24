---
title: Elemento <remove> para <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
ms.openlocfilehash: c8ad5a0ce6d7a3059943b3962b9255385cea6e15
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183993"
---
# <a name="remove-element-for-namedcaches"></a><span data-ttu-id="3f45b-102">Elemento \<remove> para \<namedCaches></span><span class="sxs-lookup"><span data-stu-id="3f45b-102">\<remove> Element for \<namedCaches></span></span>

<span data-ttu-id="3f45b-103">Quita una entrada de caché con nombre de la colección `namedCaches` de una caché en memoria.</span><span class="sxs-lookup"><span data-stu-id="3f45b-103">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  
  
## <a name="syntax"></a><span data-ttu-id="3f45b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3f45b-104">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="3f45b-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="3f45b-105">Type</span></span>  

 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3f45b-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3f45b-106">Attributes and Elements</span></span>  

 <span data-ttu-id="3f45b-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3f45b-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3f45b-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="3f45b-108">Attributes</span></span>  

 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="3f45b-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3f45b-109">Child Elements</span></span>  

 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="3f45b-110">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3f45b-110">Parent Elements</span></span>  
  
|<span data-ttu-id="3f45b-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="3f45b-111">Element</span></span>|<span data-ttu-id="3f45b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="3f45b-112">Description</span></span>|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|<span data-ttu-id="3f45b-113">Contiene una colección de valores de configuración para las <xref:System.Runtime.Caching.MemoryCache> instancias con nombre.</span><span class="sxs-lookup"><span data-stu-id="3f45b-113">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f45b-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3f45b-114">Remarks</span></span>  

 <span data-ttu-id="3f45b-115">El `remove` elemento quita una `namedCache` entrada de la colección de caché con nombre de una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="3f45b-115">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f45b-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3f45b-116">See also</span></span>

- [<span data-ttu-id="3f45b-117">\<namedCaches> (Elemento, configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="3f45b-117">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
