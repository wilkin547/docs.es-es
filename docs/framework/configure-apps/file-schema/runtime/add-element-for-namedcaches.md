---
title: Elemento <add> para <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: 076d940e0c15cf48013480fef68b8fac42cf76e9
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252888"
---
# <a name="add-element-for-namedcaches"></a><span data-ttu-id="0b24c-102">\<Agregue > elemento para \<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="0b24c-102">\<add> Element for \<namedCaches></span></span>
<span data-ttu-id="0b24c-103">Agrega una `namedCache` entrada a la `namedCaches` colección de una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="0b24c-103">Adds a `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
<span data-ttu-id="0b24c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0b24c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0b24c-105">&nbsp;&nbsp;[ **\<System. Runtime. Caching >** ](system-runtime-caching-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="0b24c-105">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span></span>\
<span data-ttu-id="0b24c-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<memoryCache >** ](memorycache-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="0b24c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)</span></span>\
<span data-ttu-id="0b24c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<namedCaches >** ](namedcaches-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="0b24c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)</span></span>\
<span data-ttu-id="0b24c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Agregar >**</span><span class="sxs-lookup"><span data-stu-id="0b24c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b24c-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0b24c-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <add name="Default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="0b24c-110">Type</span><span class="sxs-lookup"><span data-stu-id="0b24c-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0b24c-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0b24c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0b24c-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0b24c-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0b24c-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="0b24c-113">Attributes</span></span>  
  
|<span data-ttu-id="0b24c-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="0b24c-114">Attribute</span></span>|<span data-ttu-id="0b24c-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0b24c-115">Description</span></span>|  
|-|-|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="0b24c-116">Valor entero que especifica el tamaño máximo permitido (en megabytes) que puede alcanzar una instancia de un <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="0b24c-116">An integer value that specifies the maximum allowed size (in megabytes) that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="0b24c-117">El valor predeterminado es 0, lo que significa que <xref:System.Runtime.Caching.MemoryCache> se utiliza de forma predeterminada la heurística de ajuste automático de tamaño de la clase.</span><span class="sxs-lookup"><span data-stu-id="0b24c-117">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="0b24c-118">Nombre de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="0b24c-118">The name of the cache.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="0b24c-119">Un valor entero comprendido entre 0 y 100 que especifica el porcentaje máximo de memoria del equipo instalado físicamente que la memoria caché puede consumir.</span><span class="sxs-lookup"><span data-stu-id="0b24c-119">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="0b24c-120">El valor predeterminado es 0, lo que significa que <xref:System.Runtime.Caching.MemoryCache> se utiliza de forma predeterminada la heurística de ajuste automático de tamaño de la clase.</span><span class="sxs-lookup"><span data-stu-id="0b24c-120">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="0b24c-121">Valor que indica el intervalo de tiempo después del cual la implementación de caché compara la carga de memoria actual con los límites de memoria absoluto y de porcentaje que están establecidos para la instancia de caché.</span><span class="sxs-lookup"><span data-stu-id="0b24c-121">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="0b24c-122">Este valor se especifica en formato "HH: MM: SS".</span><span class="sxs-lookup"><span data-stu-id="0b24c-122">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0b24c-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0b24c-123">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="0b24c-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0b24c-124">Parent Elements</span></span>  
  
|<span data-ttu-id="0b24c-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="0b24c-125">Element</span></span>|<span data-ttu-id="0b24c-126">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0b24c-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0b24c-127">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="0b24c-127">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="0b24c-128">Contiene una colección de valores de configuración para las <xref:System.Runtime.Caching.MemoryCache> instancias con nombre.</span><span class="sxs-lookup"><span data-stu-id="0b24c-128">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b24c-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0b24c-129">Remarks</span></span>  
 <span data-ttu-id="0b24c-130">El `add` elemento agrega una entrada a la `namedCaches` colección para una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="0b24c-130">The `add` element adds an entry to the `namedCaches` collection for a memory cache.</span></span> <span data-ttu-id="0b24c-131">Puede usar el elemento [Clear](clear-element-for-namedcaches.md) antes de usar el `add` elemento para asegurarse de que no hay otras memorias caché con nombre en la colección.</span><span class="sxs-lookup"><span data-stu-id="0b24c-131">You can use the [clear](clear-element-for-namedcaches.md) element before you use the `add` element to be certain that there are no other named caches in the collection.</span></span> <span data-ttu-id="0b24c-132">Este elemento se puede utilizar en el archivo Machine. config y en el archivo Web. config.</span><span class="sxs-lookup"><span data-stu-id="0b24c-132">This element can be used in the machine.config file and in the Web.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b24c-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0b24c-133">Example</span></span>  
 <span data-ttu-id="0b24c-134">En el ejemplo siguiente se muestra cómo definir la configuración de `namedCache` la entrada predeterminada `namedCaches` en la colección para una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="0b24c-134">The following example shows how to define settings for the default `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="Default"   
               cacheMemoryLimitMegabytes="0"   
               physicalMemoryPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0b24c-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b24c-135">See also</span></span>

- [<span data-ttu-id="0b24c-136">\<namedCaches (elemento > (configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="0b24c-136">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
